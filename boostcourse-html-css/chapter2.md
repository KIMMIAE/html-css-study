# 2. HTML 태그
**Goal**
* 의미에 맞는 태그를 사용하여 브라우저가 잘 이해할 수 있도록(시멘틱 마크업) 태그를 숙지한다

## 2.1 HTML 태그 소개
* HTML 버전이 업그레이드되면서 태그가 새로 추가되기도 하고 삭제되기도 한다.
 * 현재 태그의 개수는 약 130여 개 정도이다
* 관련 통계 사이트를 보면 대부분의 웹 페이지는 약 25개 정도의 서로 다른 태그가 사용된다고 한다.
 * [통계 사이트 참고](https://www.advancedwebranking.com/seo/html-study/#overview)


## 2.2 제목과 단락요소
* 제목 태그
 * 제목(heading) 태그는 문서 내에 제목을 표현할 때 사용하는 태그이다.
 * 보통 ```<h1>```은 해당 페이지를 대표하는 큰 제목으로 주로 사용되며, 숫자가 올라갈수록 조금 더 낮은 수준의 소제목을 나타내게 된다.
* 단락 태그
 * 단락(paragraph) 태그는 paragraph를 줄여서 p로 쓴다.
 * ```<p>``` 태그를 사용해서 단락으로 구분하면 자연스럽게 개행이 된다.
* 개행
 * html은 한 칸 이상의 공백 및 개행을 무시하기 때문에 실제 코드창에 개행을 하더라도 화면에 나타나지는 않는다.
 * (강제로) 개행을 하기 위해 쓰이는 태그가 바로 ```<br>``` 태그이다.
 * linebreak를 줄여서 br이라고 한다.
 * ```<br>```은 닫기 태그와 내용이 존재하지 않는 빈 태그이다.
 * 개행하고자 하는 곳에서 ```<br>```을 선언하면 개행이 된다.

## 2.3 텍스트를 꾸며주는 요소
* ```<b>```: bold, 글자를 굵게 표현한다.
* ```<i>```: italic, 글자를 이탤릭체로 표현한다
* ```<u>```: underline, 글자에 밑줄을 표현한다.
* ```<s>```: strike, 글자에 중간선을 표현한다.
* ```<b>, <u>, <s>```는 의미가 없는 표현용 태그이다.
 * ```<s>``` 태그는 예전에 존재했던 strike 태그와는 다른 태그로, 기존 strike 태그는 폐기되어 더는 사용할 수 없음
* HTML5 버전 부터는 ```<i>``` 태그가 단순 표현용 태그에서 의미를 가지는 태그로 변경되었다.
 * 특정 이유(기술적인 용어, 외국어 문구, 소설속 인물의 생각 등)로 다른 글자와 구분하기 위해 사용됨

### 미리 알아두기
* 시멘틱 마크업이란?
 * '시멘틱' 마크업 => '의미론적인' 마크업
 * 시멘틱은 기계가 잘 이해할 수 있도록 하는 것이다. 여기서 기계는 보통 컴퓨터, (웹 개발자에겐)브라우저이다.
 * 프로그래밍 언어는 사람과 기계와의 약속 같은 것인데 HTML도 비슷하다.
  * ex.```<h1>``` 태그는 제목에 사용하자 문단을 나눌 때는 ```<p>```태그를 사용하자

```html
<!-- 화면을 보면 각각의 요소가 같은 모습으로 표현되나 그 의미가 같지는 않다. 의미를 포함할 때는 용도에 맞는 의미를 가진 우측의 태그를 사용하는 게 적절하고 시멘틱한 마크업이다. -->
<b>굵은</b> vs <strong>중요한</strong><br>
<i>기울어진</i> vs <em>강조하는</em><br>
<u>밑줄친</u> vs <ins>새롭게 추가된</ins><br>
<s>중간선이 있는</s> vs <del>삭제된</del> 
```

### 읽어보기
* [Inline text semantics](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#inline_text_semantics)

## 2.4 앵커 요소
```html
<a href="http://www.naver.com/">네이버</a>
```
* 다른 문서로 이동할 수 있는 링크를 생성한다.
* href: 링크의 목적지가 되는 URL을 지정한다.
* target: 링크된 리소스를 어디에 표시할지를 나타낸다.
  * _self: 현재 화면에 표시한다는 의미로, target 속성이 선언되지 않으면 기본적으로 self와 같이 동작한다.
  * _blank: 새로운 창에 표시한다는 의미로 외부 페이지가 나타나게끔 하는 속성이다.
* ```<a>```를 통해 페이지 내부의 특정 요소로 초점을 이동할 수도 있는데, 이를 내부 링크라고 한다.
* 내부 링크를 사용할 때는 href 속성값에 #을 쓰고 그 뒤에 페이지 내에서 이동하고자 하는 요소의 id 속성값을 적으면 된다

```html
<h1 id="top">앵커 요소</h1>
(...)
<a href="#top">위로 가기</a>
```

### 읽어보기
* [The Anchor element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)

## 2.5 의미가 없는 컨테이너 요소
* 아무 의미가 없는 태그도 있다. 태그 자체에 아무 의미가 없으며, 단순히 요소들을 묶기 위해 사용되는 태그들이다.
* 스타일을 주거나 서버에 보내는 데이터를 담기 위한 용도로 이런 의미 없는 요소들이 사용되는데, 이런 의미 없는 태그의 사용 빈도는 매우 높다.
*  html은 문설르 웹에 나타내기 위해 제작이 되었기 때문에 태그들이 문서에 최적화된 의미를 담고 있는데 최근에 웹이 문서 형태를 많이 벗어났기 때문이다.
* html 버전이 업그레이드 되면서 웹에 알맞은 태그들이 많이 생겼다.

**```<div>```태그와 ```<span>```태그**
* div(division) 태그는 블록 레벨 태그이다.
 * 블록 레벨 요소는 기본적으로 한 줄을 생성해서 내용을 표현한다
 * ex) ```<p>``` 태그
* span 태그는 인라인 레벨 태그이다.
 * 인라인 레벨 요소들은 블록 레벨 요소의 한 줄 안에서 표현되는 요소들이다.
 * ex) 텍스트를 꾸며주는 ```<b>```, ```<i>```, ```<u>```, ```<s>```는 모두 인라인 레벨 태그
