## 호이스팅 (hoisting)
 
호이스팅이란? 함수 내부의 **선언문**을 모두 끌어올려서 해당 함수 유효 범위의 최상단에 선언하는 것을 말한다.

**함수 선언식, var, let, const** 는 **호이스팅** 이 일어난다. 

**Var의 경우** 선언과 초기화가 동시에 일어나기 때문에 호이스팅이 되면 **undefined**가 일어난다. 

<br>


var의 경우 예제)

```jsx

console.log(a); ////undefined(초기화)

var a = 1

console.log(a); /// 1 

```

<br>


함수선언식 경우 예제)


```jsx
catName("Chloe"); ///함수호출이 먼저 일어난다

function catName(name) {
  console.log("My cat's name is " + name);
}
/*
위 코드의 결과는: "My cat's name is Chloe" 
*/
```

<br> 


하지만 **let과 const**의 경우에는 호이스팅이 일어나지만 선언과 초기화가 분리되어 진행되는데,

호이스팅이 되면 선언이 진행되고 초기화는 진행되지 않아 `RefeerenceError`가 뜬다. 

선언만 되었기 때문에 **참조오류**가 뜬다. 

(let과 const가 호이스팅이 일어나지 않는다고 착각하지말자!)

```jsx
 console.log(a);///ReferenceError: a is not defined

let a = 1

console.log(a);
```


