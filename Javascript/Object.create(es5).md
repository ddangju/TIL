# Object.create() 

> Object.create() 메서드는 지정된 프로토타입으로 **새 객체**를 만든다. 


### 예제

```js

const 부모객체 = {name:"kim", age: 20} 

const 자식 = Object.create(부모객체); 

console.log(자식) 

```

<br>

### 결과

![7](https://user-images.githubusercontent.com/68775082/144198536-eac9cd5b-1b1c-4790-a0cc-bf2729889428.PNG)



 **부모 객체**를 **자식**이 상속받고 싶다면 위와 같이 `Object.create()` 메서드를 사용할 수 있다. 
 
 그리고 console.log로 확인해 본 결과는?
 
 `{}` => 새로운 오브젝트가 생성되고 아직 정해준 값이 없기 때문에 빈 오브젝트로 나온다! 
 
 `Prototypoe` => 상속되어있는 부모의 객체와 속성을 확인할 수 있다. 
 
 그리고 그 아래 `Prototypoe`은 부모의 부모에 대한 객체와 속성의 값을 확인해 볼 수 있다. 
 
 그 값은 constructor의 `Object()` 인 것을 확인해 볼 수 있다.
