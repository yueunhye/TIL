CSS 단위

-   px: 픽셀 단위
-   %: 상대적 백분율. 부모 요소의 크기의 영향을 받아 크기가 변함
-   em: 상위 요소 크기의 몇 배인지를 정하는 단위
    -   상위 폰트크기가 16px일 경우 하위 폰트크기를 1em 적용시
    -   1em = 16px, 1.5em = 24px(1.5\*16)
-   rem: r(root)의 약자로 최상위.
    -   모든 브라우저의 폰트 사이즈는 16px.
    -   가장 상위인 html(or body)태그의 폰트 크기가 16px인경우, 1rem 적용시 1rem = 16px
-   vw(viewport width): 뷰포트 가로 너비의 백분율. 1vw = width의 1%
-   vh(viewport height): 뷰포트 세로 너비의 백분율, 1vh = height의 1%

CSS 자주 사용되는 속성

-   너비
    -   width
        -   요소의 가로 너비  
            min-width default value: 0  
            max-width default value: none;
    -   height
        -   요소의 세로 너비  
            min-height default value: 0  
            max-height default value: none;
-   여백
    -   내부여백 padding
        -   요소의 내부 여백을 만들어 내는만큼 요소의 크기가 늘어남
    -   외부여백 margin
        -   요소의 외부 여백을 만들어 냄
        -   음수 사용 가능
        -   margin: auto;는 가운데 정렬 가능
    -   마진중첩
        -   마진중첩은 좌·우에서는 발생하지 않고 상·하에서만 발생
        -   자식요소에 margin을 줬는데 부모요소의 margin으로 만들어져버리는 현상
        -   부모의 margin-top,bottom과 자식의 margin-top,bottom이 만나면 중첩이 생김
        -   이전형제와 다음형제가 만났을때  
            이전형제의 margin-bottom과 다음형제의 margin-top이 만나면 중첩이 생김  
            부모요소에 over:hidden;을 주면 중첩현상이 사라짐

-   border
    -   border-radius(모서리를 둥글게)
    -   box-sizing
        -   border-box  
            content + padding + border로 크기계산이 됨
        -   default값은 content-box
-   요소의 크기가 늘어남

-   overflow
    -   visible: default값. 넘칠 경우 상자밖으로 보여짐
    -   hidden: 넘치는 부분은 잘려서 보이지 않음
    -   scroll: 스크롤바가 추가됨
    -   auto: 넘친 영역만 스크롤바가 생김
-   요소의 크기 이상으로 내용이 넘쳤을 때 보여짐을 제어하는 단축 속성  
    부모 요소에 overflow를 작성해 줘야함

-   display
    -   none
    -   block
    -   inline
    -   inline-block
-   요소를 어떻게 보여줄지를 결정
-   opacity
    -   opacity default value: 1  
        0~1까지 소수점을 표현할 때 앞에 0은 생략가능 ex).3
-   요소의 투명도 설정
-   line-height
-   line-box의 높이를 지정하며 주로 텍스트간의 줄 간격을 조절할 때 사용  
    line-height default value: normal
-   문자
    -   color: 글자 색상 변경
    -   text-align  
        문자 정렬 방식
        -   left: 인라인 콘텐츠를 줄 상자의 왼쪽 모서리로 정렬
        -   right: 인라인 콘텐츠를 줄 상자의 오른쪽 모서리로 정렬
        -   center: 인라인 콘텐츠를 가운데 정렬
        -   justify: 인라인 콘텐츠를 양쪽 정렬
    -   text-decoration  
        문자의 장식
        -   underline: 글자 위에 선
        -   overline: 글자 아래에 선
        -   none: 선이 없음
        -   line-through: 글자 중간에 선
    -   text-indent  
        들여쓰기(양수), 내여쓰기(음수)  
        text-indent: -9999px;
        -   Phark Method  
            이미지로 대체할 엘리먼트에 배경이미지를 설정하고 글자는 text-indent를 이용하여 화면 바깥으로 빼내어 보이지 않게 하는 방법
