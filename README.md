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
# 발생한 트러블 슈팅 및 관련 블로그 게시물
[CORS 에러 발생 및 해결](https://park-yina.github.io/categories/project/flutter/JumpingBattle/1)<br>
[프록시 서버를 통한 문제 해결 및 또다른 문제1](https://park-yina.github.io/categories/project/flutter/JumpingBattle/2)<br>
[프록시 서버 2탄](https://park-yina.github.io/categories/project/flutter/JumpingBattle/3)
# 이후 리팩토링 방향 및 사안 정리
# 사용 기술
<div align=center><h1>📚 STACKS</h1></div>
<div align=center> 
  <img src="https://img.shields.io/badge/amazonaws-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white"> 
  <img src="https://img.shields.io/badge/firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=white">
  <img src="https://img.shields.io/badge/flask-000000?style=for-the-badge&logo=flask&logoColor=white"><br>
  <img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"> 
  <img src="https://img.shields.io/badge/html5-E34F26?style=for-the-badge&logo=html5&logoColor=white">
  <img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"> 
