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

## QA E-Commerce Testing Portfolio
### About Project

This project is a Quality Assurance testing portfolio for a simulated E-Commerce web application.
The purpose of this project is to demonstrate my skills in manual testing, API testing, database validation, bug reporting, and test documentation.

## Role : Quality Assurance / QA Tester

### Testing Scope

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

### Tools :
- Jira
- Postman
- MySQL
- DBeaver
- Google Sheets
- Git & GitHub
- Chrome DevTools

### Test Environment
Browser: Google Chrome
OS: MacOS
Testing Type: Manual & API Testing

## Project Deliverables

### Test Cases
A collection of test cases covering the main functionality of the e-commerce application.

Total Test Cases: 40

### Bug Reports
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

### API Testing
API testing was performed using Postman.

Tested endpoints include:
- Register
- Login
- Get Products
- Get Product Detail
- Add Product to Cart
- Update Cart
- Delete Cart

### Database Testing
SQL queries were used to validate:

- User data
- Product data
- Cart data
- Order data
- Payment status

### Testing Workflow
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

### Test Result
Metric	Result

```
Total Test Cases	40
- Passed	35
- Failed	5
- Blocked	0
- Pass Rate	87.5%
```

### Conclusion
Based on the test execution results, several functional issues were identified and documented. After the bug fixing process, retesting and regression testing should be performed before the application is released to production.

### Contact

- Name: `Heri Anhari`
- Email: hr.anhari@gmail.com
- LinkedIn: https://www.linkedin.com/in/heri-anhari-1b175bba/
- GitHub: https://github.com/HerryAnhari/

## 01. Test Case — 40 Data
Go to [TestCases](https://github.com/HerryAnhari/sampleportofolioqa/blob/main/TestCases.xlsx) file

## 02. Bug Report
### BUG-001 — Payment Failed Message Not Displayed
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
### BUG-002 — Product Page Not Responsive
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
## 03. Postman Collection
Untuk bagian API, struktur collection-nya bisa seperti ini:
```
E-Commerce API
│
├── Authentication
│   ├── Register
│   └── Login
│
├── Products
│   ├── Get Products
│   └── Get Product Detail
│
├── Cart
│   ├── Add To Cart
│   ├── Update Cart
│   └── Delete Cart
│
└── Order
    ├── Create Order
    └── Get Order
```
Contoh test script Postman:
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time is below 2000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});

pm.test("Response contains token", function () {
    const response = pm.response.json();
    pm.expect(response).to.have.property("token");
});
```

## 04. SQL Database Testing

### Validate User
```
SELECT id, name, email
FROM users
WHERE email = 'testuser@example.com';
```
Tujuan: memastikan data user berhasil tersimpan setelah proses registrasi.

### Validate Product
```
SELECT id, product_name, price, stock
FROM products
WHERE id = 1001;
```
Tujuan: memastikan informasi product pada database sesuai dengan data yang ditampilkan pada aplikasi.

### Validate Cart
```
SELECT user_id, product_id, quantity
FROM cart
WHERE user_id = 101;
```
Tujuan: memastikan product yang ditambahkan ke cart tersimpan dengan user yang benar.

### Validate Order
```
SELECT order_id, user_id, total_amount, status
FROM orders
WHERE user_id = 101
ORDER BY order_id DESC;
```
Tujuan: memastikan order berhasil dibuat setelah checkout.

### Validate Payment
```
SELECT order_id, payment_method, payment_status
FROM payments
WHERE order_id = 5001;
```
Tujuan: memastikan status pembayaran tersimpan dengan benar.

### Validate Order Total
```
SELECT 
    order_id,
    total_amount
FROM orders
WHERE order_id = 5001;
```
Total pada database kemudian dibandingkan dengan total yang ditampilkan pada halaman checkout.

`Note: Query di atas merupakan contoh portfolio. Nama tabel dan kolom harus disesuaikan dengan database aplikasi yang benar-benar digunakan.`

## 05. Final Test Report

### Project
E-Commerce Web Application

### Testing Period
[14-Agustus-2026] – [29-Agustus-2026]

### Testing Scope
Testing dilakukan pada fitur:

- Registration
- Login
- Product
- Shopping Cart
- Checkout
- Payment
- Order History

### Test Execution Summary
```
Result
Total Test Cases	40
Passed	35
Failed	5
Blocked	0
Pass Rate	87.5%
```

### Defect Summary
```
Severity	Total
Critical	0
High	1
Medium	2
Low	2
```

### Overall Result

Testing menemukan beberapa issue pada aplikasi, terutama pada proses payment dan responsive UI.
Issue dengan severity tinggi perlu diperbaiki sebelum production release.
Setelah bug diperbaiki, QA perlu melakukan:

1. Retesting terhadap defect.
2. Regression testing.
3. Smoke testing.
4. Final verification.

### Recommendation

Aplikasi belum direkomendasikan untuk production release sampai seluruh defect dengan severity High diselesaikan dan dilakukan regression testing.
