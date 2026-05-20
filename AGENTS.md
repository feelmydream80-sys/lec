# LEC - 강의실 프로젝트

## 저장소 목적
AI 시대 교육용 강의 자료(HTML 슬라이드)를 모아서 GitHub Pages로 서빙하는 저장소.

## 현재 구조
```
lec/
├── index.html              # 강의 카탈로그 (카드형 목록)
├── ViveCodingIntro/
│   ├── index.html          # 최신 버전 복사본
│   └── vibe-coding-intro_3.html
├── KidsSafty/
│   ├── index.html          # 최신 버전 복사본
│   └── KidsSafeAI_PPT_v4.html
└── AGENTS.md               # 이 파일
```

## 명령어

### "업데이트해줘"
- **대상:** `lec/` 폴더 내 모든 강의 폴더
- **동작:**
  1. 각 강의 폴더에서 가장 높은 버전 번호의 HTML 파일 탐색
  2. 해당 파일을 폴더의 `index.html`로 복사 (덮어쓰기)
  3. 새 폴더 발견 시 사용자에게 강의 정보 요청 후 루트 `index.html`의 `courses` 배열에 추가
  4. `git add` / `commit` / `push` 자동 수행

#### 파일명 버전 규칙
- `_숫자` 접미사로 버전 구분 (예: `vibe-coding-intro_3.html` → 버전 3, `KidsSafeAI_PPT_v4.html` → 버전 4)
- 번호가 가장 높은 파일이 최신 버전
- 숫자가 없으면 단일 파일로 간주하여 그대로 사용

## 강의 추가 방법
1. `lec/` 아래에 새 폴더 생성 (영문, PascalCase 권장)
2. 폴더 안에 HTML 슬라이드 파일 추가
3. `index.html`의 `courses` 배열에 항목 추가
4. `"업데이트해줘"` 명령어로 `index.html` 동기화 및 커밋

## index.html courses 배열 항목 구조
```js
{
  folder: '폴더명',     // lec/ 아래 폴더명 (필수)
  name: '표시할 강의명',   // (필수)
  desc: '간단 설명',      // (필수, <br> 줄바꿈 가능)
  accent: '#컬러코드',    // (필수)
  accentRgb: 'R,G,B',    // (필수)
  icon: '이모지'          // (필수)
}
```

## 오리 퍼레이드 & 게임 시스템

### 숨은 오리 찾기
- 페이지에 숨은 오리 10마리 (엄마 1 + 아기 9), 클릭으로 발견
- 발견 시 오리 아이콘이 1.5초 후 fade-out → DOM 제거
- 해당 오리가 오리 장면(duck-scene) 슬롯에 줄지어 입장 (0.5s 애니메이션)
- 10마리 모두 발견 시 confetti 폭죽

### 퍼레이드 모드
- 엄마 오리(0번) 발견되면 `paradeMode = true`, 모든 오리가 0.5px/frame 으로 우측 이동 (JS 기반, CSS 미사용)

### 무궁화 꽃이 피었습니다 게임
- 백틱(`) 키로 시작 (모든 오리 발견 후 가능)
- 게임 규칙:
  1. "무궁화 꽃이 피었습니다" 문자가 한 글자씩 랜덤 타이밍(0~500ms)으로 표시됨
  2. 글자가 표시되는 동안 스페이스바 누르면 오리들이 1px/frame 전진
  3. 문장이 끝나면 "뗏!" 표시 → 스페이스바 누르고 있으면 맨 끝 오리 잡힘 (😭)
  4. 엄마 오리(0번)가 잡히면 GAME OVER
  5. 모든 오리가 화면 오른쪽 끝(윈도우 너비-80px) 도달 시 "집에 잘 들어갔습니다!" 승리 메시지

## 디자인 컨셉
- 라이트 테마 (#F5F5F7 배경)
- Apple 스타일: SF Pro Display / Noto Sans KR, Space Mono
- Docker 스타일 네비게이션 그라디언트 (120deg, #0db7ed, #1a6bb5, #2d3748, #384d54)
- 카드 섹션별 포인트 색상: 강의 #0071E3, 프로젝트 #34C759, 추가 #FFD60A, 접속 #FF9F0A
