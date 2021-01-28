사용할 아이템 만들기      
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-1.PNG" width="50%">  

* 일단 총으로 사용하는 Gun1Cube와 Gun2Cube에 붙어있는 collider를 삭제해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-2.PNG" width="50%">  

* PlayerController스크립트를 수정해주자.  
* 숫자키를 누르면 아이템을 교체 가능하도록 해주자.  

-----------------------------
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-3.PNG" width="50%">  

* 실행해보면 숫자키로 무기를 바꿀 수 있다.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-4.PNG" width="50%">  

* 하지만 1번 무기에서 2번 무기로 바꾸고 2번무기를 한번더 누르면 무기가 사라져 버린다.  
* 어떻게 해야 될까?   

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-5.PNG" width="50%">  

* PlayerController스크립트를 수정해주자.  
* 똑같은 숫자키를 두번 누르면 사라져버리니까 전에 눌렀던 숫자키랑 같은 숫자키가 눌리면 아무일도 안일어나게 코드를 수정해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-6.PNG" width="50%">  

* 숫자키를 누르는거 말고도 간편하게 마우스 휠로도 아이템을 바꾸도록 코드를 수정해주자.  
* 마우스 휠을 움직이면 다음아이템으로 바뀌고 반대로 움직이면 이전 아이템으로 바뀌도록 해주자.  
* 목록끝에 도달하면 다시 시작으로 돌아가게 해서 막히지 않게 해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-7.PNG" width="50%">  

* 실행해보면 마우스 휠로도 아이템이 바뀌는걸 볼 수 있다.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-8.PNG" width="50%">  

* 하지만 여러개를 같이 실행해보면 내가 어떤 아이템을 들고 있는지 상대방은 모르고 나도 상대방의 아이템을 모른다.  
* 어떻게 해야 서로 같은게 보일까?    

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-9.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-10.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-11.PNG" width="50%">  

* Player Controller를 수정해주자.  
* Player properties를 hash table형식으로 저장해서 서로 어떤 아이템을 가지고 있는지 확인할 수 있게 해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-12.PNG" width="50%">  

* 실행해보면 서로 어떤 아이템을 들고 있는지 확인할 수 있다.     

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-13.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-14.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-15.PNG" width="50%">  

* 아이템을 사용하여 데미지를 입히고 받는 코드를 만들기 전에 일단 아까 만들어둔 아이템 두개의 이름을 새로 해주자.  
* 각각 rifle과 pistol로 이름을 붙여 서로 헷갈리지 않게 해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-16.PNG" width="50%">  

* 만약 아이템 갯수가 적다면 이런방식으로 각각의 아이템에 대한 설명을 일일이 적어줘도 별 문제가 없다.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-17.png" width="50%">  

* 하지만 아이템 갯수가 늘어나기 시작하는데 이 방식을 사용하면 너무나 방대한 스크립트를 관리해야한다.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-18.png" width="50%">  

* 따라서 아이템목록도 이런식으로 객체 지향적으로 설계를 해야한다.  
* 지금은 오히려 이렇게 객체지향으로 만드는게 더 많은 스크립트를 짜게 되지만 목록이 많아질수록 이방식이 절대적으로 편하다.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-19.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-2/6-2-20.PNG" width="50%">  

* 그전에 일단 rifle과 pistol에 붙여준 item스크립트를 지워준다.  

------------------------------------------------------    
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Photon.Pun;
using Hashtable = ExitGames.Client.Photon.Hashtable;//현재 게임 클라이언트가 쓰는 해쉬테이블 사용
using Photon.Realtime;

public class PlayerController : MonoBehaviourPunCallbacks//다른 포톤 반응 받아들이기
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

    void Awake()
    {
        rb = GetComponent<Rigidbody>();
        PV = GetComponent<PhotonView>();
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
}

```

* 수정한 PlayerController 스크립트의 전문이다.  

--------------  
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture6-3.md)  
-----------------------------
