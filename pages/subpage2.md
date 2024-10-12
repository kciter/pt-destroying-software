---
title: 파괴 주도 개발
layout: section
subject: 파괴 주도 개발
---

<!--
그래서 저는 파괴 주도 개발이라는 것을 떠올렸습니다. 굉장히 거창하죠?
-->

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# <danger>파괴</danger>는 안좋은 것일까?

<!--
일단 파괴라는 말이 들어가니 굉장히 부정적으로 보입니다. 그렇지만 파괴는 안좋은걸까요?
-->

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/ramen.jpg" width="220px" />

<!--
하지만 파괴가 없다면 새로운 것은 탄생할 수 없습니다. 그것만으로 파괴는 충분히 좋은 방향으로 이끌 수 있습니다.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 소프트웨어를 파괴하는 두 가지

* 기능을 삭제하는 것 / Pivoting
  * 피벗은 제품이 더 좋은 길로 나아갈 수 있는 <accent>기회</accent>
* 같은 기능을 다시 만드는 것 / Refactoring
  * 리팩터링은 소프트웨어의 <accent>생명을 연장</accent>시키는 일
  * 리팩터링이 필요한 이유는 <accent>경제성</accent>
  * 많은 기능을 빠르게 추가하기 위함

<!--
소프트웨어에서 일어나는 파괴 두 가지를 살펴봅시다.
첫 번째는 기능을 삭제하는 것입니다. 기능을 완전히 삭제할 수도 있고 다른 기능으로 재구현할 수도 있습니다. 이는 비즈니스 용어로 피벗이라 할 수 있습니다.
피벗은 마음아프지만 제품이 더 좋은 길로 나아갈 수 있는 기회를 부여합니다.

두 번째는 같은 기능을 다시 만드는 것입니다. 우리가 잘아는 리팩토링이죠. 리팩토링은 소프트웨어의 생명을 연장시키는 행위입니다. 오래 살아남기 위해선 안해서는 안될 꼭 필요한 일이죠.
-->

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 다행히 나 혼자만의 생각은 아님

<!--
솔직히 저만 이런 주장을 한다면 신뢰성도 없고 저 또한 불안했을 겁니다.
그런데 다행히 저 혼자만 이런 생각을 한건 아니더라구요.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# Greg Young - The Art of Destroying Software

* Big ball of mud paper. It argues that the big ball of mud is inevitable.<br />The way to tackle it is to create pockets of smaller ball of muds. You have to write code for the purpose of deleting it.
* Make your system easier to delete than to change
* Don’t plan for future changes, focus on the ability to rewrite from scratch when changes happen.
* https://www.youtube.com/embed/1FPsJ-if2RU?si=00mBh99JDY7EMgi7

<!--
이벤트 소싱으로 유명한 그렉 영은 소프트웨어를 파괴할 수있는 단위로 작업해야 한다고 주장했습니다.

그리고 변경에 대비하지말고 변경이 발생했을 때 처음부터 다시 만들 수 있게 만들라고 했습니다.

발표 영상을 보면 비슷한 말을 계속 반복하지만 아마 제 생각엔, 이벤트 소싱 아키텍처는 이런 상황에서 좋다는 점을 말하려고 했던 것 같습니다.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# Five Lines of Code

* 시스템에는 어느 정도 오래 지속되는 코드가 필요합니다. 도메인의 복잡성에 따라 그 필요한 양은 다릅니다.<br />그러나 이번 장에서 단 한 가지만 말하라면 바로 '적은 것이 더 낫다'입니다.
* 9.1. 다음 시대는 코드를 지우는 시대일 것이다
* 우리는 아직 코드 삭제에 익숙하지 않습니다. 나는 이것이 다음에 해결해야 할 큰 과제라고 생각합니다.

<img src="/five-lines-of-code.jpeg" width="200px" style="position: absolute; right: 20px; bottom: 20px;" />

<!--
파이브 라인스 오브 코드에서는 아얘 코드 삭제의 미학이라는 챕터가 있습니다.
저자는 다음 시대는 코드를 지우는 시대일 것이라 말하며 이에 대비해야 한다고 말합니다.
이 외에도 검색을 해보면 deletibility에 집중하면 좋다는 포스팅이나 발표자료가 있습니다. 그런 주장을 보니 조금 든든한 느낌이 들더라구요.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 파괴 지향 개발?

* 언젠가 코드가 파괴될 것이라는 사실을 받아들이고, 그것을 지향하여 개발하는 방법론
* 세 원칙
  * 불확실성이 있는 것과 없는 것을 파악한다.
  * 여러 방법을 선택할 수 있다면 파괴하기 쉬운 쪽을 선택한다.
  * 필요한 것만을 유지한다. 따라서 필요 없는 것은 전부 지운다.
* 복잡성을 인지할 수 있는 것과 아닌 것으로 구분하는 것이 중요
* 아직 발전 중

