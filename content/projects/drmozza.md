---
title: "Project 1: Dr.Mozza+"
date: 2021-07-18T02:51:40+09:00
ShowToc: true
---

[Dr.Jart+](https://us.drjart.com/) 클론 프로젝트 영상
---
{{< youtube lqHxD3Zq770 >}}

&nbsp;
&nbsp;

---
Overview
---
### 프로젝트 기간
2021.07.05(월) ~ 2021.07.16(금), 2주

### 팀 구성
- 프론트엔드: 박정훈, 이종민, 황소미
- 백엔드: 김한준, 안희수, 이동명

### 기술 스택
* Programming Tools
    - Django, MySQL, AWS(EC2, RDS)
* Communication Tools
    - Notion, Github, Postman, AQueryTool(ERD)

### Github Repository
https://github.com/dom-lee/drmozza

### API 문서
https://documenter.getpostman.com/view/12180757/Tzm3nciR

### Entity Relationship Diagram
![](https://user-images.githubusercontent.com/46280353/126058434-01eff9e9-be7a-4c57-b453-a70cd05d8c0f.png)

### 내가 맡은 역할
* 장바구니 엔드포인트
  - 카트 제품 추가 및 수량 변경
  - 요청 수량 및 재고 비교
* 주문 엔드포인트
  - 카트에 있는 제품 주문
  - 주문 이력 관리
* 쿠폰 엔드포인트
  - 쿠폰 코드 유효성 검토
* 메인페이지 엔드포인트
  - 메인페이지 Banner data 제공
  - 네비게이션바 data 제공
* 백엔드 서버 배포
  - AWS(EC2, RDS) 연동
&nbsp;
&nbsp;

---
느낀점
---
### 계획 세분화 및 기록의 중요성
프로젝트 첫날, Planning Meeting을 진행하면서 우리가 진행해야할 Task 목록들을 나열하고 각자 분량에 맞게 Task를 나눴다.
하지만, 너무 두루뭉술하게 작성한 Task와 세분화된 Task가 섞여있다보니, 너무 광범위하게 명시된 Task는 계속 In Progress 상태여서 프로젝트의 진척상황을 파악하기가 어려웠다. 

그 해결책으로, 2주차 부터는 큰 목표에 해당하는 Epic과 해당 Epic을 이루기 위한 Task를 세분화 하여 Roadmap을 관리하였다. 

또한, 아침 StandUp 미팅에서 서로 협의한 내용을 기록해두지 않아, 까먹고 똑같은 주제를 두고 다시 이야기를 하는 문제가 발생하여 Notion에 회의록을 추가로 관리하였다.
회의록에는 어제 한일, 오늘 할일, 문제사항, 협의사항을 작성하였다.

**세분화 되지 않은 기존 Trello**
![first trello setting](https://user-images.githubusercontent.com/46280353/126059840-c7c1c22a-5079-41e4-89c0-d2ea4b41c992.png)

**Task를 세분화하고 회의록을 관리한 Notion**
![Notion](https://user-images.githubusercontent.com/46280353/126060705-0385b1ef-9093-4eee-9be4-ad66ca6a4562.gif)

&nbsp;
### 모델링의 중요성
닥터 모짜렐라의 상품인 치즈와 치즈가 속해있는 카테고리는 N:N 관계로 모델링 되어있다. 하나의 치즈는 3가지의 카테고리를 가지고 있는데,
1. 우유 종류에 해당하는 cow, sheep, goat
2. 스타일 종류에 해당하는 fruit & savoury, soft, hard, blue
3. 나라에 해당하는 france, uk, netherlands, italy, spain, swiss

이렇게 하나의 제품은 각각 3개의 메뉴에 속한 카테고리 3개를 가지게 된다.

처음에 이렇게 모델링한 이유는 추후에 새로운 다른 분류의 메뉴가 발생할 경우 유연하게 대처하기 위함이었다. milk category, style category, country category를 따로 만들어 Products와 3개의 1:N 관계로 만들 경우, 새로운 분류가 발생할때 모델링을 바꿔야하기 때문이다.

하지만 이 유연함 때문에, 제품 상세페이지에서 같은 milk category이면서 다른 style category를 가진 product를 추출할 때 매번 어떤 menu에 속하는 category인지 확인하는 절차가 발생했다.

모델의 유연함도 좋지만, 발생할지 안할지 모르는 유연함 때문에 불필요한 작업이 추가로 발생하는 것에 대한 Trade Off를 고려해야 한다는 것을 느끼게 되었다.  
&nbsp;
### 같이 일하는게 즐거운 사람이 되자
같이 프로젝트를 진행했던 닥터 모짜렐라 팀원들은 다들 유쾌해서 같이 프로젝트를 진행하는게 정말 즐거웠다. 그래서인지, 더욱 소통을 많이 하게 되었고 문제가 곪기전에 바로바로 해결할 수 있었다.

프로젝트와 회사에서 일을 하는 것이 동일하다고 볼 수는 없지만, 프로젝트를 진행하면서 '같이 있는게 즐거운 사람들과 일하는 것은 얼마나 축복일까'라는 생각이 들었다. 그러기 위해서는 나 스스로가 같이 일하는게 즐거운 사람이 되어야 겠다. 💫