-   배경
    -   background-image: url("경로")  
        상대경로: index파일을 기준으로 지정하는 바법  
        절대경로: http://가 포함되어 있는 경로.이미지 가져올때에는 우클릭 이미지보기를 한 후 '이미지 주소 복사'를 하면 된다
    -   background-color  
        default value: transparent(투명한)
    -   background-size  
        default value: auto
        -   cover: 비율을 유지, 요소의 더 넓은 너비에 맞춤
        -   conatin: 비율을 유지. 요소의 더 짧은 너비에 맞춤
    -   background-repeat  
        배경 이미지의 반복 방법 지정  
        가로축이나 세로축을 따라 반복할 수도 있고 반복하지 않을 수도 있음
        -   repeat: default value
        -   no-repeat: 반복하지 않음
        -   repeat-x: x축으로 반복
        -   repeat-y: y축으로 반복
    -   background-position  
        배경 이미지 시작 위치 지정  
        기본적으로 왼쪽 상단 꼭지점부터 시작함
        -   top left, top center, top right: 왼쪽 상단, 가운데 상단, 오른쪽 상단
        -   center left, center center, center right: 왼쪽 중앙, 중앙, 오른쪽 중앙
        -   bottom left, bottom center, bottom right: 왼쪽 하단, 가운데 하단, 오른쪽 하단
    -   background-attachment  
        배경 이미지의 스크롤 여부를 정함  
        default value: scroll
        -   fixed: 요소가 스크롤 될때 배경 이미지가 뷰포트에 고정되는 속성 값
-   배치
    -   position  
        요소의 위치 지정 기준  
        default value: static
        -   relative: 요소를 원래 위치를 기준으로 상대적으로 배치
        -   absolute: 위치 상 부모 요소를 기준으로 잡고 설정(부모요소에 relative를 심어줘야함)
        -   fixed: 뷰포트를 기준으로 고정된 위치에 배치
    -   요소의 쌓임 순서(stack order)
        1.  요소에 position 속성의 값이 있는 경우 위에 쌓임
        2.  1번의 조건의 같은 경우, z-index 속성의 숫자 값이 높을 수록 위에 쌓임
        3.  1,2번의 조건까지 같은 경우, html의 다음 구조일 수록 위에 쌓임
    -   z-index  
        요소의 쌓임 정도를 지정  
        default value: auto  
        숫자가 높을수록 위에 쌓임
    -   position 속성을 사용하면서 요소의 display가 변경됨  
        relative, static는 변경되지 않지만  
        absolute, fixed는 display가 block요소로 바뀌기 때문에 따로 display: block을 안해줘도 됨  
        (inline요소는 가로세로 값을 같지 못하는데 값이 변경됐을 경우 위와같은 상황 잘 살펴보기)
