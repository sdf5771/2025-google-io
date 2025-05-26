# Language Detector API 데모

![스크린샷 2025-05-26 오전 11 53 15](https://github.com/user-attachments/assets/5225382e-ced6-462a-8c04-0654889a0851)

이 프로젝트는 2025 Google I/O에서 소개된 Chrome의 내장 Language Detector API를 시연하는 간단한 웹 애플리케이션입니다. 사용자가 텍스트를 입력하면 브라우저에 내장된 모델을 사용하여 클라이언트 측에서 언어를 감지합니다.

## 특징

- 클라이언트 측 언어 감지 (서버에 요청을 보내지 않음)
- 모델을 다운로드하여 오프라인 상태에서도 작동
- 다양한 언어 지원
- 언어 감지 신뢰도 표시

## 사용 방법

1. 브라우저에서 `index.html` 파일을 엽니다.
2. 텍스트 영역에 언어를 감지할 텍스트를 입력합니다.
3. "Detect Language" 버튼을 클릭합니다.
4. 감지된 언어와 신뢰도가 결과 영역에 표시됩니다.

## 요구 사항

![스크린샷 2025-05-26 오전 11 30 35](https://github.com/user-attachments/assets/af14225c-32e3-41f0-98d9-d2c17caddeed)

- Chrome 123 이상 버전
- Language Detection API 플래그 활성화 필요:
  1. 주소창에 `chrome://flags/#language-detection-api` 입력
  2. "Enabled" 선택
  3. 브라우저 재시작

## 기술 스택

- 순수 HTML, CSS, JavaScript
- Chrome Language Detector API

## 작동 방식

1. 브라우저가 Language Detector API를 지원하는지 확인
2. 필요한 경우 언어 감지 모델 다운로드
3. 입력된 텍스트에서 언어 감지 실행
4. 결과 표시 (감지된 언어 및 신뢰도)

## 관련 자료

- [Chrome Language Detector API 문서](https://developer.chrome.com/docs/capabilities/language-detection)
- [Google I/O 2025 발표 자료](https://example.com/google-io-2025)
- [Github - Language Detection](https://github.com/webmachinelearning/translation-api?tab=readme-ov-file#language-detection)
