# BEM (Block Element Modifier)

## Block

논리적 및 기능적으로 독립적인 페이지 컴포넌트로, 웹 컴포넌트와 동일하다. 블록은 JavaScript, Templete, CSS 및 기타 구현기술을 캡슐화 한다.

## Block features

### Nested structure

블록은 다른 블록 안에 중첩될 수 있다.

ex )

Head Block (menu block, auth block, search block, logo bock)

### Arbitary placement

블록은 페이지에서 이동하거나 페이지 또는 프로젝트 간에 이동할 수 있다. 블록을 독립적인 개체로 구현하면 페이지에서 위치를 변경할 수 있고 적절한 기능과 모양을 보장할 수 있다.

### Re-use

인터페이스는 동일한 블록의 여러 인스턴스를 포함할 수 있다.

---

## Element

외부에서 사용할 수 없는 (독립적으로 사용할 수 없는) 블록의 구성요소.

예를들어 메뉴 항목은 메뉴 블록외 컨텍스트 외부에서 사용되지 않으므로 element 이다. 

ex) 메뉴내의 각 탭들

---

## Modifier

블록 또는 엘리먼트의 모양과 동작을 정의하는 BEM 객체 이다.

Modifier는 선택 사항이다. 수정자는 런타임시에 항상 변경될 수 있따.

---

## BEM entity

Block, Element, Modifier를 모두 BEM 엔티티 라고 한다.

이것은 개별 BEM 엔티티를 참조하는 데 사용할 수 있고, 블록, Element, Modifier에 대한 일반 용어로 사용할 수 있는 개념이다.

---

## BEM Tree

```
<header class="header">
  <img class="logo">
  <form class="search-form">
    <input class="input">
    <button class="button"></button>
  </form>
  <ul class="lang-switcher">
    <li class="lang-switcher__item">
      <a class="lang-switcher__link" href="url">en</a>
    </li>
    <li class="lang-switcher__item">
      <a class="lang-swithcer__link" href="url">ru</a>
    </li>
  </ul>
</header>
```


## 네이밍 규칙

엔티티의 이름은 고유한다.

엘리먼트의 엘리먼트는 없다. 

```
block-name__element-name_mod-name_mod-val
```


### Block name

```
<div class="menu">...</div>

.menu {
  color: red;
}
```

### Element name

```
<div class="menu">
  <span class="menu__item"></span>
</div>

.menu__item { 
  color: red;
}
```

### Block Modifier

```
<div class="menu menu_hidden">...</div>
<div class="menu menu_theme_islands">...</div>

.menu_hidden {
  display: none;
}

.menu_theme_islands {
  color: green;
}
```

### Element Modifier

```
<div class="menu">
  <span class="menu__item menu__item_visible menu__item_type_radio">...</span>
</div>
```

---

## 대체 네이밍 체계

위에는 고전적인 BEM 아래는 커뮤니티에서 활발히 사용되는 대체 솔루션

### Two dash style

```
block-name__elemen-name--mode-name--mode-val
```

### Camel Case style

```
blockName-elemName_modName_modVal
```

### React style

```
BlockName-ElemName_modName_modVal
```