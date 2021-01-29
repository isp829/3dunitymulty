사용할 아이템 만들기      
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-1.PNG" width="50%">  

* PlayerManager 스크립트를 수정해주자.  
* SpawnManager로부터 Spawnpoint를 받아와서 인스턴스 생성할때 그 위치에 생성하도록 해주자.  

--------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-2.PNG" width="50%">  

* SpawnPoint 프리펩에 SpawnPoint 스크립트를 넣어주고 시작하면 사라지는 Graphics에 capsule을 넣어준다.   

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-3.PNG" width="50%">  

* SpwanManager에 SpawnManager스크립트를 넣어준다.  
* Spawnpoint는 아까 코드에서 Spawnpoint스크립트를 가진 모든 요소들이 자동으로 할당되므로 일일이 넣어줄 필요없다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-4.PNG" width="50%"><img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-5.PNG" width="50%">    

* 5개를 같이 실행해서 여러번 테스트해봤다.  
* 각자 5개 모두 랜덤하게 시작지점을 가지는걸 볼 수 있다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-6.PNG" width="50%">  
 
* 

----------------------------------   
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Photon.Pun;
using Hashtable = ExitGames.Client.Photon.Hashtable;//현재 게임 클라이언트가 쓰는 해쉬테이블 사용
using Photon.Realtime;

public class PlayerController : MonoBehaviourPunCallbacks/*다른 포톤 반응 받아들이기*/,IDamageable//인터페이스 불러오기
{
    [SerializeField] float mouseSensitivity, sprintSpeed, walkSpeed, jumpForce, smoothTime;
    [SerializeField] GameObject cameraHolder;
    [SerializeField] Item[] items;
    public int itemIndex;
    public int previousItemIndex=-1;//기본 아이템 값 없도록
    //마우스감도 뛰는속도 걷는속도 점프힘 뛰기걷기바꿀때 가속시간
    float verticalLookRotation;
    bool grounded;//점프를 위한 바닥체크
    Vector3 smoothMoveVelocity;
    Vector3 moveAmount;//실제 이동거리

    Rigidbody rb;
    PhotonView PV;

    const float maxHealth = 100f;//최대체력
    float currentHealth = maxHealth;//시작체력

    PlayerManager playerManager;
    //플레이어 매니저 선언

    void Awake()
    {
        rb = GetComponent<Rigidbody>();
        PV = GetComponent<PhotonView>();
        playerManager = PhotonView.Find((int)PV.InstantiationData[0]).GetComponent<PlayerManager>();
        //플레이어 매니저 정의 PlayerManager에서 생성한 인스턴스를 찾게된다.  
    }

    void Start()
    {
        if (PV.IsMine)
        {
            EquipItem(0);//시작하고 내 포톤뷰면 1번 아이템끼기(2번 아이템은 번호상 1이다)
        }
        else
        {
            Destroy(GetComponentInChildren<Camera>().gameObject);
            //내꺼 아니면 카메라 없애기
            Destroy(rb);
            //내거아니면 리지드 바디 없애주기
        }
    }

    void Update()
    {
        if (!PV.IsMine)
            return;//내꺼아니면 작동안함
        Look();
        Move();
        Jump();
        for (int i = 0; i < items.Length; i++)
        {
            if (Input.GetKeyDown((i + 1).ToString()))//ToString으로 하면 입력받는 String을 숫자로 표현할 수 있다. 
            {
                EquipItem(i);
                //숫자키 1 2번으로 아이템 장착 가능
                break;
            }
        }
        if (Input.GetAxisRaw("Mouse ScrollWheel") > 0f)//마우스 스크롤 움직이면
        {
            if (itemIndex >= items.Length - 1)//만약 아이템 목록끝에 다다르면
            {
                EquipItem(0);//맨처음 아이템으로
            }
            else
            {
                EquipItem(itemIndex + 1);//아니면 다음 아이템으로
            }
        }
        else if (Input.GetAxisRaw("Mouse ScrollWheel") < 0f)//마우스 스크롤 반대로 움직이면
        {
            if (itemIndex <= 0)//아이템 목록 맨처음보다 뒤로가면?
            {
                EquipItem(items.Length - 1);//맨 끝 아이템으로
            }
            else 
            { 
                EquipItem(itemIndex - 1);//아니면 이전 아이템으로
            }
        }

        if (Input.GetMouseButtonDown(0))//마우스 좌클릭시
        {
            items[itemIndex].Use();//들고있는 아이템 사용
        }
    }
   
    void Look() 
    {
        transform.Rotate(Vector3.up * Input.GetAxis("Mouse X") * mouseSensitivity);
        //마우스 움직이는 정도*민감도만큼 각도 움직이기
        verticalLookRotation += Input.GetAxis("Mouse Y") * mouseSensitivity;
        //마우스 움직이는 정도*민감도만큼 각도 값 받기
        verticalLookRotation = Mathf.Clamp(verticalLookRotation, -90f, 90f);
        //y축 -90도에서 90도만 값으로 받음
        cameraHolder.transform.localEulerAngles = Vector3.left * verticalLookRotation;
        //받은 각도로 카메라도 돌려줌
    }

    void Move()
    {
        Vector3 moveDir = new Vector3(Input.GetAxisRaw("Horizontal"), 0, Input.GetAxisRaw("Vertical")).normalized;
        //벡더방향을 가지지만 크기는 1로 노말라이즈
        moveAmount = Vector3.SmoothDamp(moveAmount, moveDir * (Input.GetKey(KeyCode.LeftShift) ? sprintSpeed : walkSpeed), ref smoothMoveVelocity, smoothTime);
        //왼쪽 쉬프트가 누르면 뛰는속도, 나머지는 걷는속도로하기
        //smoothTime만큼에 걸쳐서 이동해주기. 
    }

