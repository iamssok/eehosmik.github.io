---
layout: post
title:  React Router
date:   2024-02-14 +0900
categories: [React]
tags: [React, React Router]
---


## ✨ React Router

SPA 방식의 리액트에서 각각의 Route(경로)에 따라 선택된 페이지를 렌더링 해주는 라이브러리

> 사용자가 요청한 경로에 데이터가 전달될 수 있게 하는 것을 `라우팅(Routing)`이라고 한다.

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

<Link to="/id"></Link>
<Link to={{
  pathname: "/id",
  state: { name: "name"}
}}>Coin Name</Link>
```