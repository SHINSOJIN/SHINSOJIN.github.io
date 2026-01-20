+++
author = "Sojin Shin"
title = "POLISTAR, 정치인과 기업인들을 위한 여론 보고서"
date = "2024-02-08"
description = "여론 조사 결과와 정치인/기업인과 관련된 뉴스를 분석하여 데일리 리포트를 생성해주는 서비스"
tags = [
"next",
"typescript",
"frontend",
]
categories = [
"project",
]  
image = "polistar-tutorial.png"
+++

## 기술 스택
- **프론트엔드 :**
  <img src="https://img.shields.io/badge/typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" style="display:inline;">
  <img src="https://img.shields.io/badge/next-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="badge">
  <img src="https://img.shields.io/badge/mui-007FFF?style=for-the-badge&logo=mui&logoColor=white" style="display:inline;">
  <img src="https://img.shields.io/badge/axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white" style="display:inline;">

## 이미지 모아보기

|             로그인             |         메인(리포트)         |
|:---------------------------:|:-----------------------:|
|  ![image](https://velog.velcdn.com/images/jane20180/post/b1e9b1cf-270c-4ba8-8e79-9153230f0abc/image.gif)  | ![image](https://velog.velcdn.com/images/jane20180/post/f89789d8-75bb-4d06-ae8f-70863493ce2d/image.gif) |
|            뉴스 목록            |          문의사항           |
| ![image](https://velog.velcdn.com/images/jane20180/post/f3250432-605d-4ca9-80f4-27a7904d0e61/image.gif) | ![image](https://velog.velcdn.com/images/jane20180/post/e6134cda-bfed-4161-8eb6-e2dd81146769/image.gif)  |



## 설명
당일 보도된 많은 언론사의 정치, 기업뉴스와 여론 조사 결과를 인공지능이 분석하여 대상자의 리포트를 생성해주는 서비스입니다.  
하루에 두번, 대상자에 대한 최신 정보와 행보를 생성형 AI를 통해 리포트를 생성하고, 관련 뉴스를 그루핑하여 보여줍니다.  

[//]: # ([여기]&#40;http://dev-www.newssalad.com:8282/&#41;를 클릭하여 프로젝트를 확인할 수 있습니다.)
[여기](https://apps.apple.com/kr/app/polistar/id6476597198)를 클릭하여 App을 확인할 수 있습니다.  
(단, pc 환경에서는 접속할 수 없습니다. )


## 기능

### 공통
• 전용 코드를 통해 구독자와 당사자 구분  
• 소속(정당, 기업, 지역)에 따른 리포트 배경색 관리  
• 구독자에게 신규 뉴스 PUSH 알림 발송  
• 당사자(정치/기업인)가 직접 사용자에게 보여질 뉴스를 관리할 수 있음

### 리포트
• 인물에 대한 실시간 뉴스 제공   
• 자사 신규 엔진을 이용하여 인물에 대한 커스텀 리포트 생성  
• URL 공유를 통해 누구나 자유롭게 인물 리포트 조회(구독) 가능  

### 뉴스
• 카테고리 별(정당/인물/지역) 뉴스 그루핑  
• 원하는 조건을 필터링하여 뉴스 목록 조회 가능  
• 연관 뉴스가 있다면 함께 확인 가능  
• 내가 조회했던 뉴스의 경우 읽음     
• 자사 언론사를 통해 단독 뉴스 보도 가능  

### 유지보수
• 자사 발행 뉴스 데이터와 연동

## 어려웠던 점 / 배운점

### Next.js를 채택 이유
CSR은 초기 로딩 속도가 빠르고, 사용자와의 상호작용이 매끄럽다는 장점이 있지만, 검색 엔진 최적화가 어려우며, 초기 로딩 시간이 길어지는 단점도 있습니다. 

사실 리액트가 익숙했고, CSR 방식만 사용해보았기 때문에 장점과 단점에 크게 공감하지 못했습니다.  
이번 프로젝트를 통해 SSR을 접해보고 싶은 목표가 있어 React의 프레임워크인 Next를 사용해보았습니다.
심지어 CSR과 SSR 중에 선택해서 사용할 수 있다니 첫눈에 보기엔 안 쓸 이유가 없어보였습니다. 
(물론 React에서도 서버컴포넌트를 지원하긴 하지만, Next와 비교했을 때 자료나 네임밸류에서 밀린다고 판단하였습니다.)


### 디버깅
가장 큰 차이라고 한다면 디버깅에 있었습니다.  
React에서는 `console.log`를 통해 컴포넌트의 상태 및 데이터를 쉽게 확인할 수 있었습니다.  
하지만 Next에서는 서버에서 HTML이 완성되어 클라이언트로 전송되는 형태이기 때문에, 일반적인 방법으로는 console.log를 통한 디버깅이 어려웠습니다.  
물론 검색을 통해 Next에서도 디버깅을 하는 여러가지 방법이 있다는 것을 알게되었지만, 처음에는 낯설었습니다. 


### 동적 라우팅 페이지 배포시 404 페이지 랜더링
useRouter를 통해 이동하는 경우에는 문제가 없었으나, 새로고침을 하거나 브라우저에서 직접 url을 입력하는 경우에는 404 페이지로 리다이렉팅 되었습니다.  
찾아보니 router로 이동할 때는 특정폴더의 page.tsx 파일을 찾아 보여주지만 직접 url을 입력하는 경우 url파라미터명.tsx파일을 찾기에 나타난 에러였습니다.  
다시말해 로그인 페이지를 라우팅을 통해 이동하면 `login/page.ts`를 찾는데 url을 입력하면 `login.ts`파일 찾으려고 합니다. 

이에 따른 해결방법은 
- getStaticPaths, getStaticProps 함수를 사용해서 빌드시 정적 페이지를 모두 생성
- 동적 라우팅이 아닌 정적라우팅 생성하기
였습니다. 

프로젝트 특성 상 1000여명이 넘는 사용자(정치인)의 페이지를 생성해야했고, 심지어 사용자가 추가될 때마다 새로 빌드해야했으므로 첫번째 방법은 현실적으로 불가능하다고 판단했습니다.  
물론 첫번째 방법이 조금 더 올바른 해결 방법인 것은 알았으나, 배포를 코 앞에 두고 있었기 때문에 두번째 방법을 채택하였습니다. 
따라서 SSG 방식을 채택하여 빌드 시에 미리 HTML파일을 생성하고 있습니다. 


### 빌드/배포 관련 이슈
빌드를 하면 `Type error: Property 'href' does not exist on type '{ name: string; }'`라는 메세지가 뜨면서 빌드가 중단되었습니다.  
자바스크립트 대신 이번 프로젝트에서는 타입스크립트를 사용했는데, 원인은 알고 있었지만 빌드를 안해줄 것이라고 생각은 못했습니다.
데드라인이 일주일 남짓 남은 시점에서 배포를 하는 것이 더 우선이라고 판단하여 숙제로 남겨두고 타입 체크하는 단계를 패스하도록 옵션을 추가하였습니다.

그렇게 build는 성공하였으나 .next 파일에서는 `index.html`파일을 찾을 수 없었습니다.  
yarn start라는 명령어를 통해 out이라는 정적 파일을 모아둔 디렉토리를 생성할 수 있었고, 그 디렉토리에서 index.html을 찾을 수 있었습니다. 


### 아쉬운 점과 배운점
신중한 검토 없이 Next가 ‘좋다더라’라는 말만 듣고 바로 선택했던 것이 돌이켜 생각해보면 실수라고 생각합니다.
예상과 달리 React와 차이점이 많았고, 프로젝트 개발 일정이 약 한달 정도로 촉박한 편이었습니다.  
서버와 클라이언트 사이드의 구분을 명확히 이해하고 적절한 구조를 설계할 시간이 부족하여, 제게 좀 더 익숙한 길을 선택하는 것이 아쉬웠습니다.
대부분의 컴포넌트에 `use client`를 선언하여 사용하여, 사실상 Next를 채택한 의미가 반감되었던 것 같습니다.

하지만 이를 계기로 
- 새로운 기술을 도입할 때에는 충분한 시간과 검토가 필요하다.
- 일정이 급하다면 익숙한 것부터 천천히 마이그레이션 할 필요가 있다.
- SSR과 SSG의 개념에 대해 알 수 있는 기회였다.
- Next에서 무엇을 공부해야하고, 내게 부족한 지식이 무엇인지 알아 볼 기회였다.

라는 것을 배울 수 있었습니다. 
