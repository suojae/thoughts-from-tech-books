
### 1. Flutter Engineering: Core Concepts

>A Prime example of this is Flutter is the use of the `Listenable` class. This class serves as the foundation for the animation system in Flutter, where changes in the anumation state are treated as events.

```dart
class MyListenable extends Listenable {
  final List<VoidCallback> _listeners = [];

  @override
  void addListener(VoidCallback listener) {
    _listeners.add(listener);
  }

  @override
  void removeListener(VoidCallback listener) {
    _listeners.remove(listener);
  }

  void notify() {
    for (final listener in _listeners) {
      listener();
    }
  }
}

// 사용
void main() {
  final myListenable = MyListenable();

  myListenable.addListener(() {
    print('변화가 생겼어요!');
  });

  myListenable.notify(); // => "변화가 생겼어요!" 출력
}
```
- 플러터에서 가장 손쉽게 event driven을 하는 방법은 `Listenable` 클래스를 활용하는 것
- 예제코드처럼 먼저 콜백배열을 선언한다음에 `addListener`에 액션을 넣어주고 `notify`를 해주면 된다.

```dart
void listenTo(Listenable listenable) {
  listenable.addListener(_handleChange);
}
```
- 참고로 굳이 `Listenable`을 써주는 이유는 플러터 프레임워크안에는 위와같이 `Listenable` 타입을 받아서 쓰는 코드들이 많아서 이벤트 드리븐할 때 플러터 기본위젯들과 합작할 수 있게 된다. 


<br/>

>FLutter's widget-based architecture is inherently modular, each widget encapsulating a specific UI or functional aspect.

<br/>

<img width="450" alt="image" src="https://github.com/user-attachments/assets/9247ff87-3a76-456f-bb6d-82f48fd96c1e" />

>"Verification" involves checking whether the system is built correctly and meets the specified requirements. This is often referred to as "Static Testing".On the other hand, "Validation" checks whwether the right system is built and meets the users' needs, known as "Dynamic Testing."

<br/>

<img width="428" alt="image" src="https://github.com/user-attachments/assets/d25f8f8c-2714-4d88-a116-b7c1e9aa0403" />

>The "Shifting Left" concepts emphasizes integrating these processes early in the development cycle. For FLutter Developers, it means conducting tests and quality checks right form the initial stages. This early intervention helps detect and fix issuses promptly reducint the cost and time typically associated with later-stage debugging.


<br/>

#


### 2. Unveiling FLutter: Architecture and Engineering Insights

> In Flutter's architecture, a `Widget is an immutable configuration, while the `Element` is the dynamic entity that gets mounted.

<br/>

> In Flutter, every widget receives a set of constraints define the widget's minimum allowable sizes. 

<br/>

> Once a widget receives its constraints, it determines its size within these limits. This isze is then comunicated u[wards to the parent.

<br/>

> Each widget is laid out only once, and the process cannot be reversed or iterated. 


<br/>

>







