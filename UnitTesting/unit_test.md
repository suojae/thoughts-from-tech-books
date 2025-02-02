
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


<br/>
<br/>
<br/>

#

### Chapter 6. Styles of unit testing 주요 문장

Unfortunately, you can’t use the output-based testing style everywhere. It’s only applicable to code written in a purely functional way. 

 <br/>
 
>there are three styles of unit testing: Output-based testing, State-based testing, Communication-based testing

<img src="https://github.com/user-attachments/assets/458d76ff-7dcc-440d-b4e4-e1a69f64369a" width="300">


<br/>

>In output-based testing, tests verify the output the system generates. This style of testing assumes there are no side effects and the only result of the SUT’s work is the value it returns to the caller.

<br/>

<img src="https://github.com/user-attachments/assets/eb247ad1-f5b5-4d2c-869e-dbb40208e237" width="300">

<br/>

>In state-based testing, tests verify the final state of the system after an operation is complete. The dashed circles represent that final state.

<br/>

<img src="https://github.com/user-attachments/assets/69c43885-fd99-466f-ab8d-3f957d3a37a6" width="300">

<br/>

>  In communication-based testing, tests substitute the SUT’s collaborators with mocks and verify that the SUT calls those collaborators correctly.


<br/>

<img src="https://github.com/user-attachments/assets/115060b6-c0da-4b7c-a891-f9f1ad8ecd69" width="300">

<br/>

>Output-based testing shows the best results. This style produces tests that rarely couple to implementation details and thus don’t require much due diligence to maintain proper resistance to refactoring. 

<br/>

<img src="https://github.com/user-attachments/assets/ad35b3de-866c-48cc-8d36-3f81ba807c50" width="300">

<br/>

>Explicit inputs and outputs make mathematical functions extremely testable because the resulting tests are short, simple, and easy to understand and maintain.

 
<Br/>

>The goal of functional programming is not to eliminate side effects altogether but rather to introduce a separation between code that handles business logic and code that incurs side effects


<Br/>

<img src="https://github.com/user-attachments/assets/836958e0-62b6-4d8a-86ab-f00e64a99567" width="300">


<br/>

>Tests can mock the filesystem and capture the writes the audit system makes to the files

<br/>

<img src="https://github.com/user-attachments/assets/7063025d-a313-4793-a94d-961205e3045f" width="300">

<Br/>

>Persister and AuditManager form the functional architecture. Persister gathers files and their contents from the working directory, feeds them to AuditManager, and then converts the return value into changes in the filesystem.

 
<br/>

<img src="https://github.com/user-attachments/assets/7f9263e0-7433-4824-a797-836116a59f00" width="300">

<br/>

>ApplicationService glues the functional core (AuditManager) and the mutable shell (Persister) together and provides an entry point for external clients.


<br/>
<br/>

### Chapter 6. Styles of unit testing 나의 생각

테스트하기 이상적인 환경은 원본 코드가 순수함수로만 작성되어 완벽하게 함수형 코딩으로 작성되어있는 상황일 것이다. 이렇게되면 단순히 인터페이스 퍼블릭 메서드의 아웃풋만 검사하면 사이드 이펙트 걱정이 없기 때문에 빈틈없이 테스트를 작성할 수 있기 때문이다. 하지만 현실은 멀티 패러다임이 적용되고 있다. 절차형으로 작성된 코드를 검증해야할 때도 많기 때문에 오직 output-based 테스팅만으로는 모든 테스트 유형을 만족시킬 수 없다.

<br/> 

테스트 유형에는 output based, state based, communication based 3가지가 있지만 최대한 output based 테스트를 지향해야하며 이를 위해서는 원본 코드를 될 수 있으면 함수형으로 작성해야한다. 

 <br/>

테스트 하는 대상은 크게 value와 collaborator로 나눌 수 있다. 전자는 불변(immutable)하고, 변경되지 않는 데이터이고 후자는 변경 가능한 상태를 가질 수 있거나, 외부 시스템과 상호작용하는 객체이다. 두 대상을 테스트할 때 value는 output-based로 (그러기 위해서는 함수형 코드 작성도 필수) collaborator는 state-based 또는 communication-based testing이 필요함을 알 수 있었다.

 <br/>

이부분을 읽으면서 백엔드와 소통하는 맨 뒷단은 mock을 만들어 커뮤니케이션 베이스 테스트를 작성하고 뷰모델에 있는 상태나 레포지토리에 있는 캐시는 상태 베이스 테스트, 나머지는 모두 인터페이스에 함수형을 두어 output based 테스트를 작성하는 것이 가장 바람직한 방법이라고 생각되었다. (솔직히 커뮤니케이션 테스트는 해야할 이유를 못느꼈다. 수정에 취약하고 만약 외부와 상호작용을 테스트하려면 mock만들 시간에 차라리 통합테스트를 작성하는게 더 낫지 않나 라는 생각이 들었기 때문이다.)


