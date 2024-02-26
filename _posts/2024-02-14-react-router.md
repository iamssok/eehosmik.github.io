---
layout: post
title:  React Router
date:   2024-02-14 +0900
categories: [React]
tags: [React, reactrouterdom]
---


## ✨ React Router

SPA 방식의 리액트에서 각각의 Route(경로)에 따라 선택된 페이지를 렌더링 해주는 라이브러리

> 사용자가 요청한 경로에 데이터가 전달될 수 있게 하는 것을 `라우팅(Routing)`이라고 한다.
> `SPA(Single Page Application)`은 서버에서 필요한 데이터만 비동기로 받아와서 동적으로 현재 화면에 다시 렌더링 하는 방식이다. 웹 페이지를 로딩하더라도 최신 업데이트를 신속하게 반영하면서 페이지 로딩 속도를 향상시키고 트래픽을 줄여 부드러운 페이지 전환과 함께 업데이트가 될 때까지 기다리는 시간을 단축시킨다.

```javascript
import { BrowserRouter, Switch, Route } from "react-router-dom";
import Coins from "./routes/Coins";
import Coin from "./routes/Coin";

function Router() {
  return <BrowserRouter>
    <Switch>
      <Route path="/id"><Coin /></Route>
      <Route path="/"><Coins /></Route>
    </Switch>
  </BrowserRoter>
}
export default Router;
```

### ⚡ Link

앱 내에서 다른 경로로 이동하기 위한 컴포넌트이다. 이 컴포넌트를 사용하면 페이지를 새로 불러오는 것이 아닌 원하는 Route를 렌더링 해준다.

```javascript
import { Link } from "react-router-dom";

function Coins() { 
  return(
    <Link to="/id"></Link>
    <Link to={{
      pathname: "/id",
      state: { name: "name"}
    }}>Coin Name</Link>
  )
}
export default Coins;
```