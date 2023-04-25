# Answers to Javascript Part 1
1. line 9 prints `values added:  20`.
2. line 13 prints `final result:  20`.
3. line 9 prints `values added:  20`.
4. line 13 throws an error because since `result` was defined with keyword `let`, it was only defined in the `if` block. Once outside of the `if` block, `result` is no longer defined.
5. line 9 won't print anything because there is an error thrown on line 7 because we are not allowed to reassign a variable that was defined with the `const` keyword. Since the error is thrown, the rest of the function ceases to run.
6. line 13 also won't print anything because of the same error that was described in the previous question.