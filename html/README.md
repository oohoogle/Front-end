# HTML


## HTML 엘리먼트 작성 규칙

### 1. 기본규칙

특정 엘리먼트에 class, style을 선언할 때는 선언 순서를 준수한다. 다음과 같이 class와 style은 제일 뒷부분에 선언한다.

`<input type="text" id="user_id" title="사용자ID" class="input_txt" style="width:100px;">`


### 2. 전역 구조화 엘리먼트

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
 [stuff]
</style>
</head>
```

C. meta

문서의 기본 인코딩, Viewport, 스크립트 형식, 스타일 형식 순서로 엘리먼트를 선언핚다.
Viewport는 모바일 브라우저에 대응하는 HTML의 경우에만 선언한다.

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

### 3. 폼 엘리먼트

폼 컨트롤 엘리먼트를 마크업할 때 form, fieldset, legend 엘리먼트를 다음과 같이 선언한다. 단, 필요에 따라 개별적으로 사용할 수 있다.

```html
<form action="">
<fieldset>
<legend> 야놀자 </legend>

</fieldset>
</form>
```

A. form

action 애트리뷰트는 서버 사이드 폼 핸들러이나 필수 선언 애트리뷰트이기 때문에, 마크업 단계에서 다음과 같이 선언핚다.

```html
<form action="">
</form>
```

B. fieldset

form 엘리먼트의 자식 노드로 선언하여 폼 컨트롤 엘리먼트들을 그루핑하기 위해 선언한다.

```html
<form action="">
<fieldset>
<legend>개인정보</legend>
 
</fieldset>
</form>
```

C. legend

폼 컨트롤 그룹인 fieldset의 자식 엘리먼트로서 폼 컨트롤 엘리먼트들의 그룹 이름을 표현하기 위해 선언한다.