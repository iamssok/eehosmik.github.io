---
layout: post
title:  Javascript ES6
date:   2024-02-01 +0900
categories: [Javascript]
tags: [Javascript, ES6]
---


## ✨ Variables

### ⚡ var

- function scope
- 코드가 길어지면 사용성을 파악하기 힘들어지며 값이 바뀔 우려가 있다.
- 런타임 이전에 '선언 단계'와 '초기화 단계'가 한 번에 진행된다.
- 이 때문에 var로 선언한 변수의 경우 호이스팅 시 undefined로 변수가 초기화 된다.

> 선언이 어디에 있든 런타임 이전 단계에서 먼저 실행되는 것을 `호이스팅(Hoisting)`이라고 한다.(var, const, let, function, class 키워드를 사용해 선언한 모든 식별자는 호이스팅 된다.)

### ⚡ const & let

- block scope
- 변수를 선언할 때 기본적으로 `const`를 사용한다.
- 재할당이 필요한 변수를 선언할 때는 `let`을 사용한다.
- '선언 단계'와 초기화 단계'가 따로 진행된다. 런타임 이전에 선언 단계가 먼저 실행되지만, 초기화 단계는 변수 선언문에 도달했을 때 실행되기 때문에 초기화 단계가 이루어지기 이전에 변수에 접근하려고 하면 `참조 에러(Reference Error)`가 발생한다.

> 스코프의 시작 지점부터 초기화 단계 시작 지점(변수 선언문)까지 변수를 참조 할 수 없으며, 변수를 참조할 수 없는 이 구간을 `일시적 사각지대(Temporal Dead Zone)`이라 부른다.

### ⚡ function scope & block scope

```javascript
// var 선언
var greeting = "Nice to meet you.";
var times = 1;
if (times > 0) {
  var greeting = "I'm back.";
  console.log(greeting); // I'm back.
}
console.log(greeting); // I'm back.

// let 선언
let greeting = "Nice to meet you.";
let times = 1;
if (times > 0) {
  let greeting = "I'm back.";
  console.log(greeting); // I'm back.
}
console.log(greeting); // Nice to meet you.
```


## ✨ Arrow Function

```javascript
// 일반 함수
function nameOf(arg) {}
const nameOf = function(arg) {};

// 화살표 함수
// 매개변수가 없는 경우
const nameOf = () => console.log('sisi');
nameOf();

// 매개변수가 하나인 경우
const sayHi = aName => "Hello " + aName;
const sayHi = (aName = "anon") => "Hello " + aName;
console.log(sayHi());

// 매개변수가 여려개인 경우
const numbers = (a, b) => a + b; // 간단하게 한줄로 표현할 땐 "{}" 없이 값이 반환
console.log(numbers(1, 2));

const numbers = (a, b) => { return a + b }; 
console.log(numbers(1, 2));

const numbers = (a, b) => { a + b }; // "{}"를 사용했는데 return이 없을 때 
console.log(numbers(1, 2)); // undefined

// 객체를 반환할 때
const numbers = () => ( { a: 1, b: 2, c: 3 } );
consoloe.log(numbers()); // { a: 1, b: 2, c: 3 };
```


## ✨ Strings

```javascript
const wrapper = document.createElement("div")
const friends = ['sisi', 'moon', 'capi'];
const list = `
 <ul>
  ${friends.map((friend) => `<li>${friend}</li>`).join("")}
 </ul>
`
wrapper.innerHTML = list;

// includes() : 문자열 및 배열에 특정 요소를 포함하고 있는지 판별, 결과를 true 또는 false로 반환
const isEmail = email => email.includes("@");
console.log(isEmail(html@naver.com));

// repeat() : 문자열에 주어진 횟수만큼 반복해 붙인 새로운 문자열을 반환
const CC_NUMBER = "6060";
const CC = `${"*".repeat(10)${CC_NUMBER}}`;
console.log(CC);

// startsWith() : 문자열이 특정 문자로 시작하는지 확인하여 결과를 true 또는 false로 반환
// endsWith() : 문자열에서 특정 문자로 끝나는지 확인하여 결과를 true 또는 false로 반환
const nameOf = "Mr. sisi";
console.log(nameOf.startsWith("Mr"));
console.log(nameOf.endsWith("sisi"));
```


## ✨ Array

```javascript
const friends = ['sisi', 'moon', 'capi'];

// map() : 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환
const addHeart = friends.map((friend) => friend + "❤️");
// find() : 배열에서 함수를 만족하는 첫번째 요소를 반환. 만족하는 값이 없으면 undefined를 반환
// findIndex() : 배열에서 찾은 요소의 인덱스를 반환
const found = friends.find((friend) => friend.includes("oo"));
// filter() : 주어진 배열에서 제공된 함수에 만족하는 요소로만 필터링해 배열을 반환
const filter = friends.filter((friend) => friend.includes("oo")); 

```