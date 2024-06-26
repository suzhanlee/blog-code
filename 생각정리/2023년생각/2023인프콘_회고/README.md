# 2023 인프콘 회고

올해 2월부터 준비한 인프콘이 2023.08.15 에 성황리에 마무리 되었다.  

> 인프콘의 모든 발표는 [인프런에 무료로 공유](https://www.inflearn.com/course/%EC%9D%B8%ED%94%84%EC%BD%982023-%EB%8B%A4%EC%8B%9C%EB%B3%B4%EA%B8%B0)되어 있다.

회고 써야지 써야지 하다가, 이제야 쓴다.  

인프콘 컨퍼런스 운영에 대해서는 관여를 하지 않았다.  
TF 멤버분들이 100% 진행해주셔서 감사할 따름이다.  
그래서 인프콘을 어떻게 준비했는지 그 과정이 궁금하신 분들은 아래 회고들을 참고해보면 좋다.

- [인프콘 2023 현장 스케치](https://www.inflearn.com/pages/infcon-2023-sketch)
- [인프콘 TF 회고](https://story.inflab.com/%ec%9d%b8%ed%94%84%ec%bd%982023-%eb%b9%84%ed%95%98%ec%9d%b8%eb%93%9c-%ec%8a%a4%ed%86%a0%eb%a6%ac/)
- [인프콘 TF 리드 - 앨리스의 회고](https://yeoneui.com/archives/1098)

이번 후기는 인프콘 사이트 개발과 개인 발표자로서의 회고이다.

## 인프콘 사이트 준비

작년 인프콘 준비 기간 동안 개발 리소스가 거의 없어서, 공식 사이트 개발을 **DevOps와 디자이너 두명이서 워드프레스로 테마 골라서 만들자**로 결론내고 진행했었다.  
그리고 FE 2분이 **본업을 하면서 필요하면 테마를 수정**하는 방식을 선택했다.  
  
그리고 그 결과 작업자들의 고통의 외침을 보내더라.

![2022](./images/2022.png)

(이것외에도 회고에 가득했다.)  
  
- (해당 테마의 문제겠지만) 사이트를 열어두면 지속적으로 유튜브 영상을 가져와서 네트워크가 계속해서 증가했다. (5분정도 켜두면 1GB 네트워크를 쓰더라)
  - 물론 결국엔 테마의 PHP 코드들 삭제해가면서 해결하긴했다.
- CMS에서 편집하다가 동시에 저장하면 한쪽의 데이터가 휘발된다.
  - 그래서 사이트 편집좀 하려면 다 같이 순번을 정해서 편집해야만 했다.
- 개발 환경과 운영 환경을 구축하기가 어렵다.
  - CMS 기반이라 일반적인 웹 서비스처럼 코드를 배포하는 것이 아니라, 개발환경의 변경 내용을 운영에 반영하기가 굉장히 어려웠다.
  - 작업자가 개발에서 했던 수기작업을 운영 환경에 동일하게 해야만 했는데, 이게 너무 노가다처럼 느껴져서 결국 테스트 환경 구축을 하지 않았다.
- 원하던 커스텀한 기능을 넣기가 어려웠다.

작업자분들의 워드프레스 숙련도가 낮아서 발생한 문제겠지만, 결과적으로 다들 너무 고통스러워했다.  

그래서 올해 담당 개발 TF에서는 워드프레스가 아닌 Next에 대한 이야기가 나왔다.  
다만, 이야기 나누면서 Next 보다는 **Gatsby & CloudFront로 정적 사이트**로 만들자고 의견을 모으고 진행했다.  
(내가 Gatsby를 많이 좋아한다.)  
  
기술 스택을 결정한 후, 어떤 다양한 추가 기능들을 넣을지 이야기를 나눴다.  
그리고 공식 사이트의 여러 스펙을 확정하는 회의때 **작업자들의 아이디어 대부분을 반려**했다.  
  
여러 욕심 나는 아이디어들이 많았지만, **우리 같이 작은 스타트업에서 이정도 규모의 인력이 몇달간 행사 페이지에만 올인할 수는 없었다**.  
하고 싶어도 못한다.  
버그나 장애등으로 인프콘 준비에 완전히 몰입할 수 없기 때문이다.  

그래서 인프콘 TF 멤버들을 다 모은 자리에서 **기본 기능만 먼저 구현하자**고 했다.  
제안한 아이디어들 모두 다 너무 좋고 재밌어 보이지만, 여기에 완전히 집중하면서 하기가 힘든 환경이라고 말이다.  
기본 기능을 구현하고, **기간이 남으면 이 중에서 가장 하고 싶은 순서대로 하나씩 추가 구현**하자고 이야기하고 그렇게 진행되었다.  
  
이야기하면서도 이렇게 이야기하면 구성원들의 사기를 꺾는 것이라서 조심해야하는 것을 알면서도 할 수 밖에 없다는 것이 죄송했다.  
  
짧은 일정에 다들 다른 프로젝트와 겸직을 하는 것이라서 기본 기능 외에 추가 구현이 힘들것이라고 생각했다.  
  
그렇지만, 우리팀의 역량은 내 예상을 뛰어넘었다.  
그래서 이번 인프콘 사이트에서 가장 많은 사람들이 좋아해주신 **세션 스케줄 공유**까지 구현되었다.

![schedule](./images/schedule.png)

기본 기능이라도 기한 안에 구현 다 되었으면 좋겠다고 생각하는데, 가장 재밌어 보이는 기능 까지 추가 구현한 결과를 보게 된 것이다.  
내가 너무 우리팀의 역량을 낮게 평가하고 있었구나 하는 반성과 함께 감사한 마음을 전달했다.
  
다행히 회고때 그렇게 기획들이 일부 반려되었던것 때문에 프로젝트 겸업이 가능했다는 이야기가 나왔다.  

![2023](./images/2023.png)

(출처: TF 개발 회고)

공식 사이트는 잘 준비되었으니, 이제 본격적으로 컨퍼런스 신청 트래픽 준비가 필요했다.

### 컨퍼런스 신청 페이지 성능 준비

현재 우리 레거시 시스템에서는 수강신청에 대한 트래픽 처리양이 현저히 낮다.  
(수치 공개는... 나중에...)  
  
2023 스프링캠프 보다는 무조건 높은 신청수가 될 것이라, 이에 대한 준비가 필요했다.  

> 인프콘 신청 페이지와 유사한 사례인 올해 우리 인프런에서 진행한 2023 스프링캠프의 선착순 신청을 위한 성능 개선 사례인 [기적의 4일! Go-성능 선착순 예매 시스템 구현](https://www.inflearn.com/course/lecture?courseSlug=%EC%9D%B8%ED%94%84%EC%BD%982023-%EB%8B%A4%EC%8B%9C%EB%B3%B4%EA%B8%B0&unitId=177920&tab=activity-log) 를 참고해봐도 좋다.

물론 선착순은 아니고 추첨순이라 선착순 트래픽을 준비할 필요는 없다.  
하지만, 개발자 특성상... 페이지 오픈하면 바로 신청하는 경우가 많아서 신청 페이지가 열리는 그 순간의 트래픽을 버틸 수 있어야 했다.  
특히 이번에는 무료가 아닌 유료라서 **주문 -> 장바구니 -> 결제**까지 준비가 되어있어야했다.

DevOps와 백엔드가 합심하여 여러 성능 테스트를 하면서 신청일을 준비했다.

![at1](./images/at1.png)

![at2](./images/at2.png)

(출처: [레바툰](https://www.lezhin.com/ko/comic/revatoon/204))


막상 신청일이 다가오는데 신청자가 생각보다 적으면 어떡하지? 등의 걱정도 되었다.  
**공휴일 + 유료 컨퍼런스**라는 악조건이 얼마나 영향을 끼칠지 예상이 안됐기 때문이다.  

![day1](./images/day1.png)

![day2](./images/day2.png)

그래서 사전 라이브 방송 등도 진행하고, 트위터에도, 페이스북에도, 오픈카톡방에도 공유하면서 기다렸다.

![day2_1](./images/day2_1.png)

그리고 대망의 오픈시간이 되었다.

![day3](./images/day3.png)

![day4](./images/day4.png)

그리고 정말 많은 사람들의 신청이 시작되었다.

![day5](./images/day5.png)

![day6](./images/day6.png)

(출처: [레바툰](https://www.lezhin.com/ko/comic/revatoon/204))

결국, **공휴일 + 유료라는 악조건에도 8,712분**이나 신청해주셨다. 

![day7](./images/day7.png)

내 돈내면서 (회사에서 휴가를 주는 것도 아닌데) 공휴일에 기술 컨퍼런스를 참여하려는 분들이 이렇게 많으시구나 하면서 감동 받기도 했다.  
  
모든 신청이 잘 진행되어서, 최종 합격 인원분들을 제외하고 나머지 **수천명의 탈락되신분들을 주문, 결제 취소, 안내에 대한 대량 처리**를 진행했다. 
  
이정도로 많은 인원이 신청해주실지 몰랐고,  
예상치 못하게 많은 분들이 왔음에도 서비스의 장애 없이, 불편함 없이 마무리 되어서 준비해주신 **TF 제품팀에 정말 감사했다**.

## 발표 준비

작년과 달리 이번에는 개발바닥 라이브를 진행하지 않았다.  
여러가지 이유가 있었지만, 코엑스 2층까지 세션이 있던 상황이였고, 여러 네트워킹도 준비되어 있어서 이번에는 개발바닥 라이브에 많은 사람이 모이게 하기 보다는 새롭게 준비한 여러 행사에 많은 사람들을 분배시키는 것을 목표로 했다.  

### 키노트

매년 키노트를 준비할때마다 참고하는 발표가 있는데, 그건 바로 [금강선 디렉터님의 로아온 발표](https://www.youtube.com/watch?v=TL39Vh3hPto&t=5200s)이다.  

![loaon](./images/loaon.jpeg)

<br/>

금강선 디렉터님의 발표는 IT 제품인데도 굉장히 공감력있고, 여유가 느껴졌다.  
특히 **고객의 언어로 발표**를 한다는게 강하게 느껴졌다.  
보통 키노트는 CEO 분들이나 그에 준하는 높은 직급에 계신 분이 발표를 하시고, 그러다보니 **고객의 단어와 언어가 아닌 경우**를 자주 보는데, 그럼 그냥 교장선생님 훈화 말씀처럼 안듣게 된다.  
  
그에 반해 금강선 디렉터님의 발표는 이 게임을 즐기는 유저들이 즐겨 쓰는 단어, 즐겨쓰는 문장, 즐겨쓰는 장면들을 쓴다.  
난 그게 참 좋았다.  

> 내년엔 [네이버 단 23 컨퍼런스에서 최수연 CEO님의 발표](https://tv.naver.com/v/39568301)를 많이 참고해야겠다.  
(키노트 발표를 너무 멋지게 하시더라.)

그래서 최대한 그걸 참고하고 하면서 키노트를 준비했다.  
물론 회사일이 많다보니, 키노트에 온전히 집중할 순 없었지만, 퇴근 후에는 키노트에 많이 집중했다.  
  
1차적으로 키노트를 만들고, 2차로 디자인 팀의 도움을 받았다.  
  
아직까지도 키노트는 다른 발표들과 달리 많이 떨리고 미흡함이 느껴진다.  
매년 하다보면 점점 더 잘할 수 있지 않을까 싶다.  
  
키노트의 주제는 대표인 쭈가 회사의 방향성을 이야기하고, 내가 제품 지표에 대한 이야기를 하기로 했다.  
  
그러면서 지난 1년간 출시했던 여러 지표들 중 **수강생분들이 관심있어할 지표**만 살펴봤다.  
(지식공유자분들을 위한 지표는 이번 인프콘에서는 넣지 않았다.)

특히 커뮤니티 지표와 이력서 지표가 많이 올라서, 새삼 서비스가 잘 성장하고 있음을 다시 한번 느낄 수 있었다.  
물론 이런 지표들은 계속 보고 있긴하지만, 1년치 전체를 모아서 보니 또 색달랐다.

![keynote](./images/keynote.png)

그리고 앞으로의 1년간의 제품 로드맵을 공유했다.  

![keynote2](./images/keynote2.png)

작년도 그렇지만, 앞으로의 1년은 제품적으로 정말 많은 변화가 있을 예정이다.  
대표인 쭈가 정말 원대한 꿈을 가지고 있는 사람이고,  
나는 그걸 달성하고 싶은 욕심이 있는 사람이고,    
그리고 **우리팀은 그걸 달성할 역량이 있는 사람들이기 때문**이다.

앞으로의 1년간의 로드맵을 발표했으니, 이걸 달성하기 위해 열심히 달릴 일만 남았다.

### 인프콘 아키텍처

올해도 **인프런 아키텍처의 변화** 대한 발표를 진행했다.  

나는 사용자와 서비스가 함께 성장하는 느낌을 좋아한다.  
대표적으로 [velog](https://velog.io/) 가 있다.  
Velopert님은 velog를 만들어가는 과정을 자주 유튜브 라이브로 공유해주셨다.  
  
마찬가지로 인프런과 랠릿이 어떻게 성장해나가는지 계속 고객분들께 공유하고 싶었다.
물론 인프런은 이제 소수의 팀이 만드는 제품이 아니기 때문에, velog와 같은 형태로 공유할 수는 없다.  

서비스적인 성장은 키노트에서 공유하기 때문에, 내부 구조나 아키텍처, 환경 등이 어떻게 개선되는지 공유하고 싶었다.  
그래서 **매년 인프콘에서 인프런이, 랠릿이 이렇게 내부적으로 성장하고 있어요**를 발표하려고 한다.  

![pt1](./images/pt1.png)

![pt2](./images/pt2.png)

![pt3](./images/pt3.png)

(출처: [레바툰](https://www.lezhin.com/ko/comic/revatoon/204))

다만 이런 내용들은 필연적으로 애플리케이션 계층과 인프라 계층, 조직 구성 등 여러 요소들이 섞이기 때문에 **누구를 타겟으로 하는 것인지 명확하지 않은 뒤죽박죽 발표**가 될 수 있다.  
  
백엔드가 들어야할지, 데브옵스가 들어야할지, 시니어 혹은 개발리더분들이 들어야할지 등 뭔가 명확하지 않은 느낌이 계속 들었다.  
  
그래서 **스타트업에서 레거시와 함께 하는 5년차 미만의 주니어 개발자**분들을 대상으로 하고, 어려운 내용들은 다 제거했다.  
그리고 최대한 쉬운 용어들과 추상화된 설계도를 많이 사용했다.  

![arch1](./images/acrh1.png)

스토리 라인은 "**조직 구조가 N개의 목적조직으로 변경되었는데, 1개의 거대한 레거시를 그대로 사용해야하는 상황이라면 어떻게 할 것인가?**" 에 대한 물음으로 잡고, 이를 차근차근 해결해나가는 형태를 그렸다.  

실제 우리팀에서 겪는 과정이기도 했지만, 어느정도 매출을 내기 시작한 스타트업에서 많이들 겪는 상황이라고 생각했기 때문이다.  
  
발표 장표에는 별도의 스크립트를 작성하지 않고, **이 장표가 몇분째에 나와야하는지**만 이정표처럼 작성해두었다.

![timeline](./images/timeline.png)

작성된 발표 스크립트를 읽기만 하면 너무 재미없다.
그때 그때 청중분들 반응 보고 덧붙이거나 빼는 것을 선호한다.  
그리고 그러다보니 **발표 시간 관리를 못한다**.  
그래서 이렇게 주요 장표마다 이 장표가 발표 시작후 몇분째에 나와야하는지 두고, 그걸 보면서 발표 속도를 조절했다.  
  
이 방법은 꽤나 효과가 좋아서 **40분 발표를 39분 14초에 마무리**할 수 있었다.  
모든 내용을 누락없이, 적당한 속도감으로.  
  
개발바닥의 영향이 있어서인지, 이번 발표에도 많은 분들이 참석해주셨다.

![result](./images/result.png)

영한님이나 토비님은 개발계의 유재석 같이 신계 (神界) 에 속한 분들이기 때문에 나는 **3등이 아니라 인간계 1등**을 했다고 혼자서 축하하는 시간을 가졌다.

## 마무리

이런 컨퍼런스를 준비하면 보통 얼마나 필요하나요라는 질문을 사석이나 DM으로 자주 받는데, 우린 그날 하루를 위해 4억 2천 5백만원이 사용되었다. 
(우리 TF 멤버분들의 인건비 제외하고......)  

![money](./images/money.png)

재무적으로 보면 이런 행사를 매년 한다는 것은 우리 같이 작은 스타트업에서는 수지타산이 맞지 않다.  
그럼에도, 우리 서비스를 좋아하는 많은 분들에게 감사함을 표현하는 가장 확실한 방법이라 생각하기 때문에 매년 할 수 있었던 것 같다.
  
내년에도, 내후년에도 계속해서 멋진 행사가 될 수 있도록 좋은 서비스를, 지속 가능한 서비스를 계속 만들고 발전시켜나가야겠다.