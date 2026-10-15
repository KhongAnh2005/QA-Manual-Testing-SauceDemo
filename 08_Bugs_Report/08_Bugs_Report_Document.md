# Defect & Bug Reports Document: SauceDemo E-Commerce Web Application

Document ID: BRD-SAUCEDEMO-01  
Author: QA - Khổng Đức Anh  
Date: 28/09/2026  
Total Defects Discovered: 10 Bugs  
Status: Active Backlog (Jira-Ready)  

---

## Mục Lục

- [1. Master Defect Log Table](#1-master-defect-log-table)
- [2. Chi Tiết Các Báo Cáo Lỗi](#2-chi-tiet-cac-bao-cao-loi)

---

<a id="1-master-defect-log-table"></a>
## 1. Master Defect Log Table

| Bug ID | Title (Tiếng Việt) | Component | Severity | Priority | Linked TC | Evidence |
|:---|:---|:---|:---:|:---:|:---:|:---:|
| [BUG-01](#bug-01) | Hình ảnh tất cả sản phẩm hiển thị ảnh lỗi 404 (sl-404.jpg) đối với tài khoản problem_user | Inventory / Product Catalog | Medium | High | [TC-17](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-17%20-%20BUG-01_Problem_User_Broken_Images.png) |
| [BUG-02](#bug-02) | Bộ lọc sắp xếp kích hoạt popup alert 'Sorting is broken!' và không sắp xếp lại đối với tài khoản error_user | Inventory Sorting | Medium | Medium | [TC-18](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-18%20-%20BUG-02_Error_User_Sort_Alert_Popup.png) |
| [BUG-03](#bug-03) | Nút 'Remove' không hoạt động, không thể xóa sản phẩm Fleece Jacket khỏi giỏ hàng đối với tài khoản problem_user | Shopping Cart & Inventory | High | High | [TC-28](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-28%20-%20BUG-03_Problem_User_Remove_Button_Failure.png) |
| [BUG-04](#bug-04) | Hệ thống cho phép thanh toán giỏ hàng rỗng (Empty Cart Checkout $0.00) mà không có cảnh báo hay chặn luồng | Shopping Cart & Checkout Flow | High | High | [TC-29](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-29%20-%20BUG-04_Empty_Cart_Checkout_Allowed.png) |
| [BUG-05](#bug-05) | Trường nhập 'Last Name' tại form Checkout Step 1 không ghi nhận giá trị và chặn đứng quy trình thanh toán đối với tài khoản problem_user | Checkout Step One | High | High | [TC-43](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-43%20-%20BUG-05_Problem_User_Checkout_LastName_Blocked.png) |
| [BUG-06](#bug-06) | Nhấp nút 'Finish' tại Checkout Step 2 phát sinh lỗi ngoại lệ Runtime (La.cesetRart is not a function) đối với tài khoản error_user | Checkout Step Two | Critical | High | [TC-44](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-44%20-%20BUG-06_Error_User_Finish_Button_Runtime_Crash.png) |
| [BUG-07](#bug-07) | Liên kết điều hướng 'About' trong Sidebar menu trỏ sai URL dẫn đến trang lỗi 404 Not Found đối với tài khoản problem_user | Menu & Navigation Sidebar | Medium | Medium | [TC-49](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-49%20-%20BUG-07_Problem_User_About_Link_404_Error.png) |
| [BUG-08](#bug-08) | Vi phạm nghiêm trọng SLA thời gian phản hồi (>5.0s) do vòng lặp trễ nhân tạo trên trang danh mục đối với tài khoản performance_glitch_user | Performance SLA / Response Time | Medium | Medium | [TC-62](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-62%20-%20BUG-08_Performance_Glitch_5s_Latency_Loop.png) |
| [BUG-09](#bug-09) | Cookie phiên làm việc 'session-username' thiếu cờ bảo mật HttpOnly và Secure, gây nguy cơ rò rỉ phiên kiểm thử (Session Hijacking) | Security / Session Cookie | High | High | [TC-63](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-63%20-%20BUG-09_Security_Cookie_Missing_HttpOnly_Flag.png) |
| [BUG-10](#bug-10) | Giao diện vỡ layout, icon giỏ hàng và nút Checkout bị dịch chuyển lệch vị trí đối với tài khoản visual_user | UI Layout / Visual Regression | Low | Low | [TC-69](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [Screenshot](../Evidence/Screenshots/TC-69%20-%20BUG-10_Visual_User_Header_Layout_Misaligned.png) |

---

<a id="2-chi-tiet-cac-bao-cao-loi"></a>
## 2. Chi Tiết Các Báo Cáo Lỗi

<a id="bug-01"></a>

### [BUG-01] Hình ảnh tất cả sản phẩm hiển thị ảnh lỗi 404 (sl-404.jpg) đối với tài khoản problem_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-01 |
| **Title** | Hình ảnh tất cả sản phẩm hiển thị ảnh lỗi 404 (sl-404.jpg) đối với tài khoản problem_user |
| **Component** | Inventory / Product Catalog |
| **Severity** | Medium |
| **Priority** | High |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-17](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-04](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-07](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Toàn bộ 6 sản phẩm trên danh mục đều hiển thị chung một hình ảnh chú chó kèm thẻ 404 ('sl-404.jpg'). Mã nguồn React cố tình gán URL ảnh thành 'sl-404.jpg' khi người dùng là problem_user.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): problem_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona problem_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Truy cập vào trang web 'https://www.saucedemo.com/'.
2. Nhập username 'problem_user' và password 'secret_sauce'.
3. Nhấp vào nút 'Login'.
4. Quan sát hình ảnh đại diện của tất cả 6 sản phẩm tại trang '/inventory.html'.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Tất cả 6 sản phẩm hiển thị đúng hình ảnh tương ứng (Balo hiển thị ảnh Balo, Đèn xe đạp hiển thị ảnh Đèn...). Không có hình ảnh nào bị vỡ hoặc trỏ đến đường dẫn tài nguyên lỗi. | Toàn bộ 6 sản phẩm trên danh mục đều hiển thị chung một hình ảnh chú chó kèm thẻ 404 ('sl-404.jpg'). Mã nguồn React cố tình gán URL ảnh thành 'sl-404.jpg' khi người dùng là problem_user. |

#### 6. Visual Evidence

![BUG-01 Evidence](../Evidence/Screenshots/TC-17%20-%20BUG-01_Problem_User_Broken_Images.png)

#### 7. Business Impact

- Severity (Medium): Ảnh hưởng đến luồng vận hành của phân hệ Inventory / Product Catalog.
- Priority (High): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-01.md](BUG-01.md)

---

<a id="bug-02"></a>

### [BUG-02] Bộ lọc sắp xếp kích hoạt popup alert 'Sorting is broken!' và không sắp xếp lại đối với tài khoản error_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-02 |
| **Title** | Bộ lọc sắp xếp kích hoạt popup alert 'Sorting is broken!' và không sắp xếp lại đối với tài khoản error_user |
| **Component** | Inventory Sorting |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-18](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-04](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-08](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Trình duyệt bắn ra một popup alert chặn luồng người dùng với nội dung: 'Sorting is broken! This error has been reported to Backtrace.' và danh sách sản phẩm không được sắp xếp lại.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): error_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona error_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'error_user' và password 'secret_sauce'.
2. Tại trang danh mục '/inventory.html', nhấp vào dropdown sắp xếp ('data-test=product-sort-container').
3. Chọn tùy chọn sắp xếp 'Price (low to high)'.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Danh sách sản phẩm được sắp xếp lại theo giá tiền tăng dần (\$7.99 -> \$49.99). Không có hộp thoại popup alert nào của trình duyệt xuất hiện làm gián đoạn người dùng. | Trình duyệt bắn ra một popup alert chặn luồng người dùng với nội dung: 'Sorting is broken! This error has been reported to Backtrace.' và danh sách sản phẩm không được sắp xếp lại. |

#### 6. Visual Evidence

![BUG-02 Evidence](../Evidence/Screenshots/TC-18%20-%20BUG-02_Error_User_Sort_Alert_Popup.png)

#### 7. Business Impact

- Severity (Medium): Ảnh hưởng đến luồng vận hành của phân hệ Inventory Sorting.
- Priority (Medium): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-02.md](BUG-02.md)

---

<a id="bug-03"></a>

### [BUG-03] Nút 'Remove' không hoạt động, không thể xóa sản phẩm Fleece Jacket khỏi giỏ hàng đối với tài khoản problem_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-03 |
| **Title** | Nút 'Remove' không hoạt động, không thể xóa sản phẩm Fleece Jacket khỏi giỏ hàng đối với tài khoản problem_user |
| **Component** | Shopping Cart & Inventory |
| **Severity** | High |
| **Priority** | High |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-28](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-07](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-14](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Nút 'Remove' hoàn toàn không phản hồi khi nhấp. Sản phẩm không bị xóa khỏi giỏ hàng, nút vẫn giữ nguyên trạng thái 'Remove' và badge giỏ hàng không giảm.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): problem_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona problem_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'problem_user'.
2. Thêm sản phẩm 'Sauce Labs Fleece Jacket' (hoặc bất kỳ sản phẩm có ID chẵn) vào giỏ hàng.
3. Chuyển vào trang giỏ hàng '/cart.html'.
4. Nhấp chuột vào nút 'Remove' của sản phẩm Fleece Jacket.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Nút 'Remove' chuyển lại thành 'Add to cart' và huy hiệu giỏ hàng giảm từ 1 về 0 (biến mất hoàn toàn). | Nút 'Remove' hoàn toàn không phản hồi khi nhấp. Sản phẩm không bị xóa khỏi giỏ hàng, nút vẫn giữ nguyên trạng thái 'Remove' và badge giỏ hàng không giảm. |

#### 6. Visual Evidence

![BUG-03 Evidence](../Evidence/Screenshots/TC-28%20-%20BUG-03_Problem_User_Remove_Button_Failure.png)

#### 7. Business Impact

- Severity (High): Ảnh hưởng đến luồng vận hành của phân hệ Shopping Cart & Inventory.
- Priority (High): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-03.md](BUG-03.md)

---

<a id="bug-04"></a>

### [BUG-04] Hệ thống cho phép thanh toán giỏ hàng rỗng (Empty Cart Checkout $0.00) mà không có cảnh báo hay chặn luồng

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-04 |
| **Title** | Hệ thống cho phép thanh toán giỏ hàng rỗng (Empty Cart Checkout $0.00) mà không có cảnh báo hay chặn luồng |
| **Component** | Shopping Cart & Checkout Flow |
| **Severity** | High |
| **Priority** | High |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-29](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-08](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-15](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Hệ thống vẫn cho phép chuyển hướng sang '/checkout-step-one.html', cho phép điền thông tin và hoàn tất đơn hàng \$0.00 tại '/checkout-complete.html' mà không có bất kỳ rào cản kiểm tra số lượng sản phẩm nào.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): standard_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona standard_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'standard_user'.
2. Không thêm bất kỳ sản phẩm nào vào giỏ hàng (giỏ hàng rỗng, badge không hiển thị).
3. Nhấp vào biểu tượng giỏ hàng để chuyển tới '/cart.html'.
4. Nhấp vào nút 'Checkout'.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Nút 'Checkout' bị vô hiệu hóa (disabled), hoặc khi nhấp vào hệ thống hiển thị thông báo cảnh báo 'Your cart is empty. Please add items before checkout.' và giữ người dùng ở lại trang giỏ hàng, không cho phép chuyển tiếp sang trang thanh toán. | Hệ thống vẫn cho phép chuyển hướng sang '/checkout-step-one.html', cho phép điền thông tin và hoàn tất đơn hàng \$0.00 tại '/checkout-complete.html' mà không có bất kỳ rào cản kiểm tra số lượng sản phẩm nào. |

#### 6. Visual Evidence

![BUG-04 Evidence](../Evidence/Screenshots/TC-29%20-%20BUG-04_Empty_Cart_Checkout_Allowed.png)

#### 7. Business Impact

- Severity (High): Ảnh hưởng đến luồng vận hành của phân hệ Shopping Cart & Checkout Flow.
- Priority (High): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-04.md](BUG-04.md)

---

<a id="bug-05"></a>

### [BUG-05] Trường nhập 'Last Name' tại form Checkout Step 1 không ghi nhận giá trị và chặn đứng quy trình thanh toán đối với tài khoản problem_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-05 |
| **Title** | Trường nhập 'Last Name' tại form Checkout Step 1 không ghi nhận giá trị và chặn đứng quy trình thanh toán đối với tài khoản problem_user |
| **Component** | Checkout Step One |
| **Severity** | High |
| **Priority** | High |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-43](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-17](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Hệ thống từ chối chuyển trang và hiển thị thông báo lỗi màu đỏ: 'Error: Last Name is required' mặc dù người dùng đã nhập đầy đủ ký tự vào ô Last Name. Dữ liệu nhập vào Last Name thực chất đã bị ghi đè vào state của First Name.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): problem_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona problem_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'problem_user'.
2. Thêm sản phẩm vào giỏ và tiến hành thanh toán đến trang '/checkout-step-one.html'.
3. Nhập 'John' vào ô 'First Name'.
4. Nhập 'Smith' vào ô 'Last Name'.
5. Nhập '90210' vào ô 'Postal Code'.
6. Nhấp vào nút 'Continue'.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Ô 'Last Name' hiển thị đầy đủ chuỗi 'Smith'. Khi nhấp 'Continue', hệ thống lưu trữ thông tin và điều hướng thành công đến '/checkout-step-two.html'. | Hệ thống từ chối chuyển trang và hiển thị thông báo lỗi màu đỏ: 'Error: Last Name is required' mặc dù người dùng đã nhập đầy đủ ký tự vào ô Last Name. Dữ liệu nhập vào Last Name thực chất đã bị ghi đè vào state của First Name. |

#### 6. Visual Evidence

![BUG-05 Evidence](../Evidence/Screenshots/TC-43%20-%20BUG-05_Problem_User_Checkout_LastName_Blocked.png)

#### 7. Business Impact

- Severity (High): Ảnh hưởng đến luồng vận hành của phân hệ Checkout Step One.
- Priority (High): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-05.md](BUG-05.md)

---

<a id="bug-06"></a>

### [BUG-06] Nhấp nút 'Finish' tại Checkout Step 2 phát sinh lỗi ngoại lệ Runtime (La.cesetRart is not a function) đối với tài khoản error_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-06 |
| **Title** | Nhấp nút 'Finish' tại Checkout Step 2 phát sinh lỗi ngoại lệ Runtime (La.cesetRart is not a function) đối với tài khoản error_user |
| **Component** | Checkout Step Two |
| **Severity** | Critical |
| **Priority** | High |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-44](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-11](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-22](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Nút 'Finish' không chuyển trang. Console trình duyệt xuất hiện lỗi: 'Uncaught TypeError: La.cesetRart is not a function'. Đơn hàng không thể được xác nhận hoàn tất.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): error_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona error_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'error_user'.
2. Thêm sản phẩm có ID chẵn (ví dụ: Bike Light) vào giỏ hàng.
3. Chuyển tới Checkout Step 1, điền First Name và Zip Code (bỏ trống Last Name để tránh crash).
4. Nhấp 'Continue' để tới '/checkout-step-two.html'.
5. Nhấp vào nút 'Finish'.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Hệ thống tiếp nhận đơn hàng thành công và chuyển hướng đến '/checkout-complete.html' kèm thông báo 'Thank you for your order!'. | Nút 'Finish' không chuyển trang. Console trình duyệt xuất hiện lỗi: 'Uncaught TypeError: La.cesetRart is not a function'. Đơn hàng không thể được xác nhận hoàn tất. |

#### 6. Visual Evidence

![BUG-06 Evidence](../Evidence/Screenshots/TC-44%20-%20BUG-06_Error_User_Finish_Button_Runtime_Crash.png)

#### 7. Business Impact

- Severity (Critical): Ảnh hưởng đến luồng vận hành của phân hệ Checkout Step Two.
- Priority (High): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-06.md](BUG-06.md)

