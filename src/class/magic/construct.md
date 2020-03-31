---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "class"
- "Magic Method"
- "construct"
---

# 초기화
<hr>
`__construct()` 메서드는 객체 생성 시 초기값 설정을 해주는 특수 메서드입니다. 또는 생성자 메서드라고도 부릅니다.  

```php
$obj = new members();
```

다음과 같이 클래스 인스턴스를 생성할 때 __construct() 메서드는 한 번 실행하게 됩니다. 이 메서드명은 미리 정의된 이름입니다.  

__construct() 메서드를 사용하기 위해서는 클래스 내에 선언해야 합니다.  

|문법|
```php
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

예제 파일 class-12.php
```php
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


생성자는 항상 코드를 종속적으로 만들게 된다

생성패턴은 객체의 생성자를 보완하게 하는 패턴들의 모임입니다.

<br><br>