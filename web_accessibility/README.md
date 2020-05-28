# web_accessibility

## 웹접근성 참고 사이트

[w3c](https://www.w3.org/)

[kwacc](http://www.kwacc.or.kr/WAI/wcag21/)

[웹접근성연구소](https://www.wah.or.kr:444/index.asp)

[레진웹접근성가이드라인](https://github.com/lezhin/accessibility)

[네이버웹접근성](https://accessibility.naver.com/accessibility)


### 웹 접근성 정의

웹 접근성의 정의는 기관별로 약간씩 차이가 있으나, 이 문서에서는 보편적 접근성(Universal Accessibility)으로 정의한다.

보편적 접근성이란, 모든 사람이 다양한 조건의 환경에서 다양한 장치를 이용하여 웹 콘텐츠에 접근할 수 있도록 보장하는 것을 의미한다. 
보편적 접근성을 보장하게 되면 장애를 지닌 사람부터 일시적으로 불리한 조건을 갖게 된 정상인에 이르기까지 편리하게 웹 콘텐츠에 접근할 수 있다. 
또한, 네트워크 속도가 느리거나 모바일 기기를 사용하는 경우, 
다양한 운영체제와 웹 브라우저를 사용하는 경우 등의 환경 조건에 관계없이 웹 콘텐츠에 접근할 수 있어 웹의 사용성을 증가시킨다.

### 1. 의미를 전달하고 있는 이미지에 대체 텍스트를 제공한다.

+ 대체 텍스트는 이미지의 시각적 의도와 동등한 내용을 전달한다.
+ 대체 텍스트는 중복으로 제공하지 않는다.

```html
<!-- X -->
<img src="ipa.png">
<img src="ipa.png" alt>
<img src="ipa.png" alt="">
<img src="ipa.png" title="아이파트너즈">
<img src="ipa.png" alt="아이파트너즈" title="아이파트너즈">

<!-- O -->
<img src="ipa.png" alt="아이파트너즈">

<!-- X -->
<a href="/">
    <img src="ipa.png" alt="아이파트너즈"> 아이파트너즈
</a>

<!-- O -->
<a href="/">
    <img src="ipa.png" alt> 아이파트너즈
</a>

<!-- X -->
<a href="/" style="background:url(ipa.png) no-repeat"></a>

<!-- O -->
<a href="/" style="background:url(ipa.png) no-repeat">아이파트너즈</a>
```


### 2. 링크와 버튼 텍스트는 콘텐츠의 목적을 알 수 있다.

+ 주변 콘텐츠와 분리하여 독립적으로 접근해도 링크 또는 버튼의 목적을 알 수 있어야 한다.
+ 링크 또는 버튼에 독립적으로 접근하여 이해하기 어려운 경우 동일한 단락, 목록, 셀, 연결된 헤더셀(p, li, td, th)에 링크 또는 버튼의 목적을 설명해야 한다.

```html
<!-- X -->
<a href="#" download>설치하기</a>
<button type="button">삭제하기</button>

<!-- O -->
<a href="#" download>안드로이드 애플리케이션 설치하기</a>
<p>안드로이드 애플리케이션 <a href="#" download>설치하기</a></p>
<li>안드로이드 애플리케이션 <a href="#" download>설치하기</a></li>
<td>안드로이드 애플리케이션 <a href="#" download>설치하기</a></td>
<tr>
    <th scope="row">안드로이드 애플리케이션</th>
    <td><a href="#" download>설치하기</a></td>
</tr>

<!-- O -->
<button type="button">구매내역 삭제하기</button>
<p>구매내역 <button type="button">삭제하기</button></p>
<li>구매내역 <button type="button">삭제하기</button></li>
<td>구매내역 <button type="button">삭제하기</button></td>
<tr>
    <th scope="row">구매내역</th>
    <td><button type="button">삭제하기</button></td>
</tr>
```

### 3. 섹션에는 의미 있는 마크업과 헤딩이 있다.

+ 섹션 콘텐츠는 의미에 알맞은 article, section, nav, aside 요소로 마크업한다.
+ 섹션 콘텐츠에는 문서의 개요 체계에 알맞은 헤딩(h1~h6)을 제공한다.
+ 명시적 헤딩 기법을 사용한다. 명시적 헤딩 기법은 하나의 문서에 h1 요소를 한 번 사용한다.

```html
<!-- X -->
<div class="article">...</div>
<div class="section">...</div>
<div class="nav">...</div>
<div class="aside">...</div>

<!-- O -->
<article>
    <h2>...</h2>
    ...
</article>
<section>
    <h2>...</h2>
    ...
</section>
<nav>
    <h2>...</h2>
    ...
</nav>
<aside>
    <h2>...</h2>
    ...
</aside>
```

### 4. 문서의 휴먼 랭귀지 속성을 제공한다.

+ html 요소에 lang 속성을 제공한다.
+ 한글, 영문, 일문, 중문에는 이를 식별하기 위한 ISO-639-1 코드값 ko, en, ja, zh가 있다.

```html
<!-- X -->
<html>

<!-- O -->
<html lang="ko">
```

### 5. 폼 콘트롤 요소에 설명을 제공한다.

+ 모든 input, textarea, select 요소에는 콘트롤을 설명하는 label 요소를 맵핑하거나 또는 title 속성을 제공한다.

```html
<!-- X -->
<form>
    <input type="search">
    <button>검색</button>
</form>

<!-- O -->
<form>
    <label for="search">검색</label>
    <input id="search" type="search">
    <button>검색</button>
</form>

<!-- O -->
<form>
    <input type="search" title="검색">
    <button>검색</button>
</form>
```

### 6. 반복되는 콘텐츠 블록을 건너뛸 수 있다.

+ 일반적으로 글로벌 탐색 바와 로컬 탐색 바는 반복되는 콘텐츠 블록이다.
+ 반복되는 콘텐츠 블록이 있는 경우 페이지 시작 위치에 '본문으로 건너뛰기' 링크를 제공한다.

```html
<!-- X -->
<body>
    <h1>아이파트너즈</h1>
    <nav>...</nav>
    <main>...</main>

<!-- O -->
<body>
    <a href="#main">본문으로 건너뛰기</a>
    <h1>아이파트너즈</h1>
    <nav>...</nav>
    <main id="main">...</main>
</body>
```