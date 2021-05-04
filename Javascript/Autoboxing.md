# Autoboxing
> 2021-05-04


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ul>
    <li><a href="#introduction">Introduction</a></li>
    <li><a href="#wrapper-object">Wrapper Object</a></li>
    <li><a href="#autoboxing">Autoboxing</a></li>
    <li><a href="#references">References</a></li>
  </ul>
</details>

## Introduction
js에서 Object는 Key-value 형태로 데이터를 저장하고 참조 연산자(.)로 Object의 프로퍼티에 접근할 수 있다<br>
그런데 Primitive한 값들에도 참조 연산자 사용이 가능하다
```typescript
const a = 1;
a.toString()
```

1은 Object가 아니라 값 그 자체인데 어떻게 이런 일이 가능할까?
<br><br>

## Wrapper Object
이를 이해하려면 먼저 Wrapper Object를 알아야 한다<br>
js에서는 Primitive Type에 대응하는 4가지 Wrapper Object가 존재한다
```typescript
String, Number, Boolean, Symbol
```

String, Number, Boolean, Symbol을 이용해서 생성된 Object를 Wrapper Object라고 한다<br>
생성된 Wrapper Object들은 Primitive value가 아닌, 해당 값을 갖고 있는 객체다
```typescript
const str = 'Hello, world!'
const strObject = new String(str)

console.log(str === strObject) // false
console.log(typeof strObject) // object
console.log(typeof str) // string
```
<br><br>

## Autoboxing
Autoboxing은 Primitive한 value에 참조 연산자를 사용했을 때 임시 Wrapper Object가 생성되고 그 Object에 접근하게 되는 js의 특징이다
```typescript
const a = 1
a.toString()
```

이 실제로는 다음과 같이 실행된다
```typescript
const a = 1
new Number(a).toString()
```

이렇게 Primitive value에 참조 연산자를 사용할 경우 Wrapper Object가 생성이 되고 이를 이용해서 코드가 실행되는데 이를 Autoboxing이라고 한다
<br><br>

### References
- https://velog.io/@jakeseo_me/자바스크립트-개발자라면-알아야-할-33가지-개념-2-자바스크립트의-원시-타입Primitive-Type-번역
