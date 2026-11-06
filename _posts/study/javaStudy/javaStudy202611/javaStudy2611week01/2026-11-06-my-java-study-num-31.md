---
title: 26년 11월 1째주 자바 공부 31일차(TemporalAccessor/Temporal/TemporalAdjuster/포맷팅과 파싱)
date: 2026-11-06 17:44:00 +0900
categories: [Study, Java]
tags: [Java]
published: true
---

<h1>26년 11월 1째주 Java 공부</h1>
<h2>26년 11월 06일 금요일 자바 공부</h2>
1. 오늘은 자바 중급 1편 62강에서 67강까지 학습했다.
2. TemporalAccessor, Temporal, TemporalAdjuster, 포맷팅과 파싱에 대해 배웠다.
3. 금일 배운 내용과 어제까지 배운 내용을 토대로 AI에게 퀴즈를 내게 해 퀴즈를 풀었다.
4. 강의에서 제공하는 예제를 따라쳐봤다. 복습 시간에도 따라쳐보고 안 보고도 따라쳐봤다.
5. 금일한 내용에 대해 자바 이론책을 읽었다. 

```
1. 날짜와 시간을 조회하려면 어찌해야 하는가? ⇒ 날짜와 시간을 조회하려면 날짜와 시간 항목 중에 어떤 필드를 조회할지 선택해야 한다. 이때 날짜와 시간의 필드를 뜻하는 ChronoFiled가 사용된다. 참고로 날짜와 시간에서 필드라는 단어가 나오면 년, 월, 일, 시, 분, 초를 생각해내야 하고 각각 하나의 필드라는 것도 알고 있어야 한다.
2. LocalDateTime을 포함한 특정 시점의 시간을 제공하는 클래스는 모두 뭘 구현하고 이를 어떻게 활용하는가? ⇒ LocalDateTime을 포함한 특정 시점의 시간을 제공하는 클래스는 모두 TemporalAccessor 인터페이스를 구현한다. 참고로 TemporalAccessor 인터페이스는 특정 시점의 시간을 조회하는 기능을 제공한다. 또한 TemporalAccessor 인터페이스의 get 메소드를 활용하여 get(TemporalField field)을 호출할 때 어떤 날짜와 시간 필드를 조회할지 TemporalField의 구현인 ChronoField를 인수로 전달하면 된다.
3. get(TemporalField field)를 꼭 사용해야 하는가? ⇒ get(TemporalField field)을 사용하면 코드가 길어지고 번거롭기에 자주 사용하는 조회 필드는 간단한 편의 메소드를 제공한다. 예를 들어, dt.get(ChronoField.DAY_OF_MONTH)를 dt.getDayOfMonth()처럼 해서 사용할 수 있다.
4. 편의 메소드가 없으면 경우는? ⇒ 자주 사용하지 않는 특별한 기능은 편의 메소드를 제공하지 않는다. 편의 메소드를 사용하는 것이 가독성이 좋기에 일반적으로는 편의 메소드를 사용하고, 편의 메소드가 없는 경우 get(TemporalField field)를 사용하면 된다.
5. 날짜와 시간을 조작하려면 어떤 시간 단위를 사용해야 하는가? ⇒ 날짜와 시간을 조작하려면 어떤 시간 단위를 변경할지를 선택해야 한다. 이때 날짜와 시간의 단위를 뜻하는 ChronoUnit이 사용된다. 
6. 날짜와 시간을 조작하는데 사용하는 Temporal plus(long amountToAdd, TemporalUnit unit) 메소드는 뭐하는 메소드인가? ⇒ Temporal plus(long amountToAdd, TemporalUnit unit) 메소드는 LocalDateTime를 포함한 특정 시점의 시간을 제공하는 클래스는 모두 Temporal 인터페이스에 구현된다. Temporal은 특정 시점의 시간을 조작하는 기능을 제공한다. plus(long amountToAdd, TemporalUnit unit)를 호출할 때 더하기 할 숫자와 시간의 단위를 전달하면 된다. 이 때, TemporalUnit의 구현인 ChronoUnit을 인수로 전달하면 된다. 이 메소드는 불변이므로 반환값을 받아야하고 참고로 minus() 메소드도 존재한다.
7. plus(long amountToAdd, TemporalUnit unit) 메소드에 편의 메소드를 사용할 수 있는가? ⇒ 자주 사용하는 메소드는 편의 메소드가 제공된다. 예를 들어, dt.plus(10, ChronoUnit.YEARS)를 dt.plusYears(10)를 들 수 있다.
8. Period를 사용하면 어떤 조작을 할 수 있는가? ⇒ Period나 Duration은 기간, 즉, 시간의 간격을 뜻한다. 특정 시점의 시간에 기간으더할 수 있다.
9. 예를 들어, 날짜 정보만 있고, 분에 대한 정보가 없는 경우, 이럴 땐 어찌해야 하는가? ⇒ LocalDate는 날짜 정보만 가지고 있고, 분에 대한 정보는 없다. 따라서 분에 대한 정보를 조회하려고 하면 예외가 발생한다. 이런 문제를 예방하기 위해 TemporalAccessor와 Temporal 인터페이스는 현재 타입에서 특정 시간 단위나 필드를 사용할 수 있는지 확인할 수 있는 메소드를 제공한다. 참고로 LocalDate는 분의 초 필드를 지원하지 않기에 ChronoField.SECOND_OF_MINUTE를 조회하면 false를 반환한다.
10. 날짜와 시간을 조작할 때 사용하는 메소드는 무엇인가? ⇒ 날짜와 시간을 조작할 때 사용하는 메소드는 Temporal with(TemporalField field, long newValue) 메소드가 있다. 이는 Temporal.with()를 사용하면 날짜와 시간의 특정 필드의 값만 변경할 수 있다. 이는 불변이기에 반환 값을 받아야 한다. 참고로 자주 사용하는 메소드는 편의 메소드가 제공되는데 예를 들어, dt.with(ChronoField.YEAR, 2020)는 dt.withYear(2020)처럼 제공된다.
11. TemporalAdjuster란? ⇒ with() 메소드는 아주 단순한 날짜만 변경할 수 있기에 만약 다음 주 금요일, 이번 달의 마지막 일요일 같은 복잡한 날짜를 계산하고 싶다면 TemporalAdjuster 인터페이스를 사용하면 된다.
12. DayOfWeek란 무엇인가? ⇒ 월, 화, 수, 목, 금, 토, 일을 나타내는 열거형이다.
13. TemporalAdjuster가 제공하는 주요 메소드와 그 기능은 무엇인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드는 dayOfWeekInMonth() 메소드 , firstDayOfMonth() 메소드 , firstDayOfNextMonth() 메소드 , firstDayOfNextYear() 메소드 , firstDayOfYear() 메소드 , firstInMonth() 메소드 , lastDayOfMonth() 메소드 , lastDayOfNextMonth() 메소드 , lastDayOfNextYear() 메소드 , lastDayOfYear() 메소드 , lastInMonth() 메소드 , next() 메소드, nextorSame() 메소드, previous() 메소드, previousOrSame() 메소드가 있다.
14. TemporalAdjuster가 제공하는 주요 메소드인 dayOfWeekInMonth() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 dayOfWeekInMonth() 메소드는 주어진 요일이 몇 번째인지에 따라 날짜를 조정한다.
15. TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfMonth() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfMonth() 메소드는 해당 월의 첫째 날로 조정한다.
16. TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfNextMonth() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfNextMonth() 메소드는 다음 달의 첫째 날로 조정한다.
17. TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfNextYear() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfNextYear() 메소드는 다음 해의 첫째 날로 조정한다.
18. TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfYear() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 firstDayOfYear() 메소드는 해당 해의 첫째 날로 조정한다.
19. TemporalAdjuster가 제공하는 주요 메소드인 firstInMonth() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 firstInMonth() 메소드는 주어진 요일 중 해당 월의 첫 번째 요일로 조정한다.
20. TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfMonth() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfMonth() 메소드는 해당 월의 마지막 날로 조정한다.
21. TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfNextMonth() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfNextMonth() 메소드는 다음 달의 마지막 날로 조정한다.
22. TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfNextYear() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfNextYear() 메소드는 다음 해의 마지막 날로 조정한다.
23. TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfYear() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 lastDayOfYear() 메소드는 해당 해의 마지막 날로 조정한다.
24. TemporalAdjuster가 제공하는 주요 메소드인 lastInMonth() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 lastInMonth() 메소드는 주어진 요일 중 해당 월의 마지막 요일로 조정한다.
25. TemporalAdjuster가 제공하는 주요 메소드인 next() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 next() 메소드는 주어진 요일 이후의 가장 가까운 요일로 조정한다.
26. TemporalAdjuster가 제공하는 주요 메소드인 nextorSame() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 nextorSame() 메소드는 주어진 요일 이후의 가장 가까운 요일로 조정하되, 현재 날짜가 주어진 요일인 경우 현재 날짜를 반환한다.
27. TemporalAdjuster가 제공하는 주요 메소드인 previous() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 previous() 메소드는 주어진 요일 이전의 가장 가까운 요일로 조정한다.
28. TemporalAdjuster가 제공하는 주요 메소드인 previousOrSame() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ TemporalAdjuster가 제공하는 주요 메소드인 previousOrSame() 메소드는 주어진 요일 이전의 가장 가까운 요일로 조정하되, 현재 날짜가 주어진 요일인 경우 현재 날짜를 반환한다.
29. 포맷팅이란? ⇒ 포맷팅은 날짜와 시간 데이터를 원하는 포맷의 문자로 변경하는 것이다. 예를 들어, Date를 String으로 바꾸는 것이다.
30. 파싱이란? ⇒ 파싱은 문자열을 날짜와 시간 데이터로 변경하는 것이다. 예를 들어, String을 Date로 바꾸는 것이다.
31. LocalDate 같은 날짜 객체를 원하는 형태의 문자로 바꾸려면 어찌 해야 하는가? ⇒ LocalDate 같은 날짜 객체를 원하는 형태의 문자로 바꾸려면 DateTimeFormmatter를 사용하면 된다. 여기에 ofPattern() 메소드로 원하는 포맷을 지정하면 된다. 
32. 문자열을 날짜와 시간으로 파싱할 때도 DateTimeFormatter를 사용하는가? O/X ⇒ O. 문자열을 읽어서 날짜와 시간 객체로 만드는 것을 파싱이라 한다. 이 때 문자열의 어떤 부분이 년이고, 월이고 일인지 각각의 위치를 정해서 읽어야 한다.
```