# Java 기초 개념
> Java는 1990년 **제임스 고슬링**에 의해 개발된 **객체지향 프로그래밍 언어(Object-Oriented Programming language)**이다. 인터넷 환경(웹)에 가장 많이 사용되고 있다.

## Java의 장점
* 이식이 용이함(portable)
* 분산환경을 지원함(distributed environment)
* 실시간(real time)
* 안정성 있음(reliable)

## Java 주요 문법

### 1. 변수 (variable)

#### 1-1. 값에 의한 구분
1. 상수 (constant)
프로그램 실행에 관계없이 변하지 않는 값, 리터럴(literal)이라고도 한다.
보통 static으로 선언하여 클래스 내에서 공용으로 사용한다.
2. 변수 (variable)
  변하는 값
  * 참조 변수 (reference variable): **객체**가 저장되어있는 메모리의 주소를 저장하고 있는 변수
    * 유사 개념 : C언어의 포인터 변수(pointer variable)

#### 1-2. 변수의 자료형 (data type)
Java에서 모든 변수는 반드시 타입이 선언 되어야 한다.

1. 기본 타입(시스템 정의 타입) (primitive type)
기본 타입의 변수는 그 변수가 가리키는 메모리 주소에 **값(value)을 직접 저장**한다.
   1. 정수형 : byte(1 byte), short(2 byte), int(4 byte), long(8 byte)
   2. 실수형 : float(4 byte), double(8 byte)
   3. 문자형 : char(2 byte)
   4. 논리형 : boolean(1 byte)

2. 객체(object)
   기본 타입을 제외한 모든 것
   1. 사용자 정의 타입 (user-defined type)
   
     * 기본 타입을 이용해서 class라는 새로운 사용자 정의 타입을 정의하여 사용할 수 있다.
     * 사용자 정의 타입은 그 변수가 가리키는 메모리 주소에 값이 아니라 **객체가 저장되어있는 메모리의 주소를 저장**한다.
     * 사용자 정의 타입으로 선언된 변수를 참조 변수라고 하고, 사용자 정의타입을 참조 타입(reference type)이라고도 한다. 
   
   2. String
   
       * 결합 연산자(+)를 제외하고는 모든 String을 객체로 취급해야한다.
       * String 자체는 변경되지 않는다.
         * String 객체들의 내용이 동일한 지 검사하려면 == 연산자가 아니라 equals() 메소드를 사용해야한다.
   3. array
      * 배열은 **같은 타입의 원소를 집단적으로 저장**할 수 있는 기본적인 데이터 구조이다.
        * 자료구조 카테고리에서 상세히 다룬다.
   4. file stream

### 2. 제어문 (control statement)
프로그램(명령문)의 실행 순서를 제어하기 위해 사용하는 명령문이다. 제어문에는 조건문과 반복문이 있다.

1. 조건문 (conditional statement)
   조건문은 조건식의 결과에 따라 명령문을 선택적으로 실행하게 한다.
   1. if 문
   2. switch 문
   3. 삼항연산자 : 조건식? true일 때의 수행문 : false일 때의 수행문
      * 표현 방법이 다를 뿐 if 문이랑 같다.
1. 반복문 (repeat statement)
    1. for문
    2. while문 : 조건식을 먼저 검사한 뒤 명령문을 실행, 한 번도 실행되지 않을 수 있다.
    3. do-while문 : 먼저 명령문을 실행한 후 조건식을 검사, 최소 한 번은 실행된다.

### 3. 클래스 (class)
클래스는 크게 데이터의 특성을 나타내는 **데이터 필드(field)** 와 데이터의 기능을 표현하는 **메소드(method)**로 구성된다.
클래스는 일종의 설계도로, 클래스를 통해 동일한 형태의 여러 객체(object)를 생성할 수 있다. 
클래스로부터 하나의 객체를 생성하는 것을 인스턴스화(instantiation)이라고 하고, 그 객체를 **인스턴스(instance)**라고 한다.
객체를 생성할 때는 new 연산자를 이용한다.

* 객체 지향 개념 핵심
객체 지향 개념을 적용하는 주요 목적 중 하나는 **기존 소프트웨어의 재사용(reuse)**에 있다. 검증된 소프트웨어의 재사용은 프로그래밍 시간을 절약하고, 오류를 감소시켜 보다 신뢰성 높은 소프트웨어를 생산할 수 있게한다.
1. **캡슐화 (encapsulation)** : 외부와의 인터페이스를 위한 부분만 공개하고 나머지는 숨긴다. 
   이를 **정보은닉(information hiding)**이라고 하며 캡슐화의 핵심이다. 
   * 복잡한 내부 구조를 외부에 숨김으로써 객체를 간단하게 표현하게 할 수 있다. 
   * 사용자의 메소드 사용을 쉽도록 하게 한다. 
   * 사용자에 영향을 주지않고 필요에 따라 필드나 메소드의 구현을 자유롭게 변경할 수 있다.
