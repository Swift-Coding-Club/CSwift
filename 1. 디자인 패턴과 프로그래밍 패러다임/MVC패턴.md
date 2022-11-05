# MVC 패턴
MVC는 Smalltalk MVC와 Cocoa MVC로 나눠 작성했습니다.

## Smalltalk MVC
![Alt text](https://developer.apple.com/library/archive/documentation/General/Conceptual/CocoaEncyclopedia/Art/traditional_mvc.gif)

> Developer Apple Documentation Archive
> Traditional version of MVC as a compound pattern
> https://developer.apple.com/library/archive/documentation/General/Conceptual/CocoaEncyclopedia/Model-View-Controller/Model-View-Controller.html#//apple_ref/doc/uid/TP40010810-CH14

* MVC는 소프트웨어가 서비스하는 방식에 대한 패턴의 종류 중 하나
* 1970년 후반에 처음 사람들에게 보이게 됐고 Smalltalk MVC가 제일 먼저 등장함
* Model, View, Controller로 이루어진 디자인 패턴이라는 뜻에서 MVC 패턴이라고 지칭함

### Smalltalk MVC의 특징
* Composite, Strategy, Observer 패턴이 복합적으로 보이고 있음
* 각각 Model, View, Controller가 각자의 역할에 따라 동작한다는 것이 특징

### MVC 패턴의 예시
* MVC 패턴은 정말 많은 언어나 프레임워크에서 사용하고 있음</br>
* React, Angular, Django, JSP, Spring Boot 등


## Cocoa MVC
> The structure of UIKit apps is based on the Model-View-Controller (MVC) design pattern,wherein objects are divided by their purpose. Model objects manage the app's data and business logic. View objects provide the visual representation of your data. Controller objects act as a bridge between your model and view objects, moving data between them at appropriate times.
>
> -Developer Apple Documentation-
> https://developer.apple.com/library/archive/navigation/


Apple은 Documentation에서 Cocoa MVC에 대해 다음과 같은 설명을 하고 있습니다.
*__만약 오역이 있는 경우 저에게 Contact 해주시면 수정하겠습니다 !__*
* UIKit 앱의 구조는 Model-View-Controller Design pattern을 기반으로 한다.
* MVC Design pattern에서는 Object들이 그 목적에 따라 나누어진다.
* Model Object는 앱의 Business logic을 통제한다.
* View Object는 당신(you) 데이터의 시각적 표현을 제공한다.
* Controller Object는 당신(you)의 Model Object와 View Object 사이의 다리 역할을 하면서, 
이 둘 간의 적절한 타이밍에 이동시키는 역할을 한다.


위에서 언급했던 React, Angular, Django, JSP, Spring Boot는 **동작하는 구성 방식과 환경**들이 각기 다 다르기 때문에 기존의 전통적인 디자인 패턴의 개념을 가지고 가되, 각 언어 혹은 프레임워크의 입맛에 맞춰 조금씩 변형하고 있는데 Apple에선 iOS의 시스템을 고려해서 새로 도입한 MVC를 **"Cocoa MVC", 혹은 Apple's MVC**라고 부르고 있습니다.

### Apple이 Cocoa MVC를 내놓은 이유에 대하여
![Alt text](https://developer.apple.com/library/archive/documentation/General/Conceptual/CocoaEncyclopedia/Art/traditional_mvc.gif)
Apple이 기존의 MVC 방식을 두고, Cocoa MVC를 한 이유는 다음과 같습니다.
1. 기존의 MVC의 경우 Model, View, Controller 간의 복잡성과 과도하게 밀접한 연관성
2. 각 오브젝트들의 독립성이 없기 때문에 재사용성이 떨어짐
3. View를 갱신할 때 반드시 Controller에 대한 강제를 하지 않음

iOS 개발 시 ViewController를 사용하기 때문에 View와 Controller를 결합시켜 ViewController와 Model로 구분된다. 이에 더해 Controller가 View의 Life Cycle까지 관리하면서 Controller의 역할이 더 늘어난 것이 특징이다.

### MVC 주의점
<img src="https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/Art/model_view_controller_2x.png" width="500">

> ㄷ
> ㄷ

**Model**
* 사용자가 **<span style="color: #1DAC84">편집하길 원하는 모든 데이터</span>** 를 가지고 있어야 함
* 뷰나 컨트롤러에 대해서 **<span style="color: #1DAC84">어떤 정보도</span>** 알지 말아야 함
* 변경이 일어나면, **<span style="color: #1DAC84">변경 통지에 대한 처리 방법</span>** 을 구현해야만 함

**View**
* 모델이 가지고 있는 정보를 **<span style="color: #1DAC84">따로 저장</span>** 해서는 안 됨
* 모델이나 컨트롤러와 같이 다른 구성요소들을 몰라야 함

**Controller**
* 모델이나 뷰에 대해서 알고 있어야 함
* 모델이나 뷰의 변경을 **<span style="color: #1DAC84">모니터링</span>** 해야 함

### Apple이 생각했던 이상적인 Cocoa MVC
<img src="https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/Art/model_view_controller_2x.png" width="500">
Apple이 말하는 Cocoa MVC의 이점은 다음과 같습니다</br>

1. **<span style="color: #1DAC84">재사용성이 더 용이함</span>** 
2. 인터페이스가 **<span style="color: #1DAC84">조금 더 잘 정의</span>** 된다
3. MVC를 이용한 Application들은 다른 Application보다 **<span style="color: #1DAC84">조금 더 쉽게 확장할 수 있다</span>** 

UIKit에선 **<span style="color: #1DAC84">"자기 자체만의 MVC 디자인 패턴을 이용한다."</span>** 라고 말 하고 있습니다.

### Cocoa MVC의 한계
<img src="https://camo.githubusercontent.com/8aa2dba7aa59811552c5eb3cd7e444dd531010c570fee6461eda0e128f936187/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313630302f312a506b576a4455306a71474a4f42393732634d73726e412e706e67" width="500">

1. UIView는 어떻게 화면에 그릴지 딱 그 역할만
2. View에 대한 이벤트 발생 시 이벤트 처리는 **<span style="color: #1DAC84">Delegate or DataSource</span>** 프로토콜을 통해 **<span style="color: #1DAC84">UIViewController</span>** 에 위임
3. UIKit Framework에선 View와 Controller는 UIViewController
4. Massive 한 View Controller를 만든다 -> 그럼 **<span style="color: #1DAC84">Controller에 대한 재사용성은 어떻게 될까요?</span>**

위의 사진을 봤을 때 객체 이름이 UIViewController라고 되어있습니다. View와 Controller를 묶어서 부르고 있는데요. 저희가 위에서 살펴봤던 MVC로 봤을 때 M은 Model이 되겠지만, Cocoa Framework의 UIView와 UIViewController를 분리해 개발하긴 힘들 것으로 보입니다.
이에 더해 현재 UIKit에서의 Controller는 View Life Cycle, View Delegate, Notification 연산, 비즈니스 로직과 같은 대부분의 일들을 ViewController에서 이루어지고 있는데 규모의 크기가 일정 크기 이상 커졌을 때 Controller가 소화를 하긴 힘듭니다. 이 때문에 UIKit으로 개발하는 개발자들 사이에서 MVC를 Massive View Controller로 부르기도 합니다.

> Retired Document
> Important: This document may not represent best practices for current development. Links to downloads and other resources may no longer be valid.

Documentation Archive에서 Cocoa Core Competencies의 MVC 패턴을 확인해 보면 위에 있는 안내 문구가 나옵니다. 다음 해석은 이렇습니다.

> 폐기된 문서
> 중요 : 이 문서는 현재 개발에 대해 더 이상 모범 사례가 아닐 수 있습니다.
> 다운로드 및 기타 리소스에 대한 링크가 더 이상 유효하지 않을 수 있습니다.

### 그럼 MVC는 안 좋은건가요?
<p>
사실 해당 문서에서 장점보다 단점에 대한 내용이 많긴 했지만, MVC가 결코 나쁘다고 생각하지 않습니다. 프로젝트 규모가 크지 않고 추후에도 규모가 크게 늘어나지 않을 것 같은데 굳이 MVVM을 구축할 필요가 없듯이, 프로젝트 규모나 상황에 따라 MVC가 좋을 수도, 다른 패턴이 좋을 수도 있다고 생각하고 그래서 설계가 중요하다고 생각합니다.
</p>