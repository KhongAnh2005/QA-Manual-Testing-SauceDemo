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
