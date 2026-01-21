# 🍒 포트폴리오 블로그

개발 여정을 기록하고 프로젝트를 소개하는 개인 포트폴리오 블로그입니다.

## 🌐 배포 주소

**🔗 [https://shinsojin.github.io/](https://shinsojin.github.io/)**

## 📋 프로젝트 소개

이 블로그는 Hugo 정적 사이트 생성기를 사용하여 구축된 포트폴리오 블로그입니다. 개발 프로젝트, 학습 내용, 그리고 개발 여정을 기록하고 공유하기 위한 목적으로 제작되었습니다.

### 주요 특징

- ✨ **모던한 UI/UX**: Hugo Theme Stack 테마를 기반으로 한 깔끔하고 반응형 디자인
- 🌍 **다국어 지원**: 영어, 중국어 지원
- 🚀 **빠른 로딩 속도**: 정적 사이트 생성으로 최적화된 성능
- 📱 **반응형 디자인**: 모바일, 태블릿, 데스크톱 모든 기기에서 최적화된 경험
- 🔍 **검색 기능**: 내장된 검색 기능으로 콘텐츠 검색 가능
- 🎨 **다크 모드**: 자동/라이트/다크 모드 지원
- 📝 **카테고리 및 태그**: 프로젝트, 토이 프로젝트, 학습 내용 등으로 분류

## 🛠 기술 스택

### 핵심 기술
- **정적 사이트 생성기**: [Hugo](https://gohugo.io/) v0.122.0
- **테마**: [Hugo Theme Stack](https://github.com/CaiJimmy/hugo-theme-stack)
- **스타일링**: SCSS (Dart Sass)
- **빌드 도구**: Hugo CLI

### 배포 및 CI/CD
- **호스팅**: GitHub Pages
- **CI/CD**: GitHub Actions
- **워크플로우**: 자동 빌드 및 배포 파이프라인

### 사용된 GitHub Actions
- `actions/checkout@v6` - 코드 체크아웃
- `actions/configure-pages@v5` - GitHub Pages 설정
- `actions/upload-pages-artifact@v3` - 빌드 아티팩트 업로드
- `actions/deploy-pages@v4` - GitHub Pages 배포

## 📁 프로젝트 구조

```
SHINSOJIN.github.io/
├── .github/
│   └── workflows/
│       └── hugo.yaml          # GitHub Actions CI/CD 설정
├── archetypes/                # Hugo 콘텐츠 템플릿
├── assets/                    # 정적 자산 (이미지, JS 설정 등)
│   ├── me.jpg                 # 프로필 이미지
│   └── jsconfig.json
├── content/                   # 블로그 콘텐츠
│   ├── _index.md             # 홈페이지
│   ├── _index.zh-cn.md       # 중국어 홈페이지
│   ├── categories/           # 카테고리 페이지
│   │   ├── lesson/           # 학습 카테고리
│   │   ├── project/          # 프로젝트 카테고리
│   │   └── toy-project/      # 토이 프로젝트 카테고리
│   ├── page/                 # 일반 페이지
│   └── post/                 # 블로그 포스트
│       ├── ai-demo/          # AI 데모 프로젝트
│       ├── plog/             # Plog 프로젝트
│       ├── newssum/          # NewsSum 프로젝트
│       └── ...               # 기타 프로젝트들
├── public/                    # 빌드된 정적 파일 (자동 생성)
├── resources/                 # Hugo 리소스 캐시 (자동 생성)
├── themes/                    # Hugo 테마
│   └── hugo-theme-stack/     # 사용 중인 테마
├── hugo.toml                  # Hugo 설정 파일
├── netlify.toml               # Netlify 배포 설정 (선택사항)
└── README.md                  # 프로젝트 문서
```

## 🚀 로컬 개발 환경 설정

### 사전 요구사항

- [Hugo Extended](https://gohugo.io/installation/) v0.122.0 이상
- [Dart Sass](https://sass-lang.com/install) (테마 스타일링용)
- Git

### 설치 및 실행

1. **저장소 클론**
   ```bash
   git clone https://github.com/SHINSOJIN/SHINSOJIN.github.io.git
   cd SHINSOJIN.github.io
   ```

2. **Hugo 설치** (macOS)
   ```bash
   brew install hugo
   ```

3. **Dart Sass 설치** (macOS)
   ```bash
   brew install sass/sass/dart-sass
   ```

4. **로컬 서버 실행**
   ```bash
   hugo server
   ```
   
   또는 개발 모드로 실행 (변경사항 자동 반영):
   ```bash
   hugo server -D
   ```

5. **브라우저에서 확인**
   ```
   http://localhost:1313
   ```

## 🏗 빌드 방법

### 프로덕션 빌드

```bash
hugo --gc --minify
```

빌드된 파일은 `public/` 디렉토리에 생성됩니다.

### 빌드 옵션 설명

- `--gc`: 사용하지 않는 파일 정리 (garbage collection)
- `--minify`: HTML, CSS, JS 파일 최소화
- `--baseURL`: 배포 URL 설정 (프로덕션에서는 자동 설정됨)

## 🔄 CI/CD 파이프라인

이 프로젝트는 GitHub Actions를 사용하여 완전 자동화된 CI/CD 파이프라인을 구축했습니다.

### 워크플로우 개요

**파일 위치**: `.github/workflows/hugo.yaml`

### 트리거 조건

- **자동 실행**: `master` 브랜치에 push 시 자동 실행
- **수동 실행**: GitHub Actions 탭에서 `workflow_dispatch`로 수동 실행 가능

### 파이프라인 단계

#### 1️⃣ Build Job (빌드 작업)

**환경**: `ubuntu-latest`

**단계별 실행 순서**:

1. **Hugo CLI 설치**
   - Hugo Extended v0.122.0 설치
   - SCSS 컴파일을 위한 확장 기능 포함

2. **Dart Sass 설치**
   - 테마의 SCSS 파일 컴파일을 위한 Sass 컴파일러 설치

3. **코드 체크아웃**
   - `actions/checkout@v6` 사용
   - 서브모듈 포함하여 테마 다운로드
   - 전체 히스토리 가져오기 (`fetch-depth: 0`)

4. **GitHub Pages 설정**
   - `actions/configure-pages@v5` 사용
   - 배포 URL 및 환경 변수 설정

5. **Node.js 의존성 설치** (선택사항)
   - `package-lock.json`이 있는 경우에만 실행
   - 테마의 JavaScript 빌드에 필요할 수 있음

6. **Hugo 빌드**
   - 프로덕션 환경으로 빌드
   - `--gc`: 사용하지 않는 파일 정리
   - `--minify`: HTML, CSS, JS 최소화
   - `--baseURL`: GitHub Pages URL로 설정

7. **빌드 아티팩트 업로드**
   - `actions/upload-pages-artifact@v3` 사용
   - `public/` 디렉토리를 아티팩트로 업로드

#### 2️⃣ Deploy Job (배포 작업)

**환경**: `ubuntu-latest`  
**의존성**: `build` Job 완료 후 실행

**단계별 실행 순서**:

1. **GitHub Pages 배포**
   - `actions/deploy-pages@v4` 사용
   - 빌드된 아티팩트를 GitHub Pages에 배포
   - 배포 URL 자동 생성

### 권한 설정

워크플로우에 필요한 권한:
- `contents: read` - 코드 읽기
- `pages: write` - GitHub Pages 배포
- `id-token: write` - OIDC 인증

### 동시성 제어

- 동일한 `pages` 그룹의 배포는 하나씩만 실행
- 진행 중인 배포는 취소하지 않음 (프로덕션 안정성 보장)

### 사용된 Actions 버전

| Action | Version | 용도 |
|--------|---------|------|
| `actions/checkout` | v6 | 코드 체크아웃 |
| `actions/configure-pages` | v5 | GitHub Pages 설정 |
| `actions/upload-pages-artifact` | v3 | 빌드 아티팩트 업로드 |
| `actions/deploy-pages` | v4 | GitHub Pages 배포 |

> **참고**: 모든 Actions는 최신 버전으로 업데이트되어 deprecated 경고 없이 안정적으로 동작합니다.

## 📦 배포 방법

### 자동 배포 (GitHub Actions)

이 프로젝트는 GitHub Actions를 통해 자동으로 빌드 및 배포됩니다.

1. **master 브랜치에 push**
   ```bash
   git add .
   git commit -m "Update content"
   git push origin master
   ```

2. **GitHub Actions 자동 실행**
   - `.github/workflows/hugo.yaml` 워크플로우가 자동으로 실행됩니다
   - 빌드 → 아티팩트 업로드 → GitHub Pages 배포 순서로 진행됩니다
   - 전체 과정은 약 2-3분 소요됩니다

3. **배포 확인**
   - GitHub 저장소의 **Actions** 탭에서 배포 상태 확인
   - 빌드 및 배포 로그 실시간 확인 가능
   - 배포 완료 후 몇 분 내에 사이트에 반영됩니다

### 수동 배포

GitHub Actions를 사용하지 않는 경우:

```bash
# 빌드
hugo --gc --minify --baseURL "https://shinsojin.github.io/"

# public 디렉토리를 gh-pages 브랜치에 배포
# (GitHub Pages 설정에 따라 다를 수 있음)
```

### 수동 배포

GitHub Actions를 사용하지 않는 경우:

```bash
# 빌드
hugo --gc --minify --baseURL "https://shinsojin.github.io/"

# public 디렉토리를 gh-pages 브랜치에 배포
# (GitHub Pages 설정에 따라 다를 수 있음)
```

## 📝 새 포스트 작성하기

1. **콘텐츠 생성**
   ```bash
   hugo new post/새-포스트-이름/index.md
   ```

2. **마크다운 파일 편집**
   - `content/post/새-포스트-이름/index.md` 파일을 열어 내용 작성
   - Front Matter에 메타데이터 설정 (제목, 날짜, 카테고리, 태그 등)

3. **이미지 추가**
   - 포스트 폴더에 이미지 파일 추가
   - 마크다운에서 상대 경로로 참조

4. **커밋 및 푸시**
   ```bash
   git add .
   git commit -m "Add new post: 새 포스트"
   git push origin master
   ```

## 🎨 커스터마이징

### 테마 설정

주요 설정은 `hugo.toml` 파일에서 관리됩니다:

- 사이트 제목, 설명
- 다국어 설정
- 테마 파라미터 (사이드바, 색상, 위젯 등)
- 메뉴 구성

### 스타일 커스터마이징

테마의 SCSS 파일을 수정하거나 `assets/scss/` 디렉토리에 커스텀 스타일을 추가할 수 있습니다.

## 📚 주요 프로젝트

블로그에 소개된 주요 프로젝트들:

- **AI Demo**: AI 신규 엔진 데모 사이트 및 어드민 페이지
- **Plog**: 개발자를 위한 블로그 서비스
- **NewsSum**: 뉴스 요약 서비스
- **BucketListClass**: 버킷리스트 클래스 랜딩 페이지
- **Deep Security**: 딥러닝 기반 보안 솔루션
- 기타 프로젝트 및 토이 프로젝트들

## 🔧 트러블슈팅

### 빌드 오류

- **Hugo 버전 확인**: `hugo version`으로 버전 확인 (v0.122.0 이상 필요)
- **테마 서브모듈 확인**: `git submodule update --init --recursive`

### 배포 오류

- GitHub Actions 로그 확인
- `hugo.toml`의 `baseURL` 설정 확인
- GitHub Pages 설정에서 소스 브랜치 확인

## 📄 라이선스

이 블로그의 콘텐츠는 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) 라이선스를 따릅니다.


---

**마지막 업데이트**: 2026년 1월
