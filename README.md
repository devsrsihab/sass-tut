# SASS Practice

This repository is for practicing various functions in SASS, including number functions, string functions, color functions, and list functions.

## Table of Contents

- [1. Variable](#variable)
- [2. Nesting](#nesting)
- [3. Partials & Imports](#partials-imports)
- [4. Mixins](#mixins)
- [5. Extend](#extend)
- [6. Operators](#operators)
- [7. Interpolation](#interpolation)
- [8. Function](#function)
- [9. Number Functions](#number-functions)
- [10. String Functions](#string-functions)
- [11. Color Functions](#color-functions)
- [12. List Functions](#list-functions)

<details id="variable">
  <summary ><strong>Variable in SASS</strong></summary>

```scss
$primary: #3498db;
$text: #333;

button {
  background: $primary;
  color: $text;
}
```

</details>

<details>
  <summary><strong>Nesting in SASS</strong></summary>

```scss
.container {
  width: 100%;
  padding: 20px;

  .header {
    font-size: 24px;
    color: #333;
  }

  .content {
    margin-top: 10px;
    font-size: 16px;

    p {
      color: #666;
    }
  }
}
```

</details>

<details>
  <summary><strong>Partials & Imports in SASS</strong></summary>

```scss
// _variables.scss
$primary-color: #3498db;
$secondary-color: #2ecc71;
```

```scss
// styles.scss
@import "variables";

body {
  background-color: $primary-color;
}

.button {
  background-color: $secondary-color;
}
```

</details>

<details>
  <summary><strong>Number Functions in SASS</strong></summary>

```scss
// ===== Number Functions in SASS =====
padding: ceil(5.9);
padding: floor(2.9);
padding: round(2.4);
padding: max(1px, 4px);
padding: min(2px, 4px);
padding: percentage(0.76);
padding: comparable(11cm, 44mm);
padding: random(10px);
padding: unit(10rem);
padding: unitless(10);
```

</details>

<details> <summary><strong>String Functions in SASS</strong></summary>

```scss
// ===== String Functions in SASS =====
font-family: quote(Poppins);
font-family: unquote("Poppins");
font-family: to-upper-case("Poppins");
font-family: to-lower-case("POPPINS");
font-family: str-length("POPPINS");
font-family: str-index("Helvitica Neue", "Neue");
font-family: str-insert("Helvitica Neue", " Mono", 15);
font-family: str-slice("Helvitica Neue", 11);
font-family: unique-id();
```

</details>

<details> <summary><strong>Color Functions in SASS</strong></summary>

```scss
// ===== Color Functions in SASS =====
background-color: $card-bg;
background-color: darken($card_white_bg, 10);
background-color: lighten($primary-color, 34);
background-color: adjust-hue($primary-color, 355);
background-color: saturate($primary-color, 100);
background-color: desaturate($primary-color, 90);
background-color: mix($primary-color, blue, 50);
background-color: transparentize($primary-color, 0.8);
```

</details>

<details> <summary><strong>List Functions in SASS</strong></summary>

```scss
// ===== List Functions in SASS =====
$list: [10px 20px 30px 40px];
$list2: 50px, 60px, 70px, 80px;
padding: length($list);
padding: nth($list, 3);
padding: set-nth($list, 2, 23rem);
padding: join($list, $list2, comma);
padding: append($list, 11px, comma);
padding: zip($list, $list2);
padding: index($list, 300px);
padding: list-separator($list2);
padding: is-bracketed($list2);
```

</details>
