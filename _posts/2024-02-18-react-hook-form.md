---
layout: post
title:  React Hook Form
date:   2024-02-18 +0900
categories: [React]
tags: [React, React Hook Form]
---


## ✨ React Hook Form

React 기반의 폼 관리 라이브러리로, 복잡한 폼을 간단하게 처리하고 상태 관리를 용이하게 해주는 도구이다.

### ⚡ 

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
