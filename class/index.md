## 14.1 클래스와 객체

객체지향 방식의 프로그램 OOP는 Object-Oriented Programming의 약자입니다. 객체지향 프로그램 코딩 방식은 기존 함수형 절차적 프로그램 방식과 비교하여 소프트웨어의 유지보수 및 구조적으로 개발하는 데 있어 매우 유용합니다. 그런 점에서 최신 소스코드의 개발 방식은 클래스 기반의 코딩 스타일을 많이 적용합니다.

객체지향 프로그램은 단순한 코딩 문법 및 스타일이 아닙니다. 데이터의 처리와 기능, 각각의 요소를 하나의 객체로 처리합니다. 객체는 각각의 데이터와 기능들이 연관하여 프로그램이 동작, 구성됩니다. 


### 14.1.1 절차적 프로그램
절차적 프로그래밍 방식은 초기의 프로그램 개발 방법입니다. 단순하게 프로그램의 명령어를 모아 놓은 형태로 논리적 순서대로 쓰여진 프로그램을 코딩을 말합니다. 예전 초창기 컴퓨터 개발 방법이며, 간단한 기능과 테스트 결과를 빠르게 보기 위해서 자주 사용합니다.

만일 절차적 방식으로 작성된 대용량 프로그램은 소스의 내용을 쉽게 이해하기가 어렵습니다. 또한 복잡한 동작을 처리하기 위해서 상당량의 유지보수 시간이 필요합니다. 

### 14.1.2 구조적 프로그램
구조적 프로그램밍은 이전 절차적 프로그래밍의 문제점을 보완한 프로그램 개발 방법론 입니다. 좀 더 체계적이고 구조적으로 프로그램을 개발하기 위한 새로운 다양한 시도 중의 하나입니다.

나날이 프로그램은 복잡해지고 크기가 커지고 있습니다. 방대한 기능의 프로그램 동작 다수의 사람들이 팀원을 위하여 서로 이해하고 내용을 공유하는 것은 매우 어렵습니다. 또한 순서도를 통하여 쉽게 표현하기도 어려울 것입니다. 이러한 문제점들은 소프트웨어를 고도화하고 유지 보수하는 데 매우 어렵습니다. 
구조적 프로그램은 이러한 문제점을 보완하고자 1968년 에츠러르 다익스트라가 자신의 논문 <GOTO문의 해로움>(GO To statement considered Harmful)에서 프로그램을 함수(프로시저) 단위로 나눠서 프로시저 간에 연관과 호출을 통해 구조적 프로그램 방법을 제안한 것이 계기가 되었습니다.

하지만 기존의 함수 방식의 개발 방법은 데이터 처리 등을 구조화하여 처리하는 반면에, 실제적으로 데이터 자체까지는 구조적으로 해결을 하지 못했습니다. 또한 외부 변수들을 많이 쓰는 바람에 사용 가능한 변수 이름을 다 써버리는 등 프로그램의 크기가 커질수록 개발할 수 있는 환경은 포화되어 갔습니다.

함수형 프로그램의 다양한 문제점을 개선하기 위해서 등장한 것이 객체지향 프로그래밍입니다. 객체지향 프로그램은 작은 객체들을 만들어서 문제를 해결하고, 해결된 문제를 연결하여 더 큰 문제를 해결하는 상향식(bottom-up) 설계 방법을 도입하게 되었습니다. 또한 이렇게 생성된 객체들은 독립성과/ 신뢰성을 향상하여 객체를 수정 없이 재사용할 수 있어 개발과 유지보수를 대폭적으로 개선했습니다.


### 14.1.3 캡슐화
캡슐화는 객체지향 방법의 기본 개념입니다. 캡슐화의 목적은 ‘코드를 수없이 재사용’하는 것 입니다. 갭슐화는 프로그램 코드를 재사용하는 데 있어서 기능적인 부분과 데이터적인 부분을 한곳에 묶어서 관리할 필요성이 있습니다.

```
객체 = 변수 + 함수
```

객체와 함수의 차이점은 데이터를 같이 관리하는지 여부입니다. 보통 변수는 프로퍼티(property), 함수는 메서드(method)라고 합니다.