---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "class"
- "Masic Method"
- "invoke"
---


# 객체 함수 호출
<hr>

__invoke() 매직 메서드는 객체를 함수처럼 호출할 경우에 호출되는 메서드 입니다. $obj() 형태로 호출될 때 실행됩니다.  

예제파일) class-16.php
```php
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

화면출력)
```
int(5) bool(true)
```