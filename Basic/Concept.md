# CSS Concept

1. 외부 스타일 시트를 가장 선호할 것
2. 진짜 지구가 멸망하기 직전이 아니면 인라인 스타일을 작성하지 말 것 https://developer.mozilla.org/ko/docs/Learn/CSS/First_steps/How_CSS_is_structured

## CSS 작동 원리

1. 브라우저는 HTML을 로드한다.
2. HTML을 DOM으로 변환한다. DOM은 컴퓨터 메모리의 문서를 나타낸다. 
3. HTML 문서와 연결된 대부분의 리소스와 CSS를 가져온다.
4. 브라우저는 CSS를 분석하고 selector 유형별로 다른 규칙을 다른 buckets 으로 정렬한다. DOM 어느 노드에 어떤 규칙을 적용해야 하는지 결정하고, 필요에 따라 스타일을 첨부한다. (이 과정을 render tree라고 한다.)
5. render tree는 규칙이 적용된 후에 표시되어야 하는 구조로 배치된다.
6. 페이지의 시각적 표시가 화면에 표시된다. (painting)

Load HTML -> Parse HTML -> Create DOM tree -> Display
                  |             | Attach style to DOM nodes
                Load CSS -> Parse CSS

## 규칙 충돌

### 계단식

동일 Level의 selector라면 마지막 규칙이 우선된다.

### 우선 순위

element selector 는 점수가 낮다
class selector 는 점수가 높다

### 상속

일부 CSS 속성 값은 자식 element에 상속된다.

상속을 제어하기 위한 값

inherit : 속성 값을 부모 element의 속성 값과 동일하게 설정
initial : 브라우저의 기본 스타일 시트와 동일하게 설정
unset : 속성을 natural 값으로 재설정 한다. 즉, 속성이 자연적으로 상속되면 inherit 된 것처럼 작동하고 그렇지 않으면 initial 처럼 작동한다.

### 모든 속성 값 재설정

```
blockquote {
  background-color: red;
  border: 2px solid green;
}

.fix-this {
  all: unset; /* all 속성을 통해 모든 속성을 재설정한다. */
}
```

```
<blockquote>
  <p>This blockquote is styled</p>
</blockquote>

<blockquote class="fix-this">
  <p>This blockquote is not styled</p>
</blockquote>
```

## Cascade 이해하기

중요도 순

Importance (!important) > 우선 순위 > 소스 순서

우선 순위

inline > id selector > class selector, pseudo-class > element selector

!important는 계단식이 정상적으로 작동하는 방식을 변경하므로 반드시 필요한 경우가 아니면 절대로 사용하지 말자

id selector