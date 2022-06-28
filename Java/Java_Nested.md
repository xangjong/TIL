# [Java] 중첩 클래스 



### 중첩 클래스 (Nested Class)

-	클래스 내부에 선언한 클래스
-	클래스가 여러 클래스와 관계를 맺는 경우에는 독립적으로 선언하는 것이 좋으나
-	특정 클래스와 관계를 맺을 경우에는 관계 클래스를 해당 클래스 내부에 선언하는 것이 좋음

#### 중첩 클래스 사용 이점

-	두 클래스 멤버들을 서로 쉽게 접근 가능
-	코드의 복잡성 줄일 수 있음
-	관계 클래스는 중첩 클래스로, 불필요한 관계 클래스는 외부에서 감출 수 있기 때문에

#### 중첩 클래스 형태

<img width="452" alt="image-20220628210050964" src="https://user-images.githubusercontent.com/101630615/176176294-931696dc-a387-46a0-8641-ffe284e81534.png">

#### 중첩 인터페이스

-	클래스 내부에 선언된 인터페이스
-	해당 클래스와 긴밀한 관계를 맺는 구현 클래스를 만들기 위해 사용

<img width="452" alt="image-20220628210107399" src="https://user-images.githubusercontent.com/101630615/176176315-ca70eede-6237-4539-8c40-675bf7c6fcbf.png">

-	UI 컴포넌트 내부 이벤트 처리에 많이 활용
-	예로 안드로이드에서 View 클래스의 클릭 이벤트를 처리할 때
-	View 클래스 내부에 OnClickListener라는 중첩 인터페이스 사용



#### 클래스 내부에 선언되는 위치에 따라 2가지로 분류

-	멤버 클래스
  -	클래스의 멤버로서 선언되는 중첩 클래스
  -	클래스나 객체가 사용 중이면 언제든지 재사용 가능

-	로컬 클래스
  -	메소드 내에서만 선언되는 중첩 클래스
  -	메소드 실행 시에만 사용
  -	메소드가 실행 종료되면 없어짐


중첩 클래스도 클래스이기 때문에 컴파일 하면 바이트 코드 파일(.class)이 별도로 생성





### 중첩 클래스 분류

<img width="600" alt="image-20220628210138940" src="https://user-images.githubusercontent.com/101630615/176176317-4e83b6dd-68ee-498b-9010-5045b5e6d302.png">

(1) 인스턴스 멤버 클래스
-	static 키워드 없이 선언된 클래스
-	인스턴스 필드와 메소드만 선언 가능
-	static 필드와 메소드는 선언할 수 없음
-	바깥 클래스(A)의 객체를 생성해야만 사용할 수 있음



<img width="400" alt="image-20220628210217866" src="https://user-images.githubusercontent.com/101630615/176176323-e795d931-5321-4c15-aeda-93fdac1bf399.png">



A 클래스 외부에서 인스턴스 멤버 클래스 B의 객체를 생성하려면

-	먼저 A 객체를 생성하고  B객체 생성

<img width="500" alt="image-20220628210229688" src="https://user-images.githubusercontent.com/101630615/176176326-f3331aba-9cfd-4336-a93f-08bb3d996f0c.png">




(2) 정적 멤버 클래스
-	static 키워드로 선언된 클래스, 모든 종류의 필드, 메소드 선언 가능
-	A 클래스 외부에서 정적 멤버 클래스 객체를 생성하기 위해서는  A 객체 생성 필요 없음



<img width="550" alt="image-20220628210239178" src="https://user-images.githubusercontent.com/101630615/176176328-45c2db7e-7608-44de-b7c5-bf009058269a.png">





(3) 로컬 클래스

-	메소드 내에서 선언된 클래스
-	메소드 내에서만 사용하기 때문에 접근 제한 및 static 필요 없음 (안 붙임)
-	로컬 클래스 내부에는 인스턴스 필드와 메소드만 선언이 가능하고
-	static 필드와 메소드는 선언할 수 없음



<img width="400" alt="image-20220628210259296" src="https://user-images.githubusercontent.com/101630615/176176332-e78e66ef-b521-4b31-bb1d-be51d73785a5.png">





### 중첩 클래스의 접근 제한


(1) 바깥 필드와 메소드에서 사용 제한



