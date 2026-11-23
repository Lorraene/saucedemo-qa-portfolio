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
Logged in with user standard_user.

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

---
---

# BUG-EXP-001: All product images show the same dog photo when logged in as problem_user


| Field | Value |
|---|---|
| **ID** | BUG-002 |
| **Status** | Open |
| **Reported on** | November 22, 2026 |
| **Related test case** | EXP-001 |
| **Related requirement** | Exploratory test |
| **Severity** | Medium: Product images are incorrect (all show a dog photo), so the user cannot identify products visually.|
| **Priority** | High: The defect is visible on the main product page to every user affected, hurts trust and conversion, and is likely a simple fix. Suggested for the next release. |
| **Environment** | Google Chrome version 158.0.8127, macOS Golden Gate 27.0.1, MacBook Neo, desktop (full browser window) |
| **Test account** | Username: problem_user & Password: secret_sauce|

## Preconditions
Logged in with user problem_user.

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
Reproduced at E1 (Chrome 2, macOS) and E2 (Safari 1, macOS)

## Notes
With `standard_user` the same page shows the correct images.
Suggested fix: link each product to its correct image file.

---

# BUG-EXP-002: Users should be able to sort products by price or name ( ascending and descending ) 


| Field | Value |
|---|---|
| **ID** | BUG-003 |
| **Status** | Open |
| **Reported on** | November 23, 2026 |
| **Related test case** | EXP-002 |
| **Related requirement** | Exploratory test |
| **Severity** | Medium: The filter button doesn't respond as it should, when user select to sort products by name or price. However, the user still can see and select the product. |
| **Priority** | High: The defect is visible on the main product page to every user affected, hurts trust and conversion, and is likely a simple fix. Suggested for the next release. |
| **Environment** | Google Chrome version 158.0.8127, macOS Golden Gate 27.0.1, MacBook Neo, desktop (full browser window) |
| **Test account** | Username: problem_user & Password: secret_sauce|

## Preconditions
Logged in with user problem_user.

## Steps to reproduce
1. Access the page https://www.saucedemo.com/  
2. Execute login with credentials above.
3. Select the filter button.
4. Choose to filter by Price ( Low to High ).

## Expected result
The user must be able to sort the products by Name ( A to Z ) or ( Z to A ) and by Price ( Low to High ) or ( High to Low ).

## Actual result
The filter button displays the options but when selected, doesn't change anything. Doesn't show the order selected.
 
## Evidence
<img width="1002" height="574" alt="image" src="https://github.com/user-attachments/assets/6dfb43c8-ba9e-4535-a283-1cc1ada06bb6" />

## Reproducibility
Reproduced 3 out of 3 attempts

## Notes
With the login `standard_user`, the user are able to sort products.
Suggested to fix: Fix the functionality of the "Filter" button, ensuring that when it is triggered, the selected criteria are processed correctly and the displayed results are updated according to the parameters provided by the user.

---

# BUG-EXP-003: "Add to Cart" Button Fails to Add Selected Products to the Shopping Cart


| Field | Value |
|---|---|
| **ID** | BUG-004 |
| **Status** | Open |
| **Reported on** | November 23, 2026 |
| **Related test case** | EXP-003 |
| **Related requirement** | Exploratory test |
| **Severity** | Critical: The user cannot choose the product of his choice, affecting the user experience and sales. |
| **Priority** | High: It must be fixed with high priority since affects the user shopping leading to leave without any buy and the company's sale.|
| **Environment** | Google Chrome version 158.0.8127, macOS Golden Gate 27.0.1, MacBook Neo, desktop (full browser window) |
| **Test account** | Username: problem_user & Password: secret_sauce|

## Preconditions
Login with user problem_user .

## Steps to reproduce
1. Access the page https://www.saucedemo.com/  
2. Execute login with credentials above.
3. Try to add products to the cart by selecting the button " Add to cart ".

## Expected result
The user must be able to add to the cart any product selected.

## Actual result
The button " add to cart" doesn't work in all products. The button falis in Sauce Labs Bolt T-Shirt, Sauce Labs Fleece Jacket and Test.allTheThings() T-Shirt (Red).
 
## Evidence
<img width="1012" height="559" alt="image" src="https://github.com/user-attachments/assets/4e082b2b-6eff-4e03-91ab-0f44de114398" />

## Reproducibility
Reproduced 3 times: E1 (Chrome 2, macOS).

## Notes
With the login `standard_user`, the user are able to add all products of his choice.
Suggested to fix: Fix the functionality of the "add to cart" button, ensuring that when it is triggered, the selected criteria are processed correctly and all selected products by usar are able to add to cart and cart updated as well.

---

# BUG-EXP-004: At page "Checkout: Your Information" the user is redirected to First Name field when attempting to complete Last Name field.


| Field | Value |
|---|---|
| **ID** | BUG-005 |
| **Status** | Open |
| **Reported on** | November 23, 2026 |
| **Related test case** | EXP-004 |
| **Related requirement** | Exploratory test |
| **Severity** | Critical: User can not fill in all mandatory fields and can not complete the order.|
| **Priority** | High: It must be fixed with high priority since affects directly the buying process and user can not complete the order. |
| **Environment** | Safari version 27.0.1, macOS Golden Gate 27.0.1, MacBook Neo, desktop (full browser window) |
| **Test account** | Username: standard_user & Password: secret_sauce|

## Preconditions
Logged in with user problem_user.
Cart with selected products.

## Steps to reproduce
1. Select "Add to cart" button at any products. 
2. Click in cart button.
3. Click to Checkout.
4. Fill in Fisrt Name field.
5. Try to type at Last Name field.

## Expected result
User must be able to fill in all mandatory informations and complete the order.

## Actual result
 When the user goes to fill in the Last Name field, it is redirected to the First Name field, not allowing to complete all others fields.

## Evidence
<img width="1014" height="574" alt="image" src="https://github.com/user-attachments/assets/cd906116-5b88-404c-aaa0-705a97a16dcd" />

<img width="1024" height="575" alt="image" src="https://github.com/user-attachments/assets/b4221562-8594-41a0-a3f4-36949b35a529" />

## Reproducibility
2 out of 2 attempts (Chrome)
