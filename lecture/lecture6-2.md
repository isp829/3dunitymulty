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
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture7-1.md)  
-----------------------------
