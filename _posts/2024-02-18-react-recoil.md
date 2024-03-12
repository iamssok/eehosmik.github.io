---
layout: post
title:  "[React] Recoil"
date:   2024-02-18 +0900
categories: [React]
tags: [react, recoil, atom, useRecoilValue, useSetRecoilState, useRecoilState]
---


## ✨ Recoil

React를 위한 상태관리 라이브러리

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
