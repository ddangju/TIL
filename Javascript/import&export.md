## export 

```js

<script type="module">

import a(작명) from "경로";


```

<br>

```js

var a = 10; 

export default a;
```

첫 번째 파일에서 `type`을 `module`로 정해주고 가져오고싶은 값이 있는 파일을 `import`로 연결한다. 

그리고 가져오고 싶은 값을 지정할 수 있다. 또 내보내는 파일에서는 `export default`를 잊지말고 해주어야 한다. 


여러 개를 내보내고 싶을 때는? `export {값1, 값2};` 형식으로 작성해줄 수 있다. 






