<img src="https://github.com/user-attachments/assets/3c4aca3b-8b9d-4151-b383-374fe1d53058" width="300">

<br/>
<br/>
<br/>

#

### Chapter 1. The Goal of unit testing  주요문장

<img src="https://github.com/user-attachments/assets/3f36364f-daf8-49e1-b04e-4a762b1c2a79" width="300">

<br/>
<br/>

> Sustainability and scalability are the keys. They allow you to maintain development speed in the long run.


<br/>

<img src="https://github.com/user-attachments/assets/d84f26c1-ea35-406e-b7b0-efa83a32cf7e" width="300">

> Remember, not all tests are created equal. Some of them are valuable and contribute a lot to overall software quality. Others don’t. They raise false alarms, don’t help you catch regression errors, and are slow and difficult to maintain

> Code is a liability, not an asset. The more code you introduce, the more you extend the surface area for potential bugs in your software, and the higher the project’s upkeep cost.

<br/>

<img src="https://github.com/user-attachments/assets/d3b7334e-ec9c-4db5-bf59-d7ed59ed45e3" width="300">

<br/>
<br/>

> Likewise, targeting a specific coverage number creates a perverse incentive that goes against the goal of unit testing. Instead of focusing on testing the things that matter, people start to seek ways to attain this artificial target. Proper unit testing is difficult enough already. Imposing a mandatory coverage number only distracts developers from being mindful about what they test, and makes proper unit testing even harder to achieve.

> The only point in having automated tests is if you constantly use them. All tests should be integrated into the development cycle. Ideally, you should execute them on every code change, even the smallest one.

>1. It’s integrated into the development cycle.
>2. It targets only the most important parts of your code base.
>3. It provides maximum value with minimum maintenance costs.

<br/>

### Chapter 1. The Goal of unit testing  읽고 나의 생각

평소 추상적으로 테스트 코드를 짜는게 좋다! 라는 이야기만 들었지 막상 테스트 코드를 작성하려고 할때마다 이게 과연 맞는건가 싶었다. 저자는 테스트코드는 초반 진행이 더딜 순 있어도 프로젝트의 규모가 커질수록 테스트코드를 작성해놓는 것이 유지보수 시간을 단축시킨다고하며 서두를 시작한다.

<br/>
 

챕터1에서 저자가 강조한 점은 테스트 코드도 "코드"라는 점이다. 잠깐 테스트해보고 지우는 것이 아닌 최대한 오래 지속될 수 있는 테스트 코드를 작성해야한다. 그래서 프로젝트 진행간 바뀌지 않는 비즈니스 로직이 유닛테스트 대상으로 가장 적합하다고 볼 수 있다. 

 <br/>

테스트코드도 좋은 코드가 있고 나쁜 코드가 있음을 알 수 있었다. 하나의 메서드가 하나의 책임을 갖는 것 처럼 유닛테스트 코드도 하나의 목적을 테스트해야한다. 넓은 범위의 테스트코드는 나중에 넓은 범위속에서 문제가 생기면 어디서 문제가 생겼는지도 알기 어렵기 때문이다.

 <br/>

저자는 테스트코드 실전도입에 있어서 2가지를 강조한다. 바로 개발 사이클에 테스트코드 작성과 실행이 들어가야한다는 것, 가장 중요한 파트(비즈니스 로직)가 테스트 대상이 되어야한다는점이다. 

 <br/>

요구조건이 바뀌더라도 왠만하면 바뀌지 않는 코드들, 서비스 객체 메서드와 비즈니스 로직부터 유닛테스트를 작성해나가야함을 배울 수 있었다.

<br/>
<br/>
<br/>

#

### Chapter 2. What is a unit test? 주요 문장

>A test double is an object that looks and behaves like its release-intended counterpart but is actually a simplified version that reduces the complexity and facilitates testing

 <br/>

<img src="https://github.com/user-attachments/assets/03b3cd11-26d0-4e7e-80eb-b00d6567ec58" width="200">

 <br/>

>A unit test is an automated test that
>Verifies a small piece of code (also known as a unit),
>Does it quickly,
>And does it in an isolated manner.

<br/>

>One benefit of this approach is that if the test fails, you know for sure which part of the code base is broken: it’s the system under test. There could be no other suspects, because all of the class’s neighbors are replaced with the test doubles.

<br/>

>For now, just make a note that interfaces are required for isolating the system under test from its collaborators.

<br/>

<img src="https://github.com/user-attachments/assets/37fd40b4-7de9-4ffd-a8c7-da807710414a" width="300">

<br/>

>Another benefit is the ability to split the object graph—the web of communicating classes solving the same problem.

<br/>

