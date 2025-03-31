# SASS Practice

This repository is for practicing various functions in SASS, including number functions, string functions, color functions, and list functions.

## Table of Contents
- [Number Functions](#number-functions)
- [String Functions](#string-functions)
- [Color Functions](#color-functions)
- [List Functions](#list-functions)

<details>
  <summary><strong>Number Functions in SASS</strong></summary>


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
</details> 

<details> <summary><strong>String Functions in SASS</strong></summary>
```
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
// ===== Color Functions in SASS =====
background-color: $card-bg;
background-color: darken($card_white_bg, 10);
background-color: lighten($primary-color, 34);
background-color: adjust-hue($primary-color, 355);
background-color: saturate($primary-color, 100);
background-color: desaturate($primary-color, 90);
background-color: mix($primary-color, blue, 50);
background-color: transparentize($primary-color, 0.8);
</details>

<details> <summary><strong>List Functions in SASS</strong></summary>
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
</details> 