2. **상속(inheritance)** : is-a 관계, 하위 클래스가 상위 클래스의 모든 필드와 메소드를 마치 자기 것인 양 사용할 수 있는 것. 하위 클래스는 상위 클래스를 확장시킨 것과 같다. extends 키워드를 사용한다.
   * 기본 클래스 (base class) : 클래스 확장의 기본이 되는 클래스 = 슈퍼 클래스 (super class)
   * 파생 클래스 (derived class) : 확장된 클래스 = 서브 클래스 (sub class)
   * 메소드 오버라이딩(overriding) : 서브 클래스가 슈퍼 클래스로부터 상속받은 메소드를 재정의하여 사용하는 것
   * 클래스 게층(class hierarchy) : 클래스들 간의 상속 관계를 나타낸다. 클래스 상속 다이어그램(class inheritance diagram)이라고도 한다.
3. **다형성 (polymorphism)** : 실행시켜야할 메소드는 실행시간에 가서야 정확히 결정할 수 있다. 동적바인딩(dynamic binding), 슈퍼 클래스 객체를 참조하도록 선언된 참조 변수는 그의 서브 클래스 객체도 참조할 수 있다.(역은 성립X)

### 4. 메소드 (method)
메소드는 메소드 header와 body로 구성된다.
* 메소드 header : **반환 타입**, 메소드 이름, 매개변수 리스트
* 메소드 body : 메소드의 구현부

* 메소드 signature : 메소드의 매개변수의 수, 매개변수의 타입
  * 메소드 overloading : 한 클래스 내에 메소드 시그니처만 다르면 동일한 이름의 메소드가 여러 개 존재할 수 있다.

메소드의 매개변수 전달 시 기본 타입은 **값 호출(call-by-value) 방식**으로 전달되고, 
배열 또는 참조 타입은 **참조 호출(call-by-reference) 방식**으로 전달된다.

* 값 호출 (call by value) : 인자(argument)는 그 값(value)을 매개변수에 지정하는 방법으로 전달한다.
* 참조 호출 (call by reference) : 객체의 참조(주소)를 매개변수에 지정하게 되서, 매개변수와 인자가 모두 동일한 객체를 참조하게 된다.

#### 4.1 메소드의 종류
1. 생성자 (constructor)
   * 자바에서 객체를 생성하고 초기화를 담당하는 메소드
   * 한 클래스에 여러 개의 생성자를 가질 수 있다
   * 생성자는 반환 타입이 없고 클래스의 이름과 동일해야한다.
   * 생성자가 하나도 선언되지않은 경우에는 컴파일러가 default 생성자(무인자 생성자 non-arg constructor)를 자동으로 생성해준다. 
     * 무인자 생성자의 경우, 기본 타입은 0으로 초기화, 참조 타입은 null로 초기화된다. 

클래스의 데이터 필드는 일반적으로 private으로 선언하여 클래스 외부에서 직접 접근할 수 없도록 하는 것이 원칙이다. 이 때문에 필요한 메소드가 수정자 메소드와 접근자 메소드이다.
2. 수정자 (mutator) : setter 메소드, 객체의 필드 값을 검색만 할 수 있는 메소드
3. 접근자 (accessor) : getter 메소드, 객체의 필드 값을 변경할 수 있는 메소드
4. toString : 원하는 형식으로 객체를 출력할 수 있게 해줌
5. equals : 객체 비교 메소드, 두 개의 참조 변수가 참조하는 객체의 내용이 동일한 지 검사하는 메소드
6. 정적 메소드 (static method) : 객체를 생성하지 않고도 사용할 수 있는 메소드
7. 추상 메소드 (abstract method) : 구현은 없이 선언만 해놓은 메소드, abstract 키워드를 사용한다.
   * 추상 메소드를 포함하고 있는 클래스를 추상 클래스(abstract class)라고 한다.

### 5. 인터페이스 (interface)
구현없이 선언만 해놓은 메소드들의 집합을 인터페이스라고 한다. interface라는 키워드를 사용한다. 인터페이스의 메소드들은 모두 추상 메소드이기때문에, 인터페이스로는 객체를 생성할 수 없다.