>Unit tests themselves should be run in isolation from each other. That way, you can run the tests in parallel, sequentially, and in any order, whatever fits you best, and they still won’t affect each other’s outcome.

<br/>

>For now, just make a note that interfaces are required for isolating the system under test from its collaborators.

<br/>

>Tests shouldn’t verify units of code. Rather, they should verify units of behavior: something that is meaningful for the problem domain and, ideally, something that a business person can recognize as useful.

<br/>

>A test should tell a story about the problem your code helps to solve, and this story should be cohesive and meaningful to a non-programmer.

<br/>

<img src="https://github.com/user-attachments/assets/d911f83d-001e-49a5-8bfc-8ad2f4c8e9b9" width="300">

<br/>

>In short, an integration test is a test that verifies that your code works in integration with shared dependencies, out-of-process dependencies, or code developed by other teams in the organization

<br/>

>You may possibly even run them only on the build server, not on individual developers’ machines.

<br/>
<br/>

### Chapter 2. What is a unit test? 읽고 나의 생각

이책을 읽기 전까지 사실 단위테스트를 작성할 때 기계적으로 mock객체를 만들었다. 하지만 내가 만든 mock은 정확히 얘기하자면 Test Double의 한 종류이다. 왜 단위테스트를 할 때는 테스트 더블(대역)이 필요한걸까? 저자는 두가지 요소를 이야기하는데 바로 객체의 순수한 행동검증과 속도이다.

<br/>

함수형 프로그래밍이 대세라고는 하지만 거의 99%의 소프트웨어는 객체지향 프로그래밍을 하고 있고 객체지향의 핵심은 각 객체들의 행동을 통해 소프트웨어를 만드는 것이다. 이때 어떤 객체들은 그 자체로 독립적으로 존재하지 못하고 의존성이 걸려있는데 만약 "대역"없이 해당 객체를 검증한다면 의존성이 걸려있는 객체가 문제인건지 정말 해당 객체의 문제인지 분별하기가 어려울 것이다. 따라서 해당 객체의 동작을 검증하기위해서는 의존성이 있는 객체들의 대역을 만들게 되고 이러한 대역을 만들기 위해 의존성 걸려있는 객체의 인터페이스를 이용한다.

<br/> 

앞서 언급한 것처럼 속도면에서도 대역이 필요하다. 만약 I/O작업을 하게 될 경우 필연적으로 검증하는데 시간이 지체될 것이다. I/O 작업 클래스 대역을 만들어 놓으면 객체를 1번 테스트할 시간에 여러번 할 수 있을 것이다.

 <br/>

이번 챕터에서 가장 인상적인 문구는 유닛테스트는 코드조각을 테스트하는 것이 아니라 유의미한 행동을 테스트하는 것이다.라는 부분이었다. 유닛테스트를 작성한다는 것은 어떤 문제에 대한 단위 행동을 테스트하는 것이고 이러한 스토리가 없을 때는 테스트 작성을 다시 한 번 고려해보아야한다. 이런 관점에서 비즈니스 로직은 반드시 유닛테스트가 작성되어야함을 알 수 있었다.

 <br/>

챕터 말미에는 통합테스트에 대한 언급도 조금 나왔는데 통합테스트는 시간이 오래걸리기 때문에 유닛테스트를 빌드할 때마다 돌리는 등 자주 돌리는 사이클에 넣는다면 통합테스트는 푸시할 때 한 번 등 마지막에 적은 횟수로 테스트하는 것이 효율적임을 알 수 있었다.


<br/>
<br/>
<br/>

#

### Chapter 3. The anatomy of a unit test 주요 문장


We start by thinking about the objective: what a particular behavior should to do for us. The actual solving of the problem comes after that

 <br/>

>Two popular patterns can help you reuse the code in the arrange sections: Object Mother and Test Data Builder


<img src="https://github.com/user-attachments/assets/5fb1d50d-f361-4ee2-a5fb-b130fd8f2a6f" width="300">

<br/>

A typical application exhibits multiple behaviors. The greater the complexity of the behavior, the more facts are required to fully describe it. Each fact is represented by a test. Similar facts can be grouped into a single test method using parameterized tests.


<br/>
<br/>

### Chapter 3. The anatomy of a unit test 읽고 나의 생각

테스트 작성에 대한 구체적인 방식을 소개하는 챕터였다. 새롭게 알게된 점은


1. Given이 When, Then 의 코드를 합친만큼의 크기를 가진다.
2. Given에는 대표적으로 Object mother 와 Test Datqa Builder 가 들어간다.
3. 하나의 행동에는 여러가지 상황을 테스트해야할 수 있는데 이때는 파라미터에 여러가지 상황을 넣어 테스트한다.

