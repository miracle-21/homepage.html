<h2>실패 내용</h2>
<h4>1. 입력창에 글자가 입력되고, 입력 완료되면 채팅창에 노란 말풍선이 추가되면서 입력창 초기화</h4>
        
        <form id="textLine">
        	<span>안녕하세요!<span>
        	<button>Enter</button>
        </form>
        
*  입력창에 글자가 입력되면 ‘enter’ 박스가 밀리는 현상 발생
*  밀림 현상이 왜 나타는지 못찾음
*  시도한 방법

    * 설마 인라인 요소여서 안되나? → div, p 등으로 변경
    * 블록요소, 인라인요소로 변경도 해봄
      `display: block;`
      `display: inline;`
    * body 태그에서 주축과 교차축 기준 중앙정렬을 했는데, 하위 태그의 레이아웃만 다시 지정 할 수 없나?
    * 레이아웃 문제인것 같아 grid, flex를 찾아봄
* 결과
    * 기간 동안 css 레이아웃을 이해하고 적용시키기 어려워 다른 방법 모색

 
<h4>대화창에 커서가 깜빡이는 효과</h4>

*  css 로 구현이 가능했지만 너무 빠르거나 너무 느려서 이상함
*  javascript 로 구현하는 방법이 있어 보이나 시간 관계상 빼기로 함

<h2>사전스터디 이후 피드백</h2>


<h4>1. 한 눈에 구조를 파악할 수 있도록 html 기본구조에 따라 의미 있는 태그 사용하기</h4>
        
        
*  왼쪽 카톡창은 header 태그 지정  

*  오른쪽 소개란은 section 태그 지정   
  
*  section 태그 안에는 `<ul>, <li>` 목록 태그 지정      
        
*  메일, 깃허브 주소는 footer 태그 지정      
        
*  하이퍼링크는 `<a>` 태그, 이미지는 `<img>` 태그 지정    
        
*  그 외 의미 없는 분리는 `<div>, <p>` 태그 사용
        
        
<h4>2. 모바일같이 작은 화면에는 내용이 안보여서 반응형 웹으로 제작 필요</h4>
    
*  미디어 쿼리 사용  
        
    1. @media (max-height:700px) : 화면 높이가 낮으면 배경색이 짤려서 최소 높이 지정
        
    2. @media(max-width: 1100px) : 폭이 좁아지면 레이아웃이 행으로 정렬
        
        
<h4>3. 주석 보완</h4>
        
        
<h4>4. 클래스 이름은 명시적으로 짓기</h4>
       
*  grid 컨테이너 태그는 id=”container” 로 지정

* container 안에 총 4개의 grid item 생성

    * .kakao
            - `<h1>` : 카카오 상단 방이름
            
            - class=”kakao__txt1”~“kakao__txt8” : 말풍선
            
            - class="kakao__typingArea” : 채팅창
    * .grid_empty_space
    
            - 1열은 전체적으로 비워야지 카톡창이 아래로 흐르기 떄문에 빈 태그 생성 
    * .introduce
    
            - .introduce__title : 소개 타이틀
            
            - .introduce__txt : 소개 내용
    * `<div>`
      
            - 1열은 전체적으로 비워야지 카톡창이 아래로 흐르기 떄문에 빈 태그 생성
        
        
<h4>5. 그 외 개선 사상</h4>

*  소개 문구는 웹 폭이 좁아지면 글자 자동 줄바꿈 되도록 함

        - 대상 : .introduce__txt
        
        - 기존 : height: 480px; width: 400px;
       
        - 수정 : max-width: 800px; min-width: 400px;


*  grid를 이용해서 소개문구가 줄바꿈이 되면 노란색 구분선도 같이 길어지도록 함

        - 기존 : 소개 제목과 내용을 <div>태그로 따로 묶음
       
        - 수정 : 제목과 내용을 <ul> 태그로 같이 묶어서 폭이 길어지면 구분선도 같이 길어지게 함


<h2>아쉬운점</h2>
  
*  말풍선과 애니메이션를 나타내기 위해 작성한 코드가 너무 길다. 더 짧게 할 수는 없을까
*  레이아웃의 이해도가 낮아서 구현하지 못한 부분이 많다
*  대화창에 커서가 깜빡이는 효과도 넣어보고 싶다
*  기존 animation 효과를 grid 에서 적용할 방법을 못찾음
*  grid 셀 안의 grid 아이템을 상하좌우 정렬시키고 싶었는데 중앙정렬만 됨
*  javascript 기능이 없다
