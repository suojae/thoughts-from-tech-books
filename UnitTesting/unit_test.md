
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

