

# 자바스크립트 함수

- (자동 호출되는 함수)
- **선언적 함수 (일반 함수 : ``function() {   }``)**
- 익명 함수
- 콜백 함수
- 화살표 함수
- 디폴트 매개변수



#### 함수 (function) 
- **특정 기능을 수행**하고 결과를 돌려주는 독립적인 코드 집합
- 독립적인 모듈 {}
- 메소드, 모듈, 기능, 프로시저 등으로 불림
- 함수를 사용하기 위해서는 반드시 호출해야 함
- 함수는 호출하지 않으면 일 안 함

**함수 선언 형식**

```
function 함수명() {
		// 함수 body
	}
```

- 스스로 동작하는 함수
  - 함수 호출 없이도 자동 실행

```
(functuion(){
	// 함수 body
})();
```



#### 함수 사용 

- 함수를 사용하기 위해서는 반드시 호출
- 함수 호출 : 함수명()

```
function show() {
	alert("show()함수입니다.");
}

show(); 
: 필요한 곳에서 호출

<body onLoad="show()">
<button onClick = "show()">show</button>
: HTML 이벤트 속성에서 호출

function input(){
	show();
}
: 다른 함수 내에서 함수 호출 가능
```



#### 함수의 반환 값

- 함수 실행이 끝난 후 호출한 곳으로 돌려주는 결과 값
- 함수 내에서 return 문 사용

```
function sum(){
	return x +y;
}
document.write("합계 : " + sum())
: sum() 위치로 값 반환
```





#### 함수의 매개변수

- 함수 호출 시 전달된 값을 받기 위해 사용되는 변수

```
function sum(x,y){
	return x +y; 						// 함수 내에서만 사용하는 지역 변수로 사용
}
document.write("합계 : " + sum(10,20))
															(x,y) 인수(인자) 호출하면서 전달하는 값
```



**단위 함수**

```
toFixed(자릿수)
: 소수점 자리수 표시 함수 
evg.toFixed(2) : 소수점 이하 두 자리 출력

toLocaleString()
: 천단위 구분 기호 표시
amount.toLocaleString() : 1,000,000 표시
```



#### 함수 호이스팅

 - 함수 선언 보다 먼저 함수 호출해서 실행되는 기능
- function 키워드 사용해서 생성한 함수는 호이스팅 가능

```
show(); 
: 먼저 호출 : 함수 호이스팅 가능

function show() { … }  
: 나중에 함수 선언(정의)
```



#### 익명 함수 (Anonymous function)

- 함수명 대신 변수명에 함수 코드를 저장하는 구현 방식
- ``var 변수명 = function(매개변수) {    };``
- 익명 함수의 호이스팅 불가



#### 콜백 함수 (Callback Function)

- **매개변수로 함수를 전달바당서, 함수의 내부에서 실행하는 함수**
- **인자로 넘겨지는 함수를 콜백 함수라고 부름**
- 콜백 함수로는 주로 이름이 없는 익명 함수 사용
- (일반 함수도 콜백 함수로 사용 가능)
- 등록해 놓은 **이벤트** 또는 **특정 시점**에 되었을 때 **시스템에서 호출하는 함수**

#### 콜백 함수를 사용하는 이유

- 자바스크립트에서 **비동기 처리 방식의 문제점을 해결하기 위해 사용**
- 자바스크립트는 단일 스레드
- 하나의 작업이 끝나고 다른 작업을 수행
- 동시에 여러 개의 작업을 수행하지 않음
- 콜백 함수를 사용해서 **다른 작업이 끝나기 전에 비동기적으로 작업을 수행하는 것이 가능**

##### 콜백 함수 주의점

- 콜백 지옥 발생
  - 콜백 함수를 함수로 전달하는 과정이 반복적으로 이루어져 계속 들여쓰기 형식으로 콜백 함수를 하다보면
  - 감당하기 어려울 정도로 수준이 깊어짐

##### 콜백 지옥을 해결하기 위한 방법

- Promise : ES6 도입
- async-await : ES8 추가
  - callback 지옥 문제를 해결할 뿐 아니라 단순하고 직관적인 코드 작성이 가능



#### 콜백함수에서 지역 변수를 매개변수로 전달

함수 내의 지역변수를 콜백 함수 호출하면 전달 가능

```
function call(callback){
	var localVar = 1;
	callback(localVar);
}
```



####  동기적 / 비동기적 콜백 함수 예제

- 동기적 : 순서대로 수행
  - 예제 : function_callback_sync.html
- 비동기적 콜백 함수 사용 
  - 동시에 여러 작업 수행
  - function_callback_async.html