---

<a id="bug-07"></a>

### [BUG-07] Liên kết điều hướng 'About' trong Sidebar menu trỏ sai URL dẫn đến trang lỗi 404 Not Found đối với tài khoản problem_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-07 |
| **Title** | Liên kết điều hướng 'About' trong Sidebar menu trỏ sai URL dẫn đến trang lỗi 404 Not Found đối với tài khoản problem_user |
| **Component** | Menu & Navigation Sidebar |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-49](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-13](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-26](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Trình duyệt điều hướng sang đường dẫn lỗi 'https://saucelabs.com/error/404', hiển thị màn hình 404 Page Not Found của Sauce Labs.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): problem_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona problem_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'problem_user'.
2. Nhấp vào biểu tượng hamburger menu góc trên bên trái để mở Sidebar.
3. Nhấp vào mục liên kết 'About' ('#about_sidebar_link').

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Trình duyệt chuyển hướng thành công đến trang chủ chính thức 'https://saucelabs.com/' với mã trạng thái HTTP 200 OK. | Trình duyệt điều hướng sang đường dẫn lỗi 'https://saucelabs.com/error/404', hiển thị màn hình 404 Page Not Found của Sauce Labs. |

#### 6. Visual Evidence

![BUG-07 Evidence](../Evidence/Screenshots/TC-49%20-%20BUG-07_Problem_User_About_Link_404_Error.png)

