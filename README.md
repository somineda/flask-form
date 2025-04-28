## 📸 실행 화면
  
### 초기 화면 페이지
<img width="888" alt="스크린샷 2025-04-28 오전 10 46 08" src="https://github.com/user-attachments/assets/ce54b510-a243-4467-a48f-b5786e5d002f" />


### 회원가입 페이지
<img width="896" alt="스크린샷 2025-04-27 오후 9 51 31" src="https://github.com/user-attachments/assets/a9472abf-5063-4305-ba4a-4b68757a39c0" />

### 설문 참여 페이지
<img width="1187" alt="스크린샷 2025-04-27 오후 9 52 54" src="https://github.com/user-attachments/assets/38f891d6-9060-4853-9b11-8bb73d163eba" />
<img width="1187" alt="스크린샷 2025-04-27 오후 9 52 47" src="https://github.com/user-attachments/assets/2f2c8942-47d9-4747-9a78-1a8006292a10" />

### 설문 결과 페이지
<img width="1187" alt="스크린샷 2025-04-27 오후 9 52 39" src="https://github.com/user-attachments/assets/990b852b-945a-41f4-8959-af05a53eac7b" />

### 관리자 페이지
![스크린샷 2025-04-27 오후 5 35 54](https://github.com/user-attachments/assets/b1a5da45-4341-49a1-9f34-cab61c4bb1b1)






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


# 5. Project Structure (프로젝트 구조)
```plaintext
oz_form/
├── app/
│   ├── static/
│   │   └── images/            # 팀 로고 이미지 등 정적 파일
│   ├── templates/             # HTML 템플릿 파일
│   │   ├── index.html
│   │   ├── signup.html
│   │   ├── quiz.html
│   │   ├── question.html
│   │   ├── results.html
│   │   └── admin_login.html
│   ├── services/              # 서비스 로직 (DB 조작 및 비즈니스 로직)
│   │   ├── answers.py
│   │   ├── choices.py
│   │   ├── images.py
│   │   ├── questions.py
│   │   ├── result_service.py
│   │   └── users.py
│   ├── __init__.py            # Flask 앱 초기화 파일
│   ├── api_routes.py          # API용 라우터
│   ├── models.py              # SQLAlchemy 모델 정의
│   ├── routes.py              # 웹페이지 라우터
│   └── seeds.py               # 초기 데이터 삽입 스크립트
├── migrations/                # DB 마이그레이션 파일
│   ├── alembic.ini
│   ├── env.py
│   ├── script.py.mako
│   └── versions/
├── oz_form/                   # 추가 설정 디렉토리
├── re_images/                 # (임시) 이미지 저장 폴더
├── .gitignore                 # Git에 업로드 제외 파일 목록
├── config.py                  # 앱 설정 파일
├── my-key.pem                 # EC2 접속 키파일 (⚠️ Git 업로드 금지)
├── README.md                  # 프로젝트 개요 및 사용법
├── requirements.txt           # 필요한 라이브러리 목록
├── run.py                     # 로컬 서버 실행 파일
├── run_seeds.py               # DB seed 데이터 삽입 실행 파일
└── wsgi.py                    # Gunicorn용 WSGI 엔트리포인트

```

<br/>
<br/>

### 📁 Directory Details (디렉토리 상세 설명)

- `app/` : 메인 어플리케이션 디렉토리
- `services/` : 비즈니스 로직 분리 (DB 조회, 저장, 통계처리 등)
- `static/` : 정적 파일 (팀 로고 이미지 등)
- `templates/` : HTML 템플릿 파일
- `migrations/` : 데이터베이스 마이그레이션 파일
- `oz_form/` : 추가로 설정한 폴더
- `re_images/` : 임시 이미지 저장 폴더
- `wsgi.py` : 서버 실행을 위한 WSGI 엔트리포인트
- `run.py` : 로컬 테스트용 실행 스크립트
- `requirements.txt` : 프로젝트 의존성 목록
- `my-key.pem` : 서버 접속용 키파일 (업로드 금지)
