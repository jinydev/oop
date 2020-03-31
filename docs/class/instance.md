


### 인스턴스
---
클래스를 통하여 인스턴스 객체를 생성합니다. 인스턴스는 클래스 `설계도`에 따라서 인스턴스를 생성하게 됩니다. 

마치 붕어빵의 틀과 붕어빵과 같습니다.

인스턴스의 사전적 의미는 "경우"입니다. 클래스에 정의된 내용대로 생성을 하게 됩니다.
인스턴스가 생성이 되게 되면 시스템 메모리를 할당하게 됩니다.
인스턴스는 클래스를 통하여 하나가 아닌 여러개를 시스템 메모리의 한도 안에서 무제한 적으로 생성할 수 있습니다.

인스턴스와 객체는 동일합니다. 동일한 용어 입니다.

클래스는 인스턴스, 객체를 생성하는 `설계도`가 됩니다.


인스턴스를 생성하는 방법은 `new`키워드를 사용하는 것입니다.

```php
$변수 = new 클래스명 
```

위와 같이 사용을 할 수 있습니다.


#### 생성자 construct
클래스는 특수한 메소드가 존재합니다. 

클래스를 생성할때 `()`를 통하여 인자값을 전달 할 수 있습니다. 이 인자값은 초기 생성자를 통하여 이 값을 받아 처리를 할 수 있습니다.

PHP는 생성자로 `__construct()` 메소드를 가지고 있습니다. 다른 말로 `매직 메서드`라고도 부르기도 합니다.

클래스가 동작을 하면서, 초기화 작업들이 필요한 경우 매직 생성자 메서드를 사용하는 것은 매우 유용합니다.


[] 생성자 매직 메서드가 동작을 하기위해서는 인스턴스화를 통하여 실제적인 객체로 생성을 하여야 합니다.
즉 `new`키워드를 통하여 객체의 생성이 되지 않으면 안됩니다.

정적 호출을 통하여 클래스를 접근할때는 별도의 초기화 작업을 할 수 있는 루틴을 만들어 호출하는 것이 좋습니다.





#### 소멸자
생성자와 반대로 소멸자가 있습니다.


### 인스턴스 맴버와 공유멤버
---
클래스에서 정의한 프로퍼티는 인스턴스 생성시 `변수`와 같습니다. 이렇게 프로포티를 작성하게 되면 데이터 필드를 가지고 됩니다.
이를 인스턴스 맴버라고 합니다.

만일 인스텀스 맴버 변수를 초기화가 필요할 겨우 매직 초기화 매서드를 사용할 수 있습니다.

인스턴스를 생성성하게 되면, 자기 자신을 가를키는 `this` 키워드를 사용할 수 있습니다. `$this` 변수는 자기 자신의 인스턴스 를 말합니다.


만일 인스턴스를 생성하지 않은 ststic 의 경우에는 `self`를 사용할 수 있습니다.


인스턴스를 생성하게 되면 각각의 맴버변수들이 생성이 됩니다. 만일 여러개의 인스턴스를 생성하여 처리할 경우, 여러개의 인스턴스가 처리해야 되는 공유의 변수값이 필요한 경우가 있습니다.
이런경우 `공유 맴버변수`가 필요할 수 있습니다.

공유멤버 변수의 경우 UML 상에서 `밑줄`을 추가합니다. 공유 맴버는 별도의 인스턴스로 분리되어 관리가 됩니다.

공유맴버는 `static` 키워드를 사용합니다. 또한, 초기화도 가능합니다.

#### static method
---
`static` 메서드는 인스턴스를 생성한 경우에는 접근을 할 수 없습니다. 



메세지 보내기란? 메소드를 호출하는 것을 말합니다.





