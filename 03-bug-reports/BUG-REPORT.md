# BUG-TC14: User was redirected to checkout with an empty cart.


| Field | Value |
|---|---|
| **ID** | BUG-001 |
| **Status** | Open |
| **Reported on** | November 22, 2026 |
| **Related test case** | TC14 |
| **Related requirement** | REQ-10 |
| **Severity** | High: User was redirected to "Checkout: Your Information" page and "Checkout: Overview" page and was able to complete the order without items.|
| **Priority** | Medium: It does not affects mostly users and doesn't block real orders. |
| **Environment** | Safari version 27.0.1, macOS Golden Gate 27.0.1, MacBook Neo, desktop (full browser window) |
| **Test account** | Username: standard_user & Password: secret_sauce|

## Preconditions
Logged in.

## Steps to reproduce
1. Without adding any product, select cart button. 
2. Click in Checkout button.


## Expected result
REQ-10 A user cannot check out with an empty cart.
It should display a message stating that the cart is empty.

## Actual result
The user was redirected to a new page " Checkout: Your Information " and to "Checkout: Overview" without any product at the cart.

## Evidence
<img width="513" height="283" alt="TC14-empty cart" src="https://github.com/user-attachments/assets/367763c2-8e4a-4cbd-aeb0-c8524f5ac317" />

<img width="513" height="283" alt="TC14-chekout empty cart" src="https://github.com/user-attachments/assets/bd393d12-7ae1-48ba-8f25-78ec20792b9f" />



## Reproducibility
2 out of 2 attempts (Safari)

## Notes
Suggested fix: disable Checkout when the cart is empty.




# BUG-EXP-001: All product images show the same dog photo when logged in as problem_user


| Field | Value |
|---|---|
| **ID** | BUG-002 |
| **Status** | Open |
| **Reported on** | November 22, 2026 |
| **Related test case** | EXP-001 |
| **Related requirement** | Exploratory test |
| **Severity** | Medium: Product images are incorrect (all show a dog photo), so the user cannot identify products visually. Purchasing is still possible and names and prices are correct, so no function is blocked.|
| **Priority** | High: The defect is visible on the main product page to every user affected, hurts trust and conversion, and is likely a simple fix. Suggested for the next release. |
| **Environment** | Google Chrome version 158.0.8127, macOS Golden Gate 27.0.1, MacBook Neo, desktop (full browser window) |
| **Test account** | Username: problem_user & Password: secret_sauce|

## Preconditions
Login page open.

## Steps to reproduce
1. Access the page https://www.saucedemo.com/  
2. Execute login with credentials above.
3. Observe the product images on the Products page.


## Expected result
The user is redirected to the main page, called "Products," and views all items with the correct information and images.

## Actual result
 The product images do not match the actual products. An image of a dog appears on all products.

## Evidence
<img width="1024" height="592" alt="EXP-001 product page" src="https://github.com/user-attachments/assets/c336a139-2387-496d-8549-a3ddbe8b46b8" />


## Reproducibility
Reproduced 3 times: E1 (Chrome 2, macOS) and E2 (Safari 1, macOS)

## Notes
With `standard_user` the same page shows the correct images.
Suggested fix: link each product to its correct image file.



