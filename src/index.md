---
layout: page
title: "객체지향 프로그래밍"
keyword: "jinyphp, php, 객체지향, oop, class"
breadcrumb:
---
# 객체지향 프로그래밍




## 객체

### 객체지향
* [객체지향](./class)

* [행동](./oop/행동)





## 클래스
클래스는 기존 함수형 프로그램 코딩 개발 방법보다 향상된 객체지향형 프로그램 개발 방법론 및 환경을 지원합니다.  
PHP도 다양한 객체지향 방법론을 도입하여 최신 트렌드에 맞는 클래스 및 코딩 방법을 제공합니다. 

### 생성
* [인스턴스](./class/instance)
* [선언](./class/선언)
* [생성](./class/생성)
* [접근](./class/접근)

### 정적클래스
* [정적](./class/정적)

### 매직메서드
* [매직메서드](./class/매직메서드)

### 역할과 책임
* 책임(responsibility)

### 익명클래스
* [익명](./class/익명)

### 객체의 구분
* 일급객체

## 구조
기본적인 클래스에 대해서 살펴봤습니다.  클래스는 변수(프로퍼티)와 함수(메서드)를 묽어서 객체화 하여 사용을 했습니다. 클래스의 객체지향 방식의 코딩은 프로그램의 보다 최적화 및 유지보수화하는 데 매우 유용합니다.이번 장에서는 최신 클래스 기반의 코딩 및 확장된 기능들에 대해서 살펴 보도록 하겠습니다. 클래스의 확장은 오픈소스 및 다양한 개발자들과 협업하는 데 필요한 코드 구현 기술입니다. 

### 상속
* [상속](./extends)
* 계층

* [오버라이딩](./extends/오버라이딩)
* [추상화](./extends/추상화)
* [트래이트](./extends/트래이트)
* [네임스페이스](./extends/네임스페이스)

### 인터페이스
* [인터페이스](./extends/인터페이스)
* [투명성]
* 복수 인터페이스


## 디자인패턴 
처음으로 패턴, 디자인 패턴이라는 단어를 접했을 때 패션이나 디자인 분야의 관련 내용으로 생각하실 분들이 많이 있을 것입니다. 디자인 패턴은 많은 사람들이 격은 문제점과 해결방법들을 정리해 놓은 것을 말합니다.
* [유래](./petterns)

* [생성패턴](./petterns/생성패턴)
* [구조패턴](./petterns/구조패턴)
* [행동패턴](./petterns/행동패턴)

## 예외사항
프로그램을 개발하다 보면 수많은 오류와 예외가 발생합니다. 보통 오류는 크게 코드상의 문법 오류와 소스상의 논리적인 오류로 구분할 수 있습니다. 문법적 오류는 PHP가 시작하기 전에 체크하여 알려주기 때문에 쉽게 문법적 오류를 해결할 수 있습니다. 하지만 논리적인 오류는 쉽게 찾을 수 있는 오류가 아닙니다. 또한 이러한 문제로 인해 프로그램은 정상적인 동작을 수행하지 못하고 중간에 중단되기도 합니다.

개발자는 오류 및 예외 메시지가 발생하면 잘못된 부분을 인지하고, 문제를 해결하기 위해 노력합니다. 이러한 오류와 예외 처리가 미흡하면 다수의 잘못된 메시지가 사용자에게 출력되거나 불편함을 줄 것 입니다. 논리적인 오류는 개발자들에게 많은 디버깅 시간을 투여하게 만들도록 합니다.

그렇다고 해서 발생한 오류 메시지를 화면에 출력하면 프로그램의 완성도에 대한 신뢰를 떨어뜨릴 수 있습니다.

개발의 기술이 높아지고 경험이 많을수록 개발자는 PHP 오류와 예외를 예측하여 처리해야 합니다.

* [오류](./Exception)
* [예외](./Exception/Exception)


## 인스팩터


[재이용성](재이용성)
[일급객체](일급객체)