# 객체지향 프로그래밍

## 객체의 구분
* 일급객체

## 클래스

### 프로퍼티

### 메소드


### 속성




### 익명클래스



## 상속
* 계층


## 역할과 책임
* 책임(responsibility)

## 특징
* [캡슐화](./캡슐화)
* [은닉성]


## 인터페이스
* [투명성]
* 복수 인터페이스


## 인스팩터




# 14. 클래스
클래스는 기존 함수형 프로그램 코딩 개발 방법보다 향상된 객체지향형 프로그램 개발 방법론 및 환경을 지원합니다. PHP도 다양한 객체지향 방법론을 도입하여 최신 트렌드에 맞는 클래스 및 코딩 방법을 제공합니다. 

## 14.1 클래스와 객체

객체지향 방식의 프로그램 OOP는 Object-Oriented Programming의 약자입니다. 객체지향 프로그램 코딩 방식은 기존 함수형 절차적 프로그램 방식과 비교하여 소프트웨어의 유지보수 및 구조적으로 개발하는 데 있어 매우 유용합니다. 그런 점에서 최신 소스코드의 개발 방식은 클래스 기반의 코딩 스타일을 많이 적용합니다.

객체지향 프로그램은 단순한 코딩 문법 및 스타일이 아닙니다. 데이터의 처리와 기능, 각각의 요소를 하나의 객체로 처리합니다. 객체는 각각의 데이터와 기능들이 연관하여 프로그램이 동작, 구성됩니다. 


### 14.1.1 절차적 프로그램
절차적 프로그래밍 방식은 초기의 프로그램 개발 방법입니다. 단순하게 프로그램의 명령어를 모아 놓은 형태로 논리적 순서대로 쓰여진 프로그램을 코딩을 말합니다. 예전 초창기 컴퓨터 개발 방법이며, 간단한 기능과 테스트 결과를 빠르게 보기 위해서 자주 사용합니다.

만일 절차적 방식으로 작성된 대용량 프로그램은 소스의 내용을 쉽게 이해하기가 어렵습니다. 또한 복잡한 동작을 처리하기 위해서 상당량의 유지보수 시간이 필요합니다. 

### 14.1.2 구조적 프로그램
구조적 프로그램밍은 이전 절차적 프로그래밍의 문제점을 보완한 프로그램 개발 방법론 입니다. 좀 더 체계적이고 구조적으로 프로그램을 개발하기 위한 새로운 다양한 시도 중의 하나입니다.

나날이 프로그램은 복잡해지고 크기가 커지고 있습니다. 방대한 기능의 프로그램 동작 다수의 사람들이 팀원을 위하여 서로 이해하고 내용을 공유하는 것은 매우 어렵습니다. 또한 순서도를 통하여 쉽게 표현하기도 어려울 것입니다. 이러한 문제점들은 소프트웨어를 고도화하고 유지 보수하는 데 매우 어렵습니다. 
구조적 프로그램은 이러한 문제점을 보완하고자 1968년 에츠러르 다익스트라가 자신의 논문 <GOTO문의 해로움>(GO To statement considered Harmful)에서 프로그램을 함수(프로시저) 단위로 나눠서 프로시저 간에 연관과 호출을 통해 구조적 프로그램 방법을 제안한 것이 계기가 되었습니다.

하지만 기존의 함수 방식의 개발 방법은 데이터 처리 등을 구조화하여 처리하는 반면에, 실제적으로 데이터 자체까지는 구조적으로 해결을 하지 못했습니다. 또한 외부 변수들을 많이 쓰는 바람에 사용 가능한 변수 이름을 다 써버리는 등 프로그램의 크기가 커질수록 개발할 수 있는 환경은 포화되어 갔습니다.

함수형 프로그램의 다양한 문제점을 개선하기 위해서 등장한 것이 객체지향 프로그래밍입니다. 객체지향 프로그램은 작은 객체들을 만들어서 문제를 해결하고, 해결된 문제를 연결하여 더 큰 문제를 해결하는 상향식(bottom-up) 설계 방법을 도입하게 되었습니다. 또한 이렇게 생성된 객체들은 독립성과/ 신뢰성을 향상하여 객체를 수정 없이 재사용할 수 있어 개발과 유지보수를 대폭적으로 개선했습니다.


### 14.1.3 캡슐화
캡슐화는 객체지향 방법의 기본 개념입니다. 캡슐화의 목적은 ‘코드를 수없이 재사용’하는 것 입니다. 갭슐화는 프로그램 코드를 재사용하는 데 있어서 기능적인 부분과 데이터적인 부분을 한곳에 묶어서 관리할 필요성이 있습니다.

```
객체 = 변수 + 함수
```

객체와 함수의 차이점은 데이터를 같이 관리하는지 여부입니다. 보통 변수는 프로퍼티(property), 함수는 메서드(method)라고 합니다.

## 14.2 클래스 & 인스턴스
클래스는 계층적으로 분류한 기능과 특성의 모음이라 생각하시면 됩니다.  
클래스는 객체(object)와 실체화(instance)를 통하여 만들 수 있습니다.

PHP 에서는 클래스 선언을 다음과 같이 할 수 있습니다.

|문법|
```php
class jiny {
	클래스 내용 ...

	public $username;

	public function setName($name){
		$this->username = $name;
	}
}
```

`class`라는 키워드를 사용하고 다음에 클래스 이름을 사용자가 지정할 수 있습니다. 

클래스명은 영문 또는 언더바(_)로 시작합니다. 클래스의 내용은 중괄호 { } 안에 내용을 작성하면 됩니다.


## 14.2 접근 권한 속성

클래스와 같이 객체지향 프로그램에서 속성이라는 추가적인 접근 권한 개념이 도입됩니다. 접근 권한 속성은 각각의 클래스의 독립성과 보호를 위해서 프로퍼티(변수)나 메서드(함수) 등에 권한을 설정하는 것입니다.

PHP 클래스에서는 세 가지의 속성을 가지고 있습니다. public, protected, private를 제공합니다.
속성은 클래스 외부에서의 접근을 제한하고자 할 때 사용할 수 있습니다.

접근 속성의 종류
PHP 클래스에서는 프로퍼티 변수의 속성에 대해서 세 가지 타입을 지원합니다.

●	public:  public으로 설정된 프로퍼티 변수는 외부에서 접근이 가능합니다. 즉, 값을 읽거나 새로운 값으로 설정이 가능합니다.

●	protected: 정의한 클래스와 상속한 클래스에서만 사용이 가능합니다. 이 속성은 클래스 내의 메서드와 서브 클래스에서만 접근하여 사용할 수 있습니다. 외부에서 접근할 수는 없지만 상속을 받은 경우에는 접근이 가능합니다.

●	private: 정의한 클래스 내에서만 사용 가능합니다. 이 속성은 같은 클래스 내에서만 참조가 가능합니다. protectd와 달리 서브 클래스에서는 사용할 수 없습니다

## 14.3 클래스 선언

클래스를 사용하기 위해서는 함수 선언처럼 클래스를 미리 정의해야 합니다. 또한 PSR 코딩 스타일에 따르면 클래스는 기능별 개별 파일로 작성하는 것을 권장합니다. 또한 1개의 파일 안에 1개의 클래스 작성을 권장합니다.

클래스 이외에도 향후 설명할 인터페이스, 트레이트 등도 같은 방식의 코딩스타일 사용을 권장합니다.


### 14.3.1 class 키워드
클래스의 정의는 class 키워드를 통해 클래스를 선언할 수 있습니다. 클래스의 선언 방법은 class 키워드 다음에 클래스명을 작성을 합니다. 클래스명은 PSR-1 표준 코딩 스타일 방식을 따르면 클래스명은 낙타 표기법 (StudlyCaps) 스타일로 작성을 권장합니다.

예) StudyCaffe, JinyPhp

위의 예처럼 낙타 표기법(StudlyCaps) 방식은 첫 문자는 대문자로 표기하는 스타일입니다.

또한 클래스명은 PHP에서 예약된 키워드를 제외한 영문자로 시작되어야 합니다.

|문법|
```
class 클래스명
{
    // 프로퍼티 선언
    public $var = “default”';

    // 메서드 함수 선언
    public function 함수명()
    {
        메서드 함수 내용들...
    }
}
```

클래스 객체는 여러 개의 프로퍼티와 메서드를 포함하고 있습니니다.  클래스 객체의 프로퍼티와 메서드는 클래스 본체 중괄호 { } 안에 작성합니다.

PSR 에서 권고하는 코딩 스타일 방식을 따르면 중괄호 의 시작 위지는 클래스 선언 다음  줄에 위치합니다. 또한 class 키워드와 같은 탭 크기의 들여쓰기 위치에 자리를 잡습니다. 객체의 메서드와 프로퍼티는 중괄호 본체 안에서 들여쓰기로 작성합니다.

### 14.3.2 프로퍼티
프로퍼티는 클래스에서 변수를 부르는 또 다른 이름 중 하나입니다.  

클래스 안에 선언된 변수를 프로퍼티라고 부르는데, 이렇게 이름을 달리 부르는 것은 기존에 사용하는 변수와 클래스 안에 들어 있는 변수를 구분하기 위해서입니다.

|문법|
```
class 클래스명
{
    // 프로퍼티 선언
    private $aaa;
    public $bbb = "default";

    // _ 밑줄을 이용하여 구분할 수 있습니다.
    const DATE_APPROVED = '2017-05-17';

    // 메서드 함수 선언
    public function 함수명()
    {
        메서드 함수 내용들...
    }
}
```

프로퍼티를 작성하는 위치는 클래스 안과 메서드 함수 밖에 선언합니다. 다른 관점으로 생각해보면 클래스 객체 안에서는 바라보면 지역변수가 될 수도 있고, 메서드 밖에서는 바라보면 글로벌변수가 될 수도 있습니다.

PHP언어에서는 특성상 변수 사용과 동시에 자동으로 변수가 할당되어 생성됩니다. 이러한 점은 PHP에서 매우 편리한 기능입니다. 하지만 객체에 포함되는 프로퍼티 변수는 먼저 사용하기 전에 미리 변수를 프로퍼티로 선언해야 합니다.

프로퍼티 변수만 선언할 수 있습니다. 또는 = 대입 연산자를 통해 초기값도 같이 설정할 수 있습니다.

통상적으로 객체 안에 포함되는 프로퍼티 변수는 변수명 앞에 접근 권한 속성을 갖는 키워드를 같이 지정하여 사용합니다. 만일 접근 권한 속성을 생략하는 경우에는 명시적으로 public으로 설정한 것으로 간주합니다.

프로퍼티 변수명은 일관성 있게 사용을 권장합니다. PSR 권장 코딩 스타일로 특별히 낙타 표기법 (StudlyCaps, camelCase, under_score) 사용을 구분하지는 않습니다. 

객체 내에서 프로퍼티를 선언할 때는 PSR 권장 코딩 스타일 방식으로 중괄호 본체 안에서 들여쓰기 작성을 권고합니다.

### 14.3.3 메서드
메서드(Method)라는 이름은 객체 내에서 함수를 부르는 또 다른 이름 중 하나입니다.

클래스 안에서 작성된 함수를 메서드라고 부릅니다. 이렇게 이름을 달리 부르는 것은 기존에 사용하는 함수와 클래스 안에 있는 함수를 구분하기 위해서입니다.

클래스 안에서 메서드를 선언하는 것은 기존 함수를 선언하여 사용하는 것과 동일합니다. 단지 클래스 내부에 함수를 선언한다는 것이 차이점입니다.

|문법|
```
class ClassName
{
    public function 메서드_함수명1(매개변수)
    {
        // method body
    }

    private function 메서드_함수명2(
    	매개변수1,
    	매개변수2,
    	매개변수3
    ) {
        // method body
    }
}
```

메서드 또한 함수이기 때문에 function 키워드를 이용하여 작성합니다.

메서드 이름은 PSR 권장 표준 코딩 스타일을 따라서 낙타 표기법(camelCase) 스타일로 작성을 권고합니다. 또한 메서드 이름의 첫 시작 문자는 소문자 사용 할 것을 권장합니다.

```
예) camelCase (), loveStudy()
```

객체 내에서 메서드를 선언할 때는 PSR 권장 코딩 스타일 방식으로 중괄호 본체 안에서 들여쓰기 하여 작성할 것을 권고합니다.

객체의 메서드도 일반 함수처럼 매개변수 인자를 가질 수 있습니다. 함수와 같이 매개변수를 전달하는 소괄호를 사용하여 다수의 변수 값을 메서드로 전달할 수 있습니다. 다수의 변수를 전달할 때는 콤마로 구분하거나 여러 줄로 작성할 때는 PSR 코딩 스타일 방식으로 한 줄에 한 개의 매개변수 작성하는 것을 권고합니다.

객체의 메서드는 일반 함수와 달리 function 키워드 안에 접근 권한 속성을 갖는 키워드를 같이 지정하여 사용합니다. 프로퍼티 설정에서 접근 권한 속성을 부여하는 것과 같습니다.


### 14.3.4 클래스 상수
객체 클래스만의 상수를 선언할 수 있습니다. 객체 클래스 내에 상수를 선언하는 것은 프로그램 소스 전체에서 사용이 가능한 공용 상수가 아닙니다. 이 상수는 객체 클래스 안에서만 사용할 수 있는 상수 코드로 독립적인 효과가 있습니다.
  
아장에서 PHP 언어는 두 가지의 방식으로 상수를 설정할 수 있습니다. 하지만 이 두 가지 중에서 객체 클래스 안에서 상수 설정 가능한 방법은 const 명령만 사용 가능합니다. 즉, define() 함수는 사용하지 않습니다.

클래스 상수
```
class language {
	const ENGLISH = "en";
	const KOREAN = "ko";
}
```

객체 클래스 본문 중괄호 { } 안에 const를 사용하여 상수를 선언하면 됩니다. 상수를 선언하는 문법과 방식은 기존 PHP 상수 설정과 같지만 클래스 본문 안에 작성한다는 것이 차이점입니다.

클래스 안에 상수를 쓸 때는 PSR-2 코딩 스타일 방식으로 들여쓰기를 하여 작성합니다. PSR-1 코딩 스타일에 따라서 상수는 대문자로 작성합니다. 상수명이 길어질 때는 밑줄(_)을 통해 구분하여 상수명을 작성할 수도 있습니다.

클래스 상수를 사용할 때는 객체변수 뒤에 이중콜론(::) 기호로 사용할 수 있습니다.

|문법|
```
$객체변수::상수명
```

클래스 내부적으로 사용을 할 때는 다음과 같은 형태로 사용 가능합니다.

