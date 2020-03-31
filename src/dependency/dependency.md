### 의존성

의존성을 주입하는 것은 하나의 객체가 다른객체를 `new`키워드를 이용하여 생성하는 방식이 아니라, 외부러 부터 객체의 인스턴스를 전달 받는 방식입니다.



### 의존성 주입
---
의존성 주입은 객체간의 대화를 하기 위해서 객체지향 프로그램에서 자주 이용하는 설계 패턴입니다. 객체지향의 코드의 필수적인 기능입니다.

객체를 주입받아 처리를 하게 된면, 세부적인 동작을 직접 구현하지 않고 외부로 부터 사용하기 편리합니다.'
느슨한 결합이 됩니다.




### 느슨한 결합
---
객체간의 느슨한 결합은 유지보수를 위하여 클래스의 확장이 매우 좋아집니다.



### 이름규칙
PHP언어에서 반드시 클래스의 이름을 대소문자를 구별해서 사용을 해야 되는 것입니다. 하지만, 최근 PSR2 규칙을 적용하여 대문자로 시작되게 이름을 작성을 합니다.



프레임워크에서 중요한 개념중의 하나가 의존성을 주입(dependency injection)하는 것입니다. 

소프트웨어를 개발하때는 2가지의 문제에 자주 접하게 됩니다. 하나는 복잡성이고, 다른 하나는 변경성 입니다.

복잡하다는 것은 여러 기능들이 상호 연결이 되어 있는 상태이고, 변경성은 내용을 수정하는 것입니다.

의존성은 하나의 클래스에서 다른 클래스의 객체를 생성하고 사용하는 것입니다.

<?php
class Order
{
    private $_customer;

    public function __construct($name)
    {
        echo __CLASS__." 객체를 생성하였습니다.<br>";
        // 의존성 주입
        $this->_customer = new Customer($name);
    }

    public function saveOrder()
    {
        echo $this->_customer->getName()."님의 주문처리를 합니다.<br>";
    }
}


<?php
class Customer
{
    private $_name;

    public function __construct($name)
    {
        echo __CLASS__." 객체를 생성하였습니다.<br>";
        $this->_name = $name;
    }

    public function getName()
    {
        return $this->_name;
    }
}


<?php
require "Order.php";
require "Customer.php";

echo "의존성 주입의 예제 실습입니다.<br>";

$obj = new Order("jiny");
$obj->saveOrder();

화면출력
의존성 주입의 예제 실습입니다.
Order 객체를 생성하였습니다.
Customer 객체를 생성하였습니다.
jiny님의 주문처리를 합니다.

Order 클래스에서 직접 Customer 클래스의 인스턴스를 생성하여 사용하게 됩니다. 이런경우 강한 객체의 의존성이 발생하게 됩니다. Order클래스는 Customer 클래스에 대해서 의존성을 같는다고 말합니다.

의존성을 해결하는 방법으로 인터페이스를 도입합니다.

그래도 인터페이스로 인하여 의존성은 계속 남아 있습니다.

의존성을 완전히 해결하는 방법은 인스턴스의 생성을 제거하는 것입니다.

인자로 인스턴스를 직접 받는 방법입니다.

<?php
class Order
{
    private $_customer;

    public function __construct($customer)
    {
        echo __CLASS__." 객체를 생성하였습니다.<br>";
        // 의존성 주입
        $this->_customer = $customer;
    }

    public function saveOrder()
    {
        echo $this->_customer->getName()."님의 주문처리를 합니다.<br>";
    }
}



04-2

객체지향 이전에는 구조적 방법을 통하여 프로그램을 작성하였습니다.
모듈과 함수 데이터를 기준으로 작업을 합니다. 데이터는 전역 변수 형태로 존재를 합니다.

전역변수 방식의 코딩은 보완적으로 문제가 발생이 됩니다.

이를 해결하기 위해서 객체 지향 방식으로 바귀게 되었습ㄴ다.
