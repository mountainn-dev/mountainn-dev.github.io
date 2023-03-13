---
title: "Android Basic in Kotlin(1) - Kotlin Basic"
toc: true
toc_sticky: true
toc_label: Kotlin Basic
---
<br/>

## 1. Create your first app
### 1.1 Android version, API Level 과 SDK
안드로이드에는 __Android version__ 과 __API Level__ 이라는 것이 있다.
Android version 은 디바이스에 설치되어있는 android os 버전을 말하며, API Level 은 android os 에서 애플리케이션과 상호작용하기 위해
제공하는 프레임워크 API 의 버전을 정수값으로 나타낸 것을 말한다. <br/>프레임워크 API 는, 애플리케이션이 android os 에서 작동할 수 있도록 
각종 패키지와 클래스, 인텐트 등의 요소를 담고 있다. __SDK(Software Development Kit)__ 는 애플리케이션과 같은 소프트웨어를 개발하기 위해 개발자가 사용하는 개발 도구를 말하며 
안드로이드 SDK 와 함께 다양한 기능을 제공하는 것이 안드로이드 스튜디오다. 개발자는 애플리케이션을 개발하기 전에 Android version 과 
API Level 을 이용하여 SDK 버전 을 결정할 수 있다. <br/>

> Android version, API Level, SDK 는 각각 안드로이드의 __os 버전, 프레임워크 API 버전, 개발 도구__ 를 의미한다. 

<figure style="width: 90%" class="align-center">
    <img src="/image/posts/img1.png">
    <figcaption>출처: Google Developers</figcaption>
</figure>

위와 같이, 안드로이드에는  현재 다양한 android os 버전과 API Level 이 존재한다. API Level 은 보통 이전 버전의 API 에 새로운 내용이
추가되면서 다음 버전이 나오기 때문에, 개발자는 앱을 개발하기 전에 특정 버전만을 타겟으로 하지 않고 광범위하게 SDK 버전을 결정할 수 있다. 
바로 이 때 중요하게 사용되는 것이 __Minimum SDK__ 라는 것이다. os 에서 기본으로 실행할 수 있는 기능 외에 외부 패키지를 가져와 사용하는 경우, 
해당 패키지 기능들이 특정 프레임워크 API 에서 지원하지 않을 수 있기 때문에 개발자는 이 Minimum SDK 를 설정해주어야 한다. 
즉, Minimum SDK 는 애플리케이션이 일정 API Level 미만에서는 작동하지 않을 것이라 알려주는 동시에, 해당 기기에서 앱을 설치할 수 없도록 
막아주는 역할을 한다. 

> Minimum SDK(android:minSdkVersion) 는 애플리케이션이 일정 API Level 미만에서는 작동하지 않을 것이라 알려주는 동시에, 
__해당 기기에서 앱을 설치할 수 없도록 막아주는 역할__ 을 한다.
<br/>

## 2. Build a basic layout
### 2.1 UI 와 GUI
__UI(User Interface)__ 는, 유저와 시스템이 상호작용하기 위해 사용되는 요소들을 말한다.크게 Graphical 한 요소(GUI) 와 그렇지 않은
요소로 나뉜다. __GUI(Graphical User Interface)__ 는, 오늘날 우리가 흔히 사용하는 메뉴바, 버튼 등이 있다. 즉, 사람이 알아보기 쉽게
디자인적 요소로, 시스템이 수행할 기능을 구현해놓은 것이 GUI 이다. UI 안에 GUI 가 속하며, GUI 외에는 흔히 터미널 창으로 알고있는 terminal
프로그램이 속한 CLI 등이 있다.

> UI(User Interface) 는 시스템이 사용자와 상호작용할 때 사용되는 것을 말하며, GUI(Graphical User Interface) 는 여기에 사람이 알아보기
쉽게 디자인 요소를 추가하여 구현한 것을 말한다.

