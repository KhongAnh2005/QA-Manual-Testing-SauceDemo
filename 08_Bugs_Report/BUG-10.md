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
