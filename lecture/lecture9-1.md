다듬기
=======================
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-1.PNG" width="50%">  

* 지금은 게임이 시작되어도 외부에서 사람이들어 올 수 있다.  
* Launcher스크립트에 한줄 추가해서 게임이 시작되면 방이 안보이도록 해주자.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-2.PNG" width="50%">  
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-3.PNG" width="50%">  

* 테스트 해보면 게임이 시작되면 방목록에서 사라진다. 

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-4.PNG" width="50%">  

* 지금은 게임오버되면 그냥 고정된 카메라 시점으로 보인다.  
* 게임오버되면 자유롭게 게임을 관전하게 수정해주자.  
* Game Object를 만들고 watcher라 이름붙여주자.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-5.PNG" width="50%">  

* Rigidbody를 넣어준다.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-6.PNG" width="50%">  

* Watcher안에 CameraHolder를 넣어주고 그안에 카메라, 그리고 그안에 TMP를 넣어주자.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-7.PNG" width="50%">  

* 글자 크기와 색깔 위치를 조절해주자.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-8.png" width="50%">  

* Canvas도 설정을 해주자.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-9.PNG" width="50%">  

* DieCamera 스크립트를 작성해주자.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-10.PNG" width="100%">  

* 플레이어 움직이는 스크립트랑 똑같은 구조다.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-11.png" width="50%">  

* BuildSettings=>ProjectSettings=>InputManager에서 Jump의 음수버튼을 x로 설정해주자.  
* 이렇게 되면 관전 카메라는 스페이스바를 누르면 위로 올라가고 x를 누르면 아래로 내려가면서 떠다닐꺼다.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-12.PNG" width="50%">  

* Watcher에 DieCamera스크립트를 넣어주고 설정을 해주자.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-13.PNG" width="50%">  

* 실행해보면 잘된다.  

---------------------------   
<img src="https://github.com/isp829/3dunitymulty/blob/master/images/lecture9/lecture9-1/9-1-14.PNG" width="50%">  

* 맵에 여러 지형지물도 더 넣고 사람들도 불러서 게임을 즐겨보자

---------------------------   
[목차로](https://github.com/isp829/3dunitymulty/blob/master/README.md)  
[다음](https://github.com/isp829/3dunitymulty/blob/master/lecture/lecture10-1.md)  
-----------------------------   
