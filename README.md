# CSS(Cascading Style Sheets)
##  CSS 작성 전 준비사항
* html 문서 준비 (태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles 으로 css 파일 배치
* ex) index.html, index.css
## CSS 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결하는 **외부 스타일시트**
* html 파일 내에서 head태그 안에 style태그로 구분해서 작성하는 **내부 스타일시트**
* 외부스타일시트 장단점:
- 장점 : 1개의 css 파일로 여러개의 html을 관리할 수 있다.
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일 관리가 어려울 수 있다.
* 내부스타일시트 장단점:
- 장점 : html 파일 내에서 작성하여 태그와 한꺼번에 보기 편하다.
- 단점 : 2개 이상의 html 파일을 동시에 디자인 관리하는 것이 불가능하다.
## CSS 선택자
1. 태그선택자 : `<h1></h1>` -> `h1{속성:값;}`
2. 클래스선택자 : `<h1 class="a"></h1>` -> `.a {속성:값;}`
3. 아이디선택자 : `<h1 id="b"></h1>` -> `#b {속성:값;}`
4. 자손선택자 : `<h1><em><span></span></em></h1>` -> `h1 em span {속성:값;}`
5. 자식선택자 : `<h1><em><em></em></em></h1>` -> `h1 > em {속성:값;}`
## CSS 디자인하기
* CSS 작성 전 HTML이 미리 디자인이 되어있으면 안된다.
* **HTML을 디자인 초기화하는 작업이 CSS 디자인 전 반드시 선행되어야 한다.**
* 초기화 CSS `reset.css` 공통파일 (날짜나 프로젝트명 표기 금지!)
# CSS 글자 표현 속성
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹 글꼴(추천)을 연결할 수 있다.
* "메인대표글꼴", "후보글꼴" (후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야 한다.
* 글꼴 이름에 한글이나 공백이 있으면 ""(따옴표)가 필요하다.
## font-size
* 웹 글꼴 평균 16px
* 사용 단위 px, %, em, rem
* 절대값 : px, 상대값 : %, em, rem(권장)
* em 가장 가까운 부모의 값으로 부터 변환
* rem 부모와 상관 없이 body에 설정한 값으로 부터 변환
# 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그(1)
1. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b p {}` 8점 3+2+2+1
* **`#box #a .b p {}` 9점** 3+3+2+1
* `#wrap #box .a {}` 8점 3+3+2
* `#wrap .a .b p {}` 8점 3+2+2+1
2. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#wrap .top .a .b p {}` 3+2+2+2+1 10
* `#wrap #box .a .b p {}` * 3+3+2+2+1 11
* `.wrap .box .a .b p {}` 2+2+2+2+1 9
* `.wrap .box .a div p {}`* 2+2+2+1+1 8
## color
* 영문명 직접 입력 ex)테스트용으로 주로 밝은색을 사용한다.
* aqua, lime, yellow, coral, ...
* 헥사코드 입력 최소값0 ~ 최대값F RGB 코드 기준
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다.
* #HEX #000000 => #000, #FF00CC => #F0C
* rgba(red, green ,blue , alpha) *최대색상 255
## box css
### display
* `block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성
* `block` : 새로운 행, 크기, 여백 인식
* `inline` : 내용만큼 크기 인식 (그 외 크기 인식 불가능)
* `inline-block` : 내용만큼 크기 인식 (크기 추가설정 가능), 옆으로 정렬
### box-sizing
* `box-sizing:border-box`
* 요소오의 너비와 높이를 계산할 때 테두리, 여백 (padding)까지 포함해서 계산하는 속성
* 속성 미적용 시 : w100+h100+(padding-top20) = 100x120
* 속성 적용 시 : w100+h100+(padding-top20) = 100x100
### width, height
* 요소의 너비와 높이
* 절대값px, 상대값%, 화면 상대값 vw, vh
* 상대값 처리 0~100% 사이 값만 사용한다.
## table 
* 가로 한 줄 1행
* 입력 칸 1 개 1 열
* 테이블 관련 태그는 모드 block 특징을 가지고 있음
### tr행, td 내용 열
* 열(td)는 항상 행(tr)안에 존재해야 됨
* table은 행, 열을 자식, 자손으로 가지는 부모로써 존재
### thead, tbody, tfoot 행 그롭
* `thead` : 제목행 그룹, th 위주로 구성된 제목행(tr)을 묶을 때 사용
* `tbody` : 내용행 그룹, td위주로 구성된 내용행(tr)을 묶을 때 사용
* `tfoot` : 결과행 그룹, th&td들로 구성된 결과값을 가지는 결과행(tr)을 묶을 때 사용
## 여백
### padding
* 안쪽 여백
* 읽는 순서 Top → Right → Bottom → Left ; 시계방향
### margin
* 바깥쪽 여백
* 읽는 순서 Top → Right → Bottom → Left ; 시계방향
* 서로 다른 요소에서 겹치는 경우 값이 더해지지 않고 먼저 선언된 값만 적용되므로 겹쳐진 값을 하나만 남겨둬야 됨
* `auto` : 주로 좌우에 값을 넣어서 사용자 환경에 맞춰서 자동으로 정렬될 수 있도록 설정
## 수열 선택자
### nth-child(n)
* ex) div에 첫번째 p를 선택 `div>p:nth-child(2)`
* ex) p안의 a를 선택 `div>p:nth-child(4)>a`
## 테이블 열 수평/수직 방향 합치기
### rowspan
* 수직열 합치기 속성
### colspan
* 수평열 합치기 속성
## form 요소와 속성
### `<form action="#" method="post"></form>`
* 사용자로부터 입력 받을 수 있는 폼을 정의하는 요소
* `action` : 폼 데이터를 제출할 서버 스크립트 지정
* `method` : 폼 데이터를 제출하는 방법 `POST`,`GET`로 지정. ex)`<form action="#" method="post"></form>`
* fieldset, legend : 
- 양식의 일부를 그룹화하는 태그.
- 정보 컨트롤 요소 들을 용도에 맞게 그룹으로 묶을 경우 사용
- 폼의 양식을 더 읽기 쉽고 이해하기 편하게 구성하는 것이 주 목적
- form의 자식 요소로 배치
- `legend` 그룹 제목. CSS로 표시되지 않게 변경함
- ex) 회원가입 시 입력하는 필수양식, 선택양식 등의 그룹 용도
### `<input type="" name="">`
* type : 입력필드 속성. text, password, tel, url, email, textarea 등을 사용해 입력 성격을 지정함
* name : CSS에서 id, class와 같이 선택자로 지정할 수 있는 값
* readonly : 읽기 전용. ex)자동입력방지 표시
* required : 필수 작성 속성, 작성하지 않을 시 다음 단계로 넘어가지 않음
* autofocus, autocomplete : 페이지 로딩 시 컨트롤 자동으로 포커스 설정, `autocomlete=on` 자동 완성 기능 설정 
* value : 미리 제시되는 텍스트
* palceholder : 미리 제시되는 텍스트
* value와 placeholder의 차이점 : 
- `value` 활성화시 제거 안 됨. 직접 지우거나 수정해서 사용하는 값
- `placeholder` 활성화시 자동 제거 됨 ex)`<input type="email" placeholder="Enter your email or id" name="user_mail_id">`
* maxlength : 글자수 제한 설정
### `<textarea></textarea>`
* rows, cols : 입력할 수 있는 행과 열의 사이즈를 지정하는 값
* 사용용도 및 주의사항 : 
- 사용자가 작성할 수 있는 영역 ex)리뷰쓰기
- 약관 같이 사용자가 수정해서는 안 되는 곳에 사용 시 `readonly`를 추가로 입력해서 사용
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접 입력 가능한 입력양식
* radio 등의 사용자가 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식(데이터 구분용), 선택양식(데이터 구분 (개별 데이터X, 그룹 데이터 구분용))
* `value` : 입력양식(초기값), 선택양식(개별 데이터 구분용)





### disabled
* 필드 비활성화
* ex)회원 정보 변경에서 수정을 하면 안 되는 부분들에 주로 사용
### 
* 페이지 로딩 시 컨트롤 자동으로 포커스 설정
### autocomplete
* 자동완성 기능
* 속성에 `autocomlete=on`을 입력해서 활성화
## 속성선택자 (form관련 주로 사용)
* 태그[속성] 태그에 속성이 있을 때
* 태그[속성=값] 속성의 값이 이것일 때
* 태그[속성^=값] 속성 값이 이것으로 시작할 때
* 태그[속성$=값] 속성 값이 이것으로 끝날 때
* 태그[속성*=값] 속성 값이 이것을 포함할 때