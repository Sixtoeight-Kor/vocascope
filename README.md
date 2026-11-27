# Vocascope — 실시간 발성 시각화

## PC에서 쓰기
`vocascope.html` 파일을 크롬 또는 엣지로 열고 [마이크 켜기] → 권한 허용. 인터넷 없이도 동작합니다.

## 휴대폰 앱으로 쓰기 (무료, 약 5분)
휴대폰 마이크는 https 주소에서만 켜지므로 GitHub Pages에 한 번 올립니다.
1. github.com 에서 새 저장소 생성 (예: vocascope, Public)
2. 이 폴더의 파일 전부(index.html, manifest.webmanifest, sw.js, 아이콘 3개)를 업로드
3. Settings → Pages → Branch: main / root → Save
4. 1~2분 뒤 `https://<아이디>.github.io/vocascope/` 접속
5. 아이폰: 사파리 공유 → 홈 화면에 추가 / 안드로이드: 크롬 메뉴 → 앱 설치
설치 후에는 오프라인에서도 열립니다.

## 사용 팁
- 처음 한 번 [보정]으로 ㅣ·ㅏ·ㅜ·허밍을 녹음하면 혀·턱·비강·후두 지표가 본인 성도에 맞춰집니다 (음역별 저장).
- 모음 목표: 목표 모음을 고르면 점선 기준 모양 + 일치도 + 교정 문구가 나옵니다.
- 모양 고정: 선생님이 좋은 소리를 낸 순간 [현재 모양 저장] → 학생이 그 모양에 맞춰 봅니다.
- 파일: 녹음 파일을 재생하면서 분석합니다. 스페이스바 = 마이크 켜기/끄기.
- 이어폰 대신 스피커로 데모를 틀면 마이크와 겹치니 데모 중엔 마이크를 끄세요.

## 측정 원리와 한계
- 음정: pitchy (McLeod Pitch Method) / 포먼트: LPC 14차 + 다항식 근 계산
- 성대 접촉: 포먼트 영향을 보정한 H1*–H2* / 비강 유출: 250 Hz 비음 공명(P0) 대 구강 대역
- 후두 높이: F3·F4로 추정한 성도 길이 변화 / 혀 말림: F3 하강
- 구강압: 단면 협착도 × 음량 + 파열 감지 (압력 센서 값이 아님)
- 성도 단면: Pink Trombone(Neil Thapen, MIT) 44구간 모델 + Wakita LPC 역산
고음(남 G4·여 C5 이상)에서는 배음 간격이 넓어 포먼트 추정 정확도가 떨어집니다.

## 오픈소스
pitchy (ISC-style, Ian Johnson), fft.js (MIT, Fedor Indutny), Pink Trombone tract model (MIT, Neil Thapen)
