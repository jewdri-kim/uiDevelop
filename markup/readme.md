# HTML Tag	

- HyperText Markup Language
- https://developer.mozilla.org/ko/docs/Web/HTML
- html 은 웹콘텐츠의 의미와 구조를 정의 

- 4.01 태그정리

  https://github.com/jewdri-kim/uiDevelop/blob/master/markup/%ED%83%9C%EA%B7%B8%EC%A0%95%EB%A6%AC.odt



## Semantic VS Non-semantic

- 버튼예시 : https://www.w3schools.com/html/html_accessibility.asp

- https://developer.mozilla.org/ko/docs/Learn/HTML/Howto

- https://www.w3schools.com/html/html5_semantic_elements.asp



### 텍스트 강조의 예

![](https://github.com/jewdri-kim/uiDevelop/blob/master/img/text2.png)

#### Semantic

```html
<strong>100%당첨</strong> 할인 쿠폰 룰렛!
```

```html
<strong><em>100%당첨</em> 할인 쿠폰 룰렛!</strong>
```

```html
<h3><em>100%당첨</em> 할인 쿠폰 룰렛!</h3>
```

```html
<h3><strong>100%당첨</strong> 할인 쿠폰 룰렛!</h3>
```

#### Non-semantic

- css는 겉모양 입혀질뿐, 의미는 없음
- span, div는 의미없는 태그로영역 분리용
- 의미가 있는 강조가 있는 컨텐츠에 의미없는 태그사용은 테이블코딩과 차이가 없다. (테이블로 영역나누기)

```css
.event-name{font-size:50px;color:#000;}
.text-type{color:#c626d5;}
```

```html
<p class="event-name"><span class="text-type">100%당첨</span> 할인 쿠폰 룰렛!</p>
```

```html
<div class="event-name"><span class="text-type">100%당첨</span> 할인 쿠폰 룰렛!</div>
```



#### 같은 강조의 텍스트 디자인 입힐땐??

![](https://github.com/jewdri-kim/uiDevelop/blob/master/img/text.png)

- 영문과 국문을 구분하여 폰트스타일만 다르게 적용하기 위함
- 간격주기위해서도 사용

```html
<style>
    h2 span{font-family:'audi_ex'}
</style>
<h2>
    <span>Audi RS e-tron GT</span> 사전 예약
</h2>
```

- But
- 전체 font-family에 영문폰트 먼저 지정하면, 영문 아닌 텍스트는 자동으로 국문용 폰트로 !

```html
<style>
    body{font-family:'audi_ex','NotoSans'}
</style>
<h2>
    <span>Audi RS e-tron GT</span> 사전 예약
</h2>
```



## 구조설계

- 구조설계 실습 ppt

  https://github.com/jewdri-kim/uiDevelop/blob/master/markup/%EA%B5%AC%EC%A1%B0%EC%84%A4%EA%B3%84%EC%8B%A4%EC%8A%B5.ppt

- 하나의 같은화면이라도 다양한 관점으로 해석이 가능하다.

- 서로 이러한 부분들에 나누고 협의하는게 중요

- 기존 업무할때 쓰던 PSD로 여러개의 마크업해보고 나눠보기

  



