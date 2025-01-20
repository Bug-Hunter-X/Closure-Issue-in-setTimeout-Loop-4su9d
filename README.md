# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common issue in JavaScript related to closures and the `setTimeout` function within loops. The problem arises because the `setTimeout` callback function doesn't capture the value of `i` at the time it's created, but rather captures a reference to the variable `i`. By the time the `setTimeout` callbacks execute, the loop has already completed, resulting in all callbacks logging the final value of `i`.

## Bug Description

The provided `bug.js` file contains a function that uses a `for` loop and `setTimeout` to log numbers from 0 to 9 after a one-second delay.  However, due to closure issues, instead of logging 0 to 9 sequentially, it logs 10 ten times. This is because by the time the `setTimeout` functions execute, the loop has already completed and `i` has its final value of 10.

## Solution

The `bugSolution.js` file provides a corrected version of the code. This is achieved using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop. This ensures that each `setTimeout` callback captures its own unique value of `i`.