# 체스 학교 (chess-kids)

어린이용 체스 학습·대결 웹앱. **인터넷 없이도 동작하는 단일 파일** 앱입니다.

## 파일 구성

| 파일 | 설명 |
|---|---|
| `index.html` | 앱 전체 (HTML + CSS + 체스 엔진 + 퍼즐 + 화면). 외부 CDN 없음 |
| `manifest.webmanifest` | 홈 화면 추가(PWA) 설정 |
| `assets/icon-512.png` | 앱 아이콘 512×512 |
| `assets/apple-touch-icon.png` | iOS 홈 화면 아이콘 180×180 |
| `build/` | 제작 원본 (engine.js · puzzles.js · app.js · styles.css · index.template.html · build.py) |
| `verify_engine.py` | 24개 퍼즐 전수 수학 검증 (규칙·최적수·강제 메이트 라인) |
| `test_ui.py`, `test_deep.py`, `test_extra.py` | 화면 동작 검증 (Playwright) |
| `perft_test.py` | 체스 규칙 엔진 검증 (표준 perft 4개 국면) |
| `screenshots.py`, `make_icons.py` | 스크린샷·아이콘 생성 |

`index.html`을 고칠 때는 `build/` 안의 원본을 고치고 `python3 build/build.py`로 다시 합칩니다.

이 저장소에는 배포에 쓰이는 파일(`index.html`, `manifest.webmanifest`, `assets/`)만 들어 있습니다. `build/` 원본과 검증 스크립트(`*.py`)는 `.gitignore`로 제외되어 있습니다.

## 배포

`index.html` + `manifest.webmanifest` + `assets/` 폴더를 그대로 정적 호스팅(GitHub Pages 등)에 올리면 됩니다.
기록은 기기 브라우저의 `localStorage`(`chessKids.v1`)에만 저장되어, 주소를 공유해도 사람마다 기록이 섞이지 않습니다.
