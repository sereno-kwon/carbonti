# CARBON-TI Korea

carbonti.rubiworkshop.com 원페이지 정적 사이트 (GitHub Pages). quoc.rubiworkshop.com과 같은 구조와 디자인 체계입니다.

- `index.html` 한국어 원페이지 (CARBON-TI · RANGE · CHAINRING · DISC ROTOR · FRAME · SERVICE PARTS · COLOUR · SHOWROOM)
- 디자인은 quoc · rubi.kr과 같은 체계: 영문 Pretendard · 한글 에스코어 드림, 웨이트 400, 흑백과 얇은 라인, 각진 버튼, 라이트/다크 자동. CSS 맨 아래 `CARBON-TI 추가` 블록만 이 사이트 전용입니다.
- `404.html` 하위 주소(/chainring, /x-rotor, /x-lock, /udh, /dealers 등)를 섹션으로 연결
- `images/art/*.svg` 제품 일러스트 (실제 제품 사진이 들어오기 전까지 쓰는 자리 표시용)
- `images/og.jpg` 공유 썸네일, `images/favicon.svg`, `images/apple-touch-icon.png`

## 처음 올릴 때
1. Settings → Pages → Source: Deploy from a branch, Branch: main / (root).
2. 도메인 DNS에 `carbonti` CNAME 레코드를 `sereno-kwon.github.io`로 추가하고, Pages 설정의 Custom domain에 `carbonti.rubiworkshop.com`을 넣습니다 (CNAME 파일은 이미 들어 있음).

## 제품 사진으로 바꾸기
`index.html`에서 `images/art/...svg`를 찾아 사진 경로(예: `images/chainring/01.jpg`)로 바꾸고, 같은 요소의 `art` 클래스를 지우면 quoc 페이지와 같은 사진 레이아웃이 됩니다.
제품 컷 영역의 "제품 이미지 준비 중" 문구도 함께 지웁니다.

## 가격과 규격
가격은 ERP 품목등록(카본티.xlsx)의 소비자가 기준입니다. 가격이 바뀌면 `index.html`의 라인업, 각 섹션 `dl`, 규격표, 서비스 파츠 목록, 상단 JSON-LD `offers`를 함께 고칩니다.
X-AERORING 64/66/68T, X-ROTOR STEELCARBON 3 X-AFS 단품은 품목등록 가격이 확인되지 않아 페이지에서 뺐습니다.

## 링크
- 헤더 SHOP, "루비워크샵에서 보기" 버튼: `https://rubiworkshop.com/carbonti`
- 거래처 문의: 루비서플라이 02-516-8465, 카카오톡 채널 `https://pf.kakao.com/_NFnBj/chat`