추가로 __Terminal__ 은, 사용자로부터 text 명령어를 입력받아 컴퓨터와 상호작용 시켜주는 프로그램을 말한다. 윈도우 환경에서 이 터미널 프로그램의
이름이 바로 __CMD(Command Prompt)__ 이다. 그리고 이와 같이, Enter 키로 사용자로부터 텍스트 명령을 입력받아 실행하는 프로그램들이
__CLI(Command Line Interface)__ 에 속한다.

> Terminal 은 사용자가 컴퓨터(OS)와 상호작용할 때 사용되는 프로그램이며, 사용자로부터 Enter 와 text 기반으로 명령어를 입력받는
프로그램을 CLI(Command Line Interface) 라고 한다.
<br/>

### 2.2 View 와 View Group
우리는 모바일 앱을 이용할 때, 여러 버튼과 이미지 텍스트 등을 마주한다. 앱에서는 이러한 요소들을 __View__ 로 컨트롤한다.

<figure style="width: 40%" class="align-center">
    <img src="/image/posts/img2.jpg">
    <figcaption>출처: Google PlayStore 당근마켓</figcaption>
</figure>

위와 같이, 모바일 앱의 버튼 이미지 등 요소 하나하나가 안드로이드에서는 View 로 구분된다. 그리고, 이러한 View 들의 배치 구조를 결정해주는 것이
__View Group__ 이다. View Group 에는 Linear Layout, Grid Layout 등이 있다. View 와 View Group 의 가장 큰 차이는 
가시성과 상호작용이다. View 는 사용자에게 눈에 보이면서 사용자와 상호작용이 가능하지만, View Group 은 이러한 뷰들의 구조를 결정하기 때문에
사용자에게 보이지 않고 사용자와 상호작용이 불가능하다.

> View 는 이미지 버튼 등, 안드로이드 앱에서 사용자에게 보여지는 모든 요소를 말한다. View Group 은 View 의 구조를 결정하는데 사용되는 것을
말한다. 둘의 가장 큰 차이점은 __가시성과 상호작용__ 이다.
<br/>

### 2.3 dp 와 sp
안드로이드에는 뷰나 텍스트의 크기 등을 조절할 때 dp 와 sp 단위를 사용한다. __dp(density independent pixels)__ 는 밀도(해상도) 독립형
픽셀을 의미한다. 쉽게 말해, dp 단위로 크기를 지정하면 해상도가 아무리 바뀌어도 사용자에게 대상이 동일한 크기로 보여진다.
__sp(scale independent pixels)__ 는 배율 독립형 픽셀을 의미하며, sp 단위로 크기를 지정하면 시스템(안드로이드의 경우 Android os)에서
정한 크기에 따라 크기가 바뀐다. <br/>간단한 예로, 한 디자이너로부터 강아지 그림을 전달받았을 때 이 이미지를 dp 단위로 설정해주면, 사용자가
어느 디바이스에서 앱을 켜도 __디자이너가 의도한 대로 강아지 그림을 볼 수 있을 것이다.__ 또한, 뉴스 앱에서 기사글의 텍스트를 sp 단위로 설정해주면
앱 이용자들의 시스템 설정에 맞게 텍스트 크기가 변경할 것이다. 즉, __사용자들이 각자의 편의에 맞게 글을 볼 수 있을 것이다.__ 
따라서 앱의 디자인적 요소를 고려할 때, 디바이스의 화면 크기와 상관없이 크기가 일정해야 하는 뷰 혹은 뷰그룹은 dp , 사용자의 디바이스 설정에
따라 바뀌어야 하는 요소는 뷰 혹은 뷰그룹은 sp 단위를 적용해준다.

> dp(density independent pixels) 는 디바이스와 상관없이 일정한 크기를 유지하며, sp(scale independent pixels) 는 시스템의 설정에
따라 크기가 바뀐다.
<br/>

## 3. Add a button to an app
### 3.1 dd

