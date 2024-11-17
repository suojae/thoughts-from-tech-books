
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







