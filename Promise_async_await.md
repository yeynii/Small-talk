# Promise, async await

## Promise

<aside>
💡 Promise객체는 비동기 작업이 맞이할 미래의 완료 또는 실패와 그 결과 값을 나타냅니다

</aside>

 

- 특징
    
    ![Untitled](Promise,%20a%20933d9/Untitled.png)
    
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

- 참고사이트
    
    [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators)
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise)
