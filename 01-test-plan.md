# Test Plan: SauceDemo

**Author:** [Your Name] | **Version:** 0.1 | **Date:** [date]

## 1. Objective

Verify, through manual testing, that the main user journey of SauceDemo (log in, browse products, add to cart, check out, log out) works as a user would reasonably expect, and report any defects found.

## 2. Scope

**In scope**
- Login and logout
- Product list, sorting, adding and removing items
- Cart contents
- Checkout (information form, overview, confirmation)
- Basic compatibility: 2 desktop browsers and 1 mobile viewport

**Out of scope**
- Performance and load testing
- Security testing
- Test automation
- Accessibility audit (only obvious issues will be noted)

## 3. Assumed requirements

SauceDemo has no published requirements. These are the behaviours I assumed, based on common e-commerce practice. Each test case traces back to one of them.

| ID | Assumed requirement |
|---|---|
| REQ-01 | A registered user can log in with valid credentials and lands on the product list. |
| REQ-02 | A locked-out user cannot log in and sees a clear error message. |
| REQ-03 | Invalid or missing credentials are rejected with a clear error message. |
| REQ-04 | Pages that need a login cannot be opened without logging in. |
| REQ-05 | Products can be sorted by name and price, and the order shown matches the option chosen. |
| REQ-06 | The cart badge always shows the number of items in the cart. |
| REQ-07 | Items can be added and removed from the product list and from the cart. |
| REQ-08 | Checkout requires first name, last name and postal code. |
| REQ-09 | The order total equals item total plus tax. |
| REQ-10 | A user cannot check out with an empty cart. |
| REQ-11 | After logout the user cannot reach logged-in pages with the browser back button. |

## 4. Test approach

- **Test design:** equivalence partitioning and boundary value analysis for inputs; exploratory session for the user "problem_user", which is designed for practice and expected to behave differently.
- **Execution:** manual, one session per area. Each test case is executed once per environment listed below.
- **Defect handling:** every failure is checked against the assumed requirement. If the behaviour contradicts a requirement, I raise a bug report; if my assumption looks wrong, I note it and update this plan.

## 5. Test environments

| Env | Browser | Device |
|---|---|---|
| E1 | [Chrome, version] | [Mac, macOS version] |
| E2 | [Safari or Firefox, version] | [Mac, macOS version] |
| E3 | [Chrome in mobile emulation, device name] | Browser dev tools |

## 6. Entry and exit criteria

**Entry:** site reachable, test accounts shown on the login page work, test cases reviewed.
**Exit:** all test cases executed at least once in E1, high-priority cases also in E2 and E3, every failure either reported as a bug or explained.

## 7. Risks and limits

- Only one tester. No independent review of the test cases.
- No requirements document, so some "expected results" are my judgement.
- Demo site may change without notice, which can alter results between runs. Each run records the date.

## 8. Deliverables

Test plan, test cases, execution log, bug reports, evidence screenshots.
