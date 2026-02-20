# JumpingBattle1
(주)점핑배틀의 외주처리 건에 대한 ReadMe파일입니다.
# 의뢰 내용
## 파이어베이스 관련
- 파이어베이스 주소 암호화<br>
- 원하는 조건의 파일 자동 삭제<br>
## 웹페이지 관련
- AWS람다 사용 및 Route53 사용한 SSL HTTPS구현<br>
- 이전 랭킹 페이지를 참조하되 추가 기능 구현
  ### 추가 기능
  - 3초마다 특정 n등에서 n등까지의 등수가 refresh되어 화면에 보이도록 구현<br>
  - 랭킹 동영상 화면에도 랭킹을 보여주어 유저가 랭킹 조회를 쉽게 할 수 있도록 텍스트를 화면에 추가<br>
  ### 이전 페이지 지원 기능 및 추가 기능
  - jpg 다운로드 추가 및 video다운로드 추가<br>
  - video스트리밍 유지<br>
    - 다운로드 횟수 제한 이후에도 스트리밍은 유지<br> 오직 날짜 검증 유효성에 의해서만 스트리밍 중지
## 랭킹 웹 페이지 관련
- 전국 30개 이상의 매장, 매장 별 10개 이상의 맵에 대한 500위 까지의 랭킹을 실시간으로 보여줄것
    ### 실시간 랭킹 구현 방법
    - 웹소켓 vs 이벤트 소스 중 단방향 통신으로도 충분하다고 판단하여 이벤트 소스 방식으로 구현
    - 초반에는 폴링방식도 생각하였으나, 매장 수와 맵의 종류 등을 고려하였을 때 경제성이 심각하게 저하된다고 판단하여 제외
 

    ### 캐시 키 관련 문제 발생
    - 초반 매장별로만 데이터를 관리하였더니, 인기가 있는 지점의 경우 수천개가 넘는 데이터에서 원하는 애를 찾아오는 검색에 너무 많은 시간이 들어 병목현상이 생기는 것을 확인
    - 이를 해결하기 위해 고유키를 보다 작은 단위로 짜서 검색 성능을 30%가량 향상

## EC2관련 트러블 슛팅
- EC2인스턴스(UBUNTU T2MIRO)에서 매장을 여러번 변경할 시 느려지는 현상 발견
  ### 해결책1
  sse 개수를 여러번 변경시 느려지는 시점(4번째 검색)에 맞추어 개수 제한을 둠<BR>
  10%정도의 성능 향상이 되었으나, 여전히 클라이언트의 기대치와는 다른 것을 발견
  ### 해결책2
  이번 프로젝트에서는 주로 큰 작업이 문제 되기 보다 작은 작업이 여러번 일어나는 것이 성능 저하의 원인임을 찾음<BR>
  그래서 워커 프로세스의 개수를 줄이고 스레드의 개수를 늘려 30%의 성능 개선을 이끌어내었고,클라이언트 쪽에서도 만족을 하게됨
# 발생한 트러블 슈팅 및 관련 블로그 게시물
[CORS 에러 발생 및 해결](https://park-yina.github.io/categories/project/flutter/JumpingBattle/1)<br>
[프록시 서버를 통한 문제 해결 및 또다른 문제1](https://park-yina.github.io/categories/project/flutter/JumpingBattle/2)<br>
[프록시 서버 2탄](https://park-yina.github.io/categories/project/flutter/JumpingBattle/3)
# 이후 리팩토링 방향 및 사안 정리
/docs폴더를 통해 의사결정 및 리팩토링에 대한 확인이 가능합니다.
# 사용 기술
<div align=center><h1>📚 STACKS</h1></div>
<div align=center> 
  <img src="https://img.shields.io/badge/amazonaws-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white"> 
  <img src="https://img.shields.io/badge/firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=white">
  <img src="https://img.shields.io/badge/flask-000000?style=for-the-badge&logo=flask&logoColor=white"><br>
  <img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"> 
  <img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white">
  <img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"> 
