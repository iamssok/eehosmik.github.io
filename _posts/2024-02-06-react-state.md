---
layout: post
title:  React State
date:   2024-02-06 +0900
categories: [React]
tags: [React, State]
---


## ✨ State

### ⚡ useState

- 맨 처음 렌더링될 때 초기 상태 값을 인수로 전달 받고, 최신 상태를 유지하는 값과 그 값을 업데이트 하는 함수를 반환합니다.

```javascript
import { useState } from "react";

function App() {
  const [counter, setCounter] = useState(0);
  const onClick = () => {
    setCounter(counter + 1);
  };
  return (
    <div>
      <h1>Total Clicks : {counter}<h1>
      <button onClick={onClick}>Click Me</button>
    </div>
  );
}

export default App;
```