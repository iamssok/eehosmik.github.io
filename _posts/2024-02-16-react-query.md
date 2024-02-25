---
layout: post
title:  React Query
date:   2024-02-16 +0900
categories: [React]
tags: [React, React Query]
---


## ✨ React Query

- 서버 상태를 불러오고, 캐싱하며, 지속적으로 동기화하고 업데이트 하는 작업을 도와주는 라이브러리
- 기존의 복잡하고 장황한 코드가 필요한 데이터 불러오기 방식과 달리 컴포넌트 내부에서 간단하고 직관적으로 API를 사용할 수 있다.
- 캐싱을 통해 동일한 데이터에 대한 반복적인 비동기 데이터 호출을 방지하고, 이는 불필요한 API 콜을 줄여 서버에 대한 부담을 줄인다.

> 특정 데이터의 복사본을 저장하여 이후 동일한 데이터의 재접근 속도를 높이는 것을 `캐싱(caching)`이라고 한다.

### ⚡ useQuery

```javascript
import { useQuery } from "react-query";

function App() {
  return <h1></h1>
}

export default App;
```