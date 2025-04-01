# SASS Practice

This repository is for practicing various functions in SASS, including number functions, string functions, color functions, and list functions.

## Table of Contents

- [1. Variable](#variable)
- [2. Nesting](#nesting)
- [3. Partials & Imports](#partialsImports)
- [4. Mixins](#mixins)
- [5. Extend](#extend)
- [6. Operators](#operators)
- [7. Interpolation](#interpolation)
- [8. Function](#function)
- [9. Number Functions](#numberFunctions)
- [10. String Functions](#stringFunctions)
- [11. Color Functions](#colorFunctions)
- [12. List Functions](#listFunctions)
- [13. Selector ](#selector)
- [14. Map ](#map)
- [14. Introspection ](#introspection)

<details id="variable">
  <summary ><strong>1. Variable in SASS</strong></summary>

```scss
$primary: #3498db;
$text: #333;

button {
  background: $primary;
  color: $text;
}
```

</details>

<details id="nesting">
  <summary><strong>2. Nesting in SASS</strong></summary>

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

<details id="partialsImports">
  <summary><strong>3. Partials & Imports in SASS</strong></summary>

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

<details id="mixins">
  <summary><strong>4. Mixins in SASS</strong></summary>

```scss
// Mixin definition
@mixin button-styles($bg-color, $text-color) {
  background-color: $bg-color;
  color: $text-color;
  padding: 10px 20px;
  border-radius: 5px;
  border: none;
  font-size: 16px;

  &:hover {
    opacity: 0.8;
  }
}

// Using the mixin
.button-primary {
  @include button-styles(#3498db, white);
}

.button-secondary {
  @include button-styles(#2ecc71, white);
}
```

</details>

<details id="extend">
  <summary><strong>5. Extend in SASS</strong></summary>

```scss
// Base styles
.button {
  padding: 10px 20px;
  border-radius: 5px;
  border: none;
  font-size: 16px;
}

// Extend the base styles
.button-primary {
  @extend .button;
  background-color: #3498db;
  color: white;
}

.button-secondary {
  @extend .button;
  background-color: #2ecc71;
  color: white;
}
```

</details>

<details id="operators">
  <summary><strong>6. Operators in SASS</strong></summary>

```scss
// ===================== Arithmetic Operators =====================

// Addition (+)
$a: 5;
$b: 10;
$add: $a + $b; // Adds $a and $b, result = 15

// Subtraction (-)
$subtract: $b - $a; // Subtracts $a from $b, result = 5

// Multiplication (*)
$multiply: $a * 2; // Multiplies $a by 2, result = 10

// Division (/)
$divide: $b / $a; // Divides $b by $a, result = 2

// Modulus (%)
$modulus: $b % $a; // Divides $b by $a and returns the remainder, result = 0

// ===================== Comparison Operators =====================

// Equal to (==)
$is_equal: $a == $b; // Checks if $a is equal to $b, result = false

// Not equal to (!=)
$is_not_equal: $a != $b; // Checks if $a is not equal to $b, result = true

// Greater than (>)
$is_greater: $b > $a; // Checks if $b is greater than $a, result = true

// Less than (<)
$is_lesser: $a < $b; // Checks if $a is less than $b, result = true

// Greater than or equal to (>=)
$is_greater_or_equal: $b >= $a; // Checks if $b is greater than or equal to $a, result = true

// Less than or equal to (<=)
$is_lesser_or_equal: $a <= $b; // Checks if $a is less than or equal to $b, result = true

// ===================== Boolean Operators =====================

// AND (and)
$is_true: true and false; // Checks if both expressions are true, result = false

// OR (or)
$is_false: false or true; // Checks if at least one expression is true, result = true

// NOT (not)
$is_not_true: not true; // Inverts the boolean value of true, result = false

// ===================== String Operators =====================

// String Concatenation (+)
$string1: "Hello, ";
$string2: "world!";
$string_concat: $string1 + $string2; // Concatenates $string1 and $string2, result = "Hello, world!"

// ===================== Unary Operators =====================

// Negation (-)
$negate: -$a; // Negates the value of $a, result = -5

// ===================== List Operators =====================

// Join Lists (+)
$list1: 10px, 20px, 30px;
$list2: 40px, 50px;
$list_joined: $list1 + $list2; // Joins two lists, result = 10px, 20px, 30px, 40px, 50px

// List Separator (,)
$list: 10px, 20px, 30px; // Creates a list of values

// ===================== Example Output =====================

// Displaying results in a comment or for debugging purposes
// You can use these variables in your styles or debugging to see the results
// You could write the results to the console in a CSS rule if necessary:

.debug {
  content: "Addition result: #{$add}"; // Will output: "Addition result: 15"
  content: "Subtraction result: #{$subtract}"; // Will output: "Subtraction result: 5"
  content: "Multiplication result: #{$multiply}"; // Will output: "Multiplication result: 10"
  content: "Division result: #{$divide}"; // Will output: "Division result: 2"
  content: "Modulus result: #{$modulus}"; // Will output: "Modulus result: 0"
  content: "String Concatenation: #{$string_concat}"; // Will output: "String Concatenation: Hello, world!"
}
```

</details>

<details id="interpolation">
  <summary><strong>7. Interpolation in SASS</strong></summary>

```scss
// Mixin to set margin for a specific position (top, right, bottom, left)
@mixin margin($pistion, $unit) {
  margin-#{$pistion}: #{$unit}; // Dynamically set margin for the specified side
}

// Using the mixin to apply margin to different sides dynamically
.box1 {
  @include margin(top, 10px); // Apply margin-top: 10px
}

.box2 {
  @include margin(right, 15px); // Apply margin-right: 15px
}

.box3 {
  @include margin(bottom, 20px); // Apply margin-bottom: 20px
}

.box4 {
  @include margin(left, 25px); // Apply margin-left: 25px
}
```

</details>

<details id="function">
  <summary><strong>8. Functions in SASS</strong></summary>

```scss
// Function to calculate padding based on screen width
@function dynamic-padding($base-padding) {
  $viewport-width: 100vw; // 100% of viewport width
  $padding: $base-padding * ($viewport-width / 1000); // Scale padding with screen size (e.g., 1000px base)
  @return $padding;
}

// Applying dynamic padding to elements
.container {
  padding: dynamic-padding(20); // Will scale the padding based on screen size
}

.box {
  padding: dynamic-padding(10); // Smaller padding for the box
}
```

</details>

<details id="numberFunctions">
  <summary><strong>9. Number Functions in SASS</strong></summary>

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

<details id="stringFunctions"> 
<summary><strong>10. String Functions in SASS</strong></summary>

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

<details id="colorFunctions">
 <summary><strong>11. Color Functions in SASS</strong></summary>

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

<details id="listFunctions">
 <summary><strong>12. List Functions in SASS</strong></summary>

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

<details id="selector">
  <summary><strong>13. Selector  in SASS</strong></summary>

```scss
// ===== selectors in sass =====
$selector: selector-nest("ul", "li"); // "ul li"
$selector: selector-append(".acb,", "_active"); // ".acb_active"
$selector: selector-replace("a.abc.extra", ".extra", ".sohan"); // "a.abc.sohan"
$selector: is-superselector("a", "nav a"); // true
$selector: simple-selectors("a.sohan"); // ["a", ".sohan"]
$selector: selector-unify("a.active", "a.deactive"); // "a"
$selector: selector-extend(
  "a.active",
  "a",
  "deactive"
); // "a.active, a.deactive"

#{$selector} {
  width: 10px;
}
```

</details>

<details id="map">
  <summary><strong>14. Map in SASS</strong></summary>

```scss
// ===== map in sass =====
$font-weight: (
  "thin": 100,
  "light": 300,
  "regular": 400,
  "medium": 500,
  "bold": 700,
  "black": 900,
);
$light_weight: (
  "thin": 100,
  "light": 300,
  "regular": 400,
  "medium": 500,
  "bold": 700,
  "black": 900,
);
$bold_weight: (
  "medium": 500,
  "bold": 700,
  "black": 900,
);

$map_merge: map-merge($light_weight, $bold_weight); // Merges both maps
$map_mr: map-remove(
  $light_weight,
  "bold"
); // Removes "bold" key from $light_weight

.test {
  font-weight: map-get(
    $font-weight,
    "thine"
  ); // null (incorrect key, should be "thin")
  font-weight: map-keys(
    $font-weight
  ); // ("thin", "light", "regular", "medium", "bold", "black")
  font-weight: map-values($font-weight); // (100, 300, 400, 500, 700, 900)
  font-weight: map-has-key($light_weight, "thin"); // true
}
```

</details>

<details id="introspection ">
  <summary><strong>15. Introspection  in SASS</strong></summary>

```scss
$cha: "Arial";
$list: 10px 33px 55px;
$map: (
  "regular": 400,
  "medium": 500,
);
$num: 22px;

@mixin border_radius($radius) {
  border-radius: $radius;
}

@function adds($a, $b) {
  @return $a + $b;
}

.test {
  padding: variable-exists(num); // true (local scope variable $num exists)
  padding: global-variable-exists(
    num
  ); // true (global scope variable $num exists)
  padding: mixin-exists(
    border_radiuss
  ); // false (typo in mixin name, should be border_radius)
  padding: function-exists(adds); // true (function 'adds' exists)
  padding: type-of(map); // "map" (returns the type of $map)
  padding: inspect(num); // 22px (inspects and returns the value of $num)
}
```

</details>
