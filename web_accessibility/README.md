# web_accessibility

## 웹접근성 참고 사이트

[kwacc](http://www.kwacc.or.kr/WAI/wcag21/)

[웹접근성연구소](https://www.wah.or.kr:444/index.asp)

[레진웹접근성가이드라인](https://github.com/lezhin/accessibility)

[네이버웹접근성](https://accessibility.naver.com/accessibility)



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