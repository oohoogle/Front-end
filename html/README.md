# HTML (HyperText Markup Language)

### 1. 전역 구조화 엘리먼트

A. html

다음과 같이 lang 애트리뷰트를 선언한다.

`<html lang="ko">`

B. head

meta, title, link, script, style 순서로 엘리먼트를 선언한다.

```html
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<meta http-equiv="Content-Script-Type" content="text/javascript">
<meta http-equiv="Content-Style-Type" content="text/css">
<title>타이틀</title>
<link rel="stylesheet" type="text/css" href="css/default.css">
<script type="text/javascript" src="js/default.js"></script>
<style type="text/css">
</style>
</head>
```

C. meta

문서의 기본 인코딩, Viewport, 스크립트 형식, 스타일 형식 순서로 엘리먼트를 선언한다.

```html
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0,
minimum-scale=1.0, user-scalable=no, target-densitydpi=medium-dpi">
<meta http-equiv="Content-Script-Type" content="text/javascript">
<meta http-equiv="Content-Style-Type" content="text/css">
```

D. link

rel, type, href 순서로 애트리뷰트를 선언한다.

`<link rel="stylesheet" type="text/css" href="css/default.css">`

E. script

type, src 순서로 애트리뷰트를 선언한다. 

`<script type="text/javascript" src="js/default.js"></script>`

F. style

```html
<style type="text/css">
</style>
```

### 2. 폼 엘리먼트

폼 컨트롤 엘리먼트를 마크업할 때 form, fieldset, legend 엘리먼트를 다음과 같이 선언한다. 단, 필요에 따라 개별적으로 사용할 수 있다.

```html
<form action="">
<fieldset>
<legend> 야놀자 </legend>

</fieldset>
</form>
```

A. form

action 애트리뷰트는 서버 사이드 폼 핸들러이나 필수 선언 애트리뷰트이기 때문에, 마크업 단계에서 다음과 같이 선언한다.

```html
<form action="">
</form>
```

B. fieldset

form 엘리먼트의 자식 노드로 선언하여 폼 컨트롤 엘리먼트들을 그루핑하기 위해 선언한다.

```html
<form action="">
<fieldset>
<legend> 야놀자 </legend>
 
</fieldset>
</form>
```

C. legend

폼 컨트롤 그룹인 fieldset의 자식 엘리먼트로서 폼 컨트롤 엘리먼트들의 그룹 이름을 표현하기 위해 선언한다.

```html
<form action="">
<fieldset>
<legend> 야놀자 </legend>
 
</fieldset>
</form>
```

D. input

다음과 같이 label 엘리먼트 또는 title 애트리뷰트를 선언한다.

```html
<label for="user_id">아이디</label> <input type="text" id="user_id" name="user_id">
<input type="image" src="btn_confirm.gif" alt="확인">
<label for="num1">유선전화</label>
<input type="text" id="num1" name="num1" title="지역번호">
```

label 엘리먼트, title 애트리뷰트, alt 애트리뷰트를 통해 스크린 리더 사용자는 주변 맥락에 대한 이해 없이 각 엘리먼트에 독립적으로 접근해도 폼을 이해할 수 있다.
다음과 같이 type값에 따라 애트리뷰트를 선언한다.

+ type이 text인 경우: type, id, title, value 순서로 애트리뷰트를 선언한다.

`<input type="text" id="user_id" title="사용자ID" value="아이디를 입력하세요">`

+ type이 radio, checkbox인 경우: type, name, id, checked 순서로 애트리뷰트를 선언한다.

```html
<input type="radio" name="vt_align" id="align_lft" checked="checked"><label for="align_lft">왼쪽정렬</label>
<input type="radio" name="vt_align" id="align_cnt"> <label for="align_cnt">가욲데정렬</label>
<input type="radio" name="vt_align" id="align_rgt"> <label for="align_rgt">오른쪽정렬</label>
<input type="checkbox" name="sports" id="soccer" checked="checked"><label for="soccer">축구</label>
<input type="checkbox" name="sports" id="basketball"><label for="basketball">농구</label>
<input type="checkbox" name="sports" id="tennis"><label for="tennis">테니스</label>
```