|문법|
```
self::상수명
예제 파일 class-01.php
예제 파일 class-01.php<?php
	class language {
		const ENGLISH = "en";
		const KOREAN = "ko";

		public function getEnglish()
		{
			return self::ENGLISH;
		}
	}

	$obj = new language();

	echo "클래스 상수 출력<br>";
	echo "KOREAN = " . $obj::KOREAN . "<br>";

	echo "메서드를 이용한 상수 출력<br>";
	echo "ENGLISH = " . $obj->getEnglish() . "<br>";
?>
```

결과
```
클래스 상수 출력
KOREAN = ko
메서드를 이용한 상수 출력
ENGLISH = en
```

위의 예제는 클래스 내부에 독립 상수를 설정하고, 이를 접근 출력하는 예입니다. language 클래스는 두 개의 상수를 가지고 있습니다. 첫 번째 출력에서는 직접 객체에 접근하여 사용했습니다. 두 번째 출력에서는 매서드를 이용하여 내부 접근을 한 후에 상수값을 출력합니다.


## 14.4 인스턴스 생성
인스턴스란 말은 앞에서 선언한 클래스를 통해 객체변수를 생성하는 것을 말합니다. 

함수는 함수의 정의 후에 바로 호출하여 사용할 수 있었습니다. 하지만 객체 클래스는 선언을 했다고 해서 바로 함수처럼 호출하여 사용할 수 있는 것은 아닙니다. 사용하기 전에 인스턴스화 작업을 통해 클래스 객체를 생성을 한 번 더 해줘야 합니다. 인스턴스화는 클래스 선언된 정보를 통해 객체변수를 생성해 합니다.

 


인스턴스화를 통하여 객체를 생성하면 클래스에 정의된 프로퍼티와 메서드를 함께 생성하여 새로운 객체를 생성 합니다. 정확히 말하면 객체를 생성하여 지정된 변수에 할당(대입)하는 것입니다. 객체변수를 통해 프로퍼티와 메서드에 접근하게 됩니다.



## 14.4.1 new 키워드
정의한 클래스를 객체 인스턴스 형태로 생성하는 방법은 매우 간단합니다. 단지 정의한 클래스명 앞에 new 키워드를 통해 변수에 대입하면 됩니다.

문법)
$인스턴스 변수 = new 클래스명;

new 키워드로 대입한 변수는 객체 데이터 타입으로 생성됩니다.

예제 파일 class-02.php
```
<?php
	class JinyClass
	{

		public function test($msg)
		{
			return $msg;
		}
	}

	$JinyClass = new JinyClass();
	echo "JinyClass 인스턴스<br>";
	echo $JinyClass->test("JinyClass") . "<br>";

	$obj1 = new JinyClass;
	$obj2 = new JinyClass;

	echo "클래스 인스턴스1<br>";
	echo $obj1->test(1) . "<br>";

	echo "클래스 인스턴스2<br>";
	echo $obj2->test(2) . "<br>";
?>
```

결과
```
JinyClass 인스턴스
JinyClass
클래스 인스턴스1
1
클래스 인스턴스2
2
```

위의 예제는 클래스 객체를 생성하는 예제입니다. 예제 소스를 살펴보면 아래와 같이 클래스를 인스턴스화하여 객체를 생성할 때 어떤 예는 변수명과 클래스명이 같은 경우를 종종 볼 수 있습니다. 

```
$JinyClass = new JinyClass();
```

인스턴스 객체변수로 클래스명과 같은 이름을 사용할 수도 있습니다. 하지만 변수명과 클래스 이름은 서로 다른 의미 입니다. 객체변수는 변수이고, 클래스명은 클래스 이름이라는 것입니다. 서로 같지 않습니다. 이름만 같을 뿐 서로 영향을 주지 않습니다. 이름이 같다고 해도 왼쪽은 객체변수이고 오른쪽은 그냥 클래스명입니다.

선언된 클래스는 new 키워드를 통해 객체를 생성하면 객체는 클래스의 선언된 타입과 같습니다.

```
$obj1 = new JinyClass;
$obj2 = new JinyClass;
```

위의 예처럼 한 개의 클래스를 통해 동일한 객체 내용을 가지고 있는 데이터 타입 변수 두 개를 생성할 수 있습니다. $obj1과 $obj2는 서로 다른 객체변수입니다. 하지만 동일한 클래스의 구조를 가지고 있습니다.
 
> 함수 VS 클래스
> 함수는 선언과 호출 2단계 작업을 한 쌍으로 사용합니다. 반면에 클래스는 선언과 인스턴스 생성, 호출 3단계의 작업을 한 쌍으로 사용합니다.


### 14.4.2 객체 복사
new 키워드는 새로운 객체를 생성합니다. new 키워드는 초기화된 객체를 생성합니다. 만일 클래스 값의 초기화 같은 것이 필요하다면 그냥 new 키워드를 이용하여 객체를 생성하면 됩니다.

하지만 지금 사용 중인 객체를 복제하여 사용하려고 하면 clone 키워드를 사용해야 합니다. 

|문법|
```
$obj2 = clone $obj;
```
 

clone 키워드는 현재의 객체의 상태를 포함하여 객체를 복사합니다.

예제 파일 class-03.php
```
<?php
	class JinyClass
	{
		public $message;

		public function showMessage(){
			return $this->message;
		}

	}

	$obj = new JinyClass;
	$obj->message = "testing clone";
	echo $obj->showMessage() . "<br>";

	$obj2 = clone $obj;
	echo $obj2->showMessage() . "<br>";

?>
```

결과
```
testing clone
testing clone
```

위의 예는 객체 복사에 대한 실험입니다. 첫 번째 객체 $obj는 처음에 생성된 객체변수입니다. 생성된 객체에 메시지 내용을 설정한 다음에 화면 출력합니다.

$obj2는 $obj를 복사한 객체입니다. 현재 $obj객체의 설정값을 포함하여 새로운 객체변수에 복제가 됩니다. 복제된 $obj2를 통해 메시지를 출력하면 복제하기 전의 $obj 의 프로퍼티 값이 출력되는 것을 볼 수 있습니다.

복제는 이전 객체에 어떠한 프로퍼티 값이 설정이 되어 있다면 이 설정값까지 모두 복제를 합니다.

## 14.5 객체 접근

객체변수는 클래스를 통하여 인스턴스화된 객체변수를 통하여 메서드나 프로퍼티를 접근 및 호출합니다.

생성된 객체변수의 메서드와 프로퍼티를 호출하기 위해서는 접근 연산자 ->를 사용합니다. -> 기호는 객체 안에 있는 메서드와 프로퍼티를 접근하여 값을 설정하거나 호출할 수 있습니다.

```
$객체변수->메서드;

$객체변수->프로퍼티;
```

기존 다른 언어에서는 클래스 객체의 메서드 접근을 점(.)을 사용하기도 합니다. PHP 언어의 경우에는 -> 기호를 사용하는 차이점이 있습니다.


### 14.5.1 프로퍼티 접근
프로퍼티에 값을 저장하거나 읽어오기 위해서는 객체 접근이 필요합니다. 접근 기호를 통해 객체변수의 프로퍼티에 접근할 수 있습니다. 앞에서 설명한 것처럼 아래와 같이 작성하면 됩니다.

|문법|
```
$객체변수->프로퍼티;
```

하지만 프로퍼티 이름 앞에 `$` 기호는 사용하지 않습니다.

```php
$jiny->username = "hojin lee";
$name = $jiny->username;
```

위의 예제는 프로퍼티에 접근하여 값을 읽어오거나 저장하는 간단한 표현입니다. 접근 기호 ->만 넣어서 사용하면 됩니다.

#### 간접 접근
위의 예와 접근 방식은 객체에 직접 프로퍼티를 접근하는 방법입니다. 또한 프로퍼티를 접근할 때 프로퍼티명 앞에 $를 쓰지 않았습니다. 

만일 $를 포함하여 작성하면 프로퍼티명을 변수 값을 이용하여 호출하겠다는 의미입니다. $ 변수를 통해 간접적으로 프로퍼티에 접근하게 되는 것입니다.

```php
$obj->$proertyName ;
```

간접 접근은 가변적으로 프로퍼티를 선택하여 호출할 때 이용할 수 있습니다. 접근하려고 하는 프로퍼티는 $propertyName의 값의 이름입니다.


예제 파일 class-04.php
```
<?php
	class JinyClass
	{
		public $age;
		public $name;
	}

	$obj = new JinyClass;
	
	// 프로퍼티에 값을 저장
	$obj->age = 18;

	// 프로퍼티의 값을 읽어옵니다.
	echo "나이는 ".$obj->age." 입니다.<br>";

	// 간접 프로퍼티 접근
	// aaa 변수에 프로퍼티명을 설정 후에 간접적으로 접근함
	$aaa = "name";
	$obj->$aaa = "jiny";

	// 프로퍼티의 값을 읽어옵니다.
	echo "내 이름은 ".$obj->$aaa." 입니다.<br>";

?>
```

결과
```
나이는 18입니다.
내 이름은 jiny입니다.
```

위의 예제는 프로퍼티 간접 접근에 대한 실험입니다. 예에서 첫 번째 나이 부분은 직접 프로퍼티명을 입력하여 값을 설정하거나 읽어서 출력했습니다.

하지만 두 번째 이름은 변수에 프로퍼티명을 설정한 후에 간접적으로 프로퍼티를 선택하여 설정, 출력을 했습니다.


### 14.5.2 메서드 접근
클래스의 함수인 메서드 접근은 프로퍼티 접근 방식과 유사합니다. 객체변수 뒤에 접근 연산자 ->를 통해 메서드를 호출할 수 있습니다.

|문법|
```
$객체변수->메서드();
```

예제 파일 class-05.php
```
<?php
	class JinyClass
	{
		public $message;

		public function setMessage($msg){
			$this->message = $msg;
		}

		public function showMessage(){
			return $this->message;
		}

	}

	$obj = new JinyClass;

	// 메서드를 호출합니다.
	$obj->setMessage("hello world!");

	// 메서드 호출 및 반환값
	$msg = $obj->showMessage();
	echo $msg . "<br>";

?>
```

결과
```
hello world!
```

위의 예처럼 메서드를 단독으로 호출할 수 있습니다. 또한 메서드의 반환값을 받아서 처리할 수도 있습니다.


### 14.5.3 $this
정의된 클래스의 메서드와 프로퍼티는 인스턴스화를 통하여 생성된 객체변수에 직접 접근했습니다. 이러한 인스턴스화를 통한 객체의 생성과 접근은 클래스 외부에서 메서드와 프로퍼티를 사용하는 대표적인 방법입니다.

하지만 클래스의 정의 내부에서 선언된 프로퍼티와 메서드에 접근하려면 어떻게 해야 할까요? 클래스가 객체지향적일 때 동일한 클래스 메서드에서 다른 메서드를 호출이 필요한 경우가 많이 발생할 것입니다.

이런 경우 클래스는 내부 접근을 위해서 특별한 인스턴스 변수 $this를 제공합니다. $this 객체변수는 자기 자신의 클래스를 가르키는 셀프 변수입니다.

예제 파일 class-06.php
```
<?php
	class JinyClass
	{
		public $message;

		public function show(){
			// 내부 메서드를 호출합니다.
			echo $this->getMessage();
		}

		public function getMessage(){
			return $this->message;
		}

	}

	$obj = new JinyClass;
	$obj->message = "안녕하세요";
	echo $obj->show() . "<br>";
?>
```

결과
```
안녕하세요
```

위의 예제를 보면 클래스 내부의 프로퍼티와 메서드는 $this를 통해 내부 접근이 가능합니다.
클래스 내의 show() 메서드는 getMessage() 메서드를 호출하고, getMessage() 메서드는 message 프로퍼티에 접근합니다.

특별한 $this 인스턴스 변수를 클래스 정의 내에서 사용하기 위해서는 반드시 클래스를 인스턴스화 형태로 객체를 생성해야 합니다. 예를 들면 $this를 사용하기 위해서 다음과 같이 클래스의 인스턴스화 작업을 해야만 합니다.

```
$obj = new JinyClass;
```

위처럼 $obj 객체변수가 생성되고 나서 내부에서 $this를 통해 내부 메서드와 프로퍼티를 접근할 수 있는 것입니다. 

만일 정적 방식으로 클래스를 사용할 때는 $this를 사용할 수 없습니다. 인스턴스를 생성하지 않기 때문 입니다.

즉, $obj 인스턴스를 생성하게 되면 $this는 $obj를 가리키게 됩니다. 인스턴스를 생성하지 않으면 객체 자체가 없기 때문에 $this 사용을 못하는 것입니다.  
 

### 14.5.4 매서드체인
메서드 체인이란 $this의 특성을 이용하여 클래스 메서드를 연결하여 사용하는 코딩 스타일을 말합니다.

PHP 클래스 응용 소스를 보면, 

```
$obj->setEnv()->loading();
```

위처럼 메서드 함수를 ->로 연결하여 사용하는 코드를 본적이 있을 것입니다.

이런 형태의 메서드 호출을 매서드 체인이라고 합니다. 메서드 체인은 PHP 4.x에서 PHP 5.x 버전으로 업그레이드되면서 지원하게 되었습니다.

메서드 체인의 원리는 각각의 메서드를 실행 후 $this 반환으로서 객체를 연결합니다.

$obj->setEnv()->loading();는 $obj->setEnv()를 실행하고 $this를 반환합니다. $this는 $obj를 가리키기 때문에 다시  

$obj->loading();처럼 실행할 수 있습니다. 

 

이러한 메서드 체인 방법은 보다 코드를 간결하게 만들고 프로그램을 개발하는 데 좀 더 직관적으로 유지보수가 쉬워지는 면도 있습니다. 

예제 파일 class-07.php
```
<?php
	class members
	{
		private $user_name;
		private $user_age;
		private $user_sex;

		// 이름을 설정합니다.
		public function setUserName($name)
		{
			$this->user_name = $name;

			// 자기 자신의 객체를 반환합니다.
			return $this;
		}

		// 나이를 설정합니다.
		public function setUserAge($age)
		{
			$this->user_age = $age;

			// 자기 자신의 객체를 반환합니다.
			return $this;
		}

		// 성별을 설정합니다.
		public function setUserSex($sex)
		{
			$this->user_sex = $sex;

			// 자기 자신의 객체를 반환합니다.
			return $this;
		}

		public function show()
		{
			printf("안녕하세요. 저는 %s입니다. 나이는 %d이고요 %s입니다.",$this->user_name, $this->user_age, $this->user_sex);
		}
	}

	// 클래스를 선언합니다.
	$objMembers = new members;
	$objMembers->setUserName("jiny")->setUserAge(18)->setUserSex("남자")->show();

?>
```

결과
```
안녕하세요. 저는 jiny입니다. 나이는 18이고요 남자입니다.
```

