# Front-End React 개발
## 개발 환경 구축
### CRA 보일러 플레이트 생성
```
npx create-react-app board-app
```

### React 개발 서버 구동
```
cd board-app
npm start
```

### 테스트
* 자동으로 브라우저 탭이 열림
  - http://localhost:3000

## 개발
### bootstrap template 다운로드
* https://bootstrapmade.com/sailor-free-bootstrap-theme
* 압축 해제 후 public 폴더에 복사
* 테스트
  - http://localhost:3000/Sailor

### 폴더 생성
* src/pages: 라우터에서 사용할 페이지
  - board: 게시판
  - home: 홈
  - user: 회원
* src/components: 여러 페이지에서 공통으로 사용할 컴포넌트
  - common
  - layout: 화면 전체 구조 정의(header, footer)
* src/redux

### UI를 React 컴포넌트로 변경
* public/index.html
  - 템플릿의 index.html 헤더 부분을 추가
* src/pages/home/index.js
  - 템플릿의 index.html body 부분을 추가
#### JSX 문법으로 수정
* src/pages/home/index.js 파일 수정
* HTML 주석 제거
* 닫는 태그 추가
  - <br> -> <br />
  - <input> -> <input />
  - <img> -> <img />
* 속성 수정
  - class -> className
  - style="" -> style={{}}
* Link 컴포넌트 사용
  - "<a href" -> "<Link to"
  - </a> -> </Link>
#### react-router 설치
```
npm i react-router react-router-dom
```
* App.js에 라우팅 추가
```
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import Home from "./pages/home";
function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
      </Routes>
    </Router>
  );
}
export default App;
```

### 컴포넌트 설계
#### UI를 계층구조로 나누기
* 컴포넌트를 계층 구조로 설계
* 단일 책임 원칙: 컴포넌트는 한가지 작업만 수행하도록 구성
  - 컴포넌트가 많은 작업을 수행하다면 더 작은 하위 컴포넌트로 분할
#### 정적 버전으로 개발
* state는 사용하지 않고 props를 이용해서 하위 컴포넌트에 데이터 전달
* 하향식
  - 상위 컴포넌트 먼저 구축하고 하위 컴포넌트 구축
  - 소규모 프로젝트에 적합
* 상향식
  - 하위 컴포넌트 먼저 구축하고 상위 컴포넌트 구축
  - 대규모 프로젝트에 적합

#### state 식별
* 시간이 지나도 변함없이 유지되는가?
* props를 통해 부로모부터 전달되는가?
* 기존 state나 props 기반으로 계산할 수 있는 값인가?
* 그렇다면 state가 아님
* 나머지 값이 state일 수 있음

#### 