<img width="600" alt="image-20220628210317474" src="https://user-images.githubusercontent.com/101630615/176176336-d9d86142-d2f9-4791-98e2-b198055176f6.png">





<img width="600" alt="image-20220628210330231" src="https://user-images.githubusercontent.com/101630615/176176337-ae0d49d4-58fe-4152-98bd-4cded20c5e9c.png">





(2) 멤버 클래스에서 사용 제한

<img width="600" alt="image-20220628210348238" src="https://user-images.githubusercontent.com/101630615/176176339-c3d34129-c319-4309-8d40-49b625a46dd8.png">

정적 멤버 클래스 C 안에서는
-	바깥 클래스의 
-	정적 필드와 메소드에만 접근 가능
-	인스턴스 필드와 메소드에는 접근 불가



(3) 로컬 클래스에서 사용 제한
-	로컬 클래스 내부에서는 바깥 클래스이 필드나 메소드를 제한 없이 사용 가능
-	문제는 메소드의 매개변수나 로컬 변수를 사용할 때 로컬 클래스의 객체는 메소드 실행이 끝나도 힙 메모리 영역에 존재하기 때문에 계속 사용될 수 있지만, 메소드 실행이 끝나면 매개변수나 로컬 변수는 스택 메모리에서 사라지기 때문에 로컬 객체에서 사용할 경우 문제 발생
-	문제 해결
  -	매개변수나 로컬 변수를 final로 선언해서 수정하지 못하게 함
  -	컴파일 시 로컬 클래스에서 사용하는 매개변수나 로컬 변수의 값을 로컬 클래스 내부에 복사해 두고 사용하는데
  -	매개변수나 로컬 변수가 수정되어 값이 변경되면 로컬 클래스에 복사해 둔 값과 달라지는 문제가 발생하니까 변경되지 않도록 final로 선언
  -	즉, 로컬 클래스에서 사용 가능한 것은 final로 선언된 매개변수와 로컬 변수 뿐 (로컬 클래스에서 사용하고자 하는 매개변수와 로컬 변수에는 ``final`` 선언 
    


##### 중첩 클래스에서 바깥 클래스 참조 얻기

-	this 사용
-	바깥클래스.this.필드
-	바깥클래스.this.메소드()



#### ``this``

-	클래스 내부에서 객체 자신 참조
-	중첩 클래스에서 중첩 클래스의 객체 참조 (바깥 클래스의 객체 참조 아님)
-	this.필드, this.메소드()로 호출하면
-	중첩 클래스의 필드와 메소드 사용 가능

<img width="600" alt="image-20220628210504319" src="https://user-images.githubusercontent.com/101630615/176176341-ba228d49-ec8e-4d9e-b364-c6f2ea85b4f9.png">







### 중첩 인터페이스

-	클래스 내부에 클래스의 멤버로 선언된 인터페이스
-	인터페이스를 클래스 내부에 선언하는 이유
  -	해당 클래스와 긴밀한 관계를 맺는 구현 클래스를 만들기 위해 (주로 클래스 외부에서는 사용하지 않고 클래스에서만 사용하는 경우에)
  -	특히 UI 프로그래밍에서 이벤트 처리 목적으로 많이 활용


#### 중첩 인터페이스 선언

<img width="700" alt="image-20220628210653387" src="https://user-images.githubusercontent.com/101630615/176176343-11c298e6-e459-4b65-8aef-3f175c7fe1d3.png">





### 익명 객체 생성

#### 1.익명 자식 객체 생성

​	일반적인 객체 생성

-	부모 클래스 상속해서 자식 클래스 선언하고
-	new 연산자를 이용해서 객체 생성한 후
-	필드나 로컬 변수에 대입

<img width="500" alt="image-20220628210721319" src="https://user-images.githubusercontent.com/101630615/176176347-e0052d0b-bf08-4fce-b460-028b62e4c6a5.png">



익명 자식 객체 생성

-	자식 클래스가 재사용되지 않고 해당 필드와 변수의 초기값으로만 사용할 경우라면
-	익명 자식 객체를 생성해서 초기값으로 대입하는 것이 좋은 방법
-	일반 클래스와 차이점은 생성자 생성 불가
-	익명 자식 객체 생성 방법

<img width="500" alt="image-20220628210737318" src="https://user-images.githubusercontent.com/101630615/176176351-09229ea0-7cf6-4b5e-ac10-f36243fd159c.png">



(1)	익명 자식 객체 생성해서 클래스의 필드에 대입

<img width="600" alt="image-20220628210750045" src="https://user-images.githubusercontent.com/101630615/176176352-c5745590-a280-4b78-a29b-6f22661cffbb.png">



(2)	메소드 내에서 로컬 변수를 선언할 때 초기값으로 익명 자식 객체 생성해서 대입

<img width="500" alt="image-20220628210801514" src="https://user-images.githubusercontent.com/101630615/176176357-e40824de-771a-4f22-ad6e-1008538e4573.png">



(3)	매개변수에 익명 자식 객체 생성해서 대입
메소드의 매개변수가 부모 타입일 경우 메소드 호출 코드에서 익명 자식 객체를 생성해서 매개값으로 대입

<img width="500" alt="image-20220628210815953" src="https://user-images.githubusercontent.com/101630615/176176360-bc4a6912-b00c-4c3d-a1d9-096dcfa760b7.png">





#### 익명 객체에 새롭게 정의된 필드와 메소드

-	익명 자식 객체 내부에서만 사용
-	외부에서는 익명 객체의 필드와 메소드에 접근할 수 없음
-	이유 : 익명 자식 객체는 부모 타입 변수에 대입되므로 부모 타입에 선언된 것만 사용 가능

<img width="600" alt="image-20220628210830458" src="https://user-images.githubusercontent.com/101630615/176176364-2eb5ec57-2afc-4f63-8628-f742b55137a9.png">

 

#### 익명 자식 객체의 필드와 메소드 접근 제한 정리

-	익명 자식 객체 내부에서만 사용
-	외부에서는 익명 객체의 필드와 메소드에 접근할 수 없음
-	익명 자식 객체는 이름이 없으므로 자신의 타입의 클래스를 만들지 못함
-	그래서 무조건 부모 타입의 변수에 대입(자동 타입 변환되어 대입)
  -	따라서 부모 타입의 필드로는 부모 타입으로 정의된 것만 접근 가능 (재정의된 메소드)
  -	익명 객체의 필드와 메소드를 사용하려면 재정의된 메소드 내에서 사용





#### 2. 익명 구현 객체 생성

-	인터페이스 타입으로 필드나 변수를 선언하고 구현 객체를 초기값으로 대입
-	구현 클래스가 재사용되지 않고, 해당 필드와 변수의 초기값으로 사용하는 경우에는 익명 구현 객체를 초기값으로 대입하는 것이 좋음



#### 익명 구현 객체 생성 방법

-	new 연산자를 이용해서 구현 객체를 생성한 후, 필드나 로컬 변수에 대입

<img width="400" alt="image-20220628211302212" src="https://user-images.githubusercontent.com/101630615/176176366-aec84c9d-5a64-4d2a-a845-9f63ded6e2bd.png">


-	중괄호 { } 

  -	인터페이스를 구현해서 클래스 생성
  -	인터페이스에 선언된 모든 추상 메소드의 실체 메소드 작성
  -	추가적으로 필드와 메소드 선언 가능하지만, 메소드 내에서만 사용 가능하고 외부에서 사용 불가




(1)	필드 선언 시 초기값으로 익명 구현 객체 생성해서 대입

<img width="500" alt="image-20220628211321369" src="https://user-images.githubusercontent.com/101630615/176176368-2d1505c7-e3b0-499a-b632-d85280ad40c5.png">



(2)	메소드 내에서 로컬 변수 선언할 때 초기값으로 익명 구현 객체 대입해서 생성

<img width="500" alt="image-20220628211328450" src="https://user-images.githubusercontent.com/101630615/176176369-fd1d16ec-a211-4538-a53a-9fcb55c3251e.png">



(3)	메소드의 매개변수가 인터페이스 타입일 경우, 메소드 호출 코드에서 익명 구현 객체를 생성해서 매개값으로 대입

<img width="500" alt="image-20220628211335444" src="https://user-images.githubusercontent.com/101630615/176176373-7512c420-3bf6-48e2-af13-ca02cd9acff4.png">