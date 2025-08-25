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