위의 예제를 보면 각각의 메서드는 $this 자기 자신의 객체를 반환합니다.

```
// 클래스를 선언합니다.
$objMembers = new members;
$objMembers->setUserName("jiny")->setUserAge(18)->setUserSex("남자")->show();
```

클래스를 선언하고 메서드 체인으로 각각의 메서드를 연결, 호출합니다. 기존 메서드 호출 방식으로 호출은 다음과 같습니다.

```
// 클래스를 선언합니다.
$objMembers = new members;

// 메서드 호출로 변수를 초기화합니다.
$objMembers->setUserName("jiny");
$objMembers->setUserAge("18");
$objMembers->setUserSex("남자");

$objMembers->show();
```

위의 전형적은 메서드 호출 사용법은 메서드를 직접 하나씩 호출하여 프로퍼티 변수들을 초기화합니다. 세 개의 프로퍼티를 초기화하기 위해서 소스상에서 세 줄을 할당하여 사용합니다.

메서드 체인 방식은 함수의 연속 호출과 반환되는 값을 이용하기 때문에 직관적이고 한 줄에 모든 명령을 실행할 수 있습니다.

메서드 체인도 $this의 속성을 이용하기 때문에 사용 전에 반드시 클래스의 인스턴스를 생성 후에 사용해야 합니다.

### 14.5.5 객체 순회
PHP 5.x 부터는 객체를 리스트처럼 순회하여 접근할 수 있습니다. 다음 예제는 객체의 프로퍼티를 foreach문을 사용하여 순회하여 접근합니다.

예제 파일 class-0814.php
```
<?php
  class MyClass
  {
    public $var1 = 'value 1';
    public $var2 = 'value 2';
    public $var3 = 'value 3';
  }

  $obj = new MyClass();

  foreach($obj as $key => $value) {
    print "$key => $value <br>";
  }

?>
```

결과
```
var1 => value 1 
var2 => value 2 
var3 => value 3
```

## 14.6 정적 클래스
클래스는 지금까지 인스턴스 객체를 생성을 하여 접근을 했습니다. 정적 클래스는 인스턴스를 생성하지 않고 클래스의 메서드와 프로퍼티를 접근할 수 있는 방식입니다.

정적 클래스 방식으로 접근하여 사용 시에는 인스턴스 객체를 가리키는 $this를 사용할 수 없습니다.


### 14.6.1 static
static 키워드는 프로퍼티를 정적 타입으로 선언한다는 의미입니다. static으로 선언된 프로퍼티는 인스턴스를 생성하지 않아도 접근이 가능합니다.

하지만 인스턴스 객체변수로는 접근이 불가능합니다.

예제 파일 class-09.php
```
<?php
	// 클래스를 선언합니다.
	class Jiny
	{
		public static $aaa = 10;
	
		public function show(){
			echo "show = ". self::$aaa;
		}
	}

	echo "aaa = ". Jiny::$aaa ."<br>";

	Jiny::show();

?>
```

결과
```
aaa = 10
show = 10
```

### 14.6.2 호출
정적 메서드와 프로퍼티의 호출은 -> 기호 대신에 더블콜론(::)을 사용합니다. 인스턴스의 객체가 없기 때문에 ->를 사용할 수 없습니다.

|문법|
```
클래스명::메서드();
클래스명::$프로퍼티명
```

형태로 작성을 해주면 됩니다.

위의 예제는 정적으로 선언된 프로퍼티와 메서드를 인스턴스 없이 바로 호출하는 예제입니다.

예제 파일 class-10.php
```
<?php
	// 클래스를 선언합니다.
	class jiny
	{
		public static $my_static = 'jiny';
		
		public function staticValue()
		{
			return self::$my_static;
		}
	}

	// 정적 프로퍼티를 출력합니다.
	print "정적 프로퍼티 =". Jiny::$my_static . "<br>";

	$jiny = new Jiny();
	print "인스턴스 =". $jiny->staticValue() . "<br>";

	// 정적 프로퍼티는 인스턴트화된 경우 ->로 호출할 수 없습니다.  
	print "인스턴스 =".$jiny->my_static . "<br>";      // Undefined "Property" my_static 

	print "정적 프로퍼티 =".$jiny::$my_static . "<br>";
	$classname = 'Jiny';
	print "정적 프로퍼티 =".$classname::$my_static . "<br>"; // As of PHP 5.3.0

?>
```

결과
```
정적 프로퍼티 =jiny
인스턴스 =jiny
인스턴스 =
정적 프로퍼티 =jiny
정적 프로퍼티 =jiny
```

PHP 5.3 이상부터는 클래스 이름을 가변변수를 이용하여 호출이 가능합니다. 변수를 이용한 호출은 가변적인 클래스 선택과 호출을 할 수 있는 장점이 있습니다.


### 14.6.3 SELF
자기 자신을 호출할 때 사용하는 키워드입니다. 

예로 자기 자신의 상수나 프로퍼티, 메서드를 호출할 때 사용합니다.

클래스 안에서 선언한 상수는 다음과 같이 호출하여 사용할 수 있습니다.

```
self::상수명;
```

클래스 안에 있는 프로퍼티 호출

```
self::$변수명;
```

클래스 안에 있는 메서드 호출

```
self::메서드();
```

## 14.7 익명 클래스

클래스를 선언할 때는 클래스명이 있어야 합니다. 함수에서 도 익명 함수가 있듯이 클래스에서도 클래스명을 생략한 익명 클래스를 사용할 수 있습니다.

익명 함수 기능은 PHP 7.x으로 업그레이드되면서 새롭게 추가된 기능입니다.

예제 파일 class-114.php
```
<?php
    // 인터페이스를 설정
    interface Logger
    {
        public function log(string $msg);
    }

    class Application
    {
        private $logger;

        // 반환 타입은 logger입니다.
        public function getLogger(): Logger
        {
            return $this->logger;
        }

    	// 인자값으로 클래스를 입력을 받습니다.
    	public function setLogger(Logger $logger)
        {
        	$this->logger = $logger;
    	}
    }

    $app = new Application;

    // 인자값을 익명의 클래스로 만들어서 전달합니다.
    $app->setLogger(
        new class implements Logger {
    		public function log(string $msg)
            {
        	   echo $msg;
    		}
	   }
    );

    var_dump($app->getLogger());

?>
```

결과
```
object(class@anonymous)#2 (0) { } 
```

위의 예제는 php.net에서 php7.x 새로운 익명 함수에 대한 간단한 설명 예제를 발췌했습니다. Application이라는 클래스는 한 개의 프로퍼티 변수와 두 개의 메서드 함수를 가지고 있습니다.

그중 setLogger() 메서드 함수는 매개변수 인자로 Logger 클래스 객체 타입의 변수를 전달받습니다. 기존의 경우 클래스 객체변수를 전달하기 위해서는 new를 통해서 Logger 클래스를 인스턴스화하여 객체변수를 생성 후에 매개변수로 사용해야 했습니다.

매번 일회성의 객체변수를 생성하는 것은 불필요할 수 있습니다. 이런 경우 익명 클래스를 통해 매개변수 입력 부분에 직접 클래스를 선언하여 전달합니다.

```
new class implements Logger {
    	public function log(string $msg) {
            	echo $msg;
    	}
}
```

매개변수로 전달되는 객체변수를 위와 같이 클래스명이 생략된 형태로 객체 선언으로 대체할 수 있습니다.


## 14.8 매직 메서드
클래스는 매직 메서드라는 몇 개의 미리 사전에 정의한 특수한 메서드가 있습니다. 클래스를 생성할 때 초기값을 설정하거나 오류 동작 등 실행되는 특별한 메서드입니다.


### 14.8.1 초기화
__construct() 메서드는 객체 생성 시 초기값 설정을 해주는 특수 메서드입니다. 또는 생성자 메서드라고도 부릅니다.

```
$obj = new members();
```

다음과 같이 클래스 인스턴스를 생성할 때 __construct() 메서드는 한 번 실행하게 됩니다. 이 메서드명은 미리 정의된 이름입니다.

__construct() 메서드를 사용하기 위해서는 클래스 내에 선언해야 합니다.

|문법|
```
class 클래스명
{
	function __construct()
	{
		// 부모의 초기값을 실행합니다.
		parent::__construct();

		// 개별 초기값을 설정합니다.
	}
}
```

클래스 상속의 경우 부모의 초기값 매직 메서드는 자동으로 실행되지 않습니다. 이런 경우 별도의 부모 초기값 매직 메서드를 추가해야 합니다.

예제 파일 class-121.php
```
<?php
	class BaseClass
	{
		function __construct()
		{
			echo "BaseClass 초기화<br>";
		}
	}

	class SubClass extends BaseClass
	{
		function __construct($a1,$a2,$a3)
		{
			// 부모의 초기화 메서드를 실행합니다.
			parent::__construct();

			// 초기화 메서드를 실행합니다.
			echo "SubClass 초기화<br>";

			// 입력 매개변수를 확인합니다.
			echo "초기화 매개변수 a1 = ".$a1."<br>";
			echo "초기화 매개변수 a2 = ".$a2."<br>";
			echo "초기화 매개변수 a3 = ".$a3."<br>";
		}

		public function show()
		{
			echo "hello world! <br>";
		}
	}

	// 인스턴스 생성 시 초기화 매개변수를 같이 전달합니다.
	$obj = new SubClass("인자1","인자2","인자3");
	$obj->show();

?>
```

결과
```
BaseClass 초기화
SubClass 초기화
초기화 매개변수 a1 = 인자1
초기화 매개변수 a2 = 인자2
초기화 매개변수 a3 = 인자3
hello world! 
```

위의 예제는 상속받은 클래스의 인스턴스를 생성합니다. 인스턴스 생성 시 초기 매개변수 값과 초기화 매직 메서드를 실행합니다.


### 14.8.2 소멸자
__construct() 처럼 초기화 메서드가 있다고 한다면 반대로 소멸자 매직 메서드가 존재합니다.

PHP 스크립트의 모든 소스가 실행 끝나고 나면 __destruct() 메서드 함수가 실행됩니다.

|문법|
```
class 클래스명
{
	function __destruct()
	{
		// 소멸 작업들을 설정합니다.
	}
}
```

예제 파일 class-132.php
```
<?php
	class BaseClass
	{
		function __construct()
		{
			echo "BaseClass 초기화<br>";
		}

		public function show()
		{
			echo "hello world! <br>";
		}

		function __destruct()
		{
			echo "BaseClass 소멸<br>";
		}
	}

	// 인스턴스 생성
	$obj = new BaseClass();
	$obj->show();
?>
```

결과
```
BaseClass 초기화
hello world!
BaseClass 소멸
```

위의 예제는 클래스의 인스턴스를 생성과 스크립트 종료와 함께 __destruct() 매직 메서드가 호출됩니다.


### 14.8.3 오류 호출
매서드를 사용하기 위해서는 반드시 클래스 내에 매서드 함수를 정의해야 합니다. 하지만 정의되지 않는 클래스를 사용하려고 하면 당연히 오류가 발생할 것입니다. 공동 작업이나 소스가 커질수록 이러한 오류가 발생할 확률도 커집니다.

만일 클래스 내에서 존재하지 않는 메서드를 호출할 때 오류를 발생하지 않고 __call() 메서드를 호출합니다. 
예제 파일 class-14.php
예제 파일 class-13.php
```
<?php
	class BaseClass
	{
		function __call($method,$params)
		{
			echo "오류: 정의되지 않는 메서드 ".$method."를 ".implode(', ', $params)."호출했습니다.";
		}
	}

	// 인스턴스 생성
	$obj = new BaseClass();
	$obj->show("a1","a2","a3");
?>
```

결과
```
오류: 정의되지 않는 메서드 show를 a1, a2, a3호출했습니다.
```

위의 예제 에서는 없는 메서드를 호출합니다. 없는 메서드를 호출하게 되면 대신에 __call() 매직 메서드를 호출합니다. __call() 함수는 두 개의 인자를 받습니다. 호출한 메서드명과 입력받은 파라미터 값을 배열로 전달합니다.

매직 메서드를 잘 이용하면 공동 작업 시 잘못된 메서드의 호출로 인하여 발생할 수 있는 오류를 사전에 방지할 수 있습니다.

### 14.8.4 객체의 문자열 변환
__toString() 매직 매서드는 클래스가 문자열로 변환하여 처리될 때 동작합니다. 예로 클래스 객체를 echo $obj;처럼 출력할 때 __toString() 메서드가 동작합니다.

예재 파일 class-15.php
```
<?php
	class TestClass
	{
    		public $foo;

    		public function __construct($foo)
    		{
        		$this->foo = $foo;
    		}

    		public function __toString()
    		{
        			return $this->foo;
    		}
	}

	$obj = new TestClass('Hello');
	
	// 클래스가 문자열로 변환 
	echo $obj;
?>
```

결과
```
Hello
```

### 14.8.5 객체 함수 호출

__invoke() 매직 메서드는 객체를 함수처럼 호출할 경우에 호출되는 메서드 입니다. $obj() 형태로 호출될 때 실행됩니다.

예제파일) class-16.php
```
<?php
	class dataInt
	{
    		public function __invoke($x)
    		{
        			var_dump($x);
    		}
	}

	$obj = new dataInt;

	$obj(5);
	
	var_dump(is_callable($obj));
?>
```

화면출력
```
int(5) bool(true)
```

### 14.8.6 객체 복제 호출

__clone() 매직 메소드는 객체가 복제 되었을 때 실행회는 메서드입니다.

예제파일) class-17.php
```
<?php

    class MyClass
    {
        public $instance;

        public function __clone() {
            echo "clone object<br>";
        }

    }
        
    $obj = new MyClass();

    $obj2 = clone $obj;

?>
```

화면출력
```
clone object
```

### 14.8.7 __set(), __get(), __isset(), __unset()

__set() 매직 메서드는 접근할 수 없는 프로퍼티에 값을 쓰고자 할 때 호출됩니다. __get() 매직 메서드는 접근할 수 없는 프로퍼티의 값을 읽을 경우에 호출됩니다. __isset() 매직 메서드는 접근할 수 없는 프로퍼티에 isset() 함수나 empty() 함수를 사용할 때 호출됩니다. __unset() 매직 매서드는 접근할 수 없는 프로퍼티를 unset() 함수를 사용할 때 호출됩니다.

