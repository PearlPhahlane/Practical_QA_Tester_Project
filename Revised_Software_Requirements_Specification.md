# Software Requirements Specification

## 1. Purpose

This document defines the functional requirements for the e-commerce application.

The application shall allow registered users to:

- Log in securely.
- Browse available products.
- View individual product details.
- Sort products.
- Add and remove products from a shopping cart.
- Complete the checkout process.
- Receive confirmation of a successful purchase.
- Log out securely.

---

# 2. Login Requirements

### REQ-LOGIN-001 — User Login

The system shall allow a registered user to log in using their registered username and password.

A login shall be successful only when both the username and password match an active registered account.

### REQ-LOGIN-002 — Username Validation

The system shall reject authentication when the entered username does not match a registered username.

Usernames shall:

- Be case-sensitive.
- Contain between 3 and 50 characters.
- Allow letters, numbers, underscores (`_`), hyphens (`-`), and periods (`.`).
- Not be required to use an email address format.
- Have leading and trailing spaces removed before authentication.

### REQ-LOGIN-003 — Incorrect Password

The system shall reject authentication when the username exists but the entered password does not match the password associated with that account.

The system shall not reveal whether the username or password was incorrect.

The following error message shall be displayed:

**"Username or password is incorrect."**

### REQ-LOGIN-004 — Mandatory Username

Username shall be mandatory.

If the user attempts to log in without entering a username, the system shall prevent authentication and display:

**"Username is required."**

If both username and password are empty, the system shall display:

**"Username is required."**

### REQ-LOGIN-005 — Mandatory Password

Password shall be mandatory.

Passwords shall:

- Contain between 8 and 64 characters.
- Contain at least one uppercase letter.
- Contain at least one lowercase letter.
- Contain at least one number.
- Contain at least one special character.
- Not contain the user's username.
- Be masked on the login screen.

If the user attempts to log in without entering a password, the system shall display:

**"Password is required."**

> Password complexity rules apply when a password is created or changed. During login, the system shall validate the entered password against the stored credentials rather than re-validating password complexity.

### REQ-LOGIN-006 — Failed Authentication

When authentication fails because the entered credentials do not match an existing account, the system shall display:

**"Username or password is incorrect."**

The system shall allow a maximum of **5 consecutive failed login attempts** for a registered username.

After the fifth consecutive failed attempt:

- The account shall be temporarily locked.
- The account shall remain locked for 15 minutes.
- Further login attempts during this period shall be rejected.
- The system shall display: **"Account temporarily locked. Please try again later."**

A successful login shall reset the failed-login counter.

Disabled accounts shall not be permitted to log in.

### REQ-LOGIN-007 — Successful Authentication

After successful authentication, the user shall be redirected to the Products page.

Unauthenticated users shall not be permitted to access authenticated application pages.

If an unauthenticated user manually enters the URL of an authenticated page, the system shall redirect the user to the Login page.

---

# 3. Product Requirements

### REQ-PROD-001 — Available Products

Authenticated users shall be able to view available products.

A product shall be considered available when:

- The product is active.
- The product is currently offered for sale.
- The product has a valid name and price.

Out-of-stock products shall remain visible but shall display **"Out of stock"**.

The Add to Cart button shall be disabled for out-of-stock products.

### REQ-PROD-002 — Product Information

Each available product shall display:

- Product name.
- Product description.
- Product price.
- Product image.
- Add to Cart button.

Prices shall be displayed in US dollars, include the `$` currency symbol, and display exactly two decimal places.

Example: **$29.99**

Products without a valid name or price shall not be displayed.

If a product image is unavailable, the system shall display a default placeholder image.

If a product description is unavailable, the system shall display **"No description available."**

### REQ-PROD-003 — Product Sorting

Users shall be able to sort products by:

- Name A-Z.
- Name Z-A.
- Price low-high.
- Price high-low.

The default sorting option shall be **Name A-Z**.

Name sorting shall be alphabetical and case-insensitive.

Price sorting shall use the numeric product price.

When two products have the same price, they shall be secondarily sorted by product name from A-Z.

### REQ-PROD-004 — Product Details

Users shall be able to select an individual product by clicking its product name or image.

Selecting a product shall open the Product Details page.

The Product Details page shall display:

- Product name.
- Product image.
- Product description.
- Product price.
- Add to Cart button.
- Back to Products button.

Selecting **Back to Products** shall return the user to the Products page.

---

# 4. Shopping Cart Requirements

### REQ-CART-001 — Add Product

Users shall be able to add an available product to the shopping cart by selecting the **Add to Cart** button.

After the product has been successfully added:

- The cart counter shall update.
- The Add to Cart button shall change to **Remove** for that product.

### REQ-CART-002 — Cart Counter

The cart counter shall display the total number of unique products currently in the cart.

For example, 2 × Backpack and 3 × Handbag shall result in a cart counter of **2**.

When the cart contains no products, the cart counter shall not be displayed.

### REQ-CART-003 — Multiple Products

Users shall be able to add multiple different products to the cart.

A product may only appear once in the cart.

The application shall not support increasing the quantity of an individual product beyond **1**.

Therefore, selecting Add to Cart for a product already in the cart shall not create a duplicate product entry.

### REQ-CART-004 — Cart Product Information

Each product in the shopping cart shall display:

- Product name.
- Product image.
- Product price.
- Quantity.
- Remove button.

Quantity shall display **1**.

The cart shall also display the total price of all products before tax.

### REQ-CART-005 — Remove Product

Users shall be able to remove individual products from the shopping cart using the **Remove** button.

When the final product is removed:

- The cart shall contain no product entries.
- The cart counter shall disappear.
- The system shall display **"Your cart is empty."**

### REQ-CART-006 — Cart Counter After Removal

Removing a product shall immediately decrease the cart counter by one.

When the final product is removed, the cart counter shall no longer be displayed.

### REQ-CART-007 — Continue Shopping

Users shall be able to return to the Products page from the shopping cart by selecting **Continue Shopping**.

Products already added to the cart shall remain in the cart when the user returns to the Products page.

---

# 5. Checkout Requirements

### REQ-CHK-001 — Start Checkout

Users shall only be able to start checkout when the shopping cart contains at least one product.

The Checkout button shall be disabled when the shopping cart is empty.

### REQ-CHK-002 — Customer Information

Checkout shall require:

- First name.
- Last name.
- Postal code.

All three fields shall be mandatory.

### REQ-CHK-003 — First Name Validation

First name shall:

- Contain between 1 and 50 characters.
- Allow alphabetic characters.
- Allow spaces, hyphens, and apostrophes.
- Not contain numbers.
- Not contain other special characters.
- Have leading and trailing spaces removed.

### REQ-CHK-004 — Last Name Validation

Last name shall:

- Contain between 1 and 50 characters.
- Allow alphabetic characters.
- Allow spaces, hyphens, and apostrophes.
- Not contain numbers.
- Not contain other special characters.
- Have leading and trailing spaces removed.

### REQ-CHK-005 — Postal Code Validation

Postal code shall:

- Contain between 3 and 10 characters.
- Allow letters and numbers.
- Allow spaces and hyphens.
- Not allow other special characters.
- Have leading and trailing spaces removed.

### REQ-CHK-006 — Mandatory Information Errors

If mandatory information is missing, the user shall not proceed to the Checkout Overview page.

The system shall display:

- **"First name is required."**
- **"Last name is required."**
- **"Postal code is required."**

Validation messages shall appear directly below the affected field.

If multiple fields contain errors, an error message shall be displayed below each affected field.

### REQ-CHK-007 — Valid Checkout Information

The user shall proceed to the Checkout Overview page only when:

- First name satisfies REQ-CHK-003.
- Last name satisfies REQ-CHK-004.
- Postal code satisfies REQ-CHK-005.

Invalid information shall prevent the user from proceeding.

### REQ-CHK-008 — Checkout Overview

The Checkout Overview page shall display all products currently selected for purchase.

For each product, the system shall display:

- Product name.
- Quantity.
- Price.

Users shall not be able to change quantities from the Checkout Overview page.

Users shall be able to select **Cancel** to return to the Products page.

Cancelling checkout shall not remove products from the shopping cart.

### REQ-CHK-009 — Item Total

The Checkout Overview page shall display the item total.

The item total shall equal the sum of the prices of all products in the cart before tax.

### REQ-CHK-010 — Tax

The Checkout Overview page shall display tax.

Tax shall be calculated as:

**Item Total × 8%**

Tax shall be rounded to two decimal places using standard mathematical rounding.

### REQ-CHK-011 — Final Total

The Checkout Overview page shall display the final total.

The final total shall be calculated as:

**Item Total + Tax**

No additional shipping or service fees shall apply.

### REQ-CHK-012 — Complete Purchase

Users shall be able to complete the purchase by selecting the **Finish** button on the Checkout Overview page.

The Finish button shall only process the purchase once per checkout transaction.

After a successful purchase:

- The order shall be marked as completed.
- The shopping cart shall be cleared.
- The cart counter shall disappear.
- The user shall be redirected to the Checkout Complete page.

If the purchase cannot be completed, the user shall remain on the Checkout Overview page and the system shall display **"Unable to complete your order. Please try again."**

### REQ-CHK-013 — Purchase Confirmation

After a successful purchase, the Checkout Complete page shall display:

**"Thank you for your order!"**

The page shall also display a unique order reference number.

The user shall be able to select **Back Home**.

Selecting Back Home shall return the user to the Products page.

The shopping cart shall remain empty.

---

# 6. Logout Requirements

### REQ-LOGOUT-001 — Application Menu

Authenticated users shall be able to open the application menu.

The application menu shall be accessible from every authenticated application page.

The menu shall contain a **Logout** option.

### REQ-LOGOUT-002 — Logout

Users shall be able to log out by selecting **Logout** from the application menu.

Logging out shall:

- End the authenticated session.
- Clear authentication/session information.
- Preserve the shopping cart for the same user for their next authenticated session.

### REQ-LOGOUT-003 — After Logout

After logout, the user shall be redirected to the Login page.

The user shall not be able to access authenticated pages after logout.

If the user selects the browser Back button or manually enters the URL of an authenticated page, the system shall prevent access and redirect the user to the Login page.

A new successful login shall be required to access authenticated functionality.

---

# 7. Requirement Acceptance

These requirements supersede the previous version of the requirements document.

All questions and concerns identified during the QA Requirements Review have been addressed in this revision.

QA may now use these requirements as the test basis for:

1. Test scenario development.
2. Test case design.
3. Positive testing.
4. Negative testing.
5. Boundary-value testing.
6. Test execution.
7. Defect identification and reporting.