#### 7. Business Impact

- Severity (Medium): Ảnh hưởng đến luồng vận hành của phân hệ Menu & Navigation Sidebar.
- Priority (Medium): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-07.md](BUG-07.md)

---

<a id="bug-08"></a>

### [BUG-08] Vi phạm nghiêm trọng SLA thời gian phản hồi (>5.0s) do vòng lặp trễ nhân tạo trên trang danh mục đối với tài khoản performance_glitch_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-08 |
| **Title** | Vi phạm nghiêm trọng SLA thời gian phản hồi (>5.0s) do vòng lặp trễ nhân tạo trên trang danh mục đối với tài khoản performance_glitch_user |
| **Component** | Performance SLA / Response Time |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-62](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Trang web bị đóng băng (treo cứng UI) trong đúng 5.091 giây (>5000ms), vi phạm nghiêm trọng ngưỡng chấp nhận trải nghiệm người dùng (SLA Performance).

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): performance_glitch_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona performance_glitch_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Mở trang đăng nhập 'https://www.saucedemo.com/'.
2. Nhập username 'performance_glitch_user' và password 'secret_sauce'.
3. Bấm nút 'Login' và đo thời gian phản hồi cho đến khi trang '/inventory.html' hiển thị hoàn chỉnh.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Trang danh mục tải xong hoàn toàn trong thời gian dưới 2.0 giây, mang lại trải nghiệm mượt mà không có độ trễ bất thường. | Trang web bị đóng băng (treo cứng UI) trong đúng 5.091 giây (>5000ms), vi phạm nghiêm trọng ngưỡng chấp nhận trải nghiệm người dùng (SLA Performance). |

