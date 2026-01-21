+++
author = "Sojin Shin"
title = "웨딩북, 예비부부를 위한 종합 결혼 준비 플랫폼"
date = "2024-06-01"
description = "웨딩홀, 스드메 등 다양한 결혼 정보를 제공하고 업체 비교 및 예약, 후기 확인을 할 수 있는 종합 결혼 준비 플랫폼"
categories = [
"project",
]
tags = [
"next",
"react",
"typescript",
"redux",
"frontend",
"react-query",
"zustand",
"zod",
]
image = "logo.png"
+++

## 기술 스택
- **프론트엔드 :**
  <img src="https://img.shields.io/badge/typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" style="display:inline;">
  <img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=white" style="display:inline;">
  <img src="https://img.shields.io/badge/next-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="badge">
  <img src="https://img.shields.io/badge/redux-764ABC?style=for-the-badge&logo=redux&logoColor=white" style="display:inline;">
  <img src="https://img.shields.io/badge/scss-CC6699?style=for-the-badge&logo=sass&logoColor=white" style="display:inline;">

## 설명
[웨딩북](https://www.weddingbook.com/home)은 예비부부를 위한 종합 결혼 준비 플랫폼으로, 웨딩홀, 스드메(스튜디오, 드레스, 메이크업) 등 다양한 결혼 정보를 제공하고 업체 비교 및 예약, 후기 확인을 할 수 있게 돕는 서비스입니다. 단순 정보 제공을 넘어, 업체 관리 솔루션(웨딩북 Biz)을 제공하여 결혼 시장의 혁신을 이끌고 있으며, 데이터 기반으로 맞춤형 서비스를 제공합니다.

## 담당 업무

### 웨딩홀 파트 신규 기능 및 유지보수
- [웨딩홀 리뉴얼 FE 담당](https://www.weddingbook.com/weddinghall/search?hidetab=true)
- [방문예약/즉시계약](https://www.weddingbook.com/booking/real-time/search?hidetop=true) 가능한 예약 시스템 구현
- 예약 일정 관리 및 알림 기능 개발
- 보증금/계약금 결제 시스템 연동

### 예산 관리 기능
- 예비부부 결혼 예산 관리 기능 개발
- 카테고리별 예산 설정 및 추적 기능 구현
- 예산 대비 실제 지출 현황 시각화

### 청첩장 기능
- 청첩장 메인 화면 개발
- 청첩장 관리화면 개발
- 청첩장 공유 및 QR코드 생성 기능 개발

### 유지보수
- 웨딩홀 어드민 페이지 유지보수
- 기존 기능 개선 및 버그 수정
- 성능 최적화 작업

### 마이그레이션
- React에서 Next.js로 마이그레이션
- 기존 코드베이스 리팩토링
- SSR/SSG 적용을 통한 성능 개선

## 어려웠던 점 / 배운점

### 협업 - 코드 컨벤션의 중요성
시니어와 주니어로 구성된 팀에서 처음으로 본격적인 협업을 경험했습니다.  
이전까지는 개인 프로젝트나 소규모 팀에서 작업했기 때문에, 코드 스타일이나 네이밍 규칙에 대한 명확한 기준이 없었습니다.  
하지만 여러 명이 함께 작업하는 환경에서는 각자 다른 스타일로 코드를 작성하면 코드 리뷰 시간이 길어지고, 유지보수가 어려워진다는 것을 깨달았습니다.

팀 내에서 코드 컨벤션을 정하고, ESLint와 Prettier를 도입하여 일관된 코드 스타일을 유지하도록 했습니다.  
또한 코드 리뷰를 통해 컨벤션 준수 여부를 확인하고, 서로의 코드를 이해하는 시간을 가졌습니다.  
이를 통해 코드의 가독성이 향상되었고, 새로운 팀원이 프로젝트에 합류했을 때도 빠르게 적응할 수 있었습니다.

이 경험을 통해 협업에서는 기술적 역량뿐만 아니라, 팀원들과의 소통과 일관된 코드 작성이 얼마나 중요한지 배울 수 있었습니다.

### 본격적인 Next.js 사용
이전 프로젝트에서는 주로 React를 사용하여 CSR(Client-Side Rendering) 방식으로 개발했습니다.  
하지만 웨딩북 프로젝트에서는 SEO 최적화와 초기 로딩 속도 개선을 위해 Next.js를 도입하게 되었습니다.

Next.js를 처음 사용하면서 가장 큰 변화는 서버 컴포넌트와 클라이언트 컴포넌트의 구분이었습니다.  
서버에서 렌더링되는 컴포넌트와 클라이언트에서만 동작하는 컴포넌트를 명확히 구분해야 했고,  
각각의 특성에 맞게 상태 관리나 데이터 페칭 방식을 다르게 접근해야 했습니다.

또한 SSR(Server-Side Rendering)과 SSG(Static Site Generation)의 차이를 이해하고,  
페이지의 특성에 따라 적절한 렌더링 방식을 선택하는 것이 중요하다는 것을 배웠습니다.  
예를 들어, 정적인 정보 페이지는 SSG를 사용하고, 사용자별로 다른 내용을 보여줘야 하는 페이지는 SSR을 사용했습니다.

마이그레이션 과정에서 기존 React 코드를 Next.js에 맞게 리팩토링하는 작업도 진행했습니다.  
라우팅 방식의 변경, 이미지 최적화, 메타데이터 관리 등 Next.js의 기능을 활용하여  
코드의 품질과 성능을 개선할 수 있었습니다.

이 프로젝트를 통해 Next.js의 강력한 기능들을 경험하고,  
프론트엔드 프레임워크의 선택이 프로젝트의 성공에 얼마나 중요한 영향을 미치는지 배울 수 있었습니다.
