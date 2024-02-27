---
layout: post
title:  "[React] State"
date:   2024-02-06 +0900
categories: [React]
tags: [react, state, useState]
---


## ✨ State

### ⚡ useState

맨 처음 렌더링 될 때 초기 상태 값을 인수로 전달 받고, 최신 상태를 유지하는 값과 그 값을 업데이트 하는 함수를 반환한다.

> const [state, setState] = useState(initialState)
{: .prompt-info }

```javascript
import { useState } from "react";

function App() {
  const [counter, setCounter] = useState(0);
  const onClick = () => setCounter(counter + 1);
  return (
    <div>
      <h1>Total Clicks : {counter}</h1>
      <button onClick={onClick}>Click Me</button>
    </div>
  );
}

export default App;
```