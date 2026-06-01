# 👣 부산이음길
### 부산 지역 이동 약자를 위한 무장애 길찾기 서비스

![Generic badge](https://img.shields.io/badge/SSAFY-14th-blue.svg)
![Generic badge](https://img.shields.io/badge/Spring%20Boot-3.5-green.svg)
![Generic badge](https://img.shields.io/badge/Android-Kotlin-7F52FF.svg)
![Generic badge](https://img.shields.io/badge/GraphHopper-Routing-77B829.svg)

<br>

<div align="center">
  <img src="assets/readme/hero-main.png" width="60%">
  <br><br>
  <b>“부산의 복잡한 지형 위에서도, 이동 약자가 실제로 이동 가능한 길을 안내합니다.”</b> <br>
  접근성 데이터, 음성 안내, 시민 제보를 결합한 무장애 길찾기 서비스
</div>

---

## 🚀 MVP 기능

### 1. 무장애 경로 탐색 및 음성 안내 (Accessible Routing & Guidance)
사용자 유형과 접근성 데이터를 반영해 일반 최단 경로가 아닌, **실제 이동 가능한 경로**를 우선 안내합니다.

| 1. 목적지 설정 | 2. 무장애 경로 탐색 | 3. 경로 안내 |
| :---: | :---: | :---: |
| <img src="assets/readme/destination-search.png" height="300px"> | <img src="assets/readme/route-result.png" height="300px"> | <img src="assets/readme/navigation-guide.png" height="300px"> |
| 출발지/목적지와 사용자 조건을 입력 | 접근성 정보를 반영한 경로 후보 제공 | 단계별 경로 안내와 음성 안내 제공 |

<br>

### 2. 접근성 지도 정보 및 즐겨찾기 (Accessibility Map & Bookmark)
경로만 보여주는 것이 아니라, **장애인 화장실, 엘리베이터, 점자블록, 편의시설** 같은 접근성 정보를 지도에서 함께 제공합니다.

| 지도 홈 화면 | 접근성 시설 탐색 | 즐겨찾기 |
| :---: | :---: | :---: |
| <img src="assets/readme/home-map.png" height="300px"> | <img src="assets/readme/place-detail.png" height="300px"> | <img src="assets/readme/bookmark.png" height="300px"> |
| 현재 위치 중심 지도 홈 | 주변 시설/장소 상세 정보 확인 | 자주 가는 목적지를 저장하고 재사용 |

<br>

### 3. 장애물 제보 및 우회 경로 반영 (Hazard Report & Reroute)
사용자가 공사 구간, 점자블록 훼손, 보행 장애물 등을 제보하면, 운영자 검토 후 경로 탐색에 반영할 수 있습니다.

| 1. 제보 등록 | 2. 관리자 검토 | 3. 우회 경로 반영 |
| :---: | :---: | :---: |
| <img src="assets/readme/report-create.png" height="300px"> | <img src="assets/readme/admin-review.png" height="300px"> | <img src="assets/readme/reroute-result.png" height="300px"> |
| 앱에서 장애물 사진/위치 제보 | 관리자 화면에서 제보와 도로 속성 검토 | 위험 구간을 피한 우회 경로 재탐색 |

---

## 📱 User Flow Detail

### 👤 사용자 진입 및 모드 설정
온보딩과 사용자 유형 설정을 통해, 시각장애인·휠체어 사용자·고령자 등에게 맞는 안내 흐름을 제공합니다.

| 온보딩 | 사용자 유형 선택 | 홈 진입 |
| :---: | :---: | :---: |
| <img src="assets/readme/onboarding.png" width="400px"> | <img src="assets/readme/user-type.png" width="400px"> | <img src="assets/readme/home-map.png" width="400px"> |

### 🗺️ 경로 탐색 및 도착 흐름
경로 탐색 이후에는 지도, 안내 문구, 음성 정보를 조합해 실제 이동에 필요한 정보를 제공합니다.

| 목적지 설정 | 경로 안내 | 목적지 도착 |
| :---: | :---: | :---: |
| <img src="assets/readme/destination-search.png" width="400px"> | <img src="assets/readme/navigation-guide.png" width="400px"> | <img src="assets/readme/arrival.png" width="400px"> |

### 🛡️ 제보 및 운영자 반영 흐름
사용자 제보는 단순 저장에서 끝나지 않고, 관리자 검토와 경로 반영 워크플로까지 이어집니다.

| 제보 작성 | 관리자 지도 검토 | 반영 후 운영 |
| :---: | :---: | :---: |
| <img src="assets/readme/report-create.png" width="400px"> | <img src="assets/readme/admin-map.png" width="400px"> | <img src="assets/readme/admin-route-apply.png" width="400px"> |

---

## 🧠 핵심 기술 (GraphHopper + Accessibility Data)

GraphHopper 기반 라우팅 엔진에 접근성 속성 데이터를 결합해, 단순 최단 경로가 아니라 **이동 약자 관점에서 안전하고 실제로 이동 가능한 경로**를 계산합니다.

| Input (Route Request) | Output (Accessible Route) |
| :---: | :---: |
| <img src="assets/readme/route-input.png" height="400px"> | <img src="assets/readme/route-output.png" height="400px"> |

---

## 🛠 기술 스택 (Tech Stack)

### Architecture
![System Architecture](assets/readme/architecture.png)

### Detail

| 분류 | 기술 스택 | 비고 |
|:---:|:---|:---|
| **Frontend** | Kotlin, Android, Jetpack Compose, Material 3 | Android App |
| **Backend** | Java 21, Spring Boot 3.5, Spring Security, JPA | REST API |
| **Routing** | GraphHopper, PostGIS | 무장애 경로 계산 |
| **Data / AI** | Python | 음성/실험 코드 및 데이터 처리 |
| **Database** | PostgreSQL 16, Redis | Main DB / Cache |
| **Map / External** | Kakao Map, Kakao Local API, ODsay, Busan BIMS | 지도 / 장소 / 대중교통 |
| **Infra** | AWS EC2, Docker, Nginx, Jenkins, MinIO | 배포 / 운영 |
| **Monitoring** | Prometheus, Grafana, Loki, CloudWatch | 관측성 / 로그 |

---

## 🤖 기술 개요

※ 본 README에서는 전체 구현 중 핵심 개념만 설명합니다.

- **GraphHopper 기반 프로필 라우팅**
  - 사용자 유형별 보행 프로필 적용
  - SAFE / SHORTEST 후보 경로 조회

- **접근성 속성 기반 경로 보정**
  - 경사, 계단, 점자블록, 폭, 노면 정보 반영
  - 이동 약자 관점의 실제 이동 가능성 중심 탐색

- **TTS / 음성 안내**
  - 시각장애인을 고려한 단계별 음성 안내
  - 앱 사용 흐름에서 접근성 강화

- **Hazard Report 기반 재탐색**
  - 장애물 제보 지점을 회피 영역으로 반영
  - 기존 경로를 우회 경로로 재구성

---

## 📂 프로젝트 구조

```bash
S14P31E102/
├── FE/                    # Android 앱
├── BE/                    # Spring Boot API 서버
├── AI/                    # Python 실험 코드, 데이터 처리, 음성/분석 관련 작업
├── ADMIN/                 # 관리자 웹
├── INF/                   # 인프라 설정 자산
├── Docs/                  # PRD, 기획, 인프라, API, 회의록
├── scripts/               # make에서 호출하는 자동화 스크립트
├── docker-compose.local.yml
├── docker-compose.dev.yml
├── docker-compose.prod.yml
├── Makefile
└── README.md
```
## 빠른 시작

### Docker Compose로 실행

```bash
# 1. Git/Jira 및 로컬 개발 보조 설정
make init

# 2. 루트 환경 변수 파일 준비
# .env.local 또는 .env.dev 파일을 팀 내부 기준에 맞게 준비

# 3. 로컬 스택 실행
make local-up
```

### 접속 정보

| 서비스 | URL |
|--------|-----|
| Backend API | http://localhost:8080 |
| AI Server | http://localhost:5000 |
| GraphHopper | http://localhost:8989 |
| MinIO API | http://localhost:9000 |
| MinIO Console | http://localhost:9001 |

### 유용한 명령어

```bash
make local-logs
make local-down
make be-local-up
make ai-local-up
```

## 상세 문서

각 파트별 상세 내용은 하위 폴더의 README 또는 문서를 참고하세요.

| 문서 | 경로 |
|------|------|
| 루트 프로젝트 개요 | [README.md](README.md) |
| 백엔드 | [BE/README.md](BE/README.md) |
| 프론트엔드 | [FE/README.md](FE/README.md) |
| 인프라 | [INF/README.md](INF/README.md) |
| PRD | [Docs/PRD/2026-04-09_부산이음길_PRD.md](Docs/PRD/2026-04-09_부산이음길_PRD.md) |

## 포팅 매뉴얼

`exec/` 폴더에 배포 및 운영 관련 문서가 있습니다.

- [포팅 매뉴얼](exec/부산이음길__포팅매뉴얼.md)

## 팀 E102

SSAFY 14기 공통 프로젝트

| 이름 | 역할 | 담당 |
|------|------|------|
| 팀원 1 | Frontend | Android 앱 |
| 팀원 2 | Backend | API / 데이터 |
| 팀원 3 | Infra | Docker / AWS / Jenkins |
| 팀원 4 | AI | 음성/분석 및 데이터 |
| 팀원 5 | PM / Design | 기획 / UX |
| 팀원 6 | Full Stack | 제보 / 관리자 / 연동 |
