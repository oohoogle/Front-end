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