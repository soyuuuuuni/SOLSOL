# 🏦 2025 Shinhan Hackathon with SSAFY

#### 쏠SOL이들 (25.08.29 ~ 25.08.31)

**🔗 Repository:** [GitHub - solSOL-heycalendar](https://github.com/ZionArizona/SOLSOL)  
**🌐 Deployment:** [https://heycalendar.store](https://heycalendar.store)

---

## 📑 목차

- [프로젝트 개요](#overview)  
  - [팀원 소개](#team)  
  - [기획 배경](#background)  
- [서비스 소개](#service)  
  - [서비스 화면](#screens)  
- [프로젝트 구조](#structure)  
- [개발 환경 및 실행 방법](#setup)  
- [🐳 Docker 실행](#docker)

---

## 📌 프로젝트 개요 <a id="overview"></a>

### 1️⃣ 팀원 소개 <a id="team"></a>

| 권시온 | 김소연 | 신준호 | 정수형 |
|:-:|:-:|:-:|:-:|
| Leader, FrontEnd | BackEnd, FrontEnd | BackEnd, Frontend | BackEnd, Infra |

---

### 2️⃣ 기획 배경 <a id="background"></a>

***학생들의 장학금 탐색·신청 과정을 단순화하고, 대학 행정 업무 효율성을 높이고자 합니다.***

>
- 장학금 정보가 흩어져 있어 찾기 어려워요.  
- 신청 절차가 복잡하고 문서 제출이 불편해요.  
- 관리자는 학생별 지원 현황을 실시간으로 파악하기 어려워요.  

쏠SOL이들은 이 문제를 해결하기 위해  
**원스톱 장학금 통합 관리 플랫폼**을 제안합니다.  

---

## 🖥️ 서비스 소개 <a id="service"></a>

### 1️⃣ 서비스 화면 <a id="screens"></a>

| 사용자 페이지 | 관리자 페이지 |
|:--:|:--:|
| ![](https://github.com/ZionArizona/SOLSOL/blob/main/%EC%82%AC%EC%9A%A9%EC%9E%90%20%ED%8E%98%EC%9D%B4%EC%A7%80.png) | ![](https://github.com/ZionArizona/SOLSOL/blob/main/%EA%B4%80%EB%A6%AC%EC%9E%90%20%ED%8E%98%EC%9D%B4%EC%A7%80.png) |

- **사용자 앱 (모바일)**  
  - 학생: 장학금 검색, 신청, 문서 업로드  
  - 알림: 모집 일정·결과 안내  

- **관리자 웹 (Admin)**  
  - 장학금 공고 등록·수정  
  - 지원 현황 관리, 심사 및 승인  

---

## 🗂️ 프로젝트 구조 <a id="structure"></a>

```plaintext
apps/
├── backend/                # Spring Boot 백엔드 API 서버
├── frontend/
│   ├── Admin/              # React + Vite 기반 어드민 웹
│   └── User/               # React Native + Expo 기반 사용자 앱
├── nginx/                  # Nginx 리버스 프록시 설정
└── docker-compose.yml      # 전체 서비스 실행 설정
```

- `apps/backend`: Spring Boot로 구현된 백엔드 API 서버입니다.
- `apps/frontend/Admin`: React와 Vite로 구현된 어드민 웹 애플리케이션입니다.
- `apps/frontend/User`: React Native와 Expo로 구현된 사용자 모바일 애플리케이션입니다.
- `docker-compose.yml`: 전체 서비스를 Docker 환경에서 한 번에 실행하기 위한 설정 파일입니다.
- `nginx/`: Docker 환경에서 리버스 프록시 역할을 하는 Nginx 설정 파일입니다.

---

## ⚙️ 개발 환경 및 실행 방법 <a id="setup"></a>

### Backend (`apps/backend`)

**기술 스택**
| **BackEnd** | ![Java](https://img.shields.io/badge/Java-17-orange) ![Spring Boot](https://img.shields.io/badge/SpringBoot-3.3.3-green) ![MyBatis](https://img.shields.io/badge/ORM-MyBatis-red) ![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1) ![Gradle](https://img.shields.io/badge/Build-Gradle-02303A) |
|:-|:-|

**환경 설정**
1. JDK 17을 설치합니다.
2. `apps/backend/` 디렉토리로 이동합니다.
3. `.env` 파일을 생성하고 데이터베이스 연결 정보 등 필요한 환경 변수를 설정합니다.

**실행 방법**
```bash
./gradlew bootRun
```

**빌드 방법**
```bash
./gradlew build
```

---

### Frontend - Admin (`apps/frontend/Admin`)

**기술 스택**
| **FrontEnd(Admin)** | ![React](https://img.shields.io/badge/React-19-61DAFB) ![Vite](https://img.shields.io/badge/Build-Vite-646CFF) |
|:-|:-|

**환경 설정**
1. Node.js (LTS 버전 권장)를 설치합니다.
2. `apps/frontend/Admin/` 디렉토리로 이동합니다.
3. 필요한 패키지를 설치합니다.
   ```bash
   npm install
   ```

**개발 서버 실행**
```bash
npm run dev
```

**빌드 방법**
```bash
npm run build
```
빌드 결과물은 `dist` 디렉토리에 생성됩니다.

---

### Frontend - User (`apps/frontend/User`)

**기술 스택**
| **FrontEnd(User)** | ![React Native](https://img.shields.io/badge/ReactNative-Expo-blue) ![Expo](https://img.shields.io/badge/Expo-SDK--51-000020) |
|:-|:-|

**환경 설정**
1. Node.js (LTS 버전 권장)를 설치합니다.
2. `apps/frontend/User/` 디렉토리로 이동합니다.
3. 필요한 패키지를 설치합니다.
   ```bash
   npm install
   ```

**개발 서버 실행**
1. 사용자는 애뮬레이터에서 실행해야 합니다. 아래의 명령어를 통해 서버를 실행해 주세요.
- 애뮬레이터실행시 디바이스는 Medium Phone API 36.0을 사용해 주세요.
```bash
npx expo start
```
2. 애뮬레이터 실행 후 expo go에 입장 후 exp:/x.x.x.x:8081 입력해주세요. url은 npx expo start를 통해 확인하실 수 있습니다.
3. 1,2번 성공 시 개발한 서비스를 사용할 수 있습니다.

---

## 🐳 Docker를 이용한 전체 프로젝트 실행 <a id="docker"></a>

| **Infra** | ![Docker](https://img.shields.io/badge/Container-Docker-2496ED) ![Nginx](https://img.shields.io/badge/Proxy-Nginx-009639) ![AWS EC2](https://img.shields.io/badge/AWS-EC2-FF9900?logo=amazon-aws&logoColor=white) ![AWS RDS](https://img.shields.io/badge/AWS-RDS-527FFF?logo=amazon-aws&logoColor=white) ![AWS S3](https://img.shields.io/badge/AWS-S3-569A31?logo=amazon-aws&logoColor=white) |
|:-|:-|


**전제 조건**
- Docker
- Docker Compose

**실행 방법**
1. 프로젝트 루트 디렉토리에서 아래 명령어를 실행하여 모든 서비스를 한 번에 빌드하고 실행합니다.
   ```bash
   docker-compose up --build -d
   ```
2. `docker-compose.yml`에서 참조하는 환경 변수(예: `.env` 파일)가 올바르게 설정되어 있는지 확인하세요.

**서비스 종료**
```bash
docker-compose down
```
