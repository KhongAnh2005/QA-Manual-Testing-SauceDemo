### [BUG-03] Nút 'Remove' không hoạt động, không thể xóa sản phẩm Fleece Jacket khỏi giỏ hàng đối với tài khoản problem_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-03 |
| **Title** | Nút 'Remove' không hoạt động, không thể xóa sản phẩm Bike Light khỏi giỏ hàng đối với tài khoản problem_user |
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
2. Thêm sản phẩm 'Sauce Labs Bike Light' (hoặc bất kỳ sản phẩm có ID chẵn) vào giỏ hàng.
3. Chuyển vào trang giỏ hàng '/cart.html'.
4. Nhấp chuột vào nút 'Remove' của sản phẩm Bike Light.

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
