---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "class"
- "Masic Method"
- "destruct"
---

# 소멸자
<hr>

`__construct()` 처럼 초기화 메서드가 있다고 한다면 반대로 소멸자 매직 메서드가 존재합니다.  

PHP 스크립트의 모든 소스가 실행 끝나고 나면 `__destruct()` 메서드 함수가 실행됩니다.  

|문법|
```php
class 클래스명
{
	function __destruct()
	{
		// 소멸 작업들을 설정합니다.
	}
}
```

예제 파일 class-13.php
```php
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

위의 예제는 클래스의 인스턴스를 생성과 스크립트 종료와 함께 `__destruct()` 매직 메서드가 호출됩니다.  
