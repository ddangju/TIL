# promise?

- 자바스크립트는 기본적으로 동기적 언어이다. 이것의 문제점을 해결하기위해 나온것이 비동기 처리 중 하나인 **promise**이다. 

<br>


# promise의 사용

>**Promise**는 주로 서버에서 받아온 데이터를 화면에 표시할 때 사용한다. 일반적으로 웹을 구현할 때 서버에서 데이터를 요청하고 받아오기 위해 사용한다.

<br>


# promise 의 상태(state)

`promise`는 3가지 상태를 가질 수 있다.

- 작업진행중 = pendding : 대기 상태로서 resolve 나 reject 할 지 결정되지 않은 초기 상태이다.
- 성공 = fullfilled : 이행 상태로서 연산이 성공적으로 완료된 상태
- 에러 = rejected : 거부 상태로서 연산이 실패한 상태이다.

<br>

# promise의 형태 (Producer//필요한 promise만들기, Consumer//promise사용)


## producer 

new Promise(resolve,reject)
- promise는 excutor라는 callback함수를 전달하고 callback함수에는 resolve, reject를 전달 받는다



<br>



```js

const promise = new Promise((resolve, reject() => {
  setTimeout() => {
    resolve("성공");
    reject(new Error("실패"))
    }, 2000);
)};

```



<br>

## Consumer : then, catch, finally

- 위에서 만든 promise 사용해보기 


<br>



```js


promise.then((value) => {
  console.log(value); ///"성공"
})
  .catch(error =>{
    console.log(error)
 })
  .finally{() => (
    console.log(""); 
  });



///value는 promise가 정상적으로 실행되어 resolve 인자로 전달하는 값
///error는 promise가 작동하지 않아 reject 인자로 전달하는 값 
/// finally는 성공하든 실패하든 상관없이 무조건 호출되는 값


```

<br>



## promise chaining
- promise의 then을 호출하는 경우 똑같은 promise를 return하기 때문에 catch를 호출할 수 있다.


```js

const test = new Promise((resolve, reject) => {
  setTimeout(() => resolve(1), 1000); 
});

test
  .then(num => num*2)
  .then(num => num*3)
  .then(num => {
      return new Promise((resolve, reject) =>{
        setTimeout(() => resolve(num - 1), 1000);
      })
  })
  .then(num => console.log(num));

```



/////



```jsx
const promise = new Promise((resolve, reject) =>{});

console.log(promise);
//promise { <pending>}
```

<br>

```jsx
const promise = new Promise((resolve, reject)=>{
  resolve("resolve");
}); //Promise { 'resolve' }

promise.then((value) => {
  console.log(value);

const promise = new Promise((resolve, reject)=>{
  reject("reject");
}); //Promise { 'reject' }
```

``new Promise``에 전달되는 함수는 executor(실행자, 실행함수) 라고 부른다. ``실행함수``는 ``new Promise``가 만들어질 때 자동으로 실행되며 인자로 **resolve, reject** 받는다. 

- **resolve** 
성공적으로 끝난 경우 그 결과를 나타내는 값이 호출

- **reject** 
에러 발생 시 여러 객체를 나타내는 error와 함께 호출


한편 ``new Promise`` 생성자가 반환하는 ``promise`` 객체는 다음과 같은 **내부 프로퍼티**를 갖는다.

- ``state`` 
처음엔 ``pending(보류)``이며, ``resolve``가 호출되면 **fulfild**, ``reject``가 호출되면 **rejected**로 변한다.

- ``result``
처음엔 ``undefined``, ``resolve``가 호출되면 **value**, ``reject``가 호출되면 **error**로변한다.

![](https://images.velog.io/images/duswn38/post/81a242f7-94db-4d37-8aa2-0e400730d4c2/3.PNG)

<br>

# then, catch

프로미스의 결과나 에러를 받을 함수로 **.then, .catch**를 사용한다.

>**then()** 메서드는 **Promise**를 리턴하고 두 개의 콜백 함수를 인수로 받는다. 하나는 ``promise``가 **이행**했을 때, 다른 하나는 **거부**했을 때를 위한 콜백 함수이다.

>**catch()** 메서드는 에러가 발생한 경우만 다룬다. 
