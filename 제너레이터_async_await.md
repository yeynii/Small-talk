- 참고사이트
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Generator](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Generator)
    
    [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators)
    

## 제너레이터(Generator, 생성기)

<aside>
💡 Generator 객체는 generator function으로부터 반환된 값이며 반복자와 반복자 프로토콜을 준수합니다.

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
        
- 함수의 실행을 중간에 멈췄다가 재개할 수 있는 기능
- 생성자 함수는 요청에 따라 그 산출된(yielded, yield 식으로 산출된) 값을 계산하고, 계산하기 비싼(힘든) 수열 또는 위에 설명한 대로 무한 수열이라도 효율적으로 나타내게함.
- 값을 미리 만들어두지 않아 메모리 관리 측면에서 효율적임
- break가 없는 while(true)도 사용가능함
- 필요한 순간까지 계산을 미룰 수 있다
- 다른 작업을 하다가 다시 돌아와서 next() 해주면 진행이 멈췄던 부분부터 이어서 실행

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

![스크린샷 2022-02-06 오후 6.39.23.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/bc4994c4-0cf3-412e-8310-3593a1fa40f9/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-02-06_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_6.39.23.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220206%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220206T142114Z&X-Amz-Expires=86400&X-Amz-Signature=b21da7471f2254e56f6039b84de70a125d3943c39708fafcb5612d08ee6d7689&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA%25202022-02-06%2520%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE%25206.39.23.png%22&x-id=GetObject)

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
        
- reture()
    
    주어진 값을 반환하고 생성기를 종료합니다.
    
- throw()
    
    생성기로 에러를 throw합니다.
    

## async ∙ await

코드를 비동기식으로 간편하고 간결하게 작성할 수 있게함

promise 사용의 깔끔한 버전!

- 일종의 syntactic sugar
    - 사람이 이해 하고 표현하기 쉽게 디자인된 프로그래밍 언어 문법
    - 사람이 프로그래밍 언어를 sweeter하게 사용 할 수 있도록 도와주는 문법
        - 더욱 더 간결하고 명확하게 표현이 가능한 문법을 뜻 한다.

```jsx
async function fetchUser() {
	return 'yeyun';
	});
}

const user = fetchUser();
user.then(console.log);
```

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

## Promise

여러개의 promise를 체이닝이 가능

```jsx
function fetchUser() {
	return new Promise((resolve, reject) => {
		resolve('yeyun');
	});
}

const user = fetchUser();
user.then(console.log);
```
