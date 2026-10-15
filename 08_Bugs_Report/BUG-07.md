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
