# Test Cases — Swag Labs

## Test Case Summary

| ID | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC-001 | Log in with valid credentials | The user is redirected to the product catalog. | Not Run |
| TC-002 | Log in with an incorrect password | Access is denied and an error message is displayed. | Not Run |
| TC-003 | Log in with both fields empty | Access is denied and a required-field error message is displayed. | Not Run |
| TC-004 | Add a product to the cart | The cart displays the selected product with the corresponding price. | Not Run |
| TC-005 | Remove a product from the cart | The product is removed and the cart badge reflects the remaining number of items. | Not Run |
| TC-006 | Complete a purchase with valid test data | An order confirmation is displayed. | Not Run |

## Notes

- Expected results are preliminary test expectations.
- Their sources and any assumptions will be recorded when each test case is detailed.
- The initial walkthrough was application reconnaissance, not a documented test execution.

## TC-001 — Log in with valid credentials

### Objective
Verify that a user can access the product catalog using valid credentials.

### Preconditions
- The application is accessible.
- The user is on the login page.
- No user session is active.

### Test Data
- URL: https://www.saucedemo.com/
- Username: standard_user
- Password: secret_sauce

### Expected Result Basis
The login page provides these credentials as a demo account.
For this test, successful login is expected to display the product catalog.

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Enter the username in the Username field. | The field displays the entered username. |
| 2 | Enter the password in the Password field. | The password is entered and its characters are masked. |
| 3 | Click the Login button. | The product catalog is displayed with a list of products. |

### Execution Record
- Execution date and time: 2026-11-08 (14:47 - 14:48)
- Operating system: Debian GNU/Linux 13
- Browser and version: 155.0.8059.39
- Actual result: The username was displayed, the password was masked, and clicking Login opened the product catalog.
- Status: Passed
- Evidence:
  - [Login input](evidence/TC-001-login-input.png)
  - [Login result](evidence/TC-001-login-result.png)
- Related bug: Not applicable.

## TC-002 — Log in with an incorrect password

### Objective
Verify that a user cannot access the product catalog with an incorrect password.

### Preconditions
- The application is accessible.
- The user is on the login page.
- No user session is active.

### Test Data
- URL: https://www.saucedemo.com/
- Username: standard_user
- Password: wrong_password

### Expected Result Basis
For this test, the application is expected to reject an incorrect password.
The exact error message has not been specified.

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Enter the username in the Username field. | The entered username is displayed. |
| 2 | Enter the incorrect password in the Password field. | The password characters are masked. |
| 3 | Click the Login button. | Access is denied, an error message is displayed, and the user remains on the login page. |

### Execution Record
- Execution date and time: 2026-11-08 13:51
- Operating system: Debian GNU/Linux 13
- Browser and version: 155.0.8059.39
- Actual result: Access was denied and the user remained on the login page. The error message displayed was: "Epic sadface: Username and password do not match any user in this service".
- Status: Passed
- Evidence: [Invalid password result](evidence/TC-002-invalid-password-result.png)
- Related bug: Not applicable.

## TC-003 — Log in with both fields empty

### Objective
Verify that the application denies access when both login fields are empty.

### Preconditions
- The application is accessible.
- The user is on the login page.
- No user session is active.

### Test Data
- URL: https://www.saucedemo.com/
- Username: empty.
- Password: empty.

### Expected Result Basis
For this test, both credentials are assumed to be required.
The exact error message and validation order have not been specified.

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Clear the Username and Password fields. | Both fields are empty. |
| 2 | Click the Login button. | Access is denied, a required-field error message is displayed, and the user remains on the login page. |

### Execution Record
- Execution date and time: 2026-11-08 14:00
- Operating system: Debian GNU/Linux 13
- Browser and version: 155.0.8059.39
- Actual result: With both fields empty, access was denied and the user remained on the login page. The error message displayed was: "Epic sadface: Username is required".
- Status: Passed
- Evidence: [Empty fields result](evidence/TC-003-empty-fields-result.png)
- Related bug: Not applicable.

## TC-004 — Add a product to the cart

### Objective
Verify that a selected product is correctly added to the cart.

### Preconditions
- The user is logged in as standard_user.
- The product catalog is displayed.
- The cart is empty.

### Test Data
- Product: Sauce Labs Backpack
- Quantity: 1
- Reference price: Record the price displayed in the catalog before adding the product.

