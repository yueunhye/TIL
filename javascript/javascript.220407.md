> 표기법
  1. dach-case(kebab-case): 대시기호를 사용해 띄어쓰기를 대신함. 주로 html, css에서 사용
  2. snake_case: 언더바로 구분 주로 html, css에서 사용
  3. camelCase(낙타표기법): 주로 js에서 사용
  4. PascalCase: 가장 앞에있는단어도 대문자. 주로 js
  5. Zero-based Numbering: 0기반 번호 매기기. 특수한 경우를 제외하고 0부터 숫자시작

* 데이터 종류(자료형)
	* String(문자 데이터). 따옴표를 사용
    ```
      let myName = "SUNNY"; --> 큰따옴표 사용
      let email = 'email@email.com'; --> 따옴표 사용
      let hello = `Hello ${myName}-->보간법!`; --> 백틱을 사용하게 되면 보간법 사용 가능
      console.log(hello); --> Hello SUNNY!
     ```

    * Number(숫자 데이터). 정수 및 부동소수점 숫자를 나타냄
     ```
      let number = 123;
      let opacity = 1.57 --> 부동 소수점
     ```

	* Boolean(불린 데이터). true, false 두 가지 값밖에 없는 논리 데이터
	```
      Undefined(값이 할당되지 않은 상태)
      let undef; --> js는 undefined라는 하나의 값이 있는 상태로 인식함
      let obj = { abc: 123 }; -->객체 데이터. abc라는 속성안에 123라는 값을 넣어줌
    ``` 

	* null(어떤 값이 의도적으로 비어있음을 의미함)
	```
		null과 undefined : 무언가가 없다는건 같지만 의도적이냐 아니냐에 따라 구분되어진다
    ```

	* Object(객체 데이터). 여러 데이터를 Key:Value 형태로 저장 {} 중괄호 사용
    ```
        let user = {
          //key: Value,
          name: 'Sunny',
          age: 92,
          isValid: true
        };
        console.log(user.age); //92
	```
	* Array(배열 데이터). 여러 데이터를 순차적으로 저장 [] 대괄호 사용


* 변수
    데이터를 저장하고 참조(사용)하는 데이터의 이름
    let, const, var
    변수는 재사용 가능
    let = 값(데이터)의 재할당 가능
    const = 값(데이터)의 재할당 불가능

* 예약어
    특별한 의미를 가지고 있어, 변수나 함수 이름 등으로 사용할 수 없는 단어
    this, if, break ... --> SyntaxError

* 함수
    특정 동작(기능)을 수행하는 일부 코드의 집합(부분)
    function
	1. // 함수 선언
    ```
        function hellFunc() {
          // 실행 코드
        }
        // 함수 호출
        hellFunc();
    ```    

	2. // returnFunc()라는 함수가 return 123을 반환하고, a라는 변수가 returnFunc()함수를 호출(실행)해서 console.log를 출력함
    ```
          function returnFunc() {
            return 123;
          }
          let a = returnFunc();
          console.log(a);
     ```

	3. ///함수 선언!
    ```
          function sum(a, b) { //a와 b는 매개변수 (Parameters)
            return a + b;
          }
          //재사용
          let a = sum(1, 2) // 1과 2는 인수 (Arguments)

          console.log(a); // 3
    ```      

	4. 
    ```
       기명(이름이 있는)함수
       //함수 선언
       function hello() {
         console.log(123);
       }
       hello(); // 123
       익명(이름이 없는)함수. 이름은 선언하지 않았기 때문에 호출을 할 수 없어서 변수와 함께 사용
       //함수 표현
       let num = function () {
         console.log(456);
       }
       num(); // 456
	```
    
	5. 객체 데이터
    ```
       const sunny {
         name: 'Yu',
         age: 92,
         //메소드(method) 
         //객체데이더 내부의 속성에 함수가 할당되어 있는것.
         //함수를 데이터 처럼 표현할 수 있다
         getName: function () {
           return this.name; // this란 this가 소속되 있는 객체데이터
         }
       };
       console.log(sunny.getName()); // Yu
	```

* 조건문
	조건의 결과에 따라 다른 코드를 실행하는 구문
    ```
    if, else
    let isShow = true;
    let checked = false;
    //if
    if(isShow) {
        console.log('wow'); // wow
    }
    if(checked) {
        console.log('yeah'); // 
    }
    //else
    if(checked) {
      console.log('wow');
    } else {
      console.log('yeah');
    }
    //yeah
	```
* DOM API
	자바스크립트에서 HTML을 제어하기위한 명령들
  Document Object Model(HTML의 div, span, input ...), 
    Application Programming Interface(애플리캐이션이 동작하기 위한 명령)
    
	* script defer
		html을 모두 읽은 상태에서 다시 JS를 읽어라라는 HTML속성. 그렇게 되면 script라는 구조를 정보가 들어있는 body부분에 옮기지 않아도 됨

  ```
  // HTML 요소 (Element) 1개 검색/찾기
  const boxEl = document.querySelector('.box');
  // HTML 요소에 적용할 수 있는 메소드
  boxEl.addEventListener(); --> 인수(Arguments) 추가 가능
  // 핸들러(handler, 실행할 함수)
  -> boxEl.addEventListener('click', function(){
    console.log('wow');
  })
  // 요소의 클래스 정보 객체 활용
  boxEl.classList.add('active');
  let isContains = boxEl.classList.contains('active');
  console.log(isContains); // true
  boxEl.classList.remove('active');
  let isContains = boxEl.classList.contains('remove');
  console.log(isContains); // false
  // HTML 요소(Element) 모두 검색/찾기
  const boxEls = document.querySelectorAll('.box');
  // 찾은 요소들 반복해서 함수 실행
  // 익명 함수를 인수로 추가
  // boxEls --> 유사배열
  // boxEl: 반복 중인 요소,  index: 반복 중인 번호
  boxEls.forEach(function (boxEl, index){
    boxEl.classList.add(`order-${index + 1}`);
    console.log(index, boxEl);
  }) 

  const boxEl = document.querySelector('.box');
  // Getter, 값을 얻는 용도
  console.log(boxEl.textContent);
  // Setter, 값을 지정하는 용도
  boxEl.textContent = 'Sunny';
  console.log(boxEl.textContent);
```

* 메소드 체이닝 
```
    const a = 'hell';
    const b = a.split('').reverse().join(''); // 메소드 체이닝
    // split: 문자를 인수 기준으로 쪼개서 배열로 변환
    // reverse: 배열을 뒤집기
    // join: 배열을 인수 기준으로 문자로 병합해 반환
    console.log(b) // lleh
```
