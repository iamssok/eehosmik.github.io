---
layout: post
title:  React useEffect
date:   2024-02-14 +0900
categories: [React]
tags: [React, React Router]
---


## ✨ React Router

### ⚡ Routing

사용자가 요청한 링크주소 즉, URL에 맞는 페이지를 찾아서 보여주는 것이라고 할 수 있다.

### ⚡ React Router

SPA 방식의 리액트에서 각각의 URL에 따라 선택된 페이지를 렌더링 해주는 라이브러리이다.

> npm i react-router-dom@5.3.0
{: .prompt-info }

```javascript
import { BrowserRouter, Switch, Route } from "react.router-dom";
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
```