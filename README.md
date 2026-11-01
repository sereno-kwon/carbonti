# CARBON-TI Korea

carbonti.rubiworkshop.com 원페이지 정적 사이트 (GitHub Pages). quoc.rubiworkshop.com과 같은 구조와 디자인 체계입니다.

- `index.html` 한국어 원페이지 (CARBON-TI · RANGE · CHAINRING · DISC ROTOR · FRAME · SERVICE PARTS · COLOUR · SHOWROOM)
- `en/index.html`, `ja/index.html` 영어 · 일본어 페이지 (빌드로 생성, 직접 수정하지 않음)
- `index.src.html` 편집용 한국어 원본
- `i18n/` 번역 사전 (`ko.json` 원문 목록, `en.json` · `ja.json` 원문→번역)
- `tools/build.py` 한국어 페이지, 번역 페이지, sitemap.xml을 한 번에 생성 (quoc와 같은 스크립트)
- 디자인은 quoc · rubi.kr과 같은 체계: 영문 Pretendard · 한글 에스코어 드림, 웨이트 400, 흑백과 얇은 라인, 각진 버튼, 라이트/다크 자동. CSS 맨 아래 `CARBON-TI 추가` 블록만 이 사이트 전용입니다.
- `404.html` 하위 주소(/chainring, /x-rotor, /x-lock, /udh, /dealers 등)를 섹션으로 연결
- `images/art/*.svg` 제품 일러스트 (실제 제품 사진이 들어오기 전까지 쓰는 자리 표시용)
- `images/og.jpg` 공유 썸네일, `images/favicon.svg`, `images/apple-touch-icon.png`

## 처음 올릴 때
1. Settings → Pages → Source: Deploy from a branch, Branch: main / (root).
2. 도메인 DNS에 `carbonti` CNAME 레코드를 `sereno-kwon.github.io`로 추가하고, Pages 설정의 Custom domain에 `carbonti.rubiworkshop.com`을 넣습니다 (CNAME 파일은 이미 들어 있음).

## 문구 수정과 번역
1. `index.src.html`의 한국어 문구를 고칩니다.
2. `python3 tools/build.py` 로 한국어 페이지를 만들고, `python3 i18n/extract.py` 로 `ko.json`을 갱신합니다.
3. 새로 생기거나 바뀐 한국어 문장을 `en.json` · `ja.json`에 같은 키로 추가합니다. HTML 태그는 원문과 똑같이 유지합니다.
4. 다시 `python3 tools/build.py` 를 실행하면 번역되지 않은 문장이 있을 때 목록으로 알려줍니다.

빌드에는 `beautifulsoup4`가 필요합니다 (`pip install beautifulsoup4`).

## 제품 사진으로 바꾸기
`index.src.html`에서 `images/art/...svg`를 찾아 사진 경로(예: `images/chainring/01.jpg`)로 바꾸고, 같은 요소의 `art` 클래스를 지우면 quoc 페이지와 같은 사진 레이아웃이 됩니다.
제품 컷 영역의 "제품 이미지 준비 중" 문구도 함께 지웁니다.

## 가격과 규격
가격은 ERP 품목등록(카본티.xlsx)의 소비자가 기준입니다. 가격이 바뀌면 `index.src.html`의 라인업, 각 섹션 `dl`, 규격표, 서비스 파츠 목록, 상단 JSON-LD `offers`를 함께 고치고 빌드합니다. 번역 문장에 가격이 들어간 경우(서비스 파츠 목록) `en.json` · `ja.json`도 고칩니다.
X-AERORING 64/66/68T, X-ROTOR STEELCARBON 3 X-AFS 단품은 품목등록 가격이 확인되지 않아 페이지에서 뺐습니다.

## 링크
- 헤더 SHOP, "루비워크샵에서 보기" 버튼: `https://rubiworkshop.com/carbonti`
- 거래처 문의: 루비서플라이 02-516-8465, 카카오톡 채널 `https://pf.kakao.com/_NFnBj/chat`
