## ES 버전

<aside>
	
ECMA Script, ECMA-262
	
ECMA 인터내셔널에서 정한 자바스크립트의 표준

</aside>

### ES1 (1997)
	초판
	
### ES2 (1998)
	국제 표준과 완전히 동일한 규격을 적용
	
### ES3 (1999)
	JavsScript 기반이 다 여기서 만들어짐
	- 함수 단위의 스코프
	- 호이스팅
	- 프로토타입
	- 클로저
	- try-catch error handling
	
### ES4 (2000)
	- 버려짐.. 익스플로러 내맘대로 한다 선언... 2008년 크롬 등장하기 전까지 표준화 논의 더뎌짐
	
### ES5 (2009) ⭐️⭐️
	- 배열 관련 메소드(forEach, map, filter, reduce, some, every 등) 지원
	- Object에 대한 getter, setter 지원
	- strict 모드
	- Object.bind()
	- 실행컨텍스트 내에 존재하는 Lexical Enviroment
	- JSON 지원 ( 이전에는 XML사용 ) |

### ES5.1 (2011)
	- ES5 오류 수정버전
	
### ES6 (2015) ⭐️⭐️⭐️
	- Shorthand property names (key, value 이름이 같은경우 약식으로 쓰는 문법)
	- Destructuring assginment (구조 분해 할당)
	- Spread syntax (...)
	- Default parameters (함수의 파라미터에 default값을 부여하는 것) function a(a, b=1)
	- Ternary Operator (삼항 연산자)
	- Template Literals (백틱(``)을 이용하여 내장된 표현식을 허용하는 문자열 표현)
	- 함수 단위 스코프 → 블록 단위 스코프 변경
	- Arrow function
	- const, let
	- 모듈화 지원
	- Promise
	
### ES2016
	- 제곱 연산자 (**) 
	- Array.prototype.includes() (배열에 해당 요소가 존재하는지 확인하는 메소드)
	
### ES2017 ⭐️
	- aysnc/await
	- Object 메소드 추가
		- Object.values() : 객체 내 모든 value들을 배열 형태로 반환
		- Object.entries() : 객체 내 key, value를 묶어서 배열 형태로 반환
	- String 메소드 추가
		- String.padStart() : 문자열 앞에 여백 or 문자를 추가
		- String.padEnd() : 문자열 뒤에 여백 or 문자를 추가
	- 배열 원소 마지막에 콤마 붙이는 것 허용 (JSON에서는 안됨)

### ES201
	- 객체 리터럴에서의 전개 지원
	- Promise.prototype.finally()
	- Asynchronous Iteration // → 찾아봐야할듯 |

### ES2019
	- Array.flat() 추가 (중첩 배열 삭제, 데이터 정리 기능) 
	- Object.fromEntries(obj), Object.entries(obj) (배열 ↔ 오브젝트 변환)
	- try-catch 문법에서 catch에 매개변수 없어도 됨 |

### ES2020
	- Optional chaining (?.)
	- Nullish coalescing operator (?? 왼쪽 피연산자가 null, undefined인 경우 오른쪽 피연산자를 할당하는 문법)
	- globalThis (js 실행 환경에 관계없이 모든 환경에서 같은방법으로 global 객체에 접근 가능) 
	- Dynamic import (필요한 시점에 module Import 가능)
	- Big Int (정수 리터럴 뒤에 n을 붙이거나 함수 BigInt() 를 이용하면 큰 정수 표현 가능)
	- String.prototype.matchAll()
	- Promise.allSettled() |

### ES12 (2021)
	- String.prototype.replaceAll()
	- Promise.any()
	- WeakRef
	- Logical assignment operator ( ||=, &&=, ??=) 
	- Separators for numeric literals (_를 이용하여 큰 숫자 구분)

개발할 때는 최신 버전 문법으로하고 배포할때 BABEL을 이용해서 ES5~ES6 로 변환해서 실행!