+ type이 image인 경우: type, src, alt 순서로 애트리뷰트를 선언한다. 폼 전송 역할을 하는 디자인 버튼은 image 타입을 사용한다.
(디자인이 적용되지 않은 버튼은 `<button type="submit">`로 사용).

`<input type="image" src="img/btn_confirm.gif" alt="확인">`

E. select

동일한 스타일의 셀렉트 박스이나 너비값이 다르면 선택적으로 style 애트리뷰트를 이용하여 width값을 제어한다.

```html
<select style="width:100px">
<option>등급</option>
</select>
```

F. label
라디오 버튼, 체크 박스는 for 애트리뷰트를 부여하여 해당 엘리먼트의 id값과 동일한 이름으로 연결(coupling)한다.

```html
<input type="radio" name="alignment" id="align_lft"><label for="align_lft">왼쪽정렬</label>
<input type="checkbox" name="sports" id="soccer"> <label for="soccer">축구</label>
```

G. textarea

cols, rows 순서로 애트리뷰트를 선언한다. 
CSS를 정상적으로 불러오지 못하는 상황에서도 사용에 문제가 없도록 col, rows의 애트리뷰트값은 각각 최소 30, 5 이상이 되도록 선언한다.

`<textarea cols="30" rows="5"></textarea>`

H. button

type 애트리뷰트를 선언한다.

+ type 애트리뷰트를 button으로 선언하여 열기/닫기, 접기/펼치기 등의 UI를 제어한다.
+ 폼 전송 역할을 하는 디자인 미적용 버튼은 submit 타입을 사용한다(디자인 버튼은 `<input type="image">`로 사용).

```html
<button type="button">열기</button>
<button type="submit">전송</button>
```

### 3. 표 엘리먼트

표 엘리먼트를 아래와 같이 배치한다.

```html
<table cellspacing="0" border="1" summary="짬뽕은 자장면보다 500원 비싸고 열량이 50kcal 높다">
<caption>자장면과 짬뽕의 가격과 열량 비교</caption>
<col width="100" span="2">
<thead>
<tr>
<th>구분</th>
<th scope="col" abbr="가격">가격(won)</th>
<th scope="col" abbr="열량">열량(kcal)</th>
</tr>
</thead>
<tfoot>
<tr>
<th>계</th>
<td>6,500</td>
<td>650</td>
</tr>
</tfoot>
<tbody>
<tr>
<th scope="row">자장면</th>
<td>3,000</td>
<td>300</td>
</tr>
<tr>
<th scope="row">짬뽕</th>
<td>3,500</td>
<td>350</td>
</tr>
</tbody>
</table>
```

A. table

일반적으로 레이아웃을 표현하기 위해 사용하지 않고, 2차원의 격자형 데이터를 표현하기 위해 사용한다.

`<table summary="summary context here">`

B. caption

표의 제목을 표현하기 위해 사용한다.

`<caption>자장면과 짬뽕의 가격과 열량 비교</caption>`

표 윗부분의 헤딩 엘리먼트가 표의 제목 역할을 하는 경우에는 생략할 수 있다.

C. colgroup

col 엘리먼트를 그루핑하여 디자인을 제어할 때 선언한다. 이 엘리먼트는 선택적으로 사용한다.

```html
<colgroup>
<col width="100">
</colgroup>
<colgroup>
<col span="2" width="100">
</colgroup>
```

D. col

표 각 열의 너비 지정을 위해 선언한다.
width, span 애트리뷰트를 아래와 같은 순서로 선언한다.

```html
<col width="100" span="2">
<col width="100"><col width="100">
<col width="100"><col>
<col width="50%"><col width="50%">
```

