# Sample Portofolio QA

Ini hanya contoh portofolio, Kalau targetmu melamar sebagai Junior QA/QA Tester, struktur seperti ini sudah jauh lebih kuat daripada sekadar menulis “menguasai Jira, Postman, Selenium” di CV.

## Struktur Repository GitHub

```
qa-ecommerce-portfolio/
│
├── -README.md
│
├── 01-Test-Case/
│   └── Test-Case-Ecommerce.xlsx
│
├── 02-Bug-Report/
│   └── Bug-Report.md
│
├── 03-API-Testing/
│   ├── Ecommerce-API.postman_collection.json
│   └── API-Test-Report.md
│
├── 04-Database-Testing/
│   ├── database-query.sql
│   └── Database-Test-Report.md
│
├── 05-Test-Report/
│   └── Final-Test-Report.md
│
└── 06-Screenshots/
    ├── login.png
    ├── product.png
    ├── checkout.png
    └── jira-bug.png
```

# README.md

# QA E-Commerce Testing Portfolio
## About Project

This project is a Quality Assurance testing portfolio for a simulated E-Commerce web application.
The purpose of this project is to demonstrate my skills in manual testing, API testing, database validation, bug reporting, and test documentation.

## Role : Quality Assurance / QA Tester

## Testing Scope

The following features were tested:
- User Registration
- User Login
- Product Search
- Product Detail
- Add to Cart
- Update Cart
- Remove from Cart
- Checkout
- Payment
- Order History
- Logout
- Testing Types
- Functional Testing
- Smoke Testing
- Regression Testing
- Integration Testing
- Positive Testing
- Negative Testing
- Exploratory Testing
- API Testing
- Database Testing

## Tools :
- Jira
- Postman
- MySQL
- DBeaver
- Google Sheets
- Git & GitHub
- Chrome DevTools

## Test Environment
Browser: Google Chrome
OS: MacOS
Testing Type: Manual & API Testing

# Project Deliverables

## Test Cases
A collection of test cases covering the main functionality of the e-commerce application.

Total Test Cases: 40

## Bug Reports
Documented bugs with:

- Bug ID
- Title
- Severity
- Priority
- Environment
- Steps to reproduce
- Expected result
- Actual result
- Evidence
- Bug status

## API Testing
API testing was performed using Postman.

Tested endpoints include:
- Register
- Login
- Get Products
- Get Product Detail
- Add Product to Cart
- Update Cart
- Delete Cart

## Database Testing
SQL queries were used to validate:

- User data
- Product data
- Cart data
- Order data
- Payment status

## Testing Workflow
```
Requirement Analysis
        ↓
Test Scenario
        ↓
Test Case Creation
        ↓
Test Execution
        ↓
Bug Reporting
        ↓
Bug Fix
        ↓
Retesting
        ↓
Regression Testing
        ↓
Final Test Report
```

## Test Result
Metric	Result

```
Total Test Cases	40
- Passed	35
- Failed	5
- Blocked	0
- Pass Rate	87.5%
```

## Conclusion
Based on the test execution results, several functional issues were identified and documented. After the bug fixing process, retesting and regression testing should be performed before the application is released to production.

## Contact

- Name: `Heri Anhari`
- Email: hr.anhari@gmail.com
- LinkedIn: https://www.linkedin.com/in/heri-anhari-1b175bba/
- GitHub: https://github.com/HerryAnhari/

# 2. Test Case — 40 Data
Go to TestCases.xlsx file

# 3. Bug Report
## BUG-001 — Payment Failed Message Not Displayed
```
Module: Payment
Severity: High
Priority: High
Status: Open

- Environment
Browser: Google Chrome
OS: MacOS
Environment: Staging

- Preconditions
User sudah login dan memiliki product di shopping cart.

- Steps to Reproduce
Login ke aplikasi.
Tambahkan product ke cart.
Masuk ke halaman checkout.
Pilih payment method.
Masukkan payment data yang invalid.
Klik Pay Now.

- Expected Result
Sistem menampilkan pesan bahwa pembayaran gagal dan memberikan informasi kepada user untuk mencoba kembali.

- Actual Result
Payment gagal tetapi tidak ada pesan error yang ditampilkan kepada user.

- Severity
High — kegagalan pembayaran merupakan fungsi utama dan dapat menyebabkan user tidak mengetahui status transaksinya.

- Recommendation
Tambahkan error handling dan pesan yang informatif ketika payment gagal.
```
## BUG-002 — Product Page Not Responsive
```
Module: Product
Severity: Medium
Priority: Medium
Status: Open

- Steps to Reproduce
Buka product page.
Gunakan browser dengan mobile resolution.
Scroll halaman product.

Expected Result
Seluruh komponen product dapat ditampilkan dengan baik pada layar mobile.

Actual Result
Beberapa bagian halaman keluar dari area layar dan membutuhkan horizontal scrolling.

Recommendation
Review responsive CSS pada product page dan lakukan testing kembali pada beberapa mobile resolution.
```
# 4. SQL Database Testing

## 4a. Validate User
```
SELECT id, name, email
FROM users
WHERE email = 'testuser@example.com';
```
Tujuan: memastikan data user berhasil tersimpan setelah proses registrasi.

## 4b. Validate Product
```
SELECT id, product_name, price, stock
FROM products
WHERE id = 1001;
```
Tujuan: memastikan informasi product pada database sesuai dengan data yang ditampilkan pada aplikasi.

## 4c. Validate Cart
```
SELECT user_id, product_id, quantity
FROM cart
WHERE user_id = 101;
```
Tujuan: memastikan product yang ditambahkan ke cart tersimpan dengan user yang benar.

## 4d. Validate Order
```
SELECT order_id, user_id, total_amount, status
FROM orders
WHERE user_id = 101
ORDER BY order_id DESC;
```
Tujuan: memastikan order berhasil dibuat setelah checkout.

## 4e. Validate Payment
```
SELECT order_id, payment_method, payment_status
FROM payments
WHERE order_id = 5001;
```
Tujuan: memastikan status pembayaran tersimpan dengan benar.

## 4f. Validate Order Total
```
SELECT 
    order_id,
    total_amount
FROM orders
WHERE order_id = 5001;
```
Total pada database kemudian dibandingkan dengan total yang ditampilkan pada halaman checkout.

`Note: Query di atas merupakan contoh portfolio. Nama tabel dan kolom harus disesuaikan dengan database aplikasi yang benar-benar digunakan.`

