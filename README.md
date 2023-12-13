# goorm_attack_board
<a href="https://github.com/jaewanss/goormboard.git">게시판깃허브주소<a><br>
위 링크 게시판 웹 어플리케이션의 취약점을 공격해보려 SQL 인젝션과 XSS 공격을 테스트 해 보았습니다.<br>


<hr>
<h2>1. 'login.php'에 SQL 인젝션으로 허가되지 않은 로그인 시도</h2>
  <img width="1356" alt="스크린샷 2023-12-13 오후 10 42 19" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/35d9f0d9-bdce-45ce-bf96-a55fac3c0fc8">

<img width="1356" alt="스크린샷 2023-12-13 오후 10 42 24" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/ff47723e-8d47-4b8b-9dd6-b74032fb3773">
1=1이 참인지 묻는 SQL구문으로 로그인을 시도하였으나 실패 --> 'login.php'에서 prepare 함수를 사용하여 입력값과 쿼리문을 분리시켜 놓았기 때문

<hr>
<h2>2. 'write.php'에 XSS 공격</h2>
<img width="1356" alt="스크린샷 2023-12-13 오후 11 31 30" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/83a463de-f504-4fb7-b75f-cfbcf017a96a">
<img width="1356" alt="스크린샷 2023-12-13 오후 11 31 34" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/edda65b1-4536-4801-87d8-5ad5a5f68b8e">
테스트 공격 스크립트가 정상 작동하는 모습

<hr>
<h2>아래도 XSS를 이용</h2>
<img width="1356" alt="스크린샷 2023-12-13 오후 11 01 02" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/019fa11f-c559-49fe-9fb9-2ae0e1baa5ba">
<img width="1356" alt="스크린샷 2023-12-13 오후 11 01 08" src="https://github.com/jaewanss/goorm_attack_board/assets/152056488/cdf131b8-8e8d-4a22-b37c-6c8707934176">
게시물 클릭 시 미리 지정해둔 곳으로 cookie가 전송되게하는 스크립트를 넣었는데,<br>
애초에 게시판 형식이 목록에서 글을 클릭하여 들어갈 수 있는 구조가 아니어서 제대로 된 테스트를 못해봤으나<br>
다른 게시물들은 전부 보이지 않게 되고 해당 게시물도 제목만 보이는 현상이 발생되었습니다.

<hr>
자체적으로 만든 게시판이라 귀중한 자산이랄게 없었고, XSS는 alert 메시지를 띄우는 것에는 성공했으나<br>
정보수집과 같은 것은 지식이 부족하여 해보지 못했습니다.<br>
해커의 입장으로 어떻게 접근해서 악의적으로 활용할 수 있는지와<br>
두 번째 XSS시도에서 예상치 못한 현상이 발생한 이유를 고민해보려 합니다.
