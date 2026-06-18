# 레츠꾸
> 구미 지역을 탐방하며 미션을 수행하는 AI 미션형 지역 탐방 서비스

https://github.com/user-attachments/assets/44c1e8a4-e3b3-42ea-8406-28683caf2a4d

<br/>

## 주요 기능
- 카카오 OAuth 기반 로그인 및 JWT access token 인증
- 메인 화면에서 날씨, 보유 포인트, 사용자 프로필 정보 제공
- Google Maps 기반 미션 지도와 카테고리별 커스텀 마커 표시
- 지도에서 미션 선택, 상세 확인, 미션 수락
  - 수락한 미션은 GPS 위치 인증과 AI 기반 사진 인증을 통해 완료
- 브라우저 Geolocation API를 활용한 GPS 위치 인증
- Presigned URL 기반 이미지 업로드 및 AI 사진 인증
- SSE(Server-Sent Events)를 활용한 사진 인증 결과 실시간 수신
- 미션 완료 후 리뷰 작성 및 미션별 리뷰 조회
- 작성 가능한 리뷰와 작성 완료 리뷰를 구분한 활동 내역 관리
- 포인트 기반 리워드 샵 상품 교환

<br/>

## 사용자 흐름
```mermaid
flowchart TD
  A["카카오 로그인"] --> B["메인 화면"]
  B --> C["날씨와 보유 포인트 확인"]
  B --> D["미션 수행하기"]
  D --> E["지도에서 미션 핀 선택"]
  E --> F["미션 상세 확인"]
  F --> G["미션 수락"]
  G --> H["GPS 위치 인증"]
  H --> I{"위치 인증 성공"}
  I -->|실패| H
  I -->|성공| J["사진 가이드 확인"]
  J --> K["사진 촬영 또는 업로드"]
  K --> L["AI 이미지 인증"]
  L --> M{"사진 인증 성공"}
  M -->|실패| K
  M -->|성공| N["미션 완료"]
  N --> O["리뷰 작성"]
  N --> P["포인트 획득"]
  P --> Q["리워드 샵"]
  Q --> R["상품권 또는 제휴 쿠폰 교환"]
  R --> S["내 지갑에서 쿠폰 확인"]
```
<br/>

## 기술 스택
![React](https://img.shields.io/badge/React-19.1.0-61DAFB?style=for-the-badge&logo=react&logoColor=000000)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7.0.4-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![React Router](https://img.shields.io/badge/React%20Router-7.7.1-CA4245?style=for-the-badge&logo=reactrouter&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-1.11.0-5A29E4?style=for-the-badge&logo=axios&logoColor=white)
![Google Maps](https://img.shields.io/badge/Google%20Maps-1.2.0-4285F4?style=for-the-badge&logo=googlemaps&logoColor=white)
![React Toastify](https://img.shields.io/badge/React%20Toastify-11.0.5-FF9800?style=for-the-badge)
![Server Sent Events](https://img.shields.io/badge/Server--Sent%20Events-1.0.31-222222?style=for-the-badge)
![React Icons](https://img.shields.io/badge/React%20Icons-5.5.0-E91E63?style=for-the-badge&logo=react&logoColor=white)
![CSS Modules](https://img.shields.io/badge/CSS%20Modules-000000?style=for-the-badge&logo=cssmodules&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-9.30.1-4B32C3?style=for-the-badge&logo=eslint&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-Deploy-000000?style=for-the-badge&logo=vercel&logoColor=white)
