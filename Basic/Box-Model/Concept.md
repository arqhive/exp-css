# Box Model

CSS의 모든 것은 주위에 상자가 있다.

## Block Box

- 상자가 새 줄로 나뉜다.
- 상자는 컨테이너에서 사용 가능한 공간을 채우기 위해 인라인 방향으로 확장된다.
- width, height를 존중한다.
- padding, margin, border 등으로 인해 다른 element가 상자에서 밀려난다.

## Inline Box

- 상자가 새 줄로 넘어가지 않는다.
- width, height가 적용되지 않는다.
- vertical padding, margin, border가 적용되지만 다른 인라인 Box가 Box에서 멀어지는 것은 아님
- horizontal padding, margin, border가 적용되고 다른 인라인 Box가 Box에서 멀어지게 한다.

display 속성을 통해 박스의 성격을 변경할 수 있다.

기본적으로 박스안의 Element는 Normal flow로 배치된다. 즉, 박스 내부의 Element도 블록 및 인라인 박스의 형식으로 적용된다.

## 상자의 구성 요소

padding, margin, content, border