-   플렉스(flex)
    -   flex-container (플렉스 컨테이너)
        -   flex-direction: 아이템들이 배치되는 축의 방향을 결정하는 속성
            -   row: default값. 가로(행) 방향으로 배치
            -   row-reverse: 아이템들이 역순으로 가로 배치
            -   column: 세로(열) 방향으로 배치
            -   column-reverse: 아이템들이 역숙으로 세로 배치
                -   flex-warp: 컨테이너가 더 이상 아이템들을 한 줄에 담을 공간이 없을 때 아이템 줄바꿈 여부
                -   wrap: 줄바꿈
                -   no-wrap: default값. 줄바꿈을 하지 않음
        -   flex-flow: flex-direction과 flex-warp을 한번에 지정할 수 있는 단축 속성. 순서는 direction, warp
        -   justify-content: 메인축 방향으로 아이템 (수평)정렬
            -   flex-start: default값. 아이템 시작점 정렬
            -   flex-end: 아이템 끝점 정렬
            -   cneter: 아이템 가운데 정렬
            -   space-between: 아이템들 사이에 균일한 간격을 만들어줌
            -   space-around: 아이템들 둘레에 균일한 간격을 만들어줌
            -   space-evenly: 아이템들의 사이와 양 끝에 균일한 간격을 만들어줌
        -   align-content: flex-wrap: wrap; 이 설정된 상태여야 하며, 아이템들의 행이 2줄 이상일때 (수직)정렬
            -   stretch: default값. 아이템이 수직축 방향으로 끝까지 늘어남
            -   flex-start: 아이템 시작점 정렬
            -   flex-end: 아이템 끝점 정렬
            -   cneter: 아이템 가운데 정렬
            -   baseline: 아이템들이 텍스트 베이스라인 기준으로 정렬
        -   align-items: 수직축 방향으로 아이템들을 정렬
            -   stretch: default값. 아이템이 수직축 방향으로 끝까지 늘어남
            -   flex-start: 아이템 시작점 정렬
            -   flex-end: 아이템 끝점 정렬
            -   cneter: 아이템 가운데 정렬
            -   baseline: 아이템들이 텍스트 베이스라인 기준으로 정렬
    -   flex item에 적용하는 속성들
        -   flex-basis: flex 아이템의 기본 크기 설정
            -   flex-basis: auto(default);, 단위는 %, px, em, rem으로 표현갸능
        -   flex-grow  
            아이템들의 증가 너비 비율  
            default값은 0  
            아이템들의 flex-basis를 제외한 여백 부분을 flex-grow에 지정된 숫자의 비율로 나누어 가짐. 즉 여백의 비
        -   flex-shrink  
            아이템들의 감소 너비 비율  
            default값은 1  
            감소너비를 적용하고 싶지 않으면 flex-shrink: 0;으로 부여해 주변 적용된 크기 그대로 유지
        -   flex  
            flex-grow, flex-shrink, flex-basis를 한번에 쓸 수 있는 축약형 속성
        -   align-self: align-items의 아이템 버전. 해당 아이템의 수직축 방향 정렬
        -   order  
            각 아이템들의 시각적 나열 순서를 결정  
            숫자가 작을수록 앞에 적용됨  
            default값은 0
-   1차원 레이아웃  
    요소의 부모요소에 display: flex를 주면 수평정렬이 됨  
    flex-container는 부모요소가 되고 flex item은 자식요소가 됨  
    justify-content: center; align-item: center; 를 해주면 한가운데 정렬 가능
-   전환
    -   transition  
        transition: <property 속성먕><duration 지속시간><timing-function 타이밍함수><delay 대기시간>
        -   transition-proterty(default: all)
        -   transition-duration(default: 0)  
            property, duration은 쉼표를 통해 여러개 작성 가능  
            ex) transition: width: .3s background-color: .5s
        -   transition-timing-function(default: ease)  
            [easings.net](https://easings.net/)
        -   transition-delay(default:0s 전환 효과가 몇초뒤에 시작할지 대기시간지정)
-   변환
    -   transform  
        transform: rotate(deg(degree의 약어)) scale();
        -   2D 변환 함수
            -   translate(x, y) 이동
            -   translateX(x) 이동
            -   translateY(y) 이동
            -   scale(x, y) 크기(배수로 설정)
            -   rotate(deg) 회전
            -   skewX(x) 기울임
            -   skewY(y) 기울임
        -   3D 변환 함수
            -   rotateX(x) 회전
            -   rotateY(y) 회전
            -   backface-visibility  
                3D 변환으로 회전된 요소의 뒷면 숨김 여부
                -   visible: defualt값. 뒷면보임
                -   hidden: 뒷면숨김
            -   perspective(n) 원근법(거리)  
                transform: perspective(원근법 함수는 제일 앞에 작성해야함 300px) rotateY(45deg);
        -   perspective 속성과 함수의 차이
            -   perspective: 300px; // perspective-origin 부모요소에 원근 거리를 지정하는게 더 깔끔함
            -   transform: perspective(300px); // transform-origin


