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
