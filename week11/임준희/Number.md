### Number 생성자 함수

- new Number(v)는 [[NumberData]] 슬롯에 숫자를 담은 래퍼 객체를 만든다. 인수가 없으면 0
- 인수는 ToNumeric으로 바꾼다. 못 바꾸면 NaN
- new 없이 불면 객체를 안 만들고 변환한 원시 값만 돌려준다.

```js
Number("10"); // 10
Number(""); // 0
Number(null); // 0
Number(undefined); // NaN
Number("0x10"); // 16
Number(10n); // 10   (BigInt → Number 변환은 Number()만 허용. +10n은 TypeError)
typeof new Number(1); // 'object'
new Number(1) === 1; // false
```

### 정적 메서드

- 전부 ES6, 공통점은 인수를 숫자로 바꾸지 않음. 숫자가 아니면 바로 false
  | 메서드 | true 조건 | 전역 함수와 차이 |
  | -- | -- | -- |
  | Number.isFinite(v) | Number이고 NaN, +-Infinity가 아님 | isFinite(null)은 true, Number.isFinite(null)은 false |
  | Number.isNaN(v) | Number이고 NaN | isNaN('abc')는 true, Number.isNaN('code)는 false |
  | Number.isInteger(v) | Number이고 유한하며 소수부 없음 | 5.0, 1e300, -0 전부 true |
  | Number.isSafeInteger(v) | isInteger이고 절대값이 2^53-1 이하 | 2\*\*53은 false |

### 프로토타입 메서드

- 전부 문자열을 돌려줌
  | 메서드 | 인수 |
  | -- | -- |
  |toExponential(f) | 숫자를 지수 표기법으로 변환하여 문자열로 반환 |
  |toFixed(f) | 소수점 아래 f자리까지 남기고 나머지를 반올림하여 문자열로 반환 |
  | toPrecision(p) | 전체 p자리까지 유효하게 반올림하여 문자열로 반환. p자리로 표현 못 하면 지수 표기법 |
  | toString(radix) | 숫자를 해당 진법의 문자열로 반환 |
