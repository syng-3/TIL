✔️null 병합 연산자 `??`를 사용하면 짧은 문법으로 여러 피연산자 중 그 값이 ‘확정되어있는’ 변수를 찾을 수 있다

✔️`a ?? b`의 평가 결과

- `a`가 `null`도 아니고 `undefined`도 아니면 `a`
- 그 외의 경우는 `b`

```jsx
let firstName = null;
let lastName = null;
let nickName = "Supercoder";

// null이나 undefined가 아닌 첫 번째 피연산자
alert(firstName ?? lastName ?? nickName ?? "Anonymous"); // Supercoder
```

### '??'와 '||'의 차이

✔️null 병합 연산자는 `OR` 연산자 `||`와 상당히 유사하다

✔️차이점

- `||`는 첫 번째 *truthy* 값을 반환합니다.
- `??`는 첫 번째 *정의된(defined)* 값을 반환합니다.

⭐`**null`과 `undefined`, 숫자 `0`을 구분 지어 다뤄야 할 때 이 차이점은 매우 중요한 역할을 한다**

```jsx
let height = 0;

alert(height || 100); // 100
alert(height ?? 100); // 0
```

1. `height || 100`은 `0`을 falsy 한 값으로 취급
2. `height ?? 100` 은 height가 정확하게 `null`이나 `undefined`일 경우에만 100이 된다

### 연산자 우선순위

✔️`??`의 연산자 우선순위는 꽤 낮다

✔️`??`는 `=`와 `?` 보다는 먼저, 대부분의 연산자보다는 나중에 평가된다

✔️복잡한 표현식 안에서 `??`를 사용해 값을 하나 선택할 땐 괄호를 추가하는 게 좋다

‼️안정성 관련 이슈 때문에 `??`는 `&&`나 `||`와 함께 사용하지 못한다 → **제약을 피하려면 괄호를 사용**

```jsx
let x = (1 && 2) ?? 3; // 제대로 동작합니다.

alert(x); // 2
```
