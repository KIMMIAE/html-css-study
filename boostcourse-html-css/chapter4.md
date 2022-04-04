# 4. CSS 이해하기
**Goal**
* Cascading Style Sheets(CSS) 문법을 익힌다.
* 평소 헷갈리던 선택자 용어를 확실히 익힌다.

## 4.1 CSS 소개
**CSS와 HTML**
* HTML(마크업 언어)을 꾸며주는 표현용 언어
* html이 웹페이지의 정보를 **표현**한다면, CSS는 html을 보기 좋게 디자인하는 역할
* CSS는 분명히 HTML과는 독립된 다른 언어지만 마크업 문서 자체가 존재하지 않으면 CSS는 무용지물이나 마찬가지이다.
 * CSS는 표현을 위한 언어인데 마크업 문서가 없다면 표현할 대상이 없기 때문이다.

**CSS로 표현한 다양한 웹 사이트들**
* 전 세계 많은 웹 사이트들은 모두 HTML 태그를 이용해서 만들어졌는데, 자주 사용되는 태그의 개수를 10여 개밖에 되지 않는다.
* 모든 사이트가 비슷한 HTML 태그를 사용해서 만들어졌음에도 각각 다양하고 독창적인 디자인으로 표현 가능한 이유가 바로 CSS 덕분이다.
* CSS는 문서를 디자인하는 강력한 힘을 가졌다.

### 구경하기
* [CSS Zen Garder](http://www.csszengarden.com/)

## 4.2 CSS 문법과 적용
**CSS 구문**
```css
h1 { color: yellow; font-size: 2em; }
```
* 선택자(selector) - "h1"
* 속성(property) - "color"
* 값(value) - "yellow"
* 선언(declaration) - "color: yellow", "font-size: 2em" (속성과 값을 묶어서 '선언'이라 함)
* 선언부(declaration block) - "{ color: yellow; font-size: 2em; }" 중괄호를 포함한 부분
* 규칙(rule set) - "h1 { color: yellow; font-size: 2em; }" 선택자까지 모두 합쳐진 부분을 규칙이라 함

**CSS의 속성(Property)과 HTML의 속성(Attribute)**
* HTML에도 속성이 있고, CSS에도 속성이 있다. 두 가지는 전혀 다른 것이다.
* HTML의 속성은 영어로 attribute이고, CSS의 속성은 property이다.
* 둘 다 한국어로 번역할 때 "속성"이라고 하므로 잘 구분해야 한다.

**CSS 주석**
```css
/* 주석 내용 */
/*
  주석은 여러 줄로도
  선언 할 수 있음.
*/
```

**CSS의 적용**
1. Inline
```html
<!--
  Inline은 해당 요소에 직접 스타일 속성을 이용해서 규칙들을 선언하는 방법이다.
  해당 요소에 직접 입력하기 때문에 선택자는 필요하지 않게 되고, 선언부에 내용만 스타일 속성의 값으로 넣어주면 된다.
  Inline 스타일 방식은 코드의 재활용이 되지 않기 때문에 자주 사용하지 않는다.
-->
<div style="color:red;"> 내용 </div>
```

2. Internal
```html
<!--
  Internal은 문서에 <style>을 활용한 방법이다.
  <style>은 <head>내부에 들어가며 <style>안에 스타일 규칙이 들어간다.
  아래의 코드로 모든 <div>에 같은 스타일을 줄 수 있다. 하지만 이것도 한계가 있다.
  많은 페이지가 있는 경우에는 모든 페이지에 저마다의 규칙을 선언해줘야 한다.
  페이지가 많고 스타일 규칙 내용이 많아지면 결코 쉬운 일은 아니다.
-->
<style> div {color: red;} </style>
```

3. External
```css
/*
  External은 외부 스타일 시트 파일을 이용한 방법이다.
  외부 스타일 시트는 스타일 규칙들을 별도의 외부 파일을 만들어 넣는 방식이다.
  외부 파일은 확장자가 .css가 되며 css 파일이라고 부른다.
*/
/* 우선 CSS 파일을 하나 만들고 스타일 규칙을 선언한다 */
/* css/style.css */
div {color: red;}
```

```html
<!-- 그다음 <link>을 이용해서 CSS 파일을 연결하면 됩니다. -->
<link rel="stylesheet" href="css/style.css">
<!-- 
  <head> 내부에 <link>를 선언한 후 href 속성을 이용해 CSS 파일의 경로를 적는다.
  rel 속성은 연결되는 파일이 문서와 어떤 관계인지를 명시하는 속성으로, CSS 파일은 'stylesheet' 라고 적어야 한다.
  외부 스타일 시트 방식으로 스타일을 선언하면 많은 페이지가 있더라도 이 한 줄로 모든 페이지에 같은 스타일을 적용할 수 있다.
  또한, 수정이 필요할 때도 CSS 파일을 수정하면 연결된 모든 페이지에 반영할 수 있다.
  외부 스타일 시트 방식은 파일 관리가 편하면서도 용량이 작기 때문에 주로 사용되는 방법이다.
-->
```
4. Import
```css
/* Import는 스타일 시트 내에서 다른 스타일 시트 파일을 불러오는 방식이다 */
@import url("css/style.css");
/* <style> 내부 상단이나 외부 스타일 시트 파일 상단에 선언하는데 성능상 좋지 않아서 거의 쓰이지 않는다 */
```

### 알아두기
* css 적용 방법에서 import하는 방법은 성능상 좋지 않아서 거의 쓰이지 않는다고 했다. 그 이유는 무엇인가?
 * ```@import```는 CSS파일의 렌더링 속도를 느리게 하는데, ```@import``` 방식의 경우 ```@import``` 된 css들을 직렬 로딩 방식으로 불러오기 때문이다.
```css
@import "test1.css";  /* 1번째 */
@import "test2.css";  /* 2번째 */
@import "test3.css";  /* 3번째 */
```
* 반면 link 방식 (외부 스타일 방식)의 경우 병렬 로딩 방식으로 불러오기 때문에 test1, test2, test3가 동시에 로딩돼서 페이지 로딩 속도가 @import 방식에 비해 빠르고 효율적이다.

### 읽어보기
* [don’t use @import](https://www.stevesouders.com/blog/2009/04/09/dont-use-import/)
* [Best way to include CSS? Why use @import?](https://stackoverflow.com/questions/10036977/best-way-to-include-css-why-use-import)
* [CSS 성능 향상시키기-@import 사용 자제하기](https://yceffort.kr/2021/03/improve-css-performance#import-%EC%82%AC%EC%9A%A9-%EC%9E%90%EC%A0%9C%ED%95%98%EA%B8%B0)
