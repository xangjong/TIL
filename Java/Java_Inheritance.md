# [Java] 상속



### 클래스 상속 (Inheritance)

-	객체 지향 프로그램
  -	한 클래스에서 정의된 멤버 필드와 메소드를 다른 클래스가 물려 받는 것
  -	자식이 부모를 선택해서 물려받음
  -	상속 대상 : 부모 클래스의 필드와 메소드

#### 상속 개념의 활용

-	상속의 효과
  -	부모 클래스를 재사용해서 자식 클래스를 빨리 개발 개방
  -	클래스 사이의 멤버 중복 선언 불필요
  -	클래스 간 계층적 분류 및 관리 (효율성)
  -	유지 보수 편리성 제공
  -	경제적, 효율적

-	상속 대상 제한
  -	부모 클래스의 private 접근 갖는 필드와 메소드 제외
  -	부모 클래스가 다른 패키지에 있을 경우 default 접근 갖는 필드와 메소드 제외


##### 상속하는 클래스 

-	슈퍼 클래스, 기반 클래스, 부모 클래스
상속받는 클래스
-	서브 클래스, 파생 클래스, 자식 클래스

<img width="452" alt="image-20220619022814458" src="https://user-images.githubusercontent.com/101630615/174451819-d4321a5c-56b5-4240-892e-28bc10af9586.png">



#### 자바 상속의 특징

-	다중 상속을 지원하지 않는다
-	**extends 다음에는 오직 한 개의 클래스만 사용한다**
-	상속 횟수 제한 없음
-	계층구조의 최상위에 있는 클래스는 ``java.lang.Object`` 클래스
-	따라서 모든 클래스는 Object 클래스로부터 상속 받는 것 (Object 상속을 표현하지 않더라도 자동으로 상속 받게 됨)



### 상속에서의 생성자

#### 생성자

-	객체(인스턴스) 초기화 목적
-	부모 클래스의 생성자 : 부모 클래스의 멤버 초기화
-	자식 클래스의 생성자 : 자식 클래스의 멤버 초기화
-	자식 클래스의 객체(인스턴스)가 생성될 때
  -	부모 클래스의 멤버를 상속받기 때문
  -	부모 클래스의 생성자와 자식 클래스의 생성자 모두 실행된다
  -	(자식 클래스의 객체가 생성될 때 자식 클래스의 생성자가 자동 호출되면서 부모 클래스의 생성자도 자동 호출됨) 


#### 생성자 실행 순서

-	(1) 부모 클래스의 생성자 먼저 실행된 후
-	(2) 자식 클래스의 생성자가 실행된다 

<img width="550" alt="image-20220619023010583" src="https://user-images.githubusercontent.com/101630615/174451821-27a3c2d5-00be-4eb3-8d57-0430ba14e5a4.png">

#### 자식 클래스와 부모 클래스의 생성자 짝 맞추기

-	부모 클래스와 자식 클래스에 여러 개의 생성자가 있을 수 있는데,
-	클래스에 아무 생성자도 정의되지 않은 경우
  -	컴파일러에 의해 자동으로 기본 생성자 호출
-	생성자에 매개변수가 있는 경우
  -	짝을 이루는 생성자 호출
  -	짝을 이루는 생성자가 없으면 오류 발생

-	자식 클래스와 부모 클래스의 생성자를 짝을 맞추어 선택하기 위해 super() 메소드를 사용하여 명시적인 방법으로 해당되는 생성자를 호출
-	``super()`` : 부모 클래스의 생성자 호출

<img width="600" alt="image-20220619023122763" src="https://user-images.githubusercontent.com/101630615/174451823-66d4b11b-80ee-4a82-bfdd-69c3e78df3c4.png">





### super 레퍼런스 / super() 메소드
#### this

-	this 레퍼런스
  -	클래스 내에서 객체 자신을 가리키는 레퍼런스

-	``this()`` 메소드
  -	한 생성자에서 다른 생성자 호출하는 메소드
  -	주의 : 생성자 안에서 맨 첫줄에 와야 함


#### super

-	super 레퍼런스
  -	슈퍼 클래스(부모 클래스)를 가리키는 레퍼런스
-	``super()`` 메소드
  -	슈퍼 클래스의 생성자를 호출하는 메소드
  -	주의 : 생성자 안에서 맨 첫줄에 와야 함



### 메소드 재정의 (Overriding - 오버라이딩)

-	부모 클래스에서 상속받은 메소드를 그대로 사용하는 것이 아니라 자식 클래스에서 재정의해서 사용하는 것
-	상속 관계에서만 발생
-	메소드에만 적용 (필드(변수)에는 적용되지 않음)
-	부모 클래스의 메소드 무시

### Overriding(오버라이딩) 조건

-	부모 클래스에 선언된 메소드와 이름, 반환형, 매개변수 리스트가 완전 동일해야 함
-	부모 클래스 메소드의 접근 지정자보다 접근 범위가 좁아서는 안됨
-	public > protected > default > private

#### ``@Override`` 어노테이션

-	컴파일러에게 부모 클래스의 메소드 선언부와 동일한지 검사 지시
-	정확한 메소드 재정의를 위해 붙여주면 됨

#### 메소드 재정의 효과

-	부모 메소드를 숨기는 효과 발생
-	재정의된 자식 메소드 실행



#### 부모 메소드 사용

-	메소드 재정의된 부모 메소드 숨기는 효과
-	자식 클래스에서는 재정의된 메소드만 호출
-	자식 클래스에서 수정되기 전 부모 메소드 호출

<img width="550" alt="image-20220619032112925" src="https://user-images.githubusercontent.com/101630615/174451827-07fea9d6-7f0a-48ea-a423-11d1c29ce3dc.png">

```
super 레퍼런스 사용: super.method1();
```

#### 오버라딩 메소드 자동 입력

-	(1) Source 메뉴 : Override/Implements method
-	(2) Ctrl + 스페이스 눌러서 메소드 선택



#### ``@Override`` 어노테이션이 없을 경우

-	새로운 멤버 메소드인 줄 알고 오류 없음

그러나 @Override 어노테이션이 있는 경우

-	정확히 오버라이딩 된 것인지를 컴파일러가 체크하여 오류 발생
-	개발자의 실수를 줄일 수 있음 



<img width="600" alt="image-20220619032051764" src="https://user-images.githubusercontent.com/101630615/174451826-f7619077-8596-4009-8a0a-43be5e19477a.png">

