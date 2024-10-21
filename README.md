# java-calculator-precourse
# **문자열 덧셈 계산기**

---

## 📌 개요

---

- 문자열 덧셈 계산기는 `사용자가 입력한 문자열에서 숫자를 추출하여 더하는 기능`을 제공하는 프로그램입니다.
- 문자열에는 기본 구분자(쉼표`,`, 콜론`:`)가 포함될 수 있으며, 사용자가 원하면 커스텀 구분자를 생성할 수 있습니다.
- 잘못된 값이나 형식을 입력할 경우, 프로그램은 `IllegalArgumentException` 예외를 발생시키고 종료합니다.
- 이 프로그램은 다음과 같은 입력 규칙을 따릅니다:
  - 기본 구분자와 커스텀 구분자를 사용해 숫자를 분리합니다.
  - 커스텀 구분자는 문자열 앞 부분의 `//`와 `\n` 사이에 위치합니다.
      - ex) `"//;\n1;2;3"` → `결과 : 6`
  - 숫자 이외의 값 또는 음수나 0을 입력할 경우 예외를 발생시킵니다.

## 📝 기능 구현

---

### 1. 애플리케이션 시작

- **메시지 출력**: "덧셈할 문자열을 입력해 주세요."

### 2. 사용자 입력

- **입력 검증**:
  - **빈 문자열**
     - 아무것도 입력하지 않은 경우 `0`을 출력합니다. 
     - ex) 입력: `""` → 출력: `결과 : 0`
  - **숫자 형식 검증**
     - 문자열 내의 각 숫자가 `양수`여야 합니다. 
     - 0이나 음수가 포함된 경우, `IllegalArgumentException`이 발생합니다. 
     - ex) 입력: `"1,-2,3"` → 에러 메시지: `"잘못된 값을 입력하였습니다."`
  - **커스텀 구분자 규칙 검증**
     - 문자열 앞에 `//` + 커스텀 구분자 + `\n` 형식이어야 합니다.
     - ex) `"//;\n1;2;3"` → 구분자: `;`, `결과 : 6 `
  - **커스텀 구분자 유효성 검증**
     - 숫자를 이용해 커스텀 구분자를 생성할 수 없습니다.
     - 만약 숫자가 구분자로 입력된 경우, `"숫자로 커스텀 구분자를 만들 수 없습니다."`라는 에러 메시지를 출력합니다.

### 3. 문자열 분리 및 덧셈 계산

- **기본 구분자 사용**
    - 쉼표(`,`)와 콜론(`:`)을 사용해 문자열을 분리합니다.
    - ex) `"1,2:3"` →  `결과 : 6`

- **커스텀 구분자 사용**
    - `//` + **커스텀 구분자** + `\n` 형태로 입력된 구분자를 사용합니다.
    - 기본 구분자와 함께 사용할 수 있습니다.
    - ex) `"//;\n1;2;3"` →  `결과 : 6`

- **계산**
    - 모든 숫자를 더한 합을 계산합니다.

### 4. 결과 출력

- **출력 검증**:
    - **정상 입력**
      - 정상적으로 값을 입력하면 덧셈 후 결과를 출력합니다.
      - ex) 입력: `"1,2,3"` → 출력: `결과 : 6`
    - **빈 문자열**
      - 빈 문자열을 입력하면 결과로 0을 출력합니다.
      - ex) 입력: `""` → 출력: `결과 : 0`
    - **잘못된 값**
      - 잘못된 값을 입력하면 에러 메시지를 출력합니다.
      - ex) 입력: `"1,-2,3"` → 에러 메시지: `"잘못된 값을 입력하였습니다."`

### 5. 예외 처리 및 종료

- 사용자가 올바른 입력을 할 경우, 결과를 출력한 후 프로그램이 종료됩니다.
  - 입력: `"//;\n1;2;3"` -> 출력: `결과 : 6` -> 프로그램 종료
- 사용자가 잘못된 입력을 할 경우, 다음과 같은 **에러 메시지**를 출력한 후 프로그램이 종료됩니다:
  - 입력: `"//;\n1~2~3"` -> 에러 메시지 출력 -> 프로그램 종료