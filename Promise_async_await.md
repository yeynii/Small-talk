# Promise, async await

## Promise

<aside>
๐ก Promise๊ฐ์ฒด๋ ๋น๋๊ธฐ ์์์ด ๋ง์ดํ  ๋ฏธ๋์ ์๋ฃ ๋๋ ์คํจ์ ๊ทธ ๊ฒฐ๊ณผ ๊ฐ์ ๋ํ๋๋๋ค

</aside>

 

- ํน์ง
    
    ![Untitled](https://github.com/yeynii/Small-talk/blob/main/%E1%84%8C%E1%85%A6%E1%84%82%E1%85%A5%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%90%E1%85%A5/Untitled.png?raw=true)
    
    - pending(๋๊ธฐ), fulfilled(์ดํ), rejected(๊ฑฐ๋ถ) ์ํ๋ฅผ ๊ฐ์ง
        
        pending : ์ดํํ์ง๋ ๊ฑฐ๋ถํ์ง๋ ์์ ์ด๊ธฐ ์ํ
        
        fulfilled : ์ฐ์ฐ์ด ์ฑ๊ณต์ ์ผ๋ก ์๋ฃ๋จ
        
        rejected : ์ฐ์ฐ์ด ์คํจํจ
        
        โ fulfilled, rejected๋ฅผ ํตํ์ด settled(์ฒ๋ฆฌ) ๋ผ๊ณ  ํจ
        
    - ์ฌ๋ฌ๊ฐ์ promise๋ฅผ ์ฒด์ด๋ ๊ฐ๋ฅ
        
        `then()`, `catch()`๋ promise๋ฅผ ๋ฐํํ๊ธฐ ๋๋ฌธ
        
    
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
    

- ๋ฌธ๋ฒ
    1. ์์ฑ์
        
        Promise()
        
        ```jsx
        const promise = new Promise(executor);
        ```
        
        **Promise๊ฐ ๋ง๋ค์ด์ง๋ ์๊ฐ executor๋ ์๋์ผ๋ก ์คํ๋๋ค**
        
    2. ์ ์  ๋ฉ์๋
        
        all(iterable) : ์ฃผ์ด์ง ๋ชจ๋  ํ๋ก๋ฏธ์ค๊ฐ ์ดํํ๊ฑฐ๋, ํ ํ๋ก๋ฏธ์ค๊ฐ ๊ฑฐ๋ถ๋  ๋๊น์ง ๋๊ธฐํ๋ ์๋ก์ด ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ. ๊ฑฐ๋ถ๋๋ค๋ฉด ๋งค๊ฐ๋ณ์์ ํ๋ก๋ฏธ์ค ์ค ๊ฑฐ๋ถ๋ ์ฒซ ํ๋ก๋ฏธ์ค์ ์ฌ์ ๋ฅผ ๊ทธ๋๋ก ์ฌ์ฉ.
        
        allSettled(iterable) : ์ฃผ์ด์ง ๋ชจ๋  ํ๋ก๋ฏธ์ค๊ฐ ์ฒ๋ฆฌ๋  ๋๊น์ง ๋๊ธฐํ๋ ์๋ก์ด ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ. ํ๋ก๋ฏธ์ค ๊ฐ๊ฐ์ ์ํ์ ๊ฐ(๋๋ ๊ฑฐ๋ถ ์ฌ์ ) ์ ๋ชจ์๋์ ๋ฐฐ์ด๋ก ์ดํ.
        
        any(iterable) : ์ฃผ์ด์ง ๋ชจ๋  ํ๋ก๋ฏธ์ค ์ค ํ๋๋ผ๋ ์ดํํ๋ ์๊ฐ, ์ฆ์ ๊ทธ ํ๋ก๋ฏธ์ค์ ๊ฐ์ผ๋ก ์ดํํ๋ ์๋ก์ด ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ. ์ ๋ถ ๊ฑฐ๋ถ๋๋ฉด `AggregateError` ์ ํจ๊ป ๊ฑฐ๋ถํ๋ ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ
        
        race(iterable) : ์ฃผ์ด์ง ๋ชจ๋  ํ๋ก๋ฏธ์ค ์ค ํ๋๋ผ๋ ์ฒ๋ฆฌ๋  ๋๊น์ง ๋๊ธฐํ๋ ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ
        
        reject(reson) : ์ฃผ์ด์ง ์ฌ์ ๋ก ๊ฑฐ๋ถํ๋ ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ
        
        resolve() : ์ฃผ์ด์ง ๊ฐ์ผ๋ก ์ดํํ๋ ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ
        
    3. ์ธ์คํด์ค ๋ฉ์๋
        
        then() : ํ๋ก๋ฏธ์ค์ ์ดํ๋ฐ ๊ฑฐ๋ถ ์ฒ๋ฆฌ๊ธฐ ์ฝ๋ฐฑ์ ์ถ๊ฐํ๊ณ , ์ฝ๋ฐฑ์ด ํธ์ถ๋  ๊ฒฝ์ฐ ๊ทธ ๋ฐํ๊ฐ์ผ๋ก ์ดํํ๋ฉฐ ํธ์ถ๋์ง ์์ ๊ฒฝ์ฐ ์ฒ๋ฆฌ๋ ๊ฐ๊ณ  ์ํ ๊ทธ๋๋ก ์ฒ๋ฆฌ๋๋ ์๋ก์ด ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ
        
        catch() : ํ๋ก๋ฏธ์ค์ ๊ฑฐ๋ถ ์ฒ๋ฆฌ๊ธฐ ์ฝ๋ฐฑ์ ์ถ๊ฐํ๊ณ , ์ฝ๋ฐฑ์ด ํธ์ถ๋  ๊ฒฝ์ฐ ๊ทธ ๋ฐํ๊ฐ์ผ๋ก ์ดํํ๋ฉฐ ํธ์ถ๋์ง ์์ ๊ฒฝ์ฐ ์ดํํ ๊ฐ์ ๊ทธ๋๋ก ์ฌ์ฉํด ์ดํํ๋ ์๋ก์ด ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ
        
        finally() : ํ๋ก๋ฏธ์ค์ ์ดํ ๋ฐ ๊ฑฐ๋ถ ์ฌ๋ถ์ ์๊ด์์ด ์ฒ๋ฆฌ๋  ๊ฒฝ์ฐ ํญ์ ํธ์ถ๋๋ ์ฒ๋ฆฌ๊ธฐ ์ฝ๋ฐฑ์ ์ถ๊ฐํ๊ณ , ์ดํํ ๊ฐ ๊ทธ๋๋ก ์ดํํ๋ ์๋ก์ด ํ๋ก๋ฏธ์ค๋ฅผ ๋ฐํ
        
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
        

## async โ await

์ฝ๋๋ฅผ ๋น๋๊ธฐ์์ผ๋ก ๊ฐํธํ๊ณ  ๊ฐ๊ฒฐํ๊ฒ ์์ฑํ  ์ ์๊ฒํจ

Promise ์ฌ์ฉ์ ๊น๋ํ ๋ฒ์ !

async await์ ํตํด Promise ๋ฐํ ๊ฐ์ ๋ฐ์ ์ฌ ์ ์๋ค.

- ์ผ์ข์ syntactic sugar
    - ์ฌ๋์ด ์ดํด ํ๊ณ  ํํํ๊ธฐ ์ฝ๊ฒ ๋์์ธ๋ ํ๋ก๊ทธ๋๋ฐย ์ธ์ด ๋ฌธ๋ฒ
    - ์ฌ๋์ด ํ๋ก๊ทธ๋๋ฐ ์ธ์ด๋ฅผ sweeterํ๊ฒ ์ฌ์ฉ ํ  ์ ์๋๋ก ๋์์ฃผ๋ ๋ฌธ๋ฒ. ๋์ฑ ๊ฐ๊ฒฐํ๊ณ  ๋ชํํ๊ฒ ํํ์ด ๊ฐ๋ฅํ ๋ฌธ๋ฒ์ ๋ป ํ๋ค.

### Promise, async/await ์์ 

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

/* ํ๋ก๋ฏธ์ค ๋ฐฉ์ */
function pickFruits1() {
	return getApple()
	.then(apple => {
		return getBanana().then(banana => `${apple} + ${banana}`);
	});
}

/* async await ๋ฐฉ์ */
async function pickFruits2() {
	const apple = await getApple();
	const banana = await getBanana();
	return `${apple} + ${banana}`;
}

/* ๋ณ๋ ฌ์คํ */
async function pickFruits3() {
	const applePromise = getApple(); //ํ๋ก๋ฏธ์ค๋ ๋ง๋ค์๋ง์ ์คํ์ด ๋จ
	const bananaPromise = getBanana();
	const apple = await applePromise;
	const banana = await bananaPromise;
	return `${apple} + ${banana}`;
}

/* Promise.all์ ์ด์ฉํ ๋ณ๋ ฌ์คํ */
async function pickFruits4() {
	return Promise.all([getApple(), getBanana()]).then(fruits => fruits.join(' + '));
}

/* Promise.race๋ฅผ ์ด์ฉํ์ฌ ๋จผ์  ์คํ๋๋ ํจ์์ ๊ฒฐ๊ณผ๋ง ์คํ */
async function pickOnlyOne() {
	return Promise.race([getApple(), getBanana()]);
}

pickFruits().then(console.log);
pickOnlyOne().then(console.log);
```

### Promise vs async/await

|  | Promise | async/await |
| --- | --- | --- |
| ์๋ฌ ํธ๋ค๋ง | .catch() | try-catch()๋ฌธ |
| ์ฝ๋ ๊ฐ๋์ฑ | .then์ง์ฅ | ๋น๋๊ธฐ ์ฝ๋๊ฐ ๋๊ธฐ ์ฝ๋์ฒ๋ผ ์ฝํ๊ธฐ ํด์ฃผ์ด ์ฝ๋ ํ๋ฆ์ ์ดํดํ๊ธฐ ์ฌ์ |

- ์ฐธ๊ณ ์ฌ์ดํธ
    
    [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Iterators_and_Generators)
    
    [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Promise)