    void Jump()
    {
        if (Input.GetKeyDown(KeyCode.Space) && grounded)//땅위에서 스페이스바 누르면
        {
            rb.AddForce(transform.up * jumpForce);//점프력만큼위로 힘받음
        }
    }

    void EquipItem(int _index)
    {
        if (_index == previousItemIndex)
            return;//입력받은 숫자가 아까 받은 숫자랑 똑같으면 아무일도 안해준다.  
        itemIndex = _index;
        items[itemIndex].itemGameObject.SetActive(true);//itemIndex번쨰 아이템 on
        if (previousItemIndex != -1)//만약 초기 상태가 아니라면
        {
            items[previousItemIndex].itemGameObject.SetActive(false);
            //내가 아까 꼈던 아이템은 off
        }
        previousItemIndex = itemIndex;//무한 사이클

        if (PV.IsMine)
        {
            Hashtable hash = new Hashtable();
            hash.Add("itemIndex", itemIndex);
            //이제 hash[itemindex]가 호출되면 현재 아이템번호가 호출된다.    
            PhotonNetwork.LocalPlayer.SetCustomProperties(hash);
            //포톤으로 모든 사람에게 내가 현재끼고 있는 아이템 번호를 알려준다.  
        }
    }

    public override void OnPlayerPropertiesUpdate(Player targetPlayer, Hashtable changedProps)
    //다른 플레이어의 아이템 번호 받아들이기
    {
        if (!PV.IsMine && targetPlayer == PV.Owner)//내꺼가 아니라 다른사람꺼일때
        {
            EquipItem((int)changedProps["itemIndex"]);
            //끼고있는 아이템 정보 받아들이기
        }
    }

    public void SetGroundedState(bool _grounded)
    {
        grounded = _grounded;
    }

    void FixedUpdate()
    {
        if (!PV.IsMine)
            return;//내꺼아니면 작동안함
        rb.MovePosition(rb.position + transform.TransformDirection(moveAmount) * Time.fixedDeltaTime);
        //이동하는거는 계산 끝난 moveAmount만큼만 고정된시간(0.2초)마다에 맞춰서
    }

    public void TakeDamage(float damage)
    {
        //IDamageable 인터페이스에 있는 함수 재정의
        PV.RPC("RPC_TakeDamage", RpcTarget.All,damage);
        //피해를 입힌사람이 해당 이름가진 함수를 RpcTaget(지금은 모든 플레이어)에게 적용되도록 호출
        //Rpc를 통해 받은 피해를 모두에게 전달한다
    }

    [PunRPC]//Pun Remote Procedure Call의 약자로써 원격제어를 통해 함수를 실행시키는 기능이다.  
    void RPC_TakeDamage(float damage)
    {
        //모두에게 전달됨
        if (!PV.IsMine)
            return;//피해입은놈 아니면 실행안됨
        Debug.Log("took damage " + damage);
        currentHealth -= damage;
        if (currentHealth <= 0)
        {
            Die();
        }
    }

    void Die()
    {
        playerManager.Die();
    }
}

```

* PlayerController 스크립트의 전문이다.

---------------------------  
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Photon.Pun;
using System.IO;//path사용위해

public class PlayerManager : MonoBehaviour
{
    PhotonView PV;//포톤뷰 선언
    GameObject controller;//PlayerController로쓰이는 캡슐

    void Awake()
    {
        PV = GetComponent<PhotonView>();   
    }

    void Start()
    {
        if (PV.IsMine)//내 포톤 네트워크이면
        {
            CreateController();//플레이어 컨트롤러 붙여준다. 
        }
    }
    void CreateController()//플레이어 컨트롤러 만들기
    {
        Debug.Log("Instantiated Player Controller");
        controller = PhotonNetwork.Instantiate(Path.Combine("PhotonPrefabs", "PlayerController"), Vector3.zero, Quaternion.identity,0,new object[] { PV.ViewID});
        //포톤 프리펩에 있는 플레이어 컨트롤러를 저 위치에 저 각도로 만들어주기
        //포톤 뷰를 가지고있는 새로운 물체를 만들어주기
    }

    public void Die()
    {
        PhotonNetwork.Destroy(controller);
    }
}

```

* PlayerManager 스크립트의 전문이다.

---------------------------  
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Spawnpoint : MonoBehaviour
{
    [SerializeField] GameObject graphics;

    private void Awake()
    {
        graphics.SetActive(false);   
        //스폰포인트 위치값만 남기고 캡슐이랑 큐브는 지우기
    }
}

```

* Spawnpoint 스크립트의 전문이다.

---------------------------  
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SpawnManager : MonoBehaviour
{
    public static SpawnManager Instance;
    //다른곳에서 쓰기 쉽게 정적 클래스 선언
    [SerializeField] Spawnpoint[] spawnpoints;

    void Awake()
    {
        Instance = this;
        spawnpoints = GetComponentsInChildren<Spawnpoint>();
    }

    public Transform GetSpawnpoint()
    {
        return spawnpoints[Random.Range(0, spawnpoints.Length)].transform;
        //랜덤하게 스폰 지점 정해주기.
    }
}

```

* SpwanManager 스크립트의 전문이다.

---------------------------  

[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture6-5.md)  
-----------------------------   
