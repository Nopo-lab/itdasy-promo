# 개인정보 고지 정정 근거 (2026-10-01)

정정 대상은 기존 처리의 설명이다. 이 문서는 계약 체결 확인이나 법률 검토 완료 인증서가 아니다. 계정 자격 증명, 고객 데이터 및 업체 요청 내용은 저장하지 않는다.

## 확인된 사항

- 운영 Cloud Run 배포 소스 `ae74d3c85e3a6e6bd967c63b050bfdfdd1d741bb`의 `backend/services/generation.py`는 Vertex AI 실패 시 Gemini API 키 경로로 전환한다.
- 운영 설정의 기본 Vertex AI 위치는 서울이다. 대체 API 키가 속한 프로젝트는 결제 비활성 상태를 읽기 전용으로 확인했다. 따라서 무료 API 조건을 유료 Vertex AI 조건과 동일하게 설명할 수 없다.
- `backend/routers/image.py`는 배경 제거에 Replicate API를 우선 사용하고 remove.bg API를 대체로 사용한다. Replicate의 사진 보정·부분 제거도 이미지 추론 요청이다.
- 같은 파일의 fal.ai 배경 생성 요청에는 설명 문구와 크기만 전달한다. 원본 사진 합성은 잇데이 서버에서 수행한다.
- 의료 메모 정리 구현은 의료 내용 제거와 고객 연결·작성 시각 같은 기록 자체를 구분한다. 모든 자유 입력 메모의 자동 분류/삭제를 보장할 수 없다.
- API 사용 로그 정리는 기본적으로 dry-run이며 운영의 삭제 활성 설정은 확인되지 않았다. 모든 사용 기록의 일괄 자동 만료 주장을 하지 않는다.

## 공급자 공식 안내

| 공급자 | 확인한 범위 | 공식 출처 |
|---|---|---|
| Google Cloud | 허락 없이 모델 학습·미세조정하지 않는 조건, 현재 일반 남용 감시 최대 90일, 검색 grounding 별도 30일. 무보관 승인 확인 아님 | https://cloud.google.com/vertex-ai/generative-ai/docs/vertex-ai-zero-data-retention · https://cloud.google.com/vertex-ai/generative-ai/docs/learn/abuse-monitoring |
| Gemini API | 무료 서비스의 제품/ML 개선과 인력 검토, 개인정보 제출 금지 안내, 남용 감시 55일. 이 55일은 모든 개선 자료의 삭제 기간이 아님 | https://ai.google.dev/gemini-api/terms · https://ai.google.dev/gemini-api/docs/usage-policies |
| Replicate | API 추론 입력·출력·파일·로그 기본 1시간 삭제. 모든 계정/백업 기록 삭제 또는 무학습 계약 확인 아님 | https://replicate.com/docs/topics/predictions/data-retention/ · https://replicate.com/terms · https://replicate.com/privacy |
| remove.bg | 운영사 Canva Austria GmbH. API 이미지 처리 후 즉시 삭제, 별도 개선 프로그램 선택, EU 호스팅. 개별 데이터센터 국가 확인 아님 | https://www.remove.bg/privacy · https://www.remove.bg/help/a/are-my-images-safe · https://www.remove.bg/help/a/do-you-use-my-images-to-train-the-ai · https://www.remove.bg/i/api |
| fal.ai | 공개 DPA 기본 계약 종료까지 보관, 계정/요청 CDN 만료 설정 별도, API 학습 제한에 제외 모델 예외 존재 | https://fal.ai/legal/data-processing-addendum · https://fal.ai/legal/api-services · https://fal.ai/docs/platform-apis/v1/storage/settings/get |
| 개인정보보호위원회 | 72시간 신고 대상은 1천명 이상 외에도 민감정보/고유식별정보, 외부 불법 접근에 의한 유출을 포함 | https://pipc.go.kr/np/default/page.do?mCode=D030040000 |

## 남아 있는 운영 항목

- 무료 Gemini 대체 경로 차단은 사용자에게 결정 요청 중이다. 정책의 현재 경로 고지는 실제 변경 확인 전까지 유지한다.
- fal.ai 계정 파일 만료 조회는 HTTP 403으로 권한이 없었다. 특정 기간 자동 삭제를 주장하지 않는다. 계정 관리자 권한으로 확인하거나 공급자 확인이 필요하다.
- 별도 기업 계약·처리 약정의 체결 증빙, 공급자별 세부 국외 처리 국가·계정별 보관 설정과 해외 서비스 제공 요건은 공개 약관 열람만으로 확인되지 않는다.
- 홍보 사이트의 고지 정정은 앱 내부 정책 문서·동의 화면 업데이트와 동일한 작업이 아니다. 별도 앱 반영이 필요하다.
