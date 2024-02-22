---
layout: post
title:  React Router useParams
date:   2024-02-15 +0900
categories: [React]
tags: [React, React Router, useParams]
---


## ✨ useParams

- react-router-dom에서 제공하는 Hook중 하나로 파라미터 값을 넘겨받아 페이지에서 사용할 수 있다.

```javascript
import { BrowserRouter, Switch, Route } from "react-router-dom";
import { useParams } from "react-router-dom";

function Router() {
  return <BrowserRouter>
    <Switch>
      <Route path="/:id"><Coin /></Route>
      <Route path="/"><Coins /></Route>
    </Switch>
  </BrowserRoter>
}

function App() {
  const params = useParams();
  // /:id에서 id가 1이라면 { id : 1 } 
  // 파라미터 값을 변수에 저장, 해당 값은 객체 형태
  // 이때 객체 프로퍼티의 key는 Route에서 설정한 path parameter
  // value는 path parameter에 전달된 값
  return <h1>path parameter: {params.id}</h1>
  // 전달된 파라미터 값을 페이지에 활용
}

export default App;
```