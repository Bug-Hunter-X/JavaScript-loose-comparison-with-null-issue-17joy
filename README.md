# JavaScript Loose Comparison with Null
This repository demonstrates an uncommon bug in JavaScript related to loose comparison (==) with null. The function `foo` intends to check if a number is null, negative, or positive. However, due to the way loose comparison works with null in JavaScript, the output for `foo(0)` is unexpected (it returns 1 instead of 0).

## Bug
The bug stems from the loose comparison `a == null`.  In JavaScript, `0 == null` evaluates to `false`, leading to the `else` block being executed, resulting in an incorrect return value.

## Solution
The solution involves using strict equality (===) for null checks, to avoid the type coercion that causes this unexpected behavior. The fixed function uses `a === null` to explicitly check for null without type coercion.