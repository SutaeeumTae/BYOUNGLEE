# 병리학 II 예상문제 100선 — 臟腑辨證

한의학 **병리학 II(장부변증)** 기출 기반 예상문제 **100선** (객관식 75 + 주관식 25)을 풀 수 있는 **단일 페이지 웹 퀴즈**입니다. 별도 설치·서버·인터넷 없이 동작하며, GitHub Pages로 올리면 휴대폰에서도 바로 풀 수 있습니다.

## ✨ 기능

- 📝 **객관식 75 + 주관식 25** (주관식은 전부 "○○證" 변증명 쓰기)
- 🔀 **랜덤 배치**: 문제·선지 순서를 매번 섞음
- ✅ **복수정답 문항**은 정답 개수 표시 ("정답 2개 · 모두 고르기")
- 🧠 **즉시 채점 + 해설**, 주관식은 한글·한자 자동 인정 + 자가 채점
- 🔁 **오답노트**: 틀린 문제 자동 저장 → 반복 학습 (브라우저 localStorage)
- 🗂 **챕터 필터** / 모드(전체·객관식·주관식·오답노트)
- ⌨️ 키보드: 객관식 `1`~`5`, `Enter` 다음
- 📱 **오프라인 지원(PWA)**: 한 번 접속 후 인터넷 없이도 학습, "홈 화면에 추가" 가능

> ⚠️ 점수·오답 기록은 **여러분 브라우저에만** 저장됩니다(서버 전송 없음). 학습용 자료입니다.

## 🚀 GitHub Pages로 올리기

### 방법 A — 웹에서 클릭만으로 (가장 쉬움)

1. GitHub에서 **New repository** 생성 (예: `byungri2-quiz`), Public.
2. 저장소 페이지의 **Add file → Upload files** 클릭.
3. 이 폴더 안의 **모든 파일**(`index.html`, `manifest.json`, `sw.js`, `icon.svg`, `.nojekyll`, `README.md`)을 드래그하여 업로드 → **Commit changes**.
4. **Settings → Pages → Build and deployment**에서 Source를 **Deploy from a branch**, Branch를 **main / (root)** 으로 선택 → Save.
5. 1~2분 뒤 표시되는 주소로 접속:
   `https://<깃허브아이디>.github.io/byungri2-quiz/`

> `.nojekyll` 파일이 포함되어 있어 GitHub의 Jekyll 처리 없이 그대로 서빙됩니다.

### 방법 B — git 명령어로

```bash
# 이 폴더(병리학II_quiz_site)에서 실행
git init
git add .
git commit -m "병리학 II 예상문제 100선 퀴즈"
git branch -M main
git remote add origin https://github.com/<깃허브아이디>/byungri2-quiz.git
git push -u origin main
```
이후 **Settings → Pages**에서 Branch를 `main / (root)`로 지정하면 게시됩니다.

## 🔧 문제 내용을 수정했다면

`index.html`의 `QUESTIONS` 배열을 고친 뒤, 오프라인 캐시가 갱신되도록 **`sw.js`의 버전을 올려주세요**:

```js
const CACHE = 'byungri2-quiz-v1';  // -> 'byungri2-quiz-v2' 로 변경
```

## 📁 파일 구성

| 파일 | 설명 |
|---|---|
| `index.html` | 퀴즈 본체(문제 100선 + 앱 로직 포함, 단일 파일) |
| `manifest.json` | PWA 설정(앱 이름·아이콘·테마색) |
| `sw.js` | 서비스워커(오프라인 캐시) |
| `icon.svg` | 앱 아이콘 |
| `.nojekyll` | GitHub Pages Jekyll 처리 비활성화 |

## 💻 로컬에서 테스트

- 간단히: `index.html`을 더블클릭하면 브라우저에서 바로 실행됩니다.
- PWA(오프라인)까지 테스트하려면 로컬 서버가 필요합니다(서비스워커는 `http(s)`에서만 동작):
  ```bash
  # Node가 있으면
  npx serve .
  # Python이 있으면
  python -m http.server 8000
  ```
  그 후 `http://localhost:8000` 접속.

---
한의학 학습용 · 臟腑辨證 기말 대비