예제 파일 class-18.php
```
<?php
	class MyClass
	{

		public function __set($name, $value) {
			echo "Setting '$name' to '$value' <br>";
		}

		public function __isset($name)
		{
			echo "Is '$name' set? <br>";
		}

		public function __unset($name)
		{
			echo "Unsetting '$name' <br>";
		}

	// 접근불가 프로퍼티에 대해 isset() 나 empty() 가 호출되었을때 불려집니다. 

		public function __get($name) {
			echo "Reading '$name' <br>";
		}


	}

	$obj = new MyClass();

	// 접근 불가 프로퍼티에 값을 설정할때 매직 매소드 __set() 호출
	$obj->name = "jiny";

	isset($obj->name);

	empty($obj->name);

	unset($obj->name);


	// 접근 불가 프로퍼티에 값을 읽을때 매직 매소드 __get() 호출
	echo $obj->name;
?>
```

결과
```
Setting 'name' to 'jiny' 
Is 'name' set? 
Is 'name' set? 
Unsetting 'name' 
Reading 'name'
```

### 14.8.8 그 외 메서드
이외에도 다음과 같은 매직 메서드가 더 있습니다. 지면상 전부 다룰 수 없어서 보다 자세한 부분은 공식 사이트에서 확인 가능합니다.

●	__callStatic() : 정적 컨텍스트 내에서 접근 불가 메서드를 가져올 때 호출됩니다.
●	__sleep()
●	__wakeup()
●	__set_state() : var_export()에 의해 내보내진 클래스를 위해 호출됩니다.
●	__debugInfo() : var_dump()에 의해 덤프될 때 보여줄 속성을 가져올 때 호출됩니다.




# 15 클래스 확장
기본적인 클래스에 대해서 살펴봤습니다.  클래스는 변수(프로퍼티)와 함수(메서드)를 묽어서 객체화 하여 사용을 했습니다. 클래스의 객체지향 방식의 코딩은 프로그램의 보다 최적화 및 유지보수화하는 데 매우 유용합니다.이번 장에서는 최신 클래스 기반의 코딩 및 확장된 기능들에 대해서 살펴 보도록 하겠습니다. 클래스의 확장은 오픈소스 및 다양한 개발자들과 협업하는 데 필요한 코드 구현 기술입니다. 


## 15.1 클래스 상속

예를 들어 기존의 생성한 클래스가 하나 있습니다. 그리고 기존과 기능이 비슷하지만 몇 개의 기능이 추가된 또 다른 클래스 하나 더 만들려고 합니다.

이렇게 기존에 만들어 놓은 클래스 소스를 같이 사용을 하면서, 새로운 추가 클래스를 만들 수 있는 방법은 없을까? 개발자라면 이런 고민을 해본 적이 있을 것입니다. 기존 클래스 코드를 유지하면서 새로운 클래스를 적용할 수 있는 방법이 상속입니다.

상속은 말 그대로 부모의 클래스 자산을 이어받는 것입니다. 우리는 부모의 유전자를 기반으로 새로운 생명이 만들어졌고, 그 부모 또한 그렇습니다. 이처럼 상속은 기존의 것을 유지하면서 새로운 것을 만들 때 매우 유용합니다.

상속을 받으면 부모의 기능들은 사용할 수도 있고 자신만의 새로운 기능들도 추가할 수 있습니다. 일거양득으로 소스의 코드들을 향상시킬 수 있습니다.





### 15.1.1 상속 문법

클래스를 상속하여 사용하는 것은 매우 간단합니다. 상속을 하고자 하는 클래스를 클래스 선언부 뒤쪽에 extends 키워드를 추가하여 상속하고자 하는 부모 클래스명을 적으면 됩니다.

클래스 상속 문법
class 기존 클래스 
{

}

class 추가 클래스 extends 기존 클래스 {
}

class 추가 클래스2 extends 추가 클래스 {
}

위의 사용 문법을 보면 기존 클래스 하나가 선언되어 있습니다. 추가 클래스는 extends 키워드를 통하여 기존클래스를 상속한 새로운 클래스가 하나 더 생성을 했습니다.

처음에 만든 기존 클래스는 상속받은 추가클래스의 또 다른 클래스 상속의 부모로 사용할 수 있습니다. 추가 클래스2는 추가클래스를 상속받은 새로운 객체 입니다.

예제 파일 extends-01.php
```
<?php
    // 기본 클래스 a를 생성합니다.
    class a
    {
        public function hello($string)
        {
            echo "Hello = " . $string . "<br>";
        }
    }

    // 기본 클래스 a를 상속하는 b 클래스를 생성합니다.
    class b extends a
    {
        public function whatIs($string)
        {
            echo "myName is: " . $string . "<br>";
        }
    }

    // 상속받은 b 클래스 인스턴스를 생성합니다.
    $obj = new b();

    // 상속받은 부모의 메서드 함수를 사용할 수 있습니다.
    $obj->hello("jiny");

    // 새롭게 추가한 메서드 함수를 사용할 수 있습니다.
    $obj->whatIs("hojinLee");

?>
```

결과
```
Hello = jiny
myName is: hojinLee
```

위의 예는 클래스 상속의 예입니다. 클래스 a와 a를 상속한 새로운 클래스 b 두 개를 생성합니다.  
상속은 extends 키워드를 이용하면 됩니다. $obj 클래스 객체는 상속받은 클래스 a의 매서드를 호출하여 사용할 수 있습니다.

### 15.1.2 클래스의 계층화
클래스 상속의 또 다른 의미는 무엇일까요? 바로 클래스가 계층화 된다는 것입니다. 조상의 역사를 기록한 족보처럼 클래스도 계속 상속을 하게 되면 족보처럼 단계별로 계층화됩니다.

클래스 상속이 계속 되면서 개발자가 추가한 새로운 메서드와 프로퍼티가 추가되고 기능이 하나씩 늘어가는 것입니다. 이렇게 계층화되면서 코드는 더욱 더 고도화되고 커져 갑니다.

 

또한 계층화된 구조를 쉽게 파악하기 위해서 별도의 계층도 같은 그림을 그려서 관리하기도 합니다.

이러한 계층적 작업은 여러 사람들이 같이 코드를 작성하고 기능을 추가하는 데 매우 유연한 환경을 제공합니다. 내가 만들어 놓은 클래스를 응용하여 새로운 클래스를 다른 사람들이 만들어 사용할 수도 있을 것입니다. 클래스의 상속과 계층화는 마치 부품을 하나씩 조립하면서 또 다른 큰 부품을 만들고, 그 부품들을 조립하여 최종적인 결과물을 만들어내는 것과 유사합니다.


### 15.1.3 부모 클래스

extends로 상속받는 이전의 클래스를 부모 클래스라고 합니다.


클래스 상속 시 부모의 메서드 및 프로퍼티를 별도의 특별한 표기 없이 쉽게 사용을할 수 있습니다. 하지만 부모 클래스의 프로퍼티와 메서드 기능을 꼭 선택해서 호출하고 싶을 때는 parent:: 키워드를 이용하여 부모 클래스를 호출할 수 있습니다.



예제 파일 extends-02.php
```
<?php
    // 기본 클래스 a를 생성합니다.
    class a
    {
        public function isAdult($age)
        {
            if($age>=18) return true; else return false;
        }

    }

    // 기본 클래스 a를 상속하는 b 클래스를 생성합니다.
    class b extends a
    {
        public function whatIs($string,$age)
        {
            echo "myName is: " . $string . "<br>";

            if (parent::isAdult($age)){
                echo "성인입니다.<br>";
            } else {
                echo "미성년입니다.<br>";
            }

        }

    }

    // 상속받은 b 클래스 인스턴스를 생성합니다.
    $obj = new b();

    // 새롭게 추가한 메서드 함수를 사용할 수 있습니다.
    $obj->whatIs("hojinLee",18);

    $obj->whatIs("jiny",17);
?>
```

결과
```
myName is: hojinLee
성인입니다.
myName is: jiny
미성년입니다.
```
위의 예는 클래스 상속의 예입니다.  
클래스 b는 클래스 a를 상속받은 클래스입니다. Parent:: 키워드를 이용하여 클래스 a의 메서드를 호출할 수 있습니다.

### 15.1.4 자식 클래스  

자식 클래스는 부모 클래스의 반대말입니다. 

 

부모 클래스를 상속받아 새롭게 생성되는 클래스를 자식 클래스라고 합니다.

## 15.2 오버라이딩

클래스 상속은 부모의 기능을 이어받으면서 새로운 클래스를 생성합니다. 즉, 부모의 모든 메서드와 프로퍼티를 자식 클래스에게 사용 가능하도록 상속합니다.

하지만, 상속받은 기능 하나를 변경고자 할 때는 어떻게 해야 할까요? 기능이 약간 변경이 되거나 새롭게 재정의를 할 수 있습니다. 클래스는 이런 경우를 위해서 기존의 기능을 다시 덮어써서 다시 선언할 수 있는 오버라이딩이라는 기능을 제공합니다.

 

오버라이딩이란 상속받은 클래스의 메서드 중에서 특정 하나의 메서드의 함수를 다시 정의해서 사용을 하는 경우 입니다. 오버라이딩은 상속 전에 미리 구현해 놓은 메서드가 있을 때 상속받은 자식 클래스에서 다시 새로운 코드로 작성이 필요할 경우 매우 유용합니다.

### 15.2.1 오버라이딩 예제

그럼 상속받은 클래스를 오버라이딩을 통해 재정의하는 것을 예제를 통해서 학습해 보도록 하겠습니다. 오버라이딩 작성은 매우 간단합니다.

예제 파일 override-01.php
```
<?php
    // 기본 클래스 a를 생성합니다.
    class a
    {
        public function isAdult($age)
        {
            if($age>=18) return true; else return false;
        }

    }

    // 기본 클래스 a를 상속하는 b 클래스를 생성합니다.
    class b extends a
    {
        // a의 메서드를 오버라이딩 다시 정의합니다.
        public function isAdult($age)
        {
            if($age>=20) return true; else return false;
        }

        public function whatIs($string,$age)
        {
            echo "myName is: " . $string . "<br>";

            if ($this->isAdult($age)){
                echo "성인입니다.<br>";
            } else {
                echo "미성년입니다.<br>";
            }

        }

        public function old18($string,$age)
        {
            echo "myName is: " . $string . "<br>";

            if (parent::isAdult($age)){
                echo "성인입니다.<br>";
            } else {
                echo "미성년입니다.<br>";
            }

        }

    }

    // 상속받은 b 클래스 인스턴스를 생성합니다.
    $obj = new b();

    echo "오버라이딩한 클래스의 결과<br>";
    // 새롭게 추가한 메서드 함수를 사용할 수 있습니다.
    $obj->whatIs("hojinLee",18);
    $obj->whatIs("jiny",17);

    // 오버라이딩 이전의 메서드를 이용합니다.
    // parent 키워드 이용
    echo "===== <br>";
    echo "오버라이딩 이전의 클래스의 결과<br>";
    $obj->old18("hojinLee",18);
    $obj->old18("jiny",17);
?>
```

결과
```
오버라이딩한 클래스의 결과
myName is: hojinLee
미성년입니다.
myName is: jiny
미성년입니다.
=====
오버라이딩 이전의 클래스의 결과
myName is: hojinLee
성인입니다.
myName is: jiny
미성년입니다.
```

위의 예는 클래스의 오버라이딩 예입니다. 클래스의 메서드를 오버라이드하는 별도의 문법적 키워드는 없습니다. 그냥 동일한 메서드명으로 다시 작성하면 자동으로 오버라이딩되어 처리됩니다.   

클래스 a에는 isAdult() 메서드가 선언되어 있습니다. 클래스 b는 클래스 a를 상속받았지만 클래스 정의 내에서 클래스 a의 메서드와 동일한 이름의 isAdult() 메서드가 또 존재합니다.

기존 부모 클래스의 메서드와 자식 클래스내에 동일한 이름의 메서드가 있을 경우 자식의 메서드를 우선으로 처리합니다. 즉, 동일한 이름으로 겹치게 되면 자동으로 오버라이딩된 것으로 처리합니다.

만일 오버라이딩하기 전의 부모의 메서드를 사용하고 싶다면 parent:: 키워드를 사용하면 됩니다.
 

### 15.2.2 final 키워드

오버라이딩 기능은 부모의 메서드를 재정의 하여 사용할 수 있었습니다. 하지만 중요한 메서드의 경우 상속후에 재정의하여 사용할 경우 문제가 발생할 수도 있습니다. 이런 경우, 오버라이딩을 하지 못하게 할 필요성이 있습니다. 클래스에서는 상속을 받아도 오버라이딩이 되지 않도록 방지하는 final 키워드를 제공합니다.

final로 선언된 메서드는 상속되어도 오버라이딩을 할 수 없습니다.

예제 파일 final-01.php
```
<?php
    // php.ini의 수정 없이, 화면에 에러 발생 시 출력할 수 있습니다.
    error_reporting(E_ALL);
    ini_set("display_errors", 1);

    // 기본 클래스 a를 생성합니다.
    class a
    {

        final public function copyright (){
            // 본 메서드 함수는 대체되지 않습니다.
            echo "copyright all Right JinyPHP";
        }

    }

    // 기본 클래스 a를 상속하는 b 클래스를 생성합니다.
    class b extends a
    {

        public function copyright(){
            // 본 메서드 함수는 대체되지 않습니다.
            echo "copyright all Right ...";
        }

     
    }

    // 상속받은 b 클래스 인스턴스를 생성합니다.
    $obj = new b();

    $obj->copyright();

?>
```

오류 메시지
```
/jinyphp/final-01.php - Cannot override final method a::copyright() in C:\php-7.1.4-Win32-VC14-x86\jinyphp\final-01.php on line 27
```

위의 예제는 클래스의 오버라이딩 방지에 대한 예입니다. final키워드로설정된 메서드는 상속후 다시 오버라이딩을 할 수 없습니다. 만일 final로 선언된 메서드를 오버라이딩을 할 경우 "cannot override final method" 오류가 표시됩니다.

문법 
```
final class users
{
}
```

참고로, 만일 class 키워드 앞에 final 키워드를 입력하면 클래스 전체가 final로 설정됩니다.


## 15.3 인터페이스

클래스가 상속될 때 부모의 메서드나 프로퍼티는 자식 클래스에 전달됩니다. 또한 메서드가 변경된 경우 오버라이딩되어 다시 재정의 사용할 수 있었습니다.

만일 어떤 메서드는 꼭 필요하지만 상속받은 자식 클래스마다 서로 달라 다르게 매번 오버라이딩을 해야 한다면 어떻게 해야 될까요? 이런 경우에 부모의 메서드를 만들어 놓는 것은 의미가 없을 수 있습니다.


### 15.3.1 인터페이스 개념
인터페이스는 다수의 사람들의 클래스를 설계할 때 서로 약속한 규약과 같습니다. 자신이 만든 클래스를 다른 사람들과 협업하여 개발을 할 때 클래스의 규칙을 정의하는 것입니다. 인터페이스는 이 클래스는 어떻게 만들어야 한다는 지시와 같습니다.

