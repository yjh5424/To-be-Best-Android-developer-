# Clean Architecture 


### 개요  
클린아키텍쳐가 나온 이유는 안드로이드 뿐 만이 아니라 소프트웨어를 개발할 때 새로운 기능이 나오거나 데이터베이스를 변경해야 하는 경우 또는 테스트가 가능하고 유연한 코드가  가능한 프로젝트를 만들기 위해서 여러 아키텍쳐가 나오게 되었고 Uncle Bob의 Clean Architecture는 프로젝트를 구성하는 각 부분마다 규칙을 지정하였고 이 Clean Architecture를 이용해서 안드로이드 프레임워크에 적용한 것이다. 

### 안드로이드에서 클린 아키텍쳐를 적용하면 좋은 점

1. 본질적인 것만 남기기 때문에 여러 템플릿(라이브러리) 변경시에도 그게 코드가 변경이 없다.  

2. 1번 이유에 때문에 본질적인 것만 남으면 테스트 하기 유용하다.  

3. 안드로이드에서 보여주는 부분과 비지니스 로직을 분리가 가능하다. 

-------
### 안드로이드에서 클린아키텍쳐를 적용하는 방법

![screenshot](https://images.ctfassets.net/emmiduwd41v7/6HuRyfP1Vm4UEIiIEIeMwS/5f66cdc5c4a5af60f24920548babace1/clean-android-architecture2.jpg)


의존도는 위에 그림과 아래로 진행되고 Entities는 다른 레이어 층을 모르고  Presenters는 내부에 있는  Use Cases, Entities 알고있다. 

 - UI
어떤 프레젠터를 사용하면되는지만 알면되고 뷰에 대한 컨트롤을 하면 된다.   

 - Presenters
핵심로직을 구현하는 레이어 액티비티, 프래그먼트가 하는 내용들은 interface로 전달받아서 연결을 해준다.    

 - Use Cases 말 그대로 사용자 유스케이스와 똑같은 개념이다. 사용자가 생각한 기능 또는 플로우들에 대한 것들을 정의해놓은 층이다.     
    <code>getNotes() : List< Note > </code>   

    이런식으로 어떤 식으로 데이터를 받고 어떤 역할을 하는지에 대해서만 정의하고 핵심로직은 Presenters 레이어에서 구현하한다. 

 - Entities  
어떤 서비스의 기능을 사용할 때 사용자가 생각하는 개념  
어떤 특징 개발 프레임워크에 의존해서는 안되고 오직 사용자가 생각하는 대로 
Entities 가 정의되야함 
-------