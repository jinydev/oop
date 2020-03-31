---
layout: page
title: "Magic Method"
keyword: "jinyphp, php, 객체지향, oop, class"
description: "모던PHP는 최신 트랜드의 객체지향 프로그래밍을 활용합니다."
breadcrumb:
- "Class"
- "Masic Method"
---

# 매직 메서드(Masic Method)
<hr>
클래스는 매직 메서드라는 몇 개의 미리 사전에 정의한 특수한 메서드가 있습니다. 클래스를 생성할 때 초기값을 설정하거나 오류 동작 등 실행되는 특별한 메서드입니다.  

* [초기화](construct) (__construct)
* [소멸자](destruct) (__destruct)
* [call](call)
* [객체의 문자열 변환](tostring)
* [객체 함수 호출](invoke)
* [객체 복제 호출](clone)
* [set](set)
* __[callStatic](callstatic)() : 정적 컨텍스트 내에서 접근 불가 메서드를 가져올 때 호출됩니다.
* __sleep()
* __wakeup()
* __set_state() : var_export()에 의해 내보내진 클래스를 위해 호출됩니다.
* __debugInfo() : var_dump()에 의해 덤프될 때 보여줄 속성을 가져올 때 호출됩니다.
