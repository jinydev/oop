---
layout: page
title: "객체지향 프로그래밍"
keyword: "jinyphp, php, 객체지향, oop, class"
---

PHP4-Doc Comments

02. PHPDoc 블록
====================

프로그램의 완전 처음배우는 독자가 아니라면 언어에서 제공하는 주석의 개념을 잘 알고 있을 것입니다.

PHP는 소스의 가독성과 이해를 쉽게 하기 위해서 주석 기능을 제공합니다. PHP주석 또한 다른 언어들과 유사하게 한 줄 처리 주석 // 과 여러 줄 처리 주석 /* */ 두가지 모두 지원을 합니다.

주석은 소스코드의 이해를 돕고, 여러 사람들과 코드를 공유함과 동시에 설명을하는데 매우 유용한 시스템입니다. 경험이 많은 개발자 일수록 주석문을 잘 사용을 합니다.

02.1 주석
====================

PHP는 일반적인 코드설명 주석보다 좀더 향상된 주석 시스템을 제공합니다. 
일반적으로 여러 줄의 주석문을 작성하는 /*와 유사하지만, /**로 시작을 합니다.
이를 다른 이름으로 PHP Docs라고 합니다.

PHP는 이렇게 소스 코드내에 작성한 주석문을 스스로 읽어서 검사를 할 수 있는 특별한 클래스를 제공합니다. 소스코드의 주석을 분석하여 코드의 메타 데이터를 생성합니다.


02.2 Doc 주석 예제
====================
그럼 소스코드 내에서 주석을 이용한 메타데이터 표기하는 방법에 대해서 알아보도록 합니다.

다음은 클래스 내에서 PHP Docs를 적용한 예제 파일 입니다.
예제파일: meta_01.php
<?php
class Controller
{
	/**
	* @readwrite
	*/
	protected $_view;

	/**
	* @once
	*/
	public function authenticate()
	{
		// 코드작성부분
	}
}

