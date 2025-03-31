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

<details>
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

<details>
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

<details>
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

<details>
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

<details>
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
