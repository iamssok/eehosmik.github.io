---
layout: post
title:  "[React] Recoil"
date:   2024-02-18 +0900
categories: [React]
tags: [react, recoil, atom, selector, useRecoilState, useRecoilValue, useSetRecoilState]
---


## ✨ Recoil

React를 위한 상태관리 라이브러리

### ⚡ RecoilRoot

recoil을 사용하기 위해서는 사용하고자 하는 부모 컴포넌트에 `<RecoilRoot>`를 사용해야 한다. 보통 전역적으로 사용하기 때문에 루트 컴포넌트에 넣으면 좋다.

``` javascript
// index.tsx
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";
import { RecoilRoot } from "recoil";

ReactDOM.render(
  <React.StrictMode>
    <RecoilRoot>
      <App />
    </RecoilRoot>
  </React.StrictMode>
  document.getElementById('root')
);
```

### ⚡ Atom

- atom은 redux의 store와 같은 개념이다.
- 데이터 상태의 단위이며, 업데이트와 구독이 가능하다.
- atom의 값이 바뀌면 구독하고 있는 컴포너트는 모두 새로운 값으로 리렌더링 된다.
- 여러개 생성이 가능하다.
- atom은 key와 default값을 설정해 주어야 한다.
- key: 해당 atom을 식별하는데 필요한 고유한 문자열이며, 프로젝트 전체에서 다른 atom, selector에 대해 고유해야 한다.
- default: 초기값을 설정해준다.

```javascript
import { atom } from "recoil";

export const countState atom({
    key: 'countState',
    default: 0,
});
```

### ⚡ Selector

- atom에서는 불가능한 비동기 처리와 복잡한 로직을 구현할 수 있다.
- selector는 세가지 값을 가진다.
- key: 해당 selector를 식별하는데 필요한 고유한 문자열이며, 프로제그 전체에서 다른 atom, selector에 대해 고유해야 한다.
- get: 파생된 상태를 반환하는 곳이며, get(countState) 처럼 countState를 get하고 있으면 countState가 바뀔 때마다 새로운 값을 리턴해준다. get()을 여러번 사용 가능하고 그중 하나라도 변하게 되면 리렌더링 된다. 
- set: set 없이 get만 제공되면 selector는 read-only한 상태이지만 set을 제공하면 쓰기 가능한 상태를 반환한다.

```javascript
// atoms.tsx
import { atom, selector } from "recoil";

export const minuteState atom({
  key: "minutes",
  default: 0,
});

export const hourSelector selector({
  key: "hours",
  get: ({get}) => {
    const minutes = get(minuteState);
    return minutes / 60;
  },
  set: ({set}, newValue) => {
    const minutes = Number(newValue) * 60;
    set(minuteState, minutes);
  }
});
```

```javascript
// App.tsx
import { useRecoilState } from "recoil";
import { minuteState, hourSelector } from "./atoms";

function App() {
  const [minutes, setMinutes] = useRecoilState(minuteState);
  const [hours, setHours] = useRecoilState(hourSelector);
  const onMinutesChange = (event: React.FormEvent<HTMLInputElement>) => {
    setMinutes(+event.currentTarget.value); // number type +
  }
  const onHoursChange = (event: React.FormEvent<HTMLInputElement>) => {
    setHours(+event.currentTarget.value);
  }
  return (
    <>
      <input value={minutes} onChange={onMinutesChange} type="number" placeholder="Minutes" />
      <input value={hours} onChange={onHoursChange} type="number" placeholder="Hours" />
    </>
  )
}
export default App;
```

### ⚡ useRecoilState

상태를 읽고 변경할 때 사용한다.

```javascript
import { atom, useRecoilState } from "recoil";

const modeThemeAtom = atom({
  key: "modeTheme",
  default: true,
})

function App() {
  const [mode, setMode] = useRecoilState(modeThemeAtom);
  const toggleModeAtom = () => setMode(prev => !prev);
  return (
    <button onClick={toggleModeAtom}>Mode Change</button>
  )
}
export default App;
```

### ⚡ useRecoliValue

컴포넌트에서 상태를 읽어오기만 하면될 때 사용한다.

```javascript
import { atom, useRecoilValue } from "recoil";

const modeThemeAtom = atom({
  key: "modeTheme",
  dafault: true,
})

function App() {
  const modeTheme = useRecoilValue(modeThemeAtom);
  console.log(isDark);  // true
  return null;
}
export default App;
```

### ⚡ useSetRecoilState

상태를 변경할 때 사용한다.

```javascript
import { atom, useSetRecoilState } from "recoil";

const modeThemeAtom = atom({
  key: "modeTheme",
  dafault: true,
})

function App() {
  const setMode = useSetRecoilState(modeThemeAtom);
  const toggleModeAtom = () => setMode(prev => !prev);
  return <button onClick={toggleModeAtom}>Mode Change</button>
}
export default App;
```
