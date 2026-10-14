# Test Cases Document: SauceDemo E-Commerce Web Application

**Target Application:** SauceDemo ([https://www.saucedemo.com/](https://www.saucedemo.com/))  
**Standard Compliance:** Zephyr Test Management Standard & Anatomy of a Professional Test Case  
**Author / Owner:** QA - Khổng Đức Anh  
**Total Test Cases:** 42 Test Cases  
**Status:** Approved (Ready for Test Execution)  

---

## Table of Contents

- [1. Zephyr Compatible Structure Overview](#tc-section-1)
- [2. Test Cases Master Index Table](#tc-section-2)
- [3. Detailed Test Cases](#tc-section-3)
  - [01_Authentication (TC-01 to TC-09)](#tc-folder-01_authentication)
  - [02_Product_Catalog (TC-10 to TC-16)](#tc-folder-02_product_catalog)
  - [03_Shopping_Cart (TC-17 to TC-25)](#tc-folder-03_shopping_cart)
  - [04_Checkout (TC-26 to TC-38)](#tc-folder-04_checkout)
  - [05_Sidebar_Navigation (TC-39 to TC-41)](#tc-folder-05_sidebar_navigation)
  - [06_End_to_End (TC-42 to TC-42)](#tc-folder-06_end_to_end)

---

<a id="tc-section-1"></a>
## 1. Zephyr Compatible Structure Overview

Bộ Test Cases này được xây dựng tương thích hoàn toàn với các trường dữ liệu trên **Zephyr Scale / Zephyr Squad** trên Jira:
- **Name:** Tiêu đề ca kiểm thử rõ ràng, súc tích.
- **Objective:** Mục tiêu chi tiết của ca kiểm thử.
- **Precondition:** Điều kiện tiên quyết trước khi thực thi.
- **Folder:** Thư mục lưu trữ trong Zephyr Test Library (`01_Authentication` đến `06_End_to_End`).
- **Component:** Phân vùng chức năng của hệ thống.
- **Status:** `Approved` (Trạng thái ca kiểm thử đã được duyệt chuẩn chỉ trên Zephyr).
- **Priority / Severity:** Đánh giá mức độ ưu tiên xử lý và mức độ nghiêm trọng kỹ thuật.
- **Owner:** QA - Khổng Đức Anh.
- **UserStoryID:** Mã định danh User Story chuẩn (`US-01`, `US-02`...) dùng để tạo liên kết truy xuất trực tiếp đến work item - story trên Jira.
- **TestScenarioID:** Mã truy xuất về Kịch bản kiểm thử tương ứng (`TS-01`, `TS-02`...).
- **Test Steps:** Các bước thực hiện cụ thể theo số thứ tự (Plain Text).
- **Test Data:** Dữ liệu nhập vào ô hoặc giá trị cần thao tác.
- **Expected Result:** Kết quả kỳ vọng chi tiết và có thể đo lường cho toàn bộ ca kiểm thử.
- **Actual Result / Execution Info:** Điền '-' để sẵn sàng cập nhật sau khi chạy thực tế ở Phase 2.

<a id="tc-section-2"></a>
## 2. Test Cases Master Index Table

| **TC ID** | **Folder** | **Name** | **Type** | **Priority** | **Severity** | **UserStoryID** | **TestScenarioID** | **Status** |
|:---|:---|:---|:---|:---:|:---:|:---:|:---:|:---:|
| **TC-01** | 01_Authentication | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ | Functional / Smoke | High | Critical | US-01 | TS-01 | Approved |
| **TC-02** | 01_Authentication | Kiểm tra thông báo lỗi khi để trống cả Username và Password | Negative / Validation | High | Medium | US-02 | TS-02 | Approved |
| **TC-03** | 01_Authentication | Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password | Negative / Validation | High | Medium | US-02 | TS-02 | Approved |
| **TC-04** | 01_Authentication | Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password | Negative / Validation | Medium | Medium | US-02 | TS-02 | Approved |
| **TC-05** | 01_Authentication | Kiểm tra từ chối đăng nhập khi nhập tài khoản hoặc mật khẩu không đúng | Negative / Security | High | High | US-02 | TS-03 | Approved |
| **TC-06** | 01_Authentication | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) | Negative / Security | High | High | US-02 | TS-04 | Approved |
| **TC-07** | 01_Authentication | Kiểm tra đóng thông báo lỗi đăng nhập bằng nút biểu tượng 'X' | UI / Functional | Low | Low | US-02 | TS-02 | Approved |
| **TC-08** | 01_Authentication | Kiểm tra đăng xuất tài khoản thành công qua menu Sidebar | Functional / Smoke | High | Critical | US-03 | TS-05 | Approved |
| **TC-09** | 01_Authentication | Kiểm tra chặn truy cập trực tiếp URL nội bộ (/inventory.html) khi chưa đăng nhập | Security / Session | High | Critical | US-03 | TS-05 | Approved |
| **TC-10** | 02_Product_Catalog | Kiểm tra hiển thị đầy đủ 6 sản phẩm kèm tên, mô tả và giá bán | Functional / Catalog | High | High | US-04 | TS-06 | Approved |
| **TC-11** | 02_Product_Catalog | Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào tên sản phẩm và quay lại danh mục | Functional / Navigation | High | Medium | US-04 | TS-07 | Approved |
| **TC-12** | 02_Product_Catalog | Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào hình ảnh sản phẩm | Functional / Navigation | Medium | Medium | US-04 | TS-07 | Approved |
| **TC-13** | 02_Product_Catalog | Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái tăng dần (A to Z) | Functional / Sorting | Medium | Medium | US-05 | TS-08 | Approved |
| **TC-14** | 02_Product_Catalog | Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái giảm dần (Z to A) | Functional / Sorting | Medium | Medium | US-05 | TS-08 | Approved |
| **TC-15** | 02_Product_Catalog | Kiểm tra sắp xếp sản phẩm theo giá số học tăng dần (Price low to high) | Functional / Sorting | High | Medium | US-05 | TS-09 | Approved |
| **TC-16** | 02_Product_Catalog | Kiểm tra sắp xếp sản phẩm theo giá số học giảm dần (Price high to low) | Functional / Sorting | High | Medium | US-05 | TS-09 | Approved |
| **TC-17** | 03_Shopping_Cart | Kiểm tra nhấp 'Add to cart' đổi nút thành 'Remove' và hiện huy hiệu giỏ hàng '1' | Functional / Smoke | High | Critical | US-06 | TS-11 | Approved |
| **TC-18** | 03_Shopping_Cart | Kiểm tra thêm nhiều sản phẩm làm tăng dần số lượng trên huy hiệu giỏ hàng | Functional / Cart | High | High | US-06 | TS-11 | Approved |
| **TC-19** | 03_Shopping_Cart | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm | Functional / Cart | High | High | US-06 | TS-11 | Approved |
| **TC-20** | 03_Shopping_Cart | Kiểm tra xóa sản phẩm ngay tại trang danh mục làm giảm số lượng trên huy hiệu giỏ | Functional / Cart | High | High | US-07 | TS-12 | Approved |
| **TC-21** | 03_Shopping_Cart | Kiểm tra xóa sản phẩm duy nhất còn lại làm biến mất hoàn toàn huy hiệu giỏ hàng (Biên 1 về 0) | Boundary / Functional | High | Medium | US-07 | TS-12 | Approved |
| **TC-22** | 03_Shopping_Cart | Kiểm tra trang giỏ hàng (/cart.html) hiển thị đúng sản phẩm, số lượng 1 và đơn giá | Functional / Cart | High | Critical | US-08 | TS-13 | Approved |
| **TC-23** | 03_Shopping_Cart | Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng | Functional / Cart | High | High | US-07 | TS-14 | Approved |
| **TC-24** | 03_Shopping_Cart | Kiểm tra nút 'Continue Shopping' đưa người dùng quay lại danh mục và giữ nguyên giỏ hàng | Functional / Navigation | Medium | Medium | US-08 | TS-13 | Approved |
| **TC-25** | 03_Shopping_Cart | Kiểm tra dữ liệu giỏ hàng vẫn giữ nguyên khi tải lại trang (F5) hoặc chuyển trang | Functional / State Persistence | High | High | US-08 | TS-15 | Approved |
| **TC-26** | 04_Checkout | Kiểm tra nút 'Checkout' trên giỏ hàng chuyển sang trang thanh toán Bước 1 | Functional / Smoke | High | Critical | US-09 | TS-16 | Approved |
| **TC-27** | 04_Checkout | Kiểm tra thông báo lỗi khi để trống toàn bộ thông tin tại Checkout Bước 1 | Negative / Validation | High | High | US-09 | TS-17 | Approved |
| **TC-28** | 04_Checkout | Kiểm tra thông báo lỗi khi nhập First Name nhưng để trống Last Name | Negative / Validation | High | Medium | US-09 | TS-17 | Approved |
| **TC-29** | 04_Checkout | Kiểm tra thông báo lỗi khi nhập First Name, Last Name nhưng để trống Postal Code | Negative / Validation | High | Medium | US-09 | TS-17 | Approved |
| **TC-30** | 04_Checkout | Kiểm tra xử lý các định dạng mã bưu điện đặc biệt và quốc tế (BVA & EP) | Boundary / Equivalence | Medium | Medium | US-09 | TS-18 | Approved |
| **TC-31** | 04_Checkout | Kiểm tra nút 'Cancel' tại Bước 1 quay lại giỏ hàng và giữ nguyên các sản phẩm | Functional / Navigation | Medium | Medium | US-09 | TS-19 | Approved |
| **TC-32** | 04_Checkout | Kiểm tra nhập thông tin hợp lệ tại Bước 1 chuyển sang màn hình Bước 2 | Functional / Smoke | High | Critical | US-09 | TS-16 | Approved |
| **TC-33** | 04_Checkout | Kiểm tra màn hình Bước 2 hiển thị đúng sản phẩm, thông tin thanh toán và giao hàng | Functional / Checkout | High | High | US-10 | TS-20 | Approved |
| **TC-34** | 04_Checkout | Kiểm tra tính toán chính xác Item Total, Tax (8%) và Grand Total tại Checkout Bước 2 | Functional / Calculation | High | Critical | US-10 | TS-20 | Approved |
| **TC-35** | 04_Checkout | Kiểm tra nút 'Cancel' tại Bước 2 đưa người dùng về trang danh mục và giữ nguyên giỏ hàng | Functional / Navigation | Medium | Medium | US-10 | TS-21 | Approved |
| **TC-36** | 04_Checkout | Kiểm tra nhấp 'Finish' tại Bước 2 hoàn tất đơn hàng và hiển thị thông điệp thành công | Functional / Smoke | High | Critical | US-11 | TS-22 | Approved |
| **TC-37** | 04_Checkout | Kiểm tra làm mới và xóa huy hiệu giỏ hàng sau khi hoàn tất đặt hàng | Functional / Cart Reset | High | High | US-11 | TS-22 | Approved |
| **TC-38** | 04_Checkout | Kiểm tra nút 'Back Home' trên màn hình hoàn tất đưa người dùng về lại trang danh mục | Functional / Navigation | Medium | Medium | US-11 | TS-22 | Approved |
| **TC-39** | 05_Sidebar_Navigation | Kiểm tra mở menu Sidebar bằng biểu tượng hamburger và đóng bằng nút 'X' | UI / Navigation | Medium | Medium | US-12 | TS-24 | Approved |
| **TC-40** | 05_Sidebar_Navigation | Kiểm tra chức năng 'Reset App State' xóa sạch giỏ hàng và đặt lại các nút về 'Add to cart' | Functional / App State | High | High | US-12 | TS-27 | Approved |
| **TC-41** | 05_Sidebar_Navigation | Kiểm tra liên kết 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs | Functional / Navigation | Low | Low | US-12 | TS-26 | Approved |
| **TC-42** | 06_End_to_End | Kiểm tra toàn diện quy trình mua sắm End-to-End từ đăng nhập đến thanh toán và đăng xuất | E2E / Smoke / Business Flow | High | Critical | US-13 | TS-28 | Approved |

---

<a id="tc-section-3"></a>
## 3. Detailed Test Cases

<a id="tc-folder-01_authentication"></a>
### 01_Authentication

#### [TC-01] Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-01 |
| **Name** | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ |
| **Folder** | 01_Authentication |
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
| **Folder** | 01_Authentication |
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
| **Folder** | 01_Authentication |
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
| **Postcondition** | Người dùng chưa đăng nhập, ở lại trang đăng nhập. |

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
- **Comments / Notes:** Phân vùng EP: Username hợp lệ + Password rỗng.

#### [TC-04] Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-04 |
| **Name** | Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password |
| **Folder** | 01_Authentication |
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
| **Postcondition** | Người dùng chưa đăng nhập, ở lại trang đăng nhập. |

##### Objective
Xác minh khi người dùng để trống tên đăng nhập nhưng có nhập mật khẩu, hệ thống phải yêu cầu nhập tên đăng nhập trước.

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Để trống ô 'Username'.
3. Nhập 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Hệ thống từ chối đăng nhập và hiển thị thông báo lỗi: 'Epic sadface: Username is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Username rỗng + Password hợp lệ.

#### [TC-05] Kiểm tra từ chối đăng nhập khi nhập tài khoản hoặc mật khẩu không đúng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-05 |
| **Name** | Kiểm tra từ chối đăng nhập khi nhập tài khoản hoặc mật khẩu không đúng |
| **Folder** | 01_Authentication |
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
| **Test Data** | Username: invalid_user_99 | Password: wrong_password |
| **Postcondition** | Không có phiên làm việc nào được cấp phát. |

##### Objective
Đảm bảo hệ thống từ chối truy cập và hiển thị thông báo bảo mật khi tài khoản không tồn tại hoặc nhập sai mật khẩu.

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập tên tài khoản không tồn tại 'invalid_user_99' vào ô 'Username'.
3. Nhập mật khẩu sai 'wrong_password' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Hệ thống từ chối đăng nhập. Hiển thị thông báo lỗi bảo mật chung: 'Epic sadface: Username and password do not match any user in this service'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Tài khoản / Mật khẩu không hợp lệ.

#### [TC-06] Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-06 |
| **Name** | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) |
| **Folder** | 01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-04 |
| **Test Type** | Negative / Security |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. |
| **Test Data** | Username: locked_out_user | Password: secret_sauce |
| **Postcondition** | Tài khoản bị khóa không được phép truy cập vào ứng dụng. |

##### Objective
Đảm bảo tài khoản đã bị khóa không thể đăng nhập vào ứng dụng và hệ thống thông báo rõ ràng về tình trạng khóa tài khoản.

##### Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập tên tài khoản 'locked_out_user' vào ô 'Username'.
3. Nhập mật khẩu 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

##### Expected Result

Đăng nhập bị từ chối hoàn toàn. Hiển thị thông báo lỗi chính xác: 'Epic sadface: Sorry, this user has been locked out.'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra quy tắc nghiệp vụ về khóa tài khoản người dùng.

#### [TC-07] Kiểm tra đóng thông báo lỗi đăng nhập bằng nút biểu tượng 'X'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-07 |
| **Name** | Kiểm tra đóng thông báo lỗi đăng nhập bằng nút biểu tượng 'X' |
| **Folder** | 01_Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | UI / Functional |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang hiển thị thông báo lỗi màu đỏ trên màn hình đăng nhập. |
| **Test Data** | Kích hoạt lỗi rỗng để hiển thị thông báo lỗi |
| **Postcondition** | Trang đăng nhập trở lại trạng thái giao diện sạch sẽ. |

##### Objective
Đảm bảo người dùng có thể đóng dải thông báo lỗi màu đỏ trên màn hình đăng nhập bằng cách nhấp vào nút 'X'.

##### Test Steps

1. Nhấp nút 'Login' khi đang để trống để kích hoạt thông báo lỗi.
2. Xác nhận thông báo lỗi màu đỏ đang hiển thị.
3. Nhấp vào nút biểu tượng 'X' bên trong khung thông báo lỗi.

##### Expected Result

Dải thông báo lỗi màu đỏ và các biểu tượng cảnh báo tại các ô nhập liệu lập tức biến mất khỏi màn hình.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính tiện dụng (Usability) của giao diện người dùng.

#### [TC-08] Kiểm tra đăng xuất tài khoản thành công qua menu Sidebar

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-08 |
| **Name** | Kiểm tra đăng xuất tài khoản thành công qua menu Sidebar |
| **Folder** | 01_Authentication |
| **Component** | Sidebar Navigation / Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-03 |
| **TestScenarioID** | TS-05 |
| **Test Type** | Functional / Smoke |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập tài khoản 'standard_user' và đang ở trang '/inventory.html'. |
| **Test Data** | N/A |
| **Postcondition** | Phiên người dùng kết thúc hoàn toàn; trở về màn hình đăng nhập. |

##### Objective
Đảm bảo người dùng đã đăng nhập có thể kết thúc phiên làm việc an toàn bằng cách chọn 'Logout' trong menu điều hướng.

##### Test Steps

1. Nhấp vào biểu tượng 3 dấu gạch ngang (hamburger button) ở góc trái trên cùng.
2. Chờ menu trượt mở ra hoàn toàn.
3. Nhấp vào liên kết 'Logout'.

##### Expected Result

Phiên làm việc kết thúc. Trình duyệt chuyển hướng về trang chủ 'https://www.saucedemo.com/'. Cookie phiên 'session-username' bị xóa.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính an toàn của việc hủy phiên làm việc.

#### [TC-09] Kiểm tra chặn truy cập trực tiếp URL nội bộ (/inventory.html) khi chưa đăng nhập

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-09 |
| **Name** | Kiểm tra chặn truy cập trực tiếp URL nội bộ (/inventory.html) khi chưa đăng nhập |
| **Folder** | 01_Authentication |
| **Component** | Authentication Guard |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-03 |
| **TestScenarioID** | TS-05 |
| **Test Type** | Security / Session |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt ở chế độ ẩn danh hoặc đã xóa toàn bộ cookie, không có phiên đăng nhập nào. |
| **Test Data** | URL trực tiếp: https://www.saucedemo.com/inventory.html |
| **Postcondition** | Truy cập tài nguyên nội bộ bị từ chối; người dùng ở trang đăng nhập. |

##### Objective
Xác minh khi người dùng chưa đăng nhập mà dán thẳng URL nội bộ '/inventory.html' vào thanh địa chỉ thì hệ thống phải chặn lại.

##### Test Steps

1. Mở cửa sổ trình duyệt mới hoàn toàn không lưu cookie.
2. Nhập trực tiếp 'https://www.saucedemo.com/inventory.html' vào thanh địa chỉ và nhấn phím Enter.

##### Expected Result

Hệ thống lập tức chuyển hướng người dùng về trang đăng nhập 'https://www.saucedemo.com/'. Xuất hiện thông báo lỗi: 'Epic sadface: You can only access \'/inventory.html\' when you are logged in.'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra kiểm soát phân quyền và bảo vệ route phía client.

---

<a id="tc-folder-02_product_catalog"></a>
### 02_Product_Catalog

#### [TC-10] Kiểm tra hiển thị đầy đủ 6 sản phẩm kèm tên, mô tả và giá bán

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-10 |
| **Name** | Kiểm tra hiển thị đầy đủ 6 sản phẩm kèm tên, mô tả và giá bán |
| **Folder** | 02_Product_Catalog |
| **Component** | Inventory Catalog |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-06 |
| **Test Type** | Functional / Catalog |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đăng nhập thành công bằng 'standard_user' và đang ở trang '/inventory.html'. |
| **Test Data** | Danh sách 6 sản phẩm: Backpack (\$29.99), Bike Light (\$9.99), Bolt T-Shirt (\$15.99), Fleece Jacket (\$49.99), Onesie (\$7.99), T-Shirt (Red) (\$15.99) |
| **Postcondition** | Toàn bộ danh mục hiển thị đầy đủ trên màn hình. |

##### Objective
Đảm bảo trang danh mục sản phẩm hiển thị chính xác và đầy đủ 6 mặt hàng lưu niệm chuẩn của Sauce Labs.

##### Test Steps

1. Điều hướng đến trang '/inventory.html'.
2. Đếm tổng số lượng thẻ sản phẩm hiển thị trong danh sách '.inventory_list'.
3. Kiểm tra từng thẻ sản phẩm để xác nhận có đủ tên, mô tả, hình ảnh và giá bắt đầu bằng ký tự '\$'.

##### Expected Result

Hiển thị chính xác 6 sản phẩm. Mỗi sản phẩm có đầy đủ hình ảnh đại diện hợp lệ, tên sản phẩm, đoạn văn mô tả và giá tiền đúng định dạng số học.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính toàn vẹn dữ liệu danh mục hàng hóa.

#### [TC-11] Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào tên sản phẩm và quay lại danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-11 |
| **Name** | Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào tên sản phẩm và quay lại danh mục |
| **Folder** | 02_Product_Catalog |
| **Component** | Product Details |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-07 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm '/inventory.html'. |
| **Test Data** | Sản phẩm: Sauce Labs Backpack (ID: 4) |
| **Postcondition** | Người dùng quay về trang danh mục sản phẩm. |

##### Objective
Xác minh khi nhấp vào tiêu đề sản phẩm sẽ mở đúng trang chi tiết của sản phẩm đó và nút quay lại hoạt động chuẩn xác.

##### Test Steps

1. Nhấp vào liên kết tên sản phẩm 'Sauce Labs Backpack'.
2. Kiểm tra URL và các thông tin chi tiết trên trang mới.
3. Nhấp vào nút 'Back to products'.

##### Expected Result

Mở đúng trang '/inventory-item.html?id=4' với hình ảnh lớn, tên 'Sauce Labs Backpack', giá '\$29.99' và mô tả chi tiết. Nhấp 'Back to products' đưa người dùng quay lại đúng trang danh mục '/inventory.html'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra luồng điều hướng giữa danh mục và trang chi tiết.

#### [TC-12] Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào hình ảnh sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-12 |
| **Name** | Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào hình ảnh sản phẩm |
| **Folder** | 02_Product_Catalog |
| **Component** | Product Details |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-07 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/inventory.html'. |
| **Test Data** | Hình ảnh sản phẩm: Sauce Labs Bike Light (ID: 0) |
| **Postcondition** | Người dùng đang ở trang chi tiết sản phẩm. |

##### Objective
Xác minh khi nhấp vào hình ảnh đại diện của sản phẩm trên danh mục cũng mở đúng trang chi tiết sản phẩm.

##### Test Steps

1. Tìm sản phẩm 'Sauce Labs Bike Light' trên danh mục.
2. Nhấp trực tiếp vào hình ảnh đại diện của sản phẩm này.

##### Expected Result

Trình duyệt điều hướng đến 'https://www.saucedemo.com/inventory-item.html?id=0'. Trang chi tiết hiển thị đúng tên 'Sauce Labs Bike Light' và giá '\$9.99'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra liên kết hình ảnh.

#### [TC-13] Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái tăng dần (A to Z)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-13 |
| **Name** | Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái tăng dần (A to Z) |
| **Folder** | 02_Product_Catalog |
| **Component** | Inventory Sorting |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm '/inventory.html'. |
| **Test Data** | Tùy chọn sắp xếp: az (Name (A to Z)) |
| **Postcondition** | Danh mục duy trì sắp xếp từ A đến Z. |

##### Objective
Đảm bảo việc chọn sắp xếp 'Name (A to Z)' sắp xếp lại toàn bộ danh mục sản phẩm theo đúng thứ tự chữ cái từ A đến Z.

##### Test Steps

1. Nhấp vào hộp chọn sắp xếp (sort dropdown).
2. Chọn tùy chọn 'Name (A to Z)'.
3. Kiểm tra thứ tự hiển thị của 6 sản phẩm từ trên xuống dưới.

##### Expected Result

Sản phẩm sắp xếp theo thứ tự bảng chữ cái chính xác: 1. Sauce Labs Backpack, 2. Sauce Labs Bike Light, 3. Sauce Labs Bolt T-Shirt, 4. Sauce Labs Fleece Jacket, 5. Sauce Labs Onesie, 6. Test.allTheThings() T-Shirt (Red).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra sắp xếp mặc định và sắp xếp tăng dần theo chữ cái.

#### [TC-14] Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái giảm dần (Z to A)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-14 |
| **Name** | Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái giảm dần (Z to A) |
| **Folder** | 02_Product_Catalog |
| **Component** | Inventory Sorting |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/inventory.html'. |
| **Test Data** | Tùy chọn sắp xếp: za (Name (Z to A)) |
| **Postcondition** | Danh mục duy trì sắp xếp từ Z đến A. |

##### Objective
Đảm bảo việc chọn sắp xếp 'Name (Z to A)' đảo ngược thứ tự danh mục theo bảng chữ cái từ Z đến A.

##### Test Steps

1. Nhấp vào hộp chọn sắp xếp.
2. Chọn tùy chọn 'Name (Z to A)'.
3. Kiểm tra sản phẩm đầu tiên và sản phẩm cuối cùng.

##### Expected Result

Sản phẩm được đảo ngược theo bảng chữ cái: Sản phẩm đầu tiên là 'Test.allTheThings() T-Shirt (Red)' và sản phẩm cuối cùng là 'Sauce Labs Backpack'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra sắp xếp giảm dần theo chữ cái.

#### [TC-15] Kiểm tra sắp xếp sản phẩm theo giá số học tăng dần (Price low to high)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-15 |
| **Name** | Kiểm tra sắp xếp sản phẩm theo giá số học tăng dần (Price low to high) |
| **Folder** | 02_Product_Catalog |
| **Component** | Inventory Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-09 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/inventory.html'. |
| **Test Data** | Tùy chọn sắp xếp: lohi (Price (low to high)) |
| **Postcondition** | Danh mục duy trì sắp xếp giá tăng dần. |

##### Objective
Đảm bảo tùy chọn 'Price (low to high)' sắp xếp các mặt hàng theo giá trị số học từ rẻ nhất đến đắt nhất.

##### Test Steps

1. Nhấp vào hộp chọn sắp xếp.
2. Chọn tùy chọn 'Price (low to high)'.
3. Đọc danh sách các mức giá từ trên xuống dưới.

##### Expected Result

Các sản phẩm hiển thị chuẩn theo giá tăng dần: \$7.99 -> \$9.99 -> \$15.99 -> \$15.99 -> \$29.99 -> \$49.99. Món đầu tiên là Sauce Labs Onesie (\$7.99); món cuối cùng là Sauce Labs Fleece Jacket (\$49.99).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra sắp xếp giá số học (tránh lỗi so sánh chuỗi).

#### [TC-16] Kiểm tra sắp xếp sản phẩm theo giá số học giảm dần (Price high to low)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-16 |
| **Name** | Kiểm tra sắp xếp sản phẩm theo giá số học giảm dần (Price high to low) |
| **Folder** | 02_Product_Catalog |
| **Component** | Inventory Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-09 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/inventory.html'. |
| **Test Data** | Tùy chọn sắp xếp: hilo (Price (high to low)) |
| **Postcondition** | Danh mục duy trì sắp xếp giá giảm dần. |

##### Objective
Đảm bảo tùy chọn 'Price (high to low)' sắp xếp các mặt hàng theo giá trị số học từ đắt nhất đến rẻ nhất.

##### Test Steps

1. Nhấp vào hộp chọn sắp xếp.
2. Chọn tùy chọn 'Price (high to low)'.
3. Kiểm tra giá tiền món đầu tiên và món cuối cùng.

##### Expected Result

Các sản phẩm hiển thị chuẩn theo giá giảm dần: \$49.99 -> \$29.99 -> \$15.99 -> \$15.99 -> \$9.99 -> \$7.99. Món đầu tiên là Sauce Labs Fleece Jacket (\$49.99); món cuối cùng là Sauce Labs Onesie (\$7.99).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra sắp xếp giá giảm dần.

---

<a id="tc-folder-03_shopping_cart"></a>
### 03_Shopping_Cart

#### [TC-17] Kiểm tra nhấp 'Add to cart' đổi nút thành 'Remove' và hiện huy hiệu giỏ hàng '1'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-17 |
| **Name** | Kiểm tra nhấp 'Add to cart' đổi nút thành 'Remove' và hiện huy hiệu giỏ hàng '1' |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-11 |
| **Test Type** | Functional / Smoke |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm; giỏ hàng đang rỗng (không có huy hiệu số). |
| **Test Data** | Sản phẩm: Sauce Labs Backpack (ID nút: 'add-to-cart-sauce-labs-backpack') |
| **Postcondition** | Có 1 sản phẩm trong giỏ hàng; huy hiệu hiển thị '1'. |

##### Objective
Xác minh khi thêm một sản phẩm vào giỏ, nút chuyển trạng thái sang 'Remove' và huy hiệu giỏ hàng hiển thị số 1.

##### Test Steps

1. Kiểm tra biểu tượng giỏ hàng chưa có huy hiệu số lượng.
2. Nhấp vào nút 'Add to cart' của sản phẩm 'Sauce Labs Backpack'.

##### Expected Result

Nút bấm ngay lập tức đổi nhãn thành 'Remove' với viền đỏ (ID: 'remove-sauce-labs-backpack'). Xuất hiện huy hiệu màu đỏ trên biểu tượng giỏ hàng với con số '1'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra Smoke chức năng thêm hàng vào giỏ.

#### [TC-18] Kiểm tra thêm nhiều sản phẩm làm tăng dần số lượng trên huy hiệu giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-18 |
| **Name** | Kiểm tra thêm nhiều sản phẩm làm tăng dần số lượng trên huy hiệu giỏ hàng |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-11 |
| **Test Type** | Functional / Cart |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục với giỏ hàng rỗng. |
| **Test Data** | Thêm 3 sản phẩm: Backpack, Bike Light, Bolt T-Shirt |
| **Postcondition** | Có 3 sản phẩm trong giỏ hàng. |

##### Objective
Đảm bảo việc thêm tuần tự nhiều sản phẩm làm bộ đếm giỏ hàng tăng liên tục tương ứng (1 -> 2 -> 3).

##### Test Steps

1. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Backpack.
2. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Bike Light.
3. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Bolt T-Shirt.

##### Expected Result

Huy hiệu giỏ hàng cập nhật tăng dần chính xác lên số '3'. Cả 3 sản phẩm đều hiển thị nút 'Remove'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra logic tăng dần của bộ đếm giỏ hàng.

#### [TC-19] Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-19 |
| **Name** | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm |
| **Folder** | 03_Shopping_Cart |
| **Component** | Product Details / Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-11 |
| **Test Type** | Functional / Cart |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang chi tiết '/inventory-item.html?id=4' (Sauce Labs Backpack) với giỏ hàng rỗng. |
| **Test Data** | Nút: 'Add to cart' (id='add-to-cart') |
| **Postcondition** | Sản phẩm được lưu trong giỏ hàng và đồng bộ trên các trang. |

##### Objective
Xác minh người dùng có thể thêm sản phẩm vào giỏ hàng trực tiếp từ màn hình chi tiết sản phẩm và trạng thái được đồng bộ ra danh mục.

##### Test Steps

1. Nhấp vào nút 'Add to cart' trên trang chi tiết sản phẩm.
2. Nhấp 'Back to products' để quay về trang danh mục chính.

##### Expected Result

Nút trên trang chi tiết đổi thành 'Remove' và huy hiệu hiển thị '1'. Khi quay về danh mục, thẻ sản phẩm Backpack cũng hiển thị nút 'Remove'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính đồng bộ trạng thái giữa các trang.

#### [TC-20] Kiểm tra xóa sản phẩm ngay tại trang danh mục làm giảm số lượng trên huy hiệu giỏ

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-20 |
| **Name** | Kiểm tra xóa sản phẩm ngay tại trang danh mục làm giảm số lượng trên huy hiệu giỏ |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Functional / Cart |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục; giỏ hàng đã có 2 sản phẩm (huy hiệu hiển thị '2'). |
| **Test Data** | Nhấp 'Remove' tại sản phẩm Sauce Labs Bike Light |
| **Postcondition** | Còn lại 1 sản phẩm trong giỏ hàng. |

##### Objective
Đảm bảo nhấp vào nút 'Remove' của sản phẩm đã thêm trên danh mục sẽ giảm số lượng tương ứng.

##### Test Steps

1. Xác nhận huy hiệu giỏ hàng đang hiển thị số '2'.
2. Nhấp vào nút 'Remove' của sản phẩm Sauce Labs Bike Light.

##### Expected Result

Nút bấm của Bike Light lập tức quay về trạng thái ban đầu 'Add to cart'. Huy hiệu giỏ hàng giảm từ '2' xuống còn '1'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra logic giảm số lượng của giỏ hàng.

#### [TC-21] Kiểm tra xóa sản phẩm duy nhất còn lại làm biến mất hoàn toàn huy hiệu giỏ hàng (Biên 1 về 0)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-21 |
| **Name** | Kiểm tra xóa sản phẩm duy nhất còn lại làm biến mất hoàn toàn huy hiệu giỏ hàng (Biên 1 về 0) |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Boundary / Functional |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Giỏ hàng có đúng 1 sản phẩm duy nhất (huy hiệu hiển thị '1'). |
| **Test Data** | Nhấp 'Remove' tại sản phẩm duy nhất trong giỏ |
| **Postcondition** | Giỏ hàng rỗng hoàn toàn, không có huy hiệu. |

##### Objective
Kiểm tra giá trị biên: Khi giỏ hàng chỉ còn 1 sản phẩm và bị xóa thì huy hiệu giỏ hàng biến mất hoàn toàn thay vì hiển thị số 0.

##### Test Steps

1. Xác nhận huy hiệu giỏ hàng đang hiển thị '1'.
2. Nhấp vào nút 'Remove' của sản phẩm đó.

##### Expected Result

Nút đổi lại thành 'Add to cart'. Phần tử huy hiệu giỏ hàng (.shopping_cart_badge) bị xóa hoàn toàn khỏi DOM (không hiển thị số '0').

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kỹ thuật phân tích giá trị biên BVA (Số lượng: 1 về 0).

#### [TC-22] Kiểm tra trang giỏ hàng (/cart.html) hiển thị đúng sản phẩm, số lượng 1 và đơn giá

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-22 |
| **Name** | Kiểm tra trang giỏ hàng (/cart.html) hiển thị đúng sản phẩm, số lượng 1 và đơn giá |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-08 |
| **TestScenarioID** | TS-13 |
| **Test Type** | Functional / Cart |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã thêm 2 sản phẩm: Sauce Labs Backpack (\$29.99) và Sauce Labs Onesie (\$7.99). |
| **Test Data** | Sản phẩm: Backpack (\$29.99) và Onesie (\$7.99) |
| **Postcondition** | Người dùng đang ở trang xem giỏ hàng. |

##### Objective
Xác minh khi mở trang '/cart.html', toàn bộ danh sách các mặt hàng đã chọn được liệt kê chuẩn xác kèm số lượng QTY = 1 và đơn giá.

##### Test Steps

1. Nhấp vào biểu tượng giỏ hàng trên thanh header.
2. Kiểm tra tiêu đề trang và danh sách các dòng sản phẩm.
3. Kiểm tra cột số lượng QTY của từng món.
4. Kiểm tra tên và đơn giá của từng món.

##### Expected Result

Chuyển hướng đến '/cart.html'. Tiêu đề hiển thị 'Your Cart'. Có đúng 2 dòng sản phẩm với QTY là '1' cho mỗi món, tên và giá tiền (\$29.99 và \$7.99) hiển thị chuẩn xác.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính toàn vẹn dữ liệu trong trang giỏ hàng.

#### [TC-23] Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-23 |
| **Name** | Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-14 |
| **Test Type** | Functional / Cart |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/cart.html' có 2 sản phẩm (huy hiệu hiển thị '2'). |
| **Test Data** | Nhấp 'Remove' tại sản phẩm Sauce Labs Onesie |
| **Postcondition** | Giỏ hàng còn lại đúng 1 sản phẩm. |

##### Objective
Xác minh nút 'Remove' trên trang '/cart.html' xóa đúng dòng sản phẩm đó và cập nhật số lượng trên huy hiệu.

##### Test Steps

1. Nhấp nút 'Remove' bên cạnh món 'Sauce Labs Onesie'.
2. Quan sát sự thay đổi trên danh sách sản phẩm và huy hiệu giỏ hàng.

##### Expected Result

Dòng sản phẩm 'Sauce Labs Onesie' biến mất khỏi danh sách giỏ hàng. Huy hiệu giỏ hàng lập tức giảm từ '2' xuống còn '1'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra thao tác xóa sản phẩm trong giao diện giỏ hàng.

#### [TC-24] Kiểm tra nút 'Continue Shopping' đưa người dùng quay lại danh mục và giữ nguyên giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-24 |
| **Name** | Kiểm tra nút 'Continue Shopping' đưa người dùng quay lại danh mục và giữ nguyên giỏ hàng |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-08 |
| **TestScenarioID** | TS-13 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/cart.html' có sản phẩm trong giỏ. |
| **Test Data** | Nút: 'Continue Shopping' (id='continue-shopping') |
| **Postcondition** | Người dùng quay về trang danh mục sản phẩm. |

##### Objective
Đảm bảo nút 'Continue Shopping' tại trang giỏ hàng đưa người dùng trở lại danh mục sản phẩm mà không làm mất hàng trong giỏ.

##### Test Steps

1. Nhấp vào nút 'Continue Shopping' trên trang giỏ hàng.
2. Kiểm tra tiêu đề trang và biểu tượng giỏ hàng trên trang danh mục.

##### Expected Result

Trình duyệt chuyển về trang '/inventory.html'. Tiêu đề hiển thị 'Products'. Huy hiệu giỏ hàng và trạng thái các nút 'Remove' vẫn được bảo toàn nguyên vẹn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra luồng mua sắm tiếp tục (Continue Shopping).

#### [TC-25] Kiểm tra dữ liệu giỏ hàng vẫn giữ nguyên khi tải lại trang (F5) hoặc chuyển trang

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-25 |
| **Name** | Kiểm tra dữ liệu giỏ hàng vẫn giữ nguyên khi tải lại trang (F5) hoặc chuyển trang |
| **Folder** | 03_Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-08 |
| **TestScenarioID** | TS-15 |
| **Test Type** | Functional / State Persistence |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã thêm 2 sản phẩm vào giỏ hàng tại '/inventory.html'. |
| **Test Data** | Thao tác tải lại trang (Ctrl+F5 / Cmd+Shift+R) |
| **Postcondition** | Dữ liệu giỏ hàng nguyên vẹn sau khi tải lại trang. |

##### Objective
Đảm bảo trạng thái giỏ hàng được lưu trữ bền vững (localStorage / sessionStorage) và không bị mất khi người dùng làm mới trang.

##### Test Steps

1. Xác nhận huy hiệu giỏ hàng hiển thị số '2'.
2. Thực hiện làm mới trình duyệt (Hard Refresh: Cmd+Shift+R).
3. Chuyển sang trang '/cart.html'.
4. Kiểm tra danh sách mặt hàng và bộ đếm.

##### Expected Result

Dữ liệu giỏ hàng và huy hiệu số '2' được bảo toàn tuyệt đối, không có hiện tượng mất dữ liệu hay bị xóa trắng.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính bền vững của lưu trữ trạng thái người dùng.

---

<a id="tc-folder-04_checkout"></a>
### 04_Checkout

#### [TC-26] Kiểm tra nút 'Checkout' trên giỏ hàng chuyển sang trang thanh toán Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-26 |
| **Name** | Kiểm tra nút 'Checkout' trên giỏ hàng chuyển sang trang thanh toán Bước 1 |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-16 |
| **Test Type** | Functional / Smoke |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/cart.html' với ít nhất 1 sản phẩm trong giỏ. |
| **Test Data** | Nút: 'Checkout' (id='checkout') |
| **Postcondition** | Người dùng đang ở Checkout Bước 1. |

##### Objective
Xác minh nhấp nút 'Checkout' tại trang '/cart.html' mở thành công màn hình điền thông tin giao hàng.

##### Test Steps

1. Nhấp vào nút 'Checkout' trên trang giỏ hàng.

##### Expected Result

Trình duyệt chuyển hướng đến 'https://www.saucedemo.com/checkout-step-one.html'. Tiêu đề phụ hiển thị 'Checkout: Your Information' cùng 3 ô nhập liệu: First Name, Last Name, Zip/Postal Code.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra Smoke khởi động quy trình thanh toán.

#### [TC-27] Kiểm tra thông báo lỗi khi để trống toàn bộ thông tin tại Checkout Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-27 |
| **Name** | Kiểm tra thông báo lỗi khi để trống toàn bộ thông tin tại Checkout Bước 1 |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-17 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: '' | Last Name: '' | Postal Code: '' |
| **Postcondition** | Người dùng vẫn ở màn hình Bước 1; form chưa được gửi. |

##### Objective
Đảm bảo khi nhấn 'Continue' mà chưa nhập bất kỳ thông tin nào, hệ thống phải yêu cầu nhập First Name trước (Kỹ thuật phân vùng tương đương: Dữ liệu rỗng).

##### Test Steps

1. Để trống cả 3 ô: First Name, Last Name, Postal Code.
2. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống chặn chuyển trang. Xuất hiện thông báo lỗi màu đỏ: 'Error: First Name is required'. Các ô nhập liệu bị viền đỏ cảnh báo.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Bỏ trống toàn bộ các trường bắt buộc.

#### [TC-28] Kiểm tra thông báo lỗi khi nhập First Name nhưng để trống Last Name

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-28 |
| **Name** | Kiểm tra thông báo lỗi khi nhập First Name nhưng để trống Last Name |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-17 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: '' | Postal Code: '' |
| **Postcondition** | Người dùng ở lại màn hình Bước 1. |

##### Objective
Xác minh khi người dùng đã nhập First Name nhưng bỏ trống Last Name, hệ thống yêu cầu nhập Last Name.

##### Test Steps

1. Nhập 'John' vào ô 'First Name'.
2. Để trống ô 'Last Name' và 'Postal Code'.
3. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống từ chối chuyển bước. Xuất hiện thông báo lỗi: 'Error: Last Name is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: First Name hợp lệ + Last Name rỗng.

#### [TC-29] Kiểm tra thông báo lỗi khi nhập First Name, Last Name nhưng để trống Postal Code

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-29 |
| **Name** | Kiểm tra thông báo lỗi khi nhập First Name, Last Name nhưng để trống Postal Code |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-17 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: Doe | Postal Code: '' |
| **Postcondition** | Người dùng ở lại màn hình Bước 1. |

##### Objective
Xác minh khi người dùng đã nhập First Name và Last Name nhưng bỏ trống mã bưu điện, hệ thống yêu cầu nhập Postal Code.

##### Test Steps

1. Nhập 'John' vào First Name và 'Doe' vào Last Name.
2. Để trống ô 'Zip/Postal Code'.
3. Nhấp vào nút 'Continue'.

##### Expected Result

Hệ thống chặn chuyển bước và hiển thị thông báo lỗi: 'Error: Postal Code is required'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Tên hợp lệ + Mã bưu điện rỗng.

#### [TC-30] Kiểm tra xử lý các định dạng mã bưu điện đặc biệt và quốc tế (BVA & EP)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-30 |
| **Name** | Kiểm tra xử lý các định dạng mã bưu điện đặc biệt và quốc tế (BVA & EP) |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-18 |
| **Test Type** | Boundary / Equivalence |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: Jane | Last Name: Smith | Postal Code: 'SW1A 1AA' (UK) và '700000' (VN) |
| **Postcondition** | Chuyển bước thành công sang Checkout Bước 2. |

##### Objective
Xác minh cách hệ thống xử lý các định dạng mã bưu điện quốc tế (gồm cả chữ và số như Anh, Canada hoặc số bưu điện Việt Nam).

##### Test Steps

1. Nhập First Name: 'Jane', Last Name: 'Smith'.
2. Nhập mã bưu điện dạng chữ và số 'SW1A 1AA' rồi nhấn 'Continue'.
3. Quay lại Bước 1, nhập mã bưu điện dạng 6 chữ số '700000' rồi nhấn 'Continue'.

##### Expected Result

Hệ thống chấp nhận các định dạng mã bưu điện hợp lệ và điều hướng thành công đến màn hình tổng quan '/checkout-step-two.html'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính linh hoạt của trường Postal Code đối với định dạng quốc tế.

#### [TC-31] Kiểm tra nút 'Cancel' tại Bước 1 quay lại giỏ hàng và giữ nguyên các sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-31 |
| **Name** | Kiểm tra nút 'Cancel' tại Bước 1 quay lại giỏ hàng và giữ nguyên các sản phẩm |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-19 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-one.html'. |
| **Test Data** | Nút: 'Cancel' (id='cancel') |
| **Postcondition** | Người dùng quay về trang giỏ hàng. |

##### Objective
Đảm bảo nút 'Cancel' tại Bước 1 hủy thao tác nhập thông tin và đưa người dùng quay lại '/cart.html' mà không xóa giỏ hàng.

##### Test Steps

1. Nhấp vào nút 'Cancel' trên trang Bước 1.

##### Expected Result

Trình duyệt điều hướng quay lại trang 'https://www.saucedemo.com/cart.html'. Danh sách các sản phẩm đã chọn trước đó vẫn giữ nguyên vẹn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hủy thao tác thanh toán.

#### [TC-32] Kiểm tra nhập thông tin hợp lệ tại Bước 1 chuyển sang màn hình Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-32 |
| **Name** | Kiểm tra nhập thông tin hợp lệ tại Bước 1 chuyển sang màn hình Bước 2 |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-16 |
| **Test Type** | Functional / Smoke |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: Doe | Postal Code: 94103 |
| **Postcondition** | Người dùng đang ở màn hình Checkout Bước 2. |

##### Objective
Đảm bảo khi điền đầy đủ và hợp lệ First Name, Last Name và Postal Code thì hệ thống chuyển sang trang tổng quan đơn hàng.

##### Test Steps

1. Nhập 'John' vào First Name.
2. Nhập 'Doe' vào Last Name.
3. Nhập '94103' vào Zip/Postal Code.
4. Nhấp vào nút 'Continue'.

##### Expected Result

Chuyển hướng thành công đến 'https://www.saucedemo.com/checkout-step-two.html'. Tiêu đề phụ hiển thị 'Checkout: Overview'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Chuyển tiếp Happy Path từ Bước 1 sang Bước 2.

#### [TC-33] Kiểm tra màn hình Bước 2 hiển thị đúng sản phẩm, thông tin thanh toán và giao hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-33 |
| **Name** | Kiểm tra màn hình Bước 2 hiển thị đúng sản phẩm, thông tin thanh toán và giao hàng |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Functional / Checkout |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã hoàn thành Bước 1 với 2 sản phẩm: Backpack (\$29.99) và Bike Light (\$9.99). |
| **Test Data** | Sản phẩm: Backpack (\$29.99) & Bike Light (\$9.99) |
| **Postcondition** | Thông tin tổng quan đơn hàng được xác thực. |

##### Objective
Xác minh màn hình tổng quan đơn hàng hiển thị đúng danh sách mặt hàng, mã thanh toán 'SauceCard #31437' và đơn vị vận chuyển 'Free Pony Express Delivery!'.

##### Test Steps

1. Kiểm tra danh sách các dòng sản phẩm hiển thị trên trang.
2. Kiểm tra mục 'Payment Information'.
3. Kiểm tra mục 'Shipping Information'.

##### Expected Result

Hiển thị đúng 2 sản phẩm với QTY = 1. Mục Payment Information hiển thị 'SauceCard #31437'. Mục Shipping Information hiển thị 'Free Pony Express Delivery!'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hiển thị dữ liệu tĩnh tại Bước 2.

#### [TC-34] Kiểm tra tính toán chính xác Item Total, Tax (8%) và Grand Total tại Checkout Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-34 |
| **Name** | Kiểm tra tính toán chính xác Item Total, Tax (8%) và Grand Total tại Checkout Bước 2 |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Functional / Calculation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở '/checkout-step-two.html' với Backpack (\$29.99) và Bike Light (\$9.99). |
| **Test Data** | Tiền hàng: \$29.99 + \$9.99 = \$39.98. Thuế suất 8%: \$39.98 * 0.08 = \$3.1984 -> làm tròn \$3.20. Tổng cộng: \$43.18. |
| **Postcondition** | Các con số tài chính được xác minh chính xác tuyệt đối. |

##### Objective
Kiểm chứng bằng toán học: Item Total bằng tổng đơn giá các sản phẩm; Tax được tính chính xác bằng 8% tổng tiền hàng; Total bằng Item Total cộng Tax.

##### Test Steps

1. Đọc giá trị hiển thị tại 'Item total:'.
2. Tính toán tiền thuế kỳ vọng: 39.98 * 0.08 = 3.20.
3. Đọc giá trị hiển thị tại 'Tax:'.
4. Đọc giá trị hiển thị tại 'Total:'.

##### Expected Result

Item total hiển thị chính xác 'Item total: \$39.98'. Thuế hiển thị chính xác 'Tax: \$3.20'. Tổng thanh toán hiển thị chính xác 'Total: \$43.18' (\$39.98 + \$3.20 = \$43.18).

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra logic tài chính và công thức tính thuế quan trọng.

#### [TC-35] Kiểm tra nút 'Cancel' tại Bước 2 đưa người dùng về trang danh mục và giữ nguyên giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-35 |
| **Name** | Kiểm tra nút 'Cancel' tại Bước 2 đưa người dùng về trang danh mục và giữ nguyên giỏ hàng |
| **Folder** | 04_Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-21 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-two.html'. |
| **Test Data** | Nút: 'Cancel' (id='cancel') |
| **Postcondition** | Người dùng ở trang danh mục; giỏ hàng nguyên vẹn. |

##### Objective
Đảm bảo nút 'Cancel' trên trang Bước 2 hủy màn hình tổng quan và đưa người dùng về '/inventory.html' mà không xóa giỏ hàng.

##### Test Steps

1. Nhấp vào nút 'Cancel' trên màn hình Bước 2.
2. Kiểm tra trang hiển thị và huy hiệu giỏ hàng.

##### Expected Result

Chuyển về trang danh mục '/inventory.html'. Huy hiệu giỏ hàng vẫn giữ nguyên số lượng các sản phẩm đã chọn trước đó.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hủy bước xác nhận đơn hàng.

#### [TC-36] Kiểm tra nhấp 'Finish' tại Bước 2 hoàn tất đơn hàng và hiển thị thông điệp thành công

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-36 |
| **Name** | Kiểm tra nhấp 'Finish' tại Bước 2 hoàn tất đơn hàng và hiển thị thông điệp thành công |
| **Folder** | 04_Checkout |
| **Component** | Checkout Complete |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-11 |
| **TestScenarioID** | TS-22 |
| **Test Type** | Functional / Smoke |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-step-two.html'. |
| **Test Data** | Nút: 'Finish' (id='finish') |
| **Postcondition** | Đơn hàng đã được hoàn tất. |

##### Objective
Xác minh khi người dùng nhấp 'Finish' sẽ tạo đơn hàng thành công và chuyển đến màn hình cảm ơn kèm thông điệp giao hàng.

##### Test Steps

1. Nhấp vào nút 'Finish'.
2. Kiểm tra tiêu đề hoàn tất trên trang mới.
3. Kiểm tra thông điệp giao vận.

##### Expected Result

Chuyển hướng đến 'https://www.saucedemo.com/checkout-complete.html'. Tiêu đề chính hiển thị: 'Thank you for your order!'. Dòng thông điệp giao vận hiển thị: 'Your order has been dispatched, and will arrive just as fast as the pony can get there!'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Mốc quan trọng kết thúc quy trình đặt hàng.

#### [TC-37] Kiểm tra làm mới và xóa huy hiệu giỏ hàng sau khi hoàn tất đặt hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-37 |
| **Name** | Kiểm tra làm mới và xóa huy hiệu giỏ hàng sau khi hoàn tất đặt hàng |
| **Folder** | 04_Checkout |
| **Component** | Checkout Complete |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-11 |
| **TestScenarioID** | TS-22 |
| **Test Type** | Functional / Cart Reset |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng vừa hoàn tất đơn hàng và đang ở trang '/checkout-complete.html'. |
| **Test Data** | Kiểm tra phần tử giỏ hàng |
| **Postcondition** | Giỏ hàng rỗng hoàn toàn. |

##### Objective
Đảm bảo sau khi đặt hàng thành công, giỏ hàng được làm sạch và huy hiệu số lượng trên biểu tượng giỏ hàng biến mất hoàn toàn.

##### Test Steps

1. Quan sát biểu tượng giỏ hàng ở góc phải trên cùng màn hình.
2. Kiểm tra sự tồn tại của phần tử huy hiệu '.shopping_cart_badge'.

##### Expected Result

Biểu tượng giỏ hàng hoàn toàn trống, không còn hiển thị bất kỳ con số nào. Giỏ hàng đã được giải phóng sạch sẽ.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra làm sạch trạng thái giỏ hàng sau khi mua sắm.

#### [TC-38] Kiểm tra nút 'Back Home' trên màn hình hoàn tất đưa người dùng về lại trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-38 |
| **Name** | Kiểm tra nút 'Back Home' trên màn hình hoàn tất đưa người dùng về lại trang danh mục |
| **Folder** | 04_Checkout |
| **Component** | Checkout Complete |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-11 |
| **TestScenarioID** | TS-22 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang '/checkout-complete.html'. |
| **Test Data** | Nút: 'Back Home' (id='back-to-products') |
| **Postcondition** | Người dùng ở trang danh mục sản phẩm. |

##### Objective
Đảm bảo nút 'Back Home' tại màn hình Checkout Complete đưa người dùng quay lại trang sản phẩm sẵn sàng cho phiên mua sắm mới.

##### Test Steps

1. Nhấp vào nút 'Back Home'.

##### Expected Result

Chuyển hướng về 'https://www.saucedemo.com/inventory.html'. Toàn bộ các sản phẩm trên danh mục hiển thị nút 'Add to cart'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra luồng quay lại trang chủ mua sắm.

---

<a id="tc-folder-05_sidebar_navigation"></a>
### 05_Sidebar_Navigation

#### [TC-39] Kiểm tra mở menu Sidebar bằng biểu tượng hamburger và đóng bằng nút 'X'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-39 |
| **Name** | Kiểm tra mở menu Sidebar bằng biểu tượng hamburger và đóng bằng nút 'X' |
| **Folder** | 05_Sidebar_Navigation |
| **Component** | Sidebar Menu |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-24 |
| **Test Type** | UI / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập và đang ở trang '/inventory.html'. |
| **Test Data** | Hamburger ID: 'react-burger-menu-btn' | Nút đóng ID: 'react-burger-cross-btn' |
| **Postcondition** | Menu Sidebar đã được đóng. |

##### Objective
Xác minh menu trượt mở ra mượt mà hiển thị 4 liên kết điều hướng và đóng lại bình thường khi nhấp vào nút 'X'.

##### Test Steps

1. Nhấp vào biểu tượng 3 gạch hamburger ở góc trái trên cùng.
2. Kiểm tra menu trượt hiển thị đủ 4 liên kết: All Items, About, Logout, Reset App State.
3. Nhấp vào nút 'X' để đóng menu.

##### Expected Result

Menu trượt mở ra bình thường hiển thị đầy đủ 4 liên kết chức năng; khi nhấp nút 'X' thì menu đóng lại và trả lại tầm nhìn cho màn hình chính.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra giao diện ngăn kéo (drawer component).

#### [TC-40] Kiểm tra chức năng 'Reset App State' xóa sạch giỏ hàng và đặt lại các nút về 'Add to cart'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-40 |
| **Name** | Kiểm tra chức năng 'Reset App State' xóa sạch giỏ hàng và đặt lại các nút về 'Add to cart' |
| **Folder** | 05_Sidebar_Navigation |
| **Component** | Sidebar Menu / App State |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / App State |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã thêm 2 sản phẩm vào giỏ hàng tại '/inventory.html' (huy hiệu hiển thị '2'). |
| **Test Data** | Liên kết: 'Reset App State' (id='reset_sidebar_link') |
| **Postcondition** | Trạng thái ứng dụng được khôi phục về ban đầu. |

##### Objective
Đảm bảo nhấp vào 'Reset App State' trong menu Sidebar sẽ đặt lại toàn bộ trạng thái ứng dụng về mặc định.

##### Test Steps

1. Mở menu Sidebar.
2. Nhấp vào liên kết 'Reset App State'.
3. Đóng menu Sidebar và quan sát trang danh mục.

##### Expected Result

Huy hiệu giỏ hàng lập tức biến mất (giỏ hàng rỗng). Tất cả các nút sản phẩm trên danh mục đang ở trạng thái 'Remove' tự động đổi về 'Add to cart'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Chức năng trọng yếu phục vụ kiểm thử quản lý trạng thái.

#### [TC-41] Kiểm tra liên kết 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-41 |
| **Name** | Kiểm tra liên kết 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs |
| **Folder** | 05_Sidebar_Navigation |
| **Component** | Sidebar Menu |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-26 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập vào hệ thống. |
| **Test Data** | Liên kết: 'About' (id='about_sidebar_link') |
| **Postcondition** | Người dùng được chuyển đến trang ngoài của Sauce Labs. |

##### Objective
Xác minh nhấp vào mục 'About' sẽ mở website giới thiệu của tập đoàn Sauce Labs.

##### Test Steps

1. Mở menu Sidebar.
2. Nhấp vào liên kết 'About'.

##### Expected Result

Trình duyệt điều hướng thành công đến website chính thức 'https://saucelabs.com/'.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra liên kết ra website bên ngoài.

---

<a id="tc-folder-06_end_to_end"></a>
### 06_End_to_End

#### [TC-42] Kiểm tra toàn diện quy trình mua sắm End-to-End từ đăng nhập đến thanh toán và đăng xuất

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-42 |
| **Name** | Kiểm tra toàn diện quy trình mua sắm End-to-End từ đăng nhập đến thanh toán và đăng xuất |
| **Folder** | 06_End_to_End |
| **Component** | End-to-End E-Commerce Flow |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-13 |
| **TestScenarioID** | TS-28 |
| **Test Type** | E2E / Smoke / Business Flow |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt sạch, tài khoản 'standard_user' / 'secret_sauce'. |
| **Test Data** | User: standard_user | Sắp xếp: Price (low to high) | Mua: Onesie (\$7.99) & Bike Light (\$9.99) | Người nhận: John Doe, 94103 |
| **Postcondition** | Đơn hàng hoàn tất, phiên kết thúc, quay về màn hình đăng nhập. |

##### Objective
Thực hiện luồng nghiệp vụ mua hàng trọn vẹn xuyên suốt mọi module: Đăng nhập -> Sắp xếp -> Chọn mua nhiều món -> Kiểm tra giỏ hàng -> Nhập địa chỉ -> Kiểm tra tiền & thuế -> Hoàn tất -> Đăng xuất.

##### Test Steps

1. Truy cập 'https://www.saucedemo.com/' và đăng nhập bằng 'standard_user' / 'secret_sauce'.
2. Sắp xếp danh mục theo 'Price (low to high)'.
3. Thêm 'Sauce Labs Onesie' (\$7.99) và 'Sauce Labs Bike Light' (\$9.99) vào giỏ hàng.
4. Mở trang giỏ hàng kiểm tra danh sách rồi nhấn 'Checkout'.
5. Nhập First Name: 'John', Last Name: 'Doe', Zip: '94103' rồi nhấn 'Continue'.
6. Kiểm tra các con số tài chính: Subtotal \$17.98, Tax \$1.44, Total \$19.42.
7. Nhấp nút 'Finish' để chốt đơn hàng.
8. Nhấp 'Back Home' quay về trang chủ rồi mở Sidebar chọn 'Logout'.

##### Expected Result

Toàn bộ chu trình mua hàng diễn ra trôi chảy, không phát sinh lỗi. Tính toán tài chính chuẩn xác (\$17.98 + \$1.44 = \$19.42), giỏ hàng được làm sạch sau khi mua và đăng xuất an toàn.

##### Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử End-to-End Regression Master bao phủ toàn bộ các module tích hợp.

---

