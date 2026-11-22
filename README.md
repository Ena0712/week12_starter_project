


Project Information: 프로젝트 소개 및 Starter Project 정보
Installation: 설치·실행 방법 및 실행 화면
Source Code Exploration: 주요 파일 구조, useEffect 및 useRef 분석, 주요 코드 2개 설명
## Lab Implementation
- 각 랩의 todo를 따라 제작
## Lab Comparison

*useEffect의 Dependency Array가 필요한 이유는?*
- Dependency Array는 effect가 다시 실행할 때를 정해주는 배열로 불필요한 실행이 되는 것을 방지할 수 있다.

*Cleanup을 사용하지 않으면 어떤 문제가 발생할 수 있는가?*
- effect가 다시 실행될때에 타이머가 중복해서 실행되어 숫자가 2배, 3배같이 빠르게 올라가는 문제가 있다.

*useState와 useRef의 가장 중요한 차이는?*
- useState는 변경되면 렌더링을 하고 화면에 표시되는 값이 바꿜때 쓰고, useRef는 변해도 렌더링되지않고 유지되는 값이 필요할때 쓴다

*LAB 2와 LAB 4의 Timer 관리 방식은 어떻게 다른가?*
- lab2에서는 running이 ture가 되면 interval이 생기고 state가 바뀌면 effect가 타이머를 관리하는 방식이고, lab4는 start()가 interval을 호출하며 이벤트헨들러로 id를 통해 ref를 직접 시작하고 멈추는 명령어로 관리하는 방식이다.

## Customizing
- title 변경, css 색상 변경, console 오류 확인, 랩2와 랩4 css를 통해 타이머 상태 표시 기능 추가
Deployment: 실제 접근 가능한 Vercel URL
Weekly Review:




