
# Lab 6: Code and Branch Coverage Analysis

## Project: Warranty Claims

### About
This project implements a Python-based Warranty Claims system. It calculates out-of-warranty repair charges based on the warranty plan, product age, and claim type. It also checks claim eligibility and service deadline status.

### Objectives
- Understand code coverage and branch coverage.
- Measure test coverage using Python Coverage.
- Identify untested statements and decision branches.
- Improve test cases to achieve at least 90% coverage.

### Technologies Used
- Python 3.x
- pytest
- coverage.py

### Project Structure

```text
LAB6/
│
├── warranty_claims.py
├── test_warranty_claims.py
├── CodeCoverageTest_xxxx_application.py
├── BranchCoverageTest_xxxx_application.py
│
└── screenshots/
    ├── code_coverage.png
    └── branch_coverage.png
```

### Installation

Install the required dependencies:

```bash
pip install pytest coverage
```

### Running Tests

Run the initial test cases:

```bash
pytest -v
```

### Code Coverage Analysis

Execute tests with code coverage:

```bash
coverage run -m pytest CodeCoverageTest_xxxx_application.py
```

Display the coverage report:

```bash
coverage report -m
```

### Branch Coverage Analysis

Execute tests with branch coverage:

```bash
coverage run --branch -m pytest BranchCoverageTest_xxxx_application.py
```

Display the branch coverage report:

```bash
coverage report -m
```

### Coverage Results

The target is to achieve:

| Coverage Type | Target |
|---|---:|
| Code Coverage | At least 90% |
| Branch Coverage | At least 90% |

Refer to the screenshots folder for terminal evidence of the final coverage results.

### Deliverables
1. Code coverage test cases.
2. Branch coverage test cases.
3. Code coverage terminal screenshot.
4. Branch coverage terminal screenshot.
5. Minimum two Git commits for the separate test implementations.

### Conclusion

This lab demonstrates how code coverage and branch coverage help evaluate the completeness of software testing. Additional test cases are designed to cover untested statements, decision branches, and edge cases.
