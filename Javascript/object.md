# Object


```js

{key:value} //key와 value로 이루어져있다

```

자바스크립트를 이루고 있는 거의 모든 것은 **객체**이다. 

객체는 여러 속성을 하나의 변수에 저장할 수 있도록 해주는 데이터 타입이다

### 예제)

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
 

 
 ```js
 
 function info(info){
  console.log(info.name);
  console.log(info.age);
 
 }
 
 const obj = {name:"yeon", age:20};
 
 info(obj);
 
 ```
 
 
 # object의 value는 어떻게 가져올 수 있을까? 

 
> object.key 또는 object[key] 로 접근할 수 있다!


### 예제)

```js

const kozy = {name: "kozy", age: 20};


function print(obj,key) {
  console.log(1, obj)  /// 1 { name: 'kozy', age: 20 }
  console.log(2, obj[key]) /// 2 'kozy'
}
  console.log(3, kozy.name) /// 3 'kozy'
  console.log(4, kozy["name"]) ///4 'kozy'
  console.log(5, kozy[name]) ///5 undefined

print(kozy, "name")

``` 
 
 5번의 경우 왜 undefined가 뜰까? 
 
 **object[key]** 경우 계산된 속성명(computed)으로 **변수**로 접근이 가능하다. 
 
 **변수**를 정해주지 않았다면 **object["key"]** 형태로 key값을 string으로 지정해주어야한다.
 
 그래서 위의 코드에
 
 ```js
 
 const name = "name"
 
 ```
 
 을 설정해주면 5번의 console.log 값은 'kozy'가 나온다. 
 
 name의 변수에 "name"을 지정해주었기 때문이다! 
 
 여기서 computed속성에 대해 더 알아보자
 
 ### 예제)
 
 
 
 ```js
 
 var a = { b:1, c:2}

var b = "c"

console.log(a[b]+"와"+a.b) /// `2 와 1`

```
 
여기서 a[b]와 a.b는 다른 b이다. a[b]는 계산된속성으로 계산된 b의 값, 즉 2가 나오게 되고 

a.b는 b의값 1이 나오게 된다! 
 

 
 
 
 
  