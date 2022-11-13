# MVVM(Model-View-ViewModel)
## MVVM 패턴이란?
![Alt text](https://wnstkdyu.github.io/2018/04/20/mvvmdesignpattern/mvvm.png)

>MVVM 패턴은 MVC의 C에 해당하는 Controller가 ViewModel로 바뀐 패턴이며
>총 세 가지로 이루어져 있습니다.

* Model
* View
* ViewModel

View에 해당하는 UIView와 UIViewController는 각자의 ViewModel을 소유하고 있습니다. View가 소유한 ViewModel은 View와 바인딩 되어서 데이터나 사용자 액션을 주고받게 됩니다.
ViewModel은 자신의 Model을 가질 수 있는데 View로부터 받은 다양한 사용자 Action이나 데이터를 Model을 통해 Business logic을 처리하게 됩니다. ViewModel과 ViewModel을 소유한 Model을 통해 처리한 결과는 바인딩 된 뷰에 어떠한 데이터의 형태로 전달이 될 거고 전달이 된 데이터는 View에 업데이트되는 거죠. View의 액션과 이벤트를 View Model에 전달시키고, 다시 View Model은 Modeling이라는 Business logic을 통한 아웃풋을 다시 View에게 전해주는 단방향 디자인 패턴입니다.

### MVVM의 장점
1. View Model과 View 간의 의존성이 없기 때문에 테스트 수월해짐
2. 1 : N 관계기 때문에 중복되는 로직을 모듈화해 여러 View에 재사용 가능
### MVVM의 단점
1. MVC에 비해 설계가 복잡함
2. 데이터 바인딩으로 인한 메모리 소모 우려