# 🌸 Fractal Tree — Golden Sakura · Generative Botany

> 화면 바닥에서 자라나는 **황금색 프랙탈 나무**와, 성장이 끝난 가지 끝에서 흩날리는 **벚꽃 입자**의 서정적 제너레이티브 아트.

![status](https://img.shields.io/badge/status-live-brightgreen) ![tech](https://img.shields.io/badge/tech-HTML5%20Canvas%20%2B%20Vanilla%20JS-blue) ![license](https://img.shields.io/badge/license-MIT-yellow)

---

## 🎬 라이브 데모 (Live Demo)

| 항목 | 값 |
|------|-----|
| **Live URL** | https://fractal-tree-alpha.vercel.app |
| **상태** | 🟢 Production |
| **렌더링** | 단일 HTML, 외부 의존성 0 |
| **반응형** | viewport 자동 맞춤, 모바일 터치 지원 |

[![Live Demo](https://img.shields.io/badge/Vercel-Live%20Demo-black?style=for-the-badge&logo=vercel)](https://fractal-tree-alpha.vercel.app)

**빠른 사용법**: 페이지 열기 → 자동으로 트리가 자라남 → 1~4 키로 팔레트 전환 → 클릭으로 새 나무 심기

---

## 🤖 생성 정보 (How this was made)

이 프로젝트는 다음 프롬프트를 **그대로** MiniMax-M3에 전달하여 생성되었습니다.

> 수학적 재귀 함수(Recursion)를 사용하여 화면 바닥에서부터 기하학적인 황금색 나무가 서서히 자라나며 가지를 치는 L-System 애니메이션을 구현하고, 성장이 끝난 가지 끝에서는 벚꽃 잎 같은 핑크색 파티클이 생성되어 바람에 날려 바닥으로 떨어지는 서정적이고 감성적인 제너레이티브 아트를 코딩해줘.
>
> **Implementation Advice:** Use HTML5 Canvas. Build a recursive function for the branches (Fractal Tree). For the falling petals, create a simple particle system array after the tree finishes "growing" (animating the recursion depth). 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.

| 항목 | 값 |
|------|-----|
| AI 모델 | **MiniMax-M3** (via MiniMax API, MoA fallback chain) |
| 코딩 에이전트 | **[OpenCode](https://github.com/anomalyco/opencode)** v1.17.13 |
| 플랫폼 | macOS (Apple Silicon / M4) |
| 라이선스 | MIT |

---

## ✨ Features

- 🌳 **수학적 재귀 트리** — Recursion 함수 기반 가지 생성, 깊이 12 단계까지 부드러운 성장 애니메이션
- 🌸 **벚꽃 입자 시스템** — 성장 종료 후 가지 끝에서 핑크색 꽃잎이 생성되어 바람에 실려 낙하
- 🎨 **4가지 팔레트** — Twilight(황혼) / Dawn(여명) / Midnight(한밤) / Autumn(가을), 키보드 `1`/`2`/`3`/`4`로 전환
- 🎭 **감성적 비주얼** — 황금빛 그라데이션 가지 + 부드러운 알파 블렌딩 + 풍경 같은 색감
- 🖱️ **인터랙션** — 화면 클릭으로 새 위치에 나무 심기, 커서 크로스헤어
- 📱 **반응형** — viewport 자동 맞춤, 모바일 터치 지원
- 🚀 **제로 의존성** — 단일 HTML 파일에 모든 코드 포함, npm/CDN 불필요

---

## 🚀 사용법 (Usage)

### 라이브 데모
👉 https://fractal-tree-alpha.vercel.app 에서 바로 실행

### 로컬 실행

```bash
# 1. 클론
git clone https://github.com/sigco3111/fractal-tree.git
cd fractal-tree

# 2. 브라우저로 열기
open index.html            # macOS
xdg-open index.html        # Linux

# 또는 로컬 서버
python3 -m http.server 8000
# → http://localhost:8000
```

### 키보드 컨트롤

| 키 | 동작 |
|----|------|
| `1` | 황혼 (Twilight) — 황금 트리 + 분홍 꽃잎 |
| `2` | 여명 (Dawn) — 로즈골드 트리 + 부드러운 핑크 꽃잎 |
| `3` | 한밤 (Midnight) — 실버 트리 + 푸른 빛 꽃잎 |
| `4` | 가을 (Autumn) — 구리 트리 + 주황/빨강 꽃잎 |
| `Space` | 일시정지 / 재개 |
| `R` | 트리 리셋 (다시 자라남) |

---

## Tech Stack

| 항목 | 값 |
|------|-----|
| 렌더링 | HTML5 Canvas 2D Context |
| 언어 | Vanilla JavaScript (ES6+) |
| 스타일 | CSS3 Custom Properties (CSS Variables) |
| 폰트 | Noto Serif KR, Apple SD Gothic Neo |
| 빌드 | 없음 (zero-deps) |
| 호스팅 | Vercel (정적 사이트) |

### 알고리즘 요약

```js
// 의사 코드 — 실제 구현은 index.html 참조
function growBranch(x, y, angle, length, depth) {
  if (depth >= MAX_DEPTH) { spawnPetals(x, y); return; }
  drawLine(x, y, angle, length);
  const nx = x + cos(angle) * length;
  const ny = y + sin(angle) * length;
  setTimeout(() => {
    growBranch(nx, ny, angle - BRANCH_ANGLE, length * 0.7, depth + 1);
    growBranch(nx, ny, angle + BRANCH_ANGLE, length * 0.7, depth + 1);
  }, depth * 50);  // 단계별 시간차 → 성장 애니메이션
}
```

---

## 🗺️ 로드맵

- [x] **v0.1** — 기본 재귀 트리 + 황금색 그라데이션 + 성장 애니메이션
- [x] **v0.2** — 꽃잎 입자 시스템 (바람 + 낙하)
- [x] **v0.3** — 색상 팔레트 토글 (4종)
- [x] **v0.4** — 인터랙션 (마우스 클릭으로 새 나무 심기)
- [x] **v0.5** — 키보드 컨트롤 + 미리보기 갤러리
- [ ] **v0.6** — 소리 (바람 소리 + 성장 시 미묘한 차임)
- [ ] **v0.7** — 나무 시드 공유 (URL 해시로 나무 형태 인코딩)

---

## 🇺🇸 English

> A **golden fractal tree** slowly growing from the bottom of the screen, with **pink cherry blossom petals** drifting down from the branch tips after growth completes — generative art made with HTML5 Canvas.

- **Live Demo**: https://fractal-tree-alpha.vercel.app
- **Algorithm**: Mathematical recursion for branches + particle system for petals
- **Tech**: HTML5 Canvas, Vanilla JS, zero dependencies
- **License**: MIT

---

## 📝 라이선스

MIT License — 자유롭게 사용, 수정, 배포 가능

---

## 🙏 Credits

- **L-System / Fractal Tree** — 고전적 재귀 알고리즘
- **Particle System** — 벚꽃 낙하 시뮬레이션
- **OpenCode + MiniMax-M3** — AI 협업 부트스트랩
- **Vercel** — 정적 사이트 호스팅
- 코딩미션 참조 페이지: [cokac.com](https://cokac.com/list/announcement/24)

---

<p align="center"><sub>🌸 Built with OpenCode + MiniMax-M3 · sigco3111 · MIT · AI-generated</sub></p>