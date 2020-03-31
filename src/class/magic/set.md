---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "class"
- "Magic Method"
- "set,get"
---

# __set(), __get(), __isset(), __unset()
<hr>

__set() 매직 메서드는 접근할 수 없는 프로퍼티에 값을 쓰고자 할 때 호출됩니다. __get() 매직 메서드는 접근할 수 없는 프로퍼티의 값을 읽을 경우에 호출됩니다. __isset() 매직 메서드는 접근할 수 없는 프로퍼티에 isset() 함수나 empty() 함수를 사용할 때 호출됩니다. __unset() 매직 매서드는 접근할 수 없는 프로퍼티를 unset() 함수를 사용할 때 호출됩니다.  

예제 파일 class-18.php
```php
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
