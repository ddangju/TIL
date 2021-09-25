# Object


```js

{key:value}

```

자바스크립트를 이루고 있는 거의 모든 것은 **객체**이다. 

객체는 여러 속성을 하나의 변수에 저장할 수 있도록 해주는 데이터 타입이다

예제 :

```js

const name = "yeon"
const age = 20;

function info(name,age){
  console.log(name);
  console.log(age);
  }
  
  info(name,age)
  
  ```
  
  <br>
 
 만약에 들어가는 인자 값이 점점 많아진다면?
 
 계속해서 변수에 값을 할당하고 받는 인자도 늘어날것이다 
 
 데이터 값이 늘어나는것을 간편하게 작성하기 위해서 object를 사용할 수 있다.
 
 <br>
 
 ```js
 
 function info(info){
  console.log(info.name);
  console.log(info.age);
 
 }
 
 const obj = {name:"yeon", age:20};
 
 info(obj);
 
 ```
 
 
  