* ```<div>```, ```<span>```는 모두 아무 의미가 없으므로 실제 브라우저도 별다른 스타일을 적용하지 않는다.

```html
<div>
  <span>Lorem</span> ipsum dolor sit.
</div>
```

## 2.6 리스트 요소
* 리스트는 일련된 항목들이 나열된 것들을 의미한다.
* 콘텐츠가 많은 포털이나 검색 엔진같은 사이트에는 분야나 항목으로 구분할 것이 많으므로 리스트가 자주 사용된다.

**```<ul>```**
* ul(unordered list) 태그는 순서가 없는 리스트를 표현할 때 사용한다.
* ```<ul>```을 선언한 후 그 안에서 ```<li>```를 사용해 각 항목을 나타내서 사용한다.

```html
<ul> 
  <li> 콩나물</li> 
  <li> 파</li> 
  <li> 국  간장</li> 
  ... 
</ul> 
```

**```<ol>```**
* ol(ordered list) 태그는 순서가 있는 리스트를 표현할 때 사용한다.
 * 순서가 있는 리스트이기 때문에 화면에 숫자로 표현됨
* ```<ol>```을 선언한 후 그 안에서 ```<li>```를 사용해 각 항목을 나타내서 사용한다.

```html
<ol>
  <li>냄비에 국물용 멸치를 넣고 한소끔 끓여 멸치 육수를 7컵(1,400ml) 만든다.</li>
  <li>콩나물을 넣고 뚜껑을 덮어 콩나물이 익을 때까지 끓인다.</li>
  <li>뚜껑을 열고 대파, 마늘, 고춧가루를 넣고 끓인다.</li>
  ...
</ol>
```


**```<dl>```**
* dl(definition/description list) 태그는 용어와 그에 대한 정의를 표현할 때 사용한다.
* ```<ul>```, ```<ol>```은 항목을 단순히 나열하는 구조지만, ```<dl>```은 용어와 설명이 하나의 세트로 항목을 이루고 하나 이상의 항목으로 리스트가 이루어지는 구조이다.
* ```<dt>``` : 용어를 나타내는 태그
* ```<dd>``` : 용어에 대한 정의 또는 설명을 나타내는 태그
* 용어 하나에 여러 정의가 들어갈 때, ```<dd>```를 한 개 이상 쓰는 것이 가능하다.