이러한 클래스의 규칙들은 인터페이스 기능을 이용하여 매우 유용하게 사용할 수 있습니다. 

인터페이스로 정의된 클래스의 메서드들은 부모에서 미리 선언을 합니다. 인터페이스를 적용한 자식 클래스에서는 부모에서 지시한 인터페이스 규칙을 따라 만들라고 지시하는 것과 같습니다.

 

오픈소스 및 큰 규모의 프로젝트를 여러 사람이 함께 개발할 때 인터페이스는 매우 유용합니다. 또한 개발된 소스를 다수의 개발자들에게 배포할 경우 인터페이스 정의 기능은 불특정한 클래스의 오동작을 방지할 수 있습니다.

인터페이스로 상속받으면 자식 클래스는 인터페이스 규약에 따라서 메서드와 프로퍼티를 반드시 만들어야 합니다. 만들지 않으면 오류를 발생합니다.

### 15.3.2 인터페이스 문법

인터페이스는 class 키워드 대신에 interface 키워드를 사용하면 됩니다. 그 외의 사용법은 클래스를 선언하는 것과 매우 비슷합니다.
  
인터페이스 문법
```
interface pages 
{

  public function index();

}
```

위의 인터페이스 사용 문법예서 interface 키워드와 안에는 메서드 이름과 매개변수, 반환값 등만 정의된 것을 확인할 수 있습니다. 메서드 들의 실제적인 코드의 몸체 { }는 작성하지 않습니다. 인터페이스에서 정의된 코드의 몸체는 인터페이스를 적용한 자식 클래스에서 작성합니다.

인터페이스 내부의 메서드는 반드시 public으로 속성을 설정합니다. public 속성을 지정하는 것은 interface 선언 및 방법에 대한 특성입니다. 

### 15.3.3 클래스 사용

이렇게 미리 설계된 인터페이스 규약은 클래스 상속과 유사한 문법으로 사용할 수 있습니다. 단지 클래스 생성 시 상속 키워드 extends 대신에 인터페이스 키워드 implements 를 사용하면 됩니다.
예제 파일 interface-01.php
```
<?php
	interface pages
	{

		public function index();

	}

	class intro implements pages
	{
		public function index()
		{
			echo "인터페이스 소개 <br>";
		}
	}

	$obj = new intro();
	$obj->index();
	
?>
```

결과
```
인터페이스 소개 
```

위의 예제는 클래스의 인터페이스에 대한 예입니다. 먼저 pages 라는 이름의 인터페이스 규약을 정의합니다. intro라는 클래스를 생성할 때 이전에 정의한 pages라는 인터페이스 규약을 따릅니다.

pages 인터페이스를 따르는 클래스를 생성할 때 index()라는 메서드를 꼭 만들어 쓰라는 의미입니다. 

예제 파일 interface-02.php
```
<?php
	interface pages
	{

		public function index();

	}

	class intro implements pages
	{

	}

	$obj = new intro();
	
?>
```

결과
```
[Fri May 12 15:43:33 2017] ::1:51820 [500]: /jinyphp/interface-02.php - Class intro contains 1 abstract method and must therefore be declared abstract or implement the remaining methods (pages::index) in C:\php-7.1.4-Win32-VC14-x86\jinyphp\interface-02.php on line 9
```
두 번째 예제는 선언된 인터페이스를 구현하지 않은 경우입니다. 인터페이스를 적용하면서 인터페이스에서 규약한 방식대로 사용하지 않을 때 PHP는 에러를 출력하고 실행을 중단합니다. 

### 15.3.4 인터페이스 확장
인터페이스도 extends 키워드를 통해 상속 확장이 가능합니다. 다음 예는 인터페이스의 확장입니다.

예제 파일 interface-03.php
```
<?php
	interface a
	{
    	public function foo();
	}

	// a 인터페이스를 상속 받습니다.
	interface b extends a
	{
    	public function bar();
	}

	// 상속받은 b 인터페이스로 구현합니다.
	class c implements b
	{
    	public function foo()
    	{
    		echo "method is foo <br>";
    	}

    	public function bar()
    	{
    		echo "method is bar <br>";
    	}
    	
	}

	$obj = new c;

	// 인터페이스 a의 메서드입니다.
	$obj->foo();

	// 인터페이스 b의 메서드입니다.
	$obj->bar();

?>
```

결과
```
method is foo 
method is bar
```
위의 예는 인터페이스 상속에 대한 실험입니다. 인터페이스 b는 인터페이스 a를 상속을 받습니다.


### 15.3.5 인터페이스 다중 상속
다수의 인터페이스를 콤마(,)로 구분하여 한 번에 인터페이스를 상속받을 수 있습니다.

예제 파일 interface-04.php
```
<?php
    interface a
    {
        public function foo();
    }

    interface b
    {
        public function bar();
    }

    interface c extends a, b
    {
        public function baz();
    }

    class d implements c
    {
        public function foo()
        {
            echo "method is foo <br>";
        }

        public function bar()
        {
            echo "method is bar <br>";
        }

        public function baz()
        {
            echo "method is baz <br>";
        }
    }

    $obj = new d;

    // 인터페이스 a의 메서드입니다.
    $obj->foo();

    // 인터페이스 b의 메서드입니다.
    $obj->bar();

    // 인터페이스 c의 메서드입니다.
    $obj->baz();

?>
```

결과
```
method is foo 
method is bar 
method is baz
```
위의 예제는 인터페이스 상속에 대한 예입니다. 인터페이스 c는 인터페이스 a와 b를 직접 상속을 받습니다.


### 15.3.6 인터페이스 와 상속
기존 클래스의 상속과 인터페이스를 동시에 적용하여 새로운 클래스를 생성할 수 있습니다. 먼저 상속을 받고자 하는 클래스를 extends 키워드를 사용하여 상속을 합니다. 계속 같은 줄에서 이어서 implements 키워드를 통하여 적용하고자 하는 인터페이스를 지정할 수 있습니다.

예제 파일 interface-05.php
```
<?php
	interface a
	{
    	public function foo();
	}

	// a 인터페이스를 상속 받습니다.
	interface b extends a
	{
    	public function bar();
	}

	class Bird {
		public function info() {
			echo "I am a {$this->name} <br>";
			echo "I am an bird <br>";
		}
	}

	class Penguin extends Bird implements b {
		var $name = "Penguin";
		
		public function foo()
    	{
    		echo "method is foo <br>";
    	}

    	public function bar()
    	{
    		echo "method is bar <br>";
    	}

	}

	$obj = new Penguin;

	// 상속 메서드입니다.
	$obj->info();

	// 인터페이스 a의 메서드입니다.
	$obj->foo();

	// 인터페이스 b의 메서드입니다.
	$obj->bar();

?>
```

결과
```
I am a Penguin 
I am an bird 
method is foo 
method is bar
```

위의 예는 인터페이스 상속에 대한 실험입니다. 인터페이스 적용과 클래스를 동시에 상속을 받아 클래스를 생성을 합니다.

예제 파일 interface-06.php
```
<?php
	interface a
	{
    	public function foo();
	}

	interface b 
	{
    	public function bar();
	}

	class Bird {
		public function info() {
			echo "I am a {$this->name} <br>";
			echo "I am an bird <br>";
		}
	}

	class Penguin extends Bird implements a, b {
		var $name = "Penguin";
		
		public function foo()
    	{
    		echo "method is foo <br>";
    	}

    	public function bar()
    	{
    		echo "method is bar <br>";
    	}

	}

	$obj = new Penguin;

	// 상속 메서드 입니다.
	$obj->info();

	// 인터페이스 a의 메서드 입니다.
	$obj->foo();

	// 인터페이스 b의 메서드 입니다.
	$obj->bar();

?>
```

결과
```
I am a Penguin 
I am an bird 
method is foo 
method is bar
```

위의 예제는 인터페이스 상속에 대한 예입니다. 위의 예제는 앞의 interface-05.php와 동일한 동작을 합니다. 인터페이스 a와 b를 콤마(,)로 구분하여 다중 적용하여 동작합니다.

### 15.3.7 인터페이스 상수
인터페이스 에서도 상수를 선언하여 사용할 수 있습니다.

예제 파일 interface-07.php
```
<?php

	interface a{

    	const name = "interface a const";
	}

	echo a::name;
	echo "<br>";

	class b implements a
	{

	}

	class c extends b
	{
    	const age = 'Class c constant';
	}

	echo c::age;

?>
```

결과
```
interface a const
Class c constant
```

## 15.4 추상화

클래스의 상속과 오버라이딩, 인터페이스를 세 가지의 클래스 확장 기능을 배웠습니다. 하지만 이중 상속과 인터페이스 두 개는 함께 사용할 수 없습니다. 즉, 상속과 인터페이스 규약을 혼합하여 사용할 수 없습니다. 

이 두 개를 서로 같이 사용할 수 없는 이유는 상속과 인터페이스는 문법이 서로 매우 비슷합니다. 클래스명과 키워드 그리고 상속, 인터페이스명입니다. 

```
class 클래스명 extends 상속 클래스
{
}

class 클래스명 implements 인터페이스
{
}
```

두 개의 기능을 콤마(,)등을 이용하여 구분하거나 연장해서 사용할 수 없다는 것입니다.

 

추상화는 이러한 문법적 유사점과 두 가지 기능을 유지하면서 두 개의 기능을 같이 사용하기 위한 것이 방법입니다. 즉, 추상화 = 상속 + 인터페이스 기능을 동시에 하고 싶을 때 사용되는 OOP 개념입니다.


### 15.4.1 추상화 문법

클래스에 추상화 사용법 또한 매우 간단합니다. 추상화 설정은  클래스명 또는 메서드 앞에 새로운 추상화 키워드 abstract를 같이 선언만 해주면 됩니다.

|문법|
```
abstract class 추상화 클래스
{
    // 추상화: 인터페이스
    abstract public function 메서드();

    // 공통 메서드
    public function copyright() {
        echo "copyright all Right JinyPHP";
    }
}


class 클래스명 extends 추상화 클래스
{
    public function 메서드() {
        return "abstract Method";
    }
}
```
클래스를 정의할 때 abstract 키워드를 이용하여 추상화 클래스와 메서드 등을 생성합니다. 추상화로 선언한 메서드들은 인터페이스와 같이 자식 클래스에서 반드시 선언해야 합니다.

추상화 클래스를 적용하는 방법은 상속과 같이 extends 키워드로 사용합니다.


### 15.4.2 추상화 예제

예제 파일 abstract-01.php
```
<?php

    // 추상화 클래스를 선언합니다.
    abstract class a
    {
        // 확장 시 구현부가 필요한 메서드 정의
        abstract public function isAdult($age);
        
        public function copyright ()
        {
            // 본 메서드 함수는 대체되지 않습니다.
            echo "copyright all Right JinyPHP";
        }
    }

    // 추상화 적용
    class b extends a
    {
        // 추상화 인터페이스를 구현
        public function isAdult($age)
        {
            if ($age>=18) return true; else return false;
        }
    }

    $obj = new b();

    // 추상화에 선언된 일반 메서드를 상속, 호출 가능합니다.
    $obj->copyright();

    if ($obj->isAdult(18)){
        echo "성인입니다.";
    } else {
        echo "미성년입니다.";
    }

?>
```

결과
```
copyright all Right JinyPHP 성인입니다.
```

위의 예제를 보면 추상화 클래스는 일반 클래스처럼 프로퍼티와 메서드 등을 구현할 수 있습니다. 또한 자식 클래스에서 다시 구현 처리해야 하는 인터페이스는 abstract 키워드를 추가하여 함께 선언합니다.

추상화 클래스를 상속받은 자식 클래스는 부모의 메서드 기능도 같이 상속받아 호출 사용 가능합니다. 또한 abstract로 선언한 인터페이스 메서드를 같이 구현해야 합니다.

추상화에서 선언된 인터페이스를 구현하지 않은 경우 PHP는 에러를 출력하고 PHP 코드를 더 이상 실행하지 않습니다. 이것은 인터페이스 규약을 따르지 않는 동작과 유사합니다.


## 15.5 트레이트
클래스의 상속 기능은 기존의 코드들을 재사용하면서 새로운 클래스를 생성하기 위한 코딩 방법론이었습니다. 하지만 상속이라는 개념은 클래스의 계층화로 항상 부모가 존재합니다. 

클래스의 상속, 오버라이딩, 인터페이스, 추상화 등 객체들을 계층적으로 생성하고 정의하여 사용했습니다. 기존 방식과 같이 만일 클래스 A 기능과, 클래스 B의 기능을 가진 클래스 C를 만들고 한다면 어떻게 해야 할까요?

```
class a {
}

class b extend b {
}

class c extend b {
}
```

형태로 계속 상속 형태로 들어가면서 계층화를 해야 합니다. 객체를 계층화한다는 것은 불필요한 기능적 유전자까지 모두 부모의 영향을 받게 됩니다.

트레이트는 요즘 유전자 조작처럼 상속을 받지 않고 특정한 클래스들을 조합하는 것과 같습니다. 최신 PHP 코딩 방식에서는 이런 계층화적인 클래스 재사용 방식이 아니라 클래스 안에 새로운 또 다른 클래스를 삽입하는 개념의 트레이트를 방법을 제공합니다.

트레이트는 PHP 5.4 업그레이드되면서 적용된 기능입니다. 

 


### 15.5.1 트레이트 선언

트레이트를 선언하는 방법은 클래스 선언 문법과 비슷합니다. class 키워드 대신에 trait 키워드를 사용해주면 됩니다.

트레이트 문법
```
trait 트레이트명 
{
// 트레이트 내용 구현
}
```

이렇게 선언한 트레이트 클래스는 다른 클래스에 use 키워드로 삽입할 수 있습니다.

```
<?php
class MyClass {

  use myTrait; 

  // 클래스 내용 구현
}
?>
```

PHP언어의 전처리기 명령인 include와 require처럼 코드를 읽어서 결합하는 것과 비슷해 보입니다. 클래스의 결합이라고 이해하면 됩니다. 하지만, 상속과도 약간의 차이점이 있는 것을 알 수 있습니다.

트래이트를 구현 시 현재의 메서드를 우선적으로 적용 후에 상속된 메서드를 재정의하는 우선순위를 가지고 있습니다.


다음 예제는 트레이트를 생성 후에 클래스에 주입하여 사용하는 예제입니다.
예제 파일 trait-01.php
```
<?php

	// 기존 클래스 작성하는 것과 같이 트레이트를 작성합니다.
	trait geoLocation
	{
		public function getLatitude()
		{
    		echo "좌표  Latitude<br>";
  		}

 		public function getLongtitude()
 		{
			echo "좌표  Longtitude<br>";
 		}

	}

	// 지도 매핑 클래스를 생성합니다.
	class mapping
	{
		// use키워드로 트레이드를 삽입합니다.
  		use geoLocation;
  		
  		// 추가 클래스…. 구현
  		public function copyright()
        		{
            		// 본 메서드 함수는 대체되지 않습니다.
            		echo "copyright all Right JinyPHP";
        		}

	}

	$obj = new mapping();

	// 트레이트로 삽입한 메서드를 실행합니다.
	$obj->getLatitude();
	$obj->getLongtitude();

	// 자체 선언 메서드를 출력합니다.
	$obj->copyright();

?>
```

