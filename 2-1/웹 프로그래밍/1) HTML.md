![[web2024ai_1장.pdf]]
## 웹 프로그래밍 구조
### 프론트 엔드(front-end)
HTML(CSS, JavaScript)
### 백 엔드(back-end)
PHP
Java웹
Python웹
Node.js
Go웹
etc..
### 데이터베이스(database)
SQL(ex.Oracle, MySQL, MariaDB)
NoSQL(ex. MongoDB, Cassandra)

### 1장 실습
### 1.html
```html
<!doctype html>
<!--나는 주석입니다-->
<html>
<head>
<meta charset="UTF-8">
<title>내가 CEO다~</title>
<style>
a{margin-right : 40px;}
</style>
</head>
<body>
<h2>SIWO 주식회사</h2>
<hr>
<br>
<a href="2.html">로그인</a>
<a href="2.html">회원가입</a>
<a href="https://www.naver.com" target="_blank">네이버</a>
</body>
</html>

- <!doctype html> : 문서가 html이라는 걸 명시해줌 꼭 필요한 건 아님
- <!--주석--> : 말 그대로 주석
- <meta charset="UTF-8"> : 한글 인코딩 코드
- <h2>~</h2> : 안에 글자 크게 해줌 1~6으로 크기 조절 가능, 자체로 한 줄을 의미함
- <hr> : 가로로 한 줄 그어주는 코드
- <br> : 줄 바꿈
- &nbsp; : 공백 한칸을 의미함
- <a>~</a> : 링크 역할을 하는 태그 href속성은 어디로 이동할 것인지를 적어줌, target="_blank"를 입력시 새 탭에서 열어줌
- margin-right : 40px : 오른쪽에 공백은 40px만큼 넣겠다는 의미
```
### 2.html
```html
<!doctype html>
<html>
<head>
<title>로그인</title>
</head>
<body style="background-color : silver">
<form action="" method="">
<strong>아이디와 비밀번호를 입력하세요</strong>
아이디:<input type="text" name:"id"><br>
비밀번호:<input type="password" name="pw">
<p>
<button type="submit">확인</button>
</form>
</body>
</html>

- <form action="" method="">~</form> : 데이터를 서버로 보낼 때 사용
- <strong>~</strong> : 안에 글자 진하게
- <input type="text" name:"id"> : 글자 입력할때 사용 type속성이 text면 문자열, password면 화면에 기호로 표현됨 name속성은 id라는 가방안에 넣어서 준다고 이해하면됨
- <button type="submit">~</button> : 화면상에 버튼을 만들어주고 form 안에있는 입력된 수들을 제출해줌
```
### 3.html
```html
<html>
<head> <title>회원가입 화면이다~</title> </head>
<style> button { margin-right : 25px; } </style>
<body>
<h3> SIWO 주식 회사 회원 가입 </h3>
<form action="" method="">
<p>
아이디:<input type="text" name="id"><br>
비밀번호:<input type="password" name="pw"><br>
이름:<input type="text" name="name"><br>
성별:<input type="radio" name="gender" value="man">맨
<input type="radio" name="gender" value="woman">우먼<br>
직업:<select name="job">
<option>아직고딩</option><option>대학생</option>
<option>아티스트</option><option>공유</option>
</select>
<p>
<button type="submit">등록</button>
<button type="reset">취소</button>
</form>
</body>
</html>

- <input type="radio" name="gender" value="man"> : input 타입이 radio면 체크박스를 만들어 선택한 것의 value값을 gender가방에 넣어 제출해준다.
- <button type="reset"> : type 속성이 reset인 경우 화면을 초기화해준다.
```
### 4.html
```html
<html>
<head><title>리스트</title></head>
<style>
body{background-color:yellow;}
span{color:gray; font-size:0.8em}
table,td,th{border:1px solid blue}
</style>
<body>
<h2>회원리스트(관리자용)</h2>
<table>
<tr><th>아이디<th>비밀번호<th>이름<th>성별<th>직업
<tr><td>sony<td>1111<td>손흥민<td>남<td>축구선수
<tr><td>sunflower<td>2222<td>고흐<td>남<td>화가
<tr><td>&nbsp;<td>&nbsp;<td>&nbsp;<td>&nbsp;<td>&nbsp;
</table>
<span>총 회원 수 : 2명</span>
</body>
</html>

- table,td,th{border:1px solid blue} : 테두리 스타일을 글자크기 선종류 색깔 순으로 설정할 수 있다.
- <table>~</table> : 표를 설정함
- <tr>~</tr> : 표에서 한줄을 의미
- <th>~</th> : 표에 한칸을 의미하고 추가적으로 가운데정렬, 글자진하게 만들어줌
- <td>~</td> : 표에 한칸을 의미
- span{color:gray; font-size:0.8em} : 여기서 em과 px의 다른점은 em은 상대적으로 크기를 조정함
```
### id와 클래스
- 둘의 차이점은 id는 한번만 사용가능하고 클래스는 여러번 가능하다다
ID 
```
<p id="unique">이 요소의 글자 색상을 바꿀 거에요!</p>
#unique { color: red; }
```
CLASS
```
.highlight { color: blue; }
<p class="highlight">이 요소의 글자 색상을 바꿀 거에요!</p> 
<p class="highlight">이것도 바꿀 거에요!</p>
```
## 1장 퀴즈
![[web2024ai_1장_확인문제.pdf]]
### Quiz #1 <!DOCTYPE html>의 의미는?
이 문서가 html 문서라는 걸 명시해줌
### Quiz #2 html태그 10가지 적어 보기
```
<p>~</p> : 한 문단을 의미 <br><br>을 나타내기위해서도 사용
<form>~</form> : 정보를 전달해줄 때 사용
<a href="">~</a>: 링크 역할 href에 주소를 넣으면 웹페이지로도 이동가능 + target="_blank" 넣어주면 새탭에서 염
<table>~</table> : 표 만들 때 사용
<button type="">~</button> : 화면상에 버튼을 보여주고 눌럿을 때 type이 submit이면 form안에 정보를 서버로 전달해주고 reset이면 화면을 초기화 해줌
<style>~</style> : css기능 디자인
<input type="" name=""> : 사용자가 정보를 입력하게 해줌 type이 text면 문자열 입력이고 password면 화면상에 ****로 입력한 내용을 가려줌 radio면 체크박스를 생성함, name은 가방에 넣어주는 느낌 value는 radio일 떄 사용하고 체크햇을때 입력값이 따로 없으므로 미리 지정한 특정 value값을 보내줌
<tr> : 표에서 한줄을 의미
<td> : 표에서 한칸
<th> : 진하게 가운데정렬, 표에서 한칸
<select name="">~</select> : 선택 박스를 만들고 선택한 option값을 name가방에 넣어줌
<option>~</option> : select태그안에 선택지를 만들 때 사
```
### Quiz #3 html 주석 작성 방법은?
```
<!--주석내용-->
```
### Quiz #4 ‘이동’이라는 글자를 누르면 새 탭이 열리면서 다른 페이지(new.html)로 링크하게 만드는 html 코딩 한 줄을 적어보세요.
```
<a href="new.html" targer="_blank">이동</a>
```
### Quiz #5 type속성의 값이 submit인 button 태그는 화면에 버튼모양으로 보입니다. 이 버튼을 클릭하면 어떤 결과가 나올까요? 그리고 type속성의 값이 reset인 버튼을 클릭하면 어떤 결과가 나올까요?
form 안에 있는 정보들은 서버로 전송해줌 reset인 버튼은 화면을 초기화 시켜줌
### Quiz #6 화면 전체를 "lime" 색상으로 설정하려면 어 느 태그에 어떤 코딩을 추가해야 할까요?
```html
(1) body 태그 안에 적는 방법
<body style="background-color:lime">
(2) CSS 부분을 따로 style태그로 분리
<style>
body{backgroud-color:lime;}
</style>
(3) CSS 부분을 다른 파일로 분리
```
### Quiz #7 아래 화면 처럼 나오게 코딩해보세요.
- 맨/워먼 중 하나만 선택할 수 있고, 식성 3개 중 하나만 선택할 수 있도록 하려면 name속성을 어떻게 설정하면 되나요?
- value속성의 값은 영어로 넣으세요.
```html
<html>
<head>
</head>
<body>
성별:<input type="radio" name="gender" value="man">맨
<input type="radio" name="gender" value="woman">워먼
<br>
식성:<input type="radio" name="eat" value="meat">고기만
<input type="radio" name="eat" value="vege">야채만
<input type="radio" name="eat" value="any">뭐든
</body>
</html>
```
### Quiz #8 좌측 소스를 수정해서 우측 화면이 나오도록 하세요.
```html
<html>
<head></head>
<style>
h2{background-color:yellow;color:gray;}
strong{background-color:blue;}
</style>
<body>
<h2>HTML 확인문제</h2>
<p>
안녕하세요, <strong>아이유</strong>입니다.<br>
반갑습니다!
</body>
</html>
```
### Quiz #9 CSS 기초 문제입니다. 수업자료 1장 p. 12 예제를 아래와 같이 바꿔보세요
(2) sony를 파란색으로 바꿔보세요. (id속성 이용) 
(3) sony외에 손흥민도 파란색으로 바꿔보세요. (class 속성 이용)
```html
<html>
<head><title>리스트</title></head>
<style>
body{background-color:yellow;}
span{color:gray; font-size:0.8em}
table,td,th{border:1px solid blue}
#sonycolor{color:blue;}
.highlight{color:blue;}
</style>
<body>
<h2>회원리스트(관리자용)</h2>
<table>
<tr><th>아이디<th>비밀번호<th>이름<th>성별<th>직업
<tr><td id="sonycolor">sony<td>1111<td class="highlight">손흥민<td>남<td>축구선수
<tr><td>sunflower<td>2222<td>고흐<td>남<td>화가
<tr><td>&nbsp;<td>&nbsp;<td>&nbsp;<td>&nbsp;<td>&nbsp;
</table>
<span>총 회원 수 : 2명</span>
</body>
</html>
```

### Quiz #10 첫 과제!!
```html
<html>
<head>
<title>
2143655 장시우
</title>
</head>
<style>
body{background-color:skyblue}
table, th, td {border:1px solid black}
</style>
<body>
<hr><p>
<h3>게시판</h3>
<hr><p><br>
<table>
<tr> <th>ID <th>이름 <th>학년 <th>내용
<tr> <td>ppiyak <td>나삐약 <td>2 <td>저는 아직도 삐약이
<tr> <td>great <td>엄청나 <td>4 <td>저는 갓코딩 입니다. 으허허허
</table><br>
&nbsp;&nbsp;&nbsp;ID : <input type="text" name="id"><br>
이름 : <input type="text" name="name"><br>
학년 : <input type="text" name="grade"><br>
내용 : <input type="text" name="dia" size="50"><br><br>
<strong>이상 2주차 과제였습니다 ^ ^</strong>
</body>
</html>
```