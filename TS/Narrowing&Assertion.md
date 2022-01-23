## Type Narrowing 

Narrowing를 하는 이유는?

> 유니온 타입 같은 경우에는 타입을 정해주지 않아 에러가 뜬다. 그래서 유니온타입에도 타입을 하나로 지정해주어야한다 <br>
방법으로는 **if문과 typeof**키워드로 타입 검사를 해준다. 이 외에 방법으로는 **속성명 in 오브젝트자료**, **인스턴스 instanceof 부모** 가 있다.
<br>


예시)

```ts
function 내함수(x :number|string){
  return x + 1 /// 유니온타입 x에 number1을 더해주기 때문에 error 
}
```

```ts

function 내함수(x :number|string){
  if(typeof x === "number"){
    return x + 1
  } else {
    return
    }
}
```

<br>

## Type Assertion

> 타입을 간편하게 덮어씌우는 방식이다. 


예시)

```ts
function 내함수(x : number|string){

  let arr :number[] = [];
  array[0] = x as number;
}
```

유니온 타입인 x를 **number**타입으로 덮어씌운다.

**as**문법을 사용할 때는?

1. Narrowing할 때 사용한다.(변경할 때 사용X)
2. 들어오는 타입이 확실할 때 사용한다. 
