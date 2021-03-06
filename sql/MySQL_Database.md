# [MySQL] 데이터베이스 

  

### 데이터와 정보

\-   데이터 (Data)

\-   관찰이나 측정을 통해서 수집된 사실(facts)이나 값(value)

\-   정량적 또는 정성적인 실제 값

\-   정보 (Information)

\-   의사결정에 도움이 되도록 데이터를 의미 있는 패턴으로 정리한 것

\-   데이터에 의미를 부여한 것

 

### 데이터의 구조

\-   논리적 구조 (logical organization)

\-   사용자의 관점에서 본 데이터의 개념적 구조

\-   데이터의 논리적 배치

\-   논리적 레코드

\-   물리적 구조 (physical organization)

\-   저장 관점에서 본 데이터의 물리적 배치

\-   저장장치에 저장된 데이터의 실제 구조

\-   물리적 레코드

![clip_image002](https://user-images.githubusercontent.com/101630615/173398733-e8413401-1ef3-44c9-ad19-5f85f73fdd55.jpg)

### 데이터베이스

\-   데이터의 집합체

\-   조직에 필요한 정보를 얻기 위해

\-   논리적으로 연관된 데이터를 모아서

\-   구조적으로 통합해 놓은 것

\-   여러 사용자나 응용프로그램이 공유

\-   동시 접근 가능

 

#### 데이터베이스 관리 시스템 (DBMS)

\-   데이터베이스를 관리해주는 소프트웨어 시스템

\-   Oracle, MS SQL Server, MySQL, …..

 

#### 데이터베이스 시스템

\-   통합된 데이터를 관리, 처리 및 사용자에게 서비스하기 위한 전체 시스템

\-   데이터베이스 (DB)

\-   데이터베이스 관리 시스템 (DBMS)

\-   데이터 언어 (Data Language)

\-   사용자 (User)

\-   데이터베이스 관리자 (DBA)

\-   데이터베이스 컴퓨터 (Database Computer)

\-   시스템

 

### 데이터베이스 시스템의 구조

![clip_image004](https://user-images.githubusercontent.com/101630615/173398749-15c871c4-0e46-4149-805c-af633f84dd17.jpg)

### 데이터베이스 / DBMS 특징

\-   데이터 공유

\-   필요한 자료를 한 번만 데이터베이스에 저장하고

\-   모든 응용프로그램(사용자)가 공유

\-   데이터 중복 방지, 최신 데이터 유지, 일관성 보장

\-   이전의 File System에서는 여러 응용프로그램에서 데이터를 중복하여 저장/관리 - 많은 문제 발생

![clip_image006](https://user-images.githubusercontent.com/101630615/173398751-78864504-e2dd-469f-8cf4-3a0ee976f682.jpg)

\-   데이터 중복의 최소화

\-   동일한 데이터가 여러 개 중복되어 저장되는 것 방지

\-   데이터의 독립성

\-   데이터베이스 크기 변경하거나 데이터 파일의 저장소 변경 시 기존에 작성된 응용 프로그램에는 영향을 미치지 않도록 데이터의 독립성 보장

\-   프로그램과 데이터 분리

\-   데이터의 안정성 향상

\-   대부분의 DBMS가 제공하는 백업-복원 기능 이용

\-   데이터가 손상되는 문제가 발생할 경우 원상으로 복원, 복구하는 방법이 명확해짐

 

#### 데이터의 무결성 (Integrity)

\-   데이터베이스 안의 데이터는 오류가 없어야 하고

\-   데이터베이스에 저장된 데이터 값과 표현하는 현실 세계의 실제값이 일치해야 함

\-   데이터가 상호간에 모순성이 없고, 현실 세계에 모순되지 않도록 데이터 유지

\-   동일한 데이터가 두 곳에 저장되어 있는 경우, 어느 한 곳의 데이터만 갱신되고, 다른 곳의 데이터는 갱신되지 않는 경우, 두 데이터 간의 불일치로 데이터의 무결성이 보장되지 않음

\-   데이터베이스 시스템에서는 이러한 오류를 방지하기 위해 외래키를 사용하여 데이터간(테이블 간) 모순성 배제

![clip_image008](https://user-images.githubusercontent.com/101630615/173398755-8e3d8da0-c7f6-4513-9e6d-119bc9d95b60.jpg)

\-   무결성 제약 조건

\-   무결성을 보장하기 위해 정확하지 않은 데이터가 데이터베이스 내에 저장되는 것을 방지하기 위한 제약 조건

\-   보안

\-   데이터베이스의 테이블에 따라 접근 권한 다르게 하여 데이터베이스의 비밀 유지와 조작 방지

![clip_image010](https://user-images.githubusercontent.com/101630615/173398759-c6c73a53-e12e-45ea-8db3-35be3db9f381.jpg)

\-   데이터 추상화

\-   데이터베이스에서는 사용자에게 저장구조의 복잡성을 숨기고

\-   테이블 개념만으로 DB를 생성/관리할 수 있도록 지원

![clip_image012](https://user-images.githubusercontent.com/101630615/173398761-980994e0-57ce-4224-9217-a65633c01265.jpg)

\-   다양한 뷰 제공

\-   다양한 형태(뷰)로 사용자에게 필요한 DBMS 데이터 세트 제공

\-   수천 가지의 뷰 정의 가능

\-   사용자 편의성 제고

\-   보안 및 권한 관리

![clip_image014](https://user-images.githubusercontent.com/101630615/173398765-4f62f04a-c419-4746-ae83-8f17677d8a8d.jpg)

### 데이터베이스 관리 시스템의 기능

![clip_image016](https://user-images.githubusercontent.com/101630615/173398767-96d13946-25c1-4f5c-86d4-0e0b71a13d01.jpg)

### 데이터베이스 언어

> 데이터베이스를 구축하고 이용하기 위한 데이터베이스 관리시스템과의 통신 수단

 

### 데이터 정의어 (DDL : Data Definition Language)

\-   데이터베이스 구조 정의를 위한 언어

\-   데이터베이스 구조, 데이터 형식, 접근 방식 등 데이터베이스 구축 및 변경

\-   데이터베이스의 논리적, 물리적 구조 정의 및 변경

\-   스키마(Schema)에 사용되는 제약 조건 정의

\-   스키마 : 데이터베이스의 전체 구조 명시

\-   데이터의 물리적 순서 규정

\-   CREATE / ALTER / DROP



### 데이터 조작어 (DML : Data Manipulation Language)

\-   데이터 처리를 위해 응용프로그램과 데이터베이스 관리 시스템 간의 인터페이스를 위한 언어

\-   데이터 처리 연산 기능

\-   검색, 삽입, 삭제, 갱신, 연산 등

\-   INSERT / DELETE / UPDATE / SELECT

\-   CRUD(Create / Read / Update / Delete)

 

### 데이터 제어어 (DCL : Data Control Language)

\-   보안 및 권한 제어, 데이터 무결성, 복구, 병행 제어 등을 위한 언어

\-   데이터 보안 : 권한이 없는 접근으로 부터 보호

\-   데이터 무결성 : 데이터의 정확성, 안전성 보장

\-   데이터 복구(회복) : 시스템 오류 등으로 부터 회복

\-   병행 제어 : 다수 사용자가 공유

\-   GRANT / REVOKE / COMMIT / ROLLBACK



##### 데이터베이스의 발전

오프라인 관리

\-   종이에 연필로 기록해 장부로 관리

파일 시스템 사용

\-   컴퓨터 파일에 기록/저장 - 메모장, 엑셀 활용

\-   컴퓨터에 저장된 파일의 내용은 읽고, 쓰기가 편한 약속된 형태의 구조 사용

\-   데이터 중복으로 인한 불일치 문제

##### 데이터베이스 관리시스템 (DBMS)

\-   파일시스템의 단점 보완

\-   대량의 데이터를 보다 효율적으로 관리하고 운영

\-   중복 제거



### DBMS 종류

#### 계층형 DBMS

\-   처음으로 나온 DBMS 개념 - 1960년대에 시작

\-   레코드들을 계층구조로 표현한 데이터 모델 사용

\-   검색 빠르지만, 구조 변경 어렵고, 데이터 중복 문제 발생

![clip_image018](https://user-images.githubusercontent.com/101630615/173398768-71c29ed4-cf19-4eb7-9002-6b2563d4e217.jpg)

 

#### 네트워크형 DBMS

\-   레코드 타입과 링크(Pointer들의 집합)로 구성

\-   복잡한 내부 포인터 사용

\-   프로그래머가 이 모든 구조를 이해해야만 프로그램의 작성 가능

![clip_image020](https://user-images.githubusercontent.com/101630615/173398771-7bc98dc6-0823-4236-8b06-6a0f3cee3030.jpg)

 

#### 관계형 DBMS

\-   논리적 구조가 2차원 Table 형태

\-   Oracle, DB2, Informix, Sybase, MS SQL Server, MySQL

\-   속성값 사용

![clip_image022](https://user-images.githubusercontent.com/101630615/173398772-0e0572ee-d92a-47ab-b851-c7a6cb7a19e0.jpg)

# 관계형 데이터베이스 

### 관계형 데이터 모델

\-   데이터를 2차원 테이블 형태인 릴레이션 구조로 표현하는 논리적 데이터 모델

 

#### 릴레이션

\-   관계형 데이터 구조

\-   데이터를 원자값(Atomic Value)으로 갖는 2차원 테이블로 표현

\-   논리적 구조이므로 다양한 정렬 기준을 통하여 릴레이션 표현 가능

 

>  릴레이션(테이블) 스키마 - 구조

\-   릴레이션에 데이터를 넣을 수 있도록 하는 릴레이션 틀

\-   릴레이션 이름, 속성 이름, 속성값의 도메인 정의

\-   릴레이션 : 테이블

\-   속성 : 필드, 열, 칼럼

\-   튜플 : 행 (레코드, 로우)

![clip_image024](https://user-images.githubusercontent.com/101630615/173398775-825a7ea6-577f-4382-b3d3-f1387f0e5a36.jpg)

> 속성(Attribute) : 필드, 열, 칼럼

\-   데이터베이스를 구성하는 가장 작은 논리적 단위

\-   개체의 특성, 상태 등 기술

\-   파일 구조의 데이터 필드에 해당

\-   속성 : 학번, 이름, 학과, 학년, ….

 

> 도메인 (Domain)

\-   릴레이션에서 하나의 속성이 취할 수 있는 같은 타입의 원자값들의 집합

\-   예 : [학년] 속성의 경우 도메인은 1~4 또는 1~5

\-   실제 속성값이 나타날 때 속성값의 적법 여부를 검사하는데 이용

\-   예 : [성별] 속성의 경우 도메인 ‘남자’, ‘여자’

릴레이션 스키마 표현

\-   릴레이션 이름(속성1, 속성2, 속성3, ..)

\-   예 : 학생 (학번, 이름, 학과, 학년)

릴레이션 인스턴스

\-   어느 시점의 릴레이션에 들어 있는 튜플(행)들의 집합

\-   동적 성질 (삽입, 삭제, 갱신으로 시간에 따라 변함)

튜플(Tuple) 

\-   릴레이션의 행 (Row) : 데이터 행

\-   릴레이션 내의 모든 튜플(행)은 서로 중복되어서는 안 됨

 

#### 릴레이션(테이블)의 특징

속성(열)은 단일 값을 가진다

\-   각 속성의 값은 도메인에 정의된 값만을 가지며 그 값은 모두 단일 값이어야 한다

\-   한 속성은 2개 이상의 값을 가질 수 없다

![clip_image026](https://user-images.githubusercontent.com/101630615/173399574-039ff60d-49c1-4830-bb33-beef114fb2b7.jpg)

속성은 서로 다른 이름을 가진다

\-   속성은 한 릴레이션에서 서로 다른 이름을 가져야만 한다

\-   동일한 이름의 속성명이 존재해서는 안 된다

![clip_image028](https://user-images.githubusercontent.com/101630615/173398777-6e2fb657-91cb-4deb-a913-cf56fa179ddc.jpg)

한 속성의 값은 모두 같은 도메인 값을 가진다

\-   한 속성에 속한 열은 모두 그 속성에서 정의한 도메인 값만 가질 수 있다

![clip_image030](https://user-images.githubusercontent.com/101630615/173398781-fb47e6f4-e89d-44a3-9b05-99f9bd2e248f.jpg)

속성의 순서는 상관없다

\-   속성의 순서가 달라도 릴레이션 스키마는 같다

\-   열의 순서를 변경하더라도 이 관계의 내용은 전혀 변하지 않는다

![clip_image032](https://user-images.githubusercontent.com/101630615/173398783-aced63be-b0b2-4d49-965f-cff06fd28ccf.jpg)

릴레이션 내의 중복된 튜플은 허용하지 않는다

\-   하나의 릴레이션 인스턴스 내에서는 서로 중복된 값을 가질 수 없다

\-   모든 튜플은 서로 값이 달라야 한다

\-   각 튜플(행)을 서로 다르게 구별 짓는 속성 - 기본키

![clip_image034](https://user-images.githubusercontent.com/101630615/173398784-9489a08f-c180-4a79-a21a-bc14dc17a3f0.jpg)

튜플의 순서는 상관없다

\-   행의 순서가 달라도 같은 릴레이션이다

\-   관계 데이터 모델의 행은 실제적인 값을 가지고 있으며

\-   이 값은 시간이 지남에 따라 데이터의 삭제, 수정, 삽입에 따라 순서가 바뀔 수 있다

![clip_image036](https://user-images.githubusercontent.com/101630615/173398786-c0fddbc9-8c95-4323-ae1f-0b39e2359373.jpg)

 

### 관계 데이터 제약

>  제약 (Constraints)

\-   데이터베이스에 저장되는 데이터에 대한 규칙

\-   데이터베이스의 기본 구조를 유지하고

\-   현실세계에서 데이터가 갖는 의미를 보다 정확하게 표현하고

\-   데이터의 오류를 방지하기 위한 중요한 수단

> 관계 데이터 제약

\-   키

\-   무결성 제약 조건

> 키(Key)

\-   릴레이션을 구성하는 각 튜플(행)을 속성(열)값에 의해 유일하게 식별할 수 있게 해주는 속성 또는 속성의 집합

\-   릴레이션은 중복된 튜플을 허용하지 않기 때문에 각 튜플에 포함된 속성들 중 어느 하나(혹은 하나 이상)는 값이 달라야 한다

![clip_image038](https://user-images.githubusercontent.com/101630615/173398790-4ff09d50-359e-41a3-ab80-1b0729e65ba8.jpg)

####  

### 기본키 (주 키, Primary Key, PK)

\-   한 테이블에서 모든 행을 유일하게 구별할 수 있는 열(속성)

\-   NULL 값은 허용하지 않음

\-   키 값의 변동이 일어나지 않아야 함

\-   예1 : 학생 (학번, 성명, 학과, 학년)

\-   기본키 : 학번

\-   예2 : 대한민국 국민 (주민번호, 성명, ….)

\-   기본키 : 주민번호

\-   예3 : 상품 (상품번호, 상품명, 가격, 제조사,...)

\-   기본키 : 상품번호

 

### 외래키 (Foreign Key, FK)

\-   다른 테이블의 기본키를 참조하는 속성

\-   테이블 간의 관계(relationship) 표현 사용

\-   참조하고(외래키) 참조되는(기본키) 양쪽 릴레이션의 도메인은 서로 동일

\-   참조되는(기본키) 값이 변경되면 참조하는 (외래키) 값도 변경

\-   NULL 값과 중복값 허용

![clip_image040](https://user-images.githubusercontent.com/101630615/173398793-2790adae-5499-46a9-b69e-69b2aa57ae67.jpg)

 

#### 복합키

\-   여러 개의 속성을 묶어서 기본키로 사용하는 키

![clip_image042](https://user-images.githubusercontent.com/101630615/173398794-b1729c88-0c61-4376-a589-f8610a6846b3.jpg)

 

![clip_image044](https://user-images.githubusercontent.com/101630615/173398797-58881d9e-8d07-4efd-8fe6-fa526625f9b6.jpg)