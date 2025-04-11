# 목차
 1. [JavaScript의 등장](#javascript의-등장)  
    1-1.[Web 1.0 구성 요소](#web-10-구성-요소)
 2. [HTML 특성](#html-특성)  
    2-1. [HTML의 텍스트 태그들](#html의-텍스트-태그들)  
    2-2. [HTML의 레이아웃 Semantic 태그](#html의-레이아웃-semantic-태그)  
    2-3. [HTML의 이미지, 멀티미디어](#html의-이미지-멀티미디어)  
    2-4. [HTML의 table 태그](#html의-table-태그)  
    2-5. [HTML의 form 태그](#html의-form-태그)  
 3. [CSS 특성](#css-특성)  
    3-1. [웹 문서에 Style 적용 3가지 방법](#웹-문서에-style-적용-3가지-방법)  
    3-2. [CSS 활용해보기](#css-활용해보기)  
    3-3. [반응형 웹 컨텐츠](#반응형-웹-컨텐츠)  
    3-4. [Bootstrap](#bootstrap)
 4. [JavaScript 특성](#javascript-특성)  
    4-1. [JavaScript를 HTML 문서에 적용하는 3가지 방법](#javascript를-html-문서에-적용하는-3가지-방법)
 5. [JavaScript 기본 : 입/출력](#javascript-기본--입출력)
 6. [JavaScript 기본 : 데이터 타입](#javascript-기본--데이터-타입)  
    6-1. [심볼(Symbol) 타입](#심볼symbol-타입)
 7. [JavaScript 기본 : 변수](#javascript-기본--변수)  
    7-1. [변수명 작성 규칙](#변수명-작성-규칙)  
    7-2. [호이스팅(Hositing)](#호이스팅hositing)
 8. [JavaScript 기본 : 연산자](#javascript-기본--연산자)
 9. [JavaScript 기본 : 제어문 / 반복문](#javascript-기본--제어문--반복문)
 10. [JavaScript 기본 : 구조 분해 할당](#javascript-기본--구조-분해-할당)
 11. [JavaScript 기본 : 배열](#javascript-기본--배열)
 12. [JavaScript 기본 : 함수](#javascript-기본--함수)  
    12-1. [Closure 함수](#closure-함수)  
    12-2. [함수 내부에서의 this](#함수-내부에서의-this)
 13. [JavaScript 객체](#javascript-객체)  
    13-1. [JavaScript의 AccessModifier](#javascript의-accessmodifier)  
    13-2. [Map 과 Set 자료구조](#map-과-set-자료구조)  
    13-3. [모듈(export/import)](#모듈exportimport)
 14. [JavaScript 내장 객체](#javascript-내장-객체)  
    14-1. [JSON의 내장 객체 stringify(직렬화)/parse(역직렬화) (+브라우저 storage/DOM API)](#json의-내장-객체-stringify직렬화parse역직렬화-브라우저-storagedom-api)
 15. [JavaScript 이벤트 제어](#javascript-이벤트-제어)  
    15-1. [load 이벤트](#load-이벤트)
 16. [JavaScript 브라우저 객체 모델(BOM, Browser Object Model) API](#javascript-브라우저-객체-모델bom-browser-object-model-api)
 17. [JavaScript HTML 객체 모델(DOM, Document Object Model) API](#javascript-html-객체-모델dom-document-object-model-api)
 18. [JavaScript 예외처리](#javascript-예외처리)
 19. [Ajax(Asynchronous JavaScript And XML)](#ajaxasynchronous-javascript-and-xml)
 20. [Promise, async/await](#promise-asyncawait)  
    20-1. [Fetch API](#fetch-api)
 21. [기타 - Node.js에서 JavaScript 실행 하기](#기타---nodejs에서-javascript-실행-하기)
 22. [cors (cross origin resource sharing) : 웹의 기본 보안 정책](#cors-cross-origin-resource-sharing--웹의-기본-보안-정책)
 23. [기타 - 참고 사이트](#기타---참고-사이트)
 24. [기타 - 개발 TOOL](#기타---개발-tool)


## JavaScript의 등장
 - 1990년에 인터넷이 등장하였다.
 - 초기(web 1.0)에는 웹 브라우저의 형태는 HTML만 사용되었으며, 아래와 같은 특징이 있다.
    - 정적인 페이지만 서비스할 수 있다.
        - 만들어진 페이지만 제공한다.
    - 사용자를 구분하지 않고, 동일한 서비스를 제공한다.
    - view만 제공한다.
    - 동기방식의 요청을 처리한다.(=전체 페이지 갱신 방식)
        - 페이지가 일부만 바뀌더라도 전체 페이지를 파싱하고 랜더링 한다.
    - Client ↔ Server 구조의 C/S 형태였다.
    - html이 문법적으로 느슨했다.
        - 문서 구조 정의 뿐만이 아닌 CSS관련 내용도 다루었다.
        - 태그를 닫지 않아도 정상적으로 문법이 동작한다든지 등등
    - 이벤트 처리에는 liveScript를 사용했다.
        - JavaScript는 liveScript를 규격화한 언어라고 봐도 된다.
 - 위와 같이 웹 브라우저를 사용하였으나, 이 이후 JAVA가 등장하였다.
    - JAVA는 브라우저에서 정적인 화면이 아닌 프로그램을 구동할 수 있었다.
        - JAVA의 등장으로 인해 웹 브라우저의 가능성이 넓어지는 계기가 된다.
    - 하지만, JAVA는 JVM 위에서 구동되기 때문에 웹 브라우저에 소형 JVM이 포함되어 있어야 했다.
 - JAVA를 통해 ECMAScript 단체에서 liveScript를 규격화하여 JavaScript를 만들었다.
    - 이 때, W3C 웹 표준 단체에서 웹 브라우저에 대해 영역을 재정의하였다.
        - HTML은 구조만 담당
            - 느슨했던 HTML을 XHTML1.0 으로 재탄생시키면서 구조를 엄격하게 하였다.
            - 하지만 모바일 시장 및 여러 회사들의 반발로 인해 구조를 XHTML보다는 느슨하게, 여러 기능을 활용할 수 있도록 API를 확대시킨 HTML5도 탄생하였다.
        - CSS 표현을 담당
        - JavaScript(ECMAScript)는 동작, 구조의 동적 변경을 담당
 - 2000년 초반부터 웹에 멀티미디어가 포함되었고, 사용자 참여가 증가하였다.
    - Active X, Direct X, 어도비 플래시 등등 의 프로그램들..
 - 이 시기에 Google과 Ajax가 등장하였다.
    - Ajax는 웹 브라우저에서 서버에 요청을 보내도 전체 페이지를 새로 로딩하는 것이 아닌, 실시간으로 스크롤하며 새로운 데이터가 갱신되는 것을 볼 수 있었다.
    - Ajax는 JavaScript의 객체 구조로 프로그램을 구성하였으며, 비동기 방식으로 데이터를 처리하였다.
    - 이는 Web2.0 시대를 열었다.
        - 비동기 요청 + 부분 페이지 갱신 방식
 - 2007 ~ 2008년도에는 모바일 시장의 확대 및 BigData의 등장이 되면서 웹 브라우저에 대한 추가적인 기능 확대가 필요하여, HTML5를 탄생시키게 되었다.
    - 이에 대응하기 위해 JavaScript(ECMAScript) 또한 더욱 발전하게 되었다.
 - 2009년도에는 Node.js가 등장하면서 JavaScript가 웹 브라우저 외의 환경에서도 동작할 수 있게 되었다.
    - 이로 인해 JavaScript의 중요성은 더욱 확대가 되었다.

### Web 1.0 구성 요소
 1. HTML 파서
    - 내용을 객체로 생성 → tree 구조로 메모리에 구성
        - html 하위에 head/body 각 하위에 등등...
 2. Renderer
    - CSS의 스타일을 html에 적용.


## HTML 특성
 - html은 Browser에서 실행되는 문서의 View의 구조를 정의한다.
 - html 태그명은 대소문자를 구별하지 않는다.
 - html 최상위 태그는 하나이다. (root 태그(=root 엘리먼트))
    ```plaintext
    <html> |----<head> |--- <meta><link>, <style><script>, <title>...
           |----<body>
                  |--- 텍스트 태그 <p><ul><ol>...
                  |--- 레이아웃 태그 <div><span>, <header>,<footer>, <nav>, <aside>, <article>, <section>...
                  |--- 멀티미디어 태그 <img /> <canvas><audio><video>...
                  |--- 테이블 태그 <table><td><tr>...
                  |--- Form 태그 <form>, <input>, <textarea>, <select>, <datalist>...
    
    ※ 모든 태그의 공통 속성 : id, class, name, style..
    ```
    ```html
    <!DOCTYPE html>
     <!-- !는 문서 유형 선언으로 브라우저의 파서가 문서를 어떤 버전으로 파싱할지 결정한다. -->
    <html lang="en">
     <!-- html은 문서 유형에 따른 루트 태그(=루트 엘리먼트)이다. -->
     <!-- lang은 루트 태그의 속성이라 옵션으로 선택적으로 작성 가능하다. -->
    <head>
     <!-- HTML 문서의 메타데이터와 헤더 정보를 정의하는 부분 -->
        <meta charset="UTF-8">
         <!-- 웹 표준 인코딩 방식을 지정한다. -->
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
         <!-- viewport는 반응형 웹 컨텐츠와 관련된 설정 (사이즈 등등) -->
        <title>Document</title>
         <!-- 웹 페이지의 제목 -->
    </head>
    <body>
     <!-- 페이지를 통해 전달하고자 하는 모든 정보가 작성된다. -->
    </body>
    ```

### HTML의 텍스트 태그들
```html
<body>
    <!-- <h1>~<h6> 태그 : 제목을 표현하기 위해 사용 -->
    <h1>제목1</h1>
    <h2>제목2</h2>
    <h3>제목3</h3>
    <h4>제목4</h4>
    <h5>제목5</h5>  
    <h6>제목6</h6>

    <!-- block 태그 : 줄바꿈을 하는 태그
         inline 태그 : 줄바꿈을 하지 않는 태그 -->
    
    <!-- p 태그
         - 단락 태그이다.
         - 단락 태그 내에서는 줄바꿈이 되지 않는다.
         - 줄바꿈을 위해서는 br 태그가 사용되어야 한다.
         - i, b, strong 같은 태그들로 텍스트에 간단한 스타일을 적용할 수 있다. -->
    <p> h1 태그의 내용 텍스트는 <i>32px, 24pt</i> 이다. <br>
        h2 태그의 내용 텍스트는 <b>24px, 18pt</b> 이다.
        h3 태그의 내용 텍스트는 <strong>18px, 14pt</strong> 이다.
        h4 태그의 내용 텍스트는 16px, 12pt 이다.
        h5 태그의 내용 텍스트는 13px, 10pt 이다.
        h6 태그의 내용 텍스트는 10px, 8pt 이다.
    </p>

    <!-- ul 태그(unordered list) : 순서를 나타내지 않는 리스트 -->
    <!-- li 태그(list) : 목록을 만드는 태그 -->
    <p>
        <ul>
            <li>h1 태그의 내용 텍스트는 32px, 24pt 이다.</li>
            <li>h2 태그의 내용 텍스트는 24px, 18pt 이다.</li>
            <li>h3 태그의 내용 텍스트는 18px, 14pt 이다.</li>
            <li>h4 태그의 내용 텍스트는 16px, 12pt 이다.</li>
            <li>h5 태그의 내용 텍스트는 13px, 10pt 이다.</li>
            <li>h6 태그의 내용 텍스트는 10px, 8pt 이다.</li>
        </ul>
    </p>

    <!-- ol 태그(ordered list) : 순서를 나타내는 리스트 -->
    <p>
        <ol>
            <li>h1 태그의 내용 텍스트는 32px, 24pt 이다.</li>
            <li>h2 태그의 내용 텍스트는 24px, 18pt 이다.</li>
            <li>h3 태그의 내용 텍스트는 18px, 14pt 이다.</li>
            <li>h4 태그의 내용 텍스트는 16px, 12pt 이다.</li>
            <li>h5 태그의 내용 텍스트는 13px, 10pt 이다.</li>
            <li>h6 태그의 내용 텍스트는 10px, 8pt 이다.</li>
        </ol>
    </p>

    <!-- dl 태그 : description list를 정의할 때 사용.
         dt 태그 : description list 중에 term.name을 나타낼 때 사용.
         dd 태그 : description list 중에 term.name의 description을 정의할 때 사용. -->
    
    <!-- a 태그 : 하이퍼링크를 나타낼 때 사용한다. -->
    <a href="https://www.google.co.kr" target="_blank">구글</a>
</body>
```

### HTML의 레이아웃 Semantic 태그
 - 인터넷의 발전으로 방대한 양의 웹문서가 생기면서, 제각기 일관적이지 않게 생성된 문서 구조로 우리는 웹에서 원하는 정보를 찾을 때 점점 어려움을 겪게 되었다.
 - 시맨틱 태그 (Semantic Tag)는 포함된 콘텐츠의 특정 의미를 정의하고 목적을 갖는 태그이다.
 - 시맨틱 태그는 HTML의 구조를 설계하는데 있어 태그에 의미를 부여함으로써 웹사이트의 구조를 파악하기 쉽도록 도와주기 위해 만들어진 것다.
 - 신문지에서 각 카테고리 별로 영역이 나뉘어 작성되는 것과 같은 예시이다.
 - html5는 Semantic 태그를 활용하여 작성하도록 권장하고 있다.
![Non-Semantic vs Semantic](https://cwh-full-next-space.fra1.cdn.digitaloceanspaces.com/tutorial/html-semantic-tags/semantic-tags.png)
    ```html
    <body>
        <!-- 
        <header> : 머릿글 영역. 보통 페이지나 콘텐츠의 메조그 로고, 메뉴 등..
            <nav> : 네비게이션 링크 묶음. 다른 페이지나 섹션으로 이동할 수 있게 해줌.
        <article> : 독립적인 글/콘텐츠 단위
            <aside> : 보조 컨텐츠. 메인 콘텐츠와는 직접적인 관련은 없지만 유용한 정보(광고 등)
        <section> : 논리적인 구역 (유사한 article을 그룹핑)
        <footer> : 작성자 정보, 저작권, 연락처, 하단 메뉴 등 포함
        -->
    </body>
    ```

### HTML의 이미지, 멀티미디어
```html
<body>
    <img src="https://cwh-full-next-space.fra1.cdn.digitaloceanspaces.com/tutorial/html-semantic-tags/semantic-tags.png" alt="이미지를 띄울 수 없을 때, 대체 텍스트 입니다.">
    <!-- canvas는 하얀색 도화지를 제공한다. 도화지에서 그래픽 처리할 때는 JS 혹은 별도 라이브러리를 사용해야한다. -->
    <canvas></canvas>
    <!-- 오디오 혹은 비디오를 사용하기 위해서는 어도비 플래시 같은 프로그램이 필요했으나,
         html5부터는 웹 브라우저에서 기본 제공할 수 있도록 구성되었다. -->
    <audio src=""></audio>
    <video src=""></video>
</body>
```

### HTML의 table 태그
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>테이블</title>
    <style>
        table, th, tr, td {
            border: solid 1px black;
            border-collapse: collapse;
            padding: 8px;
        }
        td {
            width: 100px;
            text-align: center;
        }
    </style>
</head>
<body>
    <!-- table 태그는 표형식의 이미지, 데이터를 문서로 보여줄 때 사용한다.
         행 별로 열 개수를 다르게 구성할 수 있다.
         colspan 속성을 활용하면 빈 열에 대해서 셀 병합을 할 수 있다.
         rowspan 속성을 활용하면 빈 행에 대해서 셀 병합을 할 수 있다. -->
    <table>
        <tr>
            <th>이름</th>
            <th>국어</th>
            <th>영어</th>
            <th>수학</th>
            <th>프로그래밍</th>
        </tr>
        <tr>
            <td>일번</td>
            <td>10점</td>
            <td>11점</td>
            <td>12점</td>
            <td>13점</td>
        </tr>
        <tr>
            <td rowspan="2">이번</td>
            <td>20점</td>
            <td>21점</td>
            <td>22점</td>
            <td>23점</td>
        </tr>
        <tr>
            <td>30점</td>
            <td colspan="2">31점</td>
            <td>33점</td>
        </tr>
    </table>
</body>
```

### HTML의 form 태그
 - 브라우저에서 실행되는 html에서는 사용자로부터 입력을 받으려면 2가지 방빕이 있다.
    1. form 태그 내에 input, textarea, select 등을 활용.
    2. JavaScript에서 입력받는 함수를 활용.
```html
<body>
    <!-- method 속성을 통해 BackEnd에 get/post 등의 요청을 보낼 수 있다. (REST 통신) -->
    <form action="data.jsp" method="get">
        <input type="button" value="누르시오" onclick=""> <br>
        <input type="checkbox" checked>등산
            <input type="checkbox">러닝
            <input type="checkbox">테니스
            <input type="checkbox">수영 <br>
        <input type="color"> <br>
        <input type="date"> <br>
        <input type="datetime-local"> <br>
        <input type="email"> <br>
        <input type="file"> <br>
        <input type="hidden"> <br>
        <input type="image"> <br>
        <input type="month"> <br>
        <input type="number" min="-1" max="10" step="2" required> <br>
        <input type="password"> <br>
        <input type="radio"> <br>
        <input type="range"> <br>
        <input type="search"> <br>
        <input type="tel" pattern="\d{3}-\d{4}-\d{4}"> <br>
        <input type="text" placeholder="textbox 입니다" focus> <br>
        <input type="time"> <br>
        <input type="url"> <br>
        <input type="week"> <br>
        <textarea rows="5" cols="50"></textarea> <br>
        <!-- progress는 진행률을 표기 -->
        <progress min="0" max="10"></progress> <br>
        <select>
            <option value="경기도">경기도</option>
            <option value="서울">서울</option>
            <option value="제주">제주</option>
            <option value="부산">부산</option>
        </select> <br>

        <input list="browsers" name="browser" id="browser">
        <datalist id="browsers">
            <option value="Edge">
            <option value="Firefox">
            <option value="Chrome">
            <option value="Opera">
            <option value="Safari">
        </datalist> <br>

        <!-- 위 각 input에 대해 유효하지 않은 값들을 넣고 submit을 해보면 브라우저에서 오류 메세지가 나온다. -->
        <input type="submit"> <input type="reset"> <br>
    </form>
</body>
```


## CSS 특성
```plaintext
selector {
    property : value1 value2;
    property2 : value3;
    ...
}

selector에는 작성 가능한 방법
 태그명, #id속성값, .class속성값, *, 부모 > 자식, 부모 자손,
 [속성명], [속성=값], [속성*=값], [속성|=값], [속성^=값], [속성$=값],
 :check, :focus, ::가상selector 등등...

CSS의 Property 값을 선언할 때 size 관련된 값은 단위를 함께 선언해야 한다.
 - 크기(size, width, height 등) 단위 : px, cm, mm, in, pt, pc, %, em, rem, vw, vh, vmin, vmax 등등

CSS의 Property 값을 선언할 때 color 관련된 값은 #RGB, #RGBR, #ffffff, #fff, white, black, rgb(n, n, n), rgba(n, n, n, n)...
 - 색상 : #16진수(#000000~#FFFFFF), 상수(red, blue 등), rgb(0,0,0) ~ rgb(255,255,255) 함수
 - rgb() 함수의 경우, 4번째 속성은 작성할 경우 투명도(0~1)를 의미한다.

CSS는 모든 html 요소에 style을 적용할 때 Box Model을 사용하여 적용
 content --- padding --- border --- margin --- border --- padding --- content
  [ -------- 한개의 style 영역 --------] [ -------- 한개의 style 영역 --------]
 - 두개의 인접한 block element들의 위/아래 margin은 더해지지 않고 더 큰쪽 하나만 적용된다. (겹칩 적용)
```
```css
body {
    background-color: yellow;
}
```

### 웹 문서에 Style 적용 3가지 방법
 1. inline : style 속성으로 정의
    - 재사용성이 떨어지고, 유지보수가 어려워 웹 표준에서 권장하지 않음.
    - 아래 방식들 보다 우선순위가 제일 높다.
    ```html
    <body style="background-color: yellow;">
        내용
    </body>
    ```
 2. style 태그 : html 문서 내부에 style 태그 정의
    - 전역 스타일과 다른 스타일을 적용할 때 사용한다.
    ```html
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <link rel="stylesheet" href="main.css">
        <style>
            body {
                background-color: red;
            }
        </style>
        <!-- link 위에 작성 시, 순서가 달라지기 때문에 나중에 작성된게 적용된다. -->
    </head>
    <body>
        내용
    </body>
    ```
 3. 외부파일을 만들어서 연결 : link 태그를 사용해서 외부파일(.css)을 연결
    - .css, .sass 등의 파일을 생성해서 link 태그로 연결
    - 전역으로 여러 페이지에 일관된 스타일을 적용할 때 권장하는 사용방식이다.
    ```html
    <head>
        <link rel="stylesheet" href="main.css">
         <!-- rel 속성은 html과의 관계를 작성 -->
         <!-- href 속성은 연결할 파일을 지정. -->
    </head>
    <body>
        내용
    </body>
    ```
 - style 태그와 link 태그는 우선순위가 같아 선언된 순서에 영향을 받는다.

### CSS 활용해보기
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS</title>
    <style>
        * {
            color: blueviolet;
        }
        #coffee {
            background-color: yellow;
        }
        .two {
            background-color: pink;
        }
        div > p { /* 자식만 */
            background-color: green;
        }
        div p { /* 자손모두 */
            color: red;
        }
    </style>
</head>
<body>
    <h1>CSS Selector</h1>
    <div>
        <p>개나리</p>
        <p class="two">진달래</p>
        <p>라일락</p>
    </div>
    <p id="coffee">커피</p>
    <p class="two">우유</p>
    <p>녹차</p>
    <div>
        <section>
            <article>
                <p>사과</p>
                <p class="two">딸기</p>
                <p>참외</p>
            </article>
        </section>
    </div>
</body>
```

### 반응형 웹 컨텐츠
 - PDF에 있는 내용들 따라 실습
    - viewport, CSS 미디어 쿼리...
 - 실습은 코드 작성 후, 브라우저의 개발자 도구 요소 선택 옆에 화면 전환을 통해 적용 사항 확인 가능
```html
<head>
    <meta charset="UTF-8">
    <!-- <meta name="viewport" content="width=device-width, initial-scale=1.0"> -->
    <!-- 위 옵션에 따라 device에 따라 viewport 기준으로 사진이나 글자가 조정되는 것을 확인 가능하다. -->
    <title>반응형 웹 컨텐츠</title>
</head>
<body>
    <img width="450" src="https://i.namu.wiki/i/vvxxU0OGLVbrBNYc-O7rEG8AWdZhytXFi8UF0aQeVTAFurhRz3wGceg27wQca9FYLGEieUm-N2zjcSltkEI9TxJ8hfLjo87rYrRco2bGwZJdcrwSFQrM34cTgPikwZYHioMURLynESSfRDb1nqd2qA.webp">
    <h2>속초 대포항</h2>
    <p> 예전에는 배를 댈 공간이 없을 정도로 항구에 어선이 많았고 새벽에 고기를 잡아 돌아온 어선으로 북적였다. 항구로 들어오는 진입로 양옆에는 건어물 가게와 횟집이 늘어서 있고, 어판장 쪽에는 활어 난전이 형성되어 있었다. 요즘은 동해 고속도로가 개통되어 현대적인 시설의 호텔과 콘도, 깔끔한 횟집이 많이 들어섰다.</p>
</body>
```
```html
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>media query 적용</title>
    <style>
    body {
        background-color:#00ff00; /* 초록색 */
    }
    
    @media only screen and (max-width: 600px) {
    body {
            background-color:#ffff00; /* 노란색 */
        }
    }
    </style>
</head>
<body>
    
</body>
```

### Bootstrap
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
</head>
<body>
    <div class="container">
        <div class="row">
            <div class="col">
                <h3>Column 1</h3>
                <p>test1</p>
            </div>
            <div class="col">
                <h3>Column 2</h3>
                <p>test2</p>
            </div>
            <div class="col">
                <h3>Column 3</h3>
                <p>test3</p>
            </div>
        </div>
    </div>

    <br><hr><br>

    <button type="button" class="btn">Basic</button>
    <button type="button" class="btn btn-primary">Primary</button>
    <button type="button" class="btn btn-secondary">Secondary</button>
    <button type="button" class="btn btn-success">Success</button>
    <button type="button" class="btn btn-info">Info</button>
    <button type="button" class="btn btn-warning">Warning</button>
    <button type="button" class="btn btn-danger">Danger</button>
    <button type="button" class="btn btn-dark">Dark</button>
    <button type="button" class="btn btn-light">Light</button>
    <button type="button" class="btn btn-link">Link</button>
</body>
```


## JavaScript 특성
 - 플랫폼에 독립적
 - 인터프리터 언어 (=동적 타이핑 언어)
    - 데이터 타입이 실행 시점에 결정된다.
 - 함수적 프로그래밍 언어
 - 객체 지향 언어
 - Client Side(Browser)에서 실행될때 아래와 같은 것들을 한다.
    - html 요소의 이벤트 처리
    - DOM API를 이용해서 동적으로 문서 구조를 변경
    - 사용자 입력 값들의 validation check
 - 비동기 요청, 처리 진행
 - 다양한 라이브러리 지원(Frontend, 딥러닝 등등)

### JavaScript를 HTML 문서에 적용하는 3가지 방법
 - script 태그는 java를 정의하거나 외부 파일(.js)을 연결할 떄 사용한다.
 1. inline 방식
  - 재사용성이 떨어지고, 유지보수가 어려워 웹 표준에서 권장하지 않음.
    ```html
    <body onload="javascript:window.alert('load event 발생')">
        내용
    </body>
    ```
 2. script 태그를 사용해서 html 문서 내부에 정의
  - head 태그의 child로도 사용할 수 있고, body의 child로도 사용할 수 있다.
    - head 태그에서는 함수를 정의할 때 사용한다.
    - body 태그에서는 즉시실행시킬 때 사용 한다.
        - 여러개의 내용이 있는 경우, 순차적으로 실행된다.
    ```html
    <body>
        내용
        <script>
            window.alert('html 태그는 end 태그를 생략해도 되는 태그들이 있습니다.');
        </script>
    </body>
    ```
 3. script 태그를 사용해서 분리된 .js 파일을 연결
    ```html
    <head>
        <script src="main.js"></script>
    </head>
    <body>
        내용
    </body>
    ```


## JavaScript 기본 : 입/출력
```html
<body>
    JavaScript 객체를 이용해서 출력하는 방법 <br>
     1. html 문서에 출력 : document 객체 활용 <br>
     2. console 객체를 이용해서 출력(디버깅, 로깅 목적) <br>
     3. window.alert('출력내용') <br>
    <script>
        document.write("JavaScript에서 html 내용으로 출력합니다. <br>");
        console.log("브라우저 개발자도구 console탭에서 확인할 수 있습니다.");
    </script>

    <br>
    JavaScript 객체를 이용해서 입력받는 방법 <br>
    1. window.prompt('message', 기본값) : 사용자가 입력한 값을 리턴(문자열로 리턴) <br>
    2. window.confirm('message') : 확인 버튼을 누르면 true가 return / 취소 버튼을 누르면 false가 return <br>
    <script>
        let input = window.prompt('나이를 입력하세요', 15);
        document.write("타입 : " + typeof(input) + ", 나이는 :  " + input + "<br>");

        let res = window.confirm('게임을 종료하시겠습니까?');
        document.write(typeof(res) + ", " + res + "<br>");
    </script>
</body>
```


## JavaScript 기본 : 데이터 타입
```html
<body>
    원시자료형(Primitive Data Type) : string, number, boolean, bigint, symbol, undefined, null <br>
    참조자료형(Reference Data Type) : array, function, object <br>
    <script>
        let a = 'true';
        let b = '12345';
        console.log(typeof(a)); // string
        console.log(typeof(b)); // string
         // 문자열은 '' 또는 "" 로 작성
        console.log(typeof(true)); // boolean
        console.log(typeof(12345)); // number
        console.log(typeof(123.45)); // number
         // 숫자는 정수와 실수를 구분하지 않는다.
        console.log(typeof(123456n)); // bigint
         // bigint는 8byte 이상의 정수를 표현, 연산 가능한 타입
         // bigint는 범위 제한이 없는 정수이나, 운영체제의 제약을 받는다.
        
        let c = []; // 배열
        let d = new Array(); // 배열
        console.log(typeof(c)); // object
        console.log(typeof(d)); // object
         // 배열은 참조자료형이기 때문에 object로 결과가 나옴. (객체로 취급한다는 말이다.)
        
        let g; // 초기화 하지 않음.
        console.log(typeof(f)); // undefined
        console.log(typeof(g)); // undefined
        console.log(typeof(undefined)); // undefined

        let h = null; // 객체에 대해서 의도적으로 null 할당.
        console.log(typeof(h)); // object
         // null은 원시자료형이나 object가 결과로 나온다.
        
        let x = function() {};
        let y = () => {}; // 화살표 함수
        console.log(typeof(x)); // function
        console.log(typeof(y)); // function

        let o = {}; // JSON Object
        let o2 = new Object(); // JavaScript의 Root객체에 해당함.
         // 모든 JavaScript의 객체는 자동으로 Object를 상속받는다.
        console.log(typeof(o)); // object
        console.log(typeof(o2)); // object

        a = true;
        b = 1;
        console.log(a==b); // true
         // JS에서 정수와 boolean은 호환된다. (true = 1 / false = 0)
    </script>
</body>
```

### 심볼(Symbol) 타입
 - ES6에서 새로 추가되었다.
 - 객체의 속성을 고유하게 사용하기 위한 식별ID로 활용된다.
    - 속성 간의 충돌 방지를 위해서 만들어졌다.
 - 심볼은 변경 불가능한 원시 값이다.
 - 심볼은 실제 값으로 활용되지 않으며, 디버깅 시 활용된다.


## JavaScript 기본 : 변수
```html
<body>
    <p> const : 상수선언을 의미한다. <br>
                반드시 초기화가 필요하다. <br>
                한번 초기화 되면 변경이 불가하다. <br>
                ES6에서 추가되었다. <br>
        <br>
        var와 let 은 Scope의 차이가 있다. <br>
        var : 함수 Scope. <br>
              window의 속성으로 추가됨 <br>
               - 즉, 전역변수로 활용될 수 있다. <br>
               - 이는 전역객체가 오염될 수 있음을 의미한다. <br>
              호이스팅 된다. <br>
              중복 선언 가능 <br>
        let : 블록 Scope. <br>
              window의 속성으로 추가되지 않는다. <br>
              중복 선언 불가능. <br>
              ES6에서 추가되었다. <br>
    ※ window는 브라우저의 최상위 객체이다. </p>
    <script>
        const SUCCESS = true; // 초기화하지 않으면 SyntaxError(문법 오류) 발생.
        //SUCCESS = false; // TypeError 발생. (상수의 값을 바꾸려고 해서)
        console.log(SUCCESS);

        f(); // 호이스팅
        //f2(); // 변수는 호이스팅 되지만 실제 할당은 원래 위치에서 되기 때문에 오류 발생.

        console.dir(window); // window 객체 출력
        console.dir(this); // window 객체 출력
         // 위 결과에 globalVar가 추가되어 있다.
         // var 선언이 많을 수록 window 객체 자체가 무거워질 수 있고, 잘못 사용 시 문제가 있을 수 있다.
        var globalVar = 100;
        let localVar = "let으로 선언되는 변수";
         // window 객체에 추가되지 않는다.

        {
            var local = "block scope";
            let local2 = "block scope";
        }
        console.log(local);
         // var는 블록 scope이 아니기 때문에 참조 가능하다.
        //console.log(local2);
         // let은 블록 scope이기 때문에 ReferenceError(참조 오류)가 발생한다.

        function f() { // 무조건 함수 정의는 hoisting 된다.
            var functionVar = "function scope";
            globalVar2 = "window 속성으로 추가됨.";
            console.log("f() 함수가 호출됨.")
        };
        //console.log(functionVar);
         // var는 함수 scope이기 때문에 ReferenceError(참조 오류)가 발생한다.
         // 함수 밖에서 참조가 안되기 때문에 window 객체에도 추가 되지 않는다.
        
        f(); // 함수 호출
         // functionVar는 window 객체에 추가 안된다.
         // globalVar2는 window 객체에 추가 된다.
         // 즉, 함수 내에서도 window 객체에 값을 추가하고자 하는 경우에는 var/let 선언을 안하면 된다.
        
        let f2 = function() {
            console.log("f2() 함수가 호출됨.")
        }

        var globalVar = 200;
         // var는 중복 선언이 가능하다.
        //let localVar = "two";
         // let은 중복 선언이 불가하다. SyntaxError
    </script>
</body>
```

### 변수명 작성 규칙
 - 키워드는 사용불가
    - 키워드 : break, else, case 등등
 - 특수 문자는 _와 $만 허용
 - 숫자로 시작하면 안됨
 - 공백은 입력하면 안됨
 - 대소문자 구별

### 호이스팅(Hositing)
 - 인터프리터가 변수와 함수의 메모리 공간을 선언 전에 미리 할당하는 것을 의미한다.
 - JavaScript 엔진이 먼저 전체 코드를 한 번 스캔하고 실행컨텍스트에 미리 기록해 놓기 때문에 이런 현상이 발생하는 것이다.
 - 선언부만 끌어올리며, 할당은 이뤄지지 않는다.
    - 즉, 실제 메모리에 영향을 주지 않는다.
    - 이는 익명 함수가 호이스팅 되지 않는 내용과도 이어진다.


## JavaScript 기본 : 연산자
```html
<body>
    다른 프로그래밍 언어에 없는 JavaScript의 특수한 연산자만 다룹니다. <br>
    <script>
        /* 산술연산자 - 거듭제곱 연산자 */
        console.log(Math.pow(2, 3)); // 8 (옛날 방식)
        console.log(2 ** 3); // 8 (신규 방식)

        /* 비교연산자 - 동등연산자와 일치연산자*/
        let a=123, b="123";
        console.log(a==b); // true
         // value만 비교 (동등연산자)
         // JavaScript 엔진은 연산자에 따라 자동 형변환이 필요하면 형변환을 수행함.
        console.log(a===b); // false
         // value와 타입을 함께 비교 (일치연산자)
         
         /* 숫자로 구성된 문자열을 number로 형변환하는 방법 2가지.
          * 방법1) Number() 전역 객체 활용.
          * 방법2) parseInt() 전역 객체 활용. */
        console.log(Number("123seoul")); // NaN
         // NaN(Not a Number)로 Number로 형변환 불가하다는 의미다.
         // Number()는 문자열 전체가 숫자일 경우에만 형변환이 가능하다. 
        console.log(parseInt("123seoul")); // 123
         // parseInt()는 문자열로 된 부분에서 숫자만 뽑아서 형변환 해주는 특성이 있다.
        console.log(parseInt("077", 8)); // 63
         // 첫번째 인수가 8진수 값으로 전달되었다는 것을 말하며, 이를 Decimal(10진수)로 변환
        console.log(parseInt("ff", 16)); // 255
         // 첫번째 인수가 16진수 값으로 전달되었다는 것을 말하며, 이를 Decimal(10진수)로 변환
        console.log(parseInt("100001", 2)); // 33
         // 첫번째 인수가 2진수 값으로 전달되었다는 것을 말하며, 이를 Decimal(10진수)로 변환
    </script>

    <p>
        JavaScript 코딩 스타일로 true일때만 실행 또는 false 일때만 실행할 경우 &&, ||로 처리한다. <br>
        - &&와 || 의 short circuit operator 특성을 사용한다는 의미이다. <br>
        - React와 같은 대상들은 if문을 활용하지 못하는 경우가 있어 3항 연산자를 많이 활용하기 때문에 위 개념을 JavaScript에서 유달리 쓰는 경향이 있다. <br>
    </p>

    <br>
    Q> 사용자 입력 받아서 &&, || 로 짝수, 홀수를 출력합니다. 
    <script>
        let num = parseInt(window.prompt("정수를 입력하세요", 1));
        (num%2==0) && console.log(`${num}은 짝수`);
         // 앞이 true이면 뒤에 문장 실행 (=짝수)
         // 앞이 false이면 뒤에 문장 미실행 (=홀수)
         /* &&는 앞이 true이면 뒤제 문장이 무조건 실행시켜야 true/false 여부를 결정할 수 있다. */
        (num%2==0) || console.log(`${num}은 홀수`);
         // 앞이 true이면 뒤에 문장 미실행 (=짝수)
         // 앞이 false이면 뒤에 문장 실행 (=홀수)
         /* ||는 앞이 false이면 뒤제 문장이 무조건 실행시켜야 true/false 여부를 결정할 수 있다. */
    </script>

    <br>
    Q> 사용자 입력 받아서 3항 연산자(조건? true표현식 : false표현식)로 짝수, 홀수를 출력합니다. 
    <script>
        let num1 = parseInt(window.prompt("정수를 입력하세요(3항 연산자)", 1));
        console.log((num1%2==0)? `${num1}은 짝수` : `${num1}은 홀수`);
    </script>

    <br>
    instanceof 연산자 : [인스턴스(객체) instanceof 타입|부모타입] is a 관계에 대해 false, true를 리턴한다. <br>
    ?? 연산자(Nullish 연산자) : null 또는 undefined일 때, 기본값을 설정할 수 있는 연산자이다. (ES11에서 추가) <br>
    ?. 연산자(Optional 체이닝 연산자) : 인스턴스(객체).속성이 null 또는 undefined이어도 안전하게 접근 가능하게 해주는 연산자이다. (ES11에서 추가) <br>
    <script>
        let x = null ?? "default";
        console.log(x); // default

        let y = 0 ?? "default";
        console.log(y); // 0

        let z = function() { return null; }() ?? "default";
        console.log(z); // default
         // ?? 연산자는 함수의 return 값이 null일 경우에 유용하게 쓰인다.

        const user = { name: 'korea' };
        //console.log(user.number.mobile); // TypeError: Cannot read properties of undefined
        console.log(user.number?.mobile); // undefined
    </script>

    <br>
    Boolean() 또는 !!를 사용해서 boolean으로 형변환 할 수 있다.
    <script>
        console.log(!0 + ', ' + !!0 + ', ' + Boolean(0)); // true, false, false
        console.log(!NaN + ', ' + !!NaN); // true, false
        console.log(!undefined + ', ' + !!undefined); // true, false
        console.log(!null + ', ' + !!null); // true, false
        console.log(!{} + ', ' + !!{}); // false, true
        console.log(![] + ', ' + !![]); // false, true
        console.log(!'' + ', ' + !!''); // true, false
        console.log(!' ' + ', ' + !!' '); // false, true
    </script>
</body>
```


## JavaScript 기본 : 제어문 / 반복문
```html
<body>
    if~else, if~else if~else <br>
    <pre>
    switch(표현식) {
        case 값: 문장; ...; break;
        case 값: 문장; ...; break;
        case 값: 문장; ...; break;
        ...
        default: 문장; ...;
    }
    </pre>
    switch문에서 break 대신 return문 사용 <br>
    <script>
        const fruit = 'apple';
        const price = (() => {
            switch(fruit) {
            case "apple" : return 1000;
            case "banana" : return 500;
            case "orange" : return 2500;
            default : return 0;
            }
        })(); // 1회성 함수를 정의하고 즉시 호출 진행.(즉시 실행 함수)
        console.log(price);
    </script>

    반복문은 for, while, do~while문 사용 <br>
    for~in~문 : 집합객체에서 요소의 key(index)를 순차적으로 반환합니다. <br>
    for~of~문 : 집합객체에서 요소의 value를 순차적으로 반환합니다. <br>
    <script>
        let nums = [100, 99, 98, 97, 96];
        for (let key in nums) {
            console.log(key + ', ' + nums[key]);
        } // 배열의 index + value가 출력됨.
        for (let item of nums) {
            console.log(item);
        } // 배열의 value가 출력됨.

        let user = { userId : 'tester', username: '테스터', userpwd : 't1234' };
        for (let key in user) {
            console.log(key + ', ' + user[key]);
        } // 객체의 key + value가 출력됨.
        for (let item of Object.values(user)) {
            console.log(item);
        } // 객체의 value가 출력됨.
          // Object.values()는 객체가 가지고 있는 property의 값들만 묶어서 배열로 만들어준다.
          // for~of~문은 배열 대상으로만 실행되서 객체의 값은 그냥 꺼낼 수는 없다.
    </script>
    
    Object.keys(), Object.values(), Object.entries() 들은 ES8에서 추가되었다. <br>
</body>
```


## JavaScript 기본 : 구조 분해 할당
```html
<body>
    desctructuring : 배열 또는 객체의 값을 분해해서 변수에 개별 값을 할당하는 것을 말한다. (ES6에서 추가) <br>
    <script>
        let nums1 = [100, 99, 98, 97, 96];
        let [a, b, c, d, e] = nums1; // 분해 할당
        console.log(a); // 100
        console.log(b); // 99
        console.log(c); // 98
        console.log(d); // 97
        console.log(e); // 96

        let user1 = { userId : 'tester', username: '테스터', userpwd : 't1234' };
        const { userId, username, userpwd } = user1; // 분해 할당
         // 객체의 분해 할당은 각 변수에 일치하는 property들을 찾아 값을 할당합니다.
         // 즉, 미일치 하는 변수들은 일치하는 property을 못찾아 undefined가 됩니다.
        console.log(userId); // tester
        console.log(username); // 테스터
        console.log(userpwd); // t1234
    </script>

    Q> 배열의 요소 개수보다 많은 변수를 분해 할당에 선언하면? <br>
    Q> 객체의 요소를 분해할당할때 객체에 존재하지 않는 key를 분해 할당 변수로 선언하면? <br>
    <script>
        let nums2 = [100, 99, 98, 97, 96];
        let [a1, b1, c1, d1, e1, f1] = nums2; // 분해 할당
        console.log(f1); // undefined
         // f1은 nums2의 최대 index를 초과한 범위를 할당하려고 했기 때문에 undefined가 됩니다.

        let user2 = { userId : 'tester', username: '테스터', userpwd : 't1234' };
        const { USERNAME } = user2; // 분해 할당
        console.log(USERNAME); // undefined
         // 즉, 객체의 분해 할당은 각 변수에 일치하는 property들을 찾아 값을 할당합니다.
         // 미일치 하는 변수들은 일치하는 property을 못찾아 undefined가 됩니다.
    </script>

    spred (...) 연산자 : 배열 또는 객체의 요소를 분해해준다. (ES6에서 추가)<br>
    <script>
        let nums3 = [100, 99, 98, 97, 96];
        let copyNums = [...nums3, 91, 90];
        for(let n of copyNums) {
            console.log(n);
        }

        let user3 = { userId : 'tester', username: '테스터', userpwd : 't1234' };
        let customer = { ...user3, age:30, address:"seoul" };
        for(let n of Object.values(customer)) {
            console.log(n);
        }

        function hap(a, b, c, d, e) {
            return a+b+c+d+e;
        }
        console.log(hap(...nums3)); // 490
    </script>
</body>
```


## JavaScript 기본 : 배열
```html
<body>
    JavaScript의 배열은 컴파일 언어에서의 배열과 차이가 있습니다. <br>
    1. 크기가 가변적입니다. (동적으로 size가 변경됩니다.) <br>
    2. 저장되는 요소의 타입이 동일하지 않아도 됩니다. <br>

    기타 JavaScript의 배열 특성
    1. JavaScript의 배열은 Reference Type 입니다. (즉, Object 유형입니다.) <br>
    2. JavaScript의 배열은 생성되면 length 멤버 필드가 자동 생성되고 배열의 size가 저장됩니다. <br>
    3. [], new Array(), new Array(5), new Array(1,2,3,4,5,6) 로 생성 가능합니다.
    - new Array(5)로 선언되어도, 5는 초기 선언시의 size일 뿐이라 사이즈를 초과해서 값을 할당할 수 있습니다.
    <script>
        let arr1 = [true, 'korea', 3.14, function(){}, { name: 'korea', age:30 }, [10, 20]];
        console.log(arr1.length); // 6
        arr1.push(123n, {});
        console.log(arr1.length); // 8
    </script>
</body>
```


## JavaScript 기본 : 함수
```html
<body>
    함수 정의 : 기능을 수행하는 코드들의 묶음
    <br><br>
    함수적 프로그래밍 언어 특성 <br>
    1. 함수를 1급 객체로 취급한다. <br>
    2. 함수를 객체로 취급하기 때문에 변수에 할당 할 수도 있다. <br>
    3. 함수의 인수로 함수(기능)를 전달할 수 있다. <br>
    4. 함수 내부에 함수를 정의할 수 있다. <br>
    5. 함수 내부에서 함수 정의를 리턴할 수 있다. <br>
    <hr><br>
    
    함수 종류 <br>
    1. 선언적 함수 - function 키워드와 이름으로 선언 & 정의되는 함수 <br>
    2. 익명 함수 - function 키워드와 이름 없이 선언 & 정의되는 함수. 함수를 표현식으로 선언 & 정의. <br>
    3. 즉시 실행 함수 - 함수를 표현식으로 선언 & 정의하고 즉시 실행하는 함수. 1회성으로 App의 초기화를 진행할 때 적합함. <br>
    4. 화살표 함수 - function 키워드 x, 이름 선언 x <br>
    
    선언적 함수는 먼저 호출하고, 나중에 정의되더라도 호이스팅(hoisting)을 통해 정상적으로 실행 가능하다. <br>
    변수에 저장된 익명 함수는, 변수만 호이스팅(hoisting) 되고, 실제 할당은 할당이 이뤄진 위치에서 수행되기 때문에 선 호출 후 선언 & 정의인 경우에 Reference Error가 발생할 수 있다. <br>

    선언적 함수는 전역 객체(window, global)로 추가된다. (=전역 함수가 된다.) <br>
    어디서든 함수를 사용할 수 있다는 말이되며, 이와 같은 현상을 방지하기 위해서는 익명 함수를 많이 활용한다. <br>
    <pre>
        function f() { } // 선언 함수

        let g = function () { } // 익명 함수

        (function() { })(); // 즉시 실행 함수

        () => { }; // 화살표 함수 (함수의 내용이 여러줄인 경우)
        () => "값을 리턴하는 표현식 문장"; // 화살표 함수 (함수의 내용이 하나인 경우)
    </pre>
    <script>
        f(); // 선언적 함수는 호이스팅 된다.
        //g(); // Reference Error. 익명 함수는 변수만 호이스팅 되고, 함수는 호이스팅이 안된다.
        function f() {
            return console.log("선언적 함수");
        }

        let g = function () {
            return console.log("익명 함수");
        }
        g();

        (function() {
            return console.log("즉시 실행 함수");
            // 전역 초기화 코드를 1번만 실행시킬 때 활용.
        })();

        (() => console.log("즉시 실행 함수 + 화살표 함수(한줄)"))();
        (() => {
            let str = "즉시 실행 함수 + 화살표 함수(여러줄)"
            return console.log(str);
        })();
        
        console.log(this);
         // window 객체 내용 확인.
         // 선언적 함수가 window 객체에 추가된 것을 확인 가능하다.
    </script>
</body>
```
```html
<body>
    Q> 함수에 선언된 형식 매개변수의 수보다 많이 값을 전달한 경우? ignore 됨. <br>
    Q> 함수에 선언된 형식 매개변수의 수보다 적게 값을 전달한 경우? 부족한 매개변수는 undefined로 처리됨. <br>
    <script>
        function hap(a, b, c) {
            return a+b+c;
        }
        console.log(hap(10,10,10)); // 30
        console.log(hap(10,10)); // NaN
         // 3번째 인수는 undefined가 되기 때문에 NaN 반환.
        console.log(hap(10,10,10,10)); // 30
         // 지정된 매개변수 많은 인수는 무시된다.
    </script>

    모든 함수는 명시적 선언 없이 가변인자를 가지는 함수로 정의된다. <br>
    - JavaScript는 동적으로 처리되는 언어이기 때문에 가능한 일이다. <br>
    <br><br>
    모든 함수는 객체를 생성하면 arguments, caller, length, name, prototype 속성이 자동으로 생성된다. <br>
    - arguments 속성은 함수 호출 시, 전달한 파라미터 값들이 저장되는 유사 배열 객체이다. <br>
    - arguments 속성은 함수 호출시에 생성되어 length 멤버필드가 자동 생성되며 실제 전달한 파라미터 개수(arguments의 size)가 저장된다. <br>
    - arguments 속성은 화살표 함수 객체에는 생성되지 않는다. <br>
    - prototype 속성은 함수 문법으로 객체 생성을 위한 생성자 함수를 정의할 때, 객체의 기능(메서드)을 정의하는 객체이다. <br>
    - prototype 속성은 생성자 함수로부터 생성된 모든 인스턴스가 공유하는 객체이다. <br>
    - caller 속성은 현재 함수를 호출한 함수를 참조한다. <br>
    - length 속성은 함수에 정의된 매개변수(parameter)의 개수(size)가 저장된다. <br>
    - name 속성은 함수의 이름이 저장된 속성이다. <br>
    <script>
        function hap2() {
            console.log(arguments.length); // 4
            console.dir(hap2.arguments);
             // 아래서 입력된 인수가 기본적으로 추가된 arguments 속성에 담긴것을 확인 가능하다.
            
            let result = 0;
            for(let n of arguments) {
                console.log(n);
                result += n;
            }
            return result;
        }

        console.dir(hap);
        console.dir(hap2);
         // arguments, caller, length, name, prototype 속성이 동일하게 자동 추가되어 있는 것을 확인 가능하다.

        console.log(hap2(10,10,10,10)); // 40
         // 이와 같이 arguments 속성을 활용하여 함수의 매개변수를 동적으로 관리할 수 있다.
    </script>

    ES6버전부터 함수 호출시에 값을 전달하지 않을 경우 사용할 기본값을 설정할 수 있게 기능이 추가되었다. <br>
    <script>
        const greet = (name = "Guest") => `Hello, ${name}`;
         // name 변수에 값이 할당되지 않으면, Geust가 입력되도록 기본값 지정을 한다.
        console.log(greet()); // Hello, Guest
        console.log(greet("Seoul")); // Hello, Seoul
    </script>
</body>
```
```html
<body>
    콜백 함수(Callback Function) : 함수의 인수(파라미터)로 함수(기능)을 전달하는 것을 말한다. <br>
    - 다른 함수에 인자로 전달되는 함수로써 특정 이벤트 또는 조건이 발생했을 때 호출해서 실행시키기 위해 전달되는 함수이다. <br>
    - 비동기 작업에 주로 많이 사용된다. (이벤트 처리, HTTP 요청에 대한 응답을 처리하는 함수, window.setInterval(f, millisecond), window.setTimeout(f, millisecond) 등) <br>

    콜백 함수를 쓰는 이유? <br>
    - 비동기 처리를 위해서 <br>
    - 모든 함수가 선언적 함수로 구성되어서 window 객체에 추가될 경우, window 객체 자체가 무거워 질 수 있기 때문에 <br>
    위와 같은 이유로 인해 함수의 매개변수에 익명 함수로 콜백 함수를 구현한다. <br>
    여러 비동기 작업을 순차적으로 수행시킬 때는 콜백 함수 내부에 콜백 함수들이 중첩되는 구조로 만들어 진다. <br>
    그런데 이는 콜백 지옥(Callback Hell)로 이어질 수 있다. <br>

    콜백 지옥(Callback Hell) : 중첩된 콜백 함수로 인해 코드의 깊이가 깊어지고, 가독성이 낮아지고, 복잡해지고, 오류 시점이 파악하기 어려워지는 현상이다. <br>
    <script>
        function caller(param) {
            for(let i=0; i<5; i++) {
                param(i)
            }
        }

        function callee(p) {
            console.log(`I'm function: ${p}`)
        }

        caller(callee); // callee는 콜백 함수가 됨.
        caller((m) => console.log(`I'm function: ${m}`)); // 이것 또한 콜백 함수이다.
    </script>

    내부 함수는 내부 함수가 정의된 (enclosing 함수)의 내부에서만 호출 할 수 있다. <br>
    <script>
        function pythagoras(width, height) {
            function square(x) {
                return x * x;
            }
            return Math.sqrt(square(width) + square(height))
            // 내부 함수 square를 우선적으로 참조한다.
        }

        function square(w, h) {
            return w * h;
        }
        console.log(pythagoras(3, 4)); // 15
        console.log(square(3, 5));
         // 내부 함수를 사용하지 않으면 함수 이름 충돌이 발생하여 나중에 만든 함수로 overwrite 되는 현상이 발생된다.
    </script>
    <script>
        let x = "전역 변수";
        function outer() {
            let local = "로컬 변수";
            let x = "outer.x";
            function inner() {
                let innerLocal = "내부 함수의 로컬 변수";
                let x = "inner.x";
                console.log(innerLocal + ", " + x + ", " + local);
                 // outer()의 변수를 참조 가능하나, inner()에 동일한 x가 있어 inner()의 x가 우선적으로 참조됨.
            }
            inner();
            console.log("from outer : " + x + ", " + local);
             // inner() 내부의 함수는 참조 불가
        }
        outer();
    </script>

    <h3>타이머 설정에 따라 실행되는 callback 함수 실습</h3>
    <div id="timer"></div>
    <button id="stop">STOP</button>
    <script>
        window.onload = function() {
            let interverID = setInterval(()=> {
                                document.getElementById("timer").innerHTML=new Date();
                            }, 1000);
                            
            let btn = document.getElementById("stop");
            btn.onclick = function() {
                window.clearInterval(interverID);
            }
        }
    </script>
</body>
```
 - 콜백 헬 예시
    ```html
    <body>
        <script>
            function firstTask(callback) {
                setTimeout(() => {
                    console.log("First task done");
                    callback();
                }, 1000);
            }
            function secondTask(callback) {
                setTimeout(() => {
                    console.log("Second task done");
                    callback();
                }, 1000);
            }
            function thirdTask(callback) {
                setTimeout(() => {
                    console.log("Third task done");
                    callback();
            }, 1000);
            }
            // 콜백 헬 형태의 코드
            firstTask(() => {
                secondTask(() => {
                    thirdTask(() => {
                        console.log("All tasks are done");
                    });
                });
            }); 
        </script>
    </body>
    ```

### Closure 함수
```html
<body>
    Closure 함수 : 함수가 자산이 선언된 환경(렉시컬 스코프(Lexical Scope))을 기억하고, 그 환경에 접근할 수 있는 기능을 가지고 있는 함수 <br>
    전역 변수 남용을 방지하고, 특정 데이터에 대한 접근을 제한할 수 있다. <br>
    (Counter)함수 실행 후에도 로컬변수를 기억하여 지속적인 상태(state)를 유지할 수 있습니다. <br>
    <script>
        function counter() {
            let count = 0; // 외부에서 직접 접근 불가능
            return {
                increment: function() {
                    count++;
                    console.log(`Count: ${count}`);
                },
                decrement: function() {
                    count--;
                    console.log(`Count: ${count}`);
                }
            }
        }
        const myCounter = counter();
        console.log(myCounter); // increment / decrement 객체가 저장된다.
         /* increment / decrement 객체에는 count 변수가 없어 메모리 초기화(Garbage Collection)가 되어야 하나,
          * 자기 자신이 사용해야하기 때문에 count 변수를 계속 끌고 다닌다. (=count 변수를 계속 기억한다.)
          * 여기서 increment / decrement 는 Closure 함수가 된다. */

        myCounter.increment(); // 1
        myCounter.increment(); // 2
        myCounter.decrement(); // 1
        console.log(myCounter.count); // undefined. 직접 접근 불가능
        console.log(counter.count); // undefined. 직접 접근 불가능


        function multiply(x) {
            return function(y) {
                return x * y;
            }
        } /* 이러한 경우에는 y를 매개변수로 가진 익명 함수가 x 변수를 지속적으로 필요로 한다.
           * 하여 익명 함수가 Closure 함수가 된다. */
        const double = multiply(2);
         // double에는 x를 2로 기억하는 y를 매개변수로 가진 익명 함수가 객체로 할당됨.
        console.log(double);
        console.log(double(5)); // 10
    </script>

    <button id="save">저장</button>
    <button id="delete">삭제</button>
    <script>
        function createButton(label) {
            return function() {
                console.log(`${label} 버튼이 클릭 되었습니다.`)
            }
        }
        document.getElementById("save").onclick = createButton("save");
        document.getElementById("delete").onclick = createButton("delete");
         // label 이라는 변수를 기억하는 익명 객체가 Closure 함수
    </script>
</body>
```

### 함수 내부에서의 this
```html
<body>
    각 함수별로 this는 누구를 지칭하는가? <br>
    - 선언적 함수에서의 this : window 객체(전역 영역(window Scope)에 구성되었기 때문에) <br>
    - 익명 함수에서의 this : window 객체(전역 영역(window Scope)에 구성되었기 때문에) <br>
    - 화살표 함수에서의 this : window 객체(전역 영역(window Scope)에 구성되었기 때문에) <br>
    - 생성자 함수에서의 this : new로 생성된 인스턴스 자신이나, Prototype Object로부터 만들어졌기 때문에 Object로 출력됨 <br>
    - 파라미터로 전달된 함수(콜백함수)에서의 this : window(f3이 window에 포함되어 있기 때문에 일반 함수와 동일) <br>
    - 내부 함수에서의 this : window 객체(inner는 f5의 소속되어 있으나, f5는 window에 소속되어 있기 때문에) <br>
    - 이벤트 핸들러 함수 내부에서의 this : HTMLButtonElement 객체(즉, 이벤트가 발생된 소스 객체를 참조한다.) <br>

    <br>
    여담 - 선언적 함수와 생성자 함수는 비슷한 형태나 작성 규칙이나 내용이 다르다 <br>
    선언적 함수 작성 규칙 : 소문자로 시작하는 명칭 <br>
    생성자 함수 작성 규칙 : 대문자로 시작하는 명칭 <br>
    선언적 함수 내용 : 기능 <br>
    생성자 함수 내용 : 기능이 아닌 객체를 만드는 내용 <br>
    * 결론적으로 옛날 문법은 애매한 부분이 많아 class 문법의 도입이 되었다. <br><br>
    <script>
        function f() {
            document.write("선언적 함수에서 this : " + this + "<br>")
        }
        f();

        let f2 = function() {
            document.write("익명 함수에서 this : " + this + "<br>")
        }
        f2();

        (() => {
            document.write("화살표 함수에서 this : " + this + "<br>")
        })();

        function User() {
            document.write("생성자 함수에서 this : " + this + "<br>")
        }
        new User();

        function f3(callback){
            callee();
        }     
        function callee() {
            document.write("파라미터로 전달된 함수(콜백함수)에서 this : " + this + "<br>");
        }
        f3(callee);

        function f5() {
            let inner = () => {
                document.write("내부 함수에서 this : " + this + "<br>")
            }
            inner();
        }
        f5();
    </script>
    <button id="btn">클릭</button>
    <script>
        document.getElementById("btn").onclick = function() {
            document.write("이벤트 핸들러 함수 내부에서 this : " + this + "<br>")
        }
    </script>
    이벤트 발생 후, document.write()를 호출하면 렌더링 결과가 변경되면서 HTML 페이지의 내용이 지워지고 새로 기록된다 <br>
    위와 같은 동작으로 인해 document.write()는 디버깅이나 테스트용 코드에서만 사용을 권장. (서비스 Application에서 사용 x)
</body>
```


## JavaScript 객체
 - 객체 구조의 참고사항
    - [[Prototype]] 은 해당 객체가 누구로(상속)부터 만들어졌냐이다.
    - Prototype 은 상속받은 객체의 속성 정보들이 존재한다.
 - 객체에서의 null
    - 객체에서 null은 **값이 할당되지 않음** 을 말한다.
    - 이것은 곧 쓰지 않은 객체이니 Garbage Collector에게 처리하도록 얘기하는 것과 같다.
```html
<body>
    JavaScript는 Prototype 기반의 언어라고 한다. <br>
    - JavaScript의 모든 객체는 prototype 객체를 가지고 있고 그 prototype을 복제하면서 객체를 생성한다. <br>

    <br>
    객체 : 속성과 기능을 캡슐화 한 것을 객체라고 한다. <br>
    객체의 종류 <br>
    - 미리 정의된 객체(Predefined Object) : 내장 객체 (Object, Math, Date, Array, Number, Boolean...), BOM객체(window, locator, navigator, screen, document), DOM객체(Node, document, Element...) <br>
    - 정의해서 쓰는 객체(Custom Object) <br>
    
    <br>
    Custom Object 정의 방법 : JSON으로 정의, 함수문법을 사용해서 생성자 함수로 정의, ES6부터 지원하는 Class 문법으로 정의 <br>

    <br>
    JSON 객체 <br>
    - 장점 : 정적인 데이터 표현에 적합하다. <br>
    - 단점 : 동일한 구조의 객체를 여러 번 생성하려면 매번 수작업으로 정의해야 한다. (인스턴스를 생성할 수 있는 틀이 없다, 재사용성이 떨어진다.) <br>
    - 단점 : [[Prototype]] 기반의 상속이나 메서드 재사용 등의 고급 기능을 사용하지 못한다. <br>
    즉, JSON은 정적인 데이터 표현만을 위해서 사용한다. (사용 목적이 이것밖에 없다.) <br>
    기타 특징으로 JSON 객체는 동적으로 요소 추가, 삭제 가능하다. <br>
    기타 특징으로 JSON 문법으로 생성한 객체는 Object을 Prototype으로 하는 인스턴스 이다. <br>
    기타 특징으로 JSON 객체는 생성하자마다 단, 하나의 인스턴스만 생성된다.(단점과 이어진다.) <br>
    <script>
    let student = { name: 'kim', kor: 90, math: 90, eng: 85 };
    console.log(student.name);
    console.log(student['name']);
        // 둘다 key명칭으로 접근하는 방식이다.

    student.total = function() {
        return this.kor + this.math + this.eng;
    } // 요소 추가
    student.pass = function() {
        if(this.total() /3 >= 60) {
            return true;
        } else {
            return false;
        }
    } // 요소 추가
    console.log(student.total()); // 265
    console.log(student.pass()); // true

    delete student.pass; // 요소 삭제
    console.dir(student); // pass가 삭제된 것을 확인 가능.
        /* Prototype : Object
        * 이는 Object로부터 해당 객체가 생성됬음을 말한다. */

    console.log(student === Object) // false
    console.log(student === JSON) // false
    console.log(student instanceof Object) // Object과의 상속관계이기 때문에 true
    // console.log(student instanceof JSON) // JSON과 상속관계가 없기 때문에 Error
    </script>


    <br>
    함수문법을 사용해서 인스턴스를 생성하는 틀(=생성자 함수)을 정의 <br>
    - 생성자 함수로부터 인스턴스를 생성할 때 new를 사용한다. <br>
    - ES6 이전부터 사용되어 온 객체 생성 방식 <br>
    - [[Prototype]] 기반의 상속이나 메서드 재사용 등 고급 기능을 사용 가능하다. <br>
    - 동일한 구조를 가진 여러 인스턴스 생성에 적합하다. <br>
    - new 생성자함수()로 생성되는 원형 객체에 Prototype 속성이 생성된다. <br>
    - Prototype 속성에 기능(메서드)을 추가하면 new 생성자함수()로 생성되는 모든 인스턴스들이 공유하게 된다. (prototype 기반의 고급 기능) <br>
    함수문법으로 객체를 정의하면 기능이 prototype 영역에 한번만 생성되므로 메모리를 효율적으로 사용할 수 있습다.

    <br>
    apply(), bind() 함수는 파라미터로 전달되는 this(함수의 실행 컨텍스트)를 변경한다. <br>
    apply() 함수는 함수를 즉시 호출한다. 즉시 실행하면서 this를 설정한다. <br>
    bind() 함수는 함수를 즉시 호출하지 않고, this와 인자를 바인딩한 새로운 함수를 반환한다. this를 먼저 바인당한 다음에 나중에 실행 시킬 떄 활용.<br>
    참고> call() 함수도 this(함수의 실행 컨텍스트)를 변경한다. <br>
    <script>
    function Student(name, kor, math, eng) {
        this.name = name;
        this.kor = kor;
        this.math = math;
        this.eng = eng;
    }
    Student.prototype.total = function() {
        return this.kor + this.math + this.eng;
    } // prototype에 total 추가
    Student.prototype.pass = function() {
        if(this.total() /3 >= 60) {
            return true;
        } else {
            return false;
        }
    } // prototype에 pass 추가

    let kim = new Student('AA', 80, 80, 80); // 인스턴스(객체) 생성
    let song = new Student('BB', 77, 88, 99);
        // kim과 song의 원형 객체는 Student 이다.

    console.log(kim.total()) // 240
    console.log(song.total()) // 264

    console.dir(kim);
    /* Prototype : Object
        * 이는 Student 객체가 Object로부터 생성됬음을 말한다. */

    console.log(kim instanceof Student); // Student와의 상속관계이기 때문에 true
    console.log(kim instanceof Object); // Object과의 상속관계이기 때문에 true



    /* 생성자 함수로 정의된 Student Prototype은 prototype 기반으로 상속(Object)을 선언할 수 있다. */
    function SubStudent(grade) {
        this.grade = grade;
    } // 방법1
    SubStudent.prototype = Student.prototype; // 상속을 선언
    
    let park = new SubStudent(6);
    console.dir(park);
        // Prototype은 Object 이나, constructor는 Student 임을 확인할 수 있다.
    park.name = 'cc';
    park.kor = 66;
    park.math = 77;
    park.eng = 88;
    console.log(park.total()) // 231

    console.log(park instanceof Object); // true
    console.log(park instanceof Student); // true
    console.log(park instanceof SubStudent); // true

    function SubStudent2(name, kor, math, eng, grade) {
        Student.apply(this, [name, kor, math, eng]);
            // 각 변수를 받아 this에 바로 전달해준다. (Student라는 생성자 함수를 즉시 호출한다.)
        this.grade = grade
    } // 방법2
    function SubStudent3(name, kor, math, eng, grade) {
        const base = Student.bind(this);
            // Student라는 생성자 함수를 즉시 호출하지 않는다.
        base(name, kor, math, eng);
        this.grade = grade
    } // 방법3
    </script>


    <br>
    Class 문법으로 정의 <br>
    - ES6부터 class 문법으로 인스턴스를 생성할 수 있는 원형 객체를 정의할 수 있다. <br>
    - 구조도 기존대비 좀더 명확하고 직관적이다. <br>
    - 객체 지향 프로그래밍(OOP) 지원 : 복잡한 구조의 메서드와 상속관계를 체계적으로 관리 가능하다. <br>
    - 클래스 문법으로 정의하는 객체의 상속은 extends를 사용하여 선언한다. <br>
    - 자식 클래스에서 부모로부터 상속받은 메서드를 override(재정의) 할 수 있다. <br>
    - 상속관계에서 부모 클래스의 생성자 메서드를 호출할 때 super(...)를 사용한다. <br>
    - super는 생성자의 첫번째로 this를 사용하기 전에 한번만 호출해야 한다. <br>
    - 그 외, 객체 관련 특징은 함수문법을 사용한것과 동일하다. <br>
    <script>
        class StudentNew {
            constructor (name, kor, math, eng) { // 생성자 메서드
                this.name = name;
                this.kor = kor;
                this.math = math;
                this.eng = eng;
            }
            total() { // 기능 구현 메서드
                return this.kor + this.math + this.eng;
            }
            pass() {
                if(this.total() /3 >= 60) {
                    return true;
                } else {
                    return false;
                }
            }
        }

        let hong = new StudentNew("홍", 55, 77, 99);
        console.log(hong.name + ', ' + hong.total());
        console.dir(hong);

        console.log(hong instanceof Object); // true (상속 관계 확인)
        console.log(hong instanceof StudentNew); // true (원형 타입 확인)


        /* 상속은 함수문법 대비 간단하다 */
        class Learner extends StudentNew {
            constructor(name, kor, math, eng, sci) {
                // this.sci = sci; // Error. super는 this 전에 사용해야한다.
                super(name, kor, math, eng);
                this.sci = sci;
            }
            toString() { // Object로부터 상속받은 메서드를 override함
                return `Learner[name=${this.name}, birth=${this.birth}]`;
            }
        }

        let learner1 = new Learner("누구냐넌", 90, 88, 99, 75);
        console.log(learner1.total());
        console.dir(learner1); // Prototype : StudentNew

        console.log(learner1 instanceof Object); // true (상속 관계 확인)
        console.log(learner1 instanceof StudentNew); // true (상속 관계 확인)
        console.log(learner1 instanceof Learner); // true (원형 타입 확인)

        console.log(learner1.toString()); // toString 오버라이드 전/후 확인해보기
    </script>

    <br>
    기타 설명 <br>
    - JavaScript에서 상속은 [[Prototype]], Prototype을 이용해서 Prototype의 Chain 형태로 구현된다. <br>
    - Prototype의 Chain은 객체 자신과 속성과 메서드와 [[Prototype]]이 가리키는 링크를 따라 부모 역할을 하는 모든 Prototype 객체의 속성과 메서드에도 접근이 가능하다. <br>
    - 최상위 Object.prototype에서도 속성이나 기능 메서드를 찾지 못하면 undefined를 반환하지 못한다. <br>

    <br> static <br>
    - static 속성 : 인스턴스마다 고유한 값으로 생성되지 않는다. <br>
    - static 메서드 : prototype 객체에 추가되지 않는다. <br>
    - 클래스에 속하는 속성과 메서드이다. <br>
    - 인스턴스를 생성하지 않고 속성을 참조할 수 있고, 메서드를 호출 할 수 있다. <br>
    - 클래스이름으로 속성을 참조할 수 있고, 메서드를 호출 할 수 있다. <br>
    <script>
        class User {
            static type = "일반";
            static staticMethod() {
                return User.type + "은 회원이 아니다."
            }
        }
        console.log(User.type);
        console.log(User.staticMethod());
        console.dir(User); // prototype이 빈객체이다.
    </script>
</body>
```

### JavaScript의 AccessModifier
```html
<body>
    객체 지향 프로그래밍(OOP) 객체는 속성을 private로 선언하고, getter/setter은 외부에서 Access 할 수 있도록 public으로 정의한다. <br>
    단, JavaScript는 Java 처럼 AccessModifier가 정교하지 않다. <br>
    <script>
        class Person {
            #name; // #은 private 선언을 의미
            #age;
            constructor(name, age) {
                this.#name = name;
                this.#age = age;
            }
            setName(name) {
                this.#name = name || 'unknown'; // name이 false 조건일 경우에 대한 기본값 설정
            }
            getName(name) {
                return this.#name;
            }
            toString() { // Object의 toString() Override
                return `Name : ${this.#name}`;    
            }
        }
        const p = new Person('A', 500);
        console.log(p.name); // undefined (#은 private를 의미하긴 하지만, 변수명은 #name 이다.)
        // console.log(p.#name); // Private Field Error

        console.log(p.getName()); // A
        p.setName('test');
        console.log(p.getName()); // test
        p.setName(null);
        console.log(p.getName()); // unknown
        console.log(p.toString()); // Name : unknown

        console.dir(p);
    </script>
</body>
```

### Map 과 Set 자료구조
```html
<body>
    ES6에서 추가된 Map(key, value로 저장하는 자류구조), Set(value 저장, 중복 허용하지 않음) 자료구조가 있다. <br>
     - Map에 저장되는 key는 unique 해야 한다. (value는 중복 가능하다) <br>
     - Map에 저장되는 key에는 배열, 객체, 함수를 사용할 수 있다. <br>
     - Map에 저장된 순서대로 요소들을 순회한다. <br>
     - Set도 저장한 순서대로 요소들을 순회한다. <br>
        - add(), has(), delete(), clear(), size, forEach(callback) 메서드들이 제공된다. <br>
    <script>
        const map1 = new Map()
        map1.set('name', 'korea') // map 내용 추가
        map1.set('age', '30')
        map1.set(1, 'one')
        console.log(map1.get('name')) // korea
        console.log(map1.has('email')) // false (email이라는 key는 없다.)
        console.log(map1.size) // 3

        map1.delete('age') // map 내용 삭제
        console.log(map1.size) // 2

        map1.set('email', 'test@naver.com')
        map1.set('address', '1111-1111')

        map1.forEach((key, value) => { // forEach()로 요소 순회
            console.log(`${key}: ${value}`) // 저장된 순서대로 요소가 순회한다(출력된다)
        })

        map1.clear() // map 내용 전체 삭제
        console.log(map1.size) // 0

        const set1 = new Set([1, 2, 2, 2, 3])
        console.log(set1) // [1, 2, 3] (중복을 허용하지 않는다.)
        console.log(set1.has(4)) // false
    </script>
</body>
```

## 모듈(export/import)
 - ES6에서 함수 또는 클래스를 파일 단위로 모듈화하여 관리할 수 있는 기능이 추가되었다.
 - export와 import 키워드를 사용해서 파일에 저장된 기능을 내보내기/가져오기를 할 수 있다.
    ```plainttext
    -- 파일 내보내기
    export { 함수이름, 클래스이름, 변수이름 };
    export default 객체;

    -- 모듈 불러오기
    import { 함수이름, 클래스이름, 변수이름 } from 경로/파일.js;
    import 객체 from 경로/파일.js;

    -- 동적으로 모듈 불러오는 방법 : import();
    ```
 - 코드의 재사용성, 유지보수성을 향상 시키게 되었다.
 - 브라우저의 html 페이지에서 모듈을 사용하려면 script 태그의 type 속성에 module이라고 선언해야 한다.
    - 기본 타입은 type="text/javascript" 이다.
    ```plainttext
    <script type="text/javascript" src="..."></script> // 기본 사용(생략해도 됨.)
    <script type="module" src="..."></script> // 모듈 사용 시
    ```
 - 모듈 파일의 확장자는 .js 이다.
 - 모듈은 import를 사용해서 로드될 때 비동기 방식으로(Promise 객체로) 로드된다.
 - 실행중에 동적으로 모듈을 로드할때 import() 함수를 사용한다. (Promise 객체가 반환된다)
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>모듈 : export와 import</title>
</head>
<body>
    <div id="div1"></div>
    <script type="module" src="./main.js"></script>

    <script>
        import('./utills.js').then(module => {
            console.log(module.add(4,4))
        }) // 실행중에도 동적으로 모듈을 로드 할 수 있다.
    </script>
</body>
```
```javascript
/* main.js */
import { add, substract } from './utills.js'
 // 비동기 객체로 로드된다.
 // add, subtract 명칭으로 분해 할당이 된다.

import { PI, E } from './constants.js'
 // PI, E 명칭으로 분해 할당

import { person } from './person.js'
 // person 명칭으로 분해 할당

console.log(person.name) // Seoul
console.log(person.age) // 30
console.log(PI) // 3.14159
console.log(E) // 2.71828
console.log(add(2,2)) // 4
console.log(substract(3,2)) // 1

// HTML에 내용 삽입
document.getElementById("div1").innerHTML = `
        <ul>
            <li>person.name: ${person.name}</li>
            <li>person.age: ${person.age}</li>
            <li>add(2,2): ${add(2,2)}</li>
            <li>substract(3,2): ${substract(3,2)}</li>
            <li>PI: ${PI}</li>
            <li>E: ${E}</li>
        </ul>`
```
```javascript
/* constants.js */
export const PI = 3.14159
export const E = 2.71828
```
```javascript
/* person.js */
const person = {
    name: "Seoul",
    age: 30
}

export { person }
```
```javascript
/* utills.js */
export function add(a, b) {
    return a + b
}

export function substract(a, b) {
    return a - b
}
```
 - export default를 사용하면 모듈에서 하나의 기본 값 또는 객체 또는 함수를 내보낼 수 있다.
 - export default를 사용하면 import 할 때, { } 없이 가져오기 할 수 있다.
```javascript
/* main.js */
import test from "./math.js";
 // export default 인 경우, import 받을 때 원하는 명칭으로 구성할 수 있다.

console.log(test(4,4))
```
```javascript
/* math.js */
export default function multiply(a, b) {
    return a * b
}
```


## JavaScript 내장 객체
```html
<body>
    JavaScript의 여러가지 내장 객체들 사용해보기 <br>
    <script>
        let text = 'Hello World!';
        let result = text.anchor("Chapter 10"); // HTML의 a 태그로 만들어줌.
        console.log(result); // <a name="Chapter 10">Hello World!</a>
        
        let result1 = text.bold(); // HTML의 b 태그로 만듦.
        console.log(result1); // <b>Hello World!</b>
        document.write(result1);


        /* slice(start, end) : 원본 배열 또는 문자열을 변경하지 않고, 새로운 객체를 반환 */
        let result2 = text.slice(6, 12); // 6번째 자리부터 12번째 이전까지 추출
        console.log(text); // Hello World!
        console.log(result2); // World!

        let result3 = text.slice(-6, 12); // 음수로 지정할 경우 문자열을 오른쪽이 아닌 왼쪽 방향으로 읽음.
        console.log(text); // Hello World!
        console.log(result3); // World!

        let result4 = text.slice(-6); // end가 지정되지 않은 경우에는 문자열 끝까지
        console.log(text); // Hello World!
        console.log(result4); // World!


        /* substring(start, end) : 문자열에서만 사용, 음수 인덱스는 허용하지 않음, start > end 이면 자동으로 바꿔서 처리해줌.*/
        let re = text.substring(-6);
        console.log(re); // Hello World! (음수 적용이 안되어 전체 문자열 출력)
        
        re = text.substring(6, 12);
        console.log(re); // World!


        /* split(sperator, limit) : sperator로 tokenize해서 배열로 리턴 */
        let text2 = '사과-배-바나나-딸기-복숭아-귤';
        let fruits = text2.split('-', 4);
        console.log(fruits); // ['사과', '배', '바나나', '딸기']
        console.dir(fruits); // Array
    </script>

    Q> 버튼을 누를때마다 로또 번호 추출하기 <br>
    <button id="lotto">번호 추첨</button>
    <script>
        document.getElementById("lotto").onclick = function() {
            let lottos = []

            while(lottos.length < 6) { // 로또 번호 6개 추첨
                let num = Math.trunc(Math.random()*45+1); // 1이상 45이하의 난수 생성(Math.random() : 0~1 사이의 난수 생성)
                if(!lottos.includes(num)) {
                    lottos.push(num);
                }
            }
            lottos.sort((a, b) => a-b);
            document.write(lottos.join(", ") + ' ');
        }
    </script>
</body>
```

### JSON의 내장 객체 stringify(직렬화)/parse(역직렬화) (+브라우저 storage/DOM API)
 - 직렬화 : JavaScript 객체 > JSON 형식의 문자
 - 역직렬화 : JSON 형식의 문자 > JavaScript 객체
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JSON 객체를 직렬화/역직렬화 해보기</title>
    <script>
        /* JSON 객체를 직렬화/역직렬화 해보기(브라우저의 storage 활용.) */
        let todos = [];
        window.onload = function() {
            const stored = sessionStorage.getItem("todos")
            if(stored) {
                todos = JSON.parse(stored); // 역직렬화 (JSON 형식의 문자 > JavaScript 객체)
                renderTodos()
            }
        }

        function renderTodos() {
            const ulEl = document.getElementById("todoList")
            ulEl.innerHTML=""; // HTML 내용 초기화
            todos.forEach(todo => {
                const liEl = document.createElement("li") // li 태그 생성
                liEl.textContent = todo.text // li 태그에 text 입력

                const editBtnEl = document.createElement("button") // button 태그 생성
                editBtnEl.textContent = "수정" // button 라벨 지정
                editBtnEl.onclick = () => { editTodo(todo.id) }

                const delBtnEl = document.createElement("button")
                delBtnEl.textContent = "삭제"
                delBtnEl.onclick = () => { delTodo(todo.id) }

                liEl.appendChild(editBtnEl) // li 태그에 button 태그를 자식으로 추가
                liEl.appendChild(delBtnEl)
                ulEl.appendChild(liEl) // ul 태그에 li 태그를 자식으로 추가
            })
        }

        function addTodo() {
            const inputEl = document.getElementById("todoInput")
            const txt = inputEl.value.trim() // 공백 제거
            if(txt === "") return // 입력 값 없으면 retrun

            todos.push({
                id: Date.now(),
                text: txt
            })
            inputEl.value="" // 값 초기화

            saveAndRender()
        }

        function saveAndRender() {
            sessionStorage.setItem("todos", JSON.stringify(todos)) // 직렬화 (JavaScript 객체 > JSON 형식의 문자)
            renderTodos();
        }

        function editTodo(id) {
            const newText = prompt("수정할 내용을 입력하세요") // 새로 입력받기
            if(newText === null) return
            
            const todo = todos.find(t => t.id == id) // find는 배열에서 데이터를 찾으면 루프 중단
            if(todo) {
                todo.text = newText
                saveAndRender()
            }
        }

        function delTodo(id) {
            todos = todos.filter(t => t.id != id) // 매개변수와 동일한 id만 todos 에 저장
            saveAndRender()
        }
    </script>
</head>
<body>
    <h2>Todo List</h2>
    <input type="text" id="todoInput" placeholder="해야할 일 입력">
    <button onclick="addTodo()">추가</button>
    <ul id="todoList"></ul>
</body>
```


## JavaScript 이벤트 제어
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 이벤트 제어</title>
    <script>
        /* DOM Level 0 방식
        window.onload = function() {
            console.log("window 객체의 load 이벤트 핸들러1")
        }

        window.onload = function() {
            console.log("window 객체의 load 이벤트 핸들러2")
        }

        window.onload = function() {
            console.log("window 객체의 load 이벤트 핸들러3")
        } // 마지막 데이터만 출력(=하나의 이벤트에 대해서 하나의 이벤트 핸들러만 등록 가능)
        */

        /* DOM Level 2 방식
        window.addEventListener("load", function() {
            console.log("window 객체의 load 이벤트 핸들러1")
        }, false)

        window.addEventListener("load", function() {
            console.log("window 객체의 load 이벤트 핸들러2")
        }, false)

        window.addEventListener("load", function() {
            console.log("window 객체의 load 이벤트 핸들러3")
        }, false) // 1~3 모두 출력(=하나의 이벤트에 대해서 여러 이벤트 핸들러 등록 가능)
        */


        /* 버튼을 누르면 Count 증가 구성 */
        window.onload = function() {
            let count = 0
            let btnEl = document.getElementById("btn")
            btnEl.onclick = function() {
                count++
                document.getElementById("counter").innerHTML = count // count 값을 span에 할당
                this.onclick = null // 이벤트 종료가 되어 더이상 버튼 동작 불가(한번만 실행되게 됨).
            }


            /* 이벤트 강제 발생 로직 */
            let count1 = 0, count2 = 0
            let btn1El = document.getElementById("btn1")
            btn1El.onclick = function() {
                count1++
                document.getElementById("count1").innerHTML = count1
            }

            let btn2El = document.getElementById("btn2")
            btn2El.onclick = function() {
                count2++
                document.getElementById("count2").innerHTML = count2
                btn1El.onclick() // 강제 이벤트 발생. 버튼2를 누르면 버튼1도 같이 값 증가
            }
        }
    </script>
</head>
<body>
    <pre>
    DOM Level 0 이벤트 처리 방식 : 초기 이벤트 핸들러 등록 방식
     - on이벤트명 = 이벤트 핸들러 함수(event객체){ }; 방식으로 작성
        - event객체는 자동으로 전달받는다.
     - 이벤트의 핸들러를 하나만 등록할 수 있다. (단점)
    DOM Level 2 이벤트 처리 방식 : W3C 표준 이벤트 핸들러 등록 방식
     - 이벤트소스객체.addEventListener(이벤트명, 이벤트 핸들러 함수, 이벤트 캡쳐여부(Boolean - default: false)); 방식으로 작성
     - 하나의 이벤트에 대해 여러 이벤트 핸들러를 등록할 수 있다. (장점)
     - 이벤트를 제거하고자 할 때는 "이벤트소스객체.removeEventListener(이벤트명, 이벤트 핸들러 함수)" 와 같이 작성할 수 있다
        - 또는 "이벤트소스객체.on이벤트명 = null;" 로 처리할 수도 있다.
    </pre>

    <br>
    <button id="btn">Count</button>
    <span id="counter"></span>

    <br><br>
    <button id="btn1">버튼1</button>
    <button id="btn2">버튼2</button>
    <h3>버튼1 클릭 횟수 : <span id="count1"></span> </h3> 
    <h3>버튼2 클릭 횟수 : <span id="count2"></span> </h3>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 이벤트 전파</title>
    <style>
        div, h1, p {
            border: 2px solid black;
            padding: 10px;
            margin: 10px;
            text-align: center;
        }
    </style>
    <script>
        window.onload = () => {
            document.getElementById("outerDiv").onclick = function() {
                this.style.backgroundColor = "cyan"
            }
            document.getElementById("innerDiv").onclick = function() {
                this.style.backgroundColor = "green"
            }
            document.getElementById("heading1").onclick = function(event) {
                event.stopPropagation() // stopPropagation() 메서드는 이벤트 전파를 취소시킨다.
                 // 자동으로 전달받는 HTMLEvent 객체를 통해 이벤트 전파 메서드 실행.
                this.style.backgroundColor = "orange"
            }
            document.getElementById("p1").onclick = function() {
                this.style.backgroundColor = "pink"
            } /* p1 태그를 클릭 시, 모든 이벤트가 동작한다. 이는 기본 이벤트 방식이 버블링인 것을 알 수 있다.
               * stopPropagation()를 사용한 경우에는 h1 태그에서 전파가 막힌다. */
            
            document.getElementById("searchForm").onclick = function(event) {
                event.preventDefault() // 브라우저의 기본 이벤트 취소
            }

            document.getElementById("link1").onclick = function() {
                return false // 브라우저의 기본 이벤트 취소(옛날 방식. 권장 X)
            }
        } 
    </script>
</head>
<body>
    이벤트 전파 방식 <br>
    1. Event Bubbling : child element(HTML 태그)에서 발생된 이벤트가 parent element로 전파(Browser의 이벤트 전파 방식) <br>
    2. Event Capturing : parent element에서 발생된 이벤트가 child element들로 전파 <br>
    JavaScript 엔진은 이벤트 발생 시, 모든 이벤트 핸들러 함수를 호출할 때, 첫번째 인수로 발생한 이벤트 정보가 저장된 HTMLEvent 객체를 자동으로 전달한다. <br>
    기본 이벤트 전파를 취소하려면 HTMLEvent 객체의 stopPropagation() 메서드를 호출하면 된다. <br>
    <div id="outerDiv">
        <div id="innerDiv">
            <h1 id="heading1">
                <p id="p1"> 이벤트 전파 확인 </p>
            </h1>
        </div>
    </div>

    <br><hr>
    브라우저 기본 처리 이벤트 <br>
    - 기본으로 처리되는 이벤트를 취소시켜야 하는 경우, HTMLEvent 객체의 preventDefault() 메서드를 사용한다. <br>
    <form id="searchForm" action="search.jsp">
        검색어 <input type="search" name="searchWord">
        <input type="submit" value="검색">
    </form> <!-- 이벤트를 별도로 구성하지 않아도 input에 입력된 값이 자동으로 URL에 QueryString으로 추가되어 전달된다. -->

    <a href="http://www.google.co.kr" id="link1" target="_blank">구글</a>
    <!-- 이벤트를 별도로 구성하지 않아도 자동으로 연결된 링크로 이동한다. -->
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 이벤트 예제 : 과일 선택하면 메세지창 띄우기(자체 구성)</title>
    <script>
        window.onload = function() {
            document.getElementById("input").onchange = function() {
                let selectFriuit = document.getElementById("friuits");
                if(selectFriuit.value != "") {
                    alert(`선택된 과일은 ${selectFriuit.value} 입니다`);
                }
            }
        }
    </script>
</head>
<body>
    <form id="input" action="#">
        <label for="friuits">과일</label>
        <select name="friuits" id="friuits">
          <option value="">선택하세요</option>
          <option value="apple">사과</option>
          <option value="banana">바나나</option>
          <option value="cherry">체리</option>
        </select>
      </form>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript 이벤트 예제 : 과일 선택하면 메세지창 띄우기(강사님 구성)</title>
</head>
<body>
    <h3>과일을 선택하세요</h3>
    <select id="fruitSelect">
        <option value="">-- 선택하세요 --</option>
        <option value="사과">사과</option>
        <option value="바나나">바나나</option>
        <option value="오렌지">오렌지</option>
        <option value="딸기">딸기</option>
    </select>
    <script>
        const fruitSelect = document.getElementById("fruitSelect");
        fruitSelect.addEventListener("change", function() {
            const selectedValue = this.value;
            if(selectedValue) {
                alert(selectedValue+"를 선택하였습니다");
            }
        }, false);
    </script>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>경품 추천기</title>
    <style>
		body{
			font-size:9pt;
		}
		#panel1{
			border:1px #000000 solid;
			line-height:400px;
			font-size:100px;
			width:400px;
			height:400px;
			text-align:center;
			vertical-align:middle;		
		}
	</style>
    <script>
        let panel ;
        let timerID;
        let totalNumber = 0;

        window.onload = function(){
            panel = document.getElementById("panel1");
            let startBtn  = document.getElementById("btn_Start");
            startBtn.onclick = function(){
               let totalNumber= Number(document.getElementById("lab_total").value);
               panel.style = "color:#000000";
               timerID = setInterval(()=>{
                   let num = Math.floor(Math.random()*totalNumber+1);
                   panel.innerHTML = num;
                   let fSize = Math.floor(Math.random()*200+100);
                   console.log(fSize);
                   panel.style = `font-size:${fSize}px`;
               }  , 20);
            }

            let stopBtn  = document.getElementById("btn_Stop");
            stopBtn.onclick = function(){
                if(timerID) {
                    clearInterval(timerID);
                    timerID =  0;
                    panel.setAttribute("style", "color:#ff0000;font-size:200px");
                }
            } 
        }
    </script>
</head>
<body>
    <div> 
	<h4>경품추첨기-ver 0.1</h4>
	<div id="panel1" > 	
	</div>

	<div id="nav">
		참여인원 : <input type="text" id="lab_total" value="100"></input>
		<button id="btn_Start">시작</button>
		<button id="btn_Stop">멈춤</button>
	</div>
   </div>
</body>
```

### load 이벤트
 - load이벤트는 html의 모든 요소가 메모리에 객체 트리로 로드가 완료되었을 때 동작한다.
 - /html 태그까지 모두 읽은 다음 메모리에 로드가 완료되었을 때 동작.
    ```javascript
    windows.onload = function() {
        window.alert('외부파일 main.js가 실행되었습니다');
    }
    ```


## JavaScript 브라우저 객체 모델(BOM, Browser Object Model) API
 - 대표적인 BOM 객체는 window 객체가 있다.
    - alert(), prompt(), confirm(), setInterval(), clearInterval(), open(), close, on이벤트명, document, navigator, location, screen, history....
        - 해당 대상들은 window의 객체이기 때문에 브라우저의 전역 객체가 된다.
            - 즉, window.screen이 아닌 screen 과 같이 사용 가능하다.
    - screen : 브라우저별로 화면 속성이 서로 다르기 때문에 운영체제와 관련 screen 속성 제공
    - location : html 페이지 이동, 새로고침등의 기능 제공(href 속성, assign(), reload(), replace, location=location), url관련 정보를 추출
    - history : 브라우저의 user가 방문했었던 페이지 목록 저장 및 이동 메소드를 제공한다. SPA(Single Page Application) 개발 시, 유용하다.
    - document : HTML의 요소를 검색, 변경 등의 구조를 동적으로 변경한다.
```html
<body>
    이미지 클릭 시, 새창에서 크게 열리도록 구성 <br>
    <img id="img" width="100px" height="100px" src="https://i.namu.wiki/i/0xUderHjxT52FIlpSpYXJEkENhNKU1uPFDbYYXsSFQM-I0SPIlrxM020ImXKUDp1D2rAYGtor-ZX9_fjTxV_-0khoz2HJNvoUa-MEnGRMWNmaVvwjc4tEYQwo1jOHKGBJ0WHVyNSBbEl1_7D2uIcPg.webp" alt="라이언">
    <script>
        let imgEL = document.getElementById("img")
        imgEL.addEventListener("click", function() {
            window.open('./image.html', "", "width=1000, height=1000", "_blank")
             // 새창은 image.html, 사이즈는 1000x1000
        }, false) 
    </script>
    <!-- image.html 내용
     <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <script>
            window.onload = function() {
                document.body.addEventListener("click", function() {
                    window.close() // body 클릭 시, 화면 닫힘
                }, false)
            }
        </script>
    </head>
    <body>
        <img src="https://i.namu.wiki/i/0xUderHjxT52FIlpSpYXJEkENhNKU1uPFDbYYXsSFQM-I0SPIlrxM020ImXKUDp1D2rAYGtor-ZX9_fjTxV_-0khoz2HJNvoUa-MEnGRMWNmaVvwjc4tEYQwo1jOHKGBJ0WHVyNSBbEl1_7D2uIcPg.webp" alt="라이언">
    </body>
    -->
</body>
```
```html
<body>
    screen 객체는 사용자의 화면과 관련된 정보를 제공하는 객체이다. <br>
    <script>
        console.log(screen);
        var nowWidth = screen.width;
        var nowHeight = screen.height;
        var nowAvailWidth = screen.availWidth;
        var nowAvailHeight = screen.availHeight;
        var nowColorDepth = screen.colorDepth;
        var nowPixelDepth = screen.pixelDepth;
        
        document.write("화면의 너비[screen.width] : " + nowWidth, "<br>");
        document.write("화면의 높이[screen.height] : " + nowHeight, "<br>");
        document.write("화면의 너비(작업표시줄 제외)[screen.availWidth] : " + nowAvailWidth, "<br>");
        document.write("화면의 높이(작업표시줄 제외)[screen.availHeight] : " + nowAvailHeight, "<br>");
        document.write("컬러 색상 수[screen.colorDepth] : " + nowColorDepth, "<br>");
        document.write("픽셀당 비트 수[screen.pixelDepth] : " + nowPixelDepth, "<br>");

        for(key in screen) {
            console.log("*", key, screen[key])
        }
    </script>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>페이지 새로고침할 때마다 배경색 변경 시키기</title>
    <script>
        function getColor() {
            const r = Math.floor(Math.random() * 255 + 1)
            const g = Math.floor(Math.random() * 255 + 1)
            const b = Math.floor(Math.random() * 255 + 1)
            return `rgb(${r}, ${g}, ${b})`
        }
        window.onload = function() {
            document.body.style.backgroundColor = getColor()
        }
        function changeColor() {
            location.href = location.href
        }
    </script>
</head>
<body>
    페이지 새로고침 방법 <br>
    1. location.href = location.href <br>
    2. location.reload() <br>
    3. location.assign(location.href) <br>
    4. location.replcae(location.href) <br>
    5. location = location <br>

    <button id="refresh" onclick="changeColor()">클릭하면 새로고침이 됩니다.</button>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>navigator 객체로 현재 위치 정보 받아오기</title>
    <script>
        function getLocation() {
            let pEL = document.getElementById("status")
            navigator.geolocation.getCurrentPosition((position) => {
                const latitude = position.coords.latitude
                const longitude = position.coords.longitude
                pEL.textContent = `위치 :  위도 ${latitude}, 경도 ${longitude}`
            }, (error) => {
                pEL.textContent = `에러 발생 : ${error.code}` // 에러 발생 시의 에러 내용 출력
                // 에러 상수들 error.PERMISSION_DENIDE, error.POSITION_UNAVAILABLE, error.TIMEOUT...
            }, {
                enableHighAccuracy: true, // 고도 정보 받아올 수 있도록 허용
                timeout: 10000, // 타임 아웃
                maximumAge: 0 // 유휴 시간
            })
        }
    </script>
</head>
<body>
    navigator 객체는 브라우저 정보 제공 <br>
    <script>
        console.log(navigator.cookieEnabled) // true (쿠키 활성화 여부)
        console.log(navigator.language) // ko-KR (언어 정보)
        console.log(navigator.onLine) // true (온라인 상태 여부)
        console.log(navigator.userAgent) // chrome 어쩌구저쩌구... (유저 정보)
    </script>
    navigator.geolocation 객체는 위치 정보(위도, 경도, 정화도, 고도, 속도, 방향 등등)를 제공한다. <br>
    - IP를 할당해주는 서버의 위치에 따라 데이터가 달라질 수 있어 위치 정보를 완전히 신뢰하진 못한다. <br>
      - 화성에 있는데 위치 정보는 용인으로 나온다든지... <br>
    - getCurrentPosition(), watchPosition(), clearWatch()... <br>

    <h2> 현재 위치 정보 </h2>
    <button onclick="getLocation()"> 위치 정보 가져오기 </button>
    <p id="status"></p>
</body>
```


## JavaScript HTML 객체 모델(DOM, Document Object Model) API
 - document 객체 특징
    - html 문서를 추상화하는 객체이다.
    - DOM tree에서 가장 먼저 생성되는 객체이다.
    - 요소를 선택하는 메서드
        - getElementById()
        - getElementsByTagName()
        - querySelector()
        - querySelectorAll()
    - 요소 생성하는 메서드
        - createElement()
            - 만들어진 객체는 아래와 같은 방법들로 추가 가능하다.
                - parent노드.appendChild()
                - 형제노드.append()
    - 요소를 변경하는 메서드
        - 속성 검색
            - element.getAttribute("속성")
        - 속성을 추가
            - element.속성 = value
            - element.setAttribute("속성", value)
        - 속성을 삭제
            - element.removeAttribute("속성")
    - 요소를 삭제하는 메서드
        - parent노드.removeChild("삭제할 노드")
        - 특정노드.remove()
 - DOM API는 html 문서에 요소 검색, 새로운 요소 추가, 요소 변경, 삭제, 속성 추가 등을 할 수 있다.
    - 즉, 동적으로 문서 구조를 변경할 수 있다.
 - DOM 요소에서 자주 사용하는 주요 속성들
    - innerHTML : HTML태그를 포함하는 내용을 설정
    - textContent : 태그의 내용으로 순수한 텍스트를 설정
    - value : input 태그, textarea 태그에서 사용자가 입력한 값이 저장되는 속성
    - className : 클래스 이름을 문자열로 반환 및 설정
    - classList : 클래스 속성의 값 목록
    - id
    - style
    - attributes
    - parentElement
    - child
    - children
    - nextElementSibling
    - previousElementSibling
    - firstElementChild
    - LastElementChild
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM API : 요소 검색</title>
</head>
<body>
    <pre>
    [HTML문서의 요소를 검색]
     - document.getElementById(id) : id 속성으로 element 객체를 검색, 1개만 반환
     - document.getElementsByTagName('HTML 태그이름') : 검색된 조건에 일치하는 모든 element를 배열과 유사한 HTMLCollection 으로 반환
     - document.getElementsByName(name) : name 속성으로 element 객체를 검색, 검색된 조건에 일치하는 모든 element를 배열과 유사한 HTMLCollection 으로 반환
     - document.getElementsByClassName(class) : class 속성으로 element 객체를 검색, 검색된 조건에 일치하는 모든 element를 배열과 유사한 HTMLCollection 으로 반환
     - document.querySelector('css의 selector 문법을 조건으로 활용') : (HTML5에서 추가)검색된 조건에 일치하는 element 중, 첫번째 검색된 1개만 반환
     - document.querySelectorAll('css의 selector 문법을 조건으로 활용') : (HTML5에서 추가)검색된 조건에 일치하는 모든 element를 배열과 유사한 HTMLCollection 으로 반환
    </pre>
    <hr>
    <ul class="menu">
        <li>Home</li>
        <li id="about">About</li>
        <li>Contact</li>
        <li>sitemap</li>
    </ul>
    <script>
        let item1 = document.querySelector('.menu li') // class=menu 아래에 모든 li 태그
        let items1 = document.querySelectorAll('.menu li') // class=menu 아래에 모든 li 태그
        let items2 = document.querySelectorAll('.menu > li') // class=menu 아래에 자식 li 태그
        console.log(item1) // Home 데이터를 가진 li 태그만 출력
        console.log(items1) // li 태그 전체 출력
        console.log(items2) // li 태그 전체 출력

        items1.forEach((item, index) => { // 요소들의 내용 출력
          console.log(`${index+1} :`, item.textContent);
       })
    </script>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM API : 요소 추가</title>
    <script>
        window.onload = function() {
            /* 방법1 */
            let h3El1 = document.createElement("h3");
            h3El1.textContent = '안녕하세요'

            /* 방법2 */
            let h3El2 = document.createElement("h3");
            let textNode = document.createTextNode("안녕하세요2")
            h3El2.appendChild(textNode)

            /* 방법3 */
            let h3El3 = document.createElement("h3")
            h3El3.innerHTML = "<mark><strong> 안녕하세요3 </strong></mark>"
            
            document.body.appendChild(h3El1)
            document.body.appendChild(h3El2)
            document.body.appendChild(h3El3)

            
            /* 방법1 */
            let imgEl1 = document.createElement("img")
            imgEl1.src = 'https://i.namu.wiki/i/0xUderHjxT52FIlpSpYXJEkENhNKU1uPFDbYYXsSFQM-I0SPIlrxM020ImXKUDp1D2rAYGtor-ZX9_fjTxV_-0khoz2HJNvoUa-MEnGRMWNmaVvwjc4tEYQwo1jOHKGBJ0WHVyNSBbEl1_7D2uIcPg.webp'
            imgEl1.width = '200'
            imgEl1.height = '200'

            /* 방법2 */
            let imgEl2 = document.createElement("img")
            imgEl2.setAttribute('src', 'https://i.namu.wiki/i/0xUderHjxT52FIlpSpYXJEkENhNKU1uPFDbYYXsSFQM-I0SPIlrxM020ImXKUDp1D2rAYGtor-ZX9_fjTxV_-0khoz2HJNvoUa-MEnGRMWNmaVvwjc4tEYQwo1jOHKGBJ0WHVyNSBbEl1_7D2uIcPg.webp')
            
            document.body.appendChild(imgEl1)
            document.body.appendChild(imgEl2)
        }
    </script>
</head>
<body>

</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM API : 버튼 클릭 시, 선택된 대상들 출력</title>
    <style type="text/css">
        td {
            border-style: solid;
            border-width: 1px;
            font-size: 200%;
        }

        #checkedResult {
            color: green;
            font-size: 200%;
        }
    </style>
    <script>
        window.onload = function() {
            let btnEl = document.getElementById("findChecked")
            btnEl.onclick = function() {
                let inputEls = document.querySelectorAll("input:checked") // input 태그의 checked 속성이 있는 대상들
                inputEls.forEach((item, index) => {
                    document.querySelector("#checkedResult").innerHTML += inputEls[index].name + ", "
                })
            }
        }
    </script>
</head>
<body>
    <section>
        <table>
            <tr>
                <td><input type="checkbox" name="A1">A1</td>
                <td><input type="checkbox" name="A2">A2</td>
                <td><input type="checkbox" name="A3">A3</td>
            </tr>
            <tr>
                <td><input type="checkbox" name="B1">B1</td>
                <td><input type="checkbox" checked name="B2">B2</td>
                <td><input type="checkbox" name="B3">B3</td>
            </tr>
            <tr>
                <td><input type="checkbox" name="C1">C1</td>
                <td><input type="checkbox" name="C2">C2</td>
                <td><input type="checkbox" name="C3">C3</td>
            </tr>
        </table>
        
        <div>Select various checkboxes, then hit the button to identify them using querySelectorAll("*:checked").</div>
        <button type="button" id="findChecked" autofocus>Find checked boxes</button>
        <div id="checkedResult"></div>
      </section>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM API : 키보드 엔터 시, 마우스 선택된(hover) 대상 출력</title>
    <style>
        td {
            border-style: solid;
            border-width: 1px;
            font-size: 300%;
        }

        td:hover {
            background-color: cyan;
        }

        #hoverResult {
            color: green;
            font-size: 200%;
        }
    </style>
    <script>
        window.onload = function() {
            var btnEl = document.querySelector('#findHover')
            btnEl.onclick = function() {
                var tdEl = document.querySelector("td:hover")
                document.querySelector("#hoverResult").innerHTML += tdEl.innerHTML
            }
        }
    </script>
</head>
<body>
    <section>
        <table>
            <tr>
                <td>A1</td>
                <td>A2</td>
                <td>A3</td>
            </tr>
            <tr>
                <td>B1</td>
                <td>B2</td>
                <td>B3</td>
            </tr>
            <tr>
                <td>C1</td>
                <td>C2</td>
                <td>C3</td>
            </tr>
        </table>
        <button type="button" id="findHover" autofocus>Find 'td:hover' target</button>
        <div id="hoverResult"></div>		
    </section>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM API : 여러가지 활용해보기(자체구성)</title>
    <style>
		body{
			font-size:9pt;
		
		}
		
		div{
			border: 1px solid #999999;
			margin:20px;
			margin-bottom:20px;
		}
		div div{
			border: 1px dotted #CCC;
			
		}
		
		.active{
			font-size:20pt;
			color:#090;
			border:5px solid #ff0000;
		}
	</style>
    <script>
        window.onload = function() {
            let divM1El = document.getElementById("m_1")
            divM1El.style.color = 'red'

            let divM2El = document.querySelector("#m_2")
            divM2El.className = "active"

            let divM3El = document.querySelector("#m_3")
            let divM3ChildEl = divM3El.lastElementChild
            divM3El.removeChild(divM3ChildEl)
            let imgEl = document.createElement("img")
            imgEl.setAttribute("src", "https://i.namu.wiki/i/uVfvrrdFdovVGY2KqvW0S3cgurcNpVLtXkM6kjp22wE4QvCmRV1BlZtNSgTMn3XDJk1cnDDSACmGwS2gq5iv6ItS1I0nrl_gWuVrYqa0Yip_SzFXc5iVPSONyf32Pt9eOfcRvQ1lsXnINlQJtcT05g.webp")
            divM3El.appendChild(imgEl)

            let divM4El = document.querySelector("#m_4")
            let pEl = document.createElement("p")
            pEl.textContent = "항목4"
            divM4El.appendChild(pEl)

            let divM5El = document.querySelector("#m_5")
            let pEls = document.querySelectorAll("#m_5 > p") // m_5 자식인 p 태그 찾기
            pEls.forEach((item, index) => {
                if(item.textContent.includes("항목4")) {
                    item.remove()
                }
            })

            let divM6El = document.querySelector("#m_6")
            let divM6ParentEl = divM6El.parentElement
            divM6ParentEl.remove()
        }
    </script>
</head>
<body>
    <div> 
		<h4>테스트1</h4>
		<div id="m_1">
			#m_1 : 글자색을 빨간색으로 변경해주세요.
		</div>
	</div>
	<div> 
		<h4>테스트2</h4>
		<div id="m_2">
			#m_2 : 클래스 active를 적용시켜 주세요.
		</div>
	</div>
	<div> 
		<h4>테스트3</h4>
		<div id="m_3">
			#m_3 : 에고 이 이미지가 아닌데... 이미지를 춘식이로 변경해주세요"<br>
			<img src="https://i.namu.wiki/i/0xUderHjxT52FIlpSpYXJEkENhNKU1uPFDbYYXsSFQM-I0SPIlrxM020ImXKUDp1D2rAYGtor-ZX9_fjTxV_-0khoz2HJNvoUa-MEnGRMWNmaVvwjc4tEYQwo1jOHKGBJ0WHVyNSBbEl1_7D2uIcPg.webp">
		</div>
	</div>
	<div> 
		<h4>테스트4</h4>
		<div id="m_4">
			#m_ 4 :  홋! 항목4까지 있어야 하는건데, 바쁜나머지 실수를 했군요. 항목4를 제일 뒤에 추가해주시겠어요?
			<p>
				항목1
			</p>
			<p>
				항목2
			</p>
			<p>
				항목3
			</p>
		</div>
	</div>
	<div> 
		<h4>테스트5</h4>
		<div id="m_5">
			#m_ 5 :  이번에는 항목4가 더 추가되었네요. 즉시 삭제해주세요.
			<p>
				항목1
			</p>
			<p>
				항목4
			</p>
			<p>
				항목2
			</p>
		</div>
	</div>
	<div> 
		<h4>테스트6</h4>
		<div id="m_6">
			#m_ 6 : 이런이런! 이 부분은 전혀 필요없는 내용들인데 왜 있는거죠? #m_6부터 헤더태그까지 모두 삭제해주세요.
			<p>
				DOM(Document Object Model)이란?<br>
				웹페이지 문서를 조작하기 위해서 지켜야될 약속(interface)만 딸랑 적혀있는 문서랍니다.
				약속만 있을뿐 내부는 텅빈 상자랍니다.
				우리가 알고있는 W3C DOM에는 구현소스가 한줄도 존재하지 않습니다.
				그럼 실제 구현소스는??
			</p>
		</div>
	</div>
</body>
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM API : 여러가지 활용해보기(강사님 구성)</title>
    <style>
		body{
			font-size:9pt;
		
		}
		
		div{
			border: 1px solid #999999;
			margin:20px;
			margin-bottom:20px;
		}
		div div{
			border: 1px dotted #CCC;
			
		}
		
		.active{
			font-size:20pt;
			color:#090;
			border:5px solid #ff0000;
		}
	</style>
    <script>
        window.onload = function() {
            let div1 = document.querySelector("#m_1")
            div1.setAttribute("style", "color:red")

            let div2 = document.querySelector("#m_2")
            div2.setAttribute("class", "active")

            let div3 = document.querySelector("#m_3")
            let image = div3.querySelector("img")
            image.setAttribute("src", "https://i.namu.wiki/i/uVfvrrdFdovVGY2KqvW0S3cgurcNpVLtXkM6kjp22wE4QvCmRV1BlZtNSgTMn3XDJk1cnDDSACmGwS2gq5iv6ItS1I0nrl_gWuVrYqa0Yip_SzFXc5iVPSONyf32Pt9eOfcRvQ1lsXnINlQJtcT05g.webp")

            let div4 = document.querySelector("#m_4")
            let p = document.createElement("p")
            p.textContent = "항목4"
            div4.appendChild(p)

            let div5 = document.querySelector("#m_5")
            let ps = div5.querySelectorAll("p")
            ps.forEach((item, index) => {
                if(item.textContent.trim() == "항목4") {
                    div5.removeChild(item)
                }
            })

            let div6 = document.querySelector("#m_6")
            document.body.removeChild(div6.parentNode)
        }
    </script>
</head>
<body>
    <div> 
		<h4>테스트1</h4>
		<div id="m_1">
			#m_1 : 글자색을 빨간색으로 변경해주세요.
		</div>
	</div>
	<div> 
		<h4>테스트2</h4>
		<div id="m_2">
			#m_2 : 클래스 active를 적용시켜 주세요.
		</div>
	</div>
	<div> 
		<h4>테스트3</h4>
		<div id="m_3">
			#m_3 : 에고 이 이미지가 아닌데... 이미지를 춘식이로 변경해주세요"<br>
			<img src="https://i.namu.wiki/i/0xUderHjxT52FIlpSpYXJEkENhNKU1uPFDbYYXsSFQM-I0SPIlrxM020ImXKUDp1D2rAYGtor-ZX9_fjTxV_-0khoz2HJNvoUa-MEnGRMWNmaVvwjc4tEYQwo1jOHKGBJ0WHVyNSBbEl1_7D2uIcPg.webp">
		</div>
	</div>
	<div> 
		<h4>테스트4</h4>
		<div id="m_4">
			#m_ 4 :  홋! 항목4까지 있어야 하는건데, 바쁜나머지 실수를 했군요. 항목4를 제일 뒤에 추가해주시겠어요?
			<p>
				항목1
			</p>
			<p>
				항목2
			</p>
			<p>
				항목3
			</p>
		</div>
	</div>
	<div> 
		<h4>테스트5</h4>
		<div id="m_5">
			#m_ 5 :  이번에는 항목4가 더 추가되었네요. 즉시 삭제해주세요.
			<p>
				항목1
			</p>
			<p>
				항목4
			</p>
			<p>
				항목2
			</p>
		</div>
	</div>
	<div> 
		<h4>테스트6</h4>
		<div id="m_6">
			#m_ 6 : 이런이런! 이 부분은 전혀 필요없는 내용들인데 왜 있는거죠? #m_6부터 헤더태그까지 모두 삭제해주세요.
			<p>
				DOM(Document Object Model)이란?<br>
				웹페이지 문서를 조작하기 위해서 지켜야될 약속(interface)만 딸랑 적혀있는 문서랍니다.
				약속만 있을뿐 내부는 텅빈 상자랍니다.
				우리가 알고있는 W3C DOM에는 구현소스가 한줄도 존재하지 않습니다.
				그럼 실제 구현소스는??
			</p>
		</div>
	</div>
</body>
```


## JavaScript 예외처리
 - Error 객체의 주요 속성
    - name : 오류 이름(Reference Error, Type Error...)
    - message : 오류 메시지
    - stack : 오류가 발생된 코드 위치
```html
<body>
    <pre>
        try { 오류가 발생할 수 있는 코드 }
        catch { 오류가 발생했을 때 오류 처리 코드 }
        finally { 오류 처리와 상관없이 리소스들 정리 }
        throw { 오류를 발생시킬 때 사용 }
    </pre>
    <script>
        try {
            console.log(test) // Reference Error. (없는 변수를 호출)
        } catch (err) { // Error 객체를 받는다.
            console.log(err.message) // test is not defined.
        } finally {
            console.log("예외가 발생하지 않아도 항상 실행됩니다.")
        }
    </script>

    사용자 정의 예외 발생 <br>
    <script>
        function devide(a, b) {
            if (b === 0) {
                throw new Error("0으로 나눌 수 없습니다.")
            }
            return a/b
        }
        console.log(devide(5, 2))

        try {
            console.log(devide(5, 0))
        } catch (error) {
            console.log(error.message)
        }
    </script>

    Java에서는 catch에서 타입별로 여러개 사용 가능하나, JavaScript는 하나만 사용한다. (타입을 선언안하기도 하고..) <br>
    오류 유형별 처리 하려면? catch 블럭내부에서 instanceof 타입 비교 조건문 <br>
    <script>
        try {
             JSON.parse("{ invalid json }"); // JSON 문법 오류 발생
        } catch (error) {
            if (error instanceof SyntaxError) {
                console.log("JSON 문법 오류:", error.message);
            } else if (error instanceof ReferenceError) {
                console.log("정의되지 않은 변수:", error.message);
            } else {
                console.log("기타 오류:", error.message);
            }
        }
    </script>

    기본 Error 객체를 확장하여 사용자 정의 예외(Custom Error)를 만들 수도 있습니다. <br>
    <script>
        class CustomError extends Error {
            constructor(message) {
                super(message)
                this.name = "CustomError"
            }
        }

        function riskyOperation(value) {
            if (value < 0) {
                throw new CustomError("음수 값은 허용되지 않습니다.")
            }
            return Math.sqrt(value)
        }

        try {
            console.log(riskyOperation(-5))
        } catch (e) {
            console.log(`${e.name} : ${e.message}`) // CustomError : 음수 값은 허용되지 않습니다.
        }
    </script>
</body>
```


## Ajax(Asynchronous JavaScript And XML)
 - 서버에 요청과 응답을 비동기 처리하는 XMLHttpRequest를 활용한다.
 - 기본 환경(BackEnd) 구성 필요 (강의 환경일 뿐이라 꼭 중요하지 않음)
    - Java 17 (jdk-17)
        - JAVA_HOME 환경변수까지 지정
    - Tomcat 11 (https://tomcat.apache.org/)
        - 압축파일로 받기
        - bin 디렉터리 안에 startup.bat을 cmd에서 실행
            - tomcat cmd가 열림과 tomcat 서버가 시작됨.
            - 실행된 tomcat cmd 종료 시, tomcat 서버가 종료됨.
    - DataBase 구성 x
        - ID : admin / PW : 1234 이면 성공. 그 이외에는 Exception 발생하도록 구성.
    - 정상 실행 완료 시, http://localhost:8080/ 정상 접속 됨.
        - 포트 번호 변경 필요 시, conf 폴더에서 server.xml의 내용 수정하면 됨.
 - 예제-1) 로그인 페이지를 만들고 Ajax로 로그인 시도 진행. ID : admin / pw : 1234 가 아닐경우에 Exception 처리 진행.
    - 로그인 요청을 수동으로 TEST 해보고자 하면 JSP 파일을 이용해보면 된다.
        - 주소 : http://localhost:8080/loginProc.jsp?userid=admin&userpwd=1234
        - 요청을 QueryString을 직접 만들어서 진행.
        - ID/PW 각각 바꿔서도 보내보기
    - 작성한 파일들은 "tomcat 폴더 -> webapps -> ROOT 폴더"에 넣어야 동작함.
        - 웹 접속 : http://localhost:8080/partPage.html
    - 참고로 아래 HTML/CSS/JS를 vscode의 Live Server을 통해서 열고 TEST하면 CORS 에러가 발생한다.
        - vscode 와 Tomcat 2개의 웹 서버가 구성되어 있는 상태가 되고, vscode 웹 서버에서 Tomcat 서버에 리소스(GET요청)을 보내려는 상태가 되기 때문이다.
    ```jsp
    <!-- loginProc.jsp -->
    <%@ page   contentType="text/xml; charset=utf-8"     %>
    <%
        request.setCharacterEncoding("utf-8"); 
        response.setContentType("text/xml;charset=utf-8");

        String id = request.getParameter("userid"); 
        String passwd = request.getParameter("userpwd");

        String outString = "";
        int result = 0 ;

        if(id.equals("admin")&&passwd.equals("1234")){
            result = 1;  //로그인 성공
        }else if(id.equals("admin")){
            result = 0;  //패스워드 불일치 
        }else{
        result = 2; //아이디 존재하지 않음
        }

        if(result==1){
        outString="<response><result>"+ result + "</result><id>"+ id 
                    +"</id></response>";
    }else if(result==0){
        outString="<response><result>"+ result + "</result><id>"+ id 
            +"</id></response>";
    }else{
        outString="<response><result>"+ result + "</result><id>"+ id 
            +"</id></response>";
    }  
    out.println(outString);
    %>
    ```
    ```html
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>로그인 페이지</title>
        <link rel="stylesheet" href="partPage.css" type="text/css" />
        <script type="text/javascript" src="partPage.js" charset="UTF-8"></script>
    </head>
    <body>
        <!-- partPage.html -->
        <h3>부분페이지 동적 갱신</h3>
        <table border="1">
        <tr><td colspan="2" align="center"><font size=15><b>우리회사</b></font></td></tr>
        <tr>
            <td><form action="#">
                <div id="confirmed">
                    <table>
                        <tr>
                        <td>아이디</td>
                        <td><input type="text" id="userid" name="userid" size="15" maxlength="12"/></td>
                        </tr>
                        <tr>
                        <td>비밀번호</td>
                        <td><input type="password" id="userpwd" name="userpwd" size="15" maxlength="12"/></td>
                        </tr>
                        <tr><td colspan="2" align="center">
                            <input type="button" id="login" value="로그인"  /></td>
                        </tr>
                    </table>
                </div>
                </form>
            </td>
            <td width="400"><img src="https://i.namu.wiki/i/uVfvrrdFdovVGY2KqvW0S3cgurcNpVLtXkM6kjp22wE4QvCmRV1BlZtNSgTMn3XDJk1cnDDSACmGwS2gq5iv6ItS1I0nrl_gWuVrYqa0Yip_SzFXc5iVPSONyf32Pt9eOfcRvQ1lsXnINlQJtcT05g.webp"></td>
        </tr>
        <tr><td colspan="2" align="center">찾아오시는길 |회사소개|정보보호정책</td></tr>
        </table>
    </body>
    ```
    ```css
    /* partPage.css */
    div#confirmed{
    width            : 250px;
    height           : 100px;
    background-color : #e0ffff;
    border-color     : #b0e0e6;
    border-style     : dotted;
    }
    ```
    ```javascript
    /* partPage.js */
    let xhr
    window.onload = function() {
        xhr = new XMLHttpRequest()

        let loginBtn = document.getElementById("login")
        loginBtn.onclick = function() {
            let uid = document.getElementById("userid").value
            let upwd = document.getElementById("userpwd").value
            let url = "http://localhost:8080/loginProc.jsp?userid=" + uid + "&userpwd=" + upwd
            
            xhr.onreadystatechange = resultProcess // 응답을 처리하는 콜백 함수
            xhr.open("GET", url, true) // true = 비동기 여부로 보내도록 지정.
            xhr.setRequestHeader("Content-type", "application/x-www-form-urlencoded")
            xhr.send(null) // 서버로 요청 전송(send에 매개변수를 넣는 경우는 POST 요청이기 때문에 null 지정)
        }
    }

    function resultProcess() {
        if(xhr.readyState == 4 && xhr.status == 200) {
            let resultCode = xhr.responseXML.getElementsByTagName("result")[0].firstChild.data
            let name = xhr.responseXML.getElementsByTagName("id")[0].firstChild.data

            if(resultCode == 1) { // 사용자 인증 성공
                let str = "<table><tr><td align='center'><b>"+ name + "</b> 님 어서오세요..</td></tr>"
                str+="<tr><td align='center'><input type='button' id='logout' value='로그아웃' />"
                str+="</td></tr></table>"
                document.getElementById("confirmed").innerHTML = str
                // 로그인 박스를 제거 및 사용자 정보로 채우기
            } else if (resultCode == 0) {
                alert("비밀번호가 맞지 않습니다.\n다시 입력해 주시기 바랍니다.")
                document.getElementById("userid").value = name
                document.getElementById("userpwd").value = ""
                document.getElementById("userpwd").focus()
                // 아이디는 유지, 비밀번호만 공백으로 바꾸고 비밀번호에 마우스 커서가 올라가도록 구성
            } else {
                alert("아이디가 맞지 않습니다.\n다시 입력해 주시기 바랍니다.")
                document.getElementById("userid").value = ""
                document.getElementById("userpwd").value = ""
                document.getElementById("userid").focus()
                // 아이디, 비밀번호 모두 공백으로 바꾸고 아이디에 마우스 커서가 올라가도록 구성
            }
        }
    }
    ```
 - 예제-2) 버튼을 클릭하면 비동기 요청 (GET) imageProc.jsp 에서 이미지 3개를 JSON객체로 응답
    - 웹 접속 : http://localhost:8080/image.html
    - 이미지 리스트 목록 확인 : http://localhost:8080/imageProc.jsp
    ```jsp
    <!-- imageProc.jsp -->
    <%@ page contentType="application/json; charset=utf-8" %>
    <%
        String[] imageFiles = {
            "https://i.namu.wiki/i/0xUderHjxT52FIlpSpYXJEkENhNKU1uPFDbYYXsSFQM-I0SPIlrxM020ImXKUDp1D2rAYGtor-ZX9_fjTxV_-0khoz2HJNvoUa-MEnGRMWNmaVvwjc4tEYQwo1jOHKGBJ0WHVyNSBbEl1_7D2uIcPg.webp",
            "https://i.namu.wiki/i/uVfvrrdFdovVGY2KqvW0S3cgurcNpVLtXkM6kjp22wE4QvCmRV1BlZtNSgTMn3XDJk1cnDDSACmGwS2gq5iv6ItS1I0nrl_gWuVrYqa0Yip_SzFXc5iVPSONyf32Pt9eOfcRvQ1lsXnINlQJtcT05g.webp",
            "https://i.namu.wiki/i/41FABs74HgkrPCPzaIAPpmB_koPYG_3TE8GNeShK5uqjaqzOZ3KNnmkvR_VdSlv4F6sgxkJEl2WuY3-7p7vmSuAdFHhYHk-yACEGihEMU5VxdZ47VwOrxbe0Q99PBvovuue9QEMDhKEQE4YlZDmn1A.webp"
        };
        StringBuffer json = new StringBuffer();
        json.append("{\"images\":[");
        for(int i=0; i<imageFiles.length; i++) {
            json.append("\"").append(imageFiles[i]).append("\"");
            if(i<imageFiles.length-1) {
                json.append(",");
            }
        }
        json.append("]}");
        out.print(json.toString());
    %>
    ```
    ```html
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <style>
            .image_panel{
                border:1px solid #eeeeee;
                text-align:center;
                margin:5px;
            }
            .image_panel .title{
                font-size:9pt;
                color:#ff0000;
            }
        </style>
        <script type="text/javascript" src="./image.js" charset="UTF-8"></script>
    </head>
    <body>
        <!-- image.html -->
        <div>
            <button id="loadImage">이미지 정보 읽어들이기</button>
        </div>
        <div id="image_container">
            <!--여기에 가져온 이미지를 DOM API를 사용해서 추가함-->
        </div>
    </body>
    ```
    ```javascript
    /* image.js */
    window.onload = function() {
        const btn = document.getElementById("loadImage")
        btn.onclick = function() {
            const xhr = new XMLHttpRequest()
            const url = "http://localhost:8080/imageProc.jsp"

            xhr.open("GET", url, true)
            xhr.onreadystatechange = function() {
                if(xhr.readyState === 4 && xhr.status == 200) {
                    const container = document.getElementById("image_container")
                    try {
                        const imageList = JSON.parse(xhr.responseText)
                        
                        imageArray = imageList.images
                        imageArray.forEach((image, idx) => {
                            const img = document.createElement("img")
                            img.src = image
                            container.appendChild(img)
                        })
                    } catch(error) {
                        container.textContent = error.message
                    }
                }
            }
            xhr.send();
        }
    }
    ```


## Promise, async/await
 - Promise는 콜백 함수의 콜백 헬을 해결하기 위해서 기능이 추가되었다.
 - asnyc/await은 Promise 문법을 간단하게 작성할 수 있도록 만들어졌다.
    - async는 function 앞에 위치하는데, 해당 함수는 항상 Promise 객체를 반환하도록 의미하게 된다.
    ```html
    <body>
        <script>
            async function f1() {
                return 1;
            }
            f1().then(alert);
        </script>
    </body>
    ```
    - await은 Promise가 처리될 때까지(=비동기 함수가 종료될 때까지) 기다린다.
    - await은 async 함수 안에서만 동작한다.
    ```html
    <body>
        <script>
            async function f() {
                let promise = new Promise((resolve, reject) => {
                setTimeout(() => resolve("완료!"), 1000)
                });
            let result = await promise; // 프라미스가 이행될 때까지 기다린 후, 결과값을 result에 저장
            alert(result); // "완료!"
            }
            f();
        </script>
    </body>
    ```
 - 예제) 비동기 작업으로 file1.txt 읽어서 result.txt 파일 기록 후, file2.txt 읽어서 result.txt에 append, file3.txt 읽어서 result.txt에 append
    - 코드 실행은 Node.js 활용 ([실행 방법 참고](#기타---nodejs에서-javascript-실행-하기))
    ```javascript
    /* async01.js
     * 일반적인 콜백 함수 사용 (콜백 헬 예제)
     * 읽고 - 쓰기 - 읽고 - 엎어쓰기 - 읽고 - 엎어쓰기 로 총 6번의 비동기 작업이 이뤄진다. */

    const fs = require('fs');

    fs.readFile('file1.txt', 'utf8', (err, data1) => {
        if(err) {
            return console.error("Error reading file1.txt :", err)
        }
        fs.writeFile('result.txt', data1, (err)=>{
            if(err) {
                return console.error("Error write result.txt :", err)
            }
            fs.readFile('file2.txt', 'utf8', (err, data2) => {
                if(err) {
                    return console.error("Error reading file2.txt :", err)
                }
                fs.appendFile('result.txt', '\n' + data2, (err)=>{
                    if(err) {
                        return console.error("Error appending to result.txt :", err)
                    }
                    fs.readFile('file3.txt', 'utf8', (err, data3) => {
                        if(err) {
                            return console.error("Error reading file3.txt :", err)
                        }
                        fs.appendFile('result.txt', '\n' + data3, (err)=>{
                            if(err) {
                                return console.error("Error appending to result.txt :", err)
                            }
                            console.log('All files have been successfully merged into result.txt')
                        })
                    })   
                })
            })        
        })
    })
    ```
    ```javascript
    /* async02.js
     * async01.js 를 Promise로 Refactoring */

    const fs = require('fs').promises;
    // 콜백 기반 비동기 함수가 Promise 객체를 반환해서 Promise의 API를 사용할 수 있도록 해주는 서브 모듈이 추가됨.

    fs.readFile('file1.txt', 'utf8')
        .then(data1 => {
            return fs.writeFile('result.txt', data1).then(() => data1)
        })
        .then(() => fs.readFile('file2.txt', 'utf8'))
        .then(data2 => {
            return fs.appendFile('result.txt', '\n' + data2).then(() => data2)
        })
        .then(() => fs.readFile('file3.txt', 'utf8'))
        .then(data3 => {
            return fs.appendFile('result.txt', '\n' + data3).then(() => data3)
        })
        .then(() => console.log('All files have been successfully merged into result.txt'))
        .catch(err => console.log('Error:', err))
    /* 각 then 마다 Promise 객체가 반환되며, 반환될 때마다 상태가 Fullfilled 혹은 Reject의 상태가 반환된다.
     * 그 상태에 따라 JavaScript 엔진이 다음 then을 실행시킬지? catch를 실행시킬지? 판단한다 */
    ```
    ```javascript
    /* async03.js
     * async01.js, async02.js 를 async/await 으로 Refactoring */

    const fs = require('fs').promises;

    async function mergeFiles() {
        try {
            const data1 = await fs.readFile('file1.txt', 'utf8') // file1.txt를 읽을 때까지 기다렸다가 결과를 data1에 저장.
            await fs.writeFile('result.txt', data1) // result.txt에 쓸 때까지 기다렸다가 다음 문장 실행.

            const data2 = await fs.readFile('file2.txt', 'utf8')
            await fs.appendFile('result.txt', '\n' + data2)

            const data3 = await fs.readFile('file3.txt', 'utf8')
            await fs.appendFile('result.txt', '\n' + data3)

            console.log('All files have been successfully merged into result.txt')
        } catch (err) {
            console.error("Error:", err)
        }
    }
    mergeFiles();
    ```

### Fetch API
 - XMLHttpRequest 대체로 등장, 비동기 HTTP 요청을 보내기 위한 표준 API
 - Promise 타입의 객체를 반환한다.
 - 예제) Ajax에서 구성한 내용을 fetch API로 변경
    ```javascript
    /* image.js */
    window.onload = function() {
        const btn = document.getElementById("loadImage")
        btn.onclick = async function() {
            const container = document.getElementById("image_container")
            try {
                const response = await fetch("http://localhost:8080/imageProc.jsp")
                 // fetch() 함수가 반환한 객체는 Response 객체이다. (그 객체를 response 변수에 저장한 것이다.)
                if(!response.ok) {
                    throw new Error(`HTTP error! status: ${response.status}`)
                }
                const imageList = await response.json()
                 // 응답 body를 JSON으로 파싱한다. (비동기 객체로 Promise를 반환한다.)
                
                const imageArray = imageList.images;
                imageArray.forEach(image => {
                    const img = document.createElement("img")
                    img.src = image
                    container.appendChild(img)
                })
            } catch(err) {
                container.textContent = err.message
            }
        }
    }
    ```
    ```javascript
    /* partPage.js */
    window.onload = function() {
        const loginBtn = document.getElementById("login")
        loginBtn.onclick = async function() {
            let uid = document.getElementById("userid").value
            let upwd = document.getElementById("userpwd").value
            let url = "http://localhost:8080/loginProc.jsp?userid=" + uid + "&userpwd=" + upwd
            try {
                const response = await fetch(url, {
                    method: "GET",
                    headers: {
                        "Content-type": "application/x-www-form-urlencoded"
                    }
                })
        
                if(!response.ok) {
                    throw new Error(`HTTP error! status: ${response.status}`)
                }
        
                const text = await response.text()
                 // XML를 응답받는다.
                 // Response 객체에는 XML 응답을 파싱하는 메서드가 없으므로 text로 받아서 DOMParser를 이용해서 XML로 변환해야 한다.
                const parser = new DOMParser()
                const xmlDoc = parser.parseFromString(text, "application/xml")
                resultProcess(xmlDoc)
            } catch(error) {
                alert("로그인 요청 중 요류 발생: " + error.message)
            }
        }
    }

    function resultProcess(responseXML) {
        let resultCode = responseXML.getElementsByTagName("result")[0].firstChild.data
        let name = responseXML.getElementsByTagName("id")[0].firstChild.data
        if(resultCode == 1) {
            let str = "<table><tr><td align='center'><b>"+ name + "</b> 님 어서오세요..</td></tr>"
            str+="<tr><td align='center'><input type='button' id='logout' value='로그아웃' />"
            str+="</td></tr></table>"
            document.getElementById("confirmed").innerHTML = str
        } else if (resultCode == 0) {
            alert("비밀번호가 맞지 않습니다.\n다시 입력해 주시기 바랍니다.")
            document.getElementById("userid").value = name
            document.getElementById("userpwd").value = ""
            document.getElementById("userpwd").focus()
        } else {
            alert("아이디가 맞지 않습니다.\n다시 입력해 주시기 바랍니다.")
            document.getElementById("userid").value = ""
            document.getElementById("userpwd").value = ""
            document.getElementById("userid").focus()
        }
    }
    ```


## 기타 - Node.js에서 JavaScript 실행 하기
 - node.js에서는 만들어진 JavaScript 파일을 읽어 코드 실행을 진행한다.
    ```javascript
    const readline = require('readline');

    const rl = readline.createInterface({
        input: process.stdin,
        output: process.stdout
    });

    // r1.question('message', successCallback)는 비동기 함수이다.
    rl.question('What is your name?', (answer) => {
        console.log(`안녕하세요. ${answer} 님`);
        rl.close();
    });
    ```
    ```cmd
    cmd> node main.js
    ```


## cors (cross origin resource sharing) : 웹의 기본 보안 정책
 - 통신 중인 웹 서버(A서버) 외에 다른 웹 서버(B서버) 또는 다른 도메인(C도메인)에 HTML 페이지와 기타 리소스들을 공유할 수 없다.
    - 기본적으로 A서버에서 받은 리소스를 B서버에 공유할 수 없다.
    - A서버에서 서비스 해주는 웹 페이지에서 B서버의 리소스에 대한 접근이 제한된다.
        - A서버에서 GET으로 데이터를 받았는데, 그 결과를 B서버에 POST 보내는 등등..
        - 즉, 자신이 통신중인 서버 외에 다른 서버와의 통신을 할 수 없다는 말이기도 하다.
 - origin : **프로토콜 + 도메인 + 포트**를 의미 (ex. http://www.test.com:8080)


## 기타 - 참고 사이트
 - [W3C 가이드 사이트](https://www.w3schools.com/)


## 기타 - 개발 TOOL
 - 개발 TOOL : vscode 활용
 - 사용 plugin
    - Live Server : Tomcat과 같은 환경 필요없이 vscode에서 자체적으로 웹서버 open
    - Prettier : 소스 코드 색상 구분
    - Korean Language Pack : vscode 한글화
    - vscode-pdf : vscode에 pdf reader 설치


