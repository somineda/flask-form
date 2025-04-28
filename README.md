<a href="https://club-project-one.vercel.app/" target="_blank">
<img width="888" alt="스크린샷 2025-04-28 오전 10 46 08" src="https://github.com/user-attachments/assets/ce54b510-a243-4467-a48f-b5786e5d002f" />

</a>

<br/>
<br/>

# 0. Getting Started (시작하기)
```bash
$ npm start
```
[서비스 링크](http://13.125.52.254/)

<br/>
<br/>

# 1. Project Overview (프로젝트 개요)
- 프로젝트 이름: KBO 팬들을 위한 설문조사
- 프로젝트 설명: KBO 선호도, 좋아하는 구단, 우승에 관한 설문조사

<br/>
<br/>

# 2. Key Features (주요 기능)
- **설문시작 및 회원가입**:
  - 사용자는 간단한 정보 입력(이름, 성별, 나이) 후 설문을 시작할 수 있습니다. 
  - 회원가입 시 DB에 유저정보가 등록됩니다.

- **야구관련 설문 진행**:
  - 프로야구 관람 여부, 관람 방법, 선호 구단에 대한 질문이 주어집니다.
  - 사용자는 각 질문에 대해 선택지를 클릭하여 답변할 수 있습니다.

- **선택지 이미지 지원**:
  - 특정 질문(선호 구단 선택 등)에서는 구단 로고 이미지를 보고 선택할 수 있어 직관성을 높였습니다.

- **설문 결과 집계**:
  - 모든 설문이 완료되면, 사용자들의 응답을 통계로 집계하여 결과 페이지에 보여줍니다.

- **관리자 대시보드**:
  - 관리자는 모든 응답 데이터를 한눈에 확인할 수 있습니다.
  - 유저별 답변 내역도 조회할 수 있습니다.

<br/>
<br/>

## 4. Technology Stack (기술 스택)

| 구분 | 사용 기술 |
|:---|:---|
| **Frontend** | HTML5, CSS3, Bootstrap 5 |
| **Backend** | Python 3.12, Flask 3.1.0 |
| **Database** | MySQL, SQLAlchemy 2.0.37, Flask-SQLAlchemy 3.1.1, Flask-Migrate 4.0.7 |
| **Server** | AWS EC2 (Ubuntu 22.04) |
| **Web Server** | Gunicorn 23.0.0, Nginx |
| **Data Communication** | Flask-Smorest 0.45.0 |
| **ORM** | SQLAlchemy |
| **Code Formatter** | Black, Isort |
| **Version Control** | Git, GitHub |

---

> 이 프로젝트는 **Flask** 기반으로 구축된 웹 어플리케이션입니다.  
> 데이터베이스 관리는 **SQLAlchemy ORM**을 사용하여 객체 지향적으로 처리했으며,  
> **Flask-Migrate**를 통해 마이그레이션을 관리했습니다.  
> **Gunicorn**과 **Nginx**를 조합해 AWS EC2 서버에 배포하였고,  
> 코드 스타일은 **Black**과 **Isort**를 사용해 일관성 있게 관리했습니다.


# 6. Project Structure (프로젝트 구조)
```plaintext
project/
├── public/
│   ├── index.html           # HTML 템플릿 파일
│   └── favicon.ico          # 아이콘 파일
├── src/
│   ├── assets/              # 이미지, 폰트 등 정적 파일
│   ├── components/          # 재사용 가능한 UI 컴포넌트
│   ├── hooks/               # 커스텀 훅 모음
│   ├── pages/               # 각 페이지별 컴포넌트
│   ├── App.js               # 메인 애플리케이션 컴포넌트
│   ├── index.js             # 엔트리 포인트 파일
│   ├── index.css            # 전역 css 파일
│   ├── firebaseConfig.js    # firebase 인스턴스 초기화 파일
│   package-lock.json    # 정확한 종속성 버전이 기록된 파일로, 일관된 빌드를 보장
│   package.json         # 프로젝트 종속성 및 스크립트 정의
├── .gitignore               # Git 무시 파일 목록
└── README.md                # 프로젝트 개요 및 사용법
```

<br/>
<br/>

# 7. Development Workflow (개발 워크플로우)
## 브랜치 전략 (Branch Strategy)
우리의 브랜치 전략은 Git Flow를 기반으로 하며, 다음과 같은 브랜치를 사용합니다.

- Main Branch
  - 배포 가능한 상태의 코드를 유지합니다.
  - 모든 배포는 이 브랜치에서 이루어집니다.
  
- {name} Branch
  - 팀원 각자의 개발 브랜치입니다.
  - 모든 기능 개발은 이 브랜치에서 이루어집니다.

<br/>
<br/>

# 8. Coding Convention
## 문장 종료
```
// 세미콜론(;)
console.log("Hello World!");
```

<br/>


## 명명 규칙
* 상수 : 영문 대문자 + 스네이크 케이스
```
const NAME_ROLE;
```
* 변수 & 함수 : 카멜케이스
```
// state
const [isLoading, setIsLoading] = useState(false);
const [isLoggedIn, setIsLoggedIn] = useState(false);
const [errorMessage, setErrorMessage] = useState('');
const [currentUser, setCurrentUser] = useState(null);

// 배열 - 복수형 이름 사용
const datas = [];

// 정규표현식: 'r'로 시작
const = rName = /.*/;

// 이벤트 핸들러: 'on'으로 시작
const onClick = () => {};
const onChange = () => {};

// 반환 값이 불린인 경우: 'is'로 시작
const isLoading = false;

// Fetch함수: method(get, post, put, del)로 시작
const getEnginList = () => {...}
```

<br/>

## 블록 구문
```
// 한 줄짜리 블록일 경우라도 {}를 생략하지 않고, 명확히 줄 바꿈 하여 사용한다
// good
if(true){
  return 'hello'
}

// bad
if(true) return 'hello'
```

<br/>

## 함수
```
함수는 함수 표현식을 사용하며, 화살표 함수를 사용한다.
// Good
const fnName = () => {};

// Bad
function fnName() {};
```

<br/>

## 태그 네이밍
Styled-component태그 생성 시 아래 네이밍 규칙을 준수하여 의미 전달을 명확하게 한다.<br/>
태그명이 길어지더라도 의미 전달의 명확성에 목적을 두어 작성한다.<br/>
전체 영역: Container<br/>
영역의 묶음: {Name}Area<br/>
의미없는 태그: <><br/>
```
<Container>
  <ContentsArea>
    <Contents>...</Contents>
    <Contents>...</Contents>
  </ContentsArea>
</Container>
```

<br/>

## 폴더 네이밍
카멜 케이스를 기본으로 하며, 컴포넌트 폴더일 경우에만 파스칼 케이스로 사용한다.
```
// 카멜 케이스
camelCase
// 파스칼 케이스
PascalCase
```

<br/>

## 파일 네이밍
```
컴포넌트일 경우만 .jsx 확장자를 사용한다. (그 외에는 .js)
customHook을 사용하는 경우 : use + 함수명
```

<br/>
<br/>

# 9. 커밋 컨벤션
## 기본 구조
```
type : subject

body 
```

<br/>

## type 종류
```
feat : 새로운 기능 추가
fix : 버그 수정
docs : 문서 수정
style : 코드 포맷팅, 세미콜론 누락, 코드 변경이 없는 경우
refactor : 코드 리펙토링
test : 테스트 코드, 리펙토링 테스트 코드 추가
chore : 빌드 업무 수정, 패키지 매니저 수정
```

<br/>

## 커밋 이모지
```
== 코드 관련
📝	코드 작성
🔥	코드 제거
🔨	코드 리팩토링
💄	UI / style 변경

== 문서&파일
📰	새 파일 생성
🔥	파일 제거
📚	문서 작성

== 버그
🐛	버그 리포트
🚑	버그를 고칠 때

== 기타
🐎	성능 향상
✨	새로운 기능 구현
💡	새로운 아이디어
🚀	배포
```

<br/>

## 커밋 예시
```
== ex1
✨Feat: "회원 가입 기능 구현"

SMS, 이메일 중복확인 API 개발

== ex2
📚chore: styled-components 라이브러리 설치

UI개발을 위한 라이브러리 styled-components 설치
```

<br/>
<br/>

# 10. 컨벤션 수행 결과
<img width="100%" alt="코드 컨벤션" src="https://github.com/user-attachments/assets/0dc218c0-369f-45d2-8c6d-cdedc81169b4">
<img width="100%" alt="깃플로우" src="https://github.com/user-attachments/assets/2a4d1332-acc2-4292-9815-d122f5aea77c">
