# 🛍️ Project: Swag Labs E-commerce Functional Testing

![Status](https://img.shields.io/badge/Status-Completed-success)
![Role](https://img.shields.io/badge/Role-Manual%20Tester-blue)
![Tools](https://img.shields.io/badge/Tools-Excel%20%7C%20SQL%20%7C%20Chrome%20DevTools-orange)

## 1. Introduction
This project demonstrates my manual testing skills on **Swag Labs** (SauceDemo), an e-commerce website designed for testing practice.
The goal is to verify the functionality of the purchasing flow, identify bugs, and ensure a seamless user experience.

* **Website URL:** [https://www.saucedemo.com/](https://www.saucedemo.com/)
* **Tester:** Luong Manh Hung
* **Testing Period:** December 2025

## 2. Test Scope & Strategy
I focused on Black-box testing for the following critical modules:

* ✅ **Authentication:** Login (Standard user, Locked-out user), Logout.
* ✅ **Inventory:** Product display, Sorting (Price Low-High), Product details.
* ✅ **Cart Management:** Add to cart, Remove from cart, Cart badge verification.
* ✅ **Checkout Process:** Information entry, Validation (Empty fields), Order completion.

## 3. Test Artifacts (Downloadable)
Here are the detailed documents created during the testing process:

| Document | Description | Format |
| :--- | :--- | :--- |
| **[📂 Test Cases](./TestCases_SwagLabs.xlsx)** | Contains **9+ Test Cases** covering Happy Path and Negative Scenarios. | Excel |
| **[🐞 Bug Report](./BugReport_SwagLabs.xlsx)** | Detailed bug report for the "Product Image" issue found on `problem_user`. | Excel |
| **[📜 SQL Verification](./DB_Scripts.sql)** | Simulated SQL queries designed to verify data integrity in the backend. | SQL File |

*(Note: Please click the links above to view the files)*

## 4. Execution Summary
* **Total Test Cases:** 9
* **Passed:** 8
* **Failed:** 1 (Logged in Bug Report)

### 🚨 Key Bug Found:
* **Bug Title:** Product images fail to load on Inventory Page.
* **Severity:** Medium.
* **Description:** When logging in as `problem_user`, all product images are replaced with a "broken dog" image.
* **Evidence:**
    ![Bug Screenshot](./bug_screenshot.png)
    *(Please upload your screenshot to the repo and ensure the name matches)*

## 5. Backend Verification Strategy (SQL)
Although I do not have direct access to the Swag Labs database, I designed the following SQL queries to verify data logic if access were available:

```sql
-- 1. Verify User Creation
SELECT * FROM Users WHERE username = 'standard_user';

-- 2. Verify Order Details after Checkout
SELECT 
    Orders.Order_ID, 
    Customers.FullName, 
    Products.ProductName, 
    Orders.TotalAmount, 
    Orders.OrderDate
FROM Orders
JOIN Customers ON Orders.CustomerID = Customers.CustomerID
JOIN OrderDetails ON Orders.Order_ID = OrderDetails.Order_ID
## 6. Tools and environment
**OS:** Windows 11
**Browser:** Microsoft Edge
**Test Management:** Microsoft Excel, Word

---
💌 **Contact:**
* Email: luonghung6998@gmail.com
* LinkedIn: [Link LinkedIn của bạn]
JOIN Products ON OrderDetails.Product_ID = Products.Product_ID
WHERE Customers.FullName = 'Hung Luong' 
AND CAST(Orders.OrderDate AS DATE) = CAST(GETDATE() AS DATE);
