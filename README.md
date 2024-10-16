# java-calculator-precourse
# **문자열 덧셈 계산기**

---

## 개요

---

- 문자열 덧셈 계산기는 입력한 문자열에서 숫자를 추출하여 더하는 계산기이다.
- 문자열에 구분자(쉼표, 콜론)도 같이 있다면 구분자 기준으로 분리해서 각 숫자의 합을 반환하지만, 사용자가 잘못된 값을 입력하면 `IllegalArgumentException`을 발생시킨 후 애플리케이션이 종료된다.
- 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다.
- 커스텀 구분자는 문자열 앞 부분의 “//”와 “\n” 사이에 위치하는 문자이다.
    - ex) “//$\n1$2$3” → 6

## 기능 구현

---

### 1. 애플리케이션 시작

- **메시지 출력**: “덧셈할 문자열을 입력해 주세요.”

### 2. 사용자 입력

- **입력 검증**:
    - 숫자 형식인지 확인한다.
    - 0보다 큰지 확인한다. (음수와 0은 예외 처리)
    - 커스텀 구분자 규칙을 잘 지켰는지 확인한다.
        - ex) “//” + 커스텀 구분자 + “\n” + 문자열
    - **커스텀 구분자를 숫자로 지정하면 예외 처리 (수정)**
    - 검증이 실패하면 `IllegalArgumentException`을 발생시키고, “잘못된 값을 입력하였습니다.”라는 메시지를 출력 후 애플리케이션을 종료한다.

### 3. 덧셈 계산

- **문자열 분리**: 구분자를 사용하여 문자열을 분리한다.
- **계산**: 분리된 각 숫자를 추출하여 합을 계산한다.

### 4. 결과 출력

- **출력 검증**:
    - 아무것도 입력하지 않으면 0을 출력한다.
    - 입력에 문제가 없으면 덧셈 후 결과를 출력한다.
        - 형식 - “결과 : [합계]”

### 5. 애플리케이션 종료

- 모든 로직 완료 후 `main` 함수가 종료되어 애플리케이션이 종료된다.