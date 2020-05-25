# css

## css 코드 작성 규칙

### 1. 기본 규칙

A. W3C Validation

모바일에서 CSS는 사용 가능한 Hack과 CSS3 속성을 제외하고 W3C Validation을 통과해야 핚다.

B. 영문 소문자 사용

모든 속성은 영문 소문자로만 작성한다.

C. 따옴표 사용 범위

공백이 포함된 폰트명, 한글 폰트명, 작은따옴표(' ')로 감싸며, 
@charset 선언 시에는 속성값을 큰따옴표(" ")로 감싼다. 그 외의 경우에는 따옴표를 사용하지 않는다.
url 데이터 타입에는 작은 따옴표를 사용하지 않는다.

예)
`font-family: '돋움'`
`background:url(bg.gif) no-repeat 0 0`
`content:'chapter'`
`@charset "utf-8";`

D. 마지막 세미콜론 사용 지양

마지막 속성의 세미콜론(;)은 삭제한다

`.class{font-size:12px;color:#000}`


### 2. 공백

A. 선택자 간 공백 제거

쉼표로 구분되는 선택자 간 공백은 제거한다.

`a:hover,a:active,a:focus{text-decoration:underline;}`

B. 속성 간 공백 제거

속성 간 공백은 제거한다.

`.class p{color:#000;line-height:18px}`

C. 중괄호 좌우 공백 제거

중괄호 좌, 우의 공백은 제거한다.

`.class p{color:#000;line-height:18px}`

### 3. 인코딩

폰트 이름이 영문이 아닐 때 이를 브라우저에서 바르게 표현하고, HTML에서 불러온 스타읷을 제대로 렌더링하려면 반드시 CSS 읶코딩을 선언해야 한다. 
HTML과 동일한 인코딩을 묷서 첫 줄에 공백 없이 선언한다.

`@charset "utf-8";`


### 4. 속성

#### 4-1. 속성 선언 순서

속성을 선언할 때는 그 쓰임새가 레이아웃과 관련이 큰 것에서 시작하여 레이아웃과 무관한 것 순서로 선언한다. 







