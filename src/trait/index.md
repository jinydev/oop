---
layout: page
title: "PHP"
keyword: "jinyphp, php, 객체지향, oop, class"
---
### 15.5 트레이트
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

 
<br>
<hr>

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

<br>
<hr>

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

<br>
<hr>

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

<br>
<hr>

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

<br>
<hr>

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

<br>
<hr>

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

<br>
<hr>

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

<br>
<hr>

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
<br><br>