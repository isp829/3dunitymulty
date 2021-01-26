기본조작 만들기    
=======================

<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture1/lecture5-1/5-1-2.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture1/lecture5-1/5-1-2.PNG" width="50%">  

* PlayerController를 프리펩화 시켜주고 PlayerManager스크립트를 수정해준다.  
---------------------------
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    [SerializeField] float mouseSensitivity, sprintSpeed, walkSpeed, jumpForce, smoothTime;
    //마우스감도 뛰는속도 걷는속도 점프힘 뛰기걷기바꿀때 가속시간
    float verticalLookRotation;
    bool grounded;//점프를 위한 바닥체크
    Vector3 smoothMoveVelocity;
    Vector3 moveAmount;//실제 이동거리

    Rigidbody rb;

    void Awake()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        transform.Rotate(Vector3.up*Input.GetAxis("Mouse X")*mouseSensitivity);
        //마우스 움직이는 정도*민감도만큼 각도 움직이기
    }
}

```
5-1-4 
------------------------------------------------------      
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    [SerializeField] float mouseSensitivity, sprintSpeed, walkSpeed, jumpForce, smoothTime;
    [SerializeField] GameObject cameraHolder;
    //마우스감도 뛰는속도 걷는속도 점프힘 뛰기걷기바꿀때 가속시간
    float verticalLookRotation;
    
    Rigidbody rb;

    void Awake()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        transform.Rotate(Vector3.up*Input.GetAxis("Mouse X")*mouseSensitivity);
        //마우스 움직이는 정도*민감도만큼 각도 움직이기
        verticalLookRotation += Input.GetAxis("Mouse Y")*mouseSensitivity;
        //마우스 움직이는 정도*민감도만큼 각도 값 받기
        verticalLookRotation = Mathf.Clamp(verticalLookRotation, -90f, 90f);
        //y축 -90도에서 90도만 값으로 받음
        cameraHolder.transform.localEulerAngles = Vector3.left * verticalLookRotation;
        //받은 각도로 카메라도 돌려줌
    }
}

```
5-1-8
--------------
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerGroundCheck : MonoBehaviour
{
    PlayerController playerController;//Player Controller 스크립트를 메서드로 사용하기 위해 선언
    void Awake()
    {
        playerController = GetComponentInParent<PlayerController>();      
    }

    void OnTriggerEnter(Collider other)
    {
        if (other.gameObject == playerController.gameObject)
            return;//해당 물체가 player면 무시
        playerController.SetGroundedState(true);
        //닿으면 true
    }

    void OnTriggerExit(Collider other)
    {
        if (other.gameObject == playerController.gameObject)
            return;//해당 물체가 player면 무시
        playerController.SetGroundedState(false);
        //떨어지면 true
    }

    void OnTriggerStay(Collider other)
    {
        if (other.gameObject == playerController.gameObject)
            return;//해당 물체가 player면 무시
        playerController.SetGroundedState(true);
        //닿고 있으면 true
    }
}

```
5-1-15
-------------------
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    [SerializeField] float mouseSensitivity, sprintSpeed, walkSpeed, jumpForce, smoothTime;
    [SerializeField] GameObject cameraHolder;
    //마우스감도 뛰는속도 걷는속도 점프힘 뛰기걷기바꿀때 가속시간
    float verticalLookRotation;
    bool grounded;//점프를 위한 바닥체크
    Vector3 smoothMoveVelocity;
    Vector3 moveAmount;//실제 이동거리

    Rigidbody rb;

    void Awake()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        Look();
        Move();
        Jump();
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

    public void SetGroundedState(bool _grounded)
    {
        grounded = _grounded;
    }

    void FixedUpdate()
    {
        rb.MovePosition(rb.position + transform.TransformDirection(moveAmount) * Time.fixedDeltaTime);
        //이동하는거는 계산 끝난 moveAmount만큼만 고정된시간(0.2초)마다에 맞춰서
    }
}

```
5-1-21
-----------------
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture5-2.md)  
-----------------------------
