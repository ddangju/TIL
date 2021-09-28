# Array(배열)

- 배열을 생성할 때 사용하는 리스트 형태의 객체이다.

<br>


# Array를 선언할 수 있는 방법은?

```js

const arr = new Array();

const arr2 = [1,2];

```

<br>

# index를 통해 배열에 접근하기 


```js

const fruits = ["apple", "banana"]

console.log(fruits) ///[ 'apple', 'banana' ]
console.log(fruits.length) /// 2
console.log(fruits[fruits.length-1]) /// 'banana'
console.log(fruits[0]) ///'apple'
console.log(fruits[2])  ///밖에 있는 index접근하면 undefined

``` 

<br>

# Array looping

### for문

```js

const fruits = ["apple", "banana"]

for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

///'apple', 'banana'

```

<br>


### for...of문

```js

for (let fruit of fruits){
  
  console.log(fruit)
}

///'apple', 'banana'

```


<br>


### forEach

- forEach는 콜백함수를 받아온다. array에 들어가는 값마다 forEach()에서 전달한 callback함수를 실행한다.








