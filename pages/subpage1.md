---
title: 발단
layout: section
subject: 발단
---

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 항상 나를 괴롭히던 고민

* 코딩으로 밥벌이를 한지 벌써 10년이 넘었지만...
  * 어째서 아직도 무언가를 <accent>완성하는 것</accent>이 어렵게 느껴지는가?
  * 아직도 지식과 경험이 부족한 것인가?
  * 아니면 무언가 놓치고 있는 것인가?
* 개발이 <accent>어렵게 느껴지는 이유</accent>는 무엇인가?
  * 구현이 어려운 것 같지는 않은데...

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 아주 작은 깨달음
## 소프트웨어 개발이 정말 어려운 이유는 <accent>많은 것이 애매모호</accent>하기 때문

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 무엇이 소프트웨어 개발을 애매모호하게 만드는걸까?

* 서로 다른 지식 수준
* 도메인에 대한 이해
* 추상화 수준
* 급변하는 비즈니스
* 요구사항의 변화
* 올바른 구현 여부

<img src="/thinking-face.webp" width="180px" style="position: absolute; right: 40px; bottom: 40px;" />

---
layout: two-cols
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

::left::

# 구현에서의 애매모호함

* 서로 다른 지식 수준
* 도메인에 대한 이해
* 추상화 수준

::right::

# 외부에서의 애매모호함

* 급변하는 비즈니스
* 요구사항의 변화

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 애매모호함으로 인해 확신할 수 없다

## 그렇기 때문에 우리는 <danger>삭제할 수 밖에 없는 코드</danger>를 만들게 된다

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 소프트웨어를 파괴하는 두 가지

* 기능의 삭제 (Deletion) / Pivot
* 기존 기능을 다시 만드는 것 (Replacement) / Refactoring

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 어째서 이런 일이 발생하는걸까?

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<!-- <img src="/chaos.webp" width="240px" style="margin: 0 auto" /> -->

# **첫 번째는 비즈니스라는 괴물이 존재하기 때문!**

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 비즈니스라는 괴물

* 아무리 잘 설계해도 비즈니스는 급변한다.
  * 가설은 언제나 틀릴 수 있다.
  * 요구사항이 변경되는 것은 당연하다.
  * 경쟁자는 기다려주지 않는다.
  * 도메인 지식 또한 계속 변한다.
* 따라서 개발자의 예측은 높은 확률로 틀릴 수밖에 없다.
  * 확장에 대한 대응이 무의미해질 수 있다.
  * 아키텍처가 적합하지 않아질 수 있다.
  * 공든 탑이 무너지는 슬픔...
  * <danger>지우는 것조차 어려워질 수 있다.</danger>

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<!-- <img src="/chaos.webp" width="240px" style="margin: 0 auto" /> -->

# **두 번째는 개발자 개인의 지식과 경험의 문제**

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 지식과 경험의 문제

* 리팩터링을 하기에 가장 좋은 시기는 어떻게 고쳐야할지 정확하게 알 때이다.
  * 리팩터링은 지식과 경험에 기반한 <accent>기술</accent>이다.
  * 지식이 없다면 어떻게 고쳐야할지 알 수 없다.
  * 경험이 없다면 어떻게 접근해야할지 알 수 없다.
* 아이러니하게도 정확한 지식과 경험이 있다면 시간이 부족하더라도 처음부터 좋은 코드가 나온다.
  * 리팩터링은 구현하던 시기에 지식과 경험이 부족했기 때문에 해야하는 기술부채

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 이 둘을 피할 수 있을까?

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 결국 <danger>파괴</danger>는 항상 발생하는 것...

## 그런데 파괴는 안좋은 것일까?

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/ramen.jpg" width="220px" />


---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/1FPsJ-if2RU?si=00mBh99JDY7EMgi7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

**Greg Young - The Art of Destroying Software**

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/five-lines-of-code.jpeg" width="240px" />

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 이런 의견이 나오는 것은 자연스러운 일

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/myth.png" width="540px" style="margin: 0 auto;" />

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 애초에 잘 지울 수 있도록 만든다면?!

* 애매모호한 그렉 영의 발표
  * 그래서 어떻게 지워야 하는가?
  * 일주일치 작업이 어느정도인가?
  * 천 줄 이상의 코드를 배포해야 한다면?
  * 마이크로서비스 아키텍처가 아니라면?
