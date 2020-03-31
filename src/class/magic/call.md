---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "class"
- "Masic Method"
- "call"
---

# 오류 호출(__call)
<hr>

매서드를 사용하기 위해서는 반드시 클래스 내에 매서드 함수를 정의해야 합니다. 하지만 정의되지 않는 클래스를 사용하려고 하면 당연히 오류가 발생할 것입니다. 공동 작업이나 소스가 커질수록 이러한 오류가 발생할 확률도 커집니다.  

만일 클래스 내에서 존재하지 않는 메서드를 호출할 때 오류를 발생하지 않고 __call() 메서드를 호출합니다.   

예제 파일 class-### 14.php
```php
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

<br><br>