## 

- 참고사이트
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Generator](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Generator)
    
    [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators)
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise)
    

## 제너레이터(Generator, 생성기)

<aside>
💡 Generator 객체는 generator function으로부터 반환된 값이며 반복자와 반복자 프로토콜을 준수합니다.
**코드 블록의 실행을 일시 중지 (블로킹) 했다가 필요한 시점에 재개할 수 있는 특수한 함수**

</aside>

### 특징

- iterator이고 iterable이다.
    - Iterable
        
        Symbol.iterator 메서드가 있다.
        
        Symbol.iterator는 iterator를 반환해야 한다.
        
    - itrator
        
        next 메서드를 가진다.
        
        next 메서드는 value와 done속성을 가진 객체를 반환한다.
        
        작업이 끝나면 done은 true가 된다.
        
- 함수의 실행을 중간에 멈췄다가 재개할 수 있는 기능. 다른 작업을 하다가 다시 돌아와서 next() 해주면 진행이 멈췄던 부분부터 이어서 실행
- 요청에 따라 그 산출된(yielded, yield 식으로 산출된) 값을 계산하고, 계산하기 비싼(힘든) 수열 또는 무한 수열이라도 효율적으로 나타내게함.
- 값을 미리 만들어두지 않아 메모리 관리 측면에서 효율적임
- break가 없는 while(true)도 사용가능함
- 필요한 순간까지 계산을 미룰 수 있다

### 문법

```jsx
function* gen() {
	try {
	  yield 1;
	  yield 2;
	  yield 3;
	} catch (e) {
		console.log(e);
}

var g = gen(); // "Generator { }"
```

![스크린샷 2022-02-06 오후 6.39.23.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/bc4994c4-0cf3-412e-8310-3593a1fa40f9/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-02-06_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_6.39.23.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220219%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220219T054855Z&X-Amz-Expires=86400&X-Amz-Signature=7fe7c4eac691b92dd72da9b8c96f17b6053b10a42ee0f941904f495ca81b8d4d&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA%25202022-02-06%2520%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE%25206.39.23.png%22&x-id=GetObject)

### 메서드

- next()
    
    yield 표현을 통해 yield된 값을 반환합니다. 가장 가까운 yield문을 실행하고 종료됩니다.
    
    또한 생성기의 내부 상태를 수정하는 데 쓰일 수 있는 값을 받습니다. `next()`에 전달되는 값은 생성기가 중단된 마지막 `yield` 식의 결과로 처리됩니다.
    
    - 예제
        
        ```jsx
        function* fibonacci(){
          var fn1 = 0;
          var fn2 = 1;
          while (true){
            var current = fn1;
            fn1 = fn2;
            fn2 = current + fn1;
            var reset = yield current;
            if (reset){
                fn1 = 0;
                fn2 = 1;
            }
          }
        }
        
        var sequence = fibonacci();
        console.log(sequence.next().value);     // 0
        console.log(sequence.next().value);     // 1
        console.log(sequence.next().value);     // 1
        console.log(sequence.next().value);     // 2
        console.log(sequence.next().value);     // 3
        console.log(sequence.next().value);     // 5
        console.log(sequence.next().value);     // 8
        console.log(sequence.next(true).value); // 0
        console.log(sequence.next().value);     // 1
        console.log(sequence.next().value);     // 1
        console.log(sequence.next().value);     // 2
        ```
        
- return()
    
    주어진 값을 반환하고 생성기를 종료합니다.
    
- throw()
    
    생성기로 에러를 throw합니다.
    

## Promise

<aside>
💡 Promise객체는 비동기 작업이 맞이할 미래의 완료 또는 실패와 그 결과 값을 나타냅니다

</aside>

 

- 특징
    
    ![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/76f15858-3cef-4af3-ab70-aec059c91b8d/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220219%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220219T054952Z&X-Amz-Expires=86400&X-Amz-Signature=011b37eebbe837006aa4405e29f3a598603a88c4f40b10e6974d41fab9050e4c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)
    
    - pending(대기), fulfilled(이행), rejected(거부) 상태를 가짐
        
        pending : 이행하지도 거부하지도 않은 초기 상태
        
        fulfilled : 연산이 성공적으로 완료됨
        
        rejected : 연산이 실패함
        
        → fulfilled, rejected를 통틀어 settled(처리) 라고 함
        
    - 여러개의 promise를 체이닝 가능
        
        `then()`, `catch()`는 promise를 반환하기 때문
        
    
    ```jsx
    const promise = new Promise((resolve, reject) => {
    	setTimeout(() => { resolve(1) },1000)
    });
    
    promise
    	.then(a => a + 1)
    	.catch()
    	.then(b => console.log(b))
    	.catch()
    ```
    