<br/>
<br/>
<br/>

#

### Chapter 7. Refactoring toward valuable unit tests 주요 문장

>Test and production code are intrinsically connected.

 <br/>

> Normally, all code in the domain layer has a direct connection to the end users’ goals and thus exhibits a high domain significance. On the other hand, utility code doesn’t have such a connection.

<br/>

<img src="https://github.com/user-attachments/assets/a8d2a7c9-5390-4e4e-b025-22f333bd9c89" width="300">

<br/>

>The four types of code, categorized by code complexity and domain significance (the vertical axis) and the number of collaborators (the horizontal axis).

<br/>

>To split overcomplicated code, you need to use the Humble Object design pattern.

<br/>

<img src="https://github.com/user-attachments/assets/be3676b4-6d39-46d5-a439-3b370464dc5d" width="300">

<br/>

>The Humble Object pattern extracts the logic out of the overcomplicated code, making that code so humble that it doesn’t need to be tested. The extracted logic is moved into another class, decoupled from the hard-to-test dependency.

<br/>


<img src="https://github.com/user-attachments/assets/3f373c03-b6ca-445c-a780-883a5b5d7292" width="300">

<br/>

>The functional core in a functional architecture and the domain layer in a hexagonal architecture reside in the top-left quadrant

<Br/>

<img src="https://github.com/user-attachments/assets/bf730574-1741-402e-a565-bdbd2ce91012" width="300">

<br/>

>Note that improved testability is not the only reason to maintain the separation between business logic and orchestration. Such a separation also helps tackle code complexity, which is crucial for project growth, too, especially in the long run.


<Br/>

<img src="https://github.com/user-attachments/assets/9c702ef2-53d2-4f2e-84e2-24e84d574cc2" width="300">

<br/>

>The separation between business logic and orchestration works best when a business operation has three distinct stages


<br/>

<img src="https://github.com/user-attachments/assets/8301c15b-b2dc-4c43-939f-eebe927a23d3" width="300">

<br/>

>controller simplicity, domain model testability, and performance. You have to choose two out of the three.

<br/>
<br/>

### Chapter 7. Refactoring toward valuable unit tests 나의 생각

테스트 코드와 프로덕션 코드는 서로 상호보완 관계에 있다. 이 책을 읽기 전까지는 테스트 코드는 반드시 프로덕션 코드에 부차적인 것이지, 절대 테스트 코드 작성을 위해 프로덕션 코드에 수정을 가해서는 안된다라는 생각이 있었다. 하지만 좋은 테스트 코드 작성을 위한 프로덕션 코드 리팩토링은 전체 코드 품질 향상에 기여할 수 있다는 점을 알 수 있었다. 구체적으로 책에서는 collaborator들이 많은 도메인 로직을 controller와 순수 도메인 로직으로 분리하는 리팩토링을 권하고 있다.

 <br/>
 

특히 이번챕터를 통해 모바일 프레젠테이션 레이어 패턴으로 자주 사용되는 MVC/MVP 가 humble object 패턴으로부터 비롯된 것임을 알 수 있었다. 결국 자주 변하는 것과 변하지 않는 것을 분리하고 변하지 않는 것은 최대한 "함수형"으로 작성함으로써 테스트에 더 적합한 코드를 작성할 수 있다.


<br/>
<br/>
<br/>

#

### Chapter 8. Why Integration testing? 주요 문장

<br/>

<img src="https://github.com/user-attachments/assets/1d00edd0-ab3a-4b7c-a6db-5b14edee20c8" width="300">

<br/>

>Integration tests cover controllers, while unit tests cover the domain model and algorithms. 

<br/>


>integration tests go through a larger amount of code (both your code and the code of the libraries used by the application), which makes them better than unit tests at protecting against regressions. They are also more detached from the production code and therefore have better resistance to refactoring.

<br/>

>check as many of the business scenario’s edge cases as possible with unit tests; use integration tests to cover one happy path, as well as any edge cases that can’t be covered by unit tests

<br/>

<img src="https://github.com/user-attachments/assets/76d81b01-ebff-4fac-99f1-ba1d5cbeafd2" width="300">

<br/>

>Fast, cheap unit tests cover the majority of edge cases, while a smaller number of slow, more expensive integration tests ensure the correctness of the system as a whole.

<br/>

>The sooner you detect a bug, the easier it is to fix. A bug that is already in production is orders of magnitude more expensive to fix compared to a bug found during development.

<br>

