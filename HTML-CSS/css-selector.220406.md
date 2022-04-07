2022.04.06

CSS 선택자

[##_Image|kage@vliIB/btryyfY3epn/Zh4D2RuNeV5n1MEATuoWS1/img.png|CDM|1.3|{"originWidth":981,"originHeight":274,"style":"alignCenter","filename":"{ color red; padding 5px;.png"}_##]

1. 전체 선택자(universal)
	에스터리스크(*)는 페이지에 있는 전체 요소를 대상으로 함
    ```
    * { 
    margin: 0; 
    padding: 0; 
    text-decoration: none; 
    } 
    # ul아래 자식 선택자에게 도사용 가능 
    ul * { 
    color: tomato; 
    }
    ```
2. 아이디 선택자(id)
	샵(#)은 id를 대상으로 함. id선택자는 유연성이 없어서 재활용 불가
    ```
    #id {
    	width: 300px;
    }
    ```
3. 클래스 선택자(class)
	닷(.)은 class 선택자. 여러개의 요소를 대상으로 정할 수 있음
    ```
    .class {
    	color: aqua;
    }
    ```
4. 타입 선택자(type)
	element(요소)를 선택자로 하는 것
    body, p, span, h1, ol, header등......
    ```
    p {
    	font-size: 16px;
    }
    span {
    	color: tomato;
    }
    ```
5. 하위 선택자(descendant)
	하위 선택자는 공백으로 분리된 두개 이상의 선택자들로 만들어짐
    body안에 있는 span태그 모두 선택됨
    ```
    # html문서
    	<body>
          <span>tomato1</span>
          <div>
            <span>tomato2</span>
          </div>
          <span>tomato3</span>
        </body>
    ```
    ```
    # css문서
    	body span {
        	color: tomato;
        }
    ```
6. 자식 선택자(child)
	'>'로 분리된 두개 이산의 선택자들로 만들어짐
    1depth아래의 자식들만 선택됨
    ```
    # html문서
    <body>
      <span>tomato1</span>
      <div>
        <span>tomato2</span>
      </div>
      <span>tomato3</span>
    </body>
    ```
    ```
    # css문서
    body > span {
      color: aqua;
    }	
    ```
7. 인접 형제 선택자(adjacent sibling)
	'+'를 사용. 둘 다 같은 부모를 가지고 바로 뒤에 오는 요소에 적용됨
    tomato3가 color: tomato;가 적용됨
    ```
    # html문서
    <body>
      <span>tomato1</span>
      <div>
        <span>tomato2</span>
      </div>
      <span>tomato3</span>
      <span>tomato4</span>
      <span>tomato5</span>
    </body>
    ```
    ```
    # css 문서
      div + span {
        color: tomato;
      }
    ```
8. 일반 형제 선택자(general sibling)
	'~(틸드)'를 사용. 둘 다 같은 부모를 가지고 바로 뒤에 오는 모든 요소에 적용됨
    tomato3,tomato4,tomato5에 color: tomato;가 적용됨
    ```
    # html문서
    <body>
      <span>tomato1</span>
      <div>
        <span>tomato2</span>
      </div>
      <span>tomato3</span>
      <span>tomato4</span>
      <span>tomato5</span>
    </body>
    ```
    ```
    # css 문서
      div + span {
        color: tomato;
      }
    ```
9. 속성 선택자 (attribute)
	속성 선택자를 사용하면 특정 속성이나 특정 속성값을 가지고 있는 html요소를 선택할 수 있음
	```
    *속성만 있는 경우
    * selector[attribute]
    # html문서
    <body>
      <span chagne>tomato1</span>
      <div>
        <span>tomato2</span>
      </div>
      <span>tomato3</span>
    </body>
    ```
	```
    span[chagne] {
       background: black;
       color: tomato;
      }
    ```
    ```
    *속성에 값을 지정할 경우
	*selector[attribute value]
    # html문서
    <body>
      <span chagne>tomato1</span>
      <span chagne="banana" >tomato2</span>
      <span chagne>tomato3</span>
      <div>
        <span>tomato4</span>
      </div>
      <span>tomato5</span>
    </body>
    ```
	```
    span[chagne="banana"] {
      background: black;
      color: yellow;
    }
	```    
10. 가상 클래스(pseudo class)
	가상 클래스는 스타일이 적용되는 대상이 요소나 속성, 속성값에 따라 분류되는게 아니라 '상황'에 따라 분류된다
    
    * :first-child
    	ul에 첫번째 li에만 color가 적용됨
	```
    <body>
      <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
      </ul>
    </body>
    ```
    ```
    ul > li:first-child {
      color: cadetblue;
    }
    ```
    * :last-child
    	ul에 마지막 li에만 color가 적용됨
	```
    <body>
      <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
      </ul>
    </body>
    ```
    ```
    ul > li:last-child {
      color: cadetblue;
    }
    ```
    * :nth-child(n)
    	ul에 마지막 3번째에 color가 적용됨
	```
    <body>
      <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
      </ul>
    </body>
    ```
    ```
    ul > li:nth-child(3) {
      color: cadetblue;
    }
    ```
    * :link
    	아직 방문한적 없는 링크에 적용됨
	```
    <body>
      <ul>
        <li><a href=#>link<a></li>
      </ul>
    </body>
    ```
    ```
    a:link {
      color: violet;
    }
    ```    
    * :hover
    	마우스를 올렸을때 적용됨
	```
    <body>
      <ul>
        <li><a href=#>link<a></li>
      </ul>
    </body>
    ```
    ```
    a:hover {
      color: violet;
    }
    ```    
    * :active
    	마우스를 클릭하고 있을때 적용됨
	```
    <body>
      <ul>
        <li><a href=#>link<a></li>
      </ul>
    </body>
    ```
    ```
    a:active {
      color: violet;
    }
    ```
    * :focus
    	입력 양식(대표적으로 input)에 마우스를 클릭하고 입력하는 동안 적용됨
	```
    <body>
      <input>
    </body>
    ```
    ```
    input:focus {
      color: violet;
    }
    ```    
    * :not
    	이미 지정된 css스타일에서 특정한 요소를 제외시킬때 사용(선택을 하지 않기 위해 사용)
        선택할 요소:not(제외시킬요소): {}
	```
    <div>
       <p>tomato</p>
       <p class="disabled">not tomato</p>
    </div>
    ```
    ```
    div p:not(.disabled) {
       color: tomato;
    }
    ```        
11. 가상 요소(pesudo elemnet)
	가상 요소 섵낵자는 앞에 콜론이 두개 붙는게 웹 표준
    항상 content: ""; --> 항상 넣어줘야함
    ::before,::after는 inline 요소기 때문에 display:block;을 해줘야 가로세로값이 적용됨
    ::after
    	요소 앞에 내용을 삽입
	::before
    	요소 뒤에 내용을 삽입
    ```
    <body>
    <div>
      <p>Hello</p>
    </div>
    </body>
    ```
    ```
    p {
      color: tomato;
    }
    p::before {
      content:'Hi ';
      color: lime;
    }
    p::after {
      content: ' World';
      color: violet;
    }
    ```
12. 상속(inheritance)
	하위 요소에 어떤 css 속성을 명시하지 않는 경우, 기본적으로 상위 요소에 적용된 스타일이 하위 요소에도 적용되는 것
	```
    <body>
    <div>
      <h3>Hello</h3>
      <p>Hello</p>
    </div>
    </body>
    ```
    ```
    div {
      color: tomato;
    }
    p {
      color: inherit;
    }
    ```
