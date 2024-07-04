---
layout: post
title:  "[React] useEffect"
date:   2024-02-09 +0900
categories: [React]
tags: [react, useEffect]
---


## ✨ useEffect

- 컴포넌트가 렌더링 될 때마다 특정 작업을 실행한다.
- function: 해당 값이 업데이트 될 때 수행하고자 하는 함수
- deps: 배열 형태이며, 검사하고자 하는 특정값 또는 빈 배열

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