```dart
import 'package:flutter_test/flutter_test.dart';

void main() {
  final delivery = Delivery();

  group('Delivery date validation', () {
    final today = DateTime.now();

    final testCases = {
      'Past Date': today.subtract(Duration(days: 1)),
      'Today': today,
      'Tomorrow': today.add(Duration(days: 1)),
      'Day After Tomorrow': today.add(Duration(days: 2)),
    };

    testCases.forEach((description, date) {
      test('$description: Delivery allowed', () {
        final result = delivery.isDeliveryAllowed(date);
        if (description == 'Day After Tomorrow') {
          expect(result, true);
        } else {
          expect(result, false);
        }
      });
    });
  });
}
```

<br/>
<br/>
<br/>

#

### Chapter 4. The four pillars of a good unit test  주요 문장

>It is integrated into the development cycle. It targets only the most important parts of your code base. It provides maximum value with minimum maintenance costs. You become confident that your code changes won’t lead to regressions

<img src="https://github.com/user-attachments/assets/8cb381ee-c9cf-4033-ae66-18713a2c4071" width="300">

>It aligns itself with the business needs by verifying the only outcome meaningful to end users

<img src="https://github.com/user-attachments/assets/a6bf8296-576c-4000-bc2f-e7e31cbd31cc" width="300">

<br/>

>False positives (false alarms) don’t have as much of a negative effect in the beginning. But they become increasingly important as the project grows—as important as false negatives (unnoticed bugs).

<br/>

>Unfortunately, it’s impossible to create such an ideal test. The reason is that the first three attributes—protection against regressions, resistance to refactoring, and fast feedback—are mutually exclusive. It’s impossible to maximize them all: you have to sacrifice one of the three in order to max out the remaining two

<br/>

<img src="https://github.com/user-attachments/assets/17749084-1189-4f40-b919-316211d9a7b3" width="300">


<br/>

>In reality, though, resistance to refactoring is non-negotiable. You should aim at gaining as much of it as you can, provided that your tests remain reasonably quick and you don’t resort to the exclusive use of end-to-end tests.

<br/>

<img src="https://github.com/user-attachments/assets/41892e3f-5d0f-4836-b668-42e0ceadd90d" width="300">

<br/>

>The trade-off comes down to the choice between protection against regressions and fast feedback.

<br/>

<img src="https://github.com/user-attachments/assets/75a312b8-7d3a-4ab0-8397-e4bf5d9e1b52" width="300">

>Therefore, choose black-box testing over white-box testing by default. Make all tests—be they unit, integration, or end-to-end—view the system as a black box and verify behavior meaningful to the problem domain.


<br/>
<br/>

### Chapter 4. The four pillars of a good unit test  읽고 나의 생각

좋은 단위테스트 원칙은 해당 코드에 수정이 들어가도 테스트 코드는 바뀌지 말아야한다는 것으로 요약할 수 있다. 즉 좋은 단위테스트는 핵심적인 주요 로직을 테스트하는 코드로 작성되어야만한다.

 <br/>

특히 한 SUT에 대한 테스트 코드를 작성함에 있어 private 메서드는 단위 테스트 작성을 하지 않아도 된다고 느꼈는데 public한 메서드는 다른 클라이언트 객체와 소통하기 때문에 단위테스트를 작성하지만 SUT의 내부로직을 담고 있는 프라이빗 메서드에 대한 단위테스트를 작성하면 코드 변경에 취약하게 되기 때문이다.

 <br/>

테스트 코드 작성할 때 무엇을 고려해주는지도 배울 수 있었다. 먼저 포기할 수 없는 가치는 리팩토링에 유여한 테스트를 작성해야한다는 것이다. 선택사항으로는 두가지, 회귀(기능 추가, 삭제)와 빠른 피드백 사이에서 트레이드 오프를 해야하는데, 다시말해 짧은 짧은 단위테스트를 작성할 수록 테스트는 빨리빨리 돌릴 수 있지만 작은 기능 수정에도 테스트를 수정해야할 일이 생기며, 만약 end to end test같이 테스트 단위가 길어지면 작은 기능 수정에 있어서 테스트를 고치지 않아도 되지만 테스트 코드를 돌리는 시간이 길어진다. 개발함에 있어 이 두가지 요소를 고려해가며 적절한 타협점을 찾아야함을 알 수 있었다.

<Br/>

**그리고 마지막으로 언급한 중요한 점! 테스트 코드는 블랙박스 테스팅이 되어야 리팩토링에 유연해진다.**

<br/>
<br/>
<br/>

#

### Chapter 5. Mocks and test fragility 주요 문장


>A test double is an overarching term that describes all kinds of non-production-ready, fake dependencies in tests.

<br/>

