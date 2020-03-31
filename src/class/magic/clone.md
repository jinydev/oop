---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "Class"
- "Masic Method"
- "Clone"
---

# 객체 복제 호출
<hr>

`__clone()` 매직 메소드는 객체가 복제 되었을 때 실행회는 메서드입니다.  

예제파일) class-17.php
```php
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

화면출력)
```
clone object
```

<br><br>