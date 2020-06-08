# HTML element

## 1. Heading - h1 ~ h6

제목의 단계(Headings)를 뜻하며 사용자가 가장 먼저 읽는 콘텐츠는 제목이며 h 요소로 구성된다.

헤딩 태그는 문서의 주요 타이틀에 사용하며 중요도가 높은 제목일 수록 낮은 값을 갖는다.

※ h1 요소는 문서에서 단 한번만 사용할 수 있다.

```html
<h1>아이파트너즈</h1>
<h2>UX부문</h2>
```

## 2. Paragraphs – p

문장의 단락을 표현하기 위해 사용하며 새로운 문장을 사용해야 하는 경우 p 태그를 새로 선언하도록 한다.

p 요소는 하나의 문단을 나타낸다. HTML에서 문단은 이미지나 입력 폼 등 서로 관련있는 콘텐츠 무엇이나 될 수 있다.

```html
<p>Geckos are a group of usually small, usually nocturnal lizards. They are found on every continent except Australia.</p> 
<p>Some species live in houses where they hunt insects attracted by artificial light.</p>
```

## 3. Lists – ul(Unordered list), ol(Ordered list),dl(Description list)

목록은 리스트를 말하며 리스트는 크게 비순차형 목록, 순차형 목록, 정의(설명)형 목록으로 나눌 수 있다.

+ ul, ol : 비순차형 목록은 ul 이며 순차형 목록은 ol 요소를 사용한다. ul, ol 은 li(listed item)을 자식으로 가지고 있다.

+ dl(정의형 또는 설명형 목록) : 설명형 목록은 dt(Definition Term)인 용어, dd(Definition Description)인 용어 설명 요소와 dl(Description list)인 설명 목록으로 구성되는데 dl 은 dt, dd 를 자식으로 가지게 된다.

```html
<dl>
    <dt>넷플릭스</dt>
    <dd>넷플릭스 주식회사는 미국의 주문형 콘텐츠 서비스 제작 기업이다.</dd>
</dl>

<h3>넷플릭스 추천 작품</h3> 
<ul>
    <li>기묘한 이야기</li>
    <li>종이의 집</li>
    <li>나르코스</li>
</ul>

<h3>넷플릭스 인기 순위</h3>
<ol>
    <li>빅뱅이론</li>
    <li>모던 패밀리</li>
    <li>빨간머리 앤</li>
</ol>
```

## 4. Links – a(Anchor) 및 경로(path), image map

### a(anchor) - 하이퍼링크(Hyperlink)

```html
<a href="#" target="_blank">아이파트너즈</a>
```

앵커 요소는 주로 페이지 내 링크 이동 또는 다른 페이지로 이동하기 위해 사용한다. 

a 요소에 href 속성을 사용하여 링크 주소를 설정하고 요소 내부에는 콘텐츠를 추가하여 사용자에게 보여줄 수 있다.

하이퍼링크 주소는 파일을 참조하기 위해 인터넷은 URL(uniform resource locators)를 사용한다.


### 웹 문서에 URL을 입력하는 3가지 방법

+ 절대경로

절대 경로는 현재 HTML 문서와 상관없이 URL 주소를 사용해 리소스를 찾는 것을 말한다.

"http://www.ipartners.co.kr" 와 같이 사용한다. 

+ 상대 경로

상대경로는 현재 HTML 문서에서 상대적인 위치를 설정하는 것을 말한다.

"../main/index.html" 와 같이 사용한다.

+ 루트 상대경로

루트 상대경로는 현재 HTML 문서가 존재하는 영역의 최상위 루트 경로에서 대상을 찾는 것을 말한다.

"/index.html" 와 같이 사용한다.



## 5. 어휘(Phrasing) 요소

### strong 

strong 요소는 매우 심각하거나 긴급한 것(경고 등)을 포함하여 "강력한 중요" 을 나타낸다.

페이지 전체에 매우 중요한 문장이 될 수도 있고 어떤 단어들은 근처의 내용에 비해 더 중요하다는 것을  나타낼 수도 있다.

strong 요소는 기본적으로 굵은 글꼴로 웹페이지에 렌더링 되는데, 단순히 굵은 글꼴을 위한 스타일링을 적용하는데 사용해서는 안되며 그러한 목적으로는 CSS font-weight 속성을 사용해야 한다. 

※ 더 높은 중요도를 나타내지 않고 특정 텍스트에 주의를 끌려면 b 요소를 사용한다.


### b

b 요소는 독자의 주의를 요소의 콘텐츠로 끌기 위한 용도로 사용한다.

b를 사용해 텍스트를 꾸미면 안되며 CSS font-weight를 사용해 굵은 글씨체를 적용하거나 strong 요소를 사용해 특별히 중요한 텍스트를 나타내야 한다.

+ 요약 키워드, 리뷰의 제품명 등, 특별한 중요성을 가지고 있지는 않지만 굵게 표시할 부분에 b를 사용한다.

+ b 요소와 strong, em 요소를 혼동하지 않도록 주의한다. strong 요소는 중요한 글을, em 요소는 약간의 강조가 필요한 글을 나타낸다. b 요소는 아무런 의미도 갖지 않으므로 다른 요소가 적합하지 않을 때만 사용한다.


### em 

em 요소는 주위 텍스트에 비해 강조된 부분을 나타낸다. 보통 한 문장에서 단어 하나 혹은 몇 개로 제한되며, 문장의 의미에 영향을 미칠 수 있다.

em은 주로 기울임꼴을 적용해 표현하는데 단순히 기울임꼴이 필요해서 em을 사용하면 안되며 CSS font-style 속성을 사용해야 한다. 

### i 

요소는 텍스트에서 어떤 이유로 주위와 구분해야 하는 부분을 나타냅니다. 기술 용어, 외국어 구절, 등장인물의 생각 등을 예시로 들 수 있습니다. 보통 기울임꼴로 표시합니다









