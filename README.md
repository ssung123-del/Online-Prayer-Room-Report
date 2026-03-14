# 하남교구 온라인 기도실 보고서

온라인 기도실 사역을 위한 웹 기반 보고서 시스템입니다. 성도들의 기도제목을 확인하고 필터링하며, 인쇄용 보고서로 출력할 수 있습니다.

## 주요 기능

### 1. 기도제목 대시보드
- **총 기도제목**: 전체 누적 데이터 수
- **공유 기도 (공개)**: 중보기도팀과 공유 가능한 기도
- **교역자 전용 (비공개)**: 담당 목회자만 열람 가능한 기도

### 2. 필터 및 검색
- **전체 / 공유 기도 / 교역자 전용** 탭으로 빠른 필터링
- **검색**: 성도 이름 또는 기도 내용으로 검색
- **정렬**: 최신순 / 과거순 정렬 지원

### 3. 인쇄 기능
- 보고서 인쇄 버튼 클릭으로 A4 크기 보고서 출력
- 인쇄 시 화면 UI 제거, 깔끔한 문서 형식으로 변환
- 효율적인 공간 활용을 위한 순차 나열 레이아웃

## 기술 스택

- **HTML5 / CSS3 / JavaScript (Vanilla)**
- **Tailwind CSS** - 스타일링
- **Supabase** - 데이터베이스 및 인증
- **Font Awesome** - 아이콘
- **Pretendard** - 한글 폰트

## 설치 및 실행

### 1. 레포지토리 복사

```bash
git clone <repository-url>
cd Online-Prayer-Room-Report-main
```

### 2. 로컬 서버 실행

```bash
# Python 3
python -m http.server 8000

# Node.js (http-server 설치 후)
npx http-server

# 또는 VS Code Live Server 익스텐션 사용
```

### 3. 브라우저 접속

```
http://localhost:8000
```

## 환경 설정

Supabase 연결을 위해 `index.html`의 설정을 확인하세요:

```javascript
const SUPABASE_URL = 'your-supabase-url';
const SUPABASE_KEY = 'your-supabase-anon-key';
```

## 인쇄 설정

보고서 인쇄 시 다음 스타일이 적용됩니다:

- **페이지 크기**: A4
- **여백**: 15mm
- **배경색 유지**: `-webkit-print-color-adjust: exact`
- **카드 레이아웃**: 페이지 중단 방지, 단순 테두리 스타일

## 데이터 구조

기도 데이터는 `prayers` 테이블에 저장되며 다음 필드를 포함합니다:

| 필드명 | 타입 | 설명 |
|--------|------|------|
| `name` | string | 성도 이름 |
| `content` | text | 기도 내용 |
| `is_public` | boolean | 공개 여부 (true: 공유 기도, false: 교역자 전용) |
| `created_at` | timestamp | 작성 일시 |

## 브라우저 지원

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 라이선스

© 2025 하남교구
