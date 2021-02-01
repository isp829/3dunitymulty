교란용 클론 만들기
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-1.PNG" width="50%">  

* 술래를 헷갈리게 하는 클론들을 만들어주자.  
* 플레이어와 같은 모양의 Capsule을 하나 만들어주고 이름을 Clone이라 해주자. 

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-2.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-3.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-4.PNG" width="50%">  

* Clone에 rigidbody, PhotonView, PhotonTransformView, NavMeshAgent를 넣어주자. 
* Rigidbody에서 xyz고정에 xyz축회전도 고정으로 해주자.  
* NavMeshAgent는 클론들이 순찰할때 도움을 준다.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-5.PNG" width="50%">  

* ClonePatrol스크립트를 만들어준다.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-6.PNG" width="50%">  

* SpawnManager에서 스폰포인트로 썼던 위치값을 순찰포인트로 해서 계속 순찰하게 코드를 작성해주자.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-8.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-7.png" width="50%">  

* Clone 태그를 붙여주고 프리펩화 시켜준다.  

----------------------------------------------   ]
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-9.png" width="50%">  

* Game Scene에서 지형으로 쓸 물체들을 다 선택해준다.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-10.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-11.png" width="50%">  

* Navigation에서 object와 Bake 설정을 다해주고 Bake 버튼을 눌러주자.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-12.PNG" width="50%">  

* 이제 NavMeshAgent가 걸어다닐 수 있는 범위가 색깔로 표현된다.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-13.PNG" width="50%">  

* Game Scene에 Clone들을 여러개 올려놓고 실행해보면 순찰을 잘하는걸 볼 수 있다.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-14.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-15.PNG" width="50%">  

* Single Shot Gun 스크립트를 수정해주자.  
* Clone들은 총맞으면 바로 사라지도록 코드를 수정해주자.  
* 또한 술래가 클론인척하는 사람을 맞추면 체력이 회복되도록 코드를 수정해주자.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-16.png" width="50%"><img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-17.png" width="50%">    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-18.PNG" width="50%">  

* PlayerController 프리펩에있는 Rifle과 Pistol에 shooter를 추가해주자.  
* PlayerController에 Player태그를 추가해주자.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture8/lecture8-1/8-1-19.PNG" width="50%">  

* 실행해보면 총에 맞으면 Clone들은 사라지고 Player를 맞추면 체력이 회복되는걸 볼 수 있다.  

----------------------------------------------   
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture9-1.md)  
-----------------------------   
