# freelang-stdlib-i18next

FreeLang v2 stdlib — npm `i18next` 완전 대체

다국어 지원, 네임스페이스, 변수 치환, 폴백 언어

## 사용법

```freelang
import i18next from "stdlib/i18next"

// 초기화
i18next.init({
  defaultLanguage: "ko",
  fallbackLanguage: "en"
})

// 리소스 추가
i18next.addResources("ko", "common", {
  "hello": "안녕하세요",
  "welcome": "{{name}}님 환영합니다"
})

// 번역
var msg = i18next.t("common:hello")
var welcome = i18next.t("common:welcome", { name: "김철수" })

// 언어 전환
i18next.changeLanguage("en")

// 존재 확인
if i18next.exists("common:hello") {
  println("번역 존재")
}
```

## API

| 함수 | 설명 |
|------|------|
| `init(config)` | 초기화 |
| `t(key)` | 번역 조회 |
| `t_withVars(key, vars)` | 번역 + 변수 치환 |
| `changeLanguage(lang)` | 언어 전환 |
| `addResources(lang, ns, translations)` | 리소스 추가 |
| `exists(key)` | 번역 존재 확인 |
| `getLanguage()` | 현재 언어 조회 |
| `getConfig()` | 설정 조회 |
| `reset()` | 초기화 (테스트용) |

## 네이티브 함수

- `i18n_load_file(path, lang, ns)` → JSON 파일 로드
- `i18n_load_json(jsonStr, lang, ns)` → JSON 문자열 파싱
- `i18n_plural(count, key, lang)` → 복수형 처리
- `i18n_format(text, variables)` → 변수 치환
- `i18n_list_languages(dir)` → 언어 목록
- `i18n_detect_language(acceptLanguage)` → 언어 감지

## 라이선스

FreeLang Project
