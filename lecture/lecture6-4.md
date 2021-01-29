사용할 아이템 만들기      
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-1.PNG" width="100%" height="100%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-2.PNG" width="50%">  

* PlayerController 스크립트를 수정해주자.  
* IDamageable인터페이스를 불러오고, 함수를 재정의 해주자.  

--------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-3.PNG" width="50%">  

* 실행해보면 잘 작동한다.  

--------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-4.PNG" width="100%">  

* 하지만 아직은 정보가 나한테만 뜨고 남한테는 안뜬다.  
* 피해를 입힌쪽만 뜨고 받은쪽은 아무것도 안뜨면 의미가 없으니까 코드를 수정해준다. 
* 피해를 준쪽이 함수를 모두에게 호출해주고 피해를 받은 쪽만 RPC_TakeDamage를 실행하도록 해주자.  

--------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-5.png" width="100%">  

* 실행해보면 이제 상대방한테 맞을때마다 디버그 로그가 뜨는것을 알 수 있다.  
* 하지만 맞아도 아무일이 없다면 의미가 없다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-6.PNG" width="100%">  

* 이제 최대 체력이 있고 맞을때마다 체력이 깎이고 체력이 0이되면 GameOver되도록 코드를 추가해주자.  
* PlayerManager 스크립트를 수정해주자. 플레이어 컨트롤러 인스턴스를 만들때 포톤뷰 아이디를 가지게 해주자. 
* Die 함수를 만들어서 PlayerController를 삭제하게 해주자.  


----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-7.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-8.png" width="100%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-9.png" width="50%">  

* PlayerController 스크립트도 수정해주자. 
* 체력을 설정해주고 PlayerManager를 선언해서 PlayerManager의 Die함수를 불러오도록 코드를 수정해주자.   

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-10.PNG" width="50%">  

* 실행해보면 체력이 0이된 플레이어는 캐릭터가 사라지고 Game Scene에있는 Main카메라로 시점이 바뀐다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-11.PNG" width="50%">  

* Game Scene에서 SpawnManager=>SpwanPoint=>Capsule을 만들어준다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-12.PNG" width="50%">  

* Asset에 Material폴더를 만들어주고 그안에 spawnPoint가 잘 보이도록 Material을 만들어주고 Capsule에 넣어준다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-13.png" width="50%">  

* SpawnPoint를 프리펩화 시켜준다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-14.png" width="50%">  

* SpawnPoint를 스폰지점으로 삼고 싶은 곳에다가 놓아주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-15.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-16.PNG" width="50%">  

* SpawnPoint 프리펩으로 돌아가서 어느쪽이 앞인지 구분이 쉽도록 표시를 해주자.  
* 큐브를 하나 만들어주고 색깔을 구분하도록 material도 하나 만들어주자. 
* 큐브가 튀어나온쪽이 캐릭터의 앞부분이다.  
* 시작하면 맵바깥부분이 아닌 맵중앙을 보도록 회전시켜주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-17.PNG" width="50%">  

* SpawnPoint 스크립트를 작성해주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-18.PNG" width="50%">  

* 간단하게 시작되면 캡슐이랑 큐브는 사라지고 그 위치정보만 남게 해주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-19.PNG" width="50%">  

* SpawnManager 스크립트를 작성해주자.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-20.PNG" width="50%">  

* 다른 클래스에서 사용하기 위해서 정적 클래스로 선언해주고 랜덤한 스폰지점에서 시작하도록 해주자.  

----------------------------------   
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture6-5.md)  
-----------------------------   
