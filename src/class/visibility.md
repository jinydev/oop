
# 가시성(visibility)


# 14.3 접근 권한 속성
클래스와 같이 객체지향 프로그램에서속성이라는 추가적인 접근 권한 개념이 도입됩니다. 접근 권한 속성은 각각의 클래스의 독립성과 보호를위해서 프로퍼티(변수)나 메서드(함수) 등에 권한을 설정하는 것입니다.

PHP 클래스에서는 세 가지의 속성을 가지고 있습니다. public, protected, private를 제공합니다.

속성은 클래스 외부에서의 접근을제한하고자 할 때 사용할 수 있습니다.

접근 속성의 종류

PHP 클래스에서는 프로퍼티 변수의 속성에 대해서 세 가지 타입을 지원합니다.

* public:  public으로설정된 프로퍼티 변수는 외부에서 접근이 가능합니다. 즉, 값을읽거나 새로운 값으로 설정이 가능합니다.

* protected:정의한 클래스와 상속한 클래스에서만 사용이 가능합니다. 이 속성은 클래스 내의 메서드와 서브 클래스에서만 접근하여 사용할 수 있습니다. 외부에서 접근할 수는 없지만 상속을 받은 경우에는 접근이 가능합니다.

* private:정의한 클래스 내에서만 사용 가능합니다. 이 속성은 같은 클래스 내에서만 참조가 가능합니다. protectd와달리 서브 클래스에서는 사용할 수 없습니다




UML
`+`는 공개맴버
`-`는 프라이빗 맴버, 비공개 맴버라고 합니다.
`#` protected 맴버

객체지향 언어에는 기본적으로 `private`이나 PHP에서는 기본적으로 `public`입니다.

속성은 프로퍼티, 메소드 모두 각각이 앞에 선언을 해주어야 합니다.
그룹으로 지정하여 지정을 할 수 없습니다.




### 공개벰버와 비공개 멤버
---



### 속성
---
공개 맴버변수의 경우 오류 입력이 되어도 방지를 할 수 없습니다.
보호하기 위해서는 private로 사용후에 getter/setter를 이용하는 방법입니다.

# 접근 권한 속성
클래스와 같이 객체지향 프로그램에서속성이라는 추가적인 접근 권한 개념이 도입됩니다. 접근 권한 속성은 각각의 클래스의 독립성과 보호를위해서 프로퍼티(변수)나 메서드(함수) 등에 권한을 설정하는 것입니다.

PHP 클래스에서는 세 가지의 속성을 가지고 있습니다. public, protected, private를 제공합니다.

속성은 클래스 외부에서의 접근을제한하고자 할 때 사용할 수 있습니다.

접근 속성의 종류

PHP 클래스에서는 프로퍼티 변수의 속성에 대해서 세 가지 타입을 지원합니다.

* public:  public으로설정된 프로퍼티 변수는 외부에서 접근이 가능합니다. 즉, 값을읽거나 새로운 값으로 설정이 가능합니다.

* protected:정의한 클래스와 상속한 클래스에서만 사용이 가능합니다. 이 속성은 클래스 내의 메서드와 서브 클래스에서만 접근하여 사용할 수 있습니다. 외부에서 접근할 수는 없지만 상속을 받은 경우에는 접근이 가능합니다.

* private:정의한 클래스 내에서만 사용 가능합니다. 이 속성은 같은 클래스 내에서만 참조가 가능합니다. protectd와달리 서브 클래스에서는 사용할 수 없습니다




UML
`+`는 공개맴버
`-`는 프라이빗 맴버, 비공개 맴버라고 합니다.
`#` protected 맴버

객체지향 언어에는 기본적으로 `private`이나 PHP에서는 기본적으로 `public`입니다.

속성은 프로퍼티, 메소드 모두 각각이 앞에 선언을 해주어야 합니다.
그룹으로 지정하여 지정을 할 수 없습니다.




### 공개벰버와 비공개 멤버
---



### 속성
---
공개 맴버변수의 경우 오류 입력이 되어도 방지를 할 수 없습니다.
보호하기 위해서는 private로 사용후에 getter/setter를 이용하는 방법입니다.