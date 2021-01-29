사용할 아이템 만들기      
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-6/6-6-1.PNG" width="100%">  

* 두개를 실행시켜서 해보면 플레리어는 총에 맞아서 사라졌는데 총알 자국만 공중에 둥둥 떠다니는걸 볼 수 있다.  
* 어떻게 해야될까?   

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
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-6.PNG" width="50%"><img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-7.PNG" width="50%">  
 
* Rifle과 Pistol에 PhotonView를 달아준다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-8.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-9.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-10.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-11.PNG" width="50%">  

* Single SHot Gun 스크립트를 수정해주자.  
* PhotonView를 추가해주고 RayCast에 맞으면 맞은 위치를 말하도록 해주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-12.PNG" width="50%">  

* 실행해보면 RayCast에 맞은 위치가 나온다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-13.PNG" width="50%">  

* Gun 스크립트를 수정해주자.  
* 맞은 위치를 표시할 GameObject를 선언해주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-14.PNG" width="50%">  

* Game Scene에서 3D Object Quad를 만들어주고 크기를 줄여준다음 아까 만든 Spawnpoint 메테리얼을 적용시켜주자. 
* Quad는 한쪽면에서만 보이므로 180도 틀어준다.  
* Collider도 없애주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-15.PNG" width="50%">  

* 프리펩화 시켜준다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-16.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-17.PNG" width="50%">  

* Single SHot Gun 스크립트를 수정해주자.  
* RayCast가 맞은위치에 BulletImpact를 생성하도록 코드를 추가해주자.  
* 자국이 남는 방향은 물체의 방향과 동일하게 하도록 hitNormal을 써주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-18.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-19.png" width="50%">  

* PlayerController 프리펩에 있는 Rifle과 Pistol에 BulletImpact를 넣어주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-5/6-5-20.PNG" width="50%">  

* 게임을 실행하면 이런식으로 자국이 남는다.  

----------------------------------   


---------------------------  

[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture6-5.md)  
-----------------------------   
