### Math 객체

- 생성자가 아님. new Math()도 Math()도 TypeError. 그냥 일반 객체라 정적 프로퍼티와 정적 메서드만 있음
- [[Prototype]]은 Object.prototype
- 모든 메서드는 인수를 ToNumber로 바꿈.
  - Math.abs('-1')은 1
  - Math.abs([])는 0([] -> '' -> 0)
  - Math.abs({})는 NaN

### 프로퍼티

- Math.PI = 3.141592653589793
- writable, enumerable, configurable 전부 false로 덮어쓸 수 없음

### 메서드

| 메서드    | 결과                        | 인수 없으면 |
| --------- | --------------------------- | ----------- |
| abs(x)    | 절대값. 반드시 0 이나 양수  | NaN         |
| round(x)  | 소수점 이하를 반올림한 정수 | NaN         |
| ceil(x)   | 소수점 이하를 올림한 정수   | NaN         |
| floor(x)  | 소수점 이하를 내림한 정수   | NaN         |
| sqrt(x)   | 제곱근. 음수면 NaN          | NaN         |
| random()  | 0이상 1미만 실수            |             |
| pow(b, e) | b의 e제곱                   | NaN         |
| max(...a) | 가장 큰 수                  | -Infinity   |
| min(...a) | 가장 작은 수                | Infinity    |