#### 6. Visual Evidence

![BUG-08 Evidence](../Evidence/Screenshots/TC-62%20-%20BUG-08_Performance_Glitch_5s_Latency_Loop.png)

#### 7. Business Impact

- Severity (Medium): Ảnh hưởng đến luồng vận hành của phân hệ Performance SLA / Response Time.
- Priority (Medium): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-08.md](BUG-08.md)

---

<a id="bug-09"></a>

### [BUG-09] Cookie phiên làm việc 'session-username' thiếu cờ bảo mật HttpOnly và Secure, gây nguy cơ rò rỉ phiên kiểm thử (Session Hijacking)

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-09 |
| **Title** | Cookie phiên làm việc 'session-username' thiếu cờ bảo mật HttpOnly và Secure, gây nguy cơ rò rỉ phiên kiểm thử (Session Hijacking) |
| **Component** | Security / Session Cookie |
| **Severity** | High |
| **Priority** | High |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-63](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-16](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-33](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Cookie 'session-username' hoàn toàn không có cờ HttpOnly (HttpOnly=False) và không có cờ Secure. Mã JavaScript phía client có thể đọc và chỉnh sửa cookie này trực tiếp qua 'document.cookie', dẫn tới nguy cơ bị đánh cắp phiên làm việc (Session Hijacking / XSS Exploitation).

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): All Users / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona All Users.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập thành công vào 'https://www.saucedemo.com/'.
2. Mở Chrome DevTools (F12) -> Chuyển vào tab 'Application' -> Mục 'Cookies'.
3. Kiểm tra các thuộc tính bảo mật của cookie 'session-username'.
4. Chuyển sang tab 'Console', gõ lệnh 'document.cookie' và nhấn Enter.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Cookie phiên phải có cờ 'HttpOnly' được bật (ngăn chặn JavaScript client đọc cookie qua document.cookie) và cờ 'Secure' được bật (chỉ truyền qua HTTPS). | Cookie 'session-username' hoàn toàn không có cờ HttpOnly (HttpOnly=False) và không có cờ Secure. Mã JavaScript phía client có thể đọc và chỉnh sửa cookie này trực tiếp qua 'document.cookie', dẫn tới nguy cơ bị đánh cắp phiên làm việc (Session Hijacking / XSS Exploitation). |

