---
layout: post
title:  React Recoil
date:   2024-02-17 +0900
categories: [React]
tags: [React, Recoil]
---


## ✨ Recoil

Reacr를 위한 상태관리 라이브러리

### ⚡ useRecoliValue

컴포넌트에서 상태를 읽어오기만 하면될 때 사용하는 hook.

```javascript
import { atom, useRecoilValue } from "recoil";

export const isDarkAtom = atom({
  key: "isDark",
  dafault: true,
})

function App() {
  const isDark = useRecoilValue(isDarkAtom);
  console.log(isDark);  // true
  return null;
}

export default App;
```

### ⚡ useSetRecoilState

상태를 변경할 때 사용하는 hook. 

```javascript
import { atom, useSetRecoilState } from "recoil";

export const isDarkAtom = atom({
  key: "isDark",
  dafault: true,
})

function App() {
  const setDark = useSetRecoilState(isDarkAtom);
  const toggleDarkAtom = () => setDark(prev => !prev);
  return <button onClick={toggleDarkAtom}></button>
}

export default App;
```