```html
<dl>
  <dt>리플리 증후군</dt>
  <dd>허구의 세계를 진실이라 믿고 거짓된 말과 행동을 상습적으로 반복하는 반사회적 성격장애를 뜻하는 용어</dd>
  <dd>용어 하나에 여러 개의 정의가 들어갈 수 있다. 이런식으로.</dd>
  <dt>피그말리온 효과</dt>
  <dd>타인의 기대나 관심으로 인하여 능률이 오르거나 결과가 좋아지는 현상</dd>
  <dt>언더독 효과</dt>
  <dd>사람들이 약자라고 믿는 주체를 응원하게 되는 현상</dd>
</dl>
```

**리스트의 중첩**
* ```<ol>```태그의 자식으로는 ```<li>``` 태그만 올 수가 있는데 반대로 ```<li>```태그는 ```<ol>```태그 또는 ```<ul>```태그만을 부모로 가질 수가 있다.
 * ```<ol>``` 태그는 ```<div>```, ```<p>``` 같은 태그는 자식요소로 가질 수 없다.
* ```<li>``` 태그는 자식으로 ```<div>```, ```<p>``` 같은 다른 요소들이 들어올 수 있다.
* 중첩을 할 때는 ```<li>``` 태그 안에 요소들을 삽입해야 된다.

```html
<h1>월드컵 조 편성</h1>
<!-- <ol> 태그가 부모 태그 -->
<ol>
  <li>
    A조
    <ul>
      <li>러시아</li>
      <li>우루과이</li>
      <li>이집트</li>
      <li>사우디아라비아</li>
    </ul>
  </li>
  <li>
    B조
    <ul>
      <li>이란</li>
      <li>스페인</li>
      <li>포르투갈</li>
      <li>모로코</li>
    </ul>
  </li>
  <li>
    C조
    <ul>
      <li>프랑스</li>
      <li>덴마크</li>
      <li>호주</li>
      <li>페루</li>
    </ul>
  </li>
  <li>
    D조
    <ul>
      <li>크로아티아</li>
      <li>아르헨티나</li>
      <li>아이슬란드</li>
      <li>나이지리아</li>
    </ul>
  </li>
</ol>
```

