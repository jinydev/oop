---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "class"
- "Masic Method"
- "toString"
---

# 객체의 문자열 변환
<hr>

__toString() 매직 매서드는 클래스가 문자열로 변환하여 처리될 때 동작합니다. 예로 클래스 객체를 echo $obj;처럼 출력할 때 __toString() 메서드가 동작합니다.  

예재 파일 class-15.php
```php
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