---
title: 코드 파괴의 기술
layout: section
subject: 코드 파괴의 기술
---

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 어떤 코드가 파괴하기 쉬울까?

* 변화율 기록하기
* 코드 가독성 끌어올리기
* 단계 분리하기
* 참조 투명성
* 단일 책임 원칙
* 인터페이스 분리 원칙
* 스트랭글러 무화과 패턴
* 메서드 전문화
* 중복 코드 작성
* **확장을 대비하기 보다 파괴에 대비한다라는 사고 방식이 중요**

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 변화율 기록하기

* 변화율이 높을 것다고 예상되는 코드엔 **주석**을 남긴다.
* 추후 정리하거나 다른 개발자가 확인할 때 편하다.

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 코드 가독성 끌어올리기

* 성능 이슈가 없다면 선형적, 선언적으로 작성해야 한다.
* 선형적이고 선언적일 수록 가독성이 높아진다.
* 가독성이 낮으면 불안감에 삭제하기 힘들어진다.

---
layout: two-cols
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

::left::
# 🟢 
```kotlin
// 위에서 아래로 한 번만 읽으면 된다
fun binaryToDecimal(input: String): Int {
  return input
    .reversed()
    .mapIndexed { index, char ->
      if (char == '1') {
        2.0.pow(index).toInt()
      } else {
        0
      }
    }
    .sum()
}
```

::right::
# 🔴

```kotlin
// 루프를 머리에서 연산해야 한다
fun binaryToDecimal(input: String): Int {
  var decimal = 0
  var binary = input
  var power = 0

  while (binary.isNotEmpty()) {
    val lastChar = binary.last()
    binary = binary.dropLast(1)
    if (lastChar == '1') {
      decimal += 2.0.pow(power).toInt()
    }
    power += 1
  }
  
  return decimal
}
```

---
layout: two-cols
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

::left::
# 🟢 
```kotlin
// 함수명에서 의도를 바로 파악할 수 있다.
fun generateSequentialNumber(count: Int): Sequence<Int> {
  return generateSequence(1) { it + 1 }
    .take(count)
}

fun main() {
  print(
    generateSequentialNumber(10)
      .filterOdd()
      .sum()
  )
}
```

::right::
# 🟡

```kotlin
// 내용을 한 번 더 읽어야 한다.
fun main() {
  print(
    generateSequence(1) { it + 1 }
      .take(10)
      .filter { it % 2 == 1 }
      .fold(0) { a, b -> a + b }
  )
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 단계 분리하기

* 주로 프로그래밍 로직은 대체로 단계로 나눠서 작성하는 것이 가능
  * 대부분의 로직이 전처리, 계산, 후처리와 같은 형태를 지닌다.
* 단계를 분리하면 필요한 부분만 재작성이 가능하다.

---
layout: two-cols
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

::left::
# 🟢 
```kotlin
// 전처리, 계산, 후처리가 분리되어 있다
fun makeFibonacciList(n: Int): List<Int> {
  val list = mutableListOf(0, 1)
  for (i in 2 until n) {
    list.add(list[i - 2] + list[i - 1])
  }
  return list
}

fun listSum(list: List<Int>): Int {
  return list.sum()
}

fun main() {
  val list = makeFibonacciList(10) // 데이터 생성
  val sum = list.sum() // 로직
  print(sum) // 출력
}
```

::right::
# 🔴

```kotlin
// 전처리, 계산, 후처리가 섞여있다
fun fibonacciSum(n: Int): Int {
  var sum = 0
  var a = 0
  var b = 1
  var c = 0
  for (i in 0 until n) {
    // 데이터 생성과 동시에 계산
    if (i <= 1) {
      sum += i
    } else {
      c = a + b
      sum += c
      a = b
      b = c
    }
  }
  return sum
}

