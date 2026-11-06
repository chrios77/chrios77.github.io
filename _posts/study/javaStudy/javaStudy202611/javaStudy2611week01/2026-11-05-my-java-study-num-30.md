---
title: 26년 11월 1째주 자바 공부 30일차( 날짜 및 시간 클래스/시간 간격 관련 클래스)
date: 2026-11-05 17:44:00 +0900
categories: [Study, Java]
tags: [Java]
published: true
---

<h1>26년 11월 1째주 Java 공부</h1>
<h2>26년 11월 05일 목요일 자바 공부</h2>
1. 오늘은 자바 중급 1편 57강에서 61강까지 학습했다.
2. 날짜/시간 클래스 , 시간 간격 관련 클래스에 대해 배웠다.
3. 금일 배운 내용과 어제까지 배운 내용을 토대로 AI에게 퀴즈를 내게 해 퀴즈를 풀었다.
4. 강의에서 제공하는 예제를 따라쳐봤다. 복습 시간에도 따라쳐보고 안 보고도 따라쳐봤다.
5. 금일한 내용에 대해 자바 이론책을 읽었다. 

```
1. 가장 기본이 되는 날짜와 시간 클래스는 무엇인가? ⇒ 가장 기본이 되는 날짜와 시간 클래스는 LocalDate 클래스, LocalTime 클래스, LocalDateTime 클래스이다.
2. LocalDate 클래스, LocalTime 클래스, LocalDateTime 클래스에서 Local이라는 단어가 들어가게 된 이유는 무엇인가? ⇒  LocalDate 클래스, LocalTime 클래스, LocalDateTime 클래스에서 Local이라는 단어가 들어가게 된 이유는 세계 시간대를 고려하지 않아서 타임존이 적용되지 않았기 때문이다. 예를 들어, 애플리케이션 개발 시 국내 서비스만 고려할 때, 나의 생일은 2016년 8월 16일이야처럼 특정 지역의 날짜와 시간만을 고려할 때 사용한다.
3. LocalDate 클래스는 뭐하는 클래스인가? ⇒ LocalDate 클래스는 날짜만 표현할 때 사용한다. 주로 년, 월, 일을 다룬다. 예를 들어, 2013-11-21를 들 수 있다.
4. LocalDate 클래스를 통해 사용할 수 있는 메소드는 뭐가 있는가? ⇒ now() 메소드, of() 메소드, plusDays 메소드()가 있다.
5. LocalDate 클래스의 now() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDate 클래스의 now() 메소드는 현재 시간을 기준으로 날짜를 생성한다.
6. LocalDate 클래스의 of() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDate 클래스의 of() 메소드는 특정 날짜를 기준으로 생성한다. 매개변수로 년, 월, 일을 입력할 수 있다.
7. LocalDate 클래스의 plusDays() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDate 클래스의 plusDays() 메소드는 특정 일을 더한다. plusDays() 메소드 외에 다양한 plusXxx() 메소드가 존재한다.
8. 날짜 클래스를 사용할 때 주의할 것은 무엇인가? ⇒ 날짜 클래스를 사용할 때 주의할 것은 모든 날짜 클래스는 불변이다. 따라서 변경이 발생하는 경우 새로운 객체를 생성해서 반환하기에 반환값을 꼭 받아야 한다.
9. LocalTime 클래스는 뭐하는 클래스인가? ⇒ LocalTime 클래스는 시간만을 표현할 때 사용한다. 주로 시, 분, 초를 다루로 초는 밀리초, 나노초 단위도 포함할 수 있다. 예를 들어, 08:20:30.213를 들 수 있다.
10. LocalTime 클래스를 통해 사용할 수 있는 메소드는 뭐가 있는가? ⇒ LocalTime 클래스를 통해 사용할 수 있는 메소드는 now() 메소드, of() 메소드, plusSeconds() 메소드가 있다.
11. LocalTime 클래스의 now() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalTime 클래스의 now() 메소드는 현재 시간을 기준으로 시간을 생성한다.
12. LocalTime 클래스의 of() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalTime 클래스의 of() 메소드는 특정 시간을 기준으로 생성한다. () 안에 시, 분, 초, 나노초를 입력할 수 있다.
13. LocalTime 클래스의 plusSeconds() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalTime 클래스의 plusSeconds() 메소드는 특정 초를 더한다. 이 외에도 다양한 plusXxx() 메소드가 존재한다.
14. LocalTime 클래스를 사용할 때 주의할 것은 무엇인가? ⇒ 시간 클래스를 사용할 때 주의할 것은 모든 시간 클래스는 불변이다. 따라서 변경이 발생하는 경우 새로운 객체를 생성해서 반환하기에 반환값을 꼭 받아야 한다.
15. LocalDateTime 클래스는 뭐하는 클래스인가? ⇒ LocalDateTime 클래스는 LocalDate 클래스와 LocalTime 클래스을 합한 개념이다. 그러므로 LocalDate 클래스와 LocalTime 클래스를 내부에 가지고 날짜와 시간을 모두 표현한다. 예를 들어, 2013-11-21T08:20:30.213을 들 수 있다. 
16. LocalDateTime 클래스를 통해 사용할 수 있는 메소드는 뭐가 있는가? ⇒ LocalDateTime 클래스를 통해 사용할 수 있는 메소드는 now() 메소드,  of() 메소드, toXxx() 메소드, plusXxx() 메소드, isBefore() 메소드, isAfter() 메소드, isEqual() 메소드가 있다. 
17. LocalDateTime 클래스의 now() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDateTime 클래스의 now() 메소드는 현재 날짜와 시간을 기준으로 현재 날짜와 시간을 생성한다.
18. LocalDateTime 클래스의 of() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDateTime 클래스의 of() 메소드는 2가지 버전이 있다. 하나는 of(…)으로 특정 날짜와 시간을 기준으로 날짜와 시간을 생성한다. 다른 하나는 LocalDateTime.of(localDate, localTime)으로 날짜와 시간을 사용해서 LocalDateTime을 만드는 것이다.
19. LocalDateTime 클래스의 toXxx() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDateTime 클래스의 toXxx() 메소드는 날짜인 LocalDate와 시간인 LocalTime을 toXxx() 메소드를 통해 분리할 수 있다.
20. LocalDateTime 클래스의 plusXxx() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDateTime 클래스의 plusXxx() 메소드는 특정 날짜와 시간을 더한다. 이 외에 다양한 plusXxx() 메소드가 존재한다.
21. LocalDateTime 클래스의 isBefore() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDateTime 클래스의 isBefore() 메소드는 다른 날짜시간과 비교한다. 현재 날짜와 시간이 이전이라면 true를 반환한다.
22. LocalDateTime 클래스의 isAfter() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDateTime 클래스의 isAfter() 메소드는 다른 날짜시간과 비교한다. 현재 날짜와 시간이 이후하면 true를 반환한다.
23. LocalDateTime 클래스의 isEqual() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ LocalDateTime 클래스의 isEquals() 메소드는 다른 날짜 시간과 시간적으로 동일한지 비교하고 시간이 같으면 true를 반환한다.
24. isEquals() 메소드와 equals() 메소드는 어떤 차이가 있을까? ⇒ isEquals() 메소드는 단순히 비교 대상이 시간적으로 같으면 true를 반환한다. 객체가 다르고 타임존이 달라도 시간적으로 같으면 true를 반환한다. 쉽게 말해 시간을 계산해서 시간으로만 둘을 비교한다. 예를 들어 서울의 9시와 UTC의 0시는 시간적으로 같다. 이 둘을 비교하면 true를 반환한다. equals() 메소드는 객체의 타입, 타임존 등 내부 데이터의 모든 구성요소가 같아야 true를 반환한다. 예를 들어 서울의 9시와 UTC의 0시는 시간적으로 같다. 이 둘을 비교하면 타임존의 데이터가 다르기에 false를 반환한다.
25. 타임존 목록의 예시로는 뭐가 있는가? ⇒ 타임존 안에는 일광 절약 시간제에 대한 정보와 오프셋 정보를 모두 포함하고 있다. 예를 들어, 타임존 목록으로는 Europe/London, GMT, UTC, US/Arizona -07:00, America/New_York -05:00, Asia/Seoul +09:00, Asia/Dubai +04:00, Asia/Istanbul +03:00, Asia/Shanghai +08:00, Europe/Paris +01:00, Europe/Berlin +01:00 를 예시로 들 수 있다.
26. ZoneId 클래스란? ⇒ 타임존을 자바에서는 클래스 형태로 제공하는데 그것이 ZonedId 클래스이다. ZoneId 클래스는 내부에 일광 절약 시간 관련 정보, UTC와의 오프셋 정보를 포함하고 있다.
27. ZoneId 클래스를 통해 사용할 수 있는 메소드는 무엇인가? ⇒ of() 메소드, systemDefault() 메소드가 있다.
28. ZoneId 클래스의 of() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ZonedId 클래스의 of() 메소드는 시스템이 사용하는 기본 ZoneId를 반환한다. 이는 각 PC 환경마다 다른 결과가 나올 수 있다.
29. ZoneId 클래스의 systemDefault() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ZonedId 클래스의 systemDefault() 메소드는 타임존을 직접 제공해서 ZoneId를 반환한다.
30. ZonedDateTime 클래스란? ⇒ ZonedDateTime 클래스는 LocalDateTime 클래스에 시간대 정보인 ZoneId 클래스가 합쳐진 것이다. ZonedDateTime 클래스는 시간대를 고려한 날짜와 시간을 표현할 때 사용한다. 여기에는 시간대를 표현하는 타임존이 포함된다. 이는 예를 들어, 2013-11-21T08:20:30.213+9:00[Asia/Seoul]를 들 수 있다. 여기서 +9:00은 UTC로 부터의 시간대 차이이다. 이를 오프셋이라 한다. 참고로 한국은 UTC보다 +9:00 시간이다. Asia/Seoul은 타임존이라고 하는데 이 타임존을 알면 오프셋도 알 수 있다. 참고로 +9:00 같은 오프셋 정보도 타임존에 포함된다. 추가로 ZoneId 클래스를 통해 타임존을 알면 일광 절약 시간제에 대한 정보도 알 수 있으므로 일광 절약 시간제가 적용될 수 있다.
31. ZonedDateTime 클래스를 통해 사용할 수 있는 대표적인 메소드는 무엇인가? ⇒ ZonedDateTime 클래스를 통해 사용할 수 있는 대표적인 메소드는 now() 메소드, of() 메소드, withZoneSameInstant(ZoneId) 메소드가 있다.
32. ZonedDateTime 클래스의 메소드인 now() 메소드는 현재 날짜와 시간을 기준으로 날짜와 시간을 생성한다. 이때 ZoneId는 ZoneId.systemDefault() 메소드를 통해 현재 시스템을 따른다.
33. ZonedDateTime 클래스의 메소드인 of() 메소드는 특정 날짜와 시간을 기준으로 날짜와 시간을 생성하는데 주로 ZoneId를 추가해줘야 한다. 
34. ZonedDateTime 클래스의 메소드인 withZoneSameInstant(ZoneId) 메소드는 타임존을 변경한다. 타임존에 맞춰 시간도 함께 변경된다. 이 메소드를 사용하면 지금 다른 나라는 몇 시인지를 확인할 수 있다. 예를 들어 서울이 지금 9시라면, UTC 타임존으로 변경하면 0시임을 확인할 수 있다.
35. OffsetDateTime 클래스는 무엇인가? ⇒ OffsetDateTime 클래스는 LocalDateTime에 UTC 오프셋 정보인 ZoneOffset이 합쳐진 것이다. OffsetDateTime 클래스는 시간대를 고려한 날짜와 시간을 표현할 때 사용한다. 여기에는 타임존은 없고, UTC로 부터의 시간대 차이인 고정된 오프셋만 포함한다. 예를 들어, 2013-11-21T08:20:30.213+9:00를 들 수 있다. OffsetDateTime 클래스에는 ZoneId가 없기에 일광 절약 시간제가 적용되지 않는다.
36. OffsetDateTime 클래스를 통해 사용할 수 있는 메소드는 무엇인가? ⇒ OffsetDateTime 클래스를 통해 사용할 수 있는 메소드는 now() 메소드, of() 메소드가 있다.
37. ZonedDateTime 클래스와 OffsetDateTime 클래스 중 뭘 써야 할까? ⇒ ZonedDateTime 클래스는 구체적인 지역 시간대를 다룰 때 사용하며, 일광 절약 시간을 자동으로 처리할 수 있다. 사용자 지정 시간대에 따른 시간 계산이 필요할 때 적합하다. OffsetDateTime 클래스는 UTC와의 시간 차이만을 나타낼 때 사용하며, 지역 시간대의 복잡성을 고려하지 않는다. 시간대 변환 없이 로그를 기록하고, 데이터를 저장하고 처리할 때 적합하다.
38. ZonedDateTime 클래스와 OffsetDateTime 클래스의 참고 사항은 무엇인가? ⇒ ZonedDateTime 클래스와 OffsetDateTime 클래스는 글로벌 서비스를 하는 것이 아니면 잘 사용하지 않는다. 따라서 너무 깊이있게 파기보다는 대략적으로 이런 것이 있다 정도로만 알아두면 된다. 실무에서 개발하면서 글로벌 서비스를 개발할 기회가 있다면 그때 필요한 부분을 찾아 깊이 있게 학습하면 된다.
39. Instant 클래스란? ⇒ Instant 클래스는 UTC를 기준으로 하는, 시간의 한 지점을 나타낸다. Instant 클래스는 날짜와 시간을 나노초 정밀도로 표현하며, UTC 기준으로 1970년 1월 1일 0시 0분 0초를 기준으로 경과한 시간으로 계산된다. 쉽게 말해, Instant 클래스 내부에는 나노초를 포함하는 초 데이터만 들어있다. 따라서 날짜와 시간을 계산하는데 사용하는 것에는 적합하지 않다.
40. 에포크 시간이란? ⇒ 우선 에포크 시간을 영어로 하면 epoch time이라고 하고 다른 말로 Unix timestamp라고 하는데 이는 컴퓨터 시스템에서 시간을 나타내는 방법 중 하나이다. 이는 1970년 1월 1일 00:00:00 UTC부터 현재까지 경과된 시간을 초 단위로 표현한 것이다. 즉, Unix 시간은 1970년 1월 1일 이후로 경과한 전체 초의 수로, 시간대에 영향을 받지 않는 절대적인 시간 표현방식이다. 참고로 Epoch라는 단어의 뜻은 어떤 중요한 사건이 발생한 시점을 기준으로 삼는 시작점을 뜻하는 요어이다. Instant 클래스는 이 Epoch 시간을 다루는 클래스이다.
41. Instant 클래스의 장점은 무엇인가? ⇒ Instant 클래스의 장점으로는 시간대 독립성과 고정된 기준점이라는 것이 있다. 전자는 UTC를 기준으로 하므로, 시간대에 영향을 받지 않는다. 이는 전 세계 어디서나 동일한 시점을 가리키는데 유용하다. 후자는 모든 Instant 클래스는 1970년 1월 1일 UTC를 기준으로 하기에 시간 계산 및 비교가 명확하고 인관된다는 것을 말한다.
42. Instant 클래스의 단점은 무엇인가? ⇒ Instant 클래스의 단점은 사용자 친화적이지 않고, 시간대 정보가 부재하다는 것이다. 전자는 Instant 클래스는 기계적인 시간 처리에는 적합하지만, 사람이 읽고 이해하기에는 직관적이지 않다. 예를 들어, 날짜와 시간을 계산하고 사용하는데 필요한 기능이 부족하다. 후자는 Instant 클래스에는 시간대 정보가 포함되어 있지 않기에 특정 지역의 날짜와 시간으로 변환하려면 추가적인 작업이 필요하다.
43. Instant 클래스의 예시로는 어떤 것이 있는가? ⇒ 첫 예시로, 전 세계적인 시간 기준이 필요할 경우, Instant 클래스는 UTC를 기준으로 하기에 전 세계적으로 일관된 시점을 표현할 때 사용하기 좋다. 예를 들어, 로그 기록이나 트랜잭션 타임스탬프, 서버 간의 시간 동기화 등이 이에 해당한다. 두 번째 예시로 시간대 변환 없이 시간 계산이 필요할 경우, 시간대의 변화 없이 순수하게 예를 들어, 지속 시간 계산처럼 시간의 흐름만을 다루고 싶을때 Instant 클래스가 적합하다. 이는 시간대 변환의 복잡성 없이 시간 계산이 가능하게 해준다. 세 번째 예시로는 데이터 저장 및 교환을 할 경우, DB에 날짜와 시간 정보를 저장하거나, 다른 시스템과 날짜와 시간 정보를 교환할 때 Instant 클래스를 사용하면, 모든 시스템에서 동일한 기준점인 UTC를 사용하게 되므로 데이터의 일관성을 유지하기 쉽다.
44. 일반적으로 날짜와 시간을 사용할 때는 뭘 사용하면 되는가? ⇒ 일반적으로 날짜와 시간을 사용할 때는 LocalDateTime 클래스와 ZonedDateTime 클래스 등을 사용하면 된다. Instant 클래스는 날짜를 계산하기 어렵기에 특별한 경우에 한정해서 사용하면 된다.
45. Instant 클래스를 통해 사용 가능한 메소드는 무엇인가? ⇒ now() 메소드, from() 메소드, ofEpochSecond() 메소드, plusSeconds() 메소드, getEpochSecond() 메소드가 있다.
46. Instant 클래스의 메소드인 now() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ Instant 클래스의 메소드인 now() 메소드는 UTC를 기준으로 현재 시간의 Instant를 생성한다.
47. Instant 클래스의 메소드인 from() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ Instant 클래스의 메소드인 from() 메소드는 다른 타입의 날짜와 시간을 기준으로 Instant를 생성한다. 참고로 Instant는 UTC를 기준으로 하기에 시간대 정보가 필요하다. 따라서 LocalDateTime를 사용할 수 없다.
48. Instant 클래스의 메소드인 ofEpochSecond() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ Instant 클래스의 메소드인 ofEpochSecond() 메소드는 에포크 시간을 기준으로 Instant를 생성한다. 0초를 선택하면 에포크 시간인 1970년 1월 1일 0시 0분 0초로 생성된다.
49. Instant 클래스의 메소드인 plusSeconds() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ Instant 클래스의 메소드인 plusSeconds() 메소드는 초를 더한다. 이는 초, 밀리초, 나노초 정도만 더하는 간단한 메소드이다.
50. Instant 클래스의 메소드인 getEpochSecond() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ Instant 클래스의 메소드인 getEpochSecond() 메소드는 에포크 시간인 UTC 1970년 1월 1일 0시 0분 0초를 기준으로 흐른 초를 반환한다. 여기서는 앞서 에포크 시간에 3600초를 더했기에 3600이 반환된다.
51. 시간의 개념은 크게 뭐와 뭐로 나뉘에 지는가? ⇒ 시간의 개념은 크게 특정 시점의 시간 즉, 시각과, 시간의 간격 즉, 기간으로 나뉠 수 있다. 전자의 예시로는 “이 프로젝트는 2013년 8월 16일까지 완료해야 해.”, “다음 회의는 11시 30분에 진행한다.”, “내 생일은 8월 16일이야.”처럼 들 수 있고, 후자는 “앞으로 4년은 더 공부해야 해.”, “이 프로젝트는 3개월 남았어.”,“라면은 3분 동안 끓어야 해.” 같은 것을 들 수 있다.
52. Period 클래스와 Duration 클래스는 무엇인가? ⇒ Period 클래스와 Duration 클래스는 시간의 간격, 즉, 기간을 표현하는데 사용된다. 참고로 시간의 간격은 amount of time이라고 불린다.
53. Period 클래스란? ⇒ Period 클래스는 두 날짜 사이의 간격을 년, 월, 일 단위로 나타낸다. 예를 들어, “이 프로젝트는 3개월 정도 걸릴 것 같아.”, “기념일이 183일 남았어.”, “프로젝트 시작일과 종료일 사이의 간격: 프로젝트 기간”를 들 수 있다. 
54. Period 클래스의 주요 클래스는 무엇인가? ⇒ Period 클래스의 주요 클래스는 getYear() 메소드, getMonths() 메소드, getDays() 메소드, of() 메소드가 있다.
55. Period 클래스의 of() 메소드는 무슨 기능을 가지고 있는가? ⇒ Period 클래스의 of() 메소드는 특정 기간을 지정해서 Period를 생성한다. of()의 매개변수로 년, 월, 일 순으로 적어주면 된다. 이 외에도 ofDays() 메소드, ofMonths() 메소드, ofYears() 메소드가 있다.
56. Period 클래스의 of() 메소드는 주로 어디에 쓰이는가? ⇒ 2030년 1월 1일에 10일을 더하면 2030년 1월 11일이 된다라고 표현할 때 특정 날짜에 10일이라는 기간을 더할 수 있다.
57. Period 클래스의 between(startDate, endDate) 메소드는 언제 사용하는가? ⇒ 예를 들어, 2023년 1월 1일과 2023년 4월 2일간의 차이는 3개월 1일이다.라고 표현할 때 특정 날짜의 차이를 구하면 기간이 된다. Period.between(startDate, endDate)와 같이 특정 날짜의 차이를 구하면 Period가 반환된다.
58. Duration 클래스란? ⇒ Duration 클래스는 두 시간 사이의 간격을 시, 분, 초, 나노초 단위로 나타낸다. 예를 들어, “라면을 끓이는 시간은 3분이야.”, “영화 상영 시간은 2시간 20분이야.”, “서울에서 부산까지는 4시간이 걸려”를 들 수 있다. 내부에서 초를 기반으로 시, 분, 초를 계산해서 사용하기에 1분은 60초, 1시간은 3600초를 사용하기도 한다.
59. Duration 클래스의 주요 클래스는 무엇인가? ⇒ Duration 클래스의 주요 클래스는 toHour() 메소드, toMinutes() 메소드, getSeconds() 메소드, getNano() 메소드, of() 메소드가 있다.
60. Duration 클래스의 of() 메소드는 어디에 쓰이는가? ⇒ Duration 클래스의 of() 메소드는 특정 시간을 지정해서 Period를 생성한다. of(지정) 형태이고, 이 외에도 ofSeconds() 메소드, ofMinutes() 메소드,  ofHours() 메소드가 있다.
61. Duration 클래스의 between(start, end) 메소드는 언제 사용하는가? ⇒ 예를 들어 9시와 10시의 차이는 1시간이라고 표현할 때 시간의 차이를 구할 수 있다. Duration.between(start, end) 처럼 특정 시간의 차이를 구하면 Duration이 반환된다.
62. 특정 시점의 시간 관련 최고 부모는 무엇인가? 또, 이에 속해 있는 자식은 무엇인가? ⇒ 특점 시점의 시간 관현 최고 부모는 TemporalAccessor 인터페이스이고 이를 구현하면 된다. 이에 아래로 Temporal 인터페이스가 있고 그 아래에 LocalDateTime 클래스, LocalDate 클래스, LocalTime 클래스, ZonedDateTime 클래스, OffsetDateTime 클래스, Instant 클래스 등이 있다.
63. 시간의 간격, 즉, 기간 관련 최고 부모는 무엇인가? 또, 이에 속해 있는 자식은 무엇인가? ⇒  시간의 간격, 즉, 기간 관련 최고 부모는 TemporalAmount 인터페이스이다. 이를 구현하는데 사용하고 자식으로 Period 클래스, Duration 클래스가 있다.
64. TemporalAccessor 인터페이스는 뭐하는 인터페이스인가? ⇒ TemporalAccessor 인터페이스는 날짜와 시간을 읽기 위한 기본 인터페이스이고, 이 인터페이스는 특정 시점의 날짜와 시간 정보를 읽을 수 있는 최소한의 기능을 제공한다.
65. Temporal 인터페이스는 뭐하는 인터페이스인가? ⇒ Temporal 인터페이스는 TemporalAccessor 인터페이스의 하위 인터페이스로, 날짜와 시간을 추가, 빼기 등의 조작을 하기 위한 기능을 제공한다. 이를 통해 날짜와 시간을 변경하거나 조정할 수 있다. 간단히 말해, TemporalAccessor 인터페이스는 읽기 전용 접근을, Temporal 인터페이스는 읽기와 쓰기 등의 조작 기능을 모두 지원한다.
66. TemporalAmount 인터페이스는 뭐하는 인터페이스인가? ⇒ TemporalAmount 인터페이스는 시간의 양이나 기간 등의 시간의 간격을 나타내고, 날짜와 시간 객체에 적용하여 해당 객체를 조정할 수 있다. 예를 들어, 특정 날짜에 일정 기간을 더하거나 빼는데 사용된다.
67. 시간의 단위와 시간 필드로는 무엇이 있는가? ⇒ 시간의 단위와 시간 필드로는 시간의 단위를 뜻하는 TemporalUnit(ChronoUnit)과 시간의 각 필드를 뜻하는 TemporalField(ChronoField)가 있다. 참고로 ChronoUnit과 ChronoField는 구현체이다.
68. TemporalUnit과 ChronoUnit은 무엇인가? ⇒ TemporalUnit 인터페이스는 날짜와 시간을 측정하는 단위를 나타내고, 주로 사용되는 구현체는 ChronoUnit 열거형으로 구현되어 있다. 참고로 ChronoUnit은 다양한 시간 단위를 제공하고 여기서 Unit은 단위를 뜻하며, 시간의 단위 하나하나를 나타낸다. ChronoUnit을 사용하면 두 날짜 또는 시간 사이의 차이를 해당 단위로 쉽게 계산할 수 있다.
69. ChronoUnit의 시간 단위로는 무엇이 있는가? ⇒ ChronoUnit의 시간 단위로는 NANOS, MICROS, MILLS, SECONDS, MINUTES, HOURS가 있다. NANOS는 나노초 단위, MICROS는 마이크로초 단위, MILLS는 밀리초 단위, SECONDS초 단위, MINUTES는 분 단위, HOURS는 시간 단위를 나타낸다. 
70. ChronoUnit의 날짜 단위로는 무엇이 있는가? ⇒ ChronoUnit의 날짜 단위로는 DAYS, WEEKS, MONTHS, YEARS, DECADES, CENTURIES, MILLENNIA가 있다. DAYS는 일 단위, WEEKS는 주 단위, MONTHS는 월 단위, YEARS는 년 단위, DECADES는 10년 단위, CENTURIES는 세기 단위, MILLENNIA는 천년 단위를 말한다.
71. ChronoUnit의 기타 단위로는 무엇이 있는가? ⇒ ChronoUnit의 기타 단위로는 ERAS, FOREVER가 있고 각각 시대 단위, 무한대의 시간 단위를 의미한다.
72. ChronoUnit의 주요 메소드로는 무엇이 있는가? ⇒ ChronoUnit의 주요 메소드로는 between(Temporal, Temporal) 메소드, isDateBased() 메소드, isTimeBased() 메소드, isSupportedBy(Temporal)메소드, getDuration() 메소드가 있다.
73. ChronoUnit의 주요 메소드인 between(Temporal, Temporal) 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoUnit의 주요 메소드인 between(Temporal, Temporal) 메소드는 두 Temporal 객체 사이의 시간을 현재 ChronoUnit 단위로 측정하여 반환한다.
74. ChronoUnit의 주요 메소드인 isDateBased() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoUnit의 주요 메소드인 isDateBased() 메소드는 현재 ChronoUnit이 예를 들어, 일, 주, 월, 년이라는 날짜 기반 단위인지 여부를 반환한다.
75. ChronoUnit의 주요 메소드인 isTimeBased() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoUnit의 주요 메소드인 isTimeBased() 메소드는 현재 ChronoUnit이 예를 들어, 시, 분, 초라는 시간 기반 단위인지 여부를 반환한다.
76. ChronoUnit의 주요 메소드인 isSupportedBy(Temporal)-메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoUnit의 주요 메소드인 isSupportedBy(Temporal) 메소드는 주어진 Temporal 객체가 현재 ChronoUnit 단위를 지원하는지 여부를 반환한다.
77. ChronoUnit의 주요 메소드인 getDuration() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoUnit의 주요 메소드인 getDuration() 메소드는 현재 ChronoUnit의 기간을 Duration 객체로 반환한다.
78. ChronoField는 뭐하는 것인가? ⇒ ChronoField는 날짜/시간을 나타내는데 사용되는 열거형이다. 이 열거형은 다양한 필드를 통해 날짜와 시간의 특정 부분은 나타낸다. 여기에는 연도, 월, 일, 시간, 분 등이 포함된다.
79. TemporalField 인터페이스는 뭐하는 인터페이스인가? ⇒ TemporalField 인터페이스는 날짜와 시간을 나타내는데 주용된다. 주로 사용되는 구현체는 ChronoField 열거형으로 구현되어 있다.
80. ChronoField란 무엇인가? ⇒ ChronoField는 다양한 필드를 통해 날짜와 시간의 특정 부분을 나타낸다. 여기에는 연도, 월, 일, 시간, 분 등이 포함된다. 여기서 Field, 즉, 필드는 날짜와 시간 중에 있는 특정 필드들을 뜻한다. 예를 들어, 2024년 8월 16일이라고 하면 YEAR 필드는 2024, MONTH_OF_YEAR 필드는 8, DAY_OF_MONTH 필드는 16이다. 단순히 시간의 단위 하나하나를 뜻하는 ChronoUnit과는 다르다. ChronoField를 사용해야 날짜와 시간의 각 필드 중에 원하는 데이터를 조회할 수 있다.
81. ChronoField의 연도 관련 필드는 무엇이 있는가? ⇒ ChronoField의 연도 관련 필드는 ERA, YEAR_OF_ERA, YEAR, EPOCH_DAY가 있다. ERA는 AD, 즉, 서기 또는 BC, 즉, 기원전 같은 연대를 나타내고, YEAR_OF_ERA는 연대 내의 연도를 말하며, YEAR는 연도를, EPOCH_DAY는 1970-01-01부터의 일 수를 의미한다.
82. ChronoField의 월 관련 필드는 무엇이 있는가? ⇒ ChronoField의 월 관련 필드는 MONTH_OF_YEAR, PROLEPTIC_MONTH가 있다. 각각 월, 연도를 월로 확장한 값을 나타낸다. 단, MONTH_OF_YEAR는 예를 들어, 1이 1월을 의미한다.
83. ChronoField의 주/일 관련 필드는 무엇이 있는가? ⇒ DAY_OF_WEEK, ALIGNED_DAY_OF_WEEK_IN_MONTH, ALIGNED_DAY_OF_WEEK_IN_YEAR, DAY_OF_MONTH, DAY_OF_YEAR, EPOCH_DAY가 있다. DAY_OF_WEEK는 요일을 말하고 참고로 1은 월요일을 말한다. ALIGNED_DAY_OF_WEEK_IN_MONTH는 월의 첫 번째 요일을 기준으로 정렬된 요일을 말한다. ALIGNED_DAY_OF_WEEK_IN_YEAR는 연의 첫 번째 요일을 기준으로 정렬된 요일을 말한다. DAY_OF_MONTH는 월의 일을 말하고 참고로 1이 1일을 말한다. DAY_OF_YEAR는 연의 일을 말하고 1이 1월 1일을 의미한다. EPOCH_DAY는 유닉스 에폭, 즉, 1970-01-01부터의 일수를 말한다.
84. ChronoField의 시간 관련 필드는 무엇이 있는가? ⇒ ChronoField의 시간 관련 필드는 HOUR_OF_DAY, CLOCK_HOUR_OF_DAY, HOUR_OF_AMPM, CCLOCK_HOUR_OF_AMPM, MINUTE_OF_HOUR, SECOND_OF_MINUTE, NANO_OF_SECOND, MICRO_OF_SECOND, MILLI_OF_SECOND가 있다. HOUR_OF_DAY는 0시부터 23시까지의 시간을 말하고, CLOCK_HOUR_OF_DAY는 1부터 24라는 시계 시간을 말한다. HOUR_OF_AMPM는 0부터 11이라는 오전/오후 시간, CLOCK_HOUR_OF_AMPM은 1부터 12라는 오전/오후 시계 시간을 말한다. MINUTE_OF_HOUR는 0부터 59까지의 분을, SECOND_OF_MINUTE는 0부터 59까지의 초를 말한다. NANO_OF_SECOND는 0부터 999,999,999라는 나노초, MICRO_OF_SECOND는 0부터 999,999라는 초의 마이크로초를 말한다. MILLI_OF_SECOND는 0부터 999까지의 초의 밀리초를 말한다.
85. ChronoField의 기타 필드는 무엇이 있는가? ⇒ ChronoField의 기타 필드로는 AMPM_OF_DAY, INSTANT_SECONDS, OFFSET_SECONDS가 있다. AMPM_OF_DAY는 하루의 AM?PM 부분을 말하고 INSTANT_SECONDS는 초를 기준으로 한 시간을 의미하여, OFFSET_SECONDS는 UTC/GMT에서의시간 오프셋 초를 의미한다.
86.  ChronoField의 주요 메소드는 뭐뭐가 있는가? ⇒ getBaseUnit() 메소드, getRRangeUnit() 메소드, isDateBased() 메소드, isTimeBased() 메소드, range() 메소드가 있다.
87. ChronoField의 주요 메소드인 getBaseUnit() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoField의 주요 메소드인 getBaseUnit() 메소드는 반환 타입이 TemporalUnit 타입이고, 피드의 기본 단위를 반환한다. 예를 들어, 분 필드의 기본 단위는 ChronoUnit.MINUTES이다.
88. ChronoField의 주요 메소드인 getRangeUnit() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoField의 주요 메소드인 getRangeUnit() 메소드는 반환 타입이 TemporalUnit 타입이고, 필드의 범위 단위를 반환한다. 예를 들어, MONTH_OF_YEAR의 범위 단위는 ChronoUnit.YEARS이다.
89. ChronoField의 주요 메소드인 isDateBased() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoField의 주요 메소드인 isDateBased() 메소드는 반환 타입이 boolean 타입이고, 필드가 주로 날짜를 기반으로 하는지 여부를 나타낸다. YEAR와 같은 날짜 기반 필드는 true를 반환한다.
90. ChronoField의 주요 메소드인 isTimeBased() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoField의 주요 메소드인 isTimeBased() 메소드는 반환 타입이 boolean 타입이고, 필드가 주로 시간을 기반으로 하는지 여부를 나타낸다. HOUR_OF_DAY 같은 시간 기반 필드는 true를 반환한다.
91. ChronoField의 주요 메소드인 range() 메소드는 어떤 기능을 제공하는 메소드인가? ⇒ ChronoField의 주요 메소드인 range() 메소드는 반환 타입이 ValueRange 타입이고, 이 메소드는 필드가 가질 수 있는 값의 유효 범위를 ValueRange 객체로 변환한다. 이 객체는 최속밧과 최대값을 제공한다.
92. TemporalUnit(chronoUnit)과 TemporalField(chronoFiled)는 주로 어떻게 사용하는가? ⇒ TemporalUnit(chronoUnit)과 TemporalField(chronoFiled)는 단독으로 사용하기 보다는 주로 날짜와 시간을 조회하거나 조작할 때 사용한다.
```