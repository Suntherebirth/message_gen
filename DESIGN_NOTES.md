# 디자인 노트

이 앱은 **iOS Safari에서 홈 화면에 추가한 웹앱(PWA)** 형태로 사용되며,
**주 타깃 기기는 iPad 10세대(가로모드)** 입니다. UI/CSS를 수정할 때 아래 기준을 지켜주세요.

## 타깃 환경
- Safari standalone 웹앱 모드 (`apple-mobile-web-app-capable`)
- iPad 10세대 가로모드 기준 뷰포트: 약 1180×820pt (safe-area 상/하단 여백 없음, 홈 인디케이터 없음)
- 다크모드(`prefers-color-scheme: dark`)도 항상 함께 확인

## 모달/레이아웃 규칙
- 모달(`.modal`)은 내용이 길어져도 화면 아래로 잘리지 않도록 `max-height` + `overflow-y: auto`로 자체 스크롤 가능해야 함.
- 목록형 콘텐츠(태그, 변수 등)가 늘어날 수 있는 영역은 통짜로 나열하지 말고
  **탭 버튼으로 분류를 나눠서** 한 번에 보여주는 항목 수를 줄일 것 (`.manage-tabs` / `.manage-tab` 패턴 재사용).
- 스크롤이 필요한 목록 패널은 `max-height`(예: 40vh 내외)를 지정하고 `-webkit-overflow-scrolling: touch`를 적용해 iOS에서 관성 스크롤이 되도록 할 것.
- 터치 타깃은 최소 32~44px 높이를 유지.

## 확인 방법
- 브라우저 개발자 도구에서 반응형 크기를 1180×820으로 맞추고 확인.
- 실제로는 Safari에서 "홈 화면에 추가" 후 iPad 가로모드로 테스트하는 것을 권장.
