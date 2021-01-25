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
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture5-2.md)  
-----------------------------
