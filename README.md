# 🌸 Fractal Tree — Generative Cherry Blossom

화면 바닥에서 자라나는 **황금색 프랙탈 나무**와, 성장이 끝난 가지 끝에서 흩날리는 **벚꽃 입자**의 서정적 제너레이티브 아트.

단일 HTML 파일에 모든 의존관계를 담아, 별도 빌드 없이 브라우저에서 바로 실행됩니다.

---

## ✨ 결정 사항

| # | 결정 | 이유 |
|---|------|------|
| 1 | 단일 HTML5 Canvas | 외부 의존성 0, 더블클릭으로 실행 |
| 2 | 수학적 재귀 함수로 가지 생성 | L-System 미니멀 구현, 구조가 명확 |
| 3 | 성장 애니메이션 = `recursion depth`의 점진적 전개 | 미션 요구사항과 1:1 대응 |
| 4 | 꽃잎은 성장 종료 후 `Particle System`으로 추가 | "바람에 날려 바닥으로 떨어지는" 동작 분리 |
| 5 | 꽃잎은 핑크 + 살짝 알파 + 회전 | 벚꽃의 시각적 정체성 |

---

## 🛠️ 제작 환경

이 저장소의 초기 README와 프로젝트 부트스트랩은 다음 환경에서 진행되었습니다.

| 항목 | 값 |
|------|-----|
| AI 모델 | **MiniMax-M3** (via MiniMax API, MoA fallback chain) |
| 코딩 에이전트 | **[OpenCode](https://github.com/anomalyco/opencode)** v1.17.13 |
| 플랫폼 | macOS (Apple Silicon / M4) |
| 라이선스 | MIT |

> 핵심 알고리즘(`index.html`의 `<script>` 블록)은 위 환경의 **MiniMax-M3** 모델이 OpenCode CLI를 통해 작성했습니다.

---

## 📜 원본 미션 프롬프트

이 프로젝트는 아래 프롬프트를 **그대로** MiniMax-M3에 전달하여 생성되었습니다.

> 수학적 재귀 함수(Recursion)를 사용하여 화면 바닥에서부터 기하학적인 황금색 나무가 서서히 자라나며 가지를 치는 L-System 애니메이션을 구현하고, 성장이 끝난 가지 끝에서는 벚꽃 잎 같은 핑크색 파티클이 생성되어 바람에 날려 바닥으로 떨어지는 서정적이고 감성적인 제너레이티브 아트를 코딩해줘.
>
> **Implementation Advice:** Use HTML5 Canvas. Build a recursive function for the branches (Fractal Tree). For the falling petals, create a simple particle system array after the tree finishes "growing" (animating the recursion depth). 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.

요구사항 체크리스트:

- [ ] 수학적 재귀 함수 (Recursion) 기반 가지 생성
- [ ] 화면 바닥에서 위로 자라나는 L-System 애니메이션
- [ ] 황금색 기하학적 나무
- [ ] 성장 종료 후 꽃잎 입자 시스템
- [ ] 핑크색 벚꽃 + 바람 + 낙하
- [ ] HTML5 Canvas + 단일 HTML (의존성 0)

---

## 📁 구조

```
fractal-tree/
├── index.html        ← 전체 앱 (HTML + CSS + Canvas + JS)
└── README.md
```

별도 의존성 없음. `index.html`을 브라우저로 열면 바로 실행됩니다.

---

## ▶️ 실행

```bash
# 옵션 1: 브라우저에서 직접 열기
open index.html

# 옵션 2: 로컬 서버 (권장)
python3 -m http.server 8000
# → http://localhost:8000
```

---

## 🗺️ 로드맵

- [ ] **v0.1** — 기본 재귀 트리 + 황금색 그라데이션 + 성장 애니메이션
- [ ] **v0.2** — 꽃잎 입자 시스템 (바람 + 낙하)
- [ ] **v0.3** — 색상 팔레트 토글 (사계절 / 일출 / 심야)
- [ ] **v0.4** — 인터랙션 (마우스 클릭으로 새 나무 심기)

---

## 📜 라이선스

MIT