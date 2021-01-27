사용할 아이템 만들기      
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-1.PNG" width="50%">  

* 아이템을 만들기위해서 ItemInfo와 GunInfo 스크립트를 작성해주자.   

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-2.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-3.PNG" width="50%">  


* 각각 ItemInfo와 GunInfo의 스크립트이다.  
* ScriptableObject를 사용하여 간단하게 많은 양의 프리펩들에 정보를 넣어 줄 수 있다.  
* GunInfo는 ItemInfo를 받아서 New Gun menu를 만들도록 해주자.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-4.PNG" width="50%">  


* Asset=>Items=>Guns폴더들을 만들어주자.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-5.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-6.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-7.PNG" width="50%">  


* 2개의 New Gun을 만들어준다.    
* 각각 Gun1과 Gun2로 이름 지어주고 item info에도 Gun1과 Gun2라고 써주자.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-8.PNG" width="50%">  

* PlayerController 프리펩에서 itemHolder를 만들어주고 Gun1Item과 Gun2Item을 넣어주자.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-9.PNG" width="50%">  

* Item 스크립트를 작정해주자.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-10.PNG" width="50%">  

* 간단하게 itemInfo를 받고 해당 아이템 game Object를 등록할 수 있게 해준다.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-11.PNG" width="50%">  

* GunItem안에 Gun1과 Gun2의 빈 gameObject를 넣고 총 모델링으로 쓸 큐브들을 넣어주자.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-12.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-13.PNG" width="50%">  

* 두 총의 구분을 위해서 Gun1은 비교적 두껍게, Gun2은 얇게 만들어주자.  

------------------------------------------------------     
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-14.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture6/lecture6-1/6-1-15.PNG" width="50%">  

* Gun1/2Item에 item 스크립트를 넣어주고 각각의 ItemInfo와 ItemGameObject를 넣어주자.  

------------------------------------------------------     
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture6-2.md)  
-----------------------------
