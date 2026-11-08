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
- **Status:** Pass | **Date:** 08/11/2026 | **Env:** E2

### TC-002: Login with a locked-out user
- **Requirement:** REQ-02 | **Priority:** High | **Technique:** equivalence partitioning (valid username, blocked)
- **Test data:** username `locked_out_user`, valid shared password
- **Steps:** enter both fields, click **Login**.
- **Expected result:** the user stays on the login page and sees an error saying the user has been locked out.
- **Actual result:** The user stays on the login page and sees an error saying the user has been locked out.
- **Status:** Pass

### TC-003: Login with a wrong password
- **Requirement:** REQ-03 | **Priority:** High | **Technique:** equivalence partitioning (invalid partition)
- **Test data:** username `standard_user`, password `wrong_password`
- **Steps:** enter both fields, click **Login**.
- **Expected result:** login is refused with an error saying username and password do not match.
- **Actual result:** Login was refused with an error saying username and password do not match
- **Status:** Pass

### TC-004: Login with an empty username
- **Requirement:** REQ-03 | **Priority:** Medium | **Technique:** equivalence partitioning
- **Test data:** username empty, valid password
- **Steps:** leave username empty, enter the password, click **Login**.
- **Expected result:** error saying the username is required.
- **Actual result:** A message show up saying username is required.
- **Status:** Pass

### TC-005: Login with an empty password
- **Requirement:** REQ-03 | **Priority:** Medium | **Technique:** equivalence partitioning
- **Test data:** username `standard_user`, password empty
- **Steps:** enter the username, leave password empty, click **Login**.
- **Expected result:** error saying the password is required.
- **Actual result:** A message show up saying password is required, "Epic sadface: Password is required".
- **Status:** Pass

### TC-006: Open the product page without logging in
- **Requirement:** REQ-04 | **Priority:** High | **Technique:** experience-based
- **Preconditions:** logged out, no active session
- **Steps:**
  1. Open the product list address directly (`https://www.saucedemo.com/inventory.html`) in a new tab.
- **Expected result:** the site sends the user to the login page and does not show products.
- **Actual result:** The site sends the user to the login page and does not show products, the following message show up " Epic sadface: You can only access '/inventory.html' when you are logged in.".
- **Status:** Pass

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
- **Status:** Pass
- **Note:** repeat for the other three sort options as TC-007b, TC-007c, TC-007d.



### TC-008: Add one product to the cart
- **Requirement:** REQ-06, REQ-07 | **Priority:** High
- **Preconditions:** logged in as `standard_user`, cart empty
- **Steps:**
  1. Click **Add to cart** on the first product.
- **Expected result:** the cart icon shows `1` and the button on that product changes to **Remove**.
- **Actual result:** [fill in]
- **Status:** Not run

### TC-009: Remove a product from the product list
- **Requirement:** REQ-06, REQ-07 | **Priority:** Medium
- **Preconditions:** TC-008 done, one item in the cart
- **Steps:** click **Remove** on that product.
- **Expected result:** the cart badge disappears and the button changes back to **Add to cart**.
- **Actual result:** [fill in]
- **Status:** Not run

---

## Cart and checkout

### TC-010: Cart shows the right items
- **Requirement:** REQ-07 | **Priority:** High
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Add two different products. Write down their names and prices.
  2. Open the cart.
- **Expected result:** the cart lists exactly those two products, with the same names and prices, quantity 1 each.
- **Actual result:** [fill in]
- **Status:** Not run

### TC-011: Complete a purchase with valid data (happy path)
- **Requirement:** REQ-08 | **Priority:** High | **Technique:** equivalence partitioning (valid partition)
- **Preconditions:** logged in, at least one item in the cart
- **Test data:** first name `Test`, last name `User`, postal code `1000-001`
- **Steps:**
  1. Open the cart and click **Checkout**.
  2. Fill in the three fields.
  3. Click **Continue**, then **Finish**.
- **Expected result:** a confirmation page thanks the user for the order.
- **Actual result:** [fill in]
- **Status:** Not run

### TC-012: Checkout with an empty first name
- **Requirement:** REQ-08 | **Priority:** Medium | **Technique:** equivalence partitioning (invalid partition)
- **Preconditions:** logged in, one item in the cart, checkout form open
- **Test data:** first name empty, last name `User`, postal code `1000-001`
- **Steps:** fill in the form, click **Continue**.
- **Expected result:** the user stays on the form and sees an error saying the first name is required.
- **Actual result:** [fill in]
- **Status:** Not run
- **Note:** repeat for an empty last name (TC-012b) and an empty postal code (TC-012c).

### TC-013: Order total equals item total plus tax
- **Requirement:** REQ-09 | **Priority:** High
- **Preconditions:** logged in, two products in the cart, checkout form filled in, on the overview page
- **Steps:**
  1. Write down the **Item total**, **Tax** and **Total** shown.
  2. Calculate Item total + Tax by hand.
- **Expected result:** the calculated sum equals the Total shown, to the cent.
- **Actual result:** Item total = [ ] | Tax = [ ] | Total shown = [ ] | My sum = [ ]
- **Status:** Not run

### TC-014: Checkout with an empty cart (boundary: 0 items)
- **Requirement:** REQ-10 | **Priority:** High | **Technique:** boundary value analysis (lower boundary, invalid)
- **Preconditions:** logged in, cart empty
- **Steps:**
  1. Open the cart.
  2. Click **Checkout**.
- **Expected result:** the user cannot proceed to checkout, or sees a message that the cart is empty.
- **Actual result:** [fill in]
- **Status:** Not run
- **Note:** if the site lets you continue, decide: is this a defect against REQ-10 or is my assumption too strict? Write down your reasoning either way.

### TC-015: Checkout with all available products (boundary: maximum items)
- **Requirement:** REQ-06, REQ-09 | **Priority:** Medium | **Technique:** boundary value analysis (upper boundary, valid)
- **Preconditions:** logged in, cart empty
- **Steps:**
  1. Add all 6 products.
  2. Check the cart badge, then open the cart.
  3. Complete checkout with valid data.
  4. On the overview, verify the total as in TC-013.
- **Expected result:** badge shows `6`, cart lists 6 items, total is correct, order completes.
- **Actual result:** [fill in]
- **Status:** Not run

---

## Logout

### TC-016: Logout and the back button
- **Requirement:** REQ-11 | **Priority:** High | **Technique:** experience-based
- **Preconditions:** logged in as `standard_user`
- **Steps:**
  1. Open the menu and click **Logout**.
  2. Click the browser **Back** button.
- **Expected result:** the user lands on the login page after logout, and Back does not show the product list.
- **Actual result:** [fill in]
- **Status:** Not run

---

## Compatibility

### TC-017: Repeat the key flow in other environments
- **Priority:** Medium
- **Steps:** run TC-001, TC-008, TC-011 and TC-016 in E2 and E3 from the test plan.
- **Expected result:** same results as in E1.
- **Actual result:** [one line per environment]
- **Status:** Not run

---

## Exploratory testing

### EXP-001: Charter, "problem_user" versus "standard_user"
- **Mission:** explore the product list, product pages, cart and checkout as `problem_user` and compare with `standard_user`, to find behaviour that looks wrong.
- **Time box:** 30 minutes
- **Notes to take while exploring:** what you clicked, what you expected, what happened, screenshots.
- **Output:** a short list of observations, and one bug report per distinct defect in `03-bug-reports/`.
- **Session notes:** [fill in]
