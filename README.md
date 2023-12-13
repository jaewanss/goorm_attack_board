# goorm_attack_board
<a href="https://github.com/jaewanss/goormboard.git">게시판깃허브주소<a>
위 링크 게시판 웹 어플리케이션의 취약점을 공격해보려 SQL 인젝션과 XSS 공격을 테스트 해 보았습니다.



1. 'login.php'에 SQL 인젝션으로 허가되지 않은 로그인 시도
  <img width="1356" alt="스크린샷 2023-12-13 오후 10 42 19" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/35d9f0d9-bdce-45ce-bf96-a55fac3c0fc8">

<img width="1356" alt="스크린샷 2023-12-13 오후 10 42 24" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/ff47723e-8d47-4b8b-9dd6-b74032fb3773">
1=1이 참인지 묻는 SQL구문으로 로그인을 시도하였으나 실패 --> 'login.php'에서 prepare 함수를 사용하여 입력값과 쿼리문을 분리시켜 놓았기 때문


2. 'write.php'에 XSS 공격
<img width="1356" alt="스크린샷 2023-12-13 오후 11 01 02" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/019fa11f-c559-49fe-9fb9-2ae0e1baa5ba">

