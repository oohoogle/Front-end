# web_accessibility

## 웹접근성 참고 사이트

[w3c](https://www.w3.org/)

[kwacc](http://www.kwacc.or.kr/WAI/wcag21/)

[웹접근성연구소](https://www.wah.or.kr:444/index.asp)

[네이버웹접근성](https://accessibility.naver.com/accessibility)


### 웹 접근성 정의

웹 접근성은 장애를 가진 사람과 장애를 가지지 않은 사람 모두가 웹사이트를 이용할 수 있게 하는 방식을 가리킨다. 
사이트가 올바르게 설계되어 개발되고 편집되어 있을 때 모든 사용자들은 정보와 기능에 동등하게 접근할 수 있다. 

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

### 7. 초점이동

마우스와 같은 포인팅 장치를 이용하기 어려운 시각/지체 장애 사용자는 키보드만으로도 모든 정보의 접근 및 조작이 가능해야 하기 때문에 키보드에 의한 초점은 논리적으로 이동해야 하며 시각적으로 구별할 수 있어야 합니다.

+ 초점의 이동 순서는 순차적으로 일관성있게 이동해야 합니다. 일반적으로 페이지의 좌측 상단 영역에서 우측 하단 영역으로 이동하는 것이 원칙입니다.
+ 초점 이동 순서가 순환적이며, 반복적이어야 합니다.
+ 페이지에 포함된 모든 링크, 버튼, 입력창에 초점이 가야합니다.
+ 사용자가 사용할 수 없는 비활성 요소(버튼, 입력창 등)에는 초점이 가지 않아야 합니다.
+ 화면을 가리는 레이어 팝업 또는 모달창의 경우 가장 먼저 초점을 받게 합니다.