---
title: 불확실성에 대항하기
layout: section
subject: 불확실성에 대항하기
---

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 이런 <accent>고민</accent>을 해본 적 있나요?

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 소프트웨어 개발은 너무 많은 것이 <accent>애매모호</accent>하다

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 항상 나를 괴롭히던 고민

* 코딩으로 밥벌이를 한지 벌써 10년이 넘었지만...
  * 어째서 아직도 무언가를 <accent>완성하는 것</accent>이 어렵게 느껴지는가?
  * 아직 지식과 경험이 부족한 것인가?
* 애매모호함 앞에서 겸손해지는 나...

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 아주 작은 깨달음
소프트웨어 개발이 정말 어려운 이유는 <danger>많은 것이 불확실</danger>하기 때문

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# <danger>무엇</danger>이 소프트웨어 개발을 <danger>불확실</danger>하게 만드는걸까?

<img src="/thinking-face.webp" width="180px" style="position: absolute; right: 40px; bottom: 40px;" />

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 큰 이유 - 비즈니스라는 괴물

* 아무리 잘 설계해도 비즈니스는 급변한다.
  * 가설은 언제나 틀릴 수 있다.
  * 요구사항이 변경되는 것은 당연하다.
  * 경쟁자는 기다려주지 않는다.
  * 도메인 지식 또한 계속 변한다.
* 따라서 개발자의 예측은 높은 확률로 틀릴 수밖에 없다.
  * 확장에 대한 대응이 무의미해질 수 있다.
  * 아키텍처가 적합하지 않아질 수 있다.
  * 공든 탑이 무너지는 슬픔...
  * 내가 작성한 코드는 순식간에 <danger>기술 부채</danger>가 된다.

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/kano-model.png" width="420" />
<span style="font-size: 12px">카노 모델</span>

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 시간이 지나도 비즈니스의 복잡성은 죽지 않는다

당시에 완벽했던 코드도 시간이 지나면 가치가 없어진다

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 작은 이유 - 지식과 경험의 부족

* 우리는 왜 리팩터링을 하는가?
  * 코드를 이해하기 힘들어서
  * 성능에 문제가 있어서
  * 확장하기 힘들어서

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 작은 이유 - 지식과 경험의 부족

* 우리는 왜 리팩터링을 하는가?
  * 코드를 이해하기 힘들어서
  * 성능에 문제가 있어서
  * 확장하기 힘들어서
* 리팩터링은 **지식과 경험에 기반한 기술**
  * 리팩터링을 하기에 <accent>가장 좋은 시기는 어떻게 리팩터링을 해야할 지 정확히 알 때</accent>
  * 적절한 기술을 사용할 수 없다면 올바르게 고치는 것은 불가능
    * 다시 작성해도 다시 리팩터링을 하게 될 수 있다.
* 리팩터링이란 지식과 경험이 부족했기에 해야하는 <danger>개발자 스스로 만들어낸 기술부채</danger>

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 극복을 위한 노력

* 수학적인 모델링
* 설계 패턴 적용
* 방법론에 대한 공부
* 비즈니스에 대한 이해
* ...

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/silver-bullet.jpeg" width="360px" />

<spacer gap="30" />

## 결국 은총알은 없는가?

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 은총알은 없다

* 모든 것은 Trade-off라는 것을 배우게 된다.
* 따라서 완벽이라는 것은 없다는 것을 깨닫는다.
* 완벽할 수 없다면 확신할 수 없다.
* 우리는 언젠가 <danger>삭제할 수 밖에 없는 코드</danger>를 만들게 된다

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/nietzsche.jpg" width="160px" />
<span style="font-size: 12px">프리드리히 니체</span>

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 비극의 탄생

* **경계를 파괴하는 힘**
  * 현실, 자연, 무질서, 파괴, 죽음
  * 디오니소스적인 것
* **경계를 인식하고 나누는 힘**
  * 디오니소스적인 힘에 대항하는 이성적인 방법들
  * 분석, 분류, 검증
  * 아폴론적인 것
  * 대부분의 개발자는 매우 아폴론적인 존재

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/chaos.png" width="360px" />

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

<img src="/timeline.png" width="800px" />

---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 기술만으로는 해결할 수 없는 문제
## 여기서 개발자는 <accent>두 가지 선택</accent>을 할 수 있다

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 염세주의적 태도

* 디오니소스적인 힘에 대항하는 것은 **무의미**하다
  * 어차피 바뀔거야 대충 만들자
  * 설계, 방법론같은 것은 무의미하다
  * 애자일? 제대로 돌아가는 걸 본 적이 없다
* 과연 이것이 옳은 태도일까?
  * 다들 안좋다고 생각하겠지만 실제로는 많은 개발자가 염세주의적 태도를 취한다.
  * <danger>편하고 안락한 길</danger>

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 맞서 싸우기

* 디오니소스적인 힘을 **받아들이는 것**
  * 완벽할 수 없다는 것을 깨달았다
  * 그럼에도 불구하고 나아가야 한다
* 어떻게 극복해야 하는가?
  * 다음 길을 개척하고 발굴해야 한다
  * <accent>어렵고 견뎌야 하는 길</accent>

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 혼돈에 대항한 소프트웨어 업계의 역사

* 추상화 없는 계산의 수행
* 제어 구조의 발명
* 데이터 추상화
* 프로그래밍 패러다임
* MDA
* 재사용 가능한 패턴
* 애자일
* DDD
* 리팩터링 기술
* ...


---
layout: center
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 이제 어떻게 나아가야 할까?

---
layout: default
headerEnable: true
headerTitle: 소프트웨어 파괴의 미학
---

# 제안
* '어차피 지워진다'라는 염세주의적 생각에 빠지기 쉬운 것이 현실
* 그렇다면 거꾸로 생각해서 차라리 잘 지울 수 있게 만들면 어떨까?
* 즉, <danger>파괴</danger>에는 <accent>파괴</accent>로 대응해보자!
