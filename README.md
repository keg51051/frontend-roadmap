# frontend-roadmap
## 프론트엔드 개발자를 위한 로드맵 노트 레포입니다.
이미지를 클릭하면 원 출처로 이동합니다.
<a href="https://roadmap.sh/frontend">
  <img alt="frontend-roadmap_1-min" src="https://github.com/user-attachments/assets/e4a076c6-b15d-4306-aa17-e915afdbff81" />
</a>

위 이미지를 기반으로 노트 필기가 진행됩니다.

한글 표기가 어색한 용어는 영어로 작성되니 이해 부탁드립니다.

## 목차
1. [인터넷](#1-인터넷)
    - [호스팅](#호스팅이란)
    - [DNS 동작 과정](#dns-동작-과정)
    - [브라우저 동작 과정](#브라우저-동작-과정)
    - [실무 관련 주제](#인터넷-관련-프론트엔드-실무-주제)
2. [HTML](#2-html)
3. [CSS](#3-css)
4. [JavaScript](#4-javascript)
5. [TypeScript](#5-typescript)
6. 버전 관리
7. VCS 호스팅
8. 패키지 관리자
9. CSS 프레임워크
10. 프레임워크
11. Linters & Formatters
12. Module Bundlers
13. 테스트
14. 인증 전략
15. 웹 APIs
16. 웹 보안
17. SSR
18. SSG
19. 디자인 시스템
20. 배포
21. 성능
22. 웹 컴포넌트
23. GraphQL
24. PWAs
25. Mobile Apps
26. Desktop Apps

<br><br>

## 1. 인터넷
- 네트워크는 서로 연결된 컴퓨터나 기기의 모임
- 이 네트워크가 서로 연결된 커다란 네트워크가 인터넷
- 모든 장치가 표준화된 프로토콜을 통해 데이터를 주고받음.
- 웹, 이메일, 파일 전송 등은 인터넷 위에서 동작하는 앱의 한 형태

### 인터넷의 발전 과정
1. 초기엔 컴퓨터 간 직접 연결로 데이터 교환
2. 라우터의 등장으로 네트워크 간 통신 확장
3. 모뎀을 통해 전화선을 이용한 장거리 연결 실현
4. ISP의 등장으로 일반 사용자도 네트워크에 접속할 수 있는 상용 서비스 제공
5. ISP 간 상호 연결로 전 세계 네트워크가 하나로 연결된 인프라 형성

### 동작 원리
1. 데이터를 패킷으로 나누어 전송
2. 라우터가 패킷의 목적지를 확인하고 가장 효율적인 경로를 찾아 다음 목적지로 전달
3. IP, TCP, DNS 등과 같은 프로토콜을 이용해 패킷을 전송
4. 목적지에서 패킷을 다시 조립하여 원래의 데이터로 복원
5. 서버가 클라이언트 요청에 응답하면서 양방향 통신 완성
6. 추가로 HTTPS, SSL, TSL 등을 통한 보안 강화

### 용어 정리
| 용어 | 설명 |
|------|------|
| **HTTP (Hypertext Transfer Protocol) <br> HTTPS (...Secure)** | 웹 통신 프로토콜로 브라우저와 서버 간 요청·응답 수행. HTTPS는 SSL/TLS 기반 암호화 적용 (기본 포트 80 / 443) |
| **IP 주소** | 네트워크상의 장치를 식별하는 주소. IPv4는 32비트, IPv6는 128비트 체계로 더 많은 주소 제공 |
| **도메인** | 사람이 인식하기 쉬운 주소로 IP 주소를 대신하여 사용 |
| **DNS (Domain Name System)** | 도메인을 IP로 변환하는 네임 서버 시스템. 질의는 루트 → TLD → 권한 서버 순으로 진행 |
| **TCP/IP(Transmission Control Protocol/<br>Internet Protocol)** | 인터넷의 핵심 프로토콜 스택. IP는 경로 지정, TCP는 데이터 순서 및 오류 복구 담당 |
| **패킷** | 네트워크에서 전송되는 최소 데이터 단위. 헤더(정보)와 페이로드(내용)로 구성 |
| **라우터** | 패킷의 목적지를 분석해 최적 경로로 전달하는 장치. 여러 라우팅 프로토콜(BGP, OSPF 등)을 사용 |
| **모뎀** | 디지털 신호를 아날로그 신호로 변환해 전화선이나 광선을 통한 통신을 가능하게 하는 장치 |
| **ISP (Internet Service Provider)** | 인터넷 접속 서비스 제공 업체로, 사용자 네트워크를 백본망에 연결 |
| **포트** | 하나의 IP 내에서 여러 서비스(프로세스)를 구분하는 16비트 숫자 (0~65535) |
| **소켓** | IP 주소와 포트 번호의 조합으로 네트워크 통신 세션을 구분 |
| **SSL (Secure Sockets Layer)<br> TLS (Transport Layer Security)** | 데이터 암호화 및 인증을 위한 보안 프로토콜 |
| **CDN (Content Delivery Network)** | 전 세계 엣지 서버에 콘텐츠를 캐싱해 근접한 위치의 서버에서 빠르게 전달 |
| **API (Application Programming Interface)** | 클라이언트와 서버 간 데이터 교환을 위한 인터페이스. REST, GraphQL, WebSocket 등이 대표 형태 |
| **CORS (Cross-Origin Resource Sharing)** | 브라우저의 동일 출처 정책을 완화하여 다른 도메인 간 리소스 접근을 허용 |
| **캐시** | 자주 요청되는 데이터를 임시 저장하여 네트워크 부하를 줄이고 응답 속도를 높이는 기술 |

### 프론트엔드 개발자를 위한 통신 흐름 이해
- DNS 조회 → IP 주소 확인 → TCP 연결 → HTTP 요청 전송 → 응답 수신 → 렌더링
- 브라우저(클라이언트)는 HTTP 요청을 생성하고, 서버가 이에 대한 응답을 반환
- HTTPS 연결에서는 중간 단계에 SSL/TLS handshake가 포함되어 세션 암호화
- 네트워크 성능 요소(CDN, 캐시, latency 등)는 UX(User Experience)와 직접적인 연관이 있음.

---

### 호스팅이란?
- 웹사이트나 웹 서비스를 인터넷에 제공하려면, 서비스를 24시간 실행할 수 있는 서버에 파일과 데이터를 올려두고 외부에서 접속 가능하게 해야함.
- 호스팅은 이런 서버와 인프라, 유지보수 등을 전문 업체가 대신 제공해주는 서비스 구조

#### 주요 호스팅 유형
1. 웹 호스팅 (공유 호스팅)
   - 호스팅 업체의 한 서버를 여러 사용자가 나눠 쓰는 구조
   - 서버 구축 관리 부담이 없고, 비용이 저렴
   - 서버 루트 권한 없음
   - 트래픽, 저장 공간 등 자원 사용에 일부 제한
   - 소규모 서비스나 개인 블로그, 스타트업 홈페이지 등에 적합

2. 서버 호스팅
   - 서버 한 대 전체를 단독 임대
   - 서버 OS, 보안, 소프트웨어 설치, 자원 활용 등 모든 관리 및 설정 가능
   - 초기 세팅에 시간, 비용이 더 많이 들고, 직접 서버를 운영하는 역량이 요구됨
   - 대형 서비스, 기업 시스템 등 자원이 많은 곳에 적합

3. 클라우드 호스팅
   - 여러 대의 물리 서버를 가상화해, 원하는 스펙의 서버를 즉시 생성해 사용
   - 필요한 만큼 자원을 조절할 수 있으며, 트래픽 급증 시 확장에 용이
   - 후불제 방식으로 비용 관리 용이
   - 초기 서버 생성이 빠르고, 쉬운 배포 가능
   - 접속자 수가 급변하거나, 서비스가 빠르게 성장하는 스타트업 및 신규 서비스에 적합

---

### DNS 동작 과정
1. 사용자가 `www.example.com`을 브라우저에 입력  

2. 브라우저 캐시 확인  
   - 최근 방문한 도메인의 IP가 캐시에 있으면 바로 사용

3. 브라우저가 로컬 DNS 캐시 확인  
   - 로컬 캐시에 없으면 다음 단계로 진행

4. ISP DNS 서버 요청  
   - 캐시에 없으면 ISP의 DNS 서버에 질의
   - ISP DNS 서버가 해당 도메인의 IP를 알면 바로 응답

5. Recursive Query
   - ISP DNS 서버도 IP를 모르면 상위 DNS 서버에 순서대로 요청 전달
   - 루트 DNS 서버가 최상위 도메인(TLD, 예: `.com`)의 DNS 서버 위치 안내
   - TLD DNS 서버가 실제 도메인(예: `example.com`)의 권한 DNS 서버 위치 안내
   - Authoritative DNS 서버가 해당 도메인의 최종 IP 주소 반환

6. IP 주소 전달
   - 권한 DNS 서버가 반환한 IP 주소를 ISP DNS 서버 거쳐 브라우저에 전달

7. 브라우저가 받은 IP 주소로 웹 서버에 HTTP/HTTPS 요청  
   - 웹 페이지 표시

8. TTL(Time To Live) 기반 캐싱  
   - 브라우저와 ISP DNS 서버는 받은 IP를 TTL에 따라 일정 기간 캐싱  
   - TTL 만료 시 다시 DNS 조회

---

### 브라우저 동작 과정

1. URL 파싱  
   - 입력한 URL을 프로토콜, 도메인, 경로, 쿼리 등으로 분리  
   - 예: `https` 프로토콜, `www.example.com` 도메인, `/path` 경로, `query=1` 쿼리

2. DNS 조회  
   - 전체 도메인을 바탕으로 DNS를 통해 IP 주소 확인  
   - 로컬 캐시 → ISP DNS 서버 → Authoritative DNS 서버 순서로 진행

3. TCP/TLS 연결  
   - IP와 포트(기본: 80/443)로 서버와 TCP 연결  
   - HTTPS라면 TLS 핸드셰이크, 암호화 채널 형성

4. HTTP 요청 전송  
   - 서버에 GET, POST 등의 HTTP 요청과 헤더, 필요 시 바디 정보 전달

5. 서버 응답 수신  
   - 서버가 요청 처리 후 HTTP 응답 반환  
   - HTML 문서, 상태 코드, 쿠키 및 기타 헤더 포함

6. HTML 파싱 및 DOM 생성  
   - HTML 해석(코드 파싱), DOM 트리 생성

7. CSS 파싱 및 렌더 트리 생성  
   - CSS 파싱, DOM과 결합해 렌더 트리 생성  
   - 렌더 트리는 화면에 출력될 실제 노드와 스타일 보유

8. 레이아웃 계산  
   - 렌더 트리 기반 요소 위치·크기 계산

9. 페인팅  
   - 레이아웃 결과로 화면에 픽셀 단위로 그리기

10. JS 실행  
    - JS 엔진이 JS를 파싱, 실행
    - DOM 변경 시 reflow(레이아웃 재계산) / repaint 발생

11. 이벤트 처리  
    - 클릭, 입력 등 사용자 이벤트 수신
    - JS 핸들러 실행 등 interaction 구현

---

### 인터넷 관련 프론트엔드 실무 주제
- CORS 이슈와 해결
- CDN 적용 방법
- 브라우저 캐싱 및 Cache-Control 활용
- HTTPS 인증서 적용 및 에러 대응
- F12 개발자도구(Network/Performance) 분석
- 이미지 & 리소스 Lazy Load 및 최적화
- XSS/CSRF 실무 대응
- SPA 라우팅 및 상태 관리(React, Vue 등)
- API 에러 핸들링 패턴
- 비동기 데이터/컴포넌트 로딩 최적화
- OAuth/JWT 로그인 로직
- 웹 보안(SSL/TLS, 데이터 암호화)

<br>

## 2. HTML
- HyperText Markup Language
- 웹 페이지 구조와 의미를 정의하는 마크업 언어
- 다양한 태그로 계층적 구조를 가짐
- 모든 웹 프론트엔드의 기반, 브라우저가 해석

### 기본 구조
```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title>문서 제목</title>
  </head>
  <body>
    <h1>제목</h1>
    <p>본문 내용</p>
  </body>
</html>
```

### 주요 태그 및 역할
- `<!DOCTYPE html>`: 문서가 HTML5 표준임을 선언
- `<html>`: HTML 문서 루트
- `<head>`: 메타데이터 영역 (인코딩, 제목, 스타일, 스크립트, 외부 리소스)
- `<body>`: 실제 콘텐츠 표시 영역
- `<h1> ~ <h6>`: 제목(heading), h1이 최상위 크기 및 중요도
- `<p>`: paragraph, 단락(문단)
- `<a href="">`: 하이퍼링크(내부/외부)
- `<img src="" alt="">`: 이미지 표시, alt는 대체 텍스트(접근성)
- `<ul>`(순서 없는), `<ol>`(순서 있는), `<li>`(항목): 리스트
- `<table>`, `<tr>`, `<th>`, `<td>`: 테이블, 행(row), 헤더, 셀
- `<form>`, `<input>`, `<textarea>` 등: 사용자 입력/전송 폼
- `<button>`: 버튼
- `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`: 시맨틱 태그 (문서의 논리적 섹션 구분)
- `<br>`, `<hr>`: 라인 브레이크, 수평선

### 태그 속성
- class: 스타일과 스크립트 적용 대상 그룹 지정
- id: 유니크한 문서 내 고유 식별자
- style: 인라인 CSS 스타일 작성
- src, href 등: 외부 자원 경로 지정 (이미지, 링크 등)
- alt: 이미지 대체 텍스트, 접근성 필수
- title: 툴팁 텍스트 제공
- name, value: 폼 요소 식별 및 값
- tabindex, role: 접근성 관련 속성

### 특징 및 주의점
- 구조적 언어
  - 태그와 요소로 웹 컨텐츠의 구조와 의미를 계층적으로 설계
  - 모든 문서는 `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`로 구성
- 정적 문서 기반
  - 주로 동적인 처리는 CSS와 JavaScript를 통해 해결
  - HTML 자체는 뷰의 기본 틀만 제공
- 확장성 및 호환성
  - 모든 주요 웹 브라우저에서 지원
  - 브라우저별로 미묘한 렌더링 차이 발생 시, W3C 표준 준수 필요
- 계층적 중첩
  - 부모-자식 구조로 요소 중첩, 잘못된 중첩은 렌더링 오류 또는 브라우저 자동 보정
- 시맨틱 태그 권장
  - 의미 있는 태그(`header`, `main`, `section`, `article`, `footer` 등)로 문서를 논리적으로 분리
  - 접근성과 SEO 최적화에 도움
- 블록/인라인 요소 구분
  - 블록 요소(`<div>`, `<p>`, `<ul>`, `<table>` 등)는 한 줄 전체 차지
  - 인라인 요소(`<span>`, `<a>`, `<img>` 등)는 글자처럼 한 줄 내 배치
- 속성과 역할별 태그
  - 각 태그는 다양한 속성(`class`, `id`, `style`, `src`, `alt` 등)으로 기능 확장
  - 접근성 및 유지보수를 위해 alt, aria 속성, class/id 네이밍 체계 중요
- 자동 오류 보정
  - 태그가 닫히지 않아도 브라우저가 렌더링 과정에서 최대한 구조 자동 보정
  - 하지만 표준 문법·중첩을 지키는 것이 오류와 혼란 방지에 핵심
- 실제 내용은 `<body>`에 위치
  - UI의 모든 컨텐츠(텍스트, 이미지, 링크, 표 등)는 `<body>`에 포함
 
이러한 특징과 규칙을 잘 지키면 웹 표준, 유지보수성, 접근성, SEO 모두에서 좋은 HTML을 만들 수 있음

<br>

## 3. CSS
- Cascading Style Sheets
- 웹 페이지의 스타일과 레이아웃을 결정하는 스타일 시트 언어
- HTML이 문서의 구조를 담당하면 CSS는 그 구조에 색상, 폰트, 여백, 정렬, 크기, 애니메이션 등의 시각적 디자인을 적용
- CSS는 브라우저가 HTML DOM과 CSSOM을 해석해 스타일을 계산하고, 렌더 트리를 생성해 화면에 표시

### 기본 구조
```
body {
background-color: #f0f0f0;
font-family: Arial, sans-serif;
color: #333;
}

h1 {
font-size: 24px;
font-weight: bold;
}

p {
line-height: 1.6;
margin-bottom: 10px;
}
```

### 주요 개념 및 구성 요소
- Selector: 스타일을 적용할 HTML 요소를 지정 (예: 태그명, 클래스, 아이디, 속성 등)
- Property: 변경할 스타일 종류(색상, 크기, 위치 등)
- Value: 속성이 가지는 구체적 값 (예: `red`, `16px`, `center` 등)
- Declaration Block: 속성과 값을 `{}`로 묶은 단위
- Cascading: 여러 규칙이 충돌할 때 적용 우선순위 결정
- Inheritance: 일부 스타일이 부모 요소로부터 자식에게 전달됨
- Box Model: 요소의 크기와 여백, 테두리를 계산하는 기본 원리 (content, padding, border, margin)
- Positioning: 요소 위치 지정 방식 (static, relative, absolute, fixed, sticky)
- Display: 요소의 레이아웃 타입 (block, inline, flex, grid 등)
- Flexbox & Grid: 효율적인 레이아웃 배치 도구
- Media Query: 반응형 디자인을 위한 화면 크기별 스타일 적용

### 주요 CSS 속성
- 색상 및 배경: `color`, `background-color`, `background-image`  
- 텍스트: `font-family`, `font-size`, `font-weight`, `line-height`, `text-align`, `text-decoration`  
- 박스 모델: `margin`, `padding`, `border`, `width`, `height`  
- 레이아웃: `display`, `position`, `top`, `left`, `right`, `bottom`, `z-index`  
- 플렉스박스: `flex`, `justify-content`, `align-items`, `flex-direction`  
- 기타: `opacity`, `visibility`, `overflow`, `cursor`, `transition`, `animation`

### CSS 적용 방법
- 인라인 스타일: HTML 태그 내 `style` 속성에 직접 작성
- 내부 스타일 시트: `<style>` 태그 내 CSS 작성
- 외부 스타일 시트: `.css` 파일로 분리 후 HTML에서 `<link>` 태그로 연결 (권장)

### 특징 및 주의점
- CSS는 선택자 우선순위, 상속, 캐스케이딩 규칙이 복잡하여 잘못 설계하면 유지보수가 어려움  
- 범용 클래스명과 명확한 네이밍 컨벤션(BEM 등) 사용 권장  
- 브라우저별 지원 차이, 벤더 프리픽스 고려  
- 과도한 인라인 스타일 사용 피하고, 외부 스타일 시트 사용 권장  
- 반응형 디자인 위해 미디어 쿼리와 유연한 레이아웃 기법 필수  
- CSS는 웹 접근성, 성능, 사용자 경험 개선에 핵심 역할 수행

<br>

## 4. JavaScript
- 웹 페이지를 동적으로 만들고 사용자와 상호작용을 가능하게 하는 스크립트 언어
- HTML과 CSS가 구조와 스타일을 담당, JS(JavaScript)는 웹 페이지 동작과 기능을 구현
- 모든 주요 브라우저에서 지원하며 웹 개발 3대 핵심 기술 중 하나

### 기본 구조
```
// 변수 선언
let message = "Hello, World!";

// 함수 정의
function greet(name) {
  return Hello, ${name}!;
}

// 조건문
if (message) {
  console.log(greet("User"));
}

// 반복문
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

### 주요 개념
- 데이터 타입: Number, String, Boolean, Null, Undefined, Symbol, Object (배열, 함수 포함)
- 함수: 일급 객체로 취급, 익명 함수, 화살표 함수 등 다양한 표현법 지원
- 이벤트 기반 프로그래밍: 클릭, 입력, 로드 등 사용자 이벤트에 반응하는 코드 작성 가능
- 비동기 처리: 콜백 함수, Promise, async/await로 비동기 작업 처리
- DOM 조작: `document` 객체를 통해 HTML 요소를 선택, 변경, 추가, 삭제 가능
- 브라우저 API 활용: Fetch API, LocalStorage, SessionStorage, Geolocation 등 다양한 웹 API 지원
- 객체 지향 및 함수형 프로그래밍: 둘 다 지원, 다양한 설계 사용 가능
- 에러 처리: try/catch로 예외 처리
- 모듈 시스템: ES6부터 `import`와 `export` 지원, 코드 분할과 재사용 가능
- 호출 스택과 이벤트 루프: 동기/비동기 실행 구조 이해 필수

### 주요 메서드 및 문법
- 배열: `.map()`, `.filter()`, `reduce()`, `.forEach()`
- 객체 리터럴, 전개 연산자(`...`)
- 템플릿 리터럴(백틱)
- 클래스와 상속
- 익명 함수, 콜백 함수
- 화살표 함수 (`() => {}`)로 간결한 함수 표현

### 특징 및 주의점
- 동적 타이핑 언어로 타입 변환에 주의
- 브라우저 호환성 고려 (특히 ES6 이후 기능)
- 비동기 코드 작성 시 callback hell 방지 방법 숙지 (비동기 처리 중점)
- 전역 변수 남용 금지, 모듈화 필요
- DOM 업데이트는 가급적 최소화 => 성능 문제
- 클로저, 스코프, this 키워드에 대한 명확한 이해 필수

## 5. TypeScript
- JavaScript의 상위(슈퍼셋) 언어, 정적 타입을 기반으로 코드를 더 안전하게 작성할 수 있도록 설계됨
- 마이크로소프트에서 개발한 오픈 소스 언어이며, 코드는 컴파일(트랜스파일) 과정을 거쳐 일반 JavaScript로 변환되어 실행
- JavaScript와 100% 호환되며, 최신 JS 문법(ES6+)을 사전에 활용 가능

### 기본 문법
```
// 기본 타입 선언
let isDone: boolean = false;
let total: number = 100;
let name: string = "Jane Doe";

// 배열과 튜플
let list: number[] = [1, 2, 3];
let tuple: [string, number] = ["Jane", 30];

// 함수 타입 선언과 사용
function add(a: number, b: number): number {
  return a + b;
}

// 함수 타입 변수
let myAdd: (x: number, y: number) => number = function (x, y) {
  return x + y;
};

// 인터페이스 정의 및 사용
interface Person {
  firstName: string;
  lastName: string;
  age?: number;  // 선택적 속성
}

function greet(person: Person): string {
  return `Hello, ${person.firstName} ${person.lastName}`;
}

const user: Person = { firstName: "John", lastName: "Smith" };
console.log(greet(user));

// 제네릭 함수
function identity<T>(arg: T): T {
  return arg;
}

let output1 = identity<string>("myString");
let output2 = identity<number>(100);

// 유니언 타입과 타입 가드
function padLeft(value: string, padding: string | number) {
  if (typeof padding === "number") {
    return Array(padding + 1).join(" ") + value;
  }
  if (typeof padding === "string") {
    return padding + value;
  }
  throw new Error(`Expected string or number, got '${typeof padding}'.`);
}

// 비동기 함수 예시
async function fetchData(url: string): Promise<string> {
  const response = await fetch(url);
  const data = await response.text();
  return data;
}
```

### 주요 개념
- 정적 타입 지정으로 컴파일 시점에 오류 발견 가능
- 타입 추론 지원으로 선언 생략 가능
- 인터페이스와 타입 별칭으로 객체 구조 정의 및 재사용
- Generic으로 재사용 가능한 타입 작성
- Union, Intersection 타입으로 복잡한 타입 조합 가능
- 코드 모듈화

### 특징
- JavaScript 상위 집합(Superset)으로 기존 JS 코드도 실행 가능
- 컴파일 단계에서 타입 검사 수행, 런타임 오류 감소
- 점진적 도입 가능, 대형 프로젝트에 강점
- 뛰어난 IDE 지원으로 생산성 향상
- 객체지향 프로그래밍

### 주의점
- 타입 선언 누락 시 타입 불일치 위험
- 타입 시스템 학습에 시간 필요
- 런타임 타입 체크 불가(컴파일에만 적용)
- 컴파일 과정 필수
- 복잡한 타입 작성은 코드 가독성 저해