- 문법
    1. 생성자
        
        Promise()
        
        ```jsx
        const promise = new Promise(executor);
        ```
        
        **Promise가 만들어지는 순간 executor는 자동으로 실행된다**
        
    2. 정적 메서드
        
        all(iterable) : 주어진 모든 프로미스가 이행하거나, 한 프로미스가 거부될 때까지 대기하는 새로운 프로미스를 반환. 거부된다면 매개변수의 프로미스 중 거부된 첫 프로미스의 사유를 그대로 사용.
        
        allSettled(iterable) : 주어진 모든 프로미스가 처리될 때까지 대기하는 새로운 프로미스를 반환. 프로미스 각각의 상태와 값(또는 거부 사유) 을 모아놓은 배열로 이행.
        
        any(iterable) : 주어진 모든 프로미스 중 하나라도 이행하는 순간, 즉시 그 프로미스의 값으로 이행하는 새로운 프로미스를 반환. 전부 거부되면 `AggregateError` 와 함께 거부하는 프로미스를 반환
        
        race(iterable) : 주어진 모든 프로미스 중 하나라도 처리될 때까지 대기하는 프로미스를 반환
        
        reject(reson) : 주어진 사유로 거부하는 프로미스를 반환
        
        resolve() : 주어진 값으로 이행하는 프로미스를 반환
        
    3. 인스턴스 메서드
        
        then() : 프로미스에 이행및 거부 처리기 콜백을 추가하고, 콜백이 호출될 경우 그 반환값으로 이행하며 호출되지 않을 경우 처리된 값고 상태 그대로 처리되는 새로운 프로미스를 반환
        
        catch() : 프로미스에 거부 처리기 콜백을 추가하고, 콜백이 호출될 경우 그 반환값으로 이행하며 호출되지 않을 경우 이행한 값을 그대로 사용해 이행하는 새로운 프로미스를 반환
        
        finally() : 프로미스의 이행 및 거부 여부에 상관없이 처리될 경우 항상 호출되는 처리기 콜백을 추가하고, 이행한 값 그대로 이행하는 새로운 프로미스를 반환
        
        ```jsx
        promise
        	.then((value) => {
        		console.log(value)
        	})
        	.catch((error) => {
        		console.error(error)
        	)
        	.finally(() => {
        		console.log('done!')
        	})
        ```
        

## async ∙ await

코드를 비동기식으로 간편하고 간결하게 작성할 수 있게함

Promise 사용의 깔끔한 버전!

async await을 통해 Promise 반환 값을 받아 올 수 있다.

- 일종의 syntactic sugar
    - 사람이 이해 하고 표현하기 쉽게 디자인된 프로그래밍 언어 문법
    - 사람이 프로그래밍 언어를 sweeter하게 사용 할 수 있도록 도와주는 문법. 더욱 간결하고 명확하게 표현이 가능한 문법을 뜻 한다.

### Promise, async/await 예제

```jsx
function delay(ms) {
	return new Promise(resolve => setTimeout(resolve, ms));
}

async function getApple(){
	await delay(3000);
	return 'apple';
}

async function getBanana() {
	await delay(3000);
	return 'banana';
}

/* 프로미스 방식 */
function pickFruits1() {
	return getApple()
	.then(apple => {
		return getBanana().then(banana => `${apple} + ${banana}`);
	});
}

/* async await 방식 */
async function pickFruits2() {
	const apple = await getApple();
	const banana = await getBanana();
	return `${apple} + ${banana}`;
}

/* 병렬실행 */
async function pickFruits3() {
	const applePromise = getApple(); //프로미스는 만들자마자 실행이 됨
	const bananaPromise = getBanana();
	const apple = await applePromise;
	const banana = await bananaPromise;
	return `${apple} + ${banana}`;
}

/* Promise.all을 이용한 병렬실행 */
async function pickFruits4() {
	return Promise.all([getApple(), getBanana()]).then(fruits => fruits.join(' + '));
}

/* Promise.race를 이용하여 먼저 실행되는 함수의 결과만 실행 */
async function pickOnlyOne() {
	return Promise.race([getApple(), getBanana()]);
}

pickFruits().then(console.log);
pickOnlyOne().then(console.log);
```

### Promise vs async/await
|  | Promise | async/await |
| --- | --- | --- |
| 에러 핸들링 | .catch() | try-catch()문 |
| 코드 가독성 | .then지옥 | 비동기 코드가 동기 코드처럼 읽히기 해주어 코드 흐름을 이해하기 쉬움 |