결과

```
좌표 Latitude
좌표 Longtitude
copyright all Right JinyPHP
```

위의 예를 보면 트레이트를 통해 지리 정보를 출력하는 간단한 트레이트를 생성합니다. 

mapping 클래스는 geoLocation라는 클래스를 상속하는 것이 아니라 클래스 안에 트레이트로 삽입하는 것을 볼 수 있습니다.

트레이트가 주입된 클래스는 일반적인 인스턴스 형태로 생성한 다음 -> 기호를 통해 트레이트에서 선언한 메서드를 실행할 수 있습니다.


### 15.5.2 다중 트레이트
트레이트는 콤마(,)를 통하여 다중 트레이트를 적용할 수 있습니다.

|문법|
```
use trait1, trait2;
```

예제 파일 trait-02.php
```
<?php

	// 기존 클래스 작성하는 것 과 같이 트레이트를 작성합니다.
	trait Latitude
	{
		public function getLatitude()
		{
    		echo "좌표  Latitude<br>";
  		}

	}

	trait Longtitude
	{
		public function getLongtitude()
 		{
			echo "좌표  Longtitude<br>";
 		}
	}

	// 지도 매핑 클래스를 생성합니다.
	class mapping
	{
		// use키워드로 트레이드를 삽입합니다.
		// 콤마로 구분하여 다중 트레이트를 구현합니다.
  		use Latitude, Longtitude;
  		
  		// 추가 클래스…. 구현
  		public function copyright()
        		{
            		// 본 매메서드 함수는 대체되지 않습니다.
            		echo "copyright all Right JinyPHP";
        		}

	}

	$obj = new mapping();

	// 트레이트로 삽입한 매메소드메서드를 실행합니다.
	$obj->getLatitude();
	$obj->getLongtitude();

	// 자체 선언 메소드메서드를 출력합니다.
	$obj->copyright();

?>
```

결과
```
좌표 Latitude
좌표 Longtitude
copyright all Right JinyPHP
```

위의 예제는 다중 트레이트의 예입니다. 위의 trait-01.php 예제와 동일한 결과를 출력하지만, 트레이트를 두 개로 나눠서 다중 트레이트 방식으로 적용합니다.

### 15.5.3 트레이트 충돌
여러 개의 트레이트를 적용할 경우 메서드의 동일한 이름으로 인하여 충돌이 발생할 수도 있습니다. 트레이트는 오버라이딩처럼 재정의할 수가 없습니다. 이런 경우 insteadof 키워드를 통하여 충돌한 트레이트의 메서드를 직접 지정해야 합니다.

예제 파일 trait-03.php
```
<?php
    trait a {
        public function name() {
            echo "trait A name<br>";
        }

        public function age() {
            echo "trait A age<br>";
        }
    }

    trait b {
        public function name() {
            echo "trait B name<br>";
        }

        public function age() {
            echo "trait B age<br>";
        }
    }

    class members {
        use a, b {
            b::name insteadof a;
            a::age insteadof b;
            b::name as name2;
        }
    }

    $obj = new members;
    $obj->name();
    $obj->age();

    // as 별칭 메서드
    $obj->name2();

?>
```

결과
```
trait B name
trait A age
trait B name
```

위의 예제는 트레이트 충돌에 대한 예입니다. 트레이트 a와 b의 메서드는 서로 충돌합니다. 트레이트를 적용할 때 insteadof 키워드를 통하여 사용할 트레이트의 메서드를 직접 지정할 수 있습니다.

또는 as 키워드를 통해 충돌되는 메서드를 다른 이름으로 별칭을 만들어 사용할 수도 있습니다.

### 15.5.4 메서드 속성 변경
트레이트를 적용할 때 as 키워드를 통하여 메서드의 속성을 변경할 수 있습니다. 

예제 파일 trait-04.php
```
<?php
	trait HelloWorld {
    		public function sayHello() {
        			echo "Hello World!";
    		}
	}

	// sayHello 속성을 변경
	class MyClass1 {
    		use HelloWorld { sayHello as protected; }

    		public function hello(){
    			echo "protect method call <br>";
    			$this->sayHello();
    		}
	}

	$obj = new MyClass1;
	$obj->hello();

?>
```

결과
```
protect method call 
Hello World!
```

위의 예제는 as 키워드를 통하여 메서드의 속성을 변경합니다. public 속성의 sayHello() 메서드를 as 키워드를 이용하여 protect 속성으로 변경합니다. hello() 메서드는 protect 속성으로 변경된 sayHello() 메서드를 호출합니다.


### 15.5.5  트레이트 조합
하나의 트레이트에서는 또 다른 트레이트를 연결하여 조합할 수 있습니다.

예제 파일 trait-05.php
```
<?php
	trait a {
    	public function foo() {
        	echo "Trait Method foo!<br>";
    	}
	}

	trait b {
		
		// 트레이트 a 를 조합
		use a;

    	public function bar() {
        	echo "Trait Method bar!<br>";
    	}
	}

	class myClass {
		use b;
	}

	$obj = new myClass;
	$obj->foo();
	$obj->bar();

?>
```

결과
```
Trait Method foo!
Trait Method bar!
```

### 15.5.6  트레이트 추상화
트레이트 메서드를 선언할 때 abstract 키워드를 통하여 추상화 메서드도 같이 설정할 수 있습니다. abstract로 선언된 메서드는 use 키워드를 통해 트레이트 적용 후에 추상화 선언된 메서드를 생성해야 합니다.

예제 파일 trait-06.php
```
<?php
	trait Hello {
    		public function sayHelloWorld() {
        			echo "Hello ".$this->getWorld();
    		}

    		abstract public function getWorld();
	}

	class MyHelloWorld {
    		private $world;
    	
    		use Hello;
    	
    		public function getWorld() {
        			return $this->world;
    		}
    
    		public function setWorld($val) {
        			$this->world = $val;
    		}
	}

	$obj = new MyHelloWorld;
	$obj->setWorld("jiny");

	echo $obj->getWorld();
	echo "<br>";
	$obj->sayHelloWorld();

?>
```

결과
```
jiny
Hello jiny
```


### 15.5.7  트레이트 정적 호출
정적 static 키워드를 통해 선언된 트레이트 메서드는 더블콜론(::)을 이용하여 호출할 수 있습니다.

예제 파일 trait-07.php
```
<?php
	trait Hello {
    	public static function sayHelloWorld() {
        	return "Hello World!";
    	}
	}

	class MyHelloWorld {
    	use Hello;
	}

	echo MyHelloWorld::sayHelloWorld();
?>
```

결과
```
Hello World!
```

### 15.5.8  트레이트 프로퍼티
트레이트 안에서도 프로퍼티 변수를 선언할 수 있습니다. 트레이트 안에서 선언된 프로퍼티는 클래스 안에서 동일한 이름으로 프로퍼티를 정의할 수 없습니다.

예제 파일 trait-08.php
```
<?php
	trait PropertiesTrait {
    	public $x = 1;
	}

	class myClass {
    	use PropertiesTrait;
	}

	$obj = new myClass;
	echo $obj->x;
?>
```

결과
```
1
```

## 15.6 네임스페이스

네임스페이스는 같은 유형의 클래스들을 그룹으로 묶어 관리할 수 있는 가상의 폴더와 같습니다. 다른 고급 언어에서는 네임스페이스 기능을 도입하여 클래스 패키지 방법을 제공했지만 PHP는 약간 늦게 지원된 감이 있습니다. 네임스페이스 기능은 PHP의 다양한 오픈소스 프로젝트를 통해 인기를 얻고 있는 기능입니다. 또한 PHP 패키지들을 만들 때 매우 중요하게 사용되는 개념이기도 합니다.

네임스페이스 기능은 PHP 5.3부터 지원됩니다.


### 15.6.1 네임스페이스의 개념

PHP를 포함한 프로그램 언어는 동일한 이름의 클래스명의 중복을 허용하지 않습니다. 즉, 실행 스크립트 안에 클래스명은 유일한 한 개의 이름만 사용 가능합니다. 중복해서 사용할 수 없습니다.

개발자에게 이름을 정의하는 것이란 쉽지 않습니다. 각각의 의미를 부여함과 동시에 실행 스크립트 안에서 동일한 이름이 중복되지 않아야 합니다. 이러한 이름의 규칙은 개발자 한 명일 때는 큰 영향이 없습니다. 만일 다수의 개발자들이 공동으로 대형 프로젝트를 제작할 때 클래스의 이름은 중복될 여지가 있습니다. 하지만 여러 개발자들이 함께 협업하여 만들거나, 공개된 소스들과 결합하기 위해서는 클래스 이름의 중복 문제가 자주 발생하곤 했습니다.

특히 오픈소스 등 다수의 개발자들이 협업하여 만들 때 동일한 클래스 이름 중복으로 충돌이 발생할 가능성이 매우 많습니다. 매번 수많은 개발자들이 클래스 이름을 실시간으로 중복 여부를 확인할 수는 없습니다. 이러한 문제점을 해결하기 위해서 도입된 기능이 가상의 클래스 폴더인 네임스페이스가 있습니다.

 

클래스들은 네임스페이스 형태로 그룹화되어 구분됩니다. 따라서 개발자 및 프로젝트별로 구분할 수 있는 네임스페이스를 각각 가지고 있습니다. 네임스페이스를 적용하면 같은 클래스 이름을 가지고 있다고 해도 서로 충돌하지 않습니다. 하지만 네임스페이스를 적용했다고 해서 실제적인 폴더를 가지거나 구분하지는 않습니다. 네임스페이스는 가상의 폴더 계층 형태로 나누어 관리하기 때문에 공동의 작업이나 소스가 공개된 오픈소스에 매우 유용한 클래스 관리 방법입니다.


### 15.6.2 네임스페이스 문법

네임스페이스를 적용하기 위해서는 PHP 스크립트 상단 <?php 다음에 작성합니다.

|문법|
```
<?php
namespace 이름;
```

namespace 키워드 다음에 이름을 적으면 됩니다. namespace 키워드 다음의 문장은 해당 네임스페이스 경로를 적용받습니다.

네임스페이스는 여러 경로로 계층화할 수 있습니다. 마치 폴더 안에 또 다른 폴더를 만들 수 있는 것과 같습니다. 서브 네임스페이스를 구분하는 방법은 백슬래시 `\`를 사용하면 됩니다.

하지만 통상적으로 네임스페이스를 계층적으로 사용할 때 첫 경로는 ‘벤더명’으로 사용하는 경우가 많습니다. 개발자 또는 소스를 개발한 회사의 이름을 벤더명으로 적을 때가 많습니다.

네임스페이스는 물리적인 폴더 구조로 나누어지지 않기 때문에 실제적으로 1:1 매칭이 되지 않습니다. 하지만 PSR-4 및 오토로딩 도입으로 네임스페이스 클래스를 폴더를 만들어 관리하고 있는 추세로 바뀌고 있습니다.


### 15.6.3 네임스페이스 적용

기존 함수 방식의 코딩을 할 때 두 개 이상의 동일함 함수 이름을 중복하여 사용할 수 없습니다. 이러한 함수명 중복 문제를 해결하기 위한 대안이 클래스라고 할 수 있습니다. 클래스도 선언할 때 PHP 실행 파일 안에서 두 개 이상의 동일한 클래스 이름을 중복하여 사용할 수 없습니다.

클래스의 중복 방지는 네임스페이스를 통해 할 수 있습니다. 네임스페이스가 적용된 클래스는 가상의 개념의 계층이 적용되어 동일한 클래스명도 서로 다르게 인식합니다. 하나의 PHP 실행 파일에서 네임스페이스로 구분된 동일한 클래스들을 동작시킬 수 있습니다.


### 15.6.3.1 전역 네임스페이스
네임스페이스를 적용하기 전에는 일반적으로 클래스를 작성할 때 클래스 키워드와 이름을 선언하고 바로 인스턴스를 생성하여 아래와 같이 사용했습니다.

예제 파일 namespace-01.php
```
<?php
	class members
	{
		public function setUsers($id)
		{
			echo "회원ID = $id";
		}
	}

	$obj = new members();
	$obj->setUsers(123);
?>
```

결과
```
회원ID = 123
```

이처럼 별도의 네임스페이스를 사용하지 않고 클래스(members)를 선언하여 사용하는 것을 전역 네임스페이스로 정의되었다고 표현합니다.


### 15.6.3.2 네임스페이스
다음 소스는 위의 예제 앞에 네임스페이스 키워드를 추가했습니다.

예제 파일 namespace-02.php
```
<?php
	namespace jiny;

	class members
	{
		public function setUsers($id)
		{
			echo "회원ID = $id";
		}
	}

	// 네임스페이스 이름을 같이 적용
	$obj = new \jiny\members();
	$obj->setUsers(123);

	echo "<br>";
	// 현재 네임스페이스를 적용
	$obj2 = new members();
	$obj2->setUsers(123);

?>
```

결과
```
회원ID = 123
회원ID = 123
```

상단에 네임스페이스가 선언되면 네임스페이스명으로 하나의 가상 계층이 생성됩니다. 위 예에서 jiny라는 가상의 계층이 생성되고, 네임스페이스 가상 계층 안에 members 클래스가 선언한다는 것입니다.

동일한 네임스페이스 안에서 클래스 인스턴스를 생성하는 것은 기존 방법과 동일하게 사용할 수 있습니다.

```
$obj = new members();
```

즉 네임스페이스를 넣지 않는 경우 PHP는 이를 현재의 네임스페이스에 의존한다고 간주하는 것입니다.

하지만 네임스페이스를 적용한 클래스에서 호출하기 위해서는 기존에 클래스명 앞에 네임스페이스명 도 같이 넣어야 합니다.

```
$obj = new \jiny\members();
```

new 키워드와 클래스명 사이에 네임스페이스명을 넣어줍니다. 만일 서브 네임스페이스를 가지고 있다고 하면 백슬래시(\)로 네임스페이스\클래스명으로 구분하면 됩니다.

또는 전역으로 클래스를 설정을 하고자 할 때는 다음과 같은 형태로 클래스명 앞에 \를 넣으면 됩니다.

```
$obj = new \members();
```

즉 맨 앞에 \로 시작한다고 하면 루트 디렉터리처럼 전역을 선언하는 것과 같습니다.

예전에 기존 네임스페이스가 도입되기 전에는 클래스명의 중복을 피하기 위해서 클래스명 앞에 접두사를 넣어서 쓰거나 밑줄(_)를 이용하여 구별하여 사용했습니다.

```
기본 방식 => 	jiny_shop_currency   
네임스페이스 => jiny/shop/currency 
```

네임스페이스 기능을 통하여 좀더 계층적이고 익숙한 디렉터리 구조로 소스를 계층화합니다. 마치 폴더를 관리하는 것과 같은 백슬래시(\)를 이용하여 구분할 수 있습니다.

예제 파일 namespace-03.php
```
<?php
	namespace jiny\site;

	class members
	{
		public function setUsers($id)
		{
			echo "회원ID = $id";
		}
	}

	// 네임스페이스 이름을 같이 적용 
	$obj = new \jiny\site\members();
	$obj->setUsers(124);
