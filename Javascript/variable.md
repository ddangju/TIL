# 자바스크립트 변수

## var, let, const

공통점?

변수를 선언하는 방법이다

변수는 `데이터`가 변한다. `데이터`는 저장하는 공간이 존재해야 한다.

이 공간을 `RAM`이라고 생각하면 된다.

```jsx

var a = apple;

let b = banana;

const c = kiwi;

```

let, const는 JS ES6문법이다.
var와 let, const와 차이점은 대표적으로 `Scope` 이다.
스코프란 `변수나 함수가 선언되어 사용할 수 있는 유효 범위` 에 대해 정의한다.



## var 와 let, const의 차이점 

var와 let, const 의 차이점은 `변수에 접근할 수 있는 범위` 이다. 


## 1) 함수 스코프 

`함수스코프` 는 함수 내에서 선언된 변수들을 함수 **내부**에서만 접근이 가능하며 **외부** 에서는 접근할 수가 없다. 

`var`을 사용한 예시 ) 

```jsx
function hello() {
  var a = "abcd";
  console.log(a);  //"abcd"
  return a;
}

console.log(hello()); 
console.log(a); // ReferenceError: a is not defined

```

## 2) 블럭 스코프

const,let을 사용하여 블럭 내에서 선언된 변수들은 내부에서만 접근이 가능하고 **외부**에서 접근할 수가 없다.
하지만 var경우 내부와 외부에서 접근이 가능하다.

변수선언 var 사용예시 )

```jsx
{
  var b = "456";
  console.log(b); ///"456"
}
console.log(b); ///"456"
```


변수선언 const 사용예시 )

```jsx
{
  const a = "123";
  console.log(a); ///"123"
}

console.log(a); ///ReferenceError: a is not defined

```

<br>

## 호이스팅 (hoisting)
 
호이스팅이란? 함수 내부의 선언들을 모두 끌어올려서 해당 함수 유효 범위의 최상단에 선언하는 것을 말한다.

`함수선언식`의 경우와 `var` 변수 선언에서 일어난다.

`var`는 함수 호출 이후 변수를 선언해도 함수가 호출된다.

const와 let은 호이스팅이 일어나지 않는다.



함수선언식 예시 )

```jsx
catName("Chloe");

function catName(name) {
  console.log("My cat's name is " + name);
}
/*
위 코드의 결과는: "My cat's name is Chloe"
*/
```

var 변수 선언 예시 )

```jsx

console.log(a);  //undefiend

var a = 3;

```

```jsx

var a; 
console.log(a); //undefiend
a = 3;
console.log(a); //3


```


