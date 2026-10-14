## Epic: EPIC-08 - Non-Functional Quality Attributes & Security Standards

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-08 |
| **Name** | Non-Functional Quality Attributes & Security Standards |
| **Issue Type** | Epic |
| **Priority** | Medium |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 2 Stories (US-16, US-17) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Đánh giá các tiêu chuẩn chất lượng phi chức năng bao gồm: Bảo mật phiên & đầu vào, Hiệu năng đáp ứng (SLA), Trải nghiệm người dùng (Usability), Khả năng tiếp cận (Accessibility - WCAG 2.1) và Tương thích đa thiết bị/đa trình duyệt.

### 2. Included User Stories Breakdown

#### [US-16] Bảo mật thông tin phiên làm việc và chống tiêm mã độc hại (XSS/Session Security)
- **Priority:** High
- **As a:** Chuyên viên kiểm thử bảo mật (Security Tester)
- **I want:** hệ thống bảo vệ cookie phiên và làm sạch các dữ liệu đầu vào người dùng
- **So that:** ngăn ngừa rủi ro đánh cắp phiên và tấn công tiêm mã Cross-Site Scripting (XSS)
- **Acceptance Criteria:**
  - **AC1:** Cookie phiên 'session-username' và các cookie nhạy cảm phải được gắn cờ Secure, HttpOnly và SameSite=Strict.
  - **AC2:** Các trường nhập liệu (Username, First Name, Last Name, Postal Code) phải làm sạch hoặc mã hóa ký tự HTML/Script nguy hiểm (<script>, img onerror), không kích hoạt mã độc hại.
  - **AC3:** Sau khi đăng xuất, các trang nhạy cảm phía sau đăng nhập (/inventory.html, /cart.html) không thể được khôi phục hoặc xem lại thông qua bộ nhớ đệm lịch sử trình duyệt (Browser Cache / History Back).

#### [US-17] Tối ưu hiệu năng, khả năng tiếp cận, trải nghiệm người dùng và tương thích đa nền tảng
- **Priority:** Medium
- **As a:** Khách hàng truy cập đa thiết bị và người dùng có nhu cầu trợ năng
- **I want:** ứng dụng tải nhanh dưới 2 giây, giao diện hiển thị chuẩn xác trên mobile/desktop, tương phản màu tốt và hỗ trợ điều hướng bàn phím
- **So that:** tôi có thể mua sắm thuận tiện trên mọi thiết bị và điều kiện sử dụng
- **Acceptance Criteria:**
  - **AC1:** Thời gian tải trang (Page Load Time / DOMContentLoaded) dưới điều kiện mạng thông thường phải nhỏ hơn hoặc bằng 2.0 giây đối với tài khoản tiêu chuẩn.
  - **AC2:** Ứng dụng hỗ trợ điều hướng hoàn toàn bằng phím Tab (Focus ring rõ nét) và các nút thao tác icon có thuộc tính aria-label / title theo chuẩn WCAG 2.1 AA.
  - **AC3:** Giao diện hiển thị phản hồi mượt mà, không bị vỡ layout, lệch hàng cột hoặc tràn nội dung trên các kích thước màn hình di động (Viewport 375x812) và các trình duyệt Chrome, Firefox, Safari.

### 3. Key Risks & QA Strategy
Tấn công Cross-Site Scripting (XSS), vi phạm thuộc tính Cookie bảo mật, vi phạm SLA thời gian phản hồi trang (>2s), lỗi giao diện trên thiết bị di động (Responsive), và rào cản tiếp cận cho người khuyết tật.
