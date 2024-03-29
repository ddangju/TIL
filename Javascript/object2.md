## Object

```js

const num = 2;
const numObj = {num:2};

```
> 위의 경우에는 **num변수**에는 숫자 **2**자체가 들어있지만,
**numObj**에 오브젝트가 할당되면 **numObj**는 참조값이 할당된다. 

좀 더 쉽게 말하자면, 오브젝트의 고유한 참조값 예를들어 1234면 **1234**가 **numObj**에 할당된다. 

 

```js

const num = 2; ///2가 할당된다 
const numObj = {num:2}; ///1234라는 참조값이 할당된다. 

```

<br>

## Object를 복사하는 경우?

```js

const a = {id:'1', count:0}; 
const b = {id:'2', count:0};
const c = b;
```

이 경우에는 변수 **a**와 **b**가 각각 다른 참조값이 할당된다.  예를들어 1234는 a에 5678은 b에 할당된다.

그리고 **c**에는 **b**의 참조값 5678이 복사되어 할당된다!  

🔗 이것으로 **오브젝트**는 **값**자체가 변수에 저장되는 것이 아니라 **참조값**이 저장된다라는 것을 확인할 수 있다 

그렇다보니 const변수로 저장해도 **참조값**자체는 바꿀 수 없지만 **오브젝트 자체의 데이터**는 수정이 가능하다. 

```js
const arr = [
  {id:'첫번쨰', count:1},
  {id:'두번재', count:2}
  
]

arr = ["가", "나", "다"] ///TypeError: Assignment to constant variable. 
// 참조값 자체를 바꿀 수 없다 

```

<br>


```js
const arr = [
  {id:'첫번째', count:1},
  {id:'두번재', count:2}
  
]

arr[0].id = "hi"
console.log(arr)
////[ { id: 'hi', count: 1 }, { id: '두번재', count: 2 } ]
/// object자체의 데이터는 수정이 가능하다
```

<br>

## Spread Operator  경우?

```js

const arr = [ /// 참조값 1234
  {id:'첫번쨰', count:1}, ///참조값 5678
  {id:'두번재', count:2} ////참조값 910
  
]


const arr2 = arr;
const arr3 = [...arr] ///참조값 999 

```
<br>

arr[0]은  {id:'첫번쨰', count:1}의 참조값이 들어가고
arr[1]은 {id:'두번재', count:2}의 참조값이 들어간다.
그리고 **arr**배열은 **배열의 오브젝트 참조값**이 들어간다  

그리고 **arr2**에는 **arr**배열에 할당된 **참조값**이 그대로 할당되어 같은 **참조값**을 갖게 된다. 
**arr3**은 **spread operator**을 이용해 **새로운**배열을 만든다. 
🤷‍♀️ 하지만 이 메서드는 **object**내용물을 하나씩 복사해서 만드는 것이 아니라, **array배열**을 돌면서 각각의 아이템들의 **참조값을 복사**하게 된다.

그러니 더 쉽게 표현하자면 **껍데기**만 새로 만들어져 안에 들어있는 **object**들은 **arr배열안에 있는 아이템들의 참조값**을 복사해오는 것이다! 

그래서 만약 **arr**에서 id를 수정한다면 **arr3**도 동일한 값이 출력되는것을 확인할 수 있다.

<br>

```js

const arr = [
  {id:'첫번쨰', count:1},
  {id:'두번재', count:2}
  
]


const arr2 = arr;
const arr3 = [...arr]

arr[0].id="아이디"
console.log(arr3)
///
[
  { id: '아이디', count: 1 },
  { id: '두번재', count: 2 }
]

```
<br>

**arr** 배열 자체를 수정한다면 **arr2** 에서도 확인할 수 있지만, **arr3**에서는 확인할 수 없다. 
왜냐? **다른 배열 오브젝트**이기 때문이다!! 
아까 위에서 말햇듯이 **arr3**은 새로운 껍데기가 만들어지는것과 같아 다른 참조값을 가지고 있다.

