술래 정하기     
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-1.PNG" width="50%">  

* 이제 '술래'잡기 게임이니까 술래를 정해주는 코드를 작성해주자.  
* GameController 스크립트를 만들어준다.

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-2.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-3.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-4.PNG" width="50%">  

* PlayerController로부터 리스트를 받아서 그중에 한사람을 술래로 정해주는 코드를 구현하자.  
* 게임이 시작되고 3초후에 술래가 정해지도록 지연을 넣자.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-5.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-6.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-7.png" width="50%">  

* PlayerController 스크립트도 수정해주자.  
* 체력과 술래인지 아닌지를 표현하는 텍스트를위해 TMP를 사용해주자. 
* 술래가된 캐릭터는 혼자 색깔이 바뀌므로 Renderer로 선언해주자.  
* GameController와의 정보 주고 받기를 위해서 PlayerController도 선언해주고 GameController를 사용한다고 선언해주고 추가해주자.   

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-8.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-9.png" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-10.PNG" width="50%">  

* 기존에는 시작하자마자 아이템을 꼈지만 이제 술래만 아이템을 사용할 수 있으므로 시작할때는 아무것도 안들게 해준다.   
* 술래한테 패널티를 주기위해 총을 쏠때마다 일정량의 체력이 깎이도록 해주자.  
* 술래면 화면에 모두잡으라 텍스트가 나오고 아니면 도망가라 텍스트가 나오게 해준다.  
* 마지막으로 모두에게 술래가 누군지 알려주기위해 술래정하기와 술래 색변경을 RPC로 해준다.  

----------------------------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture7/lecture7-1/7-1-11.PNG" width="50%">  

* 실행해보면 게임시작 3초후에 술래가 정해지고 술래는 검정색이된다.  
* 술래에게 맞으면 GameOver가된다.  

----------------------------------------------   
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture8-1.md)  
-----------------------------   
