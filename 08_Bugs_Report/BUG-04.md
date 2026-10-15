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
