<Promise객체의 필요성>  
-비동기 처리  
비동기 처리란 특정 코드의 연산이 끝날 때까지 코드의 실행을 멈추지 않고 다음 코드를 먼저 실행하는 자바스크립트의 특성  


함수의 인자로 전달되는 resolve는 함수이다  
resolve는 작업을 완료했을 때 호출하는 함수  
reject는 작업이 실패했을 때 호출하는 함수  
resolve 함수가 호출되면 .then() 안에 있는 함수가 자동 호출  
reject 함수가 호출되면 .catch() 안에 있는 함수가 자동 호출  
```
let work = new Promise(function(resolve, reject){})
```