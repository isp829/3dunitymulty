사용할 아이템 만들기      
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-1.PNG" width="50%">  

* item 스크립트를 수정해주자.  
* item자체를 추상 클래스로 선언해주고 use라는 추상 함수를 선언해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-2.PNG" width="50%">  

* Gun 스크립트를 하나 만들어주자

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-3.PNG" width="50%">  

* item스크립트에서 사용했던거를 상속하도록 코드를 짜주자  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-4.PNG" width="50%">  

* 원거리 단발 아이템들을 관리하는 SingleShotGun스크립트를 만들어주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-5.PNG" width="50%">  

* 일단 간단하게 Gun으로부터 정보를 받고 호출되면 디버르 로그를 올리도록 코드를 작성해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-6.PNG" width="50%">  

* Player Controller를 수정해서 마우스 왼쪽버튼을 누르면 Use를 호출하도록 해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-7.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-8.png" width="50%">  

* Player Controller 프리펩에 있는 pistol과 rifle에 single shot gun스크립트를 넣어주자.  
* single shot gun스크립트에는 없는 내용이지만 gun스크립트에서 상속했으므로 gun스크립트 내용들이 뜬다.  
* 해당 정보들도 할당해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-9.png" width="50%">  

* Player Controller에도 새로 아이템들을 등록해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-10.PNG" width="50%">  

* 실행해보면 클릭할때마다 디버그 로그가 정상적으로 뜬다.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-11.PNG" width="50%">  

* 카메라에서 레이저를 발사하고 레이저가 물체에 닿으면 디버그 로그가 뜨도록 코드를 수정해주자.  

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-12.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-13.png" width="50%">  

* Rifle과 Pistol에있는 Gun스크립트에 PlayerController프리펩에 붙어있는 카메라를  할당해준다.    

------------------------------------------------------    
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-3/6-3-14.PNG" width="50%">  

* 실행해보면 잘 작동한다.   

------------------------------------------------------    



[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture6-3.md)  
-----------------------------