<img src="https://github.com/user-attachments/assets/9c857d2c-520a-43ec-8362-6dd95e781414" width="300">

<br/>

>Mocks help to emulate and examine outcoming interactions. These interactions are calls the SUT makes to its dependencies to change their state.

<br/>

>Stubs help to emulate incoming interactions. These interactions are calls the SUT makes to its dependencies to get input data.

<br/>

<img src="https://github.com/user-attachments/assets/a0328a64-579a-42b7-ba04-1532e2834acd" width="300">

<br/>

>Asserting interactions with stubs is a common anti-pattern that leads to fragile tests.

<br/>

<img src="https://github.com/user-attachments/assets/7e089e15-bf14-48de-8770-d8f6c266e9c3" width="300">

>commands correspond to mocks, while queries are consistent with stubs.

<br/>

💡 용어정리<br/>
- Command: 시스템의 상태를 변경하는 메서드. 보통 반환 값이 없고(void 반환) 외부나 시스템 내부의 상태를 변화. 예를 들어, 데이터베이스에 값을 저장하거나 이메일을 전송하는 등의 작업

- Query: 시스템의 상태를 조회하는 메서드. 외부 상태를 변경하지 않으며, 단순히 데이터를 반환. 예를 들어, 데이터베이스에서 값을 조회하거나 객체의 속성을 반환하는 작업

<br/>

> In other words, tests must focus on the whats, not the hows. All production code can be categorized along two dimensions: Public API vs. private API (where API means application programming interface), Observable behavior vs. implementation details

<br/>

<img src="https://github.com/user-attachments/assets/f55f48a1-c067-472f-8639-01d5aecce584" width="300">

<br/>

>In a well-designed API, the observable behavior coincides with the public API, while all implementation details are hidden behind the private API.

<br/>

<img src="https://github.com/user-attachments/assets/709e58d3-301f-44a7-8470-8c1cb59547ae" width="300">

<br/>

>The API of User is not well-designed: it exposes the NormalizeName method, which is not part of the observable behavior.

<br/>

>Encapsulation is the act of protecting your code against inconsistencies, also known as invariant violations.

<br/>

>Exposing implementation details goes hand in hand with invariant violations

<br/>

<img src="https://github.com/user-attachments/assets/b3a3c5d0-3456-4485-97f6-3f1720b8bc3d" width="300">

<br/>

>Tests working with different layers have a fractal nature: they verify the same behavior at different levels. 

<br/>

>The use of mocks for out-of-process dependencies that you have a full control over also leads to brittle tests

<br/>
<br/>

### Chapter 5. Mocks and test fragility 나의 생각

대표적인 TestDouble 인 mock과 stub에 대해서 설명해주며 챕터가 시작되었다. mock과 stub의 차이는 interaction의 유무였다. 무엇보다 내가  지금까지 stub을 써왔는데 mock이라고 명명했다는 것을 알 수 있는 챕터였다.🥹 기억하자 mock은 행위검증, stub은 데이터 반환할 때 쓴다!! 따라서 stub을 쓸 때 주의사항은 사이드 이펙트가 있어서는 안된다.

<br/>


좋은 테스트 코드를 작성하기 위헤서는 좋은 원본 코드가 있어야한다. 코드는 크게 외부에 노출될 행동과 내부 구현체 메서드로 나뉘는데 이때 외부에 노출될 메서드의 네이밍이 상당히 중요하다는 점을 알 수 있었다. 다른건 몰라도 외부 노출 메서드는 이름만으로 이녀석이 어떤역할을 하는지 알 수 있어야한다.

<br/> 

왜 내부 구현체 메서드를 노출시키면 안되는지도 원리를 설명해주고 있었다. 결국 좋은 코드란 캡슐화가 잘된 객체들이고 이 캡슐화의 목적은 각 객체가 "예측가능하게" 움직여 서로 의사소통하는 것이다. 이러한 이때 내부구현체가 노출되는 순간 사이드이펙트에 노출되며 해당 객체는 더이상 "예측 가능하다"고 볼 수 없다. 예측가능하지 못한 객체들이 쌓이기 시작하면 코드의 복잡성은 기하급수적으로 증가한다.

<br/>

노출된 퍼블릭 메서드는 상위(ui)계층에서 하위(data)계층으로 내려가면서 비즈니스 로직의 세분화가 된다. 이렇게 함으로써 퍼브릭 메서드들이 일종의 프랙탈 구조를 만든다고 책에서 설명하고 있었다.

<br/>

이번 챕터에서 무엇보다 가장 인상깊은 문장은 "테스트는 무얼 하느냐(what)에 집중해야지 어떻게 하느냐(how)에 집중해서는 안된다"였다.



