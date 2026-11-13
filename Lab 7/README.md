# L6_L7_43 — Warranty Claims

## Lab 7: Fuzz Testing for Input Validation Bugs

## 1. About the Project

This project demonstrates **Fuzz Testing using Python and the Hypothesis library** to identify and fix input-validation bugs in a Warranty Claims Processing application.

The application performs three main operations:

- Parses warranty claim details and warranty duration.
- Calculates the average age of products.
- Calculates the payable repair charge after applying tax and discount.

Hypothesis is used to automatically generate unexpected and invalid inputs to identify potential errors and improve application robustness.

## 2. Objectives

- Understand fuzz testing and property-based testing.
- Explore the Hypothesis testing library.
- Identify input-validation bugs using automatically generated inputs.
- Test application functions against unexpected and malformed data.
- Implement defensive input validation.
- Verify the corrected application using Pytest.

## 3. Project Structure

```text
Lab 7/
│
├── README.md
├── warranty_claims.py
└── test_warranty_claims.py
```

| File | Description |
|---|---|
| `README.md` | Project documentation and execution instructions. |
| `warranty_claims.py` | Python application containing the three functions under test. |
| `test_warranty_claims.py` | Hypothesis-based test cases for input validation. |

## 4. Technologies Used

- Python 3.8+
- Hypothesis
- Pytest
- Visual Studio Code
- Git and GitHub

## 5. Installation and Setup

### Step 1: Create and Activate Virtual Environment

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

### Step 2: Install Dependencies

```bash
python -m pip install hypothesis pytest
```

### Step 3: Verify Installation

```bash
python -m pytest --version
```

## 6. Application Execution

Run the original or corrected application using:

```bash
python warranty_claims.py
```

The application accepts three types of input:

| Function | Example Input | Purpose |
|---|---|---|
| `parse_claim()` | `standard:30` | Parses warranty plan and duration. |
| `age_average()` | `12,24,36` | Calculates average product age. |
| `payable_charge()` | `1500\|200` | Calculates payable repair charge. |

## 7. Fuzz Testing Using Hypothesis

Hypothesis generates different inputs automatically to test the application's functions.

The test module covers:

1. `test_parse_claim_no_crash()` – Tests warranty claim parsing.
2. `test_age_average_no_crash()` – Tests product age calculation.
3. `test_payable_charge_no_crash()` – Tests payable charge calculation.

The tests use Hypothesis strategies such as:

- `st.text()` – Generates different strings.
- `st.none()` – Generates None values.

### Run the Tests

```bash
python -m pytest test_warranty_claims.py -v
```

Hypothesis explores generated inputs and reports failures with counterexamples when the tested property is violated.

## 8. Bug Identification and Fixing

The original application may encounter errors when it receives:

- Missing or incorrect delimiters.
- Empty input values.
- Non-numeric values.
- Unexpected input types.
- Invalid numeric values.

The application is improved through defensive programming and input validation.

The corrected functions should reject invalid inputs clearly while preserving the expected results for valid inputs.

## 9. Expected Valid Input Results

| Function | Input | Expected Result |
|---|---|---|
| `parse_claim()` | `standard:30` | `('Standard', 30.0)` |
| `age_average()` | `12,24,36` | `24` |
| `payable_charge()` | `1500\|200` | `1570.0` |

## 10. Final Verification

After fixing the application, execute:

```bash
python warranty_claims.py
```

Then rerun the Hypothesis tests:

```bash
python -m pytest test_warranty_claims.py -v
```

The final objective is to ensure all three test functions pass with the corrected implementation.

## 11. Deliverables

1. Updated `warranty_claims.py` application.
2. Completed `test_warranty_claims.py` test cases.
3. Lab 7 fuzz-testing report in PDF format.
4. Screenshots of original execution, initial test failures, corrected execution, and final test results.

## 12. Conclusion

This laboratory demonstrates how fuzz testing and property-based testing can improve software quality and reliability. By using Hypothesis, unexpected inputs can be generated automatically to identify input-validation weaknesses. Defensive programming helps handle invalid inputs safely and makes the Warranty Claims Processing application more robust.

---

**Repository:** L6_L7_43_warranty_claims  
**Lab:** 7 – Fuzz Testing  
**Testing Framework:** Hypothesis and Pytest