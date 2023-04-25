# Answers to Javascript Part 2
1. line 12 should print `3`. Since `i` is defined by the keyword `var` in the for loop, the for loop will stop once `i` reaches the value `3`, since by then the condition `i < prices.length` is no longer true, where `prices.length` equals `3`. Thus, at line 12, `console.log(i)` should print `3`.
2. line 13 should print `150`. Since `discountedPrice` is defined by the keyword `var` on line 7, that means that it will retain its definition throughout the scope of the function. The last time that the value for `discountedPrice` is modified is in the last run of the for loop when `i = 2`. This means that `var discountedPrice = prices[i] * (1 - discount)` will set `discountedPrice` to `300 * (1 - 0.5)`, which is `150`. Thus, printing `discountedPrice` out on line 13 will print `150`.
3. line 14 should also print `150`. Again, since `finalPrice` is defined with the `var` keyword on line 4, it retains its definition throughout the scope of the function. The last time that `finalPrice` is set is when `i = 2` on the last iteration of the for loop, where `finalPrice = Math.round(discountedPrice * 100) / 100`. As we know from the last question, `discountedPrice` is set to `150`, so `(150 * 100) / 100` is still `150`, so line 14 will print `150`.
4. The function will return `[50, 100, 150]`. The code will run through the for loop, calculating `finalPrice` to be each price in the `prices` array subtracted by the discount from the `discount` variable before rounding to the nearest hundredth and then appending it to the `discounted` array. This means that after running the function with the inputs of `[100, 200, 300]` and `0.5`, you will get an array with everything half off, giving you `[50, 100, 150]`.
5. line 12 will throw an error because `i` is out of scope. It's defined with `let` on line 6, so when it exits the scope of the for loop, `i` is no longer defined, so an error is thrown.
6. line 13 throws an error as well because `discountedPrice` is declared inside the for loop and the `console.log` statement is called outside of the for loop, so `discountedPrice` is no longer defined there.
7. line 14 will print `150`, same as question 3, because `finalPrice` is declared with a `let` in the same scope as the `console.log` call, no errors are thrown, and the result will be the same as question 3.
8. Without any references to variables that are no longer defined outside of the for loop, the function will return `[50, 100, 150]`, same as question 4. This is because everything is still ran and `discounted` array will still update like normal.
9. line 11 will throw an error for the same reason as in question 5. `i` is defined with a `let` in the for loop, so when `console.log` is called outside the for loop, `i` isn't defined anymore and will throw an error.
10. line 12 will print `3` because the `console.log` statement is defined in the same scope as where `length` is declared on line 4. `length` isn't (and can't be) modified, so it remains as `prices.length` which is `3` given the input.
11. This function will return `[50, 100, 150]`. There are no errors because there are no references to variables that don't exist outside of scope. `discounted` still gets properly pushed to since while the contents of the array is changing, the pointer that `discounted` points at is not changing, so no error is thrown. This means that ultimately you get an array similar to the previous iterations of the `discountPrices` function with the same inputs.
12. In order of A through E:
    1. `student.name`
    2. `student['Grad Year']`
    3. `student.greeting()`
    4. `student['Favorite Teacher'].name`
    5. `student.courseLoad[0]`
13. In order of A through H
    1.  `'32'` because the integer `2` gets mapped into a string before being concatenated with the string `'3'`.
    2.  `1` because the string `'3'` gets mapped to the integer value `3` before doing `3 - 2` to get `1`.
    3.  `3` because `null` gets mapped to `0` and is added to `3` to get `3`.
    4.  `'3null'` because `null` gets mapped to the string `'null'` before being concatenated with `'3'` to get `'3null'`.
    5.  `4` because `true` gets mapped to `1` before being added to `3` to get `4`.
    6.  `0` because `false` gets mapped to `0` and `null` gets mapped to `0` before both are added together to get `0`.
    7.  `'3undefined'` because `undefined` gets mapped to the string `'undefined'` before being concatenated with `'3'`.
    8.  `NaN` because `'3'` is mapped to the integer `3` and `undefined` is mapped to `NaN`, so `3 - NaN` is `NaN`, or "not a number".
14. In order of A through F
    1.  `true`, because the string `'2'` is mapped to the number `2` and is compared like `2 > 1`.
    2.  `false`, because via lexicographical comparison, it will first compare the first character of the string with each other, and since `'2' < '1'` returns `false`, so does this comparison
    3.  `true` because the string `'2'` is mapped to the number `2`, and `2` is equal to `2`.
    4.  `false` because the string is not converted to a number this time and the number `2` is different from the string `'2'`
    5.  `false` because `true` is mapped to the integer `1`, and `2` is not equal to `1`.
    6.  `true` because `Boolean(2)` is `true` because the parameter given (`2`) is a truthy value, and `true` is equal to `true`
15. Both are equality checks, but `==` will automatically do type conversions while `===` will prevent type conversions from happening.
16. See `part2-question16.js`
17. Firstly, an array `newArr` will be initialized on line 2. A for loop will run a number of times equal to the length of `[1,2,3]`, which is 3 times, where every iteration it will push to `newArr` the result of `callback(array[i])`. Since the `doSomething(num)` function is given as the `callback` parameter and `doSomething` just returns `num * 2`, we essentially just push to `newArr` every element in the array `[1,2,3]` multiplied by 2. Thus, by the end of the for loop `newArr` will be `[2,4,6]`. The function will then return `newArr`, giving us `[2,4,6]`.
18. See `part2-question18.js`
19. This will print 4 lines into the console: line 1 will be `1`, line 2 will be `4`, line 3 will be `3`, line 4 will be `2`. This is because the `console.log` statements without a timeout will run first, then the ones on a timer will print based on their delays.