#### 6. Visual Evidence

![BUG-09 Evidence](../Evidence/Screenshots/TC-63%20-%20BUG-09_Security_Cookie_Missing_HttpOnly_Flag.png)

#### 7. Business Impact

- Severity (High): Ảnh hưởng đến luồng vận hành của phân hệ Security / Session Cookie.
- Priority (High): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-09.md](BUG-09.md)

---

<a id="bug-10"></a>

### [BUG-10] Giao diện vỡ layout, icon giỏ hàng và nút Checkout bị dịch chuyển lệch vị trí đối với tài khoản visual_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-10 |
| **Title** | Giao diện vỡ layout, icon giỏ hàng và nút Checkout bị dịch chuyển lệch vị trí đối với tài khoản visual_user |
| **Component** | UI Layout / Visual Regression |
| **Severity** | Low |
| **Priority** | Low |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-69](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Biểu tượng giỏ hàng bị dịch chuyển lệch tọa độ bất thường. Nút 'Checkout' bị gán class 'btn_visual_failure' khiến khoảng cách căn lề và style hiển thị bị biến dạng so với quy chuẩn thiết kế.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): visual_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona visual_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'visual_user'.
2. Quan sát thanh Header: vị trí của icon menu hamburger bên trái và biểu tượng giỏ hàng bên phải.
3. Thêm sản phẩm vào giỏ và chuyển đến trang '/cart.html'.
4. Quan sát vị trí và style hiển thị của nút 'Checkout'.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Toàn bộ các biểu tượng căn chỉnh ngay ngắn, đúng lề phải và lề trái theo CSS Grid/Flexbox chuẩn. Không có phần tử nào bị thụt lề, lệch vị trí hoặc chèn đè lên nhau. | Biểu tượng giỏ hàng bị dịch chuyển lệch tọa độ bất thường. Nút 'Checkout' bị gán class 'btn_visual_failure' khiến khoảng cách căn lề và style hiển thị bị biến dạng so với quy chuẩn thiết kế. |

#### 6. Visual Evidence

![BUG-10 Evidence](../Evidence/Screenshots/TC-69%20-%20BUG-10_Visual_User_Header_Layout_Misaligned.png)

#### 7. Business Impact

- Severity (Low): Ảnh hưởng đến luồng vận hành của phân hệ UI Layout / Visual Regression.
- Priority (Low): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).

Xem chi tiết: [BUG-10.md](BUG-10.md)

---
