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