위의 파일에는 하나의 클래스가 선언이 되어 있습니다. 클래스는 프로퍼티와 매소드가 하나씩 선언되어 있습니다. 이와 같이 /**로 표기되 주석을 가지고 있습니다.

선언한 $_view 프로퍼티 변수는 protected 속성으로 설정되어 외부에서 접근을 할 수는 없습니다. 별도의 getter/setter를 만들어 같이 사용할 것입니다. 또한 프로퍼티를 특별하게 읽기/쓰기/읽기쓰기 등의 특별한 용도로  제한을 하고 싶을 경우도 있을 것입니다.

이때, Doc 주석을 통하여 속성을 추가로 지정할 수 있습니다. 추가 속성을 통하여프로퍼티의 접근과 동작을 제어할 수 있습니다.

메소드도 호출과 실행을 제한할 수 있는 속성을 부여 하고 싶을 경우도 있을 것입니다. Doc 주석을 이용하여 매소드를 이전에 실행된 것을 확인하여 중복실행이 되지 않도록 제한할 수도 있습니다.

이처럼 주석을 통하여 메타 데이터를 생성하고 효과적으로 적요할 수 있습니다.


02.3 Inspector
이처럼 추가적인 속성을 주석으로 통하여 지정을 할 수 있습니다. 소스코드안에 있는 주석을 통하여 메타데이터를 생성합니다. 메타데이터는 키와 값을 한쌍으로 가지고 있습니다.

주석을 통하여 메타 데이터를 추출하기 위해서는 별도의 처리 로직이 필요로 합니다. 이러한 처리 로직을 Inspector라고 합니다.

Inspector 처리 로직은 소스 코드내에서 주석 내용을 읽어 올수 있는 특별한 크래스 ReflectionClass를 사용합니다. 다음 예제는 Inspector 처리를 위한 예제 입니다. 

예제코드: inspector.php
namespace Framework
{
use Framework\ArrayMethods as ArrayMethods;
use Framework\StringMethods as StringMethods;

class Inspector
{
protected $_class;
protected $_meta = array(
"class" => array(),
"properties" => array(),
"methods" => array()
);
	
protected $_properties = array();
protected $_methods = array();

public function __construct($class)
{
$this->_class = $class;
}

protected function _getClassComment()
{
$reflection = new \ReflectionClass($this->_class);
return $reflection->getDocComment();
}
	
protected function _getClassProperties()
{
$reflection = new \ReflectionClass($this->_class);
return $reflection->getProperties();
}
	
protected function _getClassMethods()
{
$reflection = new \ReflectionClass($this->_class);
return $reflection->getMethods();
}
	
protected function _getPropertyComment($property)
{
$reflection = new \ReflectionProperty($this->_class, $property);
return $reflection->getDocComment();
}

protected function _getMethodComment($method)
{
$reflection = new \ReflectionMethod($this->_class, $method);
return $reflection->getDocComment();
}

}
}

PHP의 리플렉션 클래스는 Doc 주석의 문자열을 가지고 올 수 있습니다.


클래스의 속성 및 매서드 목록을 가지고 옵니다.

만일 문자열값만 읽어오기를 원한다면 _getClassComment (), _getPropertyComment () 및 _getMethodComment () 메서드를 public으로 만들 수 있습니다.





02.4 _parse()추가
PHP 주석 구분을 분석하기 위한 _parse() 매소드를 Inspector 클래스 안에 하나더생성을 합니다.

protected function _parse($comment)
{
$meta = array();
$pattern = "(@[a-zA-Z]+\s*[a-zA-Z0-9, ()_]*)";
$matches = StringMethods::match($comment, $pattern);
			
if ($matches ! = null) {
foreach ($matches as $match) {
$parts = ArrayMethods::clean(
ArrayMethods::trim(
StringMethods::split($match, "[\s]", 2)
)
);

$meta[$parts[0]] = true;
if (sizeof($parts) > 1) {
$meta[$parts[0]] = ArrayMethods::clean(
ArrayMethods::trim(
StringMethods::split($parts[1], ",")
)
);
}
}
}

return $meta;
}





내부 _parse () 메소드는 매우 간단한 정규식을 사용하여 키 / 값 쌍을 일치시킵니다.

_get ... Meta () 메소드에 의해 리턴 된 Doc Comment 문자열 내. 이 작업은 StringMethods :: match () 메서드를 사용하여 수행합니다.

모든 경기를 반복하며 키 / 값으로 나눕니다.

값 구성 요소를 찾지 못하면 키 값을 true로 설정합니다. @readwrite 또는 @once와 같은 플래그 키에 유용합니다.

값 구성 요소를 찾으면 값을 나눈 값 배열을 키에 할당합니다.

마지막으로 키 / 값 연상 배열을 반환합니다.

이러한 내부 메소드는 코드 2-12의 public 메소드에 의해 사용되며, 구문 분석 된 Doc Comment 문자열 데이터를 리턴하는 데 사용될 것이다.






02.1 PHP Documentor 시작하기



PHP는 소스상에 있는 /** 로 시작하는 코드를 추가하고 구분할 수 있습니다.
주로 메소드나 프로퍼티에 적용하여 같이 많이 사용합니다.

@param
@throws
@return
@var 
등 여러종류가 있습니다.



PHPDoc 블록은 Inspector 기능을 구현을 통하여 주석문장을 인식합니다.



====


<?php
include "ArrayMethods.php";
include "StringMethods.php";
include "Inspector.php";

include "Base.php";

class Car extends Framework\Base
{
/**
* @readwrite
*/
protected $_color;

/**
* $write
*/
protected $_model;
}

$car = new Car();

// 프러퍼티 $_color에 값을 설정합니다.
$car->setColor("Red");

// 설정한 프로퍼티의 값을 읽어옵니다.
echo $car->getColor();

필요한 클래스파일들을 먼저 include로 결합을 합니다. 
클래스 Car는 Framework\Base를 상속받습니다. Protected로 설정된 프로퍼티 $_color에 값을 설정을 합니다. 하지만 $_color는 외부 접근이 제한되어 있습니다.

접근을 시도할 경우 Framework\Base의 __call() 매직 메서드가 호출하게 됩니다. Framework\Base 클래스는 초기화로 Inspector 클래스의 인스턴스를 하나 미리 만들어 놓습니다.











