---
title: "Android Basic in Kotlin(1) - Kotlin Basic"
toc: true
toc_sticky: true
toc_label: Kotlin Basic
---
<br/>

# 1. Create your first app
---
### 1.1 Android version, API Level 과 SDK
안드로이드에는 __Android version__ 과 __API Level__ 이라는 것이 있다.
Android version 은 디바이스에 설치되어있는 android os 버전을 말하며, API Level 은 android os 에서 애플리케이션과 상호작용하기 위해
제공하는 프레임워크 API 의 버전을 정수값으로 나타낸 것을 말한다. 프레임워크 API 는, 애플리케이션이 android os 에서 작동할 수 있도록 
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
해당 기기에서 앱을 설치할 수 없도록 막아주는 역할을 한다.

### 1.2 

### H3



