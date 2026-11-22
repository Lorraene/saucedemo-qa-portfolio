# BUG-TC14: User was redirected to checkout with an empty cart


| Field | Value |
|---|---|
| **ID** | BUG-001 |
| **Status** | Open |
| **Reported on** | 22/11/2026 |
| **Related test case** | TC14 |
| **Related requirement** | REQ-10 |
| **Severity** | High: User was redirected to Checkout: Your Information page and Checkout: Overview page and was able to complete the order without items.|
| **Priority** | Medium: It does not affects mostly users and doesn't block real orders. |
| **Environment** | Safari version 27.0.1, macOS Golden Gate 27.0.1, MacBook Neo, desktop (full browser window) |
| **Test account** | Username: standard_user & Password: secret_sauce|

## Preconditions
Logged in.

## Steps to reproduce
1. Without add any product, select cart button. 
2. Click in Checkout button.


## Expected result
REQ-10 A user cannot check out with an empty cart.
It should display a message stating that the cart is empty.

## Actual result
The user was redirected to a new page " Checkout: Your Information ".

## Evidence
<img width="513" height="283" alt="TC14-empty cart" src="https://github.com/user-attachments/assets/367763c2-8e4a-4cbd-aeb0-c8524f5ac317" />

<img width="513" height="283" alt="TC14-chekout empty cart" src="https://github.com/user-attachments/assets/bd393d12-7ae1-48ba-8f25-78ec20792b9f" />



## Reproducibility
Twice

## Notes
N/A

---

### Severity guide
- **Medium:** a feature misbehaves but there is a workaround.
