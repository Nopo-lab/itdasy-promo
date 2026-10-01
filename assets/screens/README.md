# 실제 앱 화면 캡처

2026-10-02, `Nopo-lab/itdasy-frontend` 운영 코드(51dd9985809dc939d84f49b0c0dca5e4cf9a773b)를 로컬에서 실행하고 Chrome 390 × 844, 2배 배율로 캡처했습니다. 화면을 새로 그린 목업이 아닙니다.

- `home`: 앱 홈 / `customers`: 고객 관리 / `booking`: 예약 달력 / `revenue`: 매출 관리
- `assistant`: 잇비 대화 / `caption`: 홍보 글 작성 / `editor`: 실제 통합 사진 편집기
- `publish`: 인스타그램 게시물 미리보기(연결 필요 상태) / `portfolio`: 시술 사진 정리

모든 업무 API 응답은 별도 브라우저 안에서 샘플로 대체했습니다. 운영 계정, 실제 고객 기록, 유료 AI 요청 및 실제 게시물 발행을 사용하지 않았습니다. 고객명·예약·매출·AI 답변·홍보 문구는 샘플입니다. 사진은 앱 저장소의 `output/v549-qa-images/07-clear-gel-synthetic.png`, `08-dark-color-nail-synthetic.png`, `09-french-nail-synthetic.png` 테스트 자산을 사용했습니다. 실제 고객 시술 결과나 이 앱의 AI 생성 결과임을 의미하지 않습니다.

페이지에도 실제 앱 화면과 샘플 데이터라는 안내를 표시합니다. 영어 페이지의 캡처 화면 내부는 한국어입니다. 정책·가격·제공 기능이 바뀌면 해당 캡처를 다시 확인합니다.

브랜드 색은 앱 `css/tokens.css`의 `#D58A95`, `#BC6675`, `#F7EFF0`를 따릅니다. 작은 흰색 버튼 글씨는 대비를 위해 짙은 로즈 `#A94F60`를 사용합니다.

## 최신 편집기와 샘플 사진 갱신

2026-10-02 `editor-current.webp`, `caption.webp`, `publish.webp`, `portfolio.webp`는 테스트 앱 `Nopo-lab/itdasy-frontend-test-yeunjun` main `e7ee51890949e4c4d2a83b333c24a1cbb2bca788`을 로컬에서 실행하여 다시 캡처했습니다. 최신 편집기는 사이트에서 테스트 앱 화면으로 별도 표시합니다. 고객·예약·매출·잇비 화면은 위 운영 코드 캡처입니다.

모든 API는 브라우저 안에서 샘플 응답으로 대체했으며 운영 데이터 저장, 유료 AI 실행, 발행을 하지 않았습니다. 새 샘플 사진을 실제 앱에 불러왔으며 UI를 새로 그리지 않았습니다. 생성 프롬프트는 [../samples/README.md](../samples/README.md)를 참고하세요.

홈의 로즈 영역은 원본 토큰 `#D58A95`를 그대로 사용하고 작은 버튼의 글씨에는 앱 잉크색 `#191F28`을 적용합니다.