<img src="https://github.com/user-attachments/assets/4ff2634d-3a4e-4df9-8222-5b9b2b19c01a" width="300">

<br/>

>Communications with managed dependencies are implementation details; use such dependencies as-is in integration tests. Communications with unmanaged dependencies are part of your system’s observable behavior. Such dependencies should be mocked out.

<br/>

>Use real instances of managed dependencies; replace unmanaged dependencies with mocks.

<br/>

>Using real instances of managed dependencies in integration tests helps you verify that final state from the external client’s point of view.

 <br/>

 <img src="https://github.com/user-attachments/assets/251d0987-3469-4ee4-b66c-d67f4d2b9529" width="300">

<br/>

>Treat the part of the database that is visible to external applications as an unmanaged dependency. Replace it with mocks in integration tests. Treat the rest of the database as a managed dependency. Verify its final state, not interactions with it.

<br/>

<img src="https://github.com/user-attachments/assets/6127cf6b-f538-4c5b-aa45-ded4363806c6" width="300">
<img src="https://github.com/user-attachments/assets/682a6bb1-1c57-4f6a-8808-d53c04e963dd" width="300">

<br/>

>Integration tests host the application within the same process. Unlike end-to-end tests, integration tests substitute unmanaged dependencies with mocks. The only out-of-process components for integration tests are managed dependencies.

<br/>

>One of the most misunderstood subjects in the sphere of unit testing is the use of interfaces. Developers often ascribe invalid reasons to why they introduce interfaces and, as a result, tend to overuse them.

 <br/>

Abstract out-of-process dependencies, thus achieving loose coupling
Add new functionality without changing the existing code, thus adhering to the Open-Closed principle (OCP)
Both of these reasons are misconceptions. Interfaces with a single implementation are not abstractions and don’t provide loose coupling any more than concrete classes that implement those interfaces

 <br/>

Genuine abstractions are discovered, not invented. The discovery, by definition, takes place post factum, when the abstraction already exists but is not yet clearly defined in the code

<br/>

So, why use interfaces for out-of-process dependencies at all, assuming that each of those interfaces has only one implementation? The real reason is much more practical and down-to-earth. It’s to enable mocking—as simple as that. 

<br/>

You only mock out unmanaged dependencies, so the guideline can be boiled down to this: use interfaces for unmanaged dependencies only. 

<br/>
 

Circular dependencies also interfere with testing. You often have to resort to interfaces and mocking in order to split the class graph and isolate a single unit of behavior, which, again, is a no-go when it comes to testing the domain model


<br/>

<img src="https://github.com/user-attachments/assets/3201adc3-4022-4997-9f7e-061b7d68e5fb" width="300">

<br/>


With an interface, you remove the circular dependency at compile time, but not at runtime. The cognitive load required to understand the code doesn’t become any smaller.

<br/>
<br/>

### Chapter 8. Why Integration testing? 

 <br/>
 

최대한 비즈니스 로직은 단위테스트로 커버쳐야한다. 단위테스트로 검증하기 힘든 엣지케이스들을 한방에 통합테스트로 검사해야한다.

 

에러가 있으면 최대한 빨리 잡아내야한다. 그렇지 않으면 나중에 이런 에러가 중첩되어서 더이상 건들 수 없는 코드가 되어버린다.

 

인터페이스를 만드는 기준은 모킹을 해야하느냐 말아야하느냐 -> 외부 의존성 관리이냐 아니냐로 귀결

 

인터페이스를 두면 자연스럽게 계층이 늘어나진다 그리고 늘어난 계층만큼 코드의 복잡성은 증가한다. 적절한 추상화가 필요하다.

 

 

순환 의존성을 끊고싶을 때도 인터페이스를 두는 것이 좋다.

<br/>
<br/>
<br/>

#

### Chapter 9.  Mocking best practices 주요 문장

<br/>

<img src="https://github.com/user-attachments/assets/eff83815-8ea8-4a77-b994-ff02bc2ce930" width="300">
 
<br/>

>IBus resides at the system’s edge; IMessageBus is only an intermediate link in the chain of types between the controller and the message bus. Mocking IBus instead of IMessageBusachieves the best protection against regressions.

<br/>

>mocking is the only legitimate reason to have such interfaces

<br/>

>spy is a variation of a test double that serves the same purpose as a mock. The only difference is that spies are written manually, whereas mocks are created with the help of a mocking framework. Indeed, spies are often called handwritten mocks.

<br/>

>It turns out that, when it comes to classes residing at the system edges, spies are superior to mocks. Spies help you reuse code in the assertion phase, thereby reducing the test’s size and improving readability. 

<br/>

