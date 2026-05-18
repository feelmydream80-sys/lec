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

## 배포
- GitHub Pages: `https://feelmydream80-sys.github.io/lec/`
- main 브랜치에 push 시 자동 반영 (브랜치 소스: main / root)

## 디자인 컨셉
- 다크 테마 (#060608 배경)
- 네온 포인트 컬러
- Grid 패턴 배경
- Glow 오브 효과
- 폰트: Noto Sans KR + Space Mono
- 카드형 레이아웃
