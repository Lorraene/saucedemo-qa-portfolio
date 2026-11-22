# Test Cases: SauceDemo

**URL:** https://www.saucedemo.com/
**Accounts:** the usernames and the shared password are displayed on the login page itself.
**How to use this file:** execute each case, then fill in **Actual result**, **Status** (Pass / Fail / Blocked) and **Date**. A case that fails is either a bug (create a report in `03-bug-reports/`) or a wrong assumption (note it in the plan).

> The **Expected results** below come from my assumed requirements (see `01-test-plan.md`). Messages quoted in quotation marks must be checked against the real site on the first run and corrected if the wording differs.

---

## Login

### TC-001: Login with valid credentials
- **Requirement:** REQ-01 | **Priority:** High | **Technique:** equivalence partitioning (valid partition)
- **Preconditions:** logged out, login page open
- **Test data:** username `standard_user`, password: the shared one shown on the page
- **Steps:**
  1. Enter the username.
  2. Enter the password.
  3. Click **Login**.
- **Expected result:** the product list opens and shows 6 products.
- **Actual result:** We were able to login and see 6 products.
- **Status:** Pass | **Date:** November 8, 2026 and November 22, 2026 | **Env:** E2
- **Evidence:**
  [TC01-Login page](https://github.com/user-attachments/assets/f77cf942-5090-4c77-9514-4677e0d50ac5) ;
  [TC01-homepage](https://github.com/user-attachments/assets/3877f429-ad8c-4050-9050-1ac7fc79a916) ;
[TC01-Homepage logout button](https://github.com/user-attachments/assets/0283da6a-67db-4a32-9668-5fa364328814) ;
  [TC01-logout page](https://github.com/user-attachments/assets/252d4f6d-9c38-4a73-aa43-7bcc28cf6b8b)

### TC-002: Login with a locked-out user
- **Requirement:** REQ-02 | **Priority:** High | **Technique:** equivalence partitioning (valid username, blocked)
- **Test data:** username `locked_out_user`, valid shared password
- **Steps:**
  1. Fill in username and password.
  2. Click **Login**.
- **Expected result:** the user stays on the login page and sees an error saying the user has been locked out.
- **Actual result:** The user stays on the login page and sees an error saying the user has been locked out.
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-003: Login with a wrong password
- **Requirement:** REQ-03 | **Priority:** High | **Technique:** equivalence partitioning (invalid partition)
- **Test data:** username `standard_user`, password `wrong_password`
- **Steps:**
  1. Fill in username and password.
  2. Click **Login**.
- **Expected result:** login is refused with an error saying username and password do not match.
- **Actual result:** Login was refused with an error saying username and password do not match
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-004: Login with an empty username
- **Requirement:** REQ-03 | **Priority:** Medium | **Technique:** equivalence partitioning
- **Test data:** username empty, valid password
- **Steps:**
  1. At the login page, leave username empty.
  2. Enter the password.
  3. Click **Login**.
- **Expected result:** error saying the username is required.
- **Actual result:** A message show up saying username is required.
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-005: Login with an empty password
- **Requirement:** REQ-03 | **Priority:** Medium | **Technique:** equivalence partitioning
- **Test data:** username `standard_user`, password empty
- **Steps:**
  1. At the login page, enter the username .
  2. Leave password empty.
  3. Click **Login**.
- **Expected result:** error saying the password is required.
- **Actual result:** A message show up saying password is required, "Epic sadface: Password is required".
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-006: Open the product page without logging in
- **Requirement:** REQ-04 | **Priority:** High | **Technique:** experience-based
- **Preconditions:** logged out, no active session
- **Steps:**
  1. Open the product list address directly (`https://www.saucedemo.com/inventory.html`) in a new tab.
- **Expected result:** the site sends the user to the login page and does not show products.
- **Actual result:** The site sends the user to the login page and does not show products, the following message show up
" Epic sadface: You can only access '/inventory.html' when you are logged in.".
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

---

## Products

### TC-007: Sort products by price, low to high
- **Requirement:** REQ-05 | **Priority:** Medium | **Technique:** equivalence partitioning (each sort option is one partition)
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Open the sort dropdown.
  2. Choose **Price (low to high)**.
  3. Read the six prices from top to bottom.
- **Expected result:** prices appear in ascending order.
- **Actual result:** $7.99, $9.99, $15.99, $15.99, $29.99, $49.99.
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2
- **Note:** repeat for the other three sort options as TC-007b, TC-007c, TC-007d.

  ### TC-007b: Sort products by price, high to low
- **Requirement:** REQ-05 | **Priority:** Medium | **Technique:** equivalence partitioning (each sort option is one partition)
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Open the sort dropdown.
  2. Choose **Price (high to low)**.
  3. Read the six prices from top to bottom.
- **Expected result:** prices appear in descending order.
- **Actual result:** $49.99, $29.99, $15.99, $15.99, $9.99, $7.99.
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

  ### TC-007c: Sort products by name, A to Z
- **Requirement:** REQ-05 | **Priority:** Medium | **Technique:** equivalence partitioning (each sort option is one partition)
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Open the sort dropdown.
  2. Choose **Name (A to Z)**.
  3. Read the six prices from top to bottom.
- **Expected result:** prices appear sorted by name in ascending order.
- **Actual result:**
$29.99 Backpack,
$9.99 Bike Light,
$15.99 Bolt T-Shirt,
$49.99 Fleece Jacket,  
$7.99 Onesie,
$15.99 T-shirt
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

  ### TC-007d: Sort products by name, Z to A
- **Requirement:** REQ-05 | **Priority:** Medium | **Technique:** equivalence partitioning (each sort option is one partition)
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Open the sort dropdown.
  2. Choose **Name (Z to A)**.
  3. Read the six prices from top to bottom.
- **Expected result:** prices appear sorted by name in descending order.
- **Actual result:**
$15.99 T-shirt,
$7.99 Onesie,
$49.99 Fleece Jacket,  
$15.99 Bolt T-Shirt,
$9.99 Bike Light,
$29.99 Backpack,
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-008: Add one product to the cart
- **Requirement:** REQ-06, REQ-07 | **Priority:** High
- **Preconditions:** logged in as `standard_user`, cart empty
- **Steps:**
  1. Click **Add to cart** on the first product.
- **Expected result:** the cart icon shows `1` and the button on that product changes to **Remove**.
- **Actual result:** The cart icon shows "1" and the button on that product changes to Remove.
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-009: Remove a product from the product list
- **Requirement:** REQ-06, REQ-07 | **Priority:** Medium
- **Preconditions:** TC-008 done, one item in the cart
- **Steps:**
  1. Click **Remove** on that product.
- **Expected result:** the cart badge disappears and the button changes back to **Add to cart**.
- **Actual result:** The cart icon disappears the "1" and the button on the product, goes back to " add to cart ".
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

---

## Cart and checkout

### TC-010: Cart shows the right items
- **Requirement:** REQ-07 | **Priority:** High
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Add two different products. Write down their names and prices.
  2. Open the cart.
- **Expected result:** the cart lists exactly those two products, with the same names and prices, quantity 1 each.
- **Actual result:** Two different products were added to cart ( Onesie - $7.99 & Bolt T-Shirt - $15.99 ).
The cart lists exactly those two products, with the same names and prices, quantity 1 each.
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-011: Complete a purchase with valid data (happy path)
- **Requirement:** REQ-08 | **Priority:** High | **Technique:** equivalence partitioning (valid partition)
- **Preconditions:** logged in, at least one item in the cart
- **Test data:** first name `Test`, last name `User`, postal code `1000-001`
- **Steps:**
  1. Open the cart and
  2. Click **Checkout**.
  3. Fill in the three fields: First Name; Last Name and Zip/postal Code.
  4. Click **Continue**.
  5. Click **Finish**.
- **Expected result:** a confirmation page thanks the user for the order.
- **Actual result:** The user was redirected to a new page with the following message " Thank you for your order!
Your order has been dispatched, and will arrive just as fast as the pony can get there!"
- **Status:** Pass | **Date:** November 8, 2026 and November 22, 2026  | **Env:** E2
- **Evidence:** [TC11-confirmation page](https://github.com/user-attachments/assets/3ab8cb00-6677-4378-8816-c3ac4c53301c)

### TC-012: Checkout with an empty first name
- **Requirement:** REQ-08 | **Priority:** Medium | **Technique:** equivalence partitioning (invalid partition)
- **Preconditions:** logged in, one item in the cart, checkout form open
- **Test data:** first name empty, last name `User`, postal code `1000-001`
- **Steps:**
  1. Fill in the fields: Last Name and Zip/Postal Code.
  2. Click **Continue**.
- **Expected result:** the user stays on the form and sees an error saying the first name is required.
- **Actual result:** The user stays on the form and sees an error saying " Error: First Name is required".
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2
- **Note:** repeat for an empty last name (TC-012b) and an empty postal code (TC-012c).

### TC-012b: Checkout with an empty last name
- **Requirement:** REQ-08 | **Priority:** Medium | **Technique:** equivalence partitioning (invalid partition)
- **Preconditions:** logged in, one item in the cart, checkout form open
- **Test data:** first name 'Test', last name empty, postal code `1000-001`
- **Steps:**
  1. Fill in the fields: First Name and Zip/Postal Code.
  2. Click **Continue**.
- **Expected result:** the user stays on the form and sees an error saying the last name is required.
- **Actual result:** The user stays on the form and sees an error saying " Error: Last Name is required".
- **Status:** Pass | **Date:** November 8, 2026 | **Env:** E2

### TC-012c: Checkout with an empty postal code
- **Requirement:** REQ-08 | **Priority:** Medium | **Technique:** equivalence partitioning (invalid partition)
- **Preconditions:** logged in, one item in the cart, checkout form open
- **Test data:** first name 'Test', last name 'User', postal code empty
- **Steps:**
  1. Fill in the fields: First Name and Last Name.
  2. Click **Continue**.
- **Expected result:** the user stays on the form and sees an error saying the postal code is required.
- **Actual result:** The user stays on the form and sees an error saying " Error: Postal code is required".
- **Status:** Pass | **Date:** 08/11/2026 | **Env:** E2

### TC-013: Order total equals item total plus tax
- **Requirement:** REQ-09 | **Priority:** High
- **Preconditions:** logged in, two products in the cart, checkout form filled in, on the overview page
- **Steps:**
  1. Write down the **Item total**, **Tax** and **Total** shown.
  2. Calculate Item total + Tax by hand.
- **Expected result:** the calculated sum equals the Total shown, to the cent.
- **Actual result:** Item total = 79,98 | Tax = 6,4 | Total shown = 86,38 | My sum = 86,38
  Products chose: $29.99 Backpack and $49.99 Fleece Jacket  
- **Status:** Pass | **Date:** November 8, 2026 and November 22, 2026 | **Env:** E2
- **Evidence:** [TC13-products sum](https://github.com/user-attachments/assets/a90f688c-3dd6-4999-86b6-88eef77f331a)
  
### TC-014: Checkout with an empty cart (boundary: 0 items)
- **Requirement:** REQ-10 | **Priority:** High | **Technique:** boundary value analysis (lower boundary, invalid)
- **Preconditions:** logged in, cart empty
- **Steps:**
  1. Open the cart.
  2. Click **Checkout**.
- **Expected result:** the user cannot proceed to checkout, or sees a message that the cart is empty.
- **Actual result:** The user was redirected to a new page " Checkout: Your Information ".
- **Status:** Fail | **Date:** November 8, 2026 and November 22, 2026 | **Env:** E2
- **Note:** if the site lets you continue, decide: is this a defect against REQ-10 or is my assumption too strict? Write down your reasoning either way.
It is describe on REQ-10 that "A user cannot check out with an empty cart." and in this test case, the cart with 0 products, the user was redirected to a new page
for fill in his information.
- **Evidence:** [TC14-empty cart](https://github.com/user-attachments/assets/a6c91c90-d2ab-47b0-9914-bb2f07eb367b) ;
  [TC14-checkout empty cart](https://github.com/user-attachments/assets/6d1dab55-f9f9-4035-b303-607b4496d89b)

### TC-015: Checkout with all available products (boundary: maximum items)
- **Requirement:** REQ-06, REQ-09 | **Priority:** Medium | **Technique:** boundary value analysis (upper boundary, valid)
- **Preconditions:** logged in, cart empty
- **Steps:**
  1. Add all 6 products.
  2. Check the cart badge, then open the cart.
  3. Complete checkout with valid data.
  4. On the overview, verify the total as in TC-013.
- **Expected result:** badge shows `6`, cart lists 6 items, total is correct, order completes.
- **Actual result:** Badge shows 6 items, cart lists 6 items, total is accordingly.
- Item total = 129,94 | Tax = 10,4 | Total shown = 140,34 | My sum = 140,34
- **Status:** Pass | **Date:** November 22, 2026 | **Env:** E2
- **Evidence:** [TC15-login empty cart](https://github.com/user-attachments/assets/b3362775-5cb8-49f2-b3a5-8d6f7c7173c7)
  [TC15-badge shows 6](https://github.com/user-attachments/assets/263b7e98-3515-4293-9056-1fbf9d9fa343) ;
  [TC15-cart lists 6](https://github.com/user-attachments/assets/1830cc9a-2d65-4b7f-b7e4-fb9885c5ab40) ;
  [TC15-my sum](https://github.com/user-attachments/assets/5b733689-f8fc-4db2-838b-718cbcb18c9a)

---

## Logout

### TC-016: Logout and the back button
- **Requirement:** REQ-11 | **Priority:** High | **Technique:** experience-based
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Open the menu and click **Logout**.
  2. Click the browser **Back** button.
- **Expected result:** the user lands on the login page after logout, and Back does not show the product list.
- **Actual result:** After select Logout button, the user was redirected to Login page and selecting back button in the browser does not show the product list again,
actually shows the following message "Epic sadface: You can only access '/inventory.html' when you are logged in."
- **Status:** Pass | **Date:** November 22, 2026 | **Env:** E2
-  **Evidence:** [TC16-logout and backbutton](https://github.com/user-attachments/assets/b6a6aa70-c62d-4c50-a0af-2aa737072193)

---

## Compatibility

### TC-017: Repeat the key flow in other environments
- **Priority:** Medium
- **Steps:** run TC-001, TC-008, TC-011 and TC-016 in E1 from the test plan.
- **Expected result:** same results as in E2.
- **Actual result:**
  **TC-001: Login with valid credentials**
- **Expected result:** the product list opens and shows 6 products.
- **Actual result:** We were able to login and see 6 products.
- **Status:** Pass | **Date:** November 22, 2026 | **Env:** E1
  

  **TC-008: Add one product to the cart**
- **Expected result:** the cart icon shows `1` and the button on that product changes to **Remove**.
- **Actual result:** The cart icon shows "1" and the button on that product changes to Remove.
- **Status:** Pass | **Date:** November 22, 2026 | **Env:** E1
  

  **TC-011: Complete a purchase with valid data (happy path)**
- **Expected result:** a confirmation page thanks the user for the order.
- **Actual result:** The user was redirected to a new page with the following message " Thank you for your order!
Your order has been dispatched, and will arrive just as fast as the pony can get there!"
- **Status:** Pass | **Date:** November 22, 2026 | **Env:** E1
  

  **TC-016: Logout and the back button**
- **Expected result:** the user lands on the login page after logout, and Back does not show the product list.
- **Actual result:** After select Logout button, the user was redirected to Login page and selecting back button in the browser does not show the product list again,actually shows the following message "Epic sadface: You can only access '/inventory.html' when you are logged in."
- **Status:** Pass | **Date:** November 22, 2026 | **Env:** E1

---

## Exploratory testing

### EXP-001: Charter, "problem_user" versus "standard_user"
- **Mission:** explore the product list, product pages, cart and checkout as `problem_user` and compare with `standard_user`, to find behaviour that looks wrong.
- **Time box:** 30 minutes
- **Notes to take while exploring:**
- **Product Page**
1. After logging in with the user "problem_user" and being redirected to the main "Products" page, the expected result would be to be able to see the available products with their respective images. For example, the Sauce Labs Bolt T-Shirt item should show an image of a shirt.
However, it is possible to see that the product images do not match the actual products. An image of a dog appears on all products.
2. Selected the filter button.
Users should be able to sort products by price or name ( ascending and descending ) at the first try.
However, the filter button is not working correctly, I have tested it three times, in both environments E1 and E2, test failed twice and passed once.
Selecting the filter button the available sorting options are displayed. Then, selecting any of them does not apply the chosen filter or change the product order. As a result, users are unable to sort products as expected.
3. Clicking at the " Add to cart " button, not every item is selected.
User should be able to add any item to the cart at the product page.

**Cart**
1. It only show the three items that button "" Add to cart " allowed.

**Checkout**
1. After selecting Checkout button, user are redirected to "Checkout: Your information" page and be able to fill in all information requested, as such:
First Name, Last Name and Zip/Postal Code.
However, it allows the user to fill in the First Name field but when the user goes to fill in the Last Name field, it is redirected to the First Name field,
not allowing to complete all others fields.

- **Output:** a short list of observations, and one bug report per distinct defect in `03-bug-reports/`.
- **Session notes:** The exploratory test was performed in the E1 environment.
