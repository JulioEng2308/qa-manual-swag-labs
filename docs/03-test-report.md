# Test Execution Report — Swag Labs

## Overview
This report summarizes the first manual test cycle for Swag Labs.

- Tester: Julio Cesar Cerrate Castro
- Application: https://www.saucedemo.com/
- Execution date: 2026-11-08
- Test account: standard_user
- Environment details: Recorded in each test case execution record.

## Objective
Evaluate selected login validations, cart operations,
and the successful completion of a simulated purchase.

## Results

| ID | Test Scenario | Status |
|---|---|---|
| TC-001 | Log in with valid credentials | Passed |
| TC-002 | Log in with an incorrect password | Passed |
| TC-003 | Log in with both fields empty | Passed |
| TC-004 | Add a product to the cart | Passed |
| TC-005 | Remove a product from the cart | Passed |
| TC-006 | Complete a purchase with valid test data | Passed |

## Execution Summary

| Metric | Count |
|---|---|
| Planned test cases for this cycle | 6 |
| Executed | 6 |
| Passed | 6 |
| Failed | 0 |
| Blocked | 0 |
| Not Run | 0 |

## Findings
No confirmed functional defects were identified in the six executed scenarios.

During the initial attempt at TC-002, access to the catalog was reported.
The credentials used in that attempt were not confirmed.
The test was repeated after logout with the specified incorrect password,
and access was denied. The initial observation remains unconfirmed
and was not classified as a defect.

## Checkout Verification
The order overview displayed:
- Product: Sauce Labs Backpack
- Quantity: 1
- Item total: $29.99
- Tax: $2.40
- Total: $32.39

The displayed total matched the sum of the item total and tax.
Completing the checkout displayed "Thank you for your order!".

## Limitations
- This cycle covered only six selected scenarios.
- Logout and product details were not evaluated through dedicated test cases.
- Empty username and empty password were not tested separately.
- Cart and checkout scenarios used only one product and one unit.
- Expected results include documented assumptions rather than a complete
  approved business requirements specification.
- Postal code validation rules and the tax rate were not independently verified.
- Cross-browser, mobile, performance, and in-depth security testing
  were not performed.
- Passing these tests does not establish that the application is defect-free.

## Conclusion
The six executed test cases met their documented expected results
in the recorded environment.

Additional testing is needed to cover the remaining scope
and investigate other input combinations.

## References
- [Test scope](01-scope.md)
- [Test cases and execution records](02-test-cases.md)
- [Evidence folder](evidence/)
