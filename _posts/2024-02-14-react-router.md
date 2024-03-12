---
layout: post
title:  "[React] React-Router-Dom"
date:   2024-02-14 +0900
categories: [React]
tags: [react, react-router-dom]
---


## ✨ React-Router-Dom

SPA 방식의 리액트에서 각각의 Route(경로)에 따라 선택된 페이지를 렌더링 해주는 라이브러리

> `SPA(Single Page Application)`은 서버에서 필요한 데이터만 비동기로 받아와서 현재 화면에 다시 렌더링 하는 방식이다. 웹 페이지를 로딩하더라도 최신 업데이트를 신속하게 반영하면서 페이지 로딩 속도를 향상시키고 트래픽을 줄여 부드러운 페이지 전환이 가능하다.

### ⚡ Routing

사용자가 요청한 경로에 맞는 콘텐츠로 이동시켜 주는 것을 `라우팅(Routing)`이라고 한다.

### ⚡ BrowserRouter or HashRouter

react-router-dom의 라우터는 `<BrowserRouter>`와 `<HashRouter>` 두 가지가 있다. BrowserRouter는 HTML5의 history API를 활용하여 UI를 업데이트하고, HashRouter는 URL의 hash를 활용한 라우터이다. HashRouter는 정적인(static) 페이지에 적합하다. request와 response로 이루어지는 동적인 페이지를 제작할 때에는 BrowserRouter가 보편적으로 쓰인다.

### ⚡ Route

요청받은 pathname에 해당하는 컴포넌트를 렌더링 한다.

### ⚡ Switch or Routes

path의 충돌이 일어나지 않게 Route들을 관리한다. Swtich 내부에 Route들을 넣으면 요청에 의해 매칭되는 Route들이 다수 있을 때 제일 처음 매칭되는 Route만 선별하여 실행한다. 따라서 url 겹침이나 충돌 오류를 방지할 수 있다.
 
### ⚡ Link

앱 내에서 다른 경로로 이동하기 위한 컴포넌트이다. 이 컴포넌트를 사용하면 페이지를 새로 불러오는 것이 아닌 원하는 Route를 렌더링 해준다.

```javascript
import { BrowserRouter, Switch, Route, Link } from "react-router-dom";
import Coins from "./routes/Coins";
import Coin from "./routes/Coin";

function Router() {
  return (
    <BrowserRouter>
      <Switch>
        <Route path="/id"><Coin /></Route>
        <Route path="/"><Coins /></Route>
      </Switch>
    </BrowserRoter>

    <Link to={`/:id`}>Coin Name</Link>
  );
}
export default Router;
```