>Your code should either communicate with out-of-process dependencies or be complex, but never both. This principle naturally leads to the formation of two distinct layers: the domain model (that handles complexity) and controllers (that handle the communication).

<br/>

>On the contrary: the term unit means a unit of behavior, not a unit of code. The amount of code it takes to implement such a unit of behavior is irrelevant. It could span across multiple classes, a single class, or take up just a tiny method.

<br/>

>Abstract the underlying library’s complexity
>Only expose features you need from the library
>Do that using your project’s domain language
>As I explained previously, mocks are for unmanaged dependencies only. Thus, there’s no need to abstract in-memory or managed >dependencies. For instance, if a library provides a date and time API, you can use that API as-is, because it doesn’t reach >out to unmanaged dependencies

 <br/>

>Don’t rely on production code when making assertions. Use a separate set of literals and constants in tests. Duplicate those literals and constants from the production code if necessary. Tests should provide a checkpoint independent of the production code.

<br/>
<br/>

### Chapter 9.  Mocking best practices 나의 생각

<br/>

단위테스트에서 모킹이 사용되서는 안된다. 오직 통합테스트와 end -to-end 테스트에서 사용한다.

 

유닛테스트라고 하나의 sut만 두고 테스트한다는 것은 잘못된 생각이다. 유닛테스트는 하나의 "행동"을 테스트하는 것이 핵심이다.

 

유닛 테스트는 단일 기능적 행동을 검증하는 데 초점을 맞추며, 다른 클래스나 모듈이 관여하더라도 그 행동이 잘 수행되는지를 격리된 환경에서 확인만 하면 된다.

 

 

유닛테스트의 핵심은 단일 기능(행동)과 격리된 환경이다.

 

테스트 코드 쓴다면 프로덕션의 assert는 안쓰는 것이 좋다. 중복된 검증은 불필요한 코드이다.

 

<br/>
<br/>
<br/>

#

### Chapter 10.  Testing the database 주요문장

<br/>

>Keeping the database in the source control system
Using a separate database instance for every developer
Applying the migration-based approach to database delivery
No single source of truth— The model database becomes a competing source of truth about the state of development. Maintaining two such sources (Git and the model database) creates an additional burden.

<br/>

<img src="https://github.com/user-attachments/assets/491dc2d6-33e2-4f5a-bb82-f714e2493418" width="300">

<br/>

>The state-based approach makes the state explicit and migrations implicit; the migration-based approach makes the opposite choice.

<br/>

<img src="https://github.com/user-attachments/assets/b46486c0-f02d-4b88-8231-ea2ccb163103" width="300">

<br/>
 

>Wrapping each database call into a separate transaction introduces a risk of inconsistencies due to hardware or software failures

<br/>
 
>The transaction mediates interactions between the controller and the database and thus enables atomic data modification.


<br/>

The main advantage of a unit of work over a plain transaction is the deferral of updates. Unlike a transaction, a unit of work executes all updates at the end of the business operation, thus minimizing the duration of the underlying database transaction and reducing data congestion.

 

Database transactions also implement the unit-of-work pattern

 

 

Because there are hardly any abstraction layers in reads (the domain model is one such layer), unit tests aren’t of any use there. If you decide to test your reads, do so using integration tests on a real database.



Repositories exhibit little complexity and communicate with the out-of-process dependency, thus falling into the controllers quadrant on the types-of-code diagram.

 

 

Chapter 10.  Testing the database 나의 생각
 

데이터 베이스와 컨트롤러가 트랜섹션을 할 때 뭉탱이로 할게 아니라 데이터 별로 분리해놔야 일관성 유지에 용이해진다.

 

데이터를 묶어서 유닛단위로 처리해버리면 데이터 혼잡을 줄일 수 있다는 장점이 있다.

 

Object Mother와 Test Data Builder는 테스트에서 사용할 더미 데이터(dummy data) 또는 테스트 데이터를 생성하는 패턴으로 이해할 수 있습니다

 

Object Mother는 기본값을 가진 객체 생성 메서드를 제공하며, 단순하고 빠르게 기본 객체를 생성하는 데 유리합니다.
Test Data Builder는 플루언트 인터페이스를 통해 객체의 속성을 단계적으로 설정할 수 있으며, 복잡한 객체를 생성하는 데 적합합니다.
 

Chapter 11. Unit testing anti patterns 주요 문장

 

How to test the algorithm properly, then? Don’t imply any specific implementation when writing tests. Instead of duplicating the algorithm, hard-code its results into the test, as shown in the following listing

 

The problem with code pollution is that it mixes up test and production code and thereby increases the maintenance costs of the latter. To avoid this anti-pattern, keep the test code out of the production code base.


The ambient context pollutes the production code and makes testing more difficult



