---
layout: post
title:  React useEffect
date:   2024-02-09 +0900
categories: [React]
tags: [React, useEffect]
---


## ✨ useEffect

- 컴포넌트가 렌더링 될 때마다 특정 작업을 실행할 수 있도록 하는 Hook이다.
- function: 수행하고자 하는 작업
- deps: 배열 형태이며, 검사하고자 하는 특정값 또는 빈 배열을 넣는다.
- useEffect의 첫번째 인수는 setup 함수이며, 이 함수는 컴포넌트가 렌더링된 이후에 호출된다. setup 함수는 setup 코드를 통해 외부 시스템과 연결하고, 해당 시스템의 연결을 종료할 수 있는 cleanup 함수(정리함수)를 반환한다.
- 두번째 인수는 종속성 배열로 사이드 이펙트가 의존하는 모든 값을 포함하고 있는 배열이다. 

> useEffect(function, [dependencies?])
{: .prompt-info }

```javascript
import { useState, useEffect } from "react";

function App() {
  const [counter, setValue] = useState(0);
  const [keyword, setKeyword] = useState("");
  const onClick = () => setValue((prev) => prev + 1);
  const onChange = (event) => setKeyword(event.target.value);
  console.log("I run all the time.");
  useEffect(() => {
    console.log("I run only once.");
  }, []); 
  useEffect(() => {
    console.log("I run when 'counter' changes.");
  }, [counter]);
  useEffect(() => {
    console.log("I run when 'keyword' changes.");
  }, [keyword]);
  useEffect(() => {
    console.log("I run when 'counter&keyword' changes.");
  }, [counter, keyword]);
  return (
    <div>
      <input value={keyword} onChange={onChange} type="text" placeholder="Search here..." />
      <h1>{counter}</h1>
      <button onClick={onClick}>Click me</button>
    </div>
  );
}

export default App;
```

### ⚡ Cleanup 함수

```javascript
import { useState, useEffect } from "react";

function Hello() {
  useEffect(() => {
    console.log("hi :)");
    return () => console.log("bye :(");
  }, [])
  return <h1>Hello</h1>
}

function App() {
  const [showing, setShowing] = useState(false);
  const onClick = () => setShowing((prev) => !prev);
  return (
    <div>
      {showing ? <Hello /> : null}
      <button onClick={onClick}>{showing ? "Hide" : "Show"}</button>
    </div>
  );
}

export default App;
```