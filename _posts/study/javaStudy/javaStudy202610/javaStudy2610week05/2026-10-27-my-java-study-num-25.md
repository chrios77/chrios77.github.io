---
title: 26년 10월 5째주 자바 공부 25일차(동일성과 동등성/String 클래스/StringBuilder 클래스)
date: 2026-10-27 17:44:00 +0900
categories: [Study, Java]
tags: [Java]
published: true
---

<h1>26년 10월 5째주 Java 공부</h1>
<h2>26년 10월 27일 화요일 자바 공부</h2>
1. 오늘은 자바 중급 1편 23강에서 28강까지 수강했다.
2. 동일성과 동등성, String 클래스와 이에 정의된 메소드, StringBuilder 클래스와 이에 정의된 메소드에 대해 배웠다.
3. 금일 배운 내용과 어제까지 배운 내용을 토대로 AI에게 퀴즈를 내게 해 퀴즈를 풀었다.
4. 강의에서 제공하는 예제를 따라쳐봤다. 복습 시간에도 따라쳐보고 안 보고도 따라쳐봤다.
5. 금일한 내용에 대해 자바 이론책을 읽었다. 

```
1. String 클래스를 비교할 때는 뭘 사용해야 하는가? ⇒ equals()메소드. String 클래스를 비교할 때는 == 비교가 아니라 항상 equals()메소드로 비교해야 한다.
2. 동일성이란? ⇒동일성은 영어로 identity라고 하고 == 연산자를 사용해서 두 객체의 참조가 동일한 객체를 가리키고 있는지 확인한다.
3. 동등성이란? ⇒ 동등성은 영어로 Equality라고 하고 equals() 메소드를 사용하여 두 객체가 논리적으로 같은지 확인한다.
4. 문자열의 값이 리터럴인 경우 어찌되는가? ⇒ 예를 들어, String str = “hello”; 와 같이 문자열 리터럴을 사용하면 문자열 풀에서 “hello”라는 문자를 가진  String 인스턴스를 찾고 예를 들어, x003이라는 찾은 인스턴스의 참조를 반환한다. 또 String str4 = “hello”; 의 경우 “hello” 문자열 리터럴을 사용하므로 문자열 풀에서 str3과 같은 x003 참조를 사용한다. 문자열 풀 덕분에 같은 문자를 사용하는 경우 메모리 사용을 줄이고 문자를 만드는 시간도 줄어들기에 성능도 최적화할 수 있다.
5. 풀이란 뭘 말하는 것인가? ⇒ 풀은 영어로 pool를 말하고 이는 자원이 모여있는 곳을 의미한다. 프로그래밍에서 풀은 공용 자원을 모아둔 곳을 말하고 여러 곳에서 함께 사용할 수 있는 개체를 필요할 때마다 생성하고, 제거하는 것은 비효율적이기에 이렇게 문자열 풀에 필요한 String 인스턴스를 미리 만들어두고 여러 곳에서 재사용할 수 있다면 성능과 메모리를 더 최적화할 수 있다. 참고로 문자열 풀은 힙 영역을 사용한다. 그리고 문자열 풀에서 문자를 찾을 때는 해시 알고리즘을 사용하기에 매우 빠른 속도로 원하는 String 인스턴스를 찾을 수 있다.
6. 문자열 리터럴을 사용하면 == 비교를 하고, new String()을 직접 사용하는 경우에만 equals() 비교를 사용하면 되지 않은가? ⇒ 그렇게 하면 안된다. 항상 equals() 메소드를 활용해 비교해야 한다.
7. String 클래스는 불변 객체인가? O/X ⇒ O. String은 불변 객체이다. 따라서 생성 이후에 절대로 내부의 문자열 값을 변경할 수 없다. 또한, 변경이 필요한 경우 기존 값을 변경하지 않고, 대신에 새로운 결과를 만들어서 반환한다.
8. String 클래스의 concat() 메소드는 불변 객체를 어찌하는가? ⇒ concat() 메소드는 내부에서 새로운 String 객체를 만들어서 반환한다. 따라서 불변과 기존 객체의 값을 유지한다.
9. String이 불변으로 설계된 이유는 무엇인가? ⇒ String이 불변으로 설계된 이유는 앞서 불변 객체에서 배운 내용에다가 추가로 2개의 이유가 존재한다. 첫째, 문자열 풀에 있는 String 인스턴스의 값이 중간에 변경되면 같은 문자열을 참고하는 다른 변수의 값도 함께 변경된다. 둘쨰, String은 자바 내부에서 문자열 풀을 통해 최적화를 한다. 만약 String 내부의 값을 변경할 수 있다면, 기존에 문자열 풀에서 같은 문자를 참조하는 변수의 모든 문자가 함께 변경되는 문제가 발생한다.
10. String 클래스는 사이드 이펙트 문제가 발생하는가? 또 발생하지 않는다면 그 이유는 무엇인가? ⇒ String 클래스는 불변으로 설계되어 있기에 사이드 이펙트 문제가 발생하지 않는다.
11. String 클래스의 주요 메소드는 뭐에 따라 나뉘는가? ⇒ String 클래스는 문자열을 편리하게 다루기 위한 다양한 메서드를 제공한다. String 클래스의 주요 메소드는 문자열 정보 조회, 문자열 비교, 문자열 검색, 문자열 조작 및 반환, 문자열 분할 및 조합, 기타 유틸리티에 따라 나뉠 수 있다. 기능이 너무 많기에 메서드를 외우기 보다는 주로 사용하는 메소드가 이런 것이 있구나를 대략 알아두고 필요할 때 검색하거나 API 문서를 통해 원하는 기능을 찾는 것이 좋다.
12. 
13. String 클래스의 문자열 정보 조회 관련 메소드로는 뭐가 있는가? ⇒ length() 메소드, isEmpty() 메소드, isBlank() 메소드, charAt(int index) 메소드가 있다.
14. length() 메소드는 뭘 하는 메소드인가? ⇒ length() 메소드는 문자열의 길이를 반환한다.
15. isEmpty() 메소드는 뭘 하는 메소드인가? ⇒ isEmpty() 메소드는 문자열이 길이가 0으로 비어 있는지 확인한다.  
16. isBlank() 메소드는 뭘 하는 메소드인가? ⇒ isBlank() 메소드는 문자열이 길이가 0이거나 공백만 있는 경우처럼 비어 있는지 확인한다.
17. charAt(int index) 메소드는 뭘 하는 메소드인가? ⇒ charAt(int index) 메소드는 지정된 인덱스에 있는 문자를 반환한다.
18. String 클래스의 문자열 비교 관련 메소드로는 뭐가 있는가? ⇒ equals(Object anObject) 메소드, equalsIgnoreCase(String anotherString) 메소드, compareTo(String anotherString) 메소드, compareToIgnoreCase(String str) 메소드, startsWith(String prefix) 메소드, endsWith(String suffix) 메소드가 있다.
19. equals(Object anObject) 메소드는 뭘 하는 메소드인가? ⇒ equals(Object anObject) 메소드는 두 문자열이 동일한지 비교한다.
20. equalsIgnoreCase(String anotherString) 메소드는 뭘 하는 메소드인가? ⇒ equalsIgnoreCase(String anotherString) 메소드는 두 문자열을 사전 순으로 비교한다.
21. compareTo(String anotherString) 메소드는 뭘 하는 메소드인가? ⇒ compareTo(String anotherString) 메소드는 두 문자열을 대소문자 구분 없이 사전적으로 비교한다. 
22. compareToIgnoreCase(String str) 메소드는 뭘 하는 메소드인가? ⇒ compareToIgnoreCase(String str) 메소드는 문자열이 특정 접두사로 시작하는지 확인한다.  
23. startsWith(String prefix) 메소드는 뭘 하는 메소드인가? ⇒ startsWith(String prefix) 메소드는 문자열이 특정 접미사로 끝나는지 확인한다.
24. endsWith(String suffix) 메소드는 뭘 하는 메소드인가? ⇒ endsWith(String suffix) 메소드는 
25. String 클래스의 문자열 검색 관련 메소드로는 뭐가 있는가? ⇒ contains(CharSequence s) 메소드, indexOf(String ch) 메소드, indexOf(String ch, int fromIndex) 메소드, lastIndexOf(String ch) 메소드가 있다.
26. contains(CharSequence s) 메소드는 뭘 하는 메소드인가? ⇒ contains(CharSequence s) 메소드는 문자열이 특정 문자열을 포함하고 있는지 확인한다.
27. indexOf(String ch) 메소드는 뭘 하는 메소드인가? ⇒ indexOf(String ch) 메소드는 문자열이 처음 등장하는 위치를 반환한다.
28. indexOf(String ch, int fromIndex) 메소드는 뭘 하는 메소드인가? ⇒ indexOf(String ch, int fromIndex) 메소드는 문자열이 처음 등장하는 위치를 반환한다.
29. lastIndexOf(String ch) 메소드는 뭘 하는 메소드인가? ⇒ lastIndexOf(String ch) 메소드는 문자열이 마지막으로 등장하는 위치를 반환한다.
30. String 클래스의 문자열 조작 및 반환 관련 메소드로는 뭐가 있는가? ⇒ subString(int beginIndex) 메소드, subString(int beginIndex, int endindex) 메소드, concat(String str) 메소드, replace(CharSequence target, CharSequence replacement) 메소드, replaceAll(String regx, String replacement) 메소드, replaceFirst(String regex, String replacement) 메소드, toLowerCase() 메소드, toUpperCase 메소드, trim() 메소드, strip 메소드가 있다. 참고로 이 메소드들은 다 반환값을 줘야 한다.
31. subString(int beginIndex) 메소드는 뭘 하는 메소드인가? ⇒ subString(int beginIndex) 메소드는 문자열의 부부누 분자열을 반환한다.  
32. subString(int beginIndex, int endindex) 메소드는 뭘 하는 메소드인가? ⇒ subString(int beginIndex, int endindex) 메소드는 문자열의 부부누 분자열을 반환한다.
33. concat(String str) 메소드는 뭘 하는 메소드인가? ⇒ concat(String str) 메소드는 문자열의 끝에 다른 문자열을 붙인다. 
34. replace(CharSequence target, CharSequence replacement) 메소드는 뭘 하는 메소드인가? ⇒ replace(CharSequence target, CharSequence replacement) 메소드는 문자열에서 정규 표현식과 일치하는 부분을 새 문자열로 대체한다.
35. replaceAll(String regx, String replacement) 메소드는 뭘 하는 메소드인가? ⇒ replaceAll(String regx, String replacement) 메소드는 문자열에서 정규 표현식과 일치하는 부분을 새 문자열로 대체한다.
36. replaceFirst(String regex, String replacement) 메소드는 뭘 하는 메소드인가? ⇒ replaceFirst(String regex, String replacement) 메소드는 문자열에서 정규 표현식과 일치하는 첫 번째 부분을 새 문자열로 대체한다.
37. toLowerCase() 메소드는 뭘 하는 메소드인가? ⇒ toLowerCase() 메소드는 문자열을 소문자로 변환한다.
38. toUpperCase 메소드는 뭘 하는 메소드인가? ⇒ toUpperCase 메소드는 문자열을 대문자로 변환한다.
39. trim() 메소드는 뭘 하는 메소드인가? ⇒ trim() 메소드는 문자열 양쪽 끝의 공백을 제거 한다. 단순 공백만 제거할 수도 있다. 참고로 공백을 영어로 whitespace라 한다.
40. strip 메소드는 뭘 하는 메소드인가? ⇒ strip 메소드는 공백과 유니코드 공백을 포함해서 제거한다. 이는 자바 11때부터 생긴 것이다.
41. String 클래스의 문자열 분할 및 조합 관련 메소드로는 뭐가 있는가? ⇒ split(String regex) 메소드, join(CharSequence delimiter, CharSequence … elements) 메소드가 있다.
42. split(String regex) 메소드는 뭘 하는 메소드인가? ⇒ split(String regex) 메소드는 문자열을 정규 표현식을 기준으로 분할한다.
43. join(CharSequence delimiter, CharSequence … elements) 메소드는 뭘 하는 메소드인가? ⇒ join(CharSequence delimiter, CharSequence … elements) 메소드는 주어진 구분자로 여러 문자열을 결합한다.
44. String 클래스의 기타 유틸리티 관련 메소드로는 뭐가 있는가? ⇒ valueOf(Object obj)  메소드, toCharrArray() 메소드, format(String format, Object … args) 메소드, matches(String regex) 메소드가 있다.
45. valueOf(Object obj)  메소드는 뭘 하는 메소드인가?  ⇒ valueOf(Object obj)  메소드는 다양한 타입을 문자열로 변환한다. 
46. toCharrArray() 메소드는 뭘 하는 메소드인가?  ⇒ toCharrArray() 메소드는 문자열을 문자 배열로 변환한다.
47. format(String format, Object … args) 메소드는 뭘 하는 메소드인가? ⇒ format(String format, Object … args) 메소드는 형식 문자열과 인자를 사용하여 새로운 문자열을 생성한다.
48. matches(String regex) 메소드는 뭘 하는 메소드인가?  ⇒ matches(String regex) 메소드는 문자열이 주어진 정규 표현식과 일치하는지 확인한다.
49. CharSequence는 무엇인가? ⇒ CharSequence는 String, StringBuilder의 상위 타입이다. 문자열을 처리하는 다양한 객체를 받을 수 있다.
50. String 클래스의 단점은 무엇인가? ⇒ 불변인 String 클래스의 단점은 문자를 더하거나 변경할 때마다 계속해서 새로운 객체를 생성해야 한다는 것이다.  문자를 자주 더하거나 변경해야 하는 상황이라면 더 많은 String 객체를 만들고, GC해야 한다. 결과적으로 컴퓨터의 CPU, 메모리의 자원을 더 많이 사용하게 된다. 그리고 문자열의 크기가 클수록, 문자열을 더 자주 변경할수록 시스템의 자원을 더 많이 소모한다.
51. String 클래스의 단점을 해결하는 방법은 무엇인가? ⇒ 가변 String이 존재하면 된다. 가변은 내부의 값을 바로 변경하면 되기에 새로운 객체를 생성할 필요가 없다. 그러므로 성능과 메모리의 사용면에서 불변보다 더 효율적이다. 이를 위해 자바에서는 StringBuilder이라는 가변 String 클래스를 제공한다. 물론 가변의 경우 사이드 이펙트에 주의해서 사용해야 한다. 
52. StringBuilder 클래스는 내부에 final이 아닌 변경할 수 있는 byte[] 을 가지고 있다. 자바 9 이전에는 char[] value 였고 자바 9 이후에는 byte[] value 형태였다. 자세한 건 API 도큐먼트를 확인하면 된다.
53. StringBuilder 클래스는 어떤 메소드를 제공하는가? ⇒ StringBuilder 클래스는 append 메소드(), insert() 메소드, delete() 메소드, reverse() 메소드, toString() 메소드 등을 제공한다.
54. append 메소드()는 뭘 하는 메소드인가? ⇒ append 메소드()는 여러 문자열을 추가한다. 
55. insert() 메소드는 뭘 하는 메소드인가? ⇒ insert() 메소드는 특정 위치에 문자열을 삽입한다.
56. delete() 메소드는 뭘 하는 메소드인가? ⇒ delete() 메소드는 특정 범위의 문자열을 삭제한다.
57. reverse() 메소드는 뭘 하는 메소드인가? ⇒ reverse() 메소드는 문자열을 뒤집는다.
58. toString() 메소드는 뭘 하는 메소드인가? ⇒ toString() 메소드는 StringBuilder의 결과를 기반으로 String을 생성해서 반환한다.
59. 가변 String vs 불변 String ⇒ String은 불변하다. 즉, 한 번 생성되면 그 내용을 변경할 수 없다. 따라서 문자열에 변화를 주려고 할 때마다 새로운 String 객체가 생성되고, 기존 객체는 버려진다. 이 과정에서 메모리와 처리 시간을 더 많이 소모한다. 반면, StringBuilder는 가변적이다. 하나의StringBuilder 객체 안에서 문자열을 추가, 삭제, 수정할 수 있고, 이 때마다 새로운 객체를 생성하지 않는다. 이로 인해 메모리 사용을 줄이고 성능을 향상시킬 수 있다. 단 사이드 이펙트를 주의해야 한다. 
60. StringBuilder을 어떨 때 사용하다가 String으로 변환하는 것이 좋은가? ⇒ StringBuilder는 보통 문자열을 변경하는 동안만 사용하다가 문자열 변경이 끝나면 안전하게 불변 String으로 변환하는 것이 좋다.
61. String 최적화는 자바에서 어떤가? ⇒ String 최적화는 자바가 최적화를 처리해주기에 간단한 경우에는 StringBuilder를 사용하지 않아도 된다. 대신에 문자열 더하기 연산을 사용하면 충분하다. 참고로 자바 9부터는 StringConcatFactory를 사용해 최적화를 수행한다.
62. String 최적화가 어려운 경우는 무엇인가? ⇒ 문자열을 반복문 안에서 문자열을 더하는 경우에는 String 최적화가 이루어지지 않는다. 왜냐하면 반복문의 루프 내부에서는 최적화가 되는 것처럼 보이지만, 반복 횟수만큼 객체를 생성해야 한다. 반복문 내에서의 문자열 연결은 런타임에 연결할 문자열의 개수와 내용이 결정된다. 이런 경우 컴파일러는 얼마나 많은 반복이 일어날지, 각 반복에서 문자열이 어떻게 변할지 예측할 수 없다. 그러므로 이 상황에서는 최적화가 어렵다.
63. StringBuilder를 직접 사용하는 것이 더 좋은 경우는 무엇인가? ⇒ StringBuilder를 직접 사용하는 것이 더 좋은 경우는 첫째, 반복문에서 반복해서 문자를 연결할 때, 둘째, 조건문을 통해 동적으로 문자열을 조합할 때, 셋째, 복잡한 문자열의 특정 부분을 변경해야 할 때, 넷째, 매우 긴 대용량 문자열을 다룰 때이다.
64. StringBuilder vs StringBuffer ⇒ StringBuilder와 똑같은 기능을 수행하는 StringBuffer 클래스도 있다. StringBuffer 클래스는 내부에 동기화가 되어 있어서, 멀티 스레드 상황에 안전하지만 동기화 오버헤드로 인해 성능이 느리다. StringBuilder는 멀티 스레드 상황에 안전하지 않지만 동기화 오버헤드가 없기에 속도가 빠르다. StringBuffer와 동기화에 관한 내용은 멀티 스레드를 학습해야 이해할 수 있다. 지금은 이런 것이 있구나 정도만 알아두자.
```