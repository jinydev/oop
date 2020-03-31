---
layout: page
title: "PHP Class"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
    - "class"
---
# 클래스
<hr>
클래스는 기존 함수형 프로그램 코딩 개발 방법보다 향상된 객체지향형 프로그램 개발 방법론 및 환경을 지원합니다. PHP도 다양한 객체지향 방법론을 도입하여 최신 트렌드에 맞는 클래스 및 코딩 방법을 제공합니다.  

<br>

## 클래스의 종류
<hr>

* 클래스
* [정적 클래스](14.6)
* [익명 클래스](14.7)

<br>

## 선언과 생성
<hr>

* [클래스와 객체](14.1)
* [클래스 & 인스턴스](14.2)
* [클래스 선언](14.3)
* [인스턴스 생성](14.4)
* [객체 접근](14.5)

* [상수](const)

* [인스턴스](instance)
* [메시지](message)

### 가시성 (visibility)
* [가시성](visibility)
<br>

## 매직메서드
<hr>
클래스는 매직 메서드라는 몇 개의 미리 사전에 정의한 특수한 메서드가 있습니다. 클래스를 생성할 때 초기값을 설정하거나 오류 동작 등 실행되는 특별한 메서드입니다. 

* [초기화](magic/construct) (__construct)
* [소멸자](magic/destruct) (__destruct)
* [call](magic/call)
* [객체의 문자열 변환](magic/tostring)
* [객체 함수 호출](magic/invoke)
* [객체 복제 호출](magic/clone)
* [set](magic/set)
* __[callStatic](magic/callstatic)() : 정적 컨텍스트 내에서 접근 불가 메서드를 가져올 때 호출됩니다.
* [sleep](magic/sleep) __sleep()
* [wakeup](magic/wakeup) __wakeup()
* [set_state](magic/set_srate) __set_state() : var_export()에 의해 내보내진 클래스를 위해 호출됩니다.
* [debugInfo](magic/debuginfo) __debugInfo() : var_dump()에 의해 덤프될 때 보여줄 속성을 가져올 때 호출됩니다.

<br><br>