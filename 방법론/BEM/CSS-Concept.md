# CSS with BEM

CSS는 페이지 레이아웃에 사용되며 블록 구현 기술중 하나로 간주된다.

## HTML 래퍼를 만드는 법

전통적으로 HTML 래퍼는 다음 용도로 사용된다.
- 다른 Element에 상대적인 HTML Element 위치 지정
- 섹션 내부에 Element 배치

BEM 방법론은 믹스를 사용하거나 추가 블록 Element를 생성하여 동잃란 결과를 얻는다. 추가적인 추상 래퍼를 만들 필요가 없다.

### 다른 블록을 기준으로 블록 위치 지정

다른 블록을 기준으로 위치를 지정할때는 일반적으로 Mix가 가장 좋다.

```
<body class="page">
  <!-- header and navigation -->
  <header class="header page__header">...</header>

  <!-- footer -->
  <footer class="footer page__footer">...</footer>
</body>
```

```
.page__header {
  padding: 20px;
}

.page__footer {
  padding: 50px;
}
```

### 블록 내부의 엘리먼트 배치

일반적으로 추가 블록 Element를 만들어 설정

```
<body class="page">
  <div class="page__inner">
    ...
  </div>
</body>
```

```
.page__inner {
  margin-right: auto;
  margin-left: auto;
  width: 960px;
}
```


## Selectors

BEM은 Tag 및 ID Selector를 사용하지 않는다. 오직 Class 만 사용한다.

우선순위 전투를 발생시키지 않기 위해.

마찬가지로 코드결합을 증가시키는 중첩 셀렉터, 결합 셀렉터 도 사용 최소화

Good
```
.button { }
.button--active { }
.button__icon { }
.button__text { }
.button_theme_islands { }
```

Bad
- 이름이 충돌할수 있음
- 각 블록이나 엘리먼트가 독립적이지 않을 수 있음
- 중첩 및 결합 셀렉터가 발생함

```
.button { }
.icon { }
.text { }
.theme_islands { }
```

### 예시

```
<div class="logo logo_theme_islands">
  <img src="URL" alt="logo" class="logo__img">

  <div class="user user_theme_islands">
    <img src="URL" alt="user logo" class="user__img">
  </div>
</div>
```

```
.logo { } /* logo block */
.logo__img { } /* logo__img element */
.logo_theme_islands { } /* logo_theme_islands modifier */
.user { }
.user__img { }
.user_theme_islands { }
```

## Modifiers

Modifier는 블록의 모양, 상태 및 동작을 설정한다. Modifier를 설정하거나 제거하면 블록의 디자인이 변경된다.

```
<button class="button button_size_s"></button
```

```
.button { }
.button_size_s { }
.button_Size_m { }
```

## Mix

믹스를 통해
- 코드를 복제하지 않고 여러 엔티티의 동작과 스타일을 결합
- 다른 HTML Element에 동일한 서식 적용

## 블록 그룹 스타일 지정

Bad

코드 결합이 생김
```
<article class="article">...</article>
<footer class="footer">
  <div class="copyright">...</div>
</footer>
```

```
.article, .footer div {
  ...
}
```

Good
```
<article class="article text">...</article>
<footer class="footer">
  <div class="copyright text">...</div>
</footer>
```

```
.text {
  ...
}
```

