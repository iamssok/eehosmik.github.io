---
layout: post
title:  React useEffect
date:   2024-02-09 +0900
categories: [React]
tags: [React, useEffect]
---


## ✨ useEffect

- useEffect의 첫번째 인수는 setup 함수이며, 이 함수는 컴포넌트가 렌더링된 이후에 호출된다. setup 함수는 setup 코드를 통해 외부 시스템과 연결하고, 해당 시스템의 연결을 종료할 수 있는 cleanup 함수(정리함수)를 반환한다.
- 두번째 인수는 종속성 배열로 사이드 이펙트가 의존하는 모든 값을 포함하고 있는 배열이다. 

> useEffect(setup, [dependencies?])
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
      <button onCLik={onClick}>Click me</button>
    </div>
  );
}

export default App;
```