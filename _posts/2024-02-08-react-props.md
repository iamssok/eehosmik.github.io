---
layout: post
title:  React Props
date:   2024-02-08 +0900
categories: [React]
tags: [React, Props]
---


## ✨ Props

- 컴포넌트에 데이터를 전달하고자 할 때 사용하며, 이렇게 전달된 값을 변수를 통해 참조할 수 있다.
- React에서 데이터의 흐름은 부모 컴포넌트에서 자식 컴포넌트로 전달되므로, props의 닶은 해당 컴포넌트를 불러와 사용하는 부모 컴포넌트에서 설정할 수 있다.

```javascript
function Button({ text, boolean, fontSize = 12, onClick }) {
  return (
    <button 
      onClick={onClick}
      style={{
        padding: "10px 20px".
        backgroundColor: "black",
        border: 0,
        color: "white",
        fontSize: fontSize,
        marginRight: boolean ? 5 : 0,
      }}
    >
    {text}
    </button>
  );
}

function App() {
  const [value, setValue] = useState("save");
  const changeValue = () => setValue("revert");
  return (
    <div>
      <Button text={value} boolean={true} fontSize={18} onClick={changeValue} />
      <Button text="continue" boolean={false} />
    </div>
  );
}

export default App;
```