?>
```

결과
```
회원ID = 123
```


예제 파일 namespace-04.php
```
<?php
	namespace jiny\aaa;

	class members
	{
		public function setUsers($id)
		{
			echo "회원ID = $id";
		}
	}

	
	namespace jiny\bbb;

	class members
	{
		public function setUsers($id)
		{
			echo "회원ID = $id";
		}
	}


	// 네임스페이스 이름을 같이 적용 
	echo "네임스페이스 \jiny\aaa\<br>";
	$obj = new \jiny\aaa\members();
	$obj->setUsers(126);

	echo "<br>";

	// 네임스페이스 이름을 같이 적용
	echo "네임스페이스 \jiny\bbb\<br>";
	$obj2 = new \jiny\bbb\members();
	$obj2->setUsers(127);

?>
```

결과
```
네임스페이스 \jiny\aaa\
회원ID = 126
네임스페이스 \jiny\bbb\
회원ID = 127
```

위의 예를 보면 동일 members 클래스를 네임스페이스를 통해 두 번 선언되어 있습니다. 또한 네임스페이스를 통해 클래스 인스턴스를 생성하여 호출합니다. 

### 15.6.3 클래스 이름 확인
PHP 5.5 이후 버전에서는 class 키워드를 통해 현재의 네임스페이스를 포함한 클래스 이름을 확인할 수 있습니다.

예제 파일 namespace-05.php
```
<?php
	namespace jinyPHP;
    
    class MyClass {
    }
    
    echo MyClass::class;
	
?>
```

결과
```
jinyPHP\MyClass
```

## 15.7 use 키워드

앞에서 학습한 네임스페이스를 이용했습니다. 만일 네임스페이스 명이 길다거나, 서브 네임스페이스명이 많을 때는 클래스 인스턴스 생성 시 길어진 이름으로 인하여 불편한 점이 있었습니다.    


### 15.7.1 use 개념
서브 네임스페이스로 인하여 길어진 이름은 매번 클래스의 인스턴스를 생성하는 데 많은 불편을 주었습니다. 또한 길어진 이름은 소스의 가독성을 떨어뜨리고, 오탈자를 많이 발생합니다. PHP 언어는 별칭 기능을 통해 길어진 네임스페이스명을 짧게 줄여서 사용할 수 있습니다. use 키워드는 길어진 네임스페이스를 별칭으로 치환하는 기능을 제공합니다.  


### 15.7.2 use 문법
use를 통해 네임스페이스 이름을 처리하는 방법으로 두 가지 형태를 제공합니다. 

첫째는 현재 적용되고 있는 네임스페이스의 경로를 변경합니다.

|문법|
```
use 네임스페이스경로;
```

use 명령은 클래스의 인스턴스 생성하기 전에 use 키워드를 통해 별칭을 선언 할 수 있습니다. 

use 네임스페이스경로; 를 적용하면 클래스 인스턴스 선언 시 기존 네임스페이스의 모든 경로를 다 넣지 않아도 클래스의 인스턴스를 간단하게 생성할 수 있습니다.

예제 파일 use-01.php 
```
<?php
	namespace jiny\aaa;

	class Members1
	{
		public function setUsers($id)
		{
			echo "aaa 회원ID = $id";
		}
	}


	namespace jiny2\bbb;

	class Members
	{
		public function setUsers($id)
		{
			echo "bbb 회원ID = $id";
		}
	}


	// 네임스페이스를 aaa로 변경
	echo "네임스페이스를 aaa 변경<br>";
	use jiny\aaa\Members1;

	// 네임스페이스 이름을 같이 적용 
	$obj = new Members1;
	$obj->setUsers(1);
?>
```

결과
```
네임스페이스를 aaa 변경
aaa 회원ID = 1
```

두 번째는 길어진 네임스페이스에 별명 명칭을 적어 사용하는 것입니다.

|문법|
```
use 네임스페이스경로 as 별칭;
```

as 별칭으로 짧은 이름을 새롭게 부여할 수 있습니다. 

 

as 키워드를 이용하면 개발자의 편의에 따라서 별칭을 사용자가 지정할 수 있다는 것이 매우 유용합니다.

예제 파일 use-02.php
```
<?php
	namespace jiny\aaa;

	class members
	{
		public function setUsers($id)
		{
			echo "aaa 회원ID = $id";
		}
	}


	namespace jiny\bbb;

	class members
	{
		public function setUsers($id)
		{
			echo "bbb 회원ID = $id";
		}
	}

	use jiny\aaa as aaa;
	use jiny\bbb as bbb;

	// 네임스페이스 이름을 같이 적용 
	$obj = new aaa\members();
	$obj->setUsers(1);

	echo "<br>";

	// 네임스페이스 이름을 같이 적용 
	$obj = new bbb\members();
	$obj->setUsers(2);
?>
```

결과
```
aaa 회원ID = 1
bbb 회원ID = 2
```

위의 예제에서는 as 키워드를 통하여 jiny\aaa 를 aaa로 별칭을 변경합니다. 별칭으로 작성된 이름으로 클래스를 선언할 수 있습니다.

### 15.7.3 다중 use
여러 개의 네임스페이스를 한 번에 처리할 수 있습니다. 기본적으로 use 명령은 콤마(,)를 통해 다수의 네임스페이스를 하나의 use 명령을 처리할 수 있습니다. 

|문법|
```
use 네임스페이스1,
 네임스페이스2,
 네임스페이스3;
```
하지만 콤마(,)를 이용한 다수의 처리는 코드의 가독성을 줄이고, 오류를 발행할 수 있는 상황을 만들 수 있습니다.

이를 방지하기 위해 use 명령 하나당 네임스페이스 한 개를 적어주는 스타일을 추천합니다. 

|문법|
```
use 네임스페이스1;
use 네임스페이스2;
use 네임스페이스3;
```

### 15.7.3 use 그룹화

위와 같이 한 줄 단위로 use 별칭을 작성하는 것은 불편한 점이 있습니다. 네임스페이스의 클래스를 각각의 use 명령으로 재정의하는 것은 코드 작성에 있어 복잡한 부분이 있었습니다.

```
<?php
// 이전 코드에서는 비슷한 use 명령을 여러 줄을 통해 작성했습니다.
	use some\namespace\ClassA;
	use some\namespace\ClassB;
	use some\namespace\ClassC as C;

	use function some\namespace\fn_a;
	use function some\namespace\fn_b;
	use function some\namespace\fn_c;

	use const some\namespace\ConstA;
	use const some\namespace\ConstB;
	use const some\namespace\ConstC;
?>
```
PHP 7.x로 업그레이드되면서 비슷한 유형끼리 그룹으로 설정할 수 있는 새로운 기능을 추가로 제공합니다.

|문법|
```
<?php
// PHP 7+ code
// PHP 7+ 버전에서는 같은 유형의 use 를 그룹화하여 처리를 할 수 있습니다.
<?php

	use some\namespace\{
		ClassA, 
		ClassB, 
		ClassC as C
	};
	
	use function some\namespace\{
		fn_a, 
		fn_b, 
		fn_c
	};
	
	use const some\namespace\{
		ConstA, 
		ConstB, 
		ConstC
	};
?>
```
같은 유형의 그룹은 위의 예처럼 중괄호를 이용하여 처리할 수 있습니다. 코드를 가독화하고 읽기 쉽게 만들어 사용할 수 있습니다.






# 17. 오류 및 예외 처리

프로그램을 개발하다 보면 수많은 오류와 예외가 발생합니다. 보통 오류는 크게 코드상의 문법 오류와 소스상의 논리적인 오류로 구분할 수 있습니다. 문법적 오류는 PHP가 시작하기 전에 체크하여 알려주기 때문에 쉽게 문법적 오류를 해결할 수 있습니다. 하지만 논리적인 오류는 쉽게 찾을 수 있는 오류가 아닙니다. 또한 이러한 문제로 인해 프로그램은 정상적인 동작을 수행하지 못하고 중간에 중단되기도 합니다.

개발자는 오류 및 예외 메시지가 발생하면 잘못된 부분을 인지하고, 문제를 해결하기 위해 노력합니다. 이러한 오류와 예외 처리가 미흡하면 다수의 잘못된 메시지가 사용자에게 출력되거나 불편함을 줄 것 입니다. 논리적인 오류는 개발자들에게 많은 디버깅 시간을 투여하게 만들도록 합니다.

그렇다고 해서 발생한 오류 메시지를 화면에 출력하면 프로그램의 완성도에 대한 신뢰를 떨어뜨릴 수 있습니다.

개발의 기술이 높아지고 경험이 많을수록 개발자는 PHP 오류와 예외를 예측하여 처리해야 합니다.

 
## 17.1 오류

사실 기본적인 오류 처리는 대부분의 프로그래밍 언어에서는 거의 다 지원하는 기능입니다.

우리가 가장 많이 접하는 오류는 문법적으로 코드가 잘못 작성되었을 때입니다. 인터프리터, 컴파일러는 잘못된 부분을 오류 메시지를 통해 개발자에게 즉시 알려 줍니다. 사실상 문법적인 오류는 PHP 스크립트 실행이 되지 않기 때문에 쉽게 문제를 해결할 수 있습니다.

PHP의 기본적인 문법 오류 처리는 매우 간단합니다. 오류 메시지, 파일 이름, 줄 번호를 출력하는 게 전부입니다. 오류가 발생하면 대부분 프로그램은 실행을 할 수 없거나, 동작을 중단합니다. 
  
PHP는 오류 출력 제한 연산자 @를 통해 오류 메시지 출력을 제한할 수 있지만 권장하지 않는 안티 패턴입니다. 개발자는 프로그램 오류가 발생하지 않도록 최대한 노력해야 하며, 만일 오류가 발생하면 다른 대처를 통해 처리하는 것이 좋습니다.

PHP는 오류 발생 시 처리할 수 있는 간단한 몇 가지 함수를 제공합니다.

### 17.1.1 die() & exit() 

die() 내장 함수는 exit() 함수와 유사합니다. exit() 함수는 사용자 메시지를 출력하고 현재 스크립트를 종료합니다. 

|관련함수|
```
void exit ([ string $status ] )
```

예제 파일 exit-01.php
```
<?php

	$filename = 'abcd.txt';
	$file = fopen($filename, 'r') or exit("파일을 읽을 수 없습니다.");

?>
```

결과
```
파일을 읽을 수 없습니다.
```

위의 예제는 파일 읽기 예입니다. 파일을 읽기 위해서 파일 포인터를 엽니다.  
만일 파일 포인터를 생성하지 못면 exit() 함수를 통해서 스크립트를 종료합니다.

### 17.1.2 오류 발생 

trigger_error() 함수를 이용하면 사용자가 직접 오류를 발생시킬 수 있습니다.

예제 파일 error-01.php
```
<?php
	trigger_error("사용자 오류 발생", E_USER_ERROR);
?>
```

결과
```
[Sun May 14 17:24:40 2017] PHP Fatal error: 사용자 오류 발생 in C:\php-7.1.4-Win32-VC14-x86\jinyphp\error-01.php on line 2
[Sun May 14 17:24:40 2017] ::1:56024 [500]: /jinyphp/error-01.php - 사용자 오류 발생 in C:\php-7.1.4-Win32-VC14-x86\jinyphp\error-01.php on line 2
```

E_* 상수는 여러 개의 상수를 |, & 비트 연산을 하여 사용할 수 있습니다.

* 1 : E_ERROR(integer)
치명적인 런타임 오류. 이는 메모리 할당 문제와 같이 복구할 수 없는 오류를 나타냅니다. 스크립트 실행이 중지되었습니다.
 
* 2 : E_WARNING(integer)
런타임 경고(치명적이지 않은 오류). 스크립트의 실행이 중지되지 않습니다.
 
* 4 : E_PARSE(integer)
컴파일 타임 구문 분석 오류. 구문 분석 오류는 구문 분석기에서만 생성해야 합니다.

* 8 : E_NOTICE(integer)
런타임 고지. 스크립트가 오류를 나타낼 수 있지만 스크립트를 실행하는 정상적인 과정에서 발생할 수 있음을 나타냅니다.
 
* 16 : E_CORE_ERROR(integer)
PHP가 처음 시작될 때 발생하는 치명적인 오류. 이것은 E_ERROR와 비슷하지만, PHP 코어에서 생성된다는 점만 다릅니다.
 
* 32 :E_CORE_WARNING(integer)
PHP가 처음 시작될 때 발생하는 경고(치명적이지 않은 오류). 이것은 E_WARNING과 비슷하지만 PHP 코어에서 생성된다는 점만 다릅니다.
 
* 64 : E_COMPILE_ERROR(integer)
치명적인 컴파일 타임 오류. 이것은 Zend Scripting Engine에 의해 생성된다는 것을 제외하고는 E_ERROR와 같습니다.
 
* 128 : E_COMPILE_WARNING(integer)
컴파일 타임 경고(치명적이지 않은 오류). 이것은 Zend Scripting Engine에 의해 생성된다는 점을 제외하고는 E_WARNING과 같습니다.
 
* 256 : E_USER_ERROR(integer)
사용자 생성 오류 메시지. PHP 함수 trigger_error ()를 사용하여 PHP 코드에서 생성된다는 점을 제외하고는 E_ERROR와 유사합니다.
 
* 512 : E_USER_WARNING(integer)
사용자 생성 경고 메시지. 이것은 PHP 함수 trigger_error ()를 사용하여 PHP 코드에서 생성된다는 점을 제외하고는 E_WARNING과 같습니다.
 
* 1024 : E_USER_NOTICE(integer)
사용자 생성 알림 메시지 PHP 함수 trigger_error ()를 사용하여 PHP 코드에서 생성된다는 점을 제외하고는 E_NOTICE와 같습니다.
 
* 2048 : E_STRICT(integer)
PHP가 코드의 변경을 제안하도록 하여 최상의 상호 운용성과 코드의 호환성을 보장하십시오.

* 4096 : E_RECOVERABLE_ERROR(integer)
잡을 수 있는 치명적인 오류. 아마도 위험한 오류가 발생했음을 나타내지만 엔진을 불안정한 상태로 두지 않았습니다. 사용자 정의 핸들(set_error_handler () 참조)이 오류를 catch하지 않으면 응용프로그램은 E_ERROR이므로 중단됩니다.

* 8192 : E_DEPRECATED(integer)
런타임 고지. 향후 버전에서 작동하지 않을 코드에 대한 경고를 받으려면 이 옵션을 활성화.

* 16384 : E_USER_DEPRECATED(integer)
사용자 생성 경고 메시지. PHP 함수 trigger_error ()를 사용하여 PHP 코드에서 생성된다는 점을 제외하고는 E_DEPRECATED와 같습니다.

* 32767 : E_ALL (integer)
PHP 5.4.0 이전의 레벨 E_STRICT를 제외하고 지원되는 모든 오류 및 경고.
PHP 5.4.x에서 32767, PHP 5.3.x에서 30719, PHP 5.2.x에서 6143, 이전에 2047 코드번호.


### 17.1.3 커스텀 에러 핸들러 

사용자 에러 핸들러는 매우 간단하게 생성할 수 있습니다. 단지 오류가 발생되었을 때 사용할 별도의 함수를 만들어 놓으면 됩니다.

이 함수는 적어도 2개의 파라미터를 가지고 있어야 합니다. 바로 오류 레벨과 메시지입니다. 매개변수는 최대 5개까지 추가할 수 있습니다. 사용자 에러 처리 함수를 set_error_handler() 함수를 통해 전역 오류 처리기로 등록할 수 있습니다.

|관련함수|
```
오류 처리_함수($errno, $errstr, $errfile, $errline, $errcontext)
set_error_handler(오류 처리_함수);
```

$errno
오류 단계를 대응합니다. PHP E_* 상수를 대응합니다.

$errstr
오류 메시지

$errfile
오류가 발생된 파일명

$errLine
오류가 발생된 명령줄

$errcontext
오류가 발생된 시점의 심볼 테이블 배열


예제 파일 error-02.php
```
<?php
	function userError($errno, $errstr){
		echo "사용자 오류 처리: [$errno] = $errstr <br>";
	}
	set_error_handler("userError");

	trigger_error("사용자 오류 발생", E_USER_ERROR);
