---
title: Validation
has_children: false
nav_order: 6
---

# Validation

## Testing approach

- Describe what approach you followed for testing your software
- If you followed TDD, describe it here
- Also mention which testing framework you used (e.g. `unittest` or `pytest`) and why

## Testing (automated)

> General recommendation: when discussing the tests below, please track to which requirement each test is related to.

### Unit testing

- Describe the unit tests you developed, and their rationale
- Report success rate and test coverage here

### Integration testing

- Describe couples of components that you tested together, and the corresponding test rationale/plan

- Report success rate and test coverage here

- If you used [test doubles](https://en.wikipedia.org/wiki/Test_double), describe her which type of double you used, and why

### System testing

- Describe the tests that you developed to automatically test the system as a whole
    + and the corresponding test rationale/plan
    + better would be to have system tests that match the acceptance criteria of the requirements

- Report success rate and test coverage here

- If you adopted containers (e.g. Docker compose) for testing, describe how you used them here
    + e.g. to run the system in a clean environment, or to run the tests in a clean environment

## Acceptance tests (manual)

### Connectivity Verification (Preliminary)

During the initial development of the **Data Acquisition Layer**, a manual verification script was created to ensure connectivity with Threat Intelligence providers.

**Test Script:** `tests/test_download.py`
**Goal:** Verify HTTP connection to Tranco and URLHaus and print a data preview.
**Execution:**
```bash
PYTHONPATH=. python3 tests/test_download.py
```

