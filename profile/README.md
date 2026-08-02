<div align="center">

# 🌌 GitGalaxy

### GitHub 오픈소스 생태계를 **3D 나선 은하**로 시각화하는 인터랙티브 웹 서비스

별 하나 = 저장소 하나 · 언어별 나선팔 · 활동 점수로 결정되는 궤도 · AI(RAG) 분석

<br/>

[![Frontend](https://img.shields.io/badge/Frontend-React%20%7C%20Three.js-000000?style=for-the-badge&logo=react)](https://github.com/2026-teecher-team-b/frontend)
[![Backend](https://img.shields.io/badge/Backend-Spring%20Boot%20%7C%20Java%2021-6DB33F?style=for-the-badge&logo=springboot)](https://github.com/2026-teecher-team-b/backend)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](https://github.com/2026-teecher-team-b)

</div>

---


## ✨ 한눈에 보기

GitGalaxy는 GitHub 오픈소스 저장소를 **WebGL 3D 은하계**로 그려냅니다.

- 🌟 **별 = 저장소** — 언어별로 나선팔이 나뉘고, 활동 점수가 높을수록 은하 코어 근처에 배치
- 🌀 **실시간 물리 엔진** — Web Worker 기반 O(n) 처리로 별들이 나선팔 위를 공전
- 🤖 **AI RAG 분석** — Vertex AI 임베딩 + pgvector 기반 저장소 의미 분석
- 🔐 **GitHub OAuth** — 로그인 후 즐겨찾기 저장
- 📊 **24시간 점수 추이** — GH Archive 데이터 배치 수집·정규화
- 📈 **점수 변화 이유 분석** - 레포의 상승/하락 이유를 issue/pr/commit 활동 데이터를 바탕으로 분석
 
---
## Demo


### 시작 페이지

<img width="710" height="376" alt="스크린샷 2026-08-02 오전 9 55 34" src="https://github.com/user-attachments/assets/df864a6d-772c-46b2-a978-2ec1b261127c" />


### 메인 페이지

<img width="710" height="376" alt="Adobe Express - 화면 기록 2026-08-02 오전 10 13 35 (1)" src="https://github.com/user-attachments/assets/f17d345a-420b-415d-b1c1-4c685f6cc76f" />


### 언어별필터

<img width="710" height="376" alt="화면 기록 2026-08-02 오전 10 14 40" src="https://github.com/user-attachments/assets/1341c558-4672-4b67-adea-e15c90fcc42e" />



### 레포 상세 페이지

<img width="710" height="376" alt="화면 기록 2026-08-02 오전 10 13 56" src="https://github.com/user-attachments/assets/f544fde6-41bc-4362-897f-c8f3a027dd86" />

---

## 🛠️ 기술 스택

| 영역 | 기술 |
|------|------|
| **Frontend** | ![React](https://img.shields.io/badge/-React%2018-61DAFB?logo=react&logoColor=black) ![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?logo=typescript&logoColor=white) ![Three.js](https://img.shields.io/badge/-Three.js-000000?logo=three.js) ![Vite](https://img.shields.io/badge/-Vite-646CFF?logo=vite&logoColor=white) ![Zustand](https://img.shields.io/badge/-Zustand-433E38) ![Tailwind](https://img.shields.io/badge/-Tailwind-06B6D4?logo=tailwindcss&logoColor=white) |
| **Backend** | ![Java](https://img.shields.io/badge/-Java%2021-007396?logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/-Spring%20Boot-6DB33F?logo=springboot&logoColor=white) ![Spring Security](https://img.shields.io/badge/-OAuth2-6DB33F?logo=springsecurity&logoColor=white) |
| **Data** | ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL%20%2B%20pgvector-4169E1?logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/-Redis-DC382D?logo=redis&logoColor=white) ![Elasticsearch](https://img.shields.io/badge/-Elasticsearch-005571?logo=elasticsearch&logoColor=white) |
| **AI** | ![Vertex AI](https://img.shields.io/badge/-Vertex%20AI-4285F4?logo=googlecloud&logoColor=white) (Gemini · 임베딩 · RAG) |
| **Infra** | ![Docker](https://img.shields.io/badge/-Docker-2496ED?logo=docker&logoColor=white) ![Nginx](https://img.shields.io/badge/-Nginx-009639?logo=nginx&logoColor=white) ![Prometheus](https://img.shields.io/badge/-Prometheus-E6522C?logo=prometheus&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white)|

---

## 🗂️ 레포지토리

| 레포 | 설명 | 스택 |
|------|------|------|
| [**frontend**](https://github.com/2026-teecher-team-b/frontend) | 3D 은하 시각화 웹 클라이언트 | React · Three.js · R3F |
| [**backend**](https://github.com/2026-teecher-team-b/backend) | REST API · 데이터 수집 배치 · RAG AI | Spring Boot · Java 21 |
| [**gitgalaxy-ppt**](https://github.com/2026-teecher-team-b/gitgalaxy-ppt) | 프로젝트 발표 자료 | — |

---

## 🏗️ 시스템 아키텍처

<img width="1262" height="645" alt="image" src="https://github.com/user-attachments/assets/a9f3b2d6-1c78-4a73-b4a9-b503196e4910" />


```
GitHub / GH Archive
          │  (Batch Collection)
          ▼
   ┌─────────────────┐    pgvector / Redis / Elasticsearch
   │  Spring Boot    │◀──────────────────────────────────┐
   │  REST API + RAG │── Vertex AI (Gemini / Embedding)  │
   └────────┬────────┘                                   │
            │ GET /repos / /repos/rag / OAuth            │
            ▼                                            │
   ┌─────────────────┐                                   │
   │  React Frontend │    physicsStore (Module Singleton)│
   │  R3F + Three.js │── Web Worker (Zero-copy Float32)  │
   │  InstancedMesh  │    2000 Stars (1 Draw Call)       │
   └─────────────────┘                                   │
            └────────────────────────────────────────────┘
```

---

## 👥 Team B

<div align="center">

| [<img src="https://github.com/hippocampez.png" width="80" /><br/>**yumin**](https://github.com/hippocampez) | [<img src="https://github.com/HyeonHoLe2.png" width="80" /><br/>**HyeonHoLe2**](https://github.com/HyeonHoLe2) | [<img src="https://github.com/kimdoyoung1110.png" width="80" /><br/>**Do Young**](https://github.com/kimdoyoung1110) | [<img src="https://github.com/ukongee.png" width="80" /><br/>**박유경**](https://github.com/ukongee) |
|:---:|:---:|:---:|:---:|

</div>

---

<div align="center">

**2026 Teecher · Team B** · Made with 🌌 and ☕

</div>