### Expected Result Basis
For this test, adding one product is expected to preserve its name
and catalog price in the cart, with a quantity of 1.

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Find Sauce Labs Backpack and record its displayed price. | The product name and price are visible. |
| 2 | Click Add to cart for this product. | The button changes to Remove and the cart badge displays 1. |
| 3 | Click the cart icon. | The cart page is displayed. |
| 4 | Check the product name, price, and quantity. | The cart contains only Sauce Labs Backpack, with the recorded catalog price and a quantity of 1. |

### Execution Record
- Execution date and time: 2026-11-08 (14:09 - 14:11)
- Operating system: Debian GNU/Linux 13
- Browser and version: 155.0.8059.39
- Reference catalog price: $29.99
- Actual result: After adding Sauce Labs Backpack, the button changed to Remove and the cart badge displayed 1. The cart contained only the selected product, with a quantity of 1 and a price of $29.99, matching the catalog price.
- Status: Passed
- Evidence:
  - [Catalog before adding](evidence/TC-004-catalog-before.png)
  - [Catalog after adding](evidence/TC-004-catalog-after.png)
  - [Cart result](evidence/TC-004-cart-result.png)
- Related bug: Not applicable.

## TC-005 — Remove a product from the cart

### Objective
Verify that a product can be removed from the cart.

### Preconditions
- The user is logged in as standard_user.
- The cart page is displayed.
- The cart contains only one Sauce Labs Backpack.

### Test Data
- Product to remove: Sauce Labs Backpack
- Initial quantity: 1

### Expected Result Basis
Removing the only product is expected to leave the cart empty
and remove the quantity badge from the cart icon.

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Check the cart before removal. | Only Sauce Labs Backpack is listed, with a quantity of 1, and the cart badge displays 1. |
| 2 | Click Remove for Sauce Labs Backpack. | The product disappears from the cart and the quantity badge is no longer displayed. |

### Execution Record
- Execution date and time: 2026-11-08 14:28
- Operating system: Debian GNU/Linux 13
- Browser and version: 155.0.8059.39
- Actual result: Clicking Remove for Sauce Labs Backpack on the cart page removed the only product. The cart became empty and the quantity badge was no longer displayed.
- Status: Passed
- Evidence:
  - [Cart before removal](evidence/TC-005-cart-before.png)
  - [Cart after removal](evidence/TC-005-cart-after.png)
- Related bug: Not applicable.

## TC-006 — Complete a purchase with valid test data

### Objective
Verify that a user can complete a simulated purchase with all checkout fields filled in.

### Preconditions
- The user is logged in as standard_user.
- The cart page is displayed.
- The cart contains only one Sauce Labs Backpack.

### Test Data
- Product: Sauce Labs Backpack
- Quantity: 1
- First Name: Alex
- Last Name: Tester
- Zip/Postal Code: 12345
- All customer information is fictional.

### Expected Result Basis
For this test, completing the checkout fields with the test data
is expected to allow access to the order overview.
Finishing the order is expected to display a purchase confirmation.
The postal code validation rules have not been specified.

### Test Steps

| Step | Action | Expected Result |
|---|---|---|
| 1 | Click Checkout on the cart page. | The checkout information form is displayed. |
| 2 | Enter the first name, last name, and postal code from the test data. | All three fields contain the entered values. |
| 3 | Click Continue. | The order overview is displayed. |
| 4 | Review the product, quantity, price, and totals. | Only Sauce Labs Backpack is listed, with quantity 1 and the same price as in the cart. Item total matches the product price, and Total equals Item total plus Tax. |
| 5 | Click Finish. | An order confirmation is displayed. |

### Execution Record
- Execution date and time: 2026-11-08 14:36
- Operating system: Debian GNU/Linux 13
- Browser and version: 155.0.8059.39
- Product price in cart: $29.99
- Item total: $29.99
- Tax: $2.40
- Total: $32.39
- Actual result: The checkout accepted the fictional customer information and displayed the order overview with one Sauce Labs Backpack at $29.99. The item total was $29.99, tax was $2.40, and the total was $32.39. Clicking Finish displayed "Thank you for your order!".
- Status: Passed
- Evidence:
  - [Checkout input](evidence/TC-006-checkout-input.png)
  - [Order overview](evidence/TC-006-order-overview.png)
  - [Order confirmation](evidence/TC-006-order-confirmation.png)
- Related bug: Not applicable.

### Limitations
This test checks the displayed total calculation.
It does not verify the tax rate against an external business rule.
