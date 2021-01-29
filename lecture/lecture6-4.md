사용할 아이템 만들기      
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-1.PNG" width="50%" height="200">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-2.PNG" width="50%">  

* PlayerController 스크립트를 수정해주자.  
* IDamageable인터페이스를 불러오고, 함수를 재정의 해주자.  

--------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-3.PNG" width="50%">  

* 실행해보면 잘 작동한다.  

--------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-4.PNG" width="50%">  

* 하지만 아직은 정보가 나한테만 뜨고 남한테는 안뜬다.  
* 피해를 입힌쪽만 뜨고 받은쪽은 아무것도 안뜨면 의미가 없으니까 코드를 수정해준다. 
* 피해를 준쪽이 함수를 모두에게 호출해주고 피해를 받은 쪽만 RPC_TakeDamage를 실행하도록 해주자.  

--------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-5.png" width="50%">  

* 실행해보면 이제 상대방한테 맞을때마다 디버그 로그가 뜨는것을 알 수 있다.  
* 하지만 맞아도 아무일이 없다면 의미가 없다.  

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-6.PNG" width="50%">  

* 이제 최대 체력이 있고 맞을때마다 체력이 깎이고 체력이 0이되면 GameOver되도록 코드를 추가해주자.  
* PlayerManager 스크립트를 수정해주자. 플레이어 컨트롤러 인스턴스를 만들때 포톤뷰 아이디를 가지게 해주자. 
* Die 함수를 만들어서 PlayerController를 삭제하게 해주자.  


----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-7.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-8.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-9.png" width="50%">  

* PlayerController 스크립트도 수정해주자. 
* 체력을 설정해주고 PlayerManager를 선언해서 PlayerManager의 Die함수를 불러오도록 코드를 수정해주자.   

----------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-4/6-4-10.PNG" width="50%">  

* 실행해보면 체력이 0이된 플레이어는 캐릭터가 사라지고 Game Scene에있는 Main카메라로 시점이 바뀐다.  

----------------------------------   
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture6-5.md)  
-----------------------------   
