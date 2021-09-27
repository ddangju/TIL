# Object(객체)


자바스크립트를 이루고 있는 거의 모든 것은 **객체**이다. 

객체는 여러 속성을 하나의 변수에 저장할 수 있도록 해주는 데이터 타입이다


<br>



## Object를 만드는 방법은?

```js

const obj = {} //브라캣을 사용한 객체리터럴

const obj2 = new Object();  /// new 키워드를 사용하여 만든다

```


<br>


## object 의 구성은

```js

{key:value} //key와 value로 이루어져있다

```



<br>


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
 
 
 <br>
 
 
 ## object의 value는 어떻게 가져올 수 있을까? 
 
 
 <br>

 
> object.key 또는 object[key] 로 접근할 수 있다!


 <br>


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
 
 
 <br>
 
 ### computed속성 예제)
 
 
 
 ```js
 
 var a = { b:1, c:2}

var b = "c"

console.log(a[b]+"와"+a.b) /// `2 와 1`

```
 
여기서 a[b]와 a.b는 다른 b이다. 

a[b]는 계산된속성으로 b에 "c"를 할당해주고 console.log를 호출하면 a[b]는 a["c"]가 되어 c의 값인 2가 나오게 된다.

a.b는 b의값 1이 나오게 된다! 
 
 
 
 
<br>

## object에 property를 추가할 수 있을까? : 네 

```js

const print = { name: "yeon", age:20 };
/// 이미 print에 객체를 할당했다

print.hasJob = true; 

//그리고 뒤늦게 객체를 추가할 수 있고 삭제할수도 있다. 

delete.print.hasJob;  


//하지만 error를 피하기 위해서 사용하지 않는 것이 좋다. 

```
 
 <br>
 
 
 ## for..in 과 for ..of
 
 ### 1) for (key in obj)

- 객체의 **key**에 접근하여 객체의 속성들을 반복작업 할 수 있다. 


<br>

#### 예제)

```js

/// 1) 

obj = {name:"yeon", age: 20}

for (key in obj) {
  console.log(key)  /// "name", "age"
  }
  
  
  
 /// 2)  
 
const array1 = {a :"가", b:"나", c:"다"}
let array2 = [];

for(i in array1) {
  
  array2.push(array1[i])
  console.log(array2)   /// [가]
                        /// [가, 나]
                        /// [가, 나, 다]
}


 ```
 
 위 2번 예제 경우 for in문에서 array1의 배열의 **key**가 블럭을 돌 때마다 i에 할당이 된다. 
 
 그리고 array1[i]는 array2의 빈배열에 차례대로 push된다. 
 
 
 ```js
 [] = array1[a]  /// [가]
 [a] = array1[b] /// [기, 나]
 [a,b] = array1[c] /// [가, 나, 다]
 
 ```
 
 
 ### 2) for (value of array)
 
 - 배열의 인덱스에 접근하여 값을 반복한다.
 
 ```js
 
 const array = [1, 2, 3, 4];
 
 for (value of array) {
  console.log(value); ///1,2,3,4
  }
  
```

<br>

## cloining 

- object를 복사하는 방법

#### 1) 

```js

const user = {name: "yeon", age: "20"}
const user2 = user;


const user3 = {};

for(key in user) {
  user3[key] = user[key];
}

console.log(user3)//// {name: "yeon", age: "20"}
```

<br>

for in 문이 실행하면?

```js

user3[name] = user[name];

```


<br>

user 오브젝트의 key가 user3[name]에 할당된다.
즉 user[name]이 user3[name]이 되므로 key의 값인 yeon이 나온다.
age도 똑같이 진행되고 user3의 값은 { name: "yeon", age: "20" } 이 출력된다.

<br>

#### 2) Object.assign(상속받는대상, 상속하는 대상)

- 상속 받는 대상은? 상속 하는 대상을 복사해 반영한 후 반환한다.
- 상속 하는 대상은? 상속 받는 대상에 반영하고자 하는 속성들을 갖고있다.


아래 예시를 확인해보자 

```js

const a = { a:1, b:2 };
const b = { b:3, c:4 };

const target = Object.assign(a,b);

console.log(target) /// {a:1, b:3, c:4}

```

위 코드는 **b**가 **a**를 상속한다. 즉 **b**가 복사하는 대상, **a**는 복사 하는 대상이다.

그래서 b의 경우 값이 2에서 3으로 바뀌었다  

복사하는 대상으로 배열도 가능하다. 

<br>


 
