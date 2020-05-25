# css

## CSS 코드 작성 규칙

### 1. 기본 규칙

A. W3C Validation

모바일에서 CSS는 사용 가능한 Hack과 CSS3 속성을 제외하고 W3C Validation을 통과해야 핚다.

B. 영문 소문자 사용

모든 속성은 영문 소문자로만 작성한다.

C. 따옴표 사용 범위

공백이 포함된 폰트명, 한글 폰트명, string 데이터 타입, filter 속성의 파라미터값은 작은따옴표(' ')로 감싸며, 
@charset 선언 시에는 속성값을 큰따옴표(" ")로 감싼다. 그 외의 경우에는 따옴표를 사용하지 않는다.
filter 속성의 파라미터값에 따옴표를 사용하는 것은 선택사항이다.
url 데이터 타입에는 작은 따옴표를 사용하지 않는다.

예)
```css
font-family:'돋움'
filter:progid:DXImageTransform.Microsoft.AlphaImageLoader(src='bg.png',sizingMethod='scale')
background:url(bg.gif) no-repeat 0 0
content:'Chapter:'
charset "utf-8";
```