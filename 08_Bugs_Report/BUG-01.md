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