<!--
그럼 다시 본론으로 넘어와 파괴 지향 개발이 뭘까요?
그건 화면에 써놓은대로 언젠가 코드가 파괴될 것이라는 것을 사실로 받아들이고 그것을 지향하여 개발하는 방법론입니다.
원칙도 심플하게 세가지 밖에 없습니다.



물론 이는 발표를 준비하던 당시 제가 생각한 것이기 때문에 한참 발전 중입니다. 언제든지 바뀔 수 있다는 뜻이죠. 생각해보니 방법론조차 파괴될 수 있다니 좀 심하긴 하네요.
-->

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/destruction-oriented-development-process.png" />

<!--
프로세스를 살펴보면 화면과 같습니다.

먼저 분석하고, 그에따라 경계를 분리하고, 구현합니다. 마지막으로 복잡성을 제거합니다.
그리고 이를 반복하는 피드백 루프를 진행합니다.

아주 간단하죠? 하나씩 살펴보겠습니다.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 경계 분리

* 불확실성이 높은 것과 낮은 것을 <accent>분리</accent>하는 것이 중요
* **변화율 = 불확실성**
* 변화율을 측정하는 방법
  * 기능이 실험적인가?
  * 기능이 릴리즈 되었는가?
  * 고객의 반응이 어떤가?
  * 기능이 릴리즈된 후 얼마나 지났는가?
  * 기능이 복잡한가?
  * 적절한 지식과 경험이 있는 상태에서 만들었는가?
  * 코드에 신뢰성이 있는가?
  * 코드를 이해할 수 있는가?
  * 목표 성능을 달성했는가?

<!--
먼저 경계를 어떻게 분리할지를 생각해야합니다.
이는 변화율을 기반으로 분리하는 것이 가능합니다.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 무엇부터 분리할까?

* 분리 단위
  * 애플리케이션, 모듈, 유즈케이스, 클래스, 컴포넌트, 메서드 등
  * 무엇을 기준으로 분리할 것인지 **추상화 레벨**을 결정해야 한다.
* 복잡한 비즈니스 로직일 수록 변화율이 높다.
* 기능은 시간이 지날 수록 변화율이 높아진다.
* 지원 서브 도메인에 가까울 수록 변화율이 낮다.
  * 비즈니스를 지원하는 활동
  * 계정 관리, 이메일 발송, 로깅, 모니터링 등
* 독립적으로 존재할 수 있다면 분리할 수 있다.
  * 인터페이스 만으로 통신할 수 있게 만들어야 한다.
* 불확실성을 측정할 수 없다면 억지로 분리하지 않는다.
  * 큰 단위에선 분리하지 않더라도 불확실성을 판단할 수 있는 추상화 단위에서 분리한다.

<!--
그럼 무엇부터 분리하는게 좋을까요? 그건 따져봐야 합니다.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 파괴하기 쉽게 만들기

* Make the change easy, then make the easy change - Kent Beck
* 파괴하기 쉽다는 것은 어떻게 측정하는가?

<!--
다음으로 나눴다면 구현을 해야합니다.
이때도 파괴하기 쉽도록 만들 필요가 있습니다. 그런데 파괴하기 쉽다는 것은 어떻게 측정하나요?
-->

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="destructible.png" width="400px" />

<!--
저는 세가지로 판단할 수 있다고 생각했습니다.
각각 독립성, 인지가능성, 통제가능성입니다. 이를 종합하여 파괴가능성을 판단할 수 있다는 의미입니다.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 파괴 가능성

* 독립성
  * 결합도와 응집도
  * 단일 책임 원칙
* 인지가능성
  * 코드를 인지할 수 있는가?
  * 코드의 가독성
* 통제가능성
  * 내가 통제할 수 있는 영역인가?
  * 코드오너쉽
  * 코드의 신뢰성
  * 코드의 사회성

<!--
좀 더 풀어써보면 이렇습니다.
-->

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 복잡성 제거

* 사용하지 않는다면 코드베이스에 지워라
  * 추억과 애정이 담긴 코드여도 예외는 없다
  * T) 어차피 커밋 로그에 남아있으니까 복구 가능~
* 파괴 가능성이 낮은 코드는 리팩터링하거나 다시 만들어라
  * 시간이 부족하거나 불확실성이 높다면 주석을 남긴 후 나중에 처리한다.
* **최대한 단순성을 유지하는 것이 핵심**

<img src="/kondo-marie.jpg" width="200px" style="position: absolute; right: 20px; bottom: 20px;" />

<!--
좀 더 풀어써보면 이렇습니다.
-->

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/talk-is-cheap.jpg" width="440px" />

<!--
사실 관리하는 방법론이기 때문에 코드가 중요한 것은 아닙니다.
그래도 슬슬 코드를 봐야겠죠? 리누스 토발즈의 명언 한 번 보고가겠습니다.
-->
