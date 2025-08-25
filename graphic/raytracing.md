## 02. BASIC RAYTRACING

<br/>

### Rendering a Swiss Landscape

<img width="300" alt="image" src="https://github.com/user-attachments/assets/06560c66-656e-44ff-bc17-aa2507069c52" />
<img width="300" alt="image" src="https://github.com/user-attachments/assets/d0bfa9c2-d606-4f10-9d75-9dc47551565d" />

<br/>

- 사진과 같은 스위스 풍경을 컴퓨터에 알고리즘으로 그린다고 생각해보자
1. 먼저 시점을 고정한다 (컴퓨터 그래픽스 용어: **Camera**의 위치를 고정한다)
2. 전체 이미지 틀에 방충망을 씌워, 이 방충망을 통해서만 풍경을 보도록 고정한다 (컴퓨터 그래픽스 용어: **viewPort**를 설정한다)
3. 방충망의 한 칸 한 칸을 순서대로 쳐다보며 칠해가는데 이때 확대된 네모 칸 안에 색깔 중 가장 대표적인 색 하나를 칠한다. (컴퓨터 그래픽스 용어: **pixcel** 에 **ray** 를 쏜다)

<br/>

### Ray Equation

<img width="400" alt="image" src="https://github.com/user-attachments/assets/78200f85-c2c4-4b62-9856-5a9348ce2edc" />

<br/>

- 이때 "어느 픽셀"에서 쏴야할지 알려주는 방정식은 ray equation이다. (대표색상 결정 방정식은 쉐이딩(Shading) 방정식인데 이후 챕터에서 다룰예정)
- 공식: **P=O+t⋅D**
  - P: 점 (Point). 우리가 찾고 싶은 광선 위의 어떤 지점.
  - O: 원점 (Origin). 광선이 시작하는 지점. (우리 예제에서는 카메라 위치 (0,0,0))
  - D: 방향 (Direction). 광선이 나아가는 방향을 나타내는 벡터.
  - t: 파라미터 (Parameter). 광선을 따라 얼마나 멀리 갈지를 정하는 단순한 '숫자'입니다. '거리 계수'라고 보면 된다.

