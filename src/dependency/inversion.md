---
layout: page
title: "PHP Class"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
    - "object"
---

# 의존성 뒤집기
Dependency Inversion Principle

의존성 역전은 객체지향 디자인 원칙 중의 하나 입니다.

객체지향의 생각하는 방법의 뒤집어 봅니다.

뭘 뒤집을까요? 
하나의 객체가 다른 객체를 가지고 있는 의존성과 반대로,
의존 되는 객체가 상위객체에게 자신을 포함하도록 하는 것입니다.


의존
객체를 상속하거나 추상클래스로 분리될 때 두개의 클래스가 관계를 가지는 것을 말합니다. 복합객체는 동적으로 의존성을 설정할 수 있습니다. 이를 위해서 내부에 프로퍼티를 사용합니다.



의존성 vs 의존성 주입
