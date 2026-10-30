# 📘 Assignment: First Automated Tests: Checking Even Numbers

## 🎯 Objective

Use Python's built-in `assert` statement to automatically check an even-number function with ordinary values, zero, and negative numbers. Practice using a failing test to find a bug and checking that a fix preserves previously correct behavior in this beginner-friendly, 45-60 minute assignment; no additional libraries or internet access are required.

## 📝 Tasks

### 🛠️	Write an Even-Number Function

#### Description
Spend about 10 minutes creating `even_numbers.py` with a function named `is_even(number)`. Use your knowledge of functions and arithmetic to decide whether an integer is divisible by two.

#### Requirements
Completed program should:

- Accept one integer argument and return the boolean `True` for an even number or `False` for an odd number.
- Return a value rather than printing the result or requesting input.
- Handle positive integers, zero, and negative integers. Zero is even; negative numbers follow the same divisibility rule as positive numbers.
- Define the function without running interactive code when the file is imported. Handling strings, decimals, or other input types is outside this assignment's scope.

### 🛠️	Check Results with Assertions

#### Description
Spend about 20 minutes creating `test_even_numbers.py` in the same folder. Import `is_even` from `even_numbers` and write assertions that compare its results with independently chosen expected values.

An assertion passes silently when its condition is true. For example, this check verifies both the value and the boolean return type:

```python
from even_numbers import is_even

assert is_even(4) is True
```

#### Requirements
Completed program should:

- Include at least six assertions covering two positive even integers, a positive odd integer, zero, a negative even integer, and a negative odd integer.
- Use explicit expected boolean values with `is True` or `is False`, rather than calling the function again to calculate an expected result.
- Run all assertions using `python test_even_numbers.py` from the folder containing both files, without installing a testing framework. Use `python3` if that is your system's Python command; do not use `-O`, which disables assertions.
- Print `All tests passed!` only after every assertion has passed.
- Finish without an `AssertionError` when the implementation is correct.

### 🛠️	Find a Bug and Verify the Fix

#### Description
Spend the remaining 15-30 minutes checking whether your tests detect a mistake. Temporarily change `is_even` so that it returns `True` only for positive even numbers, incorrectly rejecting zero and negative even numbers. Run the tests, investigate the first failure, and restore the correct behavior without weakening your assertions.

#### Requirements
Completed program should:

- Produce an `AssertionError` with the deliberately faulty implementation, rather than printing the success message.
- Keep the zero and negative-even assertions in the test file. If execution stops at the zero check first, run the negative-even check separately to confirm that it also detects the bug.
- Pass every test again after the function is fixed, including tests for positive and negative odd numbers.
- Include `test-results.txt` recording the failing input, expected result, observed faulty result, and final successful test output. Add one or two sentences explaining why testing only positive even numbers would miss this bug.
- Submit `even_numbers.py`, `test_even_numbers.py`, and `test-results.txt` with the corrected implementation, not the deliberately faulty version.