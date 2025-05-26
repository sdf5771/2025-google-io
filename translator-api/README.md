# Chrome Translator API 데모

![스크린샷 2025-05-26 오전 9 51 12](https://github.com/user-attachments/assets/eef95e56-13c5-464a-8a17-24dabc5529d9)


이 프로젝트는 Google I/O 2025에서 소개된 Chrome의 내장 Translator API를 테스트로 사용해보는 웹 애플리케이션입니다.

## 소개

Chrome의 Translator API는 브라우저에 내장된 AI 번역 기능으로, 클라이언트 측에서 번역을 수행합니다. 이는 다음과 같은 장점을 제공합니다:

- **프라이버시 보호**: 텍스트가 외부 서버로 전송되지 않음
- **오프라인 기능**: 한 번 모델을 다운로드한 후에는 인터넷 연결 없이도 사용 가능
- **빠른 응답 시간**: 서버 왕복 시간이 필요 없어 거의 실시간 번역 가능
- **낮은 지연 시간**: 네트워크 지연이 없어 더 나은 사용자 경험 제공

## 기능

- 여러 언어 간 텍스트 번역 지원
- 번역 모델 다운로드 진행 상태 표시
- 직관적인 사용자 인터페이스
- 번역 오류 처리 및 상태 표시

## 지원 언어

현재 다음 언어들 간의 번역을 지원합니다:

- 영어 (English)
- 한국어 (Korean)
- 일본어 (Japanese)
- 중국어 (Chinese)
- 프랑스어 (French)
- 독일어 (German)
- 스페인어 (Spanish)
- 이탈리아어 (Italian)

## 사용 요구 사항

![스크린샷 2025-05-26 오전 9 10 27](https://github.com/user-attachments/assets/b25b33bf-2e9c-47c8-807e-9dd087c9862b)


Chrome의 Translator API를 사용하려면 다음 조건이 필요합니다:

1. **Chrome 버전**: Chrome 123 이상 (2024년 5월 기준)
2. **플래그 활성화**:
   - `chrome://flags/#translation-api` 플래그 활성화
3. **브라우저 재시작**: 설정 변경 후 브라우저 재시작
4. **디스크 공간**: 언어 모델 다운로드를 위한 충분한 디스크 공간 (약 1GB)
5. **인터넷 연결**: 초기 모델 다운로드를 위한 인터넷 연결

## 사용 방법

1. 위의 요구 사항을 충족하는지 확인합니다.
2. 원본 언어와 번역할 대상 언어를 선택합니다.
3. 번역할 텍스트를 입력합니다.
4. "번역하기" 버튼을 클릭합니다.
5. 번역 결과가 출력 영역에 표시됩니다.

## 기술 정보

이 데모는 다음과 같은 Chrome API를 사용합니다:

```javascript
// Translator API 지원 여부 확인
if ('Translator' in self) {
  // Translator API 지원됨
}

// 번역 가능 여부 확인
const capabilities = await Translator.availability({
  sourceLanguage: 'en',
  targetLanguage: 'ko'
});

// 번역기 생성
const translator = await Translator.create({
  sourceLanguage: 'en',
  targetLanguage: 'ko'
});

// 텍스트 번역
const result = await translator.translate('Hello, world!');
```

## 제한 사항

- 일부 언어 쌍은 아직 지원되지 않을 수 있습니다.
- 첫 번역 시 모델 다운로드가 필요하므로 지연이 발생할 수 있습니다.
- Chrome 브라우저에서만 동작하며 다른 브라우저에서는 사용할 수 없습니다.
- 텍스트 번역만 지원하며 이미지, 오디오, 비디오 등의 번역은 지원하지 않습니다.

## 참고 자료

- [Chrome Translator API 공식 문서](https://developer.chrome.com/docs/ai/translator-api)
- [Google I/O 2025 - 크롬 AI 기능 소개](https://io.google/2025)
- [On-device Translation with Chrome](https://developer.chrome.com/docs/ai/translate-on-device)
