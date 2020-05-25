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

meta, title, link, script, style 숚서로 엘리먼트를 선언핚다.

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