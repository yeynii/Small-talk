### 주제

- 클로저 (Closure)
- 스코프 체인 (Scope chain)

### 참고사이트

[https://ljtaek2.tistory.com/147?category=863722](https://ljtaek2.tistory.com/147?category=863722)

[https://hewonjeong.github.io/deep-dive-how-do-react-hooks-really-work-ko/](https://hewonjeong.github.io/deep-dive-how-do-react-hooks-really-work-ko/)

[https://www.youtube.com/watch?v=KJP1E-Y-xyo&t=972s](https://www.youtube.com/watch?v=KJP1E-Y-xyo&t=972s)

### 클로저(Closure)

<aside>
🌟 **[Closure]** makes it possible for a function to have “private” variables.

</aside>

- 함수 + 함수를 둘러싼 환경(Lexical environment)
- 자신이 생성된 시점의 환경을 기억하는 함수
- 외부 함수 호출이 종료되었어도 외부함수의 변수 or 인자에 접근 할 수 있다
- 왜 클로저(closure : 폐쇄)인가?
    
    외부에서 해당 함수 호출이 종료된 후에도 함수의 내부변수에 대한 메모리할당을 유지하지만 직접 볼 수 없게 “은닉화” 하기 때문
    
- **React hook들은 클로저로 구성되어있다 !**
    - 클로저로 만든 useState


        ![Untitled](https://user-images.githubusercontent.com/30085476/150357947-3fb6bb13-a0e7-406d-94e3-7d3cf37758ba.png)
        
        1. get() 방식의 state
            
            ```jsx
            function useState(initialValue) {
              var _val = initialValue // _val은 useState에 의해 만들어진 지역 변수입니다.
              function state() {
                // state는 내부 함수이자 클로저입니다.
                return _val // state()는 부모 함수에 정의된 _val을 참조합니다.
              }
              function setState(newVal) {
                // 마찬가지
                _val = newVal // _val를 노출하지 않고 _val를 변경합니다.
              }
              return [state, setState] // 외부에서 사용하기 위해 함수들을 노출
            }
            var [foo, setFoo] = useState(0) // 배열 구조분해 사용
            console.log(foo()) // 0 출력 - 위에서 넘긴 initialValue
            setFoo(1) // useState의 스코프 내부에 있는 _val를 변경합니다.
            console.log(foo()) // 1 출력 - 동일한 호출하지만 새로운 initialValue
            ```
            
        
        1. 내부 변수를 그대로 노출 (제대로 동작안함)
            
            ```jsx
            // 예제 0, 다시보기 - 버그 있음 주의!
            function useState(initialValue) {
              var _val = initialValue
              // state() 함수 없음
              function setState(newVal) {
                _val = newVal
              }
              return [_val, setState] // _val를 그대로 노출
            }
            var [foo, setFoo] = useState(0)
            console.log(foo) // 함수 호출 할 필요 없이 0 출력
            setFoo(1) // useState의 스코프 내부에 있는 _val를 변경합니다.
            console.log(foo) // 0 출력 - 헐!!
            ```
            
        
        1. 모듈 안에서의 클로저
            
            ```jsx
            const React = (function() {
              let _val; // 모듈 스코프 안에 state를 잡아놓습니다.
              function useState(initVal){
            		const state = _val || initVal;
            		function setState(newVal) {
            		        _val = newVal
            		};
            		return [state, setState];
            	}
              function render(Component) {
                  const C = Component();
                  C.render();
                  return C;
                }
            	return { useState, render };
            })();
            
            function Counter() {
              const [count, setCount] = MyReact.useState(1);
              return {
                click: () => setCount(count + 1),
                render: () => console.log(count),
              }
            }
            let App
            App = React.render(Counter) // 1
            App.click()
            App = React.render(Counter) // 2
            ```
            
        
        1. 여러개의 state를 받을 수 있는 방법(일반적인 형태). 내부 변수를 배열로 다루면 됨
            
            ```jsx
            const React = (function() {
              let hooks = [];
            	let idx = 0;
              function useState(initVal){
            		const state = hooks[idx] || initVal;
            		const _idx = idx;
            		function setState(newVal) {
            			hooks[_idx] = newVal
            		};
            		idx++;
            		return [state, setState];
            	}
              function render(Component) {
            			idx = 0;
                  const C = Component();
                  C.render();
                  return C;
                }
            	return { useState, render };
            })();
            ```
            

### 스코프 체인(Scope chain)

전역 객체와 중첩된 함수의 스코프의 레퍼런스를 차례로 저장하고 각각의 **스코프가 어떻게 연결되고 있는지 보여주는 리스트**

지역 변수 → 외부 함수의 변수 → 전역 변수 순으로 탐색 (즉, 안에서 밖으로)

**console.dir()**을 사용하면, 개발자 도구로 쉽게 확인이 가능하다.

[https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcBOUCL%2FbtqFOLXDO7A%2FIpd9ZJFtPelb1GHoUhA9UK%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcBOUCL%2FbtqFOLXDO7A%2FIpd9ZJFtPelb1GHoUhA9UK%2Fimg.png)

> 렉시컬 스코프(Lexical scope) : 함수의 **선언**에 따라 상위 스코프가 결정되는 것
> 
> 
> 함수가 어디에서 **호출**되었는지는 스코프 결정에 아무런 의미를 주지 않는다
> 
> *JS에서는 렉시컬 스코프를 따름*
> 

> 스코프(scope) : 변수에 접근할 수 있는 범위
>
