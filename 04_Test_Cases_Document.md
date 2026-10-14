# Test Cases Document: SauceDemo E-Commerce Web Application

**Target Application:** SauceDemo ([https://www.saucedemo.com/](https://www.saucedemo.com/))  
**Standard Compliance:** Zephyr Test Management Standard & Anatomy of a Professional Test Case  
**Author / Owner:** QA - Khổng Đức Anh  
**Total Test Cases:** 71 Test Cases (50 Functional, 5 API, 5 Database SQL, 11 Non-Functional)  
**Status:** Approved (Ready for Test Execution)  

---

## Table of Contents

- [1. Zephyr Compatible Structure Overview](#tc-section-1)
- [2. Test Cases Master Index Table](#tc-section-2)
- [3. Detailed Test Cases](#tc-section-3)
  - [01_Functional_Testing / 01_Authentication (TC-01 to TC-09)](#tc-folder-01_functional_testing-01_authentication)
  - [01_Functional_Testing / 02_Product_Catalog (TC-10 to TC-18)](#tc-folder-01_functional_testing-02_product_catalog)
  - [01_Functional_Testing / 03_Shopping_Cart (TC-19 to TC-29)](#tc-folder-01_functional_testing-03_shopping_cart)
  - [01_Functional_Testing / 04_Checkout (TC-30 to TC-44)](#tc-folder-01_functional_testing-04_checkout)
  - [01_Functional_Testing / 05_Sidebar_Navigation (TC-45 to TC-49)](#tc-folder-01_functional_testing-05_sidebar_navigation)
  - [01_Functional_Testing / 06_End_to_End (TC-50)](#tc-folder-01_functional_testing-06_end_to_end)
  - [02_API_Testing (TC-51 to TC-55)](#tc-folder-02_api_testing)
  - [03_Database_SQL_Testing (TC-56 to TC-60)](#tc-folder-03_database_sql_testing)
  - [04_Non_Functional_Testing / Performance_Testing (TC-61 to TC-62)](#tc-folder-04_non_functional_testing-performance_testing)
  - [04_Non_Functional_Testing / Security_Testing (TC-63 to TC-65)](#tc-folder-04_non_functional_testing-security_testing)
  - [04_Non_Functional_Testing / Accessibility_Testing (TC-66 to TC-67)](#tc-folder-04_non_functional_testing-accessibility_testing)
  - [04_Non_Functional_Testing / Usability_Testing (TC-68 to TC-69)](#tc-folder-04_non_functional_testing-usability_testing)
  - [04_Non_Functional_Testing / Compatibility_Testing (TC-70 to TC-71)](#tc-folder-04_non_functional_testing-compatibility_testing)

---

<a id="tc-section-1"></a>
## 1. Zephyr Compatible Structure Overview

Bộ Test Cases này được xây dựng tương thích hoàn toàn với các trường dữ liệu trên **Zephyr Scale / Zephyr Squad** trên Jira:
- **Name:** Tiêu đề ca kiểm thử rõ ràng, súc tích.
- **Objective:** Mục tiêu chi tiết của ca kiểm thử.
- **Precondition:** Điều kiện tiên quyết trước khi thực thi.
- **Folder:** Thư mục lưu trữ phân cấp trong Zephyr Test Library (`01_Functional_Testing`, `02_API_Testing`, `03_Database_SQL_Testing`, `04_Non_Functional_Testing/Subfolders`).
- **Component:** Phân vùng chức năng của hệ thống.
- **Status:** `Approved` (Trạng thái ca kiểm thử đã được duyệt chuẩn chỉ trên Zephyr).
- **Priority / Severity:** Đánh giá mức độ ưu tiên xử lý và mức độ nghiêm trọng kỹ thuật.
- **Owner:** QA - Khổng Đức Anh.
- **UserStoryID:** Mã định danh User Story chuẩn (`US-01` đến `US-17`) dùng để tạo liên kết truy xuất trực tiếp đến work item - story trên Jira.
- **TestScenarioID:** Mã truy xuất về Kịch bản kiểm thử tương ứng (`TS-01` đến `TS-34`).
- **Test Steps:** Các bước thực hiện cụ thể theo số thứ tự (Plain Text).
- **Test Data:** Dữ liệu nhập vào ô hoặc giá trị cần thao tác.
- **Expected Result:** Kết quả kỳ vọng chi tiết và có thể đo lường cho toàn bộ ca kiểm thử.
- **Actual Result / Execution Info:** Điền '-' để sẵn sàng cập nhật sau khi chạy thực tế ở Phase 2.

<a id="tc-section-2"></a>
## 2. Test Cases Master Index Table

| **TC ID** | **Folder** | **Name** | **Type** | **Priority** | **Severity** | **UserStoryID** | **TestScenarioID** | **Status** |
|:---|:---|:---|:---|:---:|:---:|:---:|:---:|:---:|
| **TC-01** | 01_Functional_Testing/01_Authentication | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ | Functional / Smoke | High | Critical | US-01 | TS-01 | Approved |
| **TC-02** | 01_Functional_Testing/01_Authentication | Kiểm tra thông báo lỗi khi để trống cả Username và Password | Negative / Validation | High | Medium | US-02 | TS-02 | Approved |
| **TC-03** | 01_Functional_Testing/01_Authentication | Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password | Negative / Validation | High | Medium | US-02 | TS-02 | Approved |
| **TC-04** | 01_Functional_Testing/01_Authentication | Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password | Negative / Validation | Medium | Medium | US-02 | TS-02 | Approved |
| **TC-05** | 01_Functional_Testing/01_Authentication | Kiểm tra từ chối đăng nhập khi nhập sai thông tin tài khoản hoặc mật khẩu | Negative / Security | High | High | US-02 | TS-03 | Approved |
| **TC-06** | 01_Functional_Testing/01_Authentication | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) | Negative / Security | High | High | US-02 | TS-04 | Approved |
| **TC-07** | 01_Functional_Testing/01_Authentication | Kiểm tra thao tác đóng thông báo lỗi đăng nhập bằng nút 'X' | Functional / UI Interaction | Low | Low | US-02 | TS-02 | Approved |
| **TC-08** | 01_Functional_Testing/01_Authentication | Kiểm tra đăng xuất tài khoản an toàn thông qua menu điều hướng Sidebar | Functional / Security | High | Critical | US-03 | TS-05 | Approved |
| **TC-09** | 01_Functional_Testing/01_Authentication | Kiểm tra chặn truy cập trực tiếp URL trang nội bộ khi chưa đăng nhập | Security / Authorization | High | Critical | US-03 | TS-05 | Approved |
| **TC-10** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và các thông tin chi tiết | Functional / UI Verification | High | High | US-04 | TS-06 | Approved |
| **TC-11** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra xem trang chi tiết sản phẩm khi nhấp vào tên hoặc ảnh sản phẩm | Functional / Navigation | Medium | Medium | US-04 | TS-07 | Approved |
| **TC-12** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra nút 'Back to products' quay lại trang danh mục từ trang chi tiết | Functional / Navigation | Medium | Low | US-04 | TS-07 | Approved |
| **TC-13** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra sắp xếp danh mục sản phẩm theo tên từ A đến Z | Functional / Sorting | Medium | Medium | US-05 | TS-08 | Approved |
| **TC-14** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra sắp xếp danh mục sản phẩm theo tên đảo ngược từ Z đến A | Functional / Sorting | Medium | Medium | US-05 | TS-08 | Approved |
| **TC-15** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ thấp đến cao (Price low to high) | Functional / Business Logic | High | High | US-05 | TS-09 | Approved |
| **TC-16** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ cao đến thấp (Price high to low) | Functional / Business Logic | High | High | US-05 | TS-09 | Approved |
| **TC-17** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra tính toàn vẹn của liên kết hình ảnh danh mục sản phẩm đối với tài khoản problem_user | UI / Asset Integrity / Defect Detection | Medium | Medium | US-04 | TS-06 | Approved |
| **TC-18** | 01_Functional_Testing/02_Product_Catalog | Kiểm tra bộ lọc sắp xếp danh mục sản phẩm không phát sinh lỗi ngoại lệ JavaScript khi đăng nhập bằng error_user | Error Handling / UI Exception / Defect Detection | High | High | US-05 | TS-08 | Approved |
| **TC-19** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra thêm 1 sản phẩm vào giỏ hàng từ trang danh mục | Functional / State Update | High | Critical | US-06 | TS-10 | Approved |
| **TC-20** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra thêm nhiều sản phẩm vào giỏ hàng và đồng bộ bộ đếm | Functional / Boundary | High | High | US-06 | TS-10 | Approved |
| **TC-21** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm | Functional / State Update | Medium | Medium | US-06 | TS-11 | Approved |
| **TC-22** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra xóa sản phẩm khỏi giỏ hàng trực tiếp từ trang danh mục | Functional / State Update | High | High | US-06 | TS-12 | Approved |
| **TC-23** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra xóa sản phẩm khỏi giỏ hàng từ trang chi tiết sản phẩm | Functional / State Update | Medium | Medium | US-06 | TS-12 | Approved |
| **TC-24** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra mở trang giỏ hàng và hiển thị danh sách sản phẩm đã thêm | Functional / UI Verification | High | Critical | US-07 | TS-13 | Approved |
| **TC-25** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra xóa trực tiếp sản phẩm trên trang giỏ hàng (Cart Page) | Functional / List Update | High | High | US-07 | TS-14 | Approved |
| **TC-26** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra chức năng nút 'Continue Shopping' quay lại trang mua hàng | Functional / Navigation | Medium | Low | US-07 | TS-15 | Approved |
| **TC-27** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra duy trì trạng thái giỏ hàng khi tải lại trang trình duyệt (F5 / Refresh) | Functional / State Persistence | High | High | US-08 | TS-16 | Approved |
| **TC-28** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra chức năng xóa sản phẩm khỏi giỏ hàng đối với sản phẩm Fleece Jacket khi đăng nhập bằng problem_user | Functional / Negative / Defect Detection | High | High | US-06 | TS-12 | Approved |
| **TC-29** | 01_Functional_Testing/03_Shopping_Cart | Kiểm tra chặn quy trình thanh toán khi giỏ hàng không có sản phẩm nào (Empty Cart Checkout) | Functional / Negative / Business Logic / Defect Detection | High | High | US-08 | TS-17 | Approved |
| **TC-30** | 01_Functional_Testing/04_Checkout | Kiểm tra chuyển hướng từ giỏ hàng sang Checkout Bước 1 | Functional / Navigation | High | Critical | US-09 | TS-18 | Approved |
| **TC-31** | 01_Functional_Testing/04_Checkout | Kiểm tra nhập thông tin khách hàng hợp lệ tại Checkout Bước 1 | Functional / Form Submission | High | Critical | US-09 | TS-19 | Approved |
| **TC-32** | 01_Functional_Testing/04_Checkout | Kiểm tra thông báo lỗi khi để trống trường First Name tại Bước 1 | Negative / Form Validation | High | Medium | US-09 | TS-20 | Approved |
| **TC-33** | 01_Functional_Testing/04_Checkout | Kiểm tra thông báo lỗi khi để trống trường Last Name tại Bước 1 | Negative / Form Validation | High | Medium | US-09 | TS-20 | Approved |
| **TC-34** | 01_Functional_Testing/04_Checkout | Kiểm tra thông báo lỗi khi để trống trường Postal Code tại Bước 1 | Negative / Form Validation | High | Medium | US-09 | TS-20 | Approved |
| **TC-35** | 01_Functional_Testing/04_Checkout | Kiểm tra nhập các định dạng mã bưu chính đặc biệt (Ký tự chữ và dấu gạch nối) | Functional / Boundary | Medium | Low | US-09 | TS-19 | Approved |
| **TC-36** | 01_Functional_Testing/04_Checkout | Kiểm tra hủy bỏ quy trình thanh toán tại Bước 1 bằng nút 'Cancel' | Functional / Navigation | Medium | Low | US-09 | TS-21 | Approved |
| **TC-37** | 01_Functional_Testing/04_Checkout | Kiểm tra hiển thị danh sách sản phẩm và tổng quan đơn hàng tại Checkout Bước 2 | Functional / UI Verification | High | High | US-10 | TS-22 | Approved |
| **TC-38** | 01_Functional_Testing/04_Checkout | Kiểm tra hiển thị thông tin thanh toán và thông tin giao hàng tại Bước 2 | Functional / UI Verification | Medium | Low | US-10 | TS-22 | Approved |
| **TC-39** | 01_Functional_Testing/04_Checkout | Kiểm tra tính toán tài chính: Tổng tiền hàng, Thuế 8% và Tổng thanh toán tại Bước 2 | Functional / Calculation & Boundary | High | Critical | US-10 | TS-23 | Approved |
| **TC-40** | 01_Functional_Testing/04_Checkout | Kiểm tra hủy bỏ thanh toán tại Bước 2 bằng nút 'Cancel' | Functional / Navigation | Medium | Low | US-10 | TS-24 | Approved |
| **TC-41** | 01_Functional_Testing/04_Checkout | Kiểm tra hoàn tất đặt hàng thành công tại Checkout Bước 3 | Functional / Transaction | High | Critical | US-11 | TS-25 | Approved |
| **TC-42** | 01_Functional_Testing/04_Checkout | Kiểm tra nút 'Back Home' đưa người dùng quay về trang chủ sau khi hoàn tất mua hàng | Functional / Navigation | Medium | Low | US-11 | TS-26 | Approved |
| **TC-43** | 01_Functional_Testing/04_Checkout | Kiểm tra nhập liệu và lưu trữ giá trị tại trường Last Name trong form Checkout Step 1 với problem_user | Functional / Form Validation / Defect Detection | High | Critical | US-09 | TS-19 | Approved |
| **TC-44** | 01_Functional_Testing/04_Checkout | Kiểm tra hoàn tất đơn hàng tại Checkout Step 2 không bị chặn bởi lỗi Runtime khi đăng nhập bằng error_user | Functional / Transaction Integrity / Defect Detection | High | Blocker | US-10 | TS-24 | Approved |
| **TC-45** | 01_Functional_Testing/05_Sidebar_Navigation | Kiểm tra mở và đóng menu Sidebar | Functional / UI Animation | Medium | Low | US-12 | TS-27 | Approved |
| **TC-46** | 01_Functional_Testing/05_Sidebar_Navigation | Kiểm tra mục 'All Items' trong Sidebar đưa người dùng về trang danh mục | Functional / Navigation | Medium | Low | US-12 | TS-27 | Approved |
| **TC-47** | 01_Functional_Testing/05_Sidebar_Navigation | Kiểm tra mục 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs | Functional / External Link | Low | Low | US-12 | TS-27 | Approved |
| **TC-48** | 01_Functional_Testing/05_Sidebar_Navigation | Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng và xóa sạch giỏ hàng | Functional / State Reset | High | High | US-12 | TS-27 | Approved |
| **TC-49** | 01_Functional_Testing/05_Sidebar_Navigation | Kiểm tra tính hợp lệ của liên kết điều hướng 'About' trong Sidebar đối với problem_user | Navigation / Broken Link / Defect Detection | Low | Low | US-12 | TS-27 | Approved |
| **TC-50** | 01_Functional_Testing/06_End_to_End | Kiểm tra toàn diện quy trình mua sắm thương mại điện tử End-to-End từ đăng nhập đến nhận biên lai | Functional / End-to-End System Integration | High | Critical | US-13 | TS-28 | Approved |
| **TC-51** | 02_API_Testing | Kiểm tra API POST /api/v1/auth/login xác thực đăng nhập thành công với tài khoản hợp lệ | API / Integration Testing | High | Critical | US-14 | TS-31 | Approved |
| **TC-52** | 02_API_Testing | Kiểm tra API POST /api/v1/auth/login xử lý từ chối đăng nhập đối với tài khoản bị khóa (HTTP 423 Locked) | API / Negative Testing | High | High | US-14 | TS-31 | Approved |
| **TC-53** | 02_API_Testing | Kiểm tra API GET /api/v1/products lấy danh mục sản phẩm và kiểm tra Schema JSON | API / Schema Validation | High | High | US-14 | TS-31 | Approved |
| **TC-54** | 02_API_Testing | Kiểm tra API POST /api/v1/cart/items thêm sản phẩm vào giỏ hàng và cập nhật tổng số lượng | API / Functional Testing | High | High | US-14 | TS-31 | Approved |
| **TC-55** | 02_API_Testing | Kiểm tra API POST /api/v1/checkout/orders hoàn tất đơn hàng và tính toán tài chính tự động | API / Transaction & Calculation | High | Critical | US-14 | TS-31 | Approved |
| **TC-56** | 03_Database_SQL_Testing | Kiểm tra CSDL: Xác minh mật khẩu người dùng được băm an toàn trong bảng users | Database / Security Verification | High | Critical | US-15 | TS-32 | Approved |
| **TC-57** | 03_Database_SQL_Testing | Kiểm tra CSDL: Xác minh trạng thái khóa tài khoản trong bảng users đối với locked_out_user | Database / Data Consistency | High | High | US-15 | TS-32 | Approved |
| **TC-58** | 03_Database_SQL_Testing | Kiểm tra CSDL: Xác minh tính nhất quán của bảng danh mục sản phẩm và giá niêm yết | Database / Data Consistency | High | High | US-15 | TS-32 | Approved |
| **TC-59** | 03_Database_SQL_Testing | Kiểm tra CSDL: Xác minh ghi nhận bản ghi đơn hàng mới vào bảng orders sau khi thanh toán thành công | Database / Transaction Verification | High | Critical | US-15 | TS-32 | Approved |
| **TC-60** | 03_Database_SQL_Testing | Kiểm tra CSDL: Xác minh chi tiết các mặt hàng trong bảng order_items liên kết đúng với đơn hàng | Database / Relational Integrity | High | High | US-15 | TS-32 | Approved |
| **TC-61** | 04_Non_Functional_Testing/Performance_Testing | Kiểm tra phi chức năng: Đo lường thời gian phản hồi (Response Time SLA < 2.0s) khi tải trang danh mục sản phẩm | Performance Testing | Medium | Medium | US-17 | TS-34 | Approved |
| **TC-62** | 04_Non_Functional_Testing/Performance_Testing | Kiểm tra phi chức năng: Phát hiện vi phạm SLA thời gian phản hồi nghiêm trọng (>5.0s) đối với performance_glitch_user | Performance SLA / Response Time / Defect Detection | Medium | Medium | US-17 | TS-34 | Approved |
| **TC-63** | 04_Non_Functional_Testing/Security_Testing | Kiểm tra phi chức năng: Kiểm tra các cờ bảo mật của Cookie phiên làm việc (Secure, HttpOnly, SameSite) | Security Testing | High | High | US-16 | TS-33 | Approved |
| **TC-64** | 04_Non_Functional_Testing/Security_Testing | Kiểm tra phi chức năng: Kiểm tra khả năng chống tấn công Cross-Site Scripting (XSS) trên form Checkout Step 1 | Security Testing | High | Critical | US-16 | TS-33 | Approved |
| **TC-65** | 04_Non_Functional_Testing/Security_Testing | Kiểm tra phi chức năng: Kiểm tra chống rò rỉ phiên làm việc khi sử dụng nút 'Back' của trình duyệt sau khi đăng xuất | Security / Session Management | High | High | US-16 | TS-33 | Approved |
| **TC-66** | 04_Non_Functional_Testing/Accessibility_Testing | Kiểm tra phi chức năng: Kiểm tra điều hướng tuần tự bằng bàn phím (Keyboard Tab Order & Focus Ring) | Accessibility Testing | Medium | Medium | US-17 | TS-34 | Approved |
| **TC-67** | 04_Non_Functional_Testing/Accessibility_Testing | Kiểm tra phi chức năng: Kiểm tra tên trợ năng (Accessible Names / aria-label) và độ tương phản màu sắc | Accessibility Testing | Medium | Low | US-17 | TS-34 | Approved |
| **TC-68** | 04_Non_Functional_Testing/Usability_Testing | Kiểm tra phi chức năng: Tính nhất quán của phản hồi trực quan trên bộ đếm giỏ hàng | Usability Testing | Medium | Low | US-17 | TS-34 | Approved |
| **TC-69** | 04_Non_Functional_Testing/Usability_Testing | Kiểm tra phi chức năng: Phát hiện lỗi căn chỉnh layout và vị trí các thành phần trên thanh Header khi đăng nhập bằng visual_user | Visual Regression / UI Layout / Defect Detection | Low | Low | US-17 | TS-34 | Approved |
| **TC-70** | 04_Non_Functional_Testing/Compatibility_Testing | Kiểm tra phi chức năng: Kiểm tra tính tương thích hiển thị Responsive UI trên màn hình Mobile Viewport | Compatibility / Responsive Testing | Medium | Medium | US-17 | TS-34 | Approved |
| **TC-71** | 04_Non_Functional_Testing/Compatibility_Testing | Kiểm tra phi chức năng: Kiểm tra khả năng tương thích hiển thị và hoạt động trên nhiều trình duyệt (Cross-Browser) | Compatibility / Cross-Browser | Medium | Medium | US-17 | TS-34 | Approved |

---

<a id="tc-section-3"></a>
## 3. Detailed Test Cases

<a id="tc-folder-01_functional_testing-01_authentication"></a>
### 01_Functional_Testing/01_Authentication

#### [TC-01] Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-01 |
| **Name** | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-01 |
| **TestScenarioID** | TS-01 |
| **Test Type** | Functional / Smoke |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt đang mở tại địa chỉ 'https://www.saucedemo.com/'; chưa có cookie phiên làm việc nào. |
| **Test Data** | Username: standard_user | Password: secret_sauce |
| **Postcondition** | Người dùng đăng nhập thành công, phiên làm việc hoạt động trên trang '/inventory.html'. |

##### Objective
Xác minh người dùng hợp lệ có thể đăng nhập thành công bằng thông tin tài khoản tiêu chuẩn và được chuyển hướng vào trang danh mục sản phẩm.

##### Test Steps

1. Truy cập vào trang web 'https://www.saucedemo.com/'.
2. Nhập 'standard_user' vào ô 'Username'.
3. Nhập 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Đăng nhập thành công và chuyển hướng đến 'https://www.saucedemo.com/inventory.html'. Tiêu đề trang hiển thị 'Products', biểu tượng giỏ hàng xuất hiện và cookie 'session-username=standard_user' được thiết lập.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử Smoke quan trọng cho chức năng đăng nhập.

#### [TC-02] Kiểm tra thông báo lỗi khi để trống cả Username và Password

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-02 |
| **Name** | Kiểm tra thông báo lỗi khi để trống cả Username và Password |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. Cả hai ô nhập liệu đều trống. |
| **Test Data** | Username: '' (để trống) | Password: '' (để trống) |
| **Postcondition** | Không có phiên làm việc nào được tạo; thông báo lỗi hiển thị rõ ràng. |

##### Objective
Đảm bảo hệ thống chặn đăng nhập và hiển thị đúng thông báo lỗi yêu cầu khi người dùng để trống cả hai ô nhập liệu (Kỹ thuật phân vùng tương đương: Dữ liệu rỗng).

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Để trống ô 'Username'.
3. Để trống ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Hệ thống từ chối đăng nhập. Người dùng vẫn ở lại trang đăng nhập. Hộp thông báo màu đỏ hiển thị chính xác nội dung: 'Epic sadface: Username is required'. Các ô nhập liệu hiển thị biểu tượng cảnh báo màu đỏ.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Chuỗi rỗng / Không nhập dữ liệu.

#### [TC-03] Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-03 |
| **Name** | Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. |
| **Test Data** | Username: standard_user | Password: '' (để trống) |
| **Postcondition** | Không tạo cookie phiên; người dùng ở lại trang đăng nhập. |

##### Objective
Xác minh khi người dùng đã nhập tên đăng nhập hợp lệ nhưng bỏ trống mật khẩu, hệ thống phải yêu cầu nhập mật khẩu.

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập 'standard_user' vào ô 'Username'.
3. Để trống hoàn toàn ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Hệ thống từ chối đăng nhập. Xuất hiện thông báo lỗi màu đỏ với nội dung: 'Epic sadface: Password is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Thiếu trường bắt buộc Password.

#### [TC-04] Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-04 |
| **Name** | Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. |
| **Test Data** | Username: '' (để trống) | Password: secret_sauce |
| **Postcondition** | Không tạo phiên làm việc; người dùng ở lại trang đăng nhập. |

##### Objective
Xác minh khi người dùng bỏ trống ô tên đăng nhập nhưng có nhập mật khẩu, hệ thống ưu tiên thông báo yêu cầu Username.

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Để trống ô 'Username'.
3. Nhập 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Hệ thống từ chối đăng nhập. Xuất hiện thông báo lỗi màu đỏ: 'Epic sadface: Username is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Thiếu trường bắt buộc Username.

#### [TC-05] Kiểm tra từ chối đăng nhập khi nhập sai thông tin tài khoản hoặc mật khẩu

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-05 |
| **Name** | Kiểm tra từ chối đăng nhập khi nhập sai thông tin tài khoản hoặc mật khẩu |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-03 |
| **Test Type** | Negative / Security |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. |
| **Test Data** | Username: invalid_user | Password: wrong_password |
| **Postcondition** | Không cấp quyền truy cập; người dùng ở lại trang đăng nhập. |

##### Objective
Đảm bảo hệ thống bảo vệ tài khoản người dùng bằng cách từ chối truy cập và đưa ra thông báo an toàn khi nhập sai thông tin.

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập 'invalid_user' vào ô 'Username'.
3. Nhập 'wrong_password' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Hệ thống từ chối đăng nhập và hiển thị thông báo lỗi màu đỏ: 'Epic sadface: Username and password do not match any user in this service'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra bảo mật: Không tiết lộ cụ thể sai ở username hay password.

#### [TC-06] Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-06 |
| **Name** | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-04 |
| **Test Type** | Negative / Security |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Tài khoản 'locked_out_user' đã được đánh dấu trạng thái bị khóa trên hệ thống. |
| **Test Data** | Username: locked_out_user | Password: secret_sauce |
| **Postcondition** | Tài khoản bị khóa không được phép truy cập trang mua hàng. |

##### Objective
Xác minh tài khoản người dùng bị khóa trong hệ thống không thể đăng nhập và nhận được thông báo giải thích cụ thể.

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập 'locked_out_user' vào ô 'Username'.
3. Nhập 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Hệ thống ngăn chặn đăng nhập và hiển thị thông báo lỗi chính xác: 'Epic sadface: Sorry, this user has been locked out.'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra xử lý phân quyền và tài khoản bị vô hiệu hóa.

#### [TC-07] Kiểm tra thao tác đóng thông báo lỗi đăng nhập bằng nút 'X'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-07 |
| **Name** | Kiểm tra thao tác đóng thông báo lỗi đăng nhập bằng nút 'X' |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Functional / UI Interaction |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang có thông báo lỗi đăng nhập hiển thị trên màn hình. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Giao diện trang đăng nhập trở về trạng thái sạch sẽ không có thông báo lỗi. |

##### Objective
Xác minh khi xuất hiện thông báo lỗi, người dùng có thể nhấp vào biểu tượng 'X' để tắt thông báo lỗi.

##### Test Steps

1. Để trống thông tin và nhấp 'Login' để làm xuất hiện thông báo lỗi.
2. Quan sát thấy hộp thông báo lỗi màu đỏ có biểu tượng 'X' ở góc phải.
3. Nhấp vào nút biểu tượng 'X'.

##### Expected Result

Hộp thông báo lỗi màu đỏ biến mất hoàn toàn khỏi giao diện màn hình đăng nhập.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính tương tác giao diện (Usability).

#### [TC-08] Kiểm tra đăng xuất tài khoản an toàn thông qua menu điều hướng Sidebar

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-08 |
| **Name** | Kiểm tra đăng xuất tài khoản an toàn thông qua menu điều hướng Sidebar |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Sidebar Navigation / Session |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-03 |
| **TestScenarioID** | TS-05 |
| **Test Type** | Functional / Security |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang đăng nhập bằng tài khoản 'standard_user' tại trang '/inventory.html'. |
| **Test Data** | Tài khoản đang hoạt động: standard_user |
| **Postcondition** | Phiên làm việc kết thúc hoàn toàn; người dùng không còn quyền truy cập dữ liệu mua sắm. |

##### Objective
Xác minh người dùng đã đăng nhập có thể đăng xuất khỏi hệ thống an toàn qua tùy chọn Logout trên thanh menu điều hướng.

##### Test Steps

1. Nhấp vào biểu tượng 3 dấu gạch ngang (hamburger menu) ở góc trên bên trái.
2. Chờ menu trượt mở ra hoàn toàn.
3. Nhấp vào liên kết 'Logout'.
4. Kiểm tra URL trình duyệt và kiểm tra Cookie 'session-username' trong Application tab.

##### Expected Result

Hệ thống hủy phiên làm việc, xóa cookie hoặc vô hiệu hóa phiên, và chuyển hướng người dùng quay trở về trang đăng nhập 'https://www.saucedemo.com/'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử an toàn phiên làm việc cốt lõi.

#### [TC-09] Kiểm tra chặn truy cập trực tiếp URL trang nội bộ khi chưa đăng nhập

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-09 |
| **Name** | Kiểm tra chặn truy cập trực tiếp URL trang nội bộ khi chưa đăng nhập |
| **Folder** | 01_Functional_Testing/01_Authentication |
| **Component** | Access Control / Session |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-03 |
| **TestScenarioID** | TS-05 |
| **Test Type** | Security / Authorization |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt ở chế độ ẩn danh (Incognito) hoặc chưa đăng nhập (không có cookie phiên). |
| **Test Data** | URL trực tiếp: https://www.saucedemo.com/inventory.html |
| **Postcondition** | Không cấp quyền truy cập vào dữ liệu sản phẩm. |

##### Objective
Đảm bảo người dùng chưa xác thực không thể bỏ qua trang đăng nhập bằng cách gõ trực tiếp URL '/inventory.html' trên thanh địa chỉ trình duyệt.

##### Test Steps

1. Mở cửa sổ trình duyệt mới hoàn toàn sạch cookie.
2. Nhập trực tiếp đường dẫn 'https://www.saucedemo.com/inventory.html' vào thanh địa chỉ và nhấn Enter.

##### Expected Result

Hệ thống chặn truy cập, tự động chuyển hướng về trang chủ đăng nhập và hiển thị thông báo lỗi màu đỏ: 'Epic sadface: You can only access \'/inventory.html\' when you are logged in.'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bảo vệ tài nguyên nội bộ chống truy cập trái phép (URL Tampering / Direct Object Reference).

---

<a id="tc-folder-01_functional_testing-02_product_catalog"></a>
### 01_Functional_Testing/02_Product_Catalog

#### [TC-10] Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và các thông tin chi tiết

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-10 |
| **Name** | Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và các thông tin chi tiết |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Catalog |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-06 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập thành công bằng tài khoản 'standard_user'. |
| **Test Data** | Số lượng sản phẩm: 6 sản phẩm niêm yết |
| **Postcondition** | Người dùng xem được đầy đủ danh mục hàng hóa. |

##### Objective
Xác minh trang danh mục sản phẩm hiển thị chính xác toàn bộ 6 sản phẩm với đầy đủ ảnh, tên, mô tả và giá bán chuẩn định dạng tiền tệ.

##### Test Steps

1. Đăng nhập và đi đến trang '/inventory.html'.
2. Đếm số lượng sản phẩm hiển thị trên trang danh mục.
3. Kiểm tra từng sản phẩm phải có đủ: Ảnh đại diện, Tên sản phẩm dạng liên kết, Đoạn văn mô tả chi tiết, Giá tiền bắt đầu bằng ký hiệu '\$', và Nút 'Add to cart'.

##### Expected Result

Hiển thị đúng 6 sản phẩm không thiếu sót; định dạng giá tiền chuẩn xác (\$29.99, \$9.99, \$15.99, \$49.99, \$7.99, \$15.99); hình ảnh rõ nét không bị vỡ.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính toàn vẹn dữ liệu hiển thị trên giao diện người dùng.

#### [TC-11] Kiểm tra xem trang chi tiết sản phẩm khi nhấp vào tên hoặc ảnh sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-11 |
| **Name** | Kiểm tra xem trang chi tiết sản phẩm khi nhấp vào tên hoặc ảnh sản phẩm |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Details |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-07 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục '/inventory.html'. |
| **Test Data** | Sản phẩm chọn: Sauce Labs Backpack (\$29.99) |
| **Postcondition** | Người dùng xem được chi tiết của sản phẩm đã chọn. |

##### Objective
Xác minh khi người dùng nhấp vào tiêu đề hoặc ảnh của một sản phẩm, hệ thống điều hướng chính xác đến trang chi tiết của sản phẩm đó.

##### Test Steps

1. Tại trang danh mục, nhấp vào tên sản phẩm 'Sauce Labs Backpack'.
2. Quan sát URL trên thanh địa chỉ.
3. Kiểm tra thông tin hiển thị tại trang chi tiết: Tên sản phẩm, Ảnh lớn, Mô tả, Giá tiền \$29.99 và Nút 'Add to cart'.

##### Expected Result

Trình duyệt chuyển hướng đến '/inventory-item.html?id=4', thông tin sản phẩm hiển thị đồng nhất và chuẩn xác với trang danh mục ngoài.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra liên kết điều hướng và truyền tham số ID sản phẩm.

#### [TC-12] Kiểm tra nút 'Back to products' quay lại trang danh mục từ trang chi tiết

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-12 |
| **Name** | Kiểm tra nút 'Back to products' quay lại trang danh mục từ trang chi tiết |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Details |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-07 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang xem trang chi tiết của một sản phẩm bất kỳ. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng tiếp tục duyệt danh mục sản phẩm bình thường. |

##### Objective
Xác minh nút điều hướng quay lại hoạt động mượt mà và đưa người dùng trở về đúng trang danh mục ban đầu.

##### Test Steps

1. Đang ở trang chi tiết sản phẩm '/inventory-item.html?id=4'.
2. Nhấp vào nút 'Back to products' ở góc trên bên trái nội dung.

##### Expected Result

Trình duyệt quay trở lại trang danh mục '/inventory.html' và hiển thị lại đầy đủ 6 sản phẩm.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra trải nghiệm điều hướng người dùng (UX Navigation).

#### [TC-13] Kiểm tra sắp xếp danh mục sản phẩm theo tên từ A đến Z

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-13 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo tên từ A đến Z |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Name (A to Z)' |
| **Postcondition** | Danh mục duy trì thứ tự sắp xếp A-Z. |

##### Objective
Đảm bảo bộ chọn sắp xếp sắp xếp lại các sản phẩm theo thứ tự chữ cái tên sản phẩm từ A đến Z một cách chính xác.

##### Test Steps

1. Nhấp vào menu dropdown sắp xếp (Product sort container).
2. Chọn tùy chọn 'Name (A to Z)'.
3. Đọc danh sách tên các sản phẩm từ trên xuống dưới.

##### Expected Result

Danh sách sản phẩm được sắp xếp đúng thứ tự: 1. Sauce Labs Backpack, 2. Sauce Labs Bike Light, 3. Sauce Labs Bolt T-Shirt, 4. Sauce Labs Fleece Jacket, 5. Sauce Labs Onesie, 6. Test.allTheThings() T-Shirt (Red).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Sắp xếp theo thứ tự bảng chữ cái mặc định.

#### [TC-14] Kiểm tra sắp xếp danh mục sản phẩm theo tên đảo ngược từ Z đến A

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-14 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo tên đảo ngược từ Z đến A |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Name (Z to A)' |
| **Postcondition** | Danh mục hiển thị theo thứ tự tên Z đến A. |

##### Objective
Đảm bảo bộ chọn sắp xếp sắp xếp lại các sản phẩm theo thứ tự chữ cái đảo ngược từ Z đến A một cách chính xác.

##### Test Steps

1. Nhấp vào dropdown sắp xếp.
2. Chọn tùy chọn 'Name (Z to A)'.
3. Kiểm tra tên sản phẩm đầu tiên và sản phẩm cuối cùng trong danh sách.

##### Expected Result

Sản phẩm đầu tiên là 'Test.allTheThings() T-Shirt (Red)' và sản phẩm cuối cùng là 'Sauce Labs Backpack'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra thuật toán sắp xếp chuỗi ký tự ngược.

#### [TC-15] Kiểm tra sắp xếp danh mục sản phẩm theo giá từ thấp đến cao (Price low to high)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-15 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ thấp đến cao (Price low to high) |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-09 |
| **Test Type** | Functional / Business Logic |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Price (low to high)' |
| **Postcondition** | Sản phẩm sắp xếp theo giá tăng dần. |

##### Objective
Xác minh thuật toán sắp xếp giá so sánh theo giá trị số thực (numeric value), đảm bảo sản phẩm rẻ nhất xếp đầu và đắt nhất xếp cuối.

##### Test Steps

1. Nhấp vào dropdown sắp xếp.
2. Chọn tùy chọn 'Price (low to high)'.
3. Trích xuất giá của toàn bộ 6 sản phẩm theo thứ tự hiển thị.

##### Expected Result

Dãy giá hiển thị tăng dần chuẩn xác: \$7.99 (Onesie) <= \$9.99 (Bike Light) <= \$15.99 (Bolt T-Shirt) <= \$15.99 (Red T-Shirt) <= \$29.99 (Backpack) <= \$49.99 (Fleece Jacket).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phát hiện lỗi thường gặp: So sánh chuỗi (lexicographical) thay vì so sánh số học.

#### [TC-16] Kiểm tra sắp xếp danh mục sản phẩm theo giá từ cao đến thấp (Price high to low)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-16 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ cao đến thấp (Price high to low) |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-09 |
| **Test Type** | Functional / Business Logic |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Price (high to low)' |
| **Postcondition** | Sản phẩm sắp xếp theo giá giảm dần. |

##### Objective
Xác minh sản phẩm có giá cao nhất xếp ở vị trí đầu tiên và giảm dần cho đến sản phẩm có giá thấp nhất.

##### Test Steps

1. Nhấp vào dropdown sắp xếp.
2. Chọn tùy chọn 'Price (high to low)'.
3. Kiểm tra sản phẩm đầu tiên và sản phẩm cuối cùng.

##### Expected Result

Sản phẩm đầu tiên có giá \$49.99 (Sauce Labs Fleece Jacket) và sản phẩm cuối cùng có giá \$7.99 (Sauce Labs Onesie).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra thuật toán sắp xếp số học giảm dần.

#### [TC-17] Kiểm tra tính toàn vẹn của liên kết hình ảnh danh mục sản phẩm đối với tài khoản problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-17 |
| **Name** | Kiểm tra tính toàn vẹn của liên kết hình ảnh danh mục sản phẩm đối với tài khoản problem_user |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Catalog / Asset Integrity |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-06 |
| **Test Type** | UI / Asset Integrity / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt chưa có phiên làm việc. |
| **Test Data** | Username: problem_user | Password: secret_sauce |
| **Postcondition** | Giao diện hiển thị trực quan, hình ảnh sản phẩm chính xác. |

##### Objective
Xác minh tất cả hình ảnh sản phẩm trên trang danh mục tải lên chính xác ảnh thực của từng sản phẩm, không bị hỏng hoặc trỏ sai đường dẫn tài nguyên.

##### Test Steps

1. Truy cập 'https://www.saucedemo.com/'.
2. Đăng nhập bằng 'problem_user' / 'secret_sauce'.
3. Quan sát hình ảnh đại diện của cả 6 sản phẩm trên trang danh mục '/inventory.html'.
4. Kiểm tra thuộc tính 'src' của các thẻ <img> và đối chiếu với tên sản phẩm.

##### Expected Result

Tất cả 6 sản phẩm hiển thị đúng hình ảnh tương ứng (Balo hiển thị ảnh Balo, Đèn xe đạp hiển thị ảnh Đèn...). Không có hình ảnh nào bị vỡ hoặc trỏ đến đường dẫn tài nguyên lỗi.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Toàn bộ ảnh sản phẩm của problem_user bị trỏ về ảnh con chó lỗi /static/media/sl-404.168b1cce.jpg.

#### [TC-18] Kiểm tra bộ lọc sắp xếp danh mục sản phẩm không phát sinh lỗi ngoại lệ JavaScript khi đăng nhập bằng error_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-18 |
| **Name** | Kiểm tra bộ lọc sắp xếp danh mục sản phẩm không phát sinh lỗi ngoại lệ JavaScript khi đăng nhập bằng error_user |
| **Folder** | 01_Functional_Testing/02_Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Error Handling / UI Exception / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'error_user'; đang ở trang '/inventory.html'. |
| **Test Data** | Username: error_user | Tùy chọn sắp xếp: 'Price (low to high)' |
| **Postcondition** | Sản phẩm hiển thị theo đúng tiêu chí sắp xếp. |

##### Objective
Xác minh khi người dùng thay đổi tùy chọn sắp xếp danh mục, hệ thống sắp xếp mượt mà và không phát sinh cửa sổ cảnh báo unhandled exception.

##### Test Steps

1. Đăng nhập bằng 'error_user' / 'secret_sauce'.
2. Nhấp vào dropdown sắp xếp sản phẩm (mặc định 'Name (A to Z)').
3. Chọn tùy chọn 'Price (low to high)'.

##### Expected Result

Danh sách sản phẩm được sắp xếp lại theo giá tiền tăng dần (\$7.99 -> \$49.99). Không có hộp thoại popup alert nào của trình duyệt xuất hiện làm gián đoạn người dùng.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Khi error_user đổi bộ lọc, mã JavaScript kích hoạt lệnh window.alert('Sorting is broken! This error has been reported to Backtrace.'), danh sách không được sắp xếp lại.

---

<a id="tc-folder-01_functional_testing-03_shopping_cart"></a>
### 01_Functional_Testing/03_Shopping_Cart

#### [TC-19] Kiểm tra thêm 1 sản phẩm vào giỏ hàng từ trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-19 |
| **Name** | Kiểm tra thêm 1 sản phẩm vào giỏ hàng từ trang danh mục |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-10 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập; giỏ hàng ban đầu đang trống (không có huy hiệu số lượng). |
| **Test Data** | Sản phẩm: Sauce Labs Backpack |
| **Postcondition** | Giỏ hàng có 1 món hàng; trạng thái lưu vào bộ nhớ trình duyệt. |

##### Objective
Xác minh khi người dùng nhấn 'Add to cart' tại một sản phẩm trên trang danh mục, nút đổi sang 'Remove' và huy hiệu giỏ hàng hiển thị số '1'.

##### Test Steps

1. Đang ở trang danh mục sản phẩm '/inventory.html'.
2. Tìm sản phẩm 'Sauce Labs Backpack'.
3. Nhấp vào nút 'Add to cart' tương ứng với sản phẩm này.

##### Expected Result

Nút bấm lập tức chuyển thành chữ 'Remove' với viền đỏ. Biểu tượng giỏ hàng ở góc trên bên phải xuất hiện huy hiệu màu đỏ hiển thị số '1'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra đồng bộ giao diện và cập nhật trạng thái giỏ hàng (State Management).

#### [TC-20] Kiểm tra thêm nhiều sản phẩm vào giỏ hàng và đồng bộ bộ đếm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-20 |
| **Name** | Kiểm tra thêm nhiều sản phẩm vào giỏ hàng và đồng bộ bộ đếm |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-10 |
| **Test Type** | Functional / Boundary |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Giỏ hàng đang trống. |
| **Test Data** | 3 sản phẩm: Backpack, Bike Light, Bolt T-Shirt |
| **Postcondition** | Giỏ hàng lưu trữ đúng 3 sản phẩm đã chọn. |

##### Objective
Xác minh bộ đếm huy hiệu giỏ hàng tự động tăng theo đúng số lượng sản phẩm được thêm vào (kiểm tra với 3 sản phẩm khác nhau).

##### Test Steps

1. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Backpack -> Huy hiệu hiển thị 1.
2. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Bike Light -> Huy hiệu hiển thị 2.
3. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Bolt T-Shirt -> Huy hiệu hiển thị 3.

##### Expected Result

Huy hiệu giỏ hàng tăng tuần tự từ 1 -> 2 -> 3; cả 3 nút của 3 sản phẩm đều chuyển thành 'Remove'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính lũy kế của biến đếm giỏ hàng.

#### [TC-21] Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-21 |
| **Name** | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Product Details / Cart |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-11 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang xem trang chi tiết '/inventory-item.html?id=0' (Sauce Labs Bike Light). |
| **Test Data** | Sản phẩm: Sauce Labs Bike Light (\$9.99) |
| **Postcondition** | Trạng thái giỏ hàng đồng bộ giữa trang chi tiết và trang danh mục ngoài. |

##### Objective
Xác minh nút 'Add to cart' trên trang chi tiết sản phẩm hoạt động chính xác và đồng bộ huy hiệu giỏ hàng.

##### Test Steps

1. Mở trang chi tiết sản phẩm Bike Light.
2. Nhấp vào nút 'Add to cart'.
3. Nhấp vào nút 'Back to products' để quay lại trang danh mục.

##### Expected Result

Tại trang chi tiết: Nút chuyển thành 'Remove', huy hiệu giỏ hàng tăng thêm 1. Khi quay lại trang danh mục: Nút tương ứng của sản phẩm đó cũng hiển thị đúng trạng thái 'Remove'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra đồng bộ dữ liệu liên trang (Cross-page State Sync).

#### [TC-22] Kiểm tra xóa sản phẩm khỏi giỏ hàng trực tiếp từ trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-22 |
| **Name** | Kiểm tra xóa sản phẩm khỏi giỏ hàng trực tiếp từ trang danh mục |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang có 1 sản phẩm trong giỏ hàng (nút đang ở trạng thái 'Remove', huy hiệu hiển thị '1'). |
| **Test Data** | Sản phẩm: Sauce Labs Backpack |
| **Postcondition** | Giỏ hàng rỗng; dữ liệu được cập nhật sạch sẽ. |

##### Objective
Xác minh khi người dùng nhấp 'Remove' trên trang danh mục, sản phẩm được loại bỏ và huy hiệu giỏ hàng giảm tương ứng.

##### Test Steps

1. Tại trang danh mục, nhấp vào nút 'Remove' của sản phẩm 'Sauce Labs Backpack'.
2. Quan sát nút bấm và biểu tượng giỏ hàng.

##### Expected Result

Nút 'Remove' chuyển lại thành nút 'Add to cart'. Huy hiệu số lượng trên biểu tượng giỏ hàng biến mất hoàn toàn (giỏ hàng về 0).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra giá trị biên: Bộ đếm giảm từ 1 về 0 (BVA - Boundary Value Analysis).

#### [TC-23] Kiểm tra xóa sản phẩm khỏi giỏ hàng từ trang chi tiết sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-23 |
| **Name** | Kiểm tra xóa sản phẩm khỏi giỏ hàng từ trang chi tiết sản phẩm |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Product Details / Cart |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Sản phẩm đang được thêm trong giỏ hàng và người dùng đang ở trang chi tiết của sản phẩm đó. |
| **Test Data** | Sản phẩm: Sauce Labs Fleece Jacket (\$49.99) |
| **Postcondition** | Sản phẩm được loại bỏ thành công khỏi giỏ. |

##### Objective
Xác minh việc nhấn nút 'Remove' tại trang chi tiết hoạt động chính xác và làm biến mất huy hiệu giỏ hàng.

##### Test Steps

1. Đang ở trang chi tiết với nút hiển thị 'Remove'.
2. Nhấp vào nút 'Remove'.
3. Quan sát trạng thái nút và huy hiệu giỏ hàng.

##### Expected Result

Nút bấm đổi lại thành 'Add to cart' và huy hiệu số lượng trên giỏ hàng được cập nhật giảm đi 1.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực chức năng xóa tại trang chi tiết.

#### [TC-24] Kiểm tra mở trang giỏ hàng và hiển thị danh sách sản phẩm đã thêm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-24 |
| **Name** | Kiểm tra mở trang giỏ hàng và hiển thị danh sách sản phẩm đã thêm |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Cart Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-13 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã thêm 2 sản phẩm (Backpack \$29.99 và Bike Light \$9.99) vào giỏ hàng. |
| **Test Data** | 2 mặt hàng trong giỏ hàng |
| **Postcondition** | Người dùng xem được tổng quan giỏ hàng trước khi thanh toán. |

##### Objective
Xác minh khi người dùng nhấp vào biểu tượng giỏ hàng, hệ thống điều hướng đến '/cart.html' và hiển thị đúng các mặt hàng đã chọn kèm số lượng và đơn giá.

##### Test Steps

1. Nhấp vào biểu tượng giỏ hàng ở góc trên bên phải trang web.
2. Kiểm tra URL trang đích chuyển đến '/cart.html'.
3. Kiểm tra tiêu đề hiển thị 'Your Cart'.
4. Kiểm tra danh sách hiển thị đúng 2 dòng sản phẩm với cột 'QTY' = 1 và giá tiền chính xác của từng món.

##### Expected Result

Trang giỏ hàng hiển thị đầy đủ thông tin của 2 sản phẩm đã thêm, có đủ các nút 'Continue Shopping' và 'Checkout'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính chính xác của dữ liệu giỏ hàng.

#### [TC-25] Kiểm tra xóa trực tiếp sản phẩm trên trang giỏ hàng (Cart Page)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-25 |
| **Name** | Kiểm tra xóa trực tiếp sản phẩm trên trang giỏ hàng (Cart Page) |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Cart Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-14 |
| **Test Type** | Functional / List Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/cart.html' với 2 sản phẩm. |
| **Test Data** | Sản phẩm xóa: Sauce Labs Bike Light |
| **Postcondition** | Giỏ hàng cập nhật còn lại 1 sản phẩm. |

##### Objective
Xác minh khi nhấp nút 'Remove' ngay trên trang giỏ hàng, sản phẩm đó lập tức bị xóa khỏi danh sách và cập nhật huy hiệu.

##### Test Steps

1. Đang ở trang '/cart.html'.
2. Nhấp nút 'Remove' tương ứng với dòng sản phẩm 'Sauce Labs Bike Light'.
3. Quan sát danh sách giỏ hàng và huy hiệu trên biểu tượng giỏ.

##### Expected Result

Dòng sản phẩm 'Sauce Labs Bike Light' lập tức biến mất khỏi bảng giỏ hàng. Chỉ còn lại 1 sản phẩm 'Sauce Labs Backpack'. Huy hiệu giỏ hàng giảm từ 2 xuống 1.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính năng CRUD: Thao tác Delete trực tiếp trong giỏ hàng.

#### [TC-26] Kiểm tra chức năng nút 'Continue Shopping' quay lại trang mua hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-26 |
| **Name** | Kiểm tra chức năng nút 'Continue Shopping' quay lại trang mua hàng |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Cart Page |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-15 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/cart.html' với ít nhất 1 sản phẩm. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng quay lại mua sắm tiếp mà không bị mất dữ liệu giỏ hàng. |

##### Objective
Xác minh nút 'Continue Shopping' đưa người dùng quay lại trang danh mục sản phẩm và giữ nguyên các mặt hàng hiện có trong giỏ.

##### Test Steps

1. Đang ở trang giỏ hàng '/cart.html'.
2. Nhấp vào nút 'Continue Shopping'.

##### Expected Result

Hệ thống điều hướng quay trở lại trang danh mục sản phẩm '/inventory.html'. Huy hiệu giỏ hàng vẫn giữ nguyên số lượng sản phẩm đang có.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra khả năng tiếp tục trải nghiệm mua sắm.

#### [TC-27] Kiểm tra duy trì trạng thái giỏ hàng khi tải lại trang trình duyệt (F5 / Refresh)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-27 |
| **Name** | Kiểm tra duy trì trạng thái giỏ hàng khi tải lại trang trình duyệt (F5 / Refresh) |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Shopping Cart / Storage |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-08 |
| **TestScenarioID** | TS-16 |
| **Test Type** | Functional / State Persistence |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã thêm 2 sản phẩm vào giỏ hàng (huy hiệu hiển thị '2'). |
| **Test Data** | 2 sản phẩm bất kỳ |
| **Postcondition** | Dữ liệu giỏ hàng không bị xóa khi trang web được tải lại. |

##### Objective
Xác minh dữ liệu giỏ hàng được lưu trữ bền vững (State Persistence) và không bị mất khi người dùng bấm phím F5 hoặc làm mới trình duyệt.

##### Test Steps

1. Thêm 2 sản phẩm vào giỏ hàng tại trang danh mục.
2. Nhấn phím F5 hoặc nhấp nút 'Reload this page' trên trình duyệt.
3. Kiểm tra huy hiệu số lượng trên giỏ hàng và trạng thái các nút bấm.
4. Chuyển sang trang '/cart.html' và kiểm tra danh sách sản phẩm.

##### Expected Result

Sau khi tải lại trang, huy hiệu giỏ hàng vẫn hiển thị số '2', các nút của 2 sản phẩm đó vẫn ở trạng thái 'Remove', và danh sách trong giỏ hàng vẫn còn nguyên vẹn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra khả năng lưu trữ trạng thái vào LocalStorage / SessionStorage.

#### [TC-28] Kiểm tra chức năng xóa sản phẩm khỏi giỏ hàng đối với sản phẩm Fleece Jacket khi đăng nhập bằng problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-28 |
| **Name** | Kiểm tra chức năng xóa sản phẩm khỏi giỏ hàng đối với sản phẩm Fleece Jacket khi đăng nhập bằng problem_user |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Shopping Cart Management |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Functional / Negative / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'problem_user'; đã thêm 'Sauce Labs Fleece Jacket' vào giỏ hàng. |
| **Test Data** | Username: problem_user | Sản phẩm: Sauce Labs Fleece Jacket (\$49.99) |
| **Postcondition** | Sản phẩm được xóa thành công khỏi giỏ hàng. |

##### Objective
Xác minh nút 'Remove' hoạt động chính xác khi người dùng muốn loại bỏ áo khoác Fleece Jacket ra khỏi giỏ hàng.

##### Test Steps

1. Đăng nhập bằng 'problem_user' / 'secret_sauce'.
2. Tìm sản phẩm 'Sauce Labs Fleece Jacket' và nhấp 'Add to cart'.
3. Xác nhận nút chuyển thành 'Remove' và huy hiệu giỏ hàng hiển thị '1'.
4. Nhấp vào nút 'Remove' của sản phẩm 'Sauce Labs Fleece Jacket'.

##### Expected Result

Nút 'Remove' chuyển lại thành 'Add to cart' và huy hiệu giỏ hàng giảm từ 1 về 0 (biến mất hoàn toàn).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Nút Remove của áo Fleece Jacket bị vô hiệu hóa sự kiện onClick, người dùng không thể xóa món hàng này.

#### [TC-29] Kiểm tra chặn quy trình thanh toán khi giỏ hàng không có sản phẩm nào (Empty Cart Checkout)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-29 |
| **Name** | Kiểm tra chặn quy trình thanh toán khi giỏ hàng không có sản phẩm nào (Empty Cart Checkout) |
| **Folder** | 01_Functional_Testing/03_Shopping_Cart |
| **Component** | Shopping Cart / Checkout |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-08 |
| **TestScenarioID** | TS-17 |
| **Test Type** | Functional / Negative / Business Logic / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập với 'standard_user', giỏ hàng đang trống hoàn toàn (huy hiệu giỏ hàng không hiển thị). |
| **Test Data** | User: standard_user | Giỏ hàng: 0 sản phẩm |
| **Postcondition** | Quy trình thanh toán bị chặn; người dùng không thể tạo đơn hàng ảo 0 đồng. |

##### Objective
Xác minh hệ thống e-commerce phải ngăn chặn người dùng tiến hành thanh toán khi giỏ hàng đang rỗng (0 sản phẩm, tổng tiền \$0.00).

##### Test Steps

1. Truy cập trang web và đăng nhập bằng tài khoản 'standard_user'.
2. Nhấp vào biểu tượng giỏ hàng để chuyển đến trang '/cart.html'.
3. Xác nhận danh sách giỏ hàng không có sản phẩm nào.
4. Nhấp vào nút 'Checkout'.

##### Expected Result

Nút 'Checkout' bị vô hiệu hóa (disabled), hoặc khi nhấp vào hệ thống hiển thị thông báo cảnh báo 'Your cart is empty. Please add items before checkout.' và giữ người dùng ở lại trang giỏ hàng, không cho phép chuyển tiếp sang trang thanh toán.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Lỗi logic nghiệp vụ trên SauceDemo: Hệ thống cho phép checkout giỏ hàng rỗng và hoàn tất đơn hàng \$0.00.

---

<a id="tc-folder-01_functional_testing-04_checkout"></a>
### 01_Functional_Testing/04_Checkout

#### [TC-30] Kiểm tra chuyển hướng từ giỏ hàng sang Checkout Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-30 |
| **Name** | Kiểm tra chuyển hướng từ giỏ hàng sang Checkout Bước 1 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-18 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/cart.html' và giỏ hàng có chứa ít nhất 1 sản phẩm. |
| **Test Data** | Sản phẩm trong giỏ: 1 món |
| **Postcondition** | Người dùng bước vào quy trình thanh toán. |

##### Objective
Xác minh khi người dùng nhấp 'Checkout' trên trang giỏ hàng có chứa sản phẩm, hệ thống mở đúng trang điền thông tin khách hàng Bước 1.

##### Test Steps

1. Tại trang giỏ hàng '/cart.html', nhấp vào nút 'Checkout'.
2. Quan sát sự chuyển trang của trình duyệt.

##### Expected Result

Trình duyệt điều hướng thành công đến '/checkout-step-one.html'. Tiêu đề trang hiển thị 'Checkout: Your Information' với 3 ô nhập: First Name, Last Name, Zip/Postal Code.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bắt đầu chu trình thanh toán đơn hàng.

#### [TC-31] Kiểm tra nhập thông tin khách hàng hợp lệ tại Checkout Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-31 |
| **Name** | Kiểm tra nhập thông tin khách hàng hợp lệ tại Checkout Bước 1 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-19 |
| **Test Type** | Functional / Form Submission |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: Doe | Zip/Postal Code: 10001 |
| **Postcondition** | Thông tin giao hàng được lưu tạm để tính thuế và phí tại Bước 2. |

##### Objective
Xác minh khi điền đầy đủ và hợp lệ First Name, Last Name và Zip/Postal Code, hệ thống chuyển tiếp thành công sang Bước 2.

##### Test Steps

1. Nhập 'John' vào ô 'First Name'.
2. Nhập 'Doe' vào ô 'Last Name'.
3. Nhập '10001' vào ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống xác thực form thành công và điều hướng mượt mà sang trang tổng quan đơn hàng '/checkout-step-two.html'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Luồng chuẩn (Happy Path) cho bước điền thông tin thanh toán.

#### [TC-32] Kiểm tra thông báo lỗi khi để trống trường First Name tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-32 |
| **Name** | Kiểm tra thông báo lỗi khi để trống trường First Name tại Bước 1 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Negative / Form Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: '' (để trống) | Last Name: Doe | Postal Code: 10001 |
| **Postcondition** | Người dùng vẫn ở tại Bước 1; không chuyển trang. |

##### Objective
Đảm bảo hệ thống chặn tiếp tục và cảnh báo cụ thể khi người dùng bỏ trống trường bắt buộc First Name (Kỹ thuật phân vùng tương đương: Thiếu trường bắt buộc).

##### Test Steps

1. Để trống ô 'First Name'.
2. Nhập 'Doe' vào ô 'Last Name'.
3. Nhập '10001' vào ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống chặn chuyển trang. Hộp thông báo màu đỏ hiển thị chính xác nội dung: 'Error: First Name is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực trường bắt buộc First Name.

#### [TC-33] Kiểm tra thông báo lỗi khi để trống trường Last Name tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-33 |
| **Name** | Kiểm tra thông báo lỗi khi để trống trường Last Name tại Bước 1 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Negative / Form Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: '' (để trống) | Postal Code: 10001 |
| **Postcondition** | Người dùng vẫn ở tại Bước 1. |

##### Objective
Đảm bảo hệ thống cảnh báo rõ ràng khi người dùng bỏ trống trường bắt buộc Last Name.

##### Test Steps

1. Nhập 'John' vào ô 'First Name'.
2. Để trống hoàn toàn ô 'Last Name'.
3. Nhập '10001' vào ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống chặn chuyển trang và hiển thị thông báo lỗi màu đỏ: 'Error: Last Name is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực trường bắt buộc Last Name.

#### [TC-34] Kiểm tra thông báo lỗi khi để trống trường Postal Code tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-34 |
| **Name** | Kiểm tra thông báo lỗi khi để trống trường Postal Code tại Bước 1 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Negative / Form Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: Doe | Postal Code: '' (để trống) |
| **Postcondition** | Người dùng vẫn ở tại Bước 1. |

##### Objective
Đảm bảo hệ thống cảnh báo rõ ràng khi người dùng bỏ trống trường bắt buộc Zip/Postal Code.

##### Test Steps

1. Nhập 'John' vào ô 'First Name'.
2. Nhập 'Doe' vào ô 'Last Name'.
3. Để trống hoàn toàn ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống chặn chuyển trang và hiển thị thông báo lỗi màu đỏ: 'Error: Postal Code is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực trường bắt buộc Postal Code.

#### [TC-35] Kiểm tra nhập các định dạng mã bưu chính đặc biệt (Ký tự chữ và dấu gạch nối)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-35 |
| **Name** | Kiểm tra nhập các định dạng mã bưu chính đặc biệt (Ký tự chữ và dấu gạch nối) |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-19 |
| **Test Type** | Functional / Boundary |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | Postal Code: K1A-0B1 |
| **Postcondition** | Chuyển tiếp đến Bước 2 bình thường. |

##### Objective
Xác minh ô Postal Code chấp nhận các định dạng mã bưu điện quốc tế hợp lệ có chứa chữ cái hoặc dấu gạch nối (Ví dụ định dạng Canada: K1A 0B1 hoặc UK: SW1A 1AA).

##### Test Steps

1. Nhập 'John' vào ô First Name.
2. Nhập 'Doe' vào ô Last Name.
3. Nhập 'K1A-0B1' vào ô Zip/Postal Code.
4. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống chấp nhận mã bưu điện quốc tế hợp lệ và chuyển tiếp thành công sang màn hình Bước 2.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hỗ trợ định dạng mã bưu điện quốc tế (Equivalence Partitioning: Ký tự chữ số hỗn hợp).

#### [TC-36] Kiểm tra hủy bỏ quy trình thanh toán tại Bước 1 bằng nút 'Cancel'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-36 |
| **Name** | Kiểm tra hủy bỏ quy trình thanh toán tại Bước 1 bằng nút 'Cancel' |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-21 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Quay về trang giỏ hàng; không phát sinh thay đổi dữ liệu. |

##### Objective
Xác minh khi người dùng nhấp 'Cancel' tại Bước 1, hệ thống hủy thao tác và đưa người dùng quay lại trang xem giỏ hàng.

##### Test Steps

1. Đang ở màn hình Bước 1.
2. Nhấp vào nút 'Cancel'.

##### Expected Result

Hệ thống điều hướng quay trở lại trang giỏ hàng '/cart.html'. Dữ liệu các sản phẩm trong giỏ hàng được giữ nguyên vẹn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra luồng thoát hủy bỏ (Cancel flow).

#### [TC-37] Kiểm tra hiển thị danh sách sản phẩm và tổng quan đơn hàng tại Checkout Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-37 |
| **Name** | Kiểm tra hiển thị danh sách sản phẩm và tổng quan đơn hàng tại Checkout Bước 2 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-22 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã hoàn thành Bước 1 với 2 sản phẩm trong giỏ (Backpack \$29.99 và Bike Light \$9.99); đang ở '/checkout-step-two.html'. |
| **Test Data** | 2 sản phẩm đang thanh toán |
| **Postcondition** | Người dùng nắm rõ tóm tắt mặt hàng trước khi trả tiền. |

##### Objective
Xác minh trang Checkout Bước 2 hiển thị chính xác toàn bộ các mặt hàng chuẩn bị mua kèm số lượng và đơn giá từng món.

##### Test Steps

1. Quan sát phần danh sách sản phẩm trên trang Bước 2.
2. Kiểm tra tên, số lượng (QTY=1) và đơn giá của từng sản phẩm đối chiếu với lúc chọn trong giỏ hàng.

##### Expected Result

Hiển thị đúng 2 sản phẩm: Sauce Labs Backpack (\$29.99) và Sauce Labs Bike Light (\$9.99). Không có sản phẩm nào bị sai giá hay thiếu thông tin.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực tính toàn vẹn danh sách đơn hàng.

#### [TC-38] Kiểm tra hiển thị thông tin thanh toán và thông tin giao hàng tại Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-38 |
| **Name** | Kiểm tra hiển thị thông tin thanh toán và thông tin giao hàng tại Bước 2 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-22 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-two.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Các thông tin tĩnh hiển thị đầy đủ, minh bạch. |

##### Objective
Xác minh các khối thông tin cố định Payment Information và Shipping Information hiển thị chính xác theo quy định của hệ thống.

##### Test Steps

1. Cuộn trang đến phần 'Payment Information'.
2. Kiểm tra mã thẻ hiển thị.
3. Cuộn đến phần 'Shipping Information'.
4. Kiểm tra phương thức vận chuyển hiển thị.

##### Expected Result

Payment Information hiển thị chuẩn xác mã: 'SauceCard #31437'. Shipping Information hiển thị chuẩn xác: 'Free Pony Express Delivery!'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hiển thị văn bản tĩnh và định dạng thẻ thanh toán.

#### [TC-39] Kiểm tra tính toán tài chính: Tổng tiền hàng, Thuế 8% và Tổng thanh toán tại Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-39 |
| **Name** | Kiểm tra tính toán tài chính: Tổng tiền hàng, Thuế 8% và Tổng thanh toán tại Bước 2 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-23 |
| **Test Type** | Functional / Calculation & Boundary |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang Bước 2 với 2 sản phẩm: Sauce Labs Backpack (\$29.99) và Sauce Labs Bike Light (\$9.99). |
| **Test Data** | Item 1: \$29.99 | Item 2: \$9.99 | Kỳ vọng Item total: \$39.98 | Thuế 8%: \$39.98 * 0.08 = \$3.20 | Kỳ vọng Total: \$43.18 |
| **Postcondition** | Số liệu tài chính hoàn toàn minh bạch và chuẩn xác từng xu. |

##### Objective
Xác minh công thức tính toán tài chính: Item total = Tổng giá các sản phẩm; Tax = 8% của Item total (làm tròn 2 chữ số thập phân); Total = Item total + Tax.

##### Test Steps

1. Đọc giá trị tại dòng 'Item total:'.
2. Đọc giá trị tại dòng 'Tax:'.
3. Đọc giá trị tại dòng 'Total:'.
4. So sánh các giá trị thực tế với công thức tính toán toán học chuẩn.

##### Expected Result

Item total hiển thị chính xác 'Item total: \$39.98'. Thuế hiển thị chính xác 'Tax: \$3.20' (làm tròn từ 3.1984 lên 3.20). Tổng cộng hiển thị chính xác 'Total: \$43.18'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử cốt lõi cho tính toán tài chính và làm tròn số thập phân (BVA & Financial Calculation).

#### [TC-40] Kiểm tra hủy bỏ thanh toán tại Bước 2 bằng nút 'Cancel'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-40 |
| **Name** | Kiểm tra hủy bỏ thanh toán tại Bước 2 bằng nút 'Cancel' |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-24 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-two.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Quay về trang danh mục mà không làm mất giỏ hàng. |

##### Objective
Xác minh khi nhấp 'Cancel' tại Bước 2, người dùng được đưa quay trở về trang danh mục sản phẩm và giỏ hàng vẫn giữ nguyên.

##### Test Steps

1. Tại trang Bước 2, nhấp vào nút 'Cancel'.

##### Expected Result

Hệ thống điều hướng người dùng quay lại trang danh mục sản phẩm '/inventory.html'. Giỏ hàng vẫn duy trì nguyên vẹn các sản phẩm đã chọn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hành vi nút Cancel tại Bước 2.

#### [TC-41] Kiểm tra hoàn tất đặt hàng thành công tại Checkout Bước 3

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-41 |
| **Name** | Kiểm tra hoàn tất đặt hàng thành công tại Checkout Bước 3 |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 3 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-11 |
| **TestScenarioID** | TS-25 |
| **Test Type** | Functional / Transaction |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-two.html' với thông tin tài chính hợp lệ. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Đơn hàng hoàn tất; giỏ hàng giải phóng sạch sẽ. |

##### Objective
Xác minh khi người dùng nhấp 'Finish' tại Bước 2, hệ thống hoàn tất đơn hàng, chuyển sang Bước 3, hiển thị thông điệp cảm ơn và tự động xóa sạch giỏ hàng.

##### Test Steps

1. Tại trang Bước 2, nhấp vào nút 'Finish'.
2. Kiểm tra URL trang web chuyển sang '/checkout-complete.html'.
3. Kiểm tra thông điệp hoàn tất hiển thị trên trang.
4. Kiểm tra biểu tượng giỏ hàng ở góc trên bên phải.

##### Expected Result

Chuyển hướng thành công đến '/checkout-complete.html'. Hiển thị tiêu đề lớn 'Thank you for your order!' và thông điệp 'Your order has been dispatched...'. Huy hiệu số lượng trên giỏ hàng biến mất hoàn toàn (giỏ hàng đã được làm sạch sau mua hàng).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử then chốt cho giao dịch mua hàng thành công.

#### [TC-42] Kiểm tra nút 'Back Home' đưa người dùng quay về trang chủ sau khi hoàn tất mua hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-42 |
| **Name** | Kiểm tra nút 'Back Home' đưa người dùng quay về trang chủ sau khi hoàn tất mua hàng |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Step 3 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-11 |
| **TestScenarioID** | TS-26 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang xác nhận hoàn tất đơn hàng '/checkout-complete.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng sẵn sàng cho một chu trình mua hàng mới. |

##### Objective
Xác minh nút 'Back Home' tại trang hoàn tất đơn hàng đưa người dùng trở về trang danh mục và giỏ hàng vẫn ở trạng thái trống.

##### Test Steps

1. Tại trang hoàn tất đơn hàng, nhấp vào nút 'Back Home'.

##### Expected Result

Hệ thống điều hướng về trang danh mục sản phẩm '/inventory.html'. Giỏ hàng rỗng, tất cả các nút sản phẩm hiển thị 'Add to cart'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kết thúc chu trình đặt hàng.

#### [TC-43] Kiểm tra nhập liệu và lưu trữ giá trị tại trường Last Name trong form Checkout Step 1 với problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-43 |
| **Name** | Kiểm tra nhập liệu và lưu trữ giá trị tại trường Last Name trong form Checkout Step 1 với problem_user |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Workflow / Form Handling |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-19 |
| **Test Type** | Functional / Form Validation / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'problem_user'; giỏ hàng có ít nhất 1 sản phẩm; đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: 'Alex' | Last Name: 'Smith' | Postal Code: '90001' |
| **Postcondition** | Chuyển sang màn hình xác nhận đơn hàng Bước 2. |

##### Objective
Xác minh trường 'Last Name' nhận đúng ký tự người dùng gõ vào và cho phép chuyển tiếp sang Bước 2.

##### Test Steps

1. Đăng nhập 'problem_user' và thêm 1 sản phẩm vào giỏ.
2. Đi đến '/cart.html' và nhấp 'Checkout'.
3. Nhập 'Alex' vào ô 'First Name'.
4. Nhập 'Smith' vào ô 'Last Name'.
5. Nhập '90001' vào ô 'Postal Code'.
6. Nhấp vào nút 'Continue'.

##### Expected Result

Ô 'Last Name' hiển thị đầy đủ chuỗi 'Smith'. Khi nhấp 'Continue', hệ thống lưu trữ thông tin và điều hướng thành công đến '/checkout-step-two.html'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug Critical cố tình của SauceDemo: Trường Last Name bị khóa hoặc tự động ghi đè, hệ thống luôn báo lỗi 'Error: Last Name is required', chặn đứng toàn bộ luồng thanh toán của problem_user.

#### [TC-44] Kiểm tra hoàn tất đơn hàng tại Checkout Step 2 không bị chặn bởi lỗi Runtime khi đăng nhập bằng error_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-44 |
| **Name** | Kiểm tra hoàn tất đơn hàng tại Checkout Step 2 không bị chặn bởi lỗi Runtime khi đăng nhập bằng error_user |
| **Folder** | 01_Functional_Testing/04_Checkout |
| **Component** | Checkout Workflow / Transaction |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Blocker |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-24 |
| **Test Type** | Functional / Transaction Integrity / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'error_user'; đã điền xong Bước 1; đang ở '/checkout-step-two.html'. |
| **Test Data** | Username: error_user | Sản phẩm trong giỏ: 1 món bất kỳ |
| **Postcondition** | Đơn hàng được ghi nhận, giỏ hàng được làm mới. |

##### Objective
Xác minh nút 'Finish' tại trang tổng quan đơn hàng xử lý thành công giao dịch và đưa người dùng đến trang hoàn tất mà không gặp lỗi JavaScript.

##### Test Steps

1. Đăng nhập bằng 'error_user' và thêm 1 sản phẩm vào giỏ.
2. Đi qua Checkout Bước 1 với thông tin hợp lệ.
3. Tại trang Checkout Bước 2, nhấp vào nút 'Finish'.

##### Expected Result

Hệ thống tiếp nhận đơn hàng thành công và chuyển hướng đến '/checkout-complete.html' kèm thông báo 'Thank you for your order!'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug Blocker cố tình của SauceDemo: Nhấp nút Finish văng lỗi runtime exception không bắt được, chặn người dùng hoàn tất giao dịch.

---

<a id="tc-folder-01_functional_testing-05_sidebar_navigation"></a>
### 01_Functional_Testing/05_Sidebar_Navigation

#### [TC-45] Kiểm tra mở và đóng menu Sidebar

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-45 |
| **Name** | Kiểm tra mở và đóng menu Sidebar |
| **Folder** | 01_Functional_Testing/05_Sidebar_Navigation |
| **Component** | Sidebar Navigation |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / UI Animation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang đăng nhập tại trang '/inventory.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Menu đóng lại; người dùng trở lại màn hình chính. |

##### Objective
Xác minh menu Sidebar có thể mở trượt mượt mà khi nhấp vào biểu tượng hamburger và đóng lại khi nhấp vào nút biểu tượng 'X'.

##### Test Steps

1. Nhấp vào biểu tượng 3 dấu gạch ngang ở góc trên bên trái.
2. Xác nhận menu trượt hiển thị đủ 4 mục: 'All Items', 'About', 'Logout', 'Reset App State'.
3. Nhấp vào biểu tượng dấu 'X' (Close menu) ở góc trên bên phải menu trượt.

##### Expected Result

Menu trượt mở ra đầy đủ không bị che khuất và đóng lại mượt mà khi bấm 'X'. Giao diện trang chính hoạt động bình thường.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra UI component trượt (Slide-out navigation drawer).

#### [TC-46] Kiểm tra mục 'All Items' trong Sidebar đưa người dùng về trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-46 |
| **Name** | Kiểm tra mục 'All Items' trong Sidebar đưa người dùng về trang danh mục |
| **Folder** | 01_Functional_Testing/05_Sidebar_Navigation |
| **Component** | Sidebar Navigation |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang giỏ hàng '/cart.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng quay về trang danh mục sản phẩm. |

##### Objective
Xác minh khi người dùng đang ở bất kỳ trang nào (ví dụ trang giỏ hàng), nhấp vào 'All Items' trong Sidebar sẽ điều hướng về trang danh mục sản phẩm.

##### Test Steps

1. Đang ở trang '/cart.html'.
2. Mở Sidebar menu.
3. Nhấp vào liên kết 'All Items'.

##### Expected Result

Hệ thống điều hướng về trang danh mục '/inventory.html' và hiển thị đầy đủ danh sách các mặt hàng.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra điều hướng nội bộ từ Sidebar.

#### [TC-47] Kiểm tra mục 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-47 |
| **Name** | Kiểm tra mục 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs |
| **Folder** | 01_Functional_Testing/05_Sidebar_Navigation |
| **Component** | Sidebar Navigation |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / External Link |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang đăng nhập và mở menu Sidebar. |
| **Test Data** | URL đích: https://saucelabs.com/ |
| **Postcondition** | Người dùng tiếp cận được trang giới thiệu bên ngoài. |

##### Objective
Xác minh liên kết 'About' trong Sidebar trỏ đúng địa chỉ trang chủ chính thức của Sauce Labs (https://saucelabs.com/).

##### Test Steps

1. Mở menu Sidebar.
2. Nhấp vào mục 'About'.
3. Kiểm tra URL đích trên thanh địa chỉ của trình duyệt.

##### Expected Result

Trình duyệt điều hướng thành công đến website chính thức 'https://saucelabs.com/' mà không gặp lỗi kết nối.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra liên kết ngoại tuyến (Outbound link).

#### [TC-48] Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng và xóa sạch giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-48 |
| **Name** | Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng và xóa sạch giỏ hàng |
| **Folder** | 01_Functional_Testing/05_Sidebar_Navigation |
| **Component** | App State / Local Storage |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / State Reset |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã thêm 2 sản phẩm vào giỏ hàng (huy hiệu hiển thị '2'); đang ở trang '/inventory.html'. |
| **Test Data** | 2 sản phẩm đang có trong giỏ hàng |
| **Postcondition** | Trạng thái ứng dụng được khôi phục về mặc định như lúc mới đăng nhập. |

##### Objective
Xác minh khi người dùng kích hoạt 'Reset App State', toàn bộ sản phẩm trong giỏ hàng bị xóa sạch, huy hiệu giỏ hàng biến mất và các nút 'Remove' quay về 'Add to cart'.

##### Test Steps

1. Mở menu Sidebar.
2. Nhấp vào mục 'Reset App State'.
3. Đóng menu Sidebar và quan sát giao diện trang danh mục.

##### Expected Result

Huy hiệu số lượng giỏ hàng biến mất hoàn toàn. Các nút 'Remove' của các sản phẩm đã chọn trước đó chuyển lại thành 'Add to cart'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra khả năng reset trạng thái phiên kiểm thử.

#### [TC-49] Kiểm tra tính hợp lệ của liên kết điều hướng 'About' trong Sidebar đối với problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-49 |
| **Name** | Kiểm tra tính hợp lệ của liên kết điều hướng 'About' trong Sidebar đối với problem_user |
| **Folder** | 01_Functional_Testing/05_Sidebar_Navigation |
| **Component** | Sidebar Navigation / Broken Link |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Navigation / Broken Link / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'problem_user'. |
| **Test Data** | Username: problem_user |
| **Postcondition** | Trang web đích tải thành công không bị lỗi kết nối. |

##### Objective
Xác minh liên kết 'About' trong menu trượt điều hướng người dùng đến đúng trang giới thiệu chính thức của Sauce Labs.

##### Test Steps

1. Đăng nhập bằng 'problem_user' / 'secret_sauce'.
2. Nhấp vào biểu tượng 3 dấu gạch ngang (hamburger menu) để mở Sidebar.
3. Nhấp vào mục 'About' trong danh sách menu.

##### Expected Result

Trình duyệt chuyển hướng thành công đến trang chủ chính thức 'https://saucelabs.com/' với mã trạng thái HTTP 200 OK.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Đường dẫn About bị gắn sai URL dẫn đến trang lỗi 404 Not Found.

---

<a id="tc-folder-01_functional_testing-06_end_to_end"></a>
### 01_Functional_Testing/06_End_to_End

#### [TC-50] Kiểm tra toàn diện quy trình mua sắm thương mại điện tử End-to-End từ đăng nhập đến nhận biên lai

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-50 |
| **Name** | Kiểm tra toàn diện quy trình mua sắm thương mại điện tử End-to-End từ đăng nhập đến nhận biên lai |
| **Folder** | 01_Functional_Testing/06_End_to_End |
| **Component** | End-to-End Workflow |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-13 |
| **TestScenarioID** | TS-28 |
| **Test Type** | Functional / End-to-End System Integration |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt sạch không có cookie phiên; tài khoản 'standard_user' hợp lệ. |
| **Test Data** | User: standard_user | Sản phẩm: Sauce Labs Backpack (\$29.99) & Sauce Labs Onesie (\$7.99) | Khách: Khong Duc Anh, Post: 100000 |
| **Postcondition** | Đơn hàng hoàn tất, phiên làm việc đóng an toàn. |

##### Objective
Xác minh luồng trải nghiệm khách hàng xuyên suốt: Đăng nhập -> Sắp xếp lọc hàng -> Thêm 2 sản phẩm -> Kiểm tra giỏ -> Điền thông tin giao hàng -> Xác thực hóa đơn thanh toán -> Nhận biên lai hoàn tất và Đăng xuất.

##### Test Steps

1. Đăng nhập bằng tài khoản 'standard_user' / 'secret_sauce'.
2. Tại trang danh mục, chọn sắp xếp theo 'Price (low to high)'.
3. Nhấp 'Add to cart' tại sản phẩm 'Sauce Labs Onesie' (\$7.99).
4. Nhấp 'Add to cart' tại sản phẩm 'Sauce Labs Backpack' (\$29.99).
5. Nhấp vào biểu tượng giỏ hàng để chuyển sang '/cart.html', đối chiếu đủ 2 sản phẩm.
6. Nhấp nút 'Checkout' để vào Bước 1.
7. Điền First Name: 'Khong', Last Name: 'Duc Anh', Zip: '100000' rồi nhấn 'Continue'.
8. Tại Bước 2, kiểm tra: Item total = \$37.98, Tax (8%) = \$3.04, Total = \$41.02.
9. Nhấp nút 'Finish' để hoàn tất đơn hàng.
10. Xác nhận màn hình hiển thị 'Thank you for your order!'.
11. Mở menu Sidebar và nhấp 'Logout' để kết thúc phiên an toàn.

##### Expected Result

Toàn bộ chu trình mua hàng thực hiện trơn tru từ đầu đến cuối không phát sinh bất kỳ lỗi gián đoạn nào. Số liệu tính toán khớp từng xu, giỏ hàng được làm sạch và người dùng đăng xuất an toàn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử tích hợp toàn diện quan trọng nhất của hệ thống e-commerce.

---

<a id="tc-folder-02_api_testing"></a>
### 02_API_Testing

#### [TC-51] Kiểm tra API POST /api/v1/auth/login xác thực đăng nhập thành công với tài khoản hợp lệ

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-51 |
| **Name** | Kiểm tra API POST /api/v1/auth/login xác thực đăng nhập thành công với tài khoản hợp lệ |
| **Folder** | 02_API_Testing |
| **Component** | Authentication API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Integration Testing |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Máy chủ API hoạt động bình thường, endpoint '/api/v1/auth/login' sẵn sàng nhận request. |
| **Test Data** | Headers: {'Content-Type': 'application/json'} | Body: {'username': 'standard_user', 'password': 'secret_sauce'} |
| **Postcondition** | Phiên làm việc được khởi tạo trên backend token store. |

##### Objective
Xác minh API xác thực trả về mã trạng thái HTTP 200 OK kèm token xác thực JWT và thông tin phiên làm việc khi gửi credentials hợp lệ.

##### Test Steps

1. Gửi HTTP POST request đến endpoint '/api/v1/auth/login'.
2. Kiểm tra mã trạng thái HTTP response status code.
3. Kiểm tra JSON response body chứa trường 'accessToken', 'tokenType': 'Bearer', và 'expiresIn'.
4. Xác thực response header chứa 'Set-Cookie' với cờ Secure và HttpOnly.

##### Expected Result

Mã phản hồi HTTP 200 OK. JSON Response trả về cấu trúc hợp lệ chứa access token và thời hạn phiên; không để lộ thông tin nhạy cảm của mật khẩu trong body.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked do hệ thống frontend SauceDemo là Single Page App thuần client-side, không expose public REST API endpoints.

#### [TC-52] Kiểm tra API POST /api/v1/auth/login xử lý từ chối đăng nhập đối với tài khoản bị khóa (HTTP 423 Locked)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-52 |
| **Name** | Kiểm tra API POST /api/v1/auth/login xử lý từ chối đăng nhập đối với tài khoản bị khóa (HTTP 423 Locked) |
| **Folder** | 02_API_Testing |
| **Component** | Authentication API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Negative Testing |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Tài khoản 'locked_out_user' có cờ trạng thái 'is_locked = true' trong CSDL. |
| **Test Data** | Headers: {'Content-Type': 'application/json'} | Body: {'username': 'locked_out_user', 'password': 'secret_sauce'} |
| **Postcondition** | Yêu cầu bị từ chối; không có phiên làm việc nào được cấp phát. |

##### Objective
Xác minh API phản hồi mã lỗi HTTP 423 Locked hoặc 403 Forbidden và thông điệp lỗi rõ ràng khi người dùng cố gắng xác thực với tài khoản bị khóa.

##### Test Steps

1. Gửi HTTP POST request đến endpoint '/api/v1/auth/login'.
2. Kiểm tra mã trạng thái HTTP response status code.
3. Kiểm tra mã lỗi nghiệp vụ trong body: 'error_code': 'ACCOUNT_LOCKED'.
4. Kiểm tra thông điệp mô tả: 'message': 'Sorry, this user has been locked out.'.

##### Expected Result

HTTP Status 423 Locked (hoặc 403 Forbidden). Body chứa mã lỗi 'ACCOUNT_LOCKED' và không sinh ra bất kỳ token xác thực nào.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked do kiến trúc client-side SPA.

#### [TC-53] Kiểm tra API GET /api/v1/products lấy danh mục sản phẩm và kiểm tra Schema JSON

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-53 |
| **Name** | Kiểm tra API GET /api/v1/products lấy danh mục sản phẩm và kiểm tra Schema JSON |
| **Folder** | 02_API_Testing |
| **Component** | Catalog API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Schema Validation |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Header request chứa Bearer Token hợp lệ của 'standard_user'. |
| **Test Data** | Endpoint: GET /api/v1/products | Headers: {'Authorization': 'Bearer <token>'} |
| **Postcondition** | Dữ liệu trả về sẵn sàng cho client render. |

##### Objective
Xác minh endpoint trả về danh sách đầy đủ 6 sản phẩm kèm đúng kiểu dữ liệu (Schema Validation: id, name, price, stock, image_url).

##### Test Steps

1. Gửi HTTP GET request đến '/api/v1/products'.
2. Kiểm tra HTTP Status Code là 200 OK.
3. Kiểm tra mảng dữ liệu 'data' chứa chính xác 6 đối tượng sản phẩm.
4. Xác thực kiểu dữ liệu từng trường: 'id' (integer), 'name' (string), 'price' (float > 0), 'image_url' (url string hợp lệ).

##### Expected Result

HTTP Status 200 OK. JSON response tuân thủ 100% JSON Schema định nghĩa, mảng chứa đúng 6 sản phẩm với giá niêm yết chính xác.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked do kiến trúc client-side SPA.

#### [TC-54] Kiểm tra API POST /api/v1/cart/items thêm sản phẩm vào giỏ hàng và cập nhật tổng số lượng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-54 |
| **Name** | Kiểm tra API POST /api/v1/cart/items thêm sản phẩm vào giỏ hàng và cập nhật tổng số lượng |
| **Folder** | 02_API_Testing |
| **Component** | Cart API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Functional Testing |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Người dùng có giỏ hàng đang trống. |
| **Test Data** | Headers: {'Authorization': 'Bearer <token>'} | Body: {'product_id': 1, 'quantity': 1} |
| **Postcondition** | Trạng thái giỏ hàng được cập nhật trong Redis / Database session. |

##### Objective
Xác minh endpoint xử lý thêm mặt hàng vào giỏ và trả về tổng số lượng cập nhật tức thì.

##### Test Steps

1. Gửi POST request đến '/api/v1/cart/items' với product_id=1, quantity=1.
2. Kiểm tra HTTP Status Code 201 Created.
3. Kiểm tra response body chứa 'cart_items_count': 1 và 'total_amount': 29.99.

##### Expected Result

HTTP Status 201 Created. Giỏ hàng trên server ghi nhận sản phẩm mới và cập nhật bộ đếm giỏ hàng thành 1.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked do kiến trúc client-side SPA.

#### [TC-55] Kiểm tra API POST /api/v1/checkout/orders hoàn tất đơn hàng và tính toán tài chính tự động

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-55 |
| **Name** | Kiểm tra API POST /api/v1/checkout/orders hoàn tất đơn hàng và tính toán tài chính tự động |
| **Folder** | 02_API_Testing |
| **Component** | Checkout API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Transaction & Calculation |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Giỏ hàng có sản phẩm, người dùng đã hoàn tất thông tin giao hàng. |
| **Test Data** | Headers: {'Authorization': 'Bearer <token>'} | Body: {'firstName': 'John', 'lastName': 'Doe', 'postalCode': '10001', 'items': [{'id': 4, 'qty': 1, 'price': 29.99}]} |
| **Postcondition** | Đơn hàng được lưu vào cơ sở dữ liệu backend. |

##### Objective
Xác minh endpoint tiếp nhận đơn hàng, tự động tính thuế 8%, tạo mã đơn hàng duy nhất và phản hồi mã 201 Created.

##### Test Steps

1. Gửi POST request đến '/api/v1/checkout/orders'.
2. Kiểm tra HTTP Status Code là 201 Created.
3. Kiểm tra trường 'orderId' không rỗng và có định dạng UUID/Mã đơn chuẩn.
4. Kiểm tra 'itemTotal': 29.99, 'tax': 2.40 (8%), 'grandTotal': 32.39.

##### Expected Result

HTTP Status 201 Created. Tạo đơn hàng thành công, số liệu tài chính tính toán chuẩn xác, mã đơn hàng được sinh ra duy nhất.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked do kiến trúc client-side SPA.

---

<a id="tc-folder-03_database_sql_testing"></a>
### 03_Database_SQL_Testing

#### [TC-56] Kiểm tra CSDL: Xác minh mật khẩu người dùng được băm an toàn trong bảng users

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-56 |
| **Name** | Kiểm tra CSDL: Xác minh mật khẩu người dùng được băm an toàn trong bảng users |
| **Folder** | 03_Database_SQL_Testing |
| **Component** | Users Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Security Verification |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có quyền kết nối và truy vấn CSDL quản trị hệ thống. |
| **Test Data** | SQL Query: SELECT username, password_hash, salt FROM users WHERE username = 'standard_user'; |
| **Postcondition** | Đảm bảo tuân thủ tiêu chuẩn an toàn bảo mật dữ liệu người dùng (OWASP / GDPR). |

##### Objective
Xác minh hệ thống không bao giờ lưu trữ mật khẩu dưới dạng văn bản thuần (Plaintext), mật khẩu phải được băm an toàn bằng thuật toán chuẩn (BCrypt / Argon2 / SHA-256).

##### Test Steps

1. Mở kết nối Database Client (DBeaver / MySQL Workbench).
2. Thực thi câu lệnh SQL truy vấn thông tin người dùng 'standard_user'.
3. Kiểm tra giá trị cột 'password_hash'.
4. Xác nhận giá trị không trùng với chuỗi 'secret_sauce' và có độ dài tối thiểu 60 ký tự (chuẩn hash bcrypt).

##### Expected Result

Mật khẩu được lưu trữ dưới dạng chuỗi băm không thể dịch ngược (ví dụ \$2b\$12\$e8...), không xuất hiện chuỗi 'secret_sauce' trong bất kỳ trường dữ liệu nào.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked do SauceDemo không cung cấp quyền kết nối direct database.

#### [TC-57] Kiểm tra CSDL: Xác minh trạng thái khóa tài khoản trong bảng users đối với locked_out_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-57 |
| **Name** | Kiểm tra CSDL: Xác minh trạng thái khóa tài khoản trong bảng users đối với locked_out_user |
| **Folder** | 03_Database_SQL_Testing |
| **Component** | Users Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Data Consistency |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có quyền truy vấn bảng 'users'. |
| **Test Data** | SQL Query: SELECT username, is_locked, account_status FROM users WHERE username = 'locked_out_user'; |
| **Postcondition** | Dữ liệu trạng thái người dùng đồng bộ. |

##### Objective
Xác minh bản ghi của 'locked_out_user' có cờ trạng thái 'is_locked = 1' hoặc 'status = LOCKED' trong cơ sở dữ liệu.

##### Test Steps

1. Kết nối vào CSDL.
2. Thực thi câu lệnh truy vấn trạng thái tài khoản 'locked_out_user'.
3. Kiểm tra giá trị trường 'is_locked' bằng 1 (True).
4. Đối chiếu với 'standard_user' có trường 'is_locked' bằng 0 (False).

##### Expected Result

Cơ sở dữ liệu lưu trữ chính xác trạng thái khóa của tài khoản: is_locked = 1, giải thích nguyên nhân hệ thống từ chối đăng nhập trên giao diện.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked.

#### [TC-58] Kiểm tra CSDL: Xác minh tính nhất quán của bảng danh mục sản phẩm và giá niêm yết

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-58 |
| **Name** | Kiểm tra CSDL: Xác minh tính nhất quán của bảng danh mục sản phẩm và giá niêm yết |
| **Folder** | 03_Database_SQL_Testing |
| **Component** | Product Catalog Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Data Consistency |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có quyền truy vấn bảng 'products'. |
| **Test Data** | SQL Query: SELECT product_id, name, price, stock_quantity FROM products WHERE is_active = 1 ORDER BY price ASC; |
| **Postcondition** | Dữ liệu danh mục đạt chuẩn toàn vẹn. |

##### Objective
Xác minh bảng 'products' chứa đầy đủ 6 sản phẩm với giá bán chính xác và số lượng tồn kho (stock) lớn hơn 0.

##### Test Steps

1. Thực thi câu lệnh: SELECT COUNT(*) FROM products WHERE is_active = 1;
2. Xác nhận COUNT(*) bằng 6.
3. Thực thi câu lệnh: SELECT name, price FROM products ORDER BY price ASC;
4. Đối chiếu mức giá thấp nhất là 7.99 (Onesie) và cao nhất là 49.99 (Fleece Jacket).

##### Expected Result

Đủ 6 sản phẩm, giá tiền khớp 100% với giao diện UI (\$7.99, \$9.99, \$15.99, \$15.99, \$29.99, \$49.99).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked.

#### [TC-59] Kiểm tra CSDL: Xác minh ghi nhận bản ghi đơn hàng mới vào bảng orders sau khi thanh toán thành công

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-59 |
| **Name** | Kiểm tra CSDL: Xác minh ghi nhận bản ghi đơn hàng mới vào bảng orders sau khi thanh toán thành công |
| **Folder** | 03_Database_SQL_Testing |
| **Component** | Orders Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Transaction Verification |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Vừa thực hiện thành công một đơn hàng trên UI bằng 'standard_user'. |
| **Test Data** | SQL Query: SELECT order_id, user_id, item_total, tax_amount, grand_total, order_status FROM orders WHERE user_id = 'standard_user' ORDER BY created_at DESC LIMIT 1; |
| **Postcondition** | Giao dịch thanh toán được lưu trữ bền vững (ACID compliance). |

##### Objective
Xác minh sau khi người dùng nhấn 'Finish' trên giao diện, một bản ghi mới được tạo trong bảng 'orders' với đầy đủ thông tin thanh toán và thuế.

##### Test Steps

1. Thực hiện thanh toán đơn hàng trên UI.
2. Mở SQL client và thực thi truy vấn lấy đơn hàng mới nhất của 'standard_user'.
3. Đối chiếu các trường 'item_total', 'tax_amount', 'grand_total' với màn hình Checkout Step 2.
4. Kiểm tra trường 'order_status' có giá trị 'COMPLETED' hoặc 'DISPATCHED'.

##### Expected Result

Bản ghi đơn hàng được tạo thành công, dữ liệu tài chính khớp chính xác từng xu, trạng thái đơn hàng được cập nhật hợp lệ.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked.

#### [TC-60] Kiểm tra CSDL: Xác minh chi tiết các mặt hàng trong bảng order_items liên kết đúng với đơn hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-60 |
| **Name** | Kiểm tra CSDL: Xác minh chi tiết các mặt hàng trong bảng order_items liên kết đúng với đơn hàng |
| **Folder** | 03_Database_SQL_Testing |
| **Component** | Order Items Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Relational Integrity |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có mã 'order_id' vừa tạo từ câu lệnh TC-59. |
| **Test Data** | SQL Query: SELECT oi.item_id, oi.product_id, p.name, oi.unit_price, oi.quantity FROM order_items oi JOIN products p ON oi.product_id = p.product_id WHERE oi.order_id = :latest_order_id; |
| **Postcondition** | Toàn vẹn quan hệ giữa bảng đơn hàng và bảng chi tiết sản phẩm. |

##### Objective
Xác minh bảng chi tiết 'order_items' lưu đúng từng sản phẩm, số lượng và đơn giá theo khóa ngoại 'order_id'.

##### Test Steps

1. Lấy mã order_id từ đơn hàng mới nhất.
2. Thực thi câu lệnh truy vấn liên kết bảng order_items với products.
3. Kiểm tra số lượng dòng sản phẩm trả về khớp với số mặt hàng khách đã chọn.
4. Kiểm tra đơn giá từng món bằng với giá niêm yết tại thời điểm mua.

##### Expected Result

Toàn bộ các mặt hàng được liên kết chuẩn xác qua khóa ngoại (Foreign Key constraint), không có dữ liệu mồ côi (orphan records).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi ở Phase 2: Blocked.

---

<a id="tc-folder-04_non_functional_testing-performance_testing"></a>
### 04_Non_Functional_Testing/Performance_Testing

#### [TC-61] Kiểm tra phi chức năng: Đo lường thời gian phản hồi (Response Time SLA < 2.0s) khi tải trang danh mục sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-61 |
| **Name** | Kiểm tra phi chức năng: Đo lường thời gian phản hồi (Response Time SLA < 2.0s) khi tải trang danh mục sản phẩm |
| **Folder** | 04_Non_Functional_Testing/Performance_Testing |
| **Component** | Performance / Response Time |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Performance Testing |
| **Execution Environment** | Chrome Desktop DevTools / Lighthouse Audit / macOS Sonoma |
| **Precondition** | Trình duyệt sạch, không có cache (Disable cache trong DevTools), kết nối mạng ổn định (Fast 3G / 4G / Broadband). |
| **Test Data** | Tài khoản: standard_user | Tiêu chuẩn: Response Time < 2000ms |
| **Postcondition** | Hệ thống đáp ứng tiêu chuẩn hiệu năng trải nghiệm người dùng. |

##### Objective
Xác minh hiệu năng tải trang danh mục sản phẩm '/inventory.html' đáp ứng tiêu chuẩn thời gian phản hồi dưới 2.0 giây trong điều kiện mạng tiêu chuẩn.

##### Test Steps

1. Mở Chrome DevTools -> tab 'Network', tích chọn 'Disable cache'.
2. Mở tab 'Lighthouse' hoặc 'Performance'.
3. Đăng nhập bằng 'standard_user' / 'secret_sauce'.
4. Ghi nhận thời gian DOMContentLoaded, Time to First Byte (TTFB), và Fully Loaded Time của trang '/inventory.html'.

##### Expected Result

Thời gian tải toàn bộ trang danh mục dưới 2.0 giây. Điểm hiệu năng Lighthouse đạt trên 90 điểm. Các tài nguyên tĩnh (static assets) tải nhanh chóng không bị nghẽn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử hiệu năng phi chức năng đo lường chỉ số Web Vitals (FCP, LCP, CLS).

#### [TC-62] Kiểm tra phi chức năng: Phát hiện vi phạm SLA thời gian phản hồi nghiêm trọng (>5.0s) đối với performance_glitch_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-62 |
| **Name** | Kiểm tra phi chức năng: Phát hiện vi phạm SLA thời gian phản hồi nghiêm trọng (>5.0s) đối với performance_glitch_user |
| **Folder** | 04_Non_Functional_Testing/Performance_Testing |
| **Component** | Performance / Latency Glitch |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Performance SLA / Response Time / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt chưa có phiên làm việc; kết nối mạng ổn định (High-speed Broadband). |
| **Test Data** | Username: performance_glitch_user | Password: secret_sauce |
| **Postcondition** | Người dùng chuyển trang nhanh chóng. |

##### Objective
Xác minh thời gian từ lúc nhấn 'Login' đến khi trang danh mục hiển thị đầy đủ phải đáp ứng tiêu chuẩn hiệu năng phần mềm (Response Time SLA < 2 giây), bẫy lỗi nghẽn mạng nhân tạo.

##### Test Steps

1. Mở DevTools Network Tab.
2. Nhập 'performance_glitch_user' và 'secret_sauce'.
3. Nhấp 'Login' và đo lường thời gian từ lúc gửi yêu cầu đến khi sự kiện DOMContentLoaded / trang '/inventory.html' hoàn tất tải.

##### Expected Result

Trang danh mục tải xong hoàn toàn trong thời gian dưới 2.0 giây, mang lại trải nghiệm mượt mà không có độ trễ bất thường.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: performance_glitch_user bị chèn độ trễ nhân tạo 5 giây (5000ms delay), vi phạm nghiêm trọng SLA trải nghiệm người dùng.

---

<a id="tc-folder-04_non_functional_testing-security_testing"></a>
### 04_Non_Functional_Testing/Security_Testing

#### [TC-63] Kiểm tra phi chức năng: Kiểm tra các cờ bảo mật của Cookie phiên làm việc (Secure, HttpOnly, SameSite)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-63 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra các cờ bảo mật của Cookie phiên làm việc (Secure, HttpOnly, SameSite) |
| **Folder** | 04_Non_Functional_Testing/Security_Testing |
| **Component** | Security / Session Cookie |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-16 |
| **TestScenarioID** | TS-33 |
| **Test Type** | Security Testing |
| **Execution Environment** | Chrome Desktop DevTools / Application Tab |
| **Precondition** | Người dùng đăng nhập thành công vào hệ thống. |
| **Test Data** | Cookie: session-username | Kỳ vọng cờ: Secure=True, HttpOnly=True, SameSite=Lax/Strict |
| **Postcondition** | Phiên làm việc được bảo vệ chống lộ lọt cookie qua các cuộc tấn công XSS. |

##### Objective
Xác minh các cookie quản lý phiên làm việc như 'session-username' được thiết lập đầy đủ các thuộc tính bảo mật để chống tấn công đánh cắp cookie (Session Hijacking / XSS).

##### Test Steps

1. Đăng nhập bằng 'standard_user' / 'secret_sauce'.
2. Mở Chrome DevTools -> tab 'Application' -> mục 'Cookies' -> 'https://www.saucedemo.com'.
3. Kiểm tra cột 'HttpOnly': xem có dấu tích hay không.
4. Kiểm tra cột 'Secure': xem có được bật hay không.
5. Mở tab 'Console' và gõ lệnh: document.cookie để kiểm tra xem mã JavaScript có thể đọc được cookie phiên hay không.

##### Expected Result

Cookie phiên phải có cờ 'HttpOnly' được bật (ngăn chặn JavaScript client đọc cookie qua document.cookie) và cờ 'Secure' được bật (chỉ truyền qua HTTPS).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Lỗ hổng bảo mật thực tế trên SauceDemo: Cookie 'session-username' hoàn toàn không có cờ HttpOnly, JavaScript client có thể đọc và sửa đổi tự do qua document.cookie.

#### [TC-64] Kiểm tra phi chức năng: Kiểm tra khả năng chống tấn công Cross-Site Scripting (XSS) trên form Checkout Step 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-64 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra khả năng chống tấn công Cross-Site Scripting (XSS) trên form Checkout Step 1 |
| **Folder** | 04_Non_Functional_Testing/Security_Testing |
| **Component** | Security / Form Sanitization |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-16 |
| **TestScenarioID** | TS-33 |
| **Test Type** | Security Testing |
| **Execution Environment** | Chrome Desktop DevTools / Security Testing |
| **Precondition** | Đang ở trang '/checkout-step-one.html' với 1 sản phẩm trong giỏ. |
| **Test Data** | Payload XSS: <script>alert('XSS_VULNERABILITY')</script> hoặc <img src=x onerror=alert(1)> |
| **Postcondition** | Dữ liệu được hiển thị dưới dạng văn bản thuần an toàn. |

##### Objective
Xác minh các ô nhập liệu First Name, Last Name, Postal Code thực hiện làm sạch dữ liệu đầu vào (Input Sanitization), không thực thi mã JavaScript độc hại khi người dùng nhập chuỗi payload XSS.

##### Test Steps

1. Nhập '<script>alert("XSS")</script>' vào ô 'First Name'.
2. Nhập '<img src=x onerror=alert(1)>' vào ô 'Last Name'.
3. Nhập '12345' vào ô 'Postal Code'.
4. Nhấp nút 'Continue' và quan sát màn hình Bước 2.

##### Expected Result

Hệ thống mã hóa thực thể HTML (HTML entity encoding) hoặc loại bỏ thẻ độc hại. Tuyệt đối không có hộp thoại alert popup nào của mã JavaScript được thực thi trên trình duyệt.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử bảo mật hộp đen (OWASP Top 10 - Injection / Cross-Site Scripting).

#### [TC-65] Kiểm tra phi chức năng: Kiểm tra chống rò rỉ phiên làm việc khi sử dụng nút 'Back' của trình duyệt sau khi đăng xuất

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-65 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra chống rò rỉ phiên làm việc khi sử dụng nút 'Back' của trình duyệt sau khi đăng xuất |
| **Folder** | 04_Non_Functional_Testing/Security_Testing |
| **Component** | Security / Session Invalidation |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-16 |
| **TestScenarioID** | TS-33 |
| **Test Type** | Security / Session Management |
| **Execution Environment** | Chrome Desktop / Firefox / Safari |
| **Precondition** | Người dùng đang đăng nhập và vừa thực hiện 'Logout'. |
| **Test Data** | Tài khoản: standard_user |
| **Postcondition** | Phiên làm việc được hủy bỏ hoàn toàn cả trên server và client cache. |

##### Objective
Xác minh sau khi người dùng chọn 'Logout', việc nhấn nút Back trên trình duyệt không cho phép truy cập lại các thông tin nhạy cảm đã lưu trong bộ nhớ đệm (Cache Control & Session Invalidation).

##### Test Steps

1. Đăng nhập bằng 'standard_user' và thêm sản phẩm vào giỏ.
2. Mở Sidebar và nhấp 'Logout' để kết thúc phiên (quay về trang '/').
3. Nhấp vào nút 'Back' (Quay lại trang trước) trên thanh công cụ của trình duyệt web.
4. Quan sát phản hồi của trang web.

##### Expected Result

Hệ thống ngăn chặn truy cập, kiểm tra thấy không có cookie phiên hợp lệ sẽ lập tức điều hướng về trang đăng nhập với thông báo lỗi 'Epic sadface: You can only access \'/inventory.html\' when you are logged in.'. Không hiển thị trang sản phẩm từ bộ nhớ đệm.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra cơ chế Cache-Control: no-cache, no-store, must-revalidate.

---

<a id="tc-folder-04_non_functional_testing-accessibility_testing"></a>
### 04_Non_Functional_Testing/Accessibility_Testing

#### [TC-66] Kiểm tra phi chức năng: Kiểm tra điều hướng tuần tự bằng bàn phím (Keyboard Tab Order & Focus Ring)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-66 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra điều hướng tuần tự bằng bàn phím (Keyboard Tab Order & Focus Ring) |
| **Folder** | 04_Non_Functional_Testing/Accessibility_Testing |
| **Component** | Accessibility / Keyboard Navigation |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Accessibility Testing |
| **Execution Environment** | Chrome Desktop / macOS Sonoma / Keyboard Only Navigation |
| **Precondition** | Trang chủ hoặc trang đăng nhập được mở; không sử dụng chuột máy tính. |
| **Test Data** | Phím bấm: Tab, Shift+Tab, Enter, Spacebar |
| **Postcondition** | Trang web hỗ trợ tốt khả năng tiếp cận (Accessibility compliance). |

##### Objective
Xác minh người dùng khuyết tật hoặc người dùng chỉ sử dụng bàn phím có thể nhấn phím 'Tab' để di chuyển tuần tự qua các nút bấm, ô nhập liệu và nhấn 'Enter'/'Space' để kích hoạt hành động.

##### Test Steps

1. Truy cập trang đăng nhập 'https://www.saucedemo.com/'.
2. Nhấn phím 'Tab' liên tục và quan sát viền con trỏ lấy nét (Focus Ring / Outline).
3. Xác nhận thứ tự lấy nét: Ô Username -> Ô Password -> Nút Login.
4. Gõ thông tin tài khoản và nhấn phím 'Enter' tại nút Login.
5. Trên trang sản phẩm, nhấn Tab để di chuyển qua từng thẻ sản phẩm và nút 'Add to cart'.

##### Expected Result

Vị trí con trỏ lấy nét (focus indicator) hiển thị viền rõ ràng, thứ tự Tab di chuyển tự nhiên từ trên xuống dưới, từ trái sang phải theo tiêu chuẩn WCAG 2.1 Level AA.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử tiêu chuẩn khả năng tiếp cận WCAG 2.1 (Web Content Accessibility Guidelines).

#### [TC-67] Kiểm tra phi chức năng: Kiểm tra tên trợ năng (Accessible Names / aria-label) và độ tương phản màu sắc

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-67 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra tên trợ năng (Accessible Names / aria-label) và độ tương phản màu sắc |
| **Folder** | 04_Non_Functional_Testing/Accessibility_Testing |
| **Component** | Accessibility / Screen Reader |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Accessibility Testing |
| **Execution Environment** | Chrome DevTools / Lighthouse Accessibility Audit |
| **Precondition** | Đang ở trang '/inventory.html'. |
| **Test Data** | Công cụ kiểm tra: Axe DevTools / Chrome Lighthouse Accessibility Audit |
| **Postcondition** | Trang web thân thiện với người dùng trợ năng. |

##### Objective
Xác minh các biểu tượng icon (nút mở menu, giỏ hàng, mạng xã hội footer) có gắn thuộc tính 'aria-label' hoặc 'title' để trình đọc màn hình (Screen Reader) có thể đọc được cho người khiếm thị.

##### Test Steps

1. Mở Chrome DevTools -> Inspect phần tử biểu tượng giỏ hàng và nút hamburger menu.
2. Kiểm tra sự hiện diện của thuộc tính 'aria-label' hoặc 'title' hoặc văn bản ẩn (screen-reader text).
3. Chạy Lighthouse Audit mục 'Accessibility'.
4. Kiểm tra tỷ lệ tương phản màu sắc (Color Contrast Ratio >= 4.5:1) giữa màu chữ và màu nền.

##### Expected Result

Điểm trợ năng Lighthouse đạt trên 90 điểm. Các nút dạng icon có nhãn mô tả rõ ràng, tỷ lệ tương phản màu sắc đạt chuẩn WCAG 2.1 AA.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Đảm bảo tuân thủ tiêu chuẩn tiếp cận phổ quát (Universal Accessibility).

---

<a id="tc-folder-04_non_functional_testing-usability_testing"></a>
### 04_Non_Functional_Testing/Usability_Testing

#### [TC-68] Kiểm tra phi chức năng: Tính nhất quán của phản hồi trực quan trên bộ đếm giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-68 |
| **Name** | Kiểm tra phi chức năng: Tính nhất quán của phản hồi trực quan trên bộ đếm giỏ hàng |
| **Folder** | 04_Non_Functional_Testing/Usability_Testing |
| **Component** | Usability / Visual Feedback |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Usability Testing |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma |
| **Precondition** | Đang ở trang '/inventory.html'. |
| **Test Data** | Sản phẩm: Sauce Labs Backpack |
| **Postcondition** | Trải nghiệm người dùng đạt độ hài lòng cao. |

##### Objective
Xác minh khi thêm hoặc xóa sản phẩm, biểu tượng giỏ hàng và huy hiệu số lượng cập nhật phản hồi trực quan ngay lập tức, không gây nhầm lẫn cho người dùng.

##### Test Steps

1. Nhấp 'Add to cart' tại sản phẩm Balo.
2. Quan sát sự thay đổi màu sắc và chữ trên nút (từ chữ đen viền xám sang chữ đỏ viền đỏ 'Remove').
3. Quan sát huy hiệu đỏ trên icon giỏ hàng ở thanh header.
4. Nhấp 'Remove' và quan sát sự biến mất tức thì của huy hiệu mà không giật màn hình.

##### Expected Result

Phản hồi thị giác diễn ra mượt mà tức thì (<100ms), người dùng nhận biết rõ ràng sản phẩm đã được thêm/xóa khỏi giỏ hàng mà không cần kiểm tra lại.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra nguyên lý phản hồi tức thời của Jakob Nielsen (Visibility of system status).

#### [TC-69] Kiểm tra phi chức năng: Phát hiện lỗi căn chỉnh layout và vị trí các thành phần trên thanh Header khi đăng nhập bằng visual_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-69 |
| **Name** | Kiểm tra phi chức năng: Phát hiện lỗi căn chỉnh layout và vị trí các thành phần trên thanh Header khi đăng nhập bằng visual_user |
| **Folder** | 04_Non_Functional_Testing/Usability_Testing |
| **Component** | UI Layout / Header Alignment |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Visual Regression / UI Layout / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/inventory.html'. |
| **Test Data** | Username: visual_user | Password: secret_sauce |
| **Postcondition** | Giao diện trực quan đẹp mắt, đúng chuẩn thiết kế. |

##### Objective
Xác minh tính nhất quán của giao diện người dùng (Pixel-perfect & Visual Alignment), phát hiện lỗi biểu tượng giỏ hàng và menu bị xô lệch tọa độ so với thiết kế chuẩn.

##### Test Steps

1. Đăng nhập bằng 'visual_user' / 'secret_sauce'.
2. Kiểm tra thanh Header phía trên cùng của trang '/inventory.html'.
3. Đối chiếu vị trí, margin, padding của biểu tượng giỏ hàng và nút menu so với giao diện chuẩn của 'standard_user'.

##### Expected Result

Toàn bộ các biểu tượng căn chỉnh ngay ngắn, đúng lề phải và lề trái theo CSS Grid/Flexbox chuẩn. Không có phần tử nào bị thụt lề, lệch vị trí hoặc chèn đè lên nhau.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của visual_user: Biểu tượng giỏ hàng bị dịch chuyển vị trí bất thường và nút bấm bị áp dụng CSS class sai lệch.

---

<a id="tc-folder-04_non_functional_testing-compatibility_testing"></a>
### 04_Non_Functional_Testing/Compatibility_Testing

#### [TC-70] Kiểm tra phi chức năng: Kiểm tra tính tương thích hiển thị Responsive UI trên màn hình Mobile Viewport

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-70 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra tính tương thích hiển thị Responsive UI trên màn hình Mobile Viewport |
| **Folder** | 04_Non_Functional_Testing/Compatibility_Testing |
| **Component** | Compatibility / Mobile Responsive |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Compatibility / Responsive Testing |
| **Execution Environment** | Chrome Device Mode / Emulated Mobile Viewports (iOS & Android) |
| **Precondition** | Mở trang web trên trình duyệt Chrome. |
| **Test Data** | Thiết bị mô phỏng: iPhone 14 / Samsung Galaxy S20 (Viewport 375x812 và 412x915) |
| **Postcondition** | Trải nghiệm mượt mà trên nền tảng di động. |

##### Objective
Xác minh bố cục giao diện trang danh mục sản phẩm và giỏ hàng tự động co giãn linh hoạt, không bị vỡ khung hình hoặc mất nút bấm khi xem trên màn hình điện thoại di động.

##### Test Steps

1. Bật chế độ mô phỏng thiết bị di động (Toggle Device Toolbar - Ctrl+Shift+M).
2. Chọn thiết bị 'iPhone 14' (độ phân giải 390x844 px).
3. Đăng nhập và quan sát trang danh mục sản phẩm '/inventory.html'.
4. Kiểm tra lưới sản phẩm chuyển từ 2 cột sang 1 cột duy nhất (Single Column Layout).
5. Kiểm tra biểu tượng giỏ hàng, menu sidebar và các nút bấm 'Add to cart' có kích thước vùng chạm (Touch Target > 44x44 px) phù hợp cho ngón tay hay không.

##### Expected Result

Giao diện hiển thị cân đối, không xuất hiện thanh cuộn ngang (Horizontal scrollbar). Chữ đọc rõ ràng không bị đè chữ, các nút bấm bấm dễ dàng trên màn hình cảm ứng.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử tính tương thích đa thiết bị (Cross-device Responsive Testing).

#### [TC-71] Kiểm tra phi chức năng: Kiểm tra khả năng tương thích hiển thị và hoạt động trên nhiều trình duyệt (Cross-Browser)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-71 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra khả năng tương thích hiển thị và hoạt động trên nhiều trình duyệt (Cross-Browser) |
| **Folder** | 04_Non_Functional_Testing/Compatibility_Testing |
| **Component** | Compatibility / Cross-Browser |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Compatibility / Cross-Browser |
| **Execution Environment** | Multi-browser: Chrome / Firefox / Safari on macOS Sonoma |
| **Precondition** | Cài đặt sẵn các trình duyệt Chrome, Firefox, Safari trên máy trạm. |
| **Test Data** | Trình duyệt: Chrome v124+, Firefox v125+, Safari v17+ |
| **Postcondition** | Ứng dụng tương thích hoàn hảo với các trình duyệt thông dụng. |

##### Objective
Xác minh quy trình đăng nhập, thêm hàng và thanh toán hoạt động ổn định và nhất quán trên các trình duyệt phổ biến (Google Chrome, Mozilla Firefox, Apple Safari).

##### Test Steps

1. Mở lần lượt từng trình duyệt: Google Chrome, Mozilla Firefox, Apple Safari.
2. Truy cập 'https://www.saucedemo.com/' trên từng trình duyệt.
3. Đăng nhập bằng 'standard_user'.
4. Thêm sản phẩm vào giỏ, kiểm tra giao diện giỏ hàng và form checkout.

##### Expected Result

Giao diện hiển thị nhất quán trên cả 3 trình duyệt; các hiệu ứng chuyển động, nút bấm và form nhập liệu hoạt động đồng bộ không có sự sai khác về tính năng.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử khả năng tương thích trình duyệt (Cross-browser Compatibility).

---

