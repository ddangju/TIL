
```js
console.log(this) //window가 출력된다. 

function 함수() {
  console.log(this);   ///window가 출력된다. 
}

const 오브젝트 = {
  data : "yeon"
  function : function() {
      console.log(this);     
   }
}

//// {
//  data : "yeon"
//  function : function() {
//      console.log(this);     
//   }
//}        
가 출력된다

```


위와 같이 **object**안에서의 **this**는 그 함수를 가지고 있는 **object**를 뜻한다. 즉, 나를 포함하고 있는 **object**

<br>


- arraow function의 경우에는?

```js

console.log(this); ///window

const 오브젝트 = {
  data : "yeon"
  function : () => {
      console.log(this);     ////window가 출력된다! 
   }
}
```

신문법인 화살표 함수는 this의 값을 새로 만들지 않고 상위 요소의 this의 값을 물려받는다.

> 여기서 {windows}는 함수나 변수를 작성하면 window라는 **오브젝트**에서 보관한다.
> 그래서 콘솔로 그냥 window가 출력되는 것이 아니라, **windows object**에 담겨있는 것이 출력되는 것이다.

<br>