#### 화살표 함수 (Arrow Function)

- function 키워드 대신 화살표(=>)를 사용하여 간결한 방법으로 선언하는 함수

```
() => { …. } // 매개변수가 없는 경우

x => { … } // 매개변수 한 개인 경우. () 괄호 생략 가능

(x, y) => { … } // 매개변수가 여러 개인 경우. 괄호 생략 불가

x => { return x*x } // 리턴값 있는 경우

x => x * x // 1줄인 경우 return 생략 가능
```



#### 디폴트 매개변수 (Default Parameter)

- **매개변수를 디폴트**로 설정해 놓으면
- 전달되는 값이 없을 경우 디폴트 매개값으로 적용
- 순서 주의! 
  - 디폴트 매개변수와 일반 매개변수를 섞어서 사용할 경우 
  - 디폴트 매개변수를 맨 뒤에 위치시킴





# 자바스크립트 객체(Object)

- 내장 객체

- 브라우저 객체
- 문서 객체(DOM)
- 사용자 정의 객체



####  자바스크립트 내장 객체(Built in Object)

- 미리 정의되어 있는 객체
- 선언 과정을 통해 객체 변수를 정의해서 사용
- 특별한 경우에는 사용자 정의 객체를 정의하여 사용
- 대부분의 경우에는 내장 객체 사용

##### 대표적인 내장 객체

- Date : 날짜와 시간을 처리하기 위한 객체
- Array : 배열을 만들기 위한 객체
- String : 문자열을 다루기 위한 객체
- Math : 수학 계산을 위한 객체
- Screen : 화면의 해상도나 색상, 크기에 관한 정보를 제공하는 객체

#### 객체 생성 및 사용 예

- 생성
  - ``var today = new Date();``
  - ``var arr = new Array(3);``
- 사용 (객체. 메소드())
  - ``today.getMouth();``
  - ``arr.sort();``



> #### Date 객체

- 날짜와 시간을 관리해주는 내장 객체
- 웹 페이지에 오늘 날짜와 시간 및 요일 등 표시
- ``var today = new Date();``
- ``var month = today.getMonth();``

#### Date 객체의 시간/날짜 정보를 반환하는 메소드

<img width="500" alt="image-20220617203254037" src="https://user-images.githubusercontent.com/101630615/174290534-64ebfafb-1ab3-4034-87fe-801937672074.png">

#### Date 객체의 시간/날짜 정보를 설정하는 메소드

<img width="500" alt="image-20220617203238834" src="https://user-images.githubusercontent.com/101630615/174290530-79c24d6f-9e1b-4679-a668-92fa017016e0.png">



#### 날짜/시간 정보의 포맷을 변경하는데 사용되는 메소드

<img width="400" alt="image-20220617203210805" src="https://user-images.githubusercontent.com/101630615/174290523-97d68b8e-1dba-425c-9890-e73b20ab79a0.png">



#### Array 객체의 주요 메소드

<img width="500" alt="image-20220617203202237" src="https://user-images.githubusercontent.com/101630615/174290521-6c258532-7187-4429-8966-1c8ad3539d80.png">





#### Math 객체

- 수학적 계산에 필요한 함수 또는 상수 값 제공
- 상수 값은 속성으로
- 수학은 메소드로 제공
- Math 객체는 속성이나 메소드를 접근하기 위해 따로 객체 변수 선언하지 않음
- 형식 
  - ``Math.속성``
  - ``Math.메소드()``
- 예
  - Math.PI : 원주율
  - Math.abs() : 절대값

#### Math 객체의 주요 메소드

<img width="500" alt="image-20220617203151056" src="https://user-images.githubusercontent.com/101630615/174290516-7ecf0480-2f58-449b-a5f3-14d8cb03715c.png">



#### ``Math.random()``

- 1 ~ 10 사이의 수 중에서 랜덤 숫자 생성

```
var num = 1 + Math.floor(Math.random()*10);
```



#### String 객체

- 문자열 객체
  - ``var name = new String();``
  - ``name.fontsize(5);``
- new를 이용해서 객체를 생성하지 않고 상수 형태(“문자열”)로 문자열을 만들어도 객체의 특징 모두 사용
  - ``var name = “홍길동”;``
  - ``name.fontsize(5);``
  - 객체로 자동 변환 : 일시적



#### String 객체의 주요 메소드

<img width="452" alt="image-20220617203131803" src="https://user-images.githubusercontent.com/101630615/174290505-63eb31b2-1280-48d7-bc53-6dc2368c9578.png">