?>
```

결과
```
사용자 오류 처리: [256] = 사용자 오류 발생
```

위의 예제는 사용자 오류 처리를 위한 예입니다. 먼저 오류 발생 시 처리할 함수를 생성합니다. 생성한 처리 함수를 set_error_handler() 함수를 통해 등록합니다. 그리고 사용자가 직접 오류를 발생하여 앞서 지정한 오류 처리 함수가 동작을 하는지 테스트할 수 있습니다.


## 17.2 예외
예외라는 말은 프로그램 실행 도중 예상치 않은 동작이나 불확실한 처리로 발생할 수 있는 부분을 예상하여 오류까지도 같이 처리를 하는 코딩 방법입니다. try{} catch {}의 문법과 별도의 예외 처리를 위한 클래스 등이 존재합니다.

예외 처리는 PHP스크립트가 실행하면서 오류가 발생했을 때 처리할 수 있는 로직을 만들어 넣을 수 있는 기술입니다. 예외 처리 개념은 PHP 5.x 이전에는 도입되지 않았습니다.

오류의 경우는 프로그램의 문제가 발생하면 오류를 통보하고 프로그램이 중단됩니다. 하지만, 예외는 갑작스러운 오류 발생 시 스크립트를 그냥 종료하는 것이 아니라 별도의 처리 루틴을 통해 안전하게 프로그램을 마칠 수 있도록 합니다.


### 17.2.1 Exception 클래스
PHP는 예외 처리를 위해서 특별한 Exception 클래스를 제공합니다. 예외 처리 클래스는 예외 발생 시 심각한 오류를 안전한 경로로 우회하여 처리할 수 있도록 도와줍니다.

예외 처리 클래스 Exception도 new 키워드를 통해 인스턴스를 생성하여 사용할 수 있습니다. Exception 클래스는 오류 코드와 메시지를 전달하고 값을 처리할 수 있는 추가 메서드를 지원합니다.

예제 파일 exception-01.php
```
<?php
	$msg = "예외 클래스 오류 발생";
	$code = 444;
	$e = new Exception($msg,$code);

	echo "예외 코드 = ".$e->getCode();
	echo "<br>";
	echo "예외 메시지 = ".$e->getMessage();
?>
```

결과
```
예외 코드 = 444
예외 메시지 = 예외 클래스 오류 발생
```

예외 Exception 클래스 구조와 인터페이스는 다음과 같습니다.

```
Exception {
/* Properties */
protected string $message ;
protected int $code ;
protected string $file ;
protected int $line ;

/* Methods */
public __construct ([ string $message = "" [, int $code = 0 [, Throwable $previous = NULL ]]] )
final public string getMessage ( void )
final public Throwable getPrevious ( void )
final public mixed getCode ( void )
final public string getFile ( void )
final public int getLine ( void )
final public array getTrace ( void )
final public string getTraceAsString ( void )
public string __toString ( void )
final private void __clone ( void )
}
```

예외 처리가 발생하면 PHP 엔진은 Exception 클래스로 예외를 발생한 부분을 처리하게 됩니다.

PHP 7.x에서는 Exception 클래스는 throwable 인터페이스를 따릅니다.

```
Throwable {
/* Methods */
abstract public string getMessage ( void )
abstract public int getCode ( void )
abstract public string getFile ( void )
abstract public int getLine ( void )
abstract public array getTrace ( void )
abstract public string getTraceAsString ( void )
abstract public Throwable getPrevious ( void )
abstract public string __toString ( void )
}
```

### 17.2.2 throw

throw 키워드를 이용하여 사용자가 직접 예외를 발생할 수 있습니다. 예외가 발생하면 PHP는 코드 실행을 중지됩니다.

throw 키워드는 Exception과 관련 서브 클래스에서만 사용이 가능한 키워드입니다. 

●	Exception
●	ErrorException

예제 파일 exception-02.php
```
<?php
	throw new Exception("강제적 예외 발생");
?>
``

결과
```
[Sun May 14 16:21:35 2017] ::1:55806 [500]: /jinyphp/exception-02.php - Uncaught Exception: 강제적 예외 발생 in C:\php-7.1.4-Win32-VC14-x86\jinyphp\exception-02.php:2
Stack trace:
#0 {main}
thrown in C:\php-7.1.4-Win32-VC14-x86\jinyphp\exception-02.php on line 2
```

위의 예제는 예외 발생 처리 예입니다. throw 명령으로 사용자가 직접 예외를 발생할 수 있습니다.

### 17.2.3 Exception 상속

예외 처리 Exception 클래스를 상속받아 새로운 에외 처리 클래스를 직접 만들어서 사용할 수도 있습니다. 새로운 예외 처리는 클래스는 기존의 exception 함수를 상속받아서 생성을 합니다.

|문법|
```
class divException extends exception {}
```

예제 파일 exception-03.php
```
<?php
	class aaaEx extends exception
	{
		public function showErr($msg)
		{
			echo $msg;
		}
	}

	$msg = "예외 클래스 오류 발생";
	$code = 444;
	$e = new aaaEx($msg,$code);

	$e->showErr("Exception을 상속합니다.");
	echo "<br>";
	echo "예외코드 = ".$e->getCode();
	echo "<br>";
	echo "예외메시지 = ".$e->getMessage();
?>
```

결과
```
Exception을 상속합니다.
예외 코드 = 444
예외 메시지 = 예외 클래스 오류 발생
```

위의 예제는 예외 처리 클래스 상속에 대한 예입니다. 기존 exception 예외 클래스를 상속받아 새로운 예외 처리 클래스를 만들어서 사용할 수 있습니다.

### 17.2.4 예외 포착
개발자는 예외 처리에 대해서 수동적인 방어 보다는 능동적인 방어가 필요합니다. 적극적으로 예외가 발생될 것을 예측하여 프로그램 코드를 작성해야 합니다.

PHP 언어는 예외를 포착할 수 있는 try ~ catch 명령 키워드를 제공합니다. try~catch는 C++이나 Java 등에서 일찌감치 예외 처리를 위해 사용하던 문법입니다. PHP 5.x 이후부터는 이와 비슷한 스타일로 예외 처리 문장을 만들 수 있습니다.

프로그램이 동작할 때 예외가 발생할 가능성이 있다고 하면 try {} catch {} 명령으로 예외 발생을 대비하는 것이 좋습니다.

 

try~catch는 2개의 영역으로 나누어져 있습니다.

|문법|
```
try {
	예외가 발생할 가능성이 있는 내용들을 코딩합니다.
} catch (클래스명 $변수명) {
	예외가 발생될 경우 처리할 내용들
}
```


#### try { } 부분
try 본문 안에는 예외가 발생될 가능성이 높은 코드를 작성하는 영역입니다. 특별한 코드가 이니라 정상적으로 수행하고자 하는 코드를 작성합니다. 만일 이 코드들이 예외를 발생할 여지가 있는 경우 try{} 로 코드를 감싸서 실행하는 것입니다.

오류 예외가 발생되지 않으면 큰 문제나 의미 없이 코드가 실행될 것입니다. 만일 try 안에 있는 코드에 예외가 발생하면 코드 실행을 중단하게 됩니다. 그리고 catch 부분의 코드를 수행합니다.

#### catch {} 부분
catch (클래스명 $변수명) { }은 try{} 본문에 예외가 포착되었을 때 처리되는 내용들입니다.

예외가 발생할 때 Excetion 클래스를 통해 예외 상태나 메시지를 받아올 수 있습니다. Exception 클래스는 예외를 처리할 수 있는 다양한 프로퍼티와 메서드를 가지고 있습니다.

|문법|
```
catch(Exception $err){
	echo $err->getMessage();
} 
```

예외 발생 시 Exception 클래스로 생성된 인스턴스를 받습니다. 생성된 인스턴스로 Exception 메서드를 실행할 수 있습니다.

예제 파일 exception-04.php
```
<?php
	try {
	
		throw new Exception("강제적 예외 발생");

	} catch(Exception $err){
		// Try {} 부분에 연산 오류로 인하여 예외 처리가 발생됨
		echo "예외 처리 발생 :".$err->getMessage();
	} 
?>
```

결과
```
예외 처리 발생: 강제적 예외 발생
```

위의 예제는 try~catch 동작에 대한 예입니다. try {} 본문 안에서 강제적으로 throw 명령을 통해 개발자가 직접 예외를 발생합니다. 예외가 발생되면catch{} 안의 내용이 실행됩니다. catch 실행 시 예외 처리 클래스 exception 객체를 동시에 생성하여 catch 내부로 전달합니다.

catch 내에서는 exception 클래스로 생성된 객체를 접근하여 메시지 및 상태를 체크할 수 있습니다.

### 17.2.5 다중 catch
만일 예외 처리의 유형이 다양한 경우 catch를 연결하여 사용 가능합니다.

|문법|
```
try {
	예외가 발생할 가능성이 있는 내용들을 코딩합니다.
} catch (클래스명 $변수명) {
	예외가 발생될 경우 처리할 내용들
} catch (클래스명 $변수명) {
	예외가 발생될 경우 처리할 내용들
}
```

catch는 위의 표현처럼 계속 체인 형태로 연결하여 사용할 수 있습니다.

예제 파일 exception-05.php
```
<?php
	try {
		$servername = "localhost";
		$dbname = "testDB";
		$username = "jiny";
		$pasword = "abcd1234";

		$conn = new PDO("mysql:host=$servername;dbname=$dbname", $username, $password);
	
	} catch (PDOException $e) {
		echo "PDO 오류";

	} catch (Exception $e) {
		echo "일반예외";
	}
?>
```

결과
```
PDO 오류
```

위의 예제는 다수의 catch 처리를 위한 실험입니다. 예외가 발생되면 예외 상태에 따라서 상항별로 catch 로 분기하여 처리됩니다.
 

### 17.2.6 finally

finally { } 부분은 PHP 5.5에서 도입된 기능으로 try 부분이나 catch부분 처리가 끝나고 처리할 내용을 추가로 정의할 수 있습니다. finally {}는 독립적으로 사용을 할 수 없고 반드시 try ~ catch문 뒤에 소속되어 사용 가능합니다. 즉, 종속된 기능 명령어 입니다.

사용 문법
```
try {
	예외가 발생할 가능성이 있는 내용들을 코딩합니다.
} catch (클래스명 $변수명) {
	예외가 발생될 경우 처리할 내용들
} finally {
	예외 발생 여부와 상관없이 처리할 내용
}
```

예제 파일 exception-06.php
```
<?php
	try {
	
		throw new Exception("강제적 예외 발생");

	} catch(Exception $err){
		// Try {} 부분에 연산오류로 인하여 예외 처리가 발생됨
		echo "예외 처리 발생 :".$err->getMessage();
	} finally {
		// try {} 또는 catch(){} 부분의 처리 후에 처리가 됩니다.
		echo "<br>";
		echo "finally 연산 종료";
	}
?>
```

결과
```
예외 처리 발생: 강제적 예외 발생
finally 연산 종료
```

위의 예제는 final 에 대한 예입니다. 예외가 발생하면 catch 부분을 수행합니다. 그리고 catch 부분을 처리 후에 finally {} 부분을 실행합니다.


### 17.2.7 전역 예외 처리
try~catch로 처리하지 못한 예외가 있을 수도 있습니다. 이런 경우 전역 예외 처리를 통해 예상치 못한 예외도 포착할 수 있습니다.

|관련함수|
```
callable set_exception_handler ( callable $exception_handler )
```

`set_exception_handler();` 내장 함수를 통하여 전역 예외 처리를 등록할 수 있습니다.

|관련함수|
```
bool restore_exception_handler ( void )
```

`restore_exception_handler();` 내장 함수는 설정한 전역 처리기를 복원합니다.


예제 파일 exception-07.php
```
<?php
	// 전역 예외 처리기를 등록합니다.
	set_exception_handler(function(Exception $e){
		echo "전역 예외 처리 포착<br>";
		echo "예외 메시지 = ".$e->getMessage();
	});

	throw new Exception("강제적 예외 발생");

	// 설정한 전역 처리기를 복원합니다.
	restore_exception_handler();
?>
```

결과
```
전역 예외 처리 포착
예외 메시지 = 강제적 예외 발생
```

위의 예제는 전역 예외 처리에 대한 예입니다. set_exception_handler() 함수를 통해 적역 예외 처리 함수를 등록합니다.

