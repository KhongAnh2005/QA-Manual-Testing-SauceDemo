# Epics Specification: SauceDemo E-Commerce Application

Document ID: ED-SAUCEDEMO-01  
Target Application: SauceDemo (https://www.saucedemo.com/)  
Author: QA - Khổng Đức Anh  
Date: 12/09/2026  
Total Epics: 8 Epics  
Status: Approved  

---

## Mục Lục

- [1. Danh Sách 8 Epics Chính](#1-danh-sach-8-epics-chinh)
- [2. Chi Tiết Các Epics](#2-chi-tiet-cac-epics)

---

<a id="1-danh-sach-8-epics-chinh"></a>
## 1. Danh Sách 8 Epics Chính

| Epic ID | Epic Name | Scope Summary | Priority | Status |
|:---|:---|:---|:---:|:---:|
| [EPIC-01](#epic-01) | Authentication & Session Management | Quản lý xác thực người dùng, đăng nhập, xử lý tài khoản bị khóa, đăng xuất và kiểm soát quyền truy cập phiên làm việc. | High | Approved |
| [EPIC-02](#epic-02) | Product Catalog & Inventory Browsing | Hiển thị danh mục sản phẩm, hình ảnh, thông tin mô tả, xem trang chi tiết sản phẩm và các bộ lọc sắp xếp hàng hóa. | High | Approved |
| [EPIC-03](#epic-03) | Shopping Cart Management | Thêm/xóa sản phẩm khỏi giỏ hàng, đồng bộ huy hiệu số lượng (Badge Counter), trang xem giỏ hàng và duy trì trạng thái dữ liệu. | High | Approved |
| [EPIC-04](#epic-04) | Checkout Workflow | Quy trình thanh toán 3 bước: Xác thực thông tin khách hàng (Step 1), Tổng quan đơn hàng & tính toán tiền/thuế (Step 2), và Xác nhận hoàn tất đơn hàng (Step 3). | High | Approved |
| [EPIC-05](#epic-05) | Sidebar Navigation & App State | Menu trượt điều hướng (All Items, liên kết About, Logout, Reset App State) và chức năng làm mới trạng thái ứng dụng. | Medium | Approved |
| [EPIC-06](#epic-06) | End-to-End E-Commerce Workflow | Luồng trải nghiệm mua sắm tích hợp xuyên suốt từ đăng nhập, sắp xếp, chọn sản phẩm, giỏ hàng, thanh toán đến hoàn tất đơn hàng và đăng xuất. | High | Approved |
| [EPIC-07](#epic-07) | Backend Services & Database Data Integrity | Kiểm thử các giao thức hợp đồng giao tiếp RESTful API và tính toàn vẹn của cơ sở dữ liệu quan hệ (Database/SQL) mô phỏng trong hệ sinh thái thương mại điện tử. | Medium | Approved |
| [EPIC-08](#epic-08) | Non-Functional Quality Attributes & Security Standards | Đánh giá các tiêu chuẩn chất lượng phi chức năng bao gồm: Bảo mật phiên & đầu vào, Hiệu năng đáp ứng (SLA), Trải nghiệm người dùng (Usability), Khả năng tiếp cận (Accessibility - WCAG 2.1) và Tương thích đa thiết bị/đa trình duyệt. | Medium | Approved |

---

<a id="2-chi-tiet-cac-epics"></a>
## 2. Chi Tiết Các Epics

<a id="epic-01"></a>

### EPIC-01: Authentication & Session Management

| Field | Value |
|:---|:---|
| Epic ID | EPIC-01 |
| Epic Name | Authentication & Session Management |
| Priority | High |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Quản lý xác thực người dùng, đăng nhập, xử lý tài khoản bị khóa, đăng xuất và kiểm soát quyền truy cập phiên làm việc.

Xem chi tiết: [EPIC-01.md](EPIC-01.md)


---

<a id="epic-02"></a>

### EPIC-02: Product Catalog & Inventory Browsing

| Field | Value |
|:---|:---|
| Epic ID | EPIC-02 |
| Epic Name | Product Catalog & Inventory Browsing |
| Priority | High |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Hiển thị danh mục sản phẩm, hình ảnh, thông tin mô tả, xem trang chi tiết sản phẩm và các bộ lọc sắp xếp hàng hóa.

Xem chi tiết: [EPIC-02.md](EPIC-02.md)


---

<a id="epic-03"></a>

### EPIC-03: Shopping Cart Management

| Field | Value |
|:---|:---|
| Epic ID | EPIC-03 |
| Epic Name | Shopping Cart Management |
| Priority | High |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Thêm/xóa sản phẩm khỏi giỏ hàng, đồng bộ huy hiệu số lượng (Badge Counter), trang xem giỏ hàng và duy trì trạng thái dữ liệu.

Xem chi tiết: [EPIC-03.md](EPIC-03.md)


---

<a id="epic-04"></a>

### EPIC-04: Checkout Workflow

| Field | Value |
|:---|:---|
| Epic ID | EPIC-04 |
| Epic Name | Checkout Workflow |
| Priority | High |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Quy trình thanh toán 3 bước: Xác thực thông tin khách hàng (Step 1), Tổng quan đơn hàng & tính toán tiền/thuế (Step 2), và Xác nhận hoàn tất đơn hàng (Step 3).

Xem chi tiết: [EPIC-04.md](EPIC-04.md)


---

<a id="epic-05"></a>

### EPIC-05: Sidebar Navigation & App State

| Field | Value |
|:---|:---|
| Epic ID | EPIC-05 |
| Epic Name | Sidebar Navigation & App State |
| Priority | Medium |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Menu trượt điều hướng (All Items, liên kết About, Logout, Reset App State) và chức năng làm mới trạng thái ứng dụng.

Xem chi tiết: [EPIC-05.md](EPIC-05.md)


---

<a id="epic-06"></a>

### EPIC-06: End-to-End E-Commerce Workflow

| Field | Value |
|:---|:---|
| Epic ID | EPIC-06 |
| Epic Name | End-to-End E-Commerce Workflow |
| Priority | High |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Luồng trải nghiệm mua sắm tích hợp xuyên suốt từ đăng nhập, sắp xếp, chọn sản phẩm, giỏ hàng, thanh toán đến hoàn tất đơn hàng và đăng xuất.

Xem chi tiết: [EPIC-06.md](EPIC-06.md)


---

<a id="epic-07"></a>

### EPIC-07: Backend Services & Database Data Integrity

| Field | Value |
|:---|:---|
| Epic ID | EPIC-07 |
| Epic Name | Backend Services & Database Data Integrity |
| Priority | Medium |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Kiểm thử các giao thức hợp đồng giao tiếp RESTful API và tính toàn vẹn của cơ sở dữ liệu quan hệ (Database/SQL) mô phỏng trong hệ sinh thái thương mại điện tử.

Xem chi tiết: [EPIC-07.md](EPIC-07.md)


---

<a id="epic-08"></a>

### EPIC-08: Non-Functional Quality Attributes & Security Standards

| Field | Value |
|:---|:---|
| Epic ID | EPIC-08 |
| Epic Name | Non-Functional Quality Attributes & Security Standards |
| Priority | Medium |
| Assignee / Reporter | QA - Khổng Đức Anh |
| Status | Approved |

**Mô Tả Nghiệp Vụ:**

Đánh giá các tiêu chuẩn chất lượng phi chức năng bao gồm: Bảo mật phiên & đầu vào, Hiệu năng đáp ứng (SLA), Trải nghiệm người dùng (Usability), Khả năng tiếp cận (Accessibility - WCAG 2.1) và Tương thích đa thiết bị/đa trình duyệt.

Xem chi tiết: [EPIC-08.md](EPIC-08.md)


---
