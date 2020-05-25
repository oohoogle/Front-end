# css

## css 코드 작성 규칙

### 1. 기본 규칙

A. W3C Validation

모바일에서 CSS는 사용 가능한 Hack과 CSS3 속성을 제외하고 W3C Validation을 통과해야 한다.

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

폰트 이름이 영문이 아닐 때 이를 브라우저에서 바르게 표현하고, HTML에서 불러온 스타일을 제대로 렌더링하려면 반드시 CSS 인코딩을 선언해야 한다. 
HTML과 동일한 인코딩을 묷서 첫 줄에 공백 없이 선언한다.

`@charset "utf-8";`


### 4. 속성

#### 4-1. 속성 선언 순서

속성을 선언할 때는 그 쓰임새가 레이아웃과 관련이 큰 것에서 시작하여 레이아웃과 무관한 것 순서로 선언한다. 

1) 표시 : display

2) 넘침 : overflow

3) 흐름 : float

4) 위치 : position

5) 크기 : width & height

6) 간격 : margin & padding 

7) 테두리 : border

8) 배경 : background 

9) 폰트 : font

10) 기타

#### 4-2. 약식속성의 전체속성 선언 순서

1) margin : margin-top, margin-right, margin-bottom, margin-left

2) padding : padding-top, padding-right, padding-bottom, padding-left

3) border : border-top, border-right, border-bottom, border-left, border-width, bordertop-width, border-right-width, border-bottom-width, border-left-width,
border-style, border-top-style, border-right-style, border-bottom-style, borderleft-style, border-color, border-top-color, border-right-color, border-bottomcolor, border-left-color

4) background : background-color, background-image, background-repeat, backgroundattachment, background-position

5) font : font-style, font-variant, font-weight, font-size, font-family, line-height
 

#### 4-3. 약식 속성 사용 범위

background와 border는 약식 속성을 우선적으로 사용하며, font 약식 속성은 사용하지 않는다.

A. background

속성값은 background-color, background-image, background-repeat, background-attachment, background-position 순서로 선언한다.

배경 스타일 속성을 초기 선언할 때는 반드시 background 단일 속성을 사용하며, 이후 배경의 부분적인
속성이 변경될 경우 background 관련 속성(background-attachment, background-color, backgroundimage, background-position, background-repeat)을 선언한다.

```css
.class {background:#ccc url(bg.gif) no-repeat 0 0}
.class_v1 {background-position:0 -50px}
.class_v2 {background-position:0 -100px}
```

B. border

속성값은 border-width, border-style, border-color 순서로 선언한다.

테두리 스타읷 속성을 초기 선언할 때는 반드시 border 단일 속성을 사용하고, 이후 테두리의 부분적인 속성이 변경될 경우 border 관련 속성(border-width, border-style, border-color)을 선언한다.

```css
.class {border:1px solid #ccc}
.class_v1 {border-color:#666}
.class_v2 {border-style:dotted}
.class2 {border-top:1px solid #ccc}
.class2_v1 {border-top-color:#666}
.class2_v2 {border-top-style:dotted}
```

테두리의 상, 우, 하, 좌 스타일이 2개 이상 다르면, 공통 스타일을 약식 속성으로 선언한 후 다른 부분은 관련 속성으로 선언한다.

```css
.class{border:1px solid;border-color:#ddd #ddd #eee #eee}
.class{border:1px;border-style:solid dotted;border-color:#ddd #ddd #eee #eee}
```

C. font

폰트 스타일은 약식 속성으로 선언하지 않는다.

`.class p{font-family:gulim;font-style:normal;font-variant:normal;font-weight:normal;font-size:15px;line-height:normal}`

#### 4-4. 한글 폰트 선언

영문폰트를 선언할 경우 특정 브라우저에서 폰트를 올바르게 출력하지 못하는 경우가 있으므로 한글 폰트 선언 시 한글, 영문 폰트를 모두 선언한다.

`font-family:'돋움',dotum`

## 5. 초기 타입

```css
@charset "utf-8";
body,p,h1,h2,h3,h4,h5,h6,ul,ol,li,dl,dt,dd,table,th,td,form,fieldset,legend,input,textare
a,button,select{margin:0;padding:0}
body,input,textarea,select,button,table{font-family:'돋움',Dotum,AppleGothic,sansserif;font-size:12px}
img,fieldset{border:0}
ul,ol{list-style:none}
em,address{font-style:normal}
a{text-decoration:none}
a:hover,a:active,a:focus{text-decoration:underline}
```