width, span 애트리뷰트는 필요에 따라 선택적으로 사용한다.


E. thead

표 머리글을 그루핑할 때 선언한다. 이 엘리먼트는 th 엘리먼트만으로 그루핑되지 않으면 선언하지 않는다.

```html
<thead>
<tr>
<th>구분</th>
<th scope="col" abbr="가격">가격</th>
<th scope="col" abbr="열량">열량</th>
</tr>
</thead>
```


F. tfoot

표 바닥글을 그루핑할 때 선언한다. tfoot 애트리뷰트는 thead와 tbody 엘리먼트 사이에 위치해야 한다. 
이 애트리뷰트는 선택적으로 사용한다.

```html 
<thead>
…
</thead>
<tfoot>
<tr>
<th>계</th>
<td>6,500</td>
<td>650</td>
</tr>
</tfoot>
<tbody>
…
</tbody>
```

G. th

scope 애트리뷰트를 선언한다.

`<th scope="col" abbr="가격">가격</th>`

H. tbody

표 본문을 그루핑하기 위해 선언한다. 테이블의 본문(body)이 하나이고 thead나 tfoot이 없을 경우 생략할 수 있다.

```html
<tbody>
<tr>
<th scope="row">자장면</th>
<td>3,000</td>
<td>300</td>
</tr>
</tbody>
```

### 4. 기타 엘리먼트

A. a

href, target, title 순서로 애트리뷰트를 선언한다.

+ 새 창으로 페이지를 표시해야 할 때 target 애트리뷰트를 선택적으로 사용한다.
+ class로 디자인을 제어할 경우 class 애트리뷰트를 선택적으로 사용한다.
+ title 애트리뷰트는 예고 없이 새 창을 표시해야 하거나 이동 경로를 정확히 알 수 없을 때, 또는 브라우저에 독립적으로 툴팁을 표현하기 위해 사용한다.

`<a href="index.html" target="_blank" title="새창">인쇄하기</a>`

B. img

src, width, height, title, alt, usemap 순서로 애트리뷰트를 선언한다

+ 이미지 내용과 동일한 값을 alt 애트리뷰트에 표기하여, 이미지를 볼 수 없는 환경(스크린 리더, 이미지서버 장애, 이미지 표시 하지 않음 설정)에서도 내용을 확인할 수 있게 한다.
+ title 애트리뷰트를 선언한 경우에도 alt 애트리뷰트를 함께 선언한다.
+ title 애트리뷰트는 alt 애트리뷰트값을 축약하거나 브라우저에 독립적으로 툴팁을 표현하기 위해 사용한다.

`<img src="logo.gif" wdith="30" height="10" title="고객센터" alt="고객센터" usemap="#help">`

C. map

map 엘리먼트의 name 애트리뷰트를 선언하여 img 엘리먼트의 usemap 애트리뷰트와 같은 이름으로 연결한다.

```html
<img src="img_main.gif" width="696" height="196" title="한글날이벤트" alt="한글날이벤트, 한글을 글꼴로 나눕니다" usemap="#help">
<map name="help">
<area shape="rect" coords="506,48,608,139" href="#" target="_blank" title="고객센터" alt="고객센터">
</map>
```

D. area

shape, coords, href, target, title, alt 순서로 애트리뷰트를 선언한다.

+ title 애트리뷰트를 선언한 경우에도 alt 애트리뷰트를 함께 선언한다.
+ target 애트리뷰트는 새 창으로 페이지를 표시해야 할 때 사용한다.
+ title 애트리뷰트는 예고 없이 새 창을 표시해야 하거나 이동 경로를 정확히 알 수 없을 때, alt 애트리뷰트값을 축약하거나, 브라우저에 독립적으로 툴팁을 표현하기 위해 사용한다.

```<area shape="rect" coords="506,48,608,139" href="#" target="_blank" title="새창" alt="고객센터">```

