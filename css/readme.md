# css	

- 네이밍 규칙

  네이버코딩 컨벤션 참고

  https://github.com/jewdri-kim/uiDevelop/blob/master/css/NHN_Coding_Conventions_for_Markup_Languages-ko_open.pdf

- 속성 표기 규칙

  네이버코딩 컨벤션 참고

  https://github.com/jewdri-kim/uiDevelop/blob/master/css/%EC%BB%A8%EB%B2%A4%EC%85%98CCS%EA%B4%80%EB%A0%A8v1.0.odt

- css 방법론

  https://kaylee105.github.io/css/

- 팀만의 스타일 혹은 프로젝트 가이더의 스타일에 준수하여 서로 맞추는것이 중요!

- 업무 특성에 따라 효율적인 규칙을 만드는것이 중요



- 아래부턴 우리팀에서 적용하는 방법 (참고)



## 속성 선택자 활용*

- 속성 선택자(Attribute Selector)는 특정 속성(attribute)을 갖고 있거나 특정 속성이 특정 값 등을 갖고 있는 요소(element)를 선택
- 속성선택자의 형태
  - [attribute]
  - [attribute="value"]
  - [attribute~="value"]
  - [attribute|="value"]
  - [attribute^="value"]
  - [attribute$="value"]
  - [attribute*="value"]
- 우리가 평소에 많이 쓰는것중 하나 

```css
input[type="text"],
input[type="submit"],
input[type="password"],
input[type="search"],
input[type="number"],
input[type="reset"],
input[type="email"], input[type="tel"],
input[type="search"],
input[type="file"],
input[type="email"],
input[type="tel"],
textarea{width:100%;border:1px solid #ddd;height:50px;box-sizing:border-box;padding:0 19px;font-size:16px;color:$CBlack;letter-spacing:-1px;font-weight:500;font-family:"Roboto","Noto",sans-serif;line-height:50px}

input[type="submit"] {cursor:pointer}

input[readonly]
```



### [attributename^="value"]   ( css3 )

- 우리팀에서 제일 많이 활용하는것 
- attributename 속성의 값이 value로 시작하는 요소를 선택



#### 공통스타일 적용하기

- 이 선택자를 활용하여 공통 네이밍 정하고 그걸로 시작하는 클래스들에게 공통 스타일 적용

```css
[class^='btn-wrap']{
	margin-top:30px;
	font-size:0;
	text-align:center;

	[class^='btn-']+[class^='btn-']{
		margin-left:20px;
	}
}
```

```css
[class^='btn-type']{
	display:inline-flex;
	align-items:center;
	justify-content:center;
	position:relative;
	height:80px;
	margin-left:8px;
	border-radius:40px;
	font-size:24px;
	text-align:center;
	line-height:80px;
	letter-spacing:-0.18px;
	color:#fff;
	transition:0.5s;
	font-family:$fontE,$fontK;
	font-weight:400;
}
```



#### 개별 요소마다 스타일 적용



##### 1. 아이콘예시

- 클래스가 'ico-' 로 시작하는 선택자들에게 아래 공통으로 스타일 적용!
- 각각의 아이콘마다  사이즈와 백그라운드 position위치만 다르므로!
- http://code.d2.co.kr/2019/ahc/pc/shop/html/guide/icon.html

```css
[class^='ico-']{
	display:inline-block;
	background:url($sp-common) no-repeat 0 0;
}
.ico-user{
	width:97px;
	height:90px;
	background-position-y:-87px;
}
.ico-users{
	width:76px;
	height:68px;
	background-position:-61px -179px;
}
```



##### 2. 버튼예시

