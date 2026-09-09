﻿# CCMC 시리즈 소개 페이지

**'[클로드코드 마스터클래스](<https://jtech-co.github.io/CCMC/>)'** 전자책 5권을 소개하고 크몽 구매로 연결하는 정적 페이지입니다.

<img src="./og.png" width="80%">

## 구성
- `index.html`: 외부 폰트·스크립트 없는 자체 완결 소개 페이지입니다.
- `og.png`: SNS 공유 미리보기 이미지(1200x630). 카카오톡·페이스북·쓰레드 등에서 링크 공유 시 표시됩니다.
- `og-source.html`: og.png의 고화질 웹 버전입니다.

## 유지보수
- `og:image`는 **절대 URL**이어야 합니다. 상대 경로(`og.png`)로 두면 카카오톡·페이스북 크롤러가 미리보기를 만들지 못합니다. 배포 주소가 바뀌면 `index.html` head의 `canonical`, `og:url`, `og:image`, `og:image:secure_url`, `twitter:image`를 함께 고칩니다.
- 문구나 수치를 바꾸면 `og-source.html`을 고친 뒤 다시 렌더링합니다. 한글 경로에서는 크롬이 `file://`를 읽지 못하므로 ASCII 경로로 복사해 실행합니다.

```bash
chrome --headless=new --screenshot=og.png --window-size=1200,630 --hide-scrollbars og-source.html
```

- 페이지 수치(전 5권, 34개 장, A4 219페이지, 권별 분량, 최종 검증일)는 병합 PDF 실측값입니다. 재조판하면 `index.html`의 `hero-meta`와 `vol-pages`, `og-source.html`의 `meta`를 함께 갱신합니다.
