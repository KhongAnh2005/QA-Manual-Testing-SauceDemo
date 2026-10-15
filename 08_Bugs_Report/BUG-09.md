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
