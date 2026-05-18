# LEC - 강의실 프로젝트

## 저장소 목적
AI 시대 교육용 강의 자료(HTML 슬라이드)를 모아서 GitHub Pages로 서빙하는 저장소.

## 현재 구조
```
lec/
├── index.html              # 강의 카탈로그 (카드형 목록)
├── ViveCodingIntro/
│   └── vibe-coding-intro_3.html  # Vibe Coding 입문 강의
├── KidsSafty/
│   └── KidsSafeAI_PPT_v4.html    # Kids Safe AI 강의
└── AGENTS.md               # 이 파일
```

## 강의 추가 방법
1. `lec/` 아래에 새 폴더 생성 (영문, PascalCase 권장)
2. 폴더 안에 HTML 슬라이드 파일 추가
3. `index.html`의 `courses` 배열에 항목 추가
4. `git add`, `commit`, `push`

## index.html courses 배열 항목 구조
```js
{
  folder: '폴더명',
  file: '파일명.html',
  name: '표시할 강의명',
  desc: '간단 설명 (<br> 줄바꿈 가능)',
  accent: '#컬러코드',
  accentRgb: 'R,G,B',
  icon: '이모지'
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
