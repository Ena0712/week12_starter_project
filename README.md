


## Project Information
- Timer 프로젝트의 요구 기능을 작성하고 수정하는 것

## Installation
- clone 후 npm install, npm run dev를 진행

## Source Code Exploration
```
src/
├── App.jsx          # Lab 탭 전환
├── App.css
├── main.jsx        # 전체 스타일
└── components
    ├── Lab1_EffectTimer.jsx
    ├── Lab2_TimerControl.jsx
    ├── Lab3_InputFocus_sx
    └── Lab4_RefTimer.jsx
```
- useEffect는 렌더링항 후에 일어나는 효과를 처리하고 Dependency Array가 바뀔때만 실행되게 한다.
- useRef는 렌더링해도 값을 유지하지만 값이 변경되도 렌더링이 되지 않는다.

```jsx
useEffect(() => {
  if (!running) return;
  const id = setInterval(() => {
    setCount(prev => prev + 1);
  }, 1000);
  return () => clearInterval(id);
}, [running]);
```
- running이 true가 되면 interval을 만들고 false가 되면 cleanup이 intervl을 정리한다.

```jsx
const start = () => {
  if (timerRef.current) return;
  timerRef.current = setInterval(() => {
    setCount(prev => prev + 1);
  }, 1000);
  setRunning(true);
};

const stop = () => {
  clearInterval(timerRef.current);
  timerRef.current = null;
  setRunning(false);
};
```
- 타이머아이디는 timerRef에 있고, state에는 running,count가 있다.timerRef.current가 이미 있으면 start가 끝나서 intervaldl 중복생성되지않는다.

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

## Deployment
https://week12-starter-project-tau.vercel.app

## Weekly Review
useEffect와 useRef의 차이와 USEREF에 대해 무엇인디 어떻게 쓰는지에 대해 알 수 있었다.
수업과 제공된 수업자료를 통해 따라가면 어렵지 않게 수행이 가능한 적절한 과제였다고 생각한다.




