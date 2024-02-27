---
layout: post
title:  "[React] React-Router-Dom Hooks"
date:   2024-02-15 +0900
categories: [React]
tags: [react, react-router-dom, useParams, useLocation, useRouteMatch]
---


## ✨ useParams

파라미터 값을 넘겨받을 수 있다.

```javascript
import { BrowserRouter, Switch, Route } from "react-router-dom";
import Coins from "./routes/Coins";
import Coin from "./routes/Coin";

function Router() {
  return <BrowserRouter>
    <Switch>
      <Route path="/:id"><Coin /></Route>
      <Route path="/"><Coins /></Route>
    </Switch>
  </BrowserRoter>
}
export default Router;
```
```javascript
import { useParams } from "react-router-dom";

function Coin() {
  const params = useParams();
  // 파라미터 값을 변수에 저장, 해당 값은 객체 형태
  // 이때 객체 프로퍼티의 key는 Route에서 설정한 path parameter
  // value는 path parameter에 전달된 값
  // /:id에서 id가 1이라면 { id : 1 } 

  // 동적 라우팅 값으로 걸어둔 이름으로 객체를 가져올 수 있다.
  const { id } = useParams();
  // 현재 주소의 값이 http://localhost:3000/1 이라면
  console.log(id);
  return <h1>path parameter: {params.id}</h1>
  // "1"이 출력
}
export default Coin;
```

## ✨ useLocation

사용자가 현재 머물러 있는 페이지에 대한 정보를 알려준다.

```javascript
import { Link } from "react-router-dom"

function Coins() {
  return <Coin>  
    <Link to={
      pathname: `/${id}`,
      state: { name: "btc" }
    }>Coin Name</Link>
  </Coin>
}
// Link to {{}}
export default Coins;
```

```javascript
import { useLocation } from "react-router-dom";

function Coin() {
  const { state } = useLocation();  // name: "btc"
  return <h1>{state.name}</h1>
}
export default Coin;
```

## ✨ useRouteMatch