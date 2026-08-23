# Requirements Review

| Requirement ID | Requirement | Questions / Concerns |
|---|---|---|
| REQ-LOGIN-001 | The system shall allow a registered user to log in using a valid username and password. | What defines a valid username and password? |
| REQ-LOGIN-002 | The system shall reject login attempts where the username is incorrect. | Are usernames case-sensitive?<br><br>Should an incorrect username produce a different error message from an incorrect password? |
| REQ-LOGIN-003 | The system shall reject login attempts where the password is incorrect. | Should an incorrect password produce a different error message from an incorrect username? |
| REQ-LOGIN-004 | Username is mandatory. | What happens if the username is left blank?<br><br>Are numbers and special characters allowed?<br><br>What is the minimum and maximum username length?<br><br>Are usernames required to be in email format?<br><br>Should leading and trailing spaces be accepted or removed? |
| REQ-LOGIN-005 | Password is mandatory. | What happens if the password is left blank?<br><br>What is the minimum and maximum password length?<br><br>Are there password complexity requirements such as uppercase letters, numbers, or special characters?<br><br>Should passwords be masked when entered?<br><br>Are passwords allowed to contain the user's username, name, or birthdate? |
| REQ-LOGIN-006 | An appropriate error message shall be displayed when authentication fails. | "Appropriate error message" is ambiguous. What exact error message should be displayed for each authentication failure?<br><br>Is there a maximum number of failed login attempts?<br><br>What happens when the maximum number is reached?<br><br>What happens if the account is locked or disabled? |
| REQ-LOGIN-007 | A successfully authenticated user shall be redirected to the Products page. | Should unauthenticated users be prevented from accessing the Products page?<br><br>What happens if an unauthenticated user manually enters the Products page URL? |

## Product Requirements

| Requirement ID | Requirement | Questions / Concerns |
|---|---|---|
| REQ-PROD-001 | Authenticated users shall be able to view available products. | What defines an "available" product? Does it mean in stock, active, or simply present in the product catalogue? |
| REQ-PROD-002 | Each product shall display:<br><br>- Product name<br>- Description<br>- Price<br>- Product image<br>- Add to Cart button | What happens if a product image, name, description, or price is missing?<br><br>What currency and format should be used for the price? |
| REQ-PROD-003 | Users shall be able to sort products by:<br><br>- Name A-Z<br>- Name Z-A<br>- Price low-high<br>- Price high-low | What is the default sorting order when the Products page loads?<br><br>How should products with identical names or prices be ordered? |
| REQ-PROD-004 | Users shall be able to open an individual product. | "Open an individual product" is ambiguous. Should selecting a product open a product-details page, modal, or another view?<br><br>What information should be displayed when the product is opened? |

## Shopping Cart Requirements

| Requirement ID | Requirement | Questions / Concerns |
|---|---|---|
| REQ-CART-001 | Users shall be able to add a product to their shopping cart. | How does the user add the product? For example, must they select an "Add to Cart" button?<br><br>What should happen immediately after the product is added? |
| REQ-CART-002 | The cart counter shall update when a product is added. | What exactly does the cart counter represent: total units or unique products?<br><br>For example, if the cart contains two hats and three handbags, should the counter display 5 or 2? |
| REQ-CART-003 | Users shall be able to add multiple products. | Can the same product be added more than once?<br><br>If the same product is added twice, should it appear as two separate rows or one row with quantity 2?<br><br>Is there a maximum quantity that can be added? |
| REQ-CART-004 | Products added to the cart shall display the correct:<br><br>- Product name<br>- Price<br>- Quantity | Should the cart also display the product image, item subtotal, or overall cart total?<br><br>How should quantity be displayed for duplicate products? |
| REQ-CART-005 | Users shall be able to remove products from the cart. | What should happen when the last product is removed?<br><br>Should the cart display an empty-cart message? |
| REQ-CART-006 | Removing a product shall update the cart counter. | When the final product is removed, should the cart counter disappear or display 0? |
| REQ-CART-007 | Users shall be able to return to the Products page from the cart. | Should products already added to the cart remain in the cart when the user returns to the Products page? |

## Checkout Requirements

| Requirement ID | Requirement | Questions / Concerns |
|---|---|---|
| REQ-CHK-001 | Users with products in their cart shall be able to start checkout. | What happens if a user attempts to access checkout with an empty cart? |
| REQ-CHK-002 | Checkout shall require:<br><br>- First name<br>- Last name<br>- Postal code | Are these the only customer details required for checkout? |
| REQ-CHK-003 | First name is mandatory. | What constitutes a valid first name?<br><br>Are numbers and special characters allowed?<br><br>Is a single character such as "A" valid?<br><br>What is the minimum and maximum length? |
| REQ-CHK-004 | Last name is mandatory. | What constitutes a valid last name?<br><br>Are numbers and special characters allowed?<br><br>Is a single character such as "A" valid?<br><br>What is the minimum and maximum length? |
| REQ-CHK-005 | Postal code is mandatory. | What constitutes a valid postal code?<br><br>Must it be numeric?<br><br>Are letters allowed?<br><br>What format and length are expected? |
| REQ-CHK-006 | The system shall display an error when mandatory information is missing. | What exact error message should be displayed for each missing field?<br><br>Where should validation errors appear?<br><br>What happens if multiple mandatory fields are missing? |
| REQ-CHK-007 | Users who provide valid information shall proceed to the checkout overview. | "Valid information" is not defined. What validation rules determine whether the first name, last name, and postal code are valid? |
| REQ-CHK-008 | The checkout overview shall display the selected products. | Should users be able to change quantities or remove products from the checkout overview?<br><br>Can users return to the cart without losing their checkout information? |
| REQ-CHK-009 | The checkout overview shall display the item total. | How is the item total calculated?<br><br>Should it equal the sum of the prices and quantities of all products before tax? |
| REQ-CHK-010 | The checkout overview shall display tax. | How is tax calculated?<br><br>What tax rate should be applied?<br><br>How should tax values be rounded? |
| REQ-CHK-011 | The checkout overview shall display the final total. | How is the final total calculated?<br><br>Should the final total equal item total + tax?<br><br>Are there any additional fees or charges? |
| REQ-CHK-012 | Users shall be able to complete the purchase. | What should happen after the user selects the option to complete the purchase?<br><br>Should the cart be cleared after a successful purchase?<br><br>What happens if the purchase cannot be completed? |
| REQ-CHK-013 | A successful purchase shall display a confirmation message. | What exact confirmation message should be displayed?<br><br>Should an order/reference number be displayed?<br><br>Where can the user navigate after completing the purchase? |

## Logout Requirements

| Requirement ID | Requirement | Questions / Concerns |
|---|---|---|
| REQ-LOGOUT-001 | Authenticated users shall be able to open the application menu. | How should the application menu be opened?<br><br>Should the menu be available from every authenticated page? |
| REQ-LOGOUT-002 | Users shall be able to log out. | What should happen to the user's session and cart when they log out? |
| REQ-LOGOUT-003 | After logout, users shall be returned to the login page. | Should the authenticated session be invalidated immediately?<br><br>What happens if the user uses the browser Back button after logging out?<br><br>Should the user be prevented from accessing authenticated pages by manually entering their URLs after logout? |