### 읽어보기
* [```<ul>```: The Unordered List element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
* [```<ol>```: The Ordered List element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
* [```<dl>```: The Description List element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl)

## 2.7 이미지 요소
* ```<img>```는 문서에 이미지를 삽입하는 태그로, 닫는 태그가 없는 빈 태그이다.
* src 속성: <img>의 필수 속성으로 이미지의 경로를 나타내는 속성이다
* alt 속성: 이미지의 대체 텍스트를 나타내는 속성이다. 대체 텍스트는 이미지를 대체하는 글을 뜻하며, 웹 접근성 측면에서 중요한 속성이다.
* width, height 속성: 이미지의 가로/세로 크기를 나타내는 속성이다.
  * 값의 단위는 필요하지 않으며, 값을 입력하면 자동으로 픽셀 단위로 계산된다.
  * width/height는 선택적인 속성이지만 이미지의 크기가 고정적이라면 width/height 속성을 선언하는 것이 성능적인 측면에서 좋다.
  * 둘 중 하나만 선언하면 나머지 한 속성은 선언한 속성의 크기에 맞춰 자동으로 비율에 맞게 변경된다.
  * 두 속성 모두 선언하면 이미지는 비율과 무관하게 선언한 크기대로 변경된다.

**상대경로와 절대경로**
* src 속성에 들어가는 이미지의 경로에는 상대경로와 절대경로가 있다.
* 상대경로는 현재 웹 페이지를 기준으로 상대적으로 이미지의 위치를 나타내는 경로이다.
  * 상대 경로에서의 './'는 페이지가 있는 현재 폴더를 나타낸다.
* 절대경로는 실제 그 이미지가 위치한 곳의 전체 경로이다.

```html
<!-- 상대경로 -->
<img src="./images/pizza.png" alt="피자">

<!-- 절대경로 -->
<img src="C:/users/document/images/pizza.png" alt="피자">
<img src="http://www.naver.com/pizza.png" alt="피자">
```

**이미지 파일 형식**
* gif : 제한적인 색을 사용하고 용량이 적으며 투명 이미지와 애니메이션 이미지를 지원하는 형식
* jpg : 사진이나 일반적인 그림에 쓰이며 높은 압축률과 자연스러운 색상 표현을 지원하는 형식(투명을 지원하지 않는다.)
* png : 이미지 손실이 적으며 투명과 반투명을 모두 지원하는 형식

## 2.8 테이블 요소 1

**표의 구성 요소**
* 표는 셀(내용이 들어가는 하나의 칸)로 이루어져 있다.
* 표의 행(가로 방향)을 row, 열(세로 방향)을 column이라 한다.
* ```<table>``` : 데이터 표를 나타내는 태그
* ```<tr>``` : 행을 나타내는 태그
* ```<th>``` : 제목 셀을 나타내는 태그
* ```<td>``` : 셀을 나타내는 태그
* 하나의 ```<table>```은 하나 이상의 ```<tr>```로 이루어져 있으며, ```<tr>```은 셀을 나타내는 ```<th>```, ```<td>```를 자식으로 가지게 된다.

**표의 구조와 관련된 태그**
* 표가 복잡해지면 표를 해석해서 음성으로 전달해야 하는 스크린 리더기와 같은 보조 기기를 통해서는 표의 내용을 이해하는 것이 더욱 어려워진다. 따라서, 표를 구조적으로 파악하기 위해 도움이 되는 태그를 사용해야 한다.
* ```<caption>```: 표의 제목을 나타내는 태그
* ```<thead>```: 제목 행을 그룹화하는 태그
* ```<tfoot>```: 바닥 행을 그룹화하는 태그
* ```<tbody>```: 본문 행을 그룹화하는 태그

```html
<table>
  <caption>Monthly Savings</caption>
  <thead>
      <tr>
          <th>Month</th>
          <th>Savings</th>
      </tr>
  </thead>
  <tbody>
      <tr>
          <td>January</td>
          <td>$100</td>
      </tr>
      <tr>
          <td>February</td>
          <td>$80</td>
      </tr>
  </tbody>
  <tfoot>
      <tr>
          <td>Sum</td>
          <td>$180</td>
      </tr>
  </tfoot>
</table>
```

**테이블 관련 속성**
* colspan: 셀을 가로방향으로 병합
* rowspan: 셀을 세로방향으로 병합

### 알아두기
* HTML4: ```<tfoot>``` 위치가 ```<tbody>``` 전에 위치한다. 데이터의 양이(```<tbody>```) 잠재적으로 매우 클수도 있기 때문에 그 전에 ```<tfoot>```을 렌더해야 했기 때문
* HTML5:  ```<tfoot>```의 위치가 ```<tbody>``` 앞에 와도 되고, 뒤에 와도 상관없음.
* HTML5.1 ~ 현재(5.2): ```<tfoot>```이 ```<tbody>``` 뒤에 위치해야 함. ```<tfoot>```의 위치가 ```<tbody>``` 앞에 나올 경우 웹 접근성의 키보드의 초점 이동 순서 항목에 문제가 있기 때문에 변경됨.

## 2.9 테이블 요소 2
**복잡한 표 만들기**
```html
<table>
  <caption>Specification values</caption>
  <thead>
    <tr>
      <th rowspan="2">Grade.</th>
      <th rowspan="2">Point.</th>
      <th colspan="2">Strength.</th>
      <th rowspan="2">Percent.</th>
    </tr>
    <tr>
      <th>kg/mm</th>
      <th>lb/in</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Hard</td>
      <td>0.45</td>
      <td>56.2</td>
      <td>80,000</td>
      <td>20</td>
    </tr>
    <tr>
      <td>Medium</td>
      <td>0.45</td>
      <td>49.2</td>
      <td>70,000</td>
      <td>25</td>
    </tr>
    <tr>
      <td>Soft</td>
      <td>0.45</td>
      <td>42.2</td>
      <td>60,000</td>
      <td>30</td>
    </tr>
  </tbody>
</table>
```

**기타 테이블 관련 속성**
* ```<colgroup>```: 테이블에서 서식 지정을 위해 하나 이상의 열을 그룹으로 묶을 때 사용
* ```<col>```: ```<colgroup>``` 요소에 속하는 각 열(column)의 속성을 정의할 때 사용
* scope 속성: 해당 헤더 셀이 관련되는 셀의 종류를 명시.일반 웹 브라우저에서는 ```<th>``` 요소에 scope 속성을 명시해도 아무런 시각적 효과도 나타나지 않지만, 스크린 리더기와 같은 장치에서는 유용하게 사용될 수 있다.
* headers 속성: 해당 데이터 셀과 연관된 하나 이상의 헤더 셀(header cell)을 명시. 일반 웹 브라우저에서는 ```<td>``` 요소에 headers 속성을 명시해도 시각적으로 어떠한 효과도 보여주지 않지만, 스크린 리더기와 같은 장치에서는 유용하게 사용될 수 있다.

### 읽어보기
* [```<table>```: The Table element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)

## 2.10 폼 요소 1
* 폼 관련 요소(FORM): 서버에 데이터를 전달하기 위한 요소들.
 * ex) 대표적인 폼 요소 ```<input>```
* ```<input>```은 내용이 없는 빈 요소이며 type 속성을 통해 여러 종류의 입력 양식으로 나타나게 된다.

**input 요소들**
* type="text"
 * 주로 아이디, 이름, 주소, 전화번호 등 단순한 텍스트를 입력할 때 사용
 * type="text"의 placeholder 속성은 사용자가 입력하기 전 미리 화면에 노출하는 값으로, 입력하는 값의 양식을 표현할 수 있다.
```html
<input type="text" placeholder="사용자가 입력하기 전 미리 화면에 노출하는 값">
```
* type="password"
 * 암호와 같이 공개할 수 없는 내용을 입력할 때 사용
 * 화면에는 type="text"와 같게 나타나지만 실제로 입력할 때 값을 노출하지 않는다.
```html
<input type="password">
```
* type="radio"
 * 라디오 버튼을 만들 때 사용
 * 라디오 버튼은 중복 선택이 불가능하며 하나의 항목만을 선택해야 한다.
 * (fun)옛날 자동차의 라디오 버튼처럼 생겼다고 해서 라디오 버튼이라고 부른다고 함.
 * name 속성으로 같은 성격의 라디오 버튼임을 명시해줘야 한다.
```html
<input type="radio" name="gender"> 남자
<input type="radio" name="gender"> 여자
```
* type="checkbox"
 * 체크박스를 만들 때 사용
 * 체크박스는 중복 선택이 가능하다.
```html
<input type="checkbox" name="hobby"> 등산
<input type="checkbox" name="hobby"> 독서
<input type="checkbox" name="hobby"> 운동
```
* 라디오 버튼과 체크박스에는 checked, name 속성이 존재한다.
  * checked 속성은 값이 별도로 존재하지 않는 boolean 속성이다.
  * boolean 속성은 true/false 둘 중 하나의 값을 가지며 속성이 존재하면 true, 속성이 존재하지 않으면 false를 가진다.
  * name 속성은 라디오 버튼과 체크박스를 그룹화시켜주는 속성이다.

## 2.11 폼 요소 2
**input 요소들2**
* type="file"
 * 파일을 서버에 올릴 때 사용
 * 브라우저에 따라 표현되는 형태는 조금씩 다르지만, 모두 같은 역할을 함.
```html
<input type="file">
```
* type="submit|reset|image|button"
 * submit, reset, image, button 타입은 모두 클릭 가능한 버튼을 만든다.
  * submit : form의 값을 전송하는 버튼
  * reset : form의 값을 초기화하는 버튼
  * image : 이미지를 삽입할 수 있는 버튼 (submit과 동작이 동일함)
  * button : 아무 기능이 없는 버튼
```html
<!-- 실제로는 없는 페이지(./test.html) 임시로 넣었기 때문에 submit 버튼 누르면 파일 찾을 수 없다는 에러 뜸 -->
<form action="./test.html">
  메시지: <input type="text" name="message"><br>
  <input type="submit">
  <!-- reset 버튼 누르면 폼 초기화 -->
  <input type="reset">
  <!-- 이미지 버튼은 이미지 관련 속성인 src, alt 속성이 반드시 필요하며 width/height 속성을 적용할 수도 있다. -->
  <input type="image" src="http://placehold.it/50x50?text=click" alt="click" width="50" height="50">
  <!-- button 타입은 개발자가 직접 커스텀해서 기능 추가해줄 때 사용 -->
  <input type="button" value="버튼">
</form>
```

### 읽어보기
* [HTML elements reference: Form](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#forms)

## 2.12 폼 요소 3
**select**
* ```<select>```는 선택 목록 상자 또는 콤보박스라고도 한다.
* 몇 개의 선택지를 리스트 형태로 노출하고 그중 하나를 선택할 수 있게 하는 태그이다.
 * multiple 속성을 사용하면 다중 선택도 가능
* ```<select>```내부의 ```<option>```으로 각 항목을 나타낸다
* ```<option>```의 속성으로는 selected가 있으며 이는 선택된 항목을 의미한다.
```html
<select>
  <option>서울</option>
  <option>경기</option>
  <option>강원</option>
  <option>제주</option>
</select>
```

**textarea**
* 한 줄만을 입력할 수 있는 ```<input type="text">```와 달리 여러 줄의 텍스트를 입력할 때 사용한다.
* ```<textarea>```에는 텍스트 상자의 크기를 조절하는 rows, cols 속성이 있다.
 * cols : 가로 크기를 조절하는 속성(한 줄에 들어가는 글자의 수, 수치의 의미는 평균적인 글자의 너비로 정확히 글자 수를 나타내지는 않는다.)
 * rows : 세로 크기를 조절하는 속성(화면에 보여지는 줄 수)
```html
<textarea rows="5" cols="30" placeholder="자기소개는 짧게 해주세요"></textarea>
```

**button**
* 사용자가 클릭 가능한 버튼을 만들 때 사용하며 submit, reset, button 3가지의 타입이 있다.
* 각 버튼은 이전에 배웠던 input 타입의 submit, reset, button과 모두 같은 기능을 가진 버튼이다.
* 다만, 빈 태그가 아니며 내용을 안에 직접 넣을 수 있으므로 좀 더 자유로운 스타일 표현이 가능하다.
```html
<button type="submit|reset|button">
  <img src="./test_icon.png" alt="자유로운 스타일 표현 가능">
  빈 태그가 아니라 내용을 안에 직접 넣을 수 있다
</button>
```

## 2.13 폼 요소 4
**label**
* <label>은 form 요소의 이름과 form 요소를 명시적으로 연결시켜주기 위해 사용한다
* 모든 form 요소에 사용할 수 있다.
* form 요소의 id 속성값과 <label>의 for 속성값을 같게 적어주어야 한다.
* <label>을 사용하면 이를 클릭했을 경우 해당 form 요소를 클릭한 것처럼 동작한다.
* 스크린 리더기를 통해 듣게 되면 해당 form 요소에 접근 시 <label>을 함께 읽어주게 된다.
* <label>은 사용성, 접근성적인 측면으로 중요한 역할을 하므로 반드시 써주는 것이 좋다.(필수적)
```html
<label for="name">이름</label>: <input type="text" id="name"><br>
<label for="nickname">닉네임</label>: <input type="text" id="nickname"><br>
<label for="address">주소</label>: <input type="text" id="address"><br>
```

**fieldset, legend**
* ```<fieldset>```, ```<legend>```는 form 요소를 구조화 하기 위해 필요한 태그이다
* ```<fieldset>``` : 여러 개의 폼 요소를 그룹화하여 구조적으로 만들기 위해 사용
* ```<legend>``` : 폼 요소의 제목으로 ```<fieldset>``` 내부에 작성
* ```<fieldset>```은 보통 form의 성격에 따라 구분합니다.
* ```<legend>```는 ```<fieldset>```의 자식으로 반드시 최상단에 위치해야 합니다.

```html
<fieldset>
  <legend>필수 정보</legend>
  <label for="name">아이디</label>: <input type="text" id="id"><br>
  <label for="userpwd">비밀번호</label>: <input type="password" id="userpwd"><br>
</fieldset>
<fieldset>
  <legend>부가 정보</legend>
  <label for="nickname">닉네임</label>: <input type="text" id="nickname"><br>
  <label for="address">주소</label>: <input type="text" id="address"><br>
</fieldset>
```

**form**
* ```<form>```은 form 요소들을 감싸는 태그로 데이터를 묶어서 실제 서버로 전송해주는 역할을 하는 태그이다.
* 만약 ```<fieldset>```으로 구조화되어있다면 ```<fieldset>```도 함께 감싸는 역할을 한다.
```html
<form action="" method="">
  <fieldset>
    <legend>필수 정보</legend>
    <label for="name">아이디</label>: <input type="text" id="id"><br>
    <label for="userpwd">비밀번호</label>: <input type="password" id="userpwd"><br>
  </fieldset>
  <fieldset>
    <legend>부가 정보</legend>
    <label for="nickname">닉네임</label>: <input type="text" id="nickname"><br>
    <label for="address">주소</label>: <input type="text" id="address"><br>
  </fieldset>
</form>
```
* ```<form>```에는 대표적인 2가지 속성이 있다.
* action: 데이터를 처리하기 위한 서버의 주소
* method: 데이터를 전송하는 방식을 지정
 * method 속성값에는 get/post 2가지 방식이 존재한다.
 * get 방식은 데이터가 전송될 때 주소창에 파라미터 형태로 붙어 데이터가 노출된다.
  * 민감한 정보를 다룰 때는 쓰면 안 된다.
 * 반면, post 방식은 데이터가 전송될 때 데이터가 노출되지 않는다.
  * 민감한 정보를 다룰 때는 post 방식을 사용해야 함
