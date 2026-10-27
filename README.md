
# Student Utilities – Unit Testing

## Overview

`student_utils.py` contains three utility functions:

- `calculate_average(marks)`: Calculates the average of student marks.
- `is_passing(mark)`: Checks whether a mark meets the passing threshold of 40.
- `get_grade(average)`: Returns a grade based on the student's average.

## How to Run the Tests

Run the following command from the project directory:

```bash
python test_student_utils.py
```

## Test Results

- **Total tests:** 9
- **Result:** All 9 tests passed
- **Status:** GREEN

### Sample Test Output

```text
.........
----------------------------------------------------------------------
Ran 9 tests in 0.000s

OK
```

Each dot represents a passing test. `OK` indicates that all nine tests passed successfully.

## RED → FIX → GREEN

- **RED:** Initial tests exposed issues in average calculation, passing-threshold handling, and grade classification.
- **FIX:** Corrected the average denominator, included the passing threshold using `>=`, and checked grade conditions from highest to lowest.
- **GREEN:** Reran the test suite and confirmed that all nine tests passed.

## Audit Summary

The code audit found that the nine reported tests cover the main corrected behaviors. However, additional tests are recommended to improve coverage:

1. **Empty input:** Test `calculate_average([])`. The intended behavior is to return `0` if the empty-list guard has been implemented.
2. **Failing grade:** Test `get_grade(40)` to verify it returns `"Fail"`.
3. **Grade boundaries:** Test `get_grade(45)`, `get_grade(60)`, and `get_grade(90)` to verify the threshold conditions.
4. **Invalid inputs:** Decide whether non-numeric or negative marks should be accepted or rejected, based on the project requirements.

See [audit.md](audit.md) for the detailed audit report.

**Note:** The nine tests passed in the reported test run. The additional scenarios above are recommendations and have not been confirmed as tested.