fun main() {
  print(fibonacciSum(10)) // 출력
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 참조 투명성 보장

* 같은 입력에 대해 항상 같은 출력을 보장하는 것
* 순수 함수, 불변 객체 등
* **코드 신뢰성**과 관련이 있다.
* 만약 지켜지지 않았는데 코드가 잘 작동한다면..? 😱
  * 영향을 미치는 모든 곳이 불확실해진다.
  * 함부로 건들면 결함이 생길지도 모른다는 불안감이 생겨 삭제하기 힘들어진다.
* 최소한 멱등성이라도 지녀야 한다.

---
layout: two-cols
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

::left::

# 🟢
```kotlin
// 순수 함수
fun factorial(n: Int): Int {
  if (n == 0) {
    return 1
  }
  return n * factorial(n - 1)
}
```

<spacer gap="10" />

```kotlin
// 사이드 이펙트가 있지만 멱등성을 지닌 함수
val cache = mutableMapOf<Int, Int>()
fun factorial(n: Int): Int {
  if (n == 0) {
    return 1
  } else if (cache.containsKey(n)) {
    return cache[n]!!
  }
  val result = n * factorial(n - 1)
  cache[n] = result
  return result
}
```

::right::

# 🔴

```kotlin
// 참조 투명성이 없는 함수
var result = 1
fun factorial(n: Int): Int {
  if (n == 0) {
    return result
  }
  result *= n
  return factorial(n - 1)
}

// 나중에 result 변수가 변경된다면..?
```


---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 단일 책임 원칙

* 가장 이해하기 쉬우면서 가장 적용하기 어려운 원칙
* **단일 책임의 기준**이 무엇인가?
* 요구사항을 잘 이해할 필요가 있음

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 다음 코드는 단일 책임 원칙을 지키는가?

```kotlin
class UserInfo {
  val userId: Long
  val userName: String
  val email: String
  val telephone: String
  val provinceAddress: String // 도
  val cityAddress: String // 시
  val regionAddress: String // 구
  val detailAddress: String // 상세 주소
  val avatarUrl: String
  val createdAt: OffsetDateTime
  val updatedAt: OffsetDateTime
  val lastLoginAt: OffsetDateTime
}
```

* 두 가지 견해가 있을 수 있다.
  * 🙆‍♂️ 사용자와 관련된 정보가 포함되어 있고 모든 속성과 메서드가 사용자와 같은 비즈니스 모델에 속해 있어 만족한다.
  * 🙅‍♂️ 주소 정보와 시간 정보에 대한 비율이 상대적으로 크기 때문에 UserAddress로 분리할 수 있어 책임을 분리할 수 있다.
  * 요구사항에 따라 다르다!

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 인터페이스 분리 원칙

* 클라이언트는 필요하지 않은 인터페이스에 의존하면 안된다.
  * 클라이언트는 인터페이스 호출자
* 인터페이스 계의 단일 책임 원칙
* **기능을 제거할 필요가 있다면 인터페이스를 지우기만 하면 된다.**

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/huge-inheritance-tree.png" width="700px" />

# 삭제하기 힘든 설계

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/isp.png" width="700px" />

# 만약 인터페이스를 분리해서 만든다면?

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

```kotlin
interface Bird {
  fun fly()
  fun walk()
  fun swim()
}

class Sparrow : Bird {
  override fun fly() = // ...
  override fun walk() = // ...
  override fun swim() = // ...
}

class Penguin : Bird {
  override fun fly() = // ...
  override fun walk() = // ...
  override fun swim() = // ...
}

class Ostrich : Bird {
  override fun fly() = // ...
  override fun walk() = // ...
  override fun swim() = // ...
}
```


---
layout: two-cols
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

::left::
```kotlin
interface Flyable {
  fun fly()
}

interface Walkable {
  fun walk()
}

interface Swimmable {
  fun swim()
}
```

::right::
```kotlin
class Sparrow : Flyable, Walkable {
  override fun fly() = // ...
  override fun walk() = // ...
}

class Penguin : Walkable, Swimmable {
  override fun walk() = // ...
  override fun swim() = // ...
}

class Ostrich : Walkable {
  override fun walk() = // ...
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 잘 작동하는 코드 교체하기

* 스트랭글러 무화과 패턴 (Strangler pig pattern)
  * https://martinfowler.com/bliki/StranglerFigApplication.html
* 레거시 코드를 교체할 때 사용하는 패턴
  * 레거시 코드 일부를 새로운 코드로 교체
  * 안정화 기간이 지난 후 대체된 레거시 코드를 제거
  * 반복
* **기존 코드를 교체하는 것이 아니라 새로운 코드를 추가하고 기존 코드를 감싸는 방식**

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 스트랭글러 무화과 패턴

## Step 1

<spacer gap="10" />

```kotlin
class LegacyCode {
  fun oldMethod1() {
    // ...
  }

  fun oldMethod2() {
    // ...
  }
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 스트랭글러 무화과 패턴

## Step 2

<spacer gap="10" />

```kotlin
class LegacyCode {
  fun oldMethod1() {
    // ...
  }

  fun oldMethod2() {
    // ...
  }
}

class NewCode {
  private val legacyCode = LegacyCode()

  fun newMethod1() {
    // ...
  }

  fun oldMethod2() {
    legacyCode.oldMethod()
  }
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 스트랭글러 무화과 패턴

## Step 3

<spacer gap="10" />

```kotlin
class NewCode {
  fun newMethod1() {
    // ...
  }

  fun newMethod2() {
    // ...
  }
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 스트랭글러 무화과 패턴

## Step 2

<spacer gap="10" />

```kotlin
class LegacyCode {
  fun oldMethod1() {
    // ...
  }

  fun oldMethod2() {
    // ...
  }
}

class NewCode {
  private val legacyCode = LegacyCode()

  fun newMethod1() {
    // ...
  }

  fun oldMethod2() {
    legacyCode.oldMethod()
  }
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 메서드 전문화

* 메서드의 일반화를 줄이고 더 특정한 목적을 가지도록 하는 것
* 개발자의 본능을 거스르는 일
* 분리되는 만큼 삭제하기 편하다.

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 메서드 전문화

## Step 1

<spacer gap="10" />

```kotlin
fun udpateUser(userId: Long, email: String, telephone: String, address: Address) {
  // ...
}
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 메서드 전문화

## Step 2

<spacer gap="10" />

```kotlin
fun updateUserEmail(userId: Long, email: String) {
  // ...
}

fun updateUserTelephone(userId: Long, telephone: String) {
  // ...
}

// ...
```

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 중복 코드 작성

* 변화율이 높은 곳에선 일부러 중복 코드를 작성한다.
  * 둘 중 하나는 분명 변경될 것이라는 확신이 있을 때
  * 개발자의 경험과 직관에 따라 선택
* 개발자의 본능을 매우 거스르는 일... 😱
  * 따라서 예제 코드는 작성하지 않겠다...
