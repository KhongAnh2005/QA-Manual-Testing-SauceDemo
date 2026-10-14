## Epic: EPIC-01 - Authentication & Session Management

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-01 |
| **Name** | Authentication & Session Management |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 3 Stories (US-01, US-02, US-03) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Quản lý xác thực người dùng, đăng nhập, xử lý tài khoản bị khóa, đăng xuất và kiểm soát quyền truy cập phiên làm việc.

### 2. Included User Stories Breakdown

#### [US-01] Đăng nhập thành công với thông tin tài khoản hợp lệ
- **Priority:** High
- **As a:** Khách hàng tiêu chuẩn (Standard Customer)
- **I want:** đăng nhập vào hệ thống bằng tên người dùng và mật khẩu hợp lệ
- **So that:** tôi có thể truy cập danh mục sản phẩm và tiến hành mua sắm
- **Acceptance Criteria:**
  - **AC1:** Khi người dùng nhập Username 'standard_user' và Password 'secret_sauce' rồi nhấn nút 'Login', hệ thống điều hướng thành công đến trang '/inventory.html'.
  - **AC2:** Trang sản phẩm hiển thị tiêu đề 'Products' và biểu tượng giỏ hàng hiển thị rõ ràng.
  - **AC3:** Cookie phiên 'session-username=standard_user' được khởi tạo và lưu trữ an toàn trong trình duyệt.

#### [US-02] Xử lý lỗi khi đăng nhập không hợp lệ hoặc tài khoản bị khóa
- **Priority:** High
- **As a:** Chuyên viên kiểm thử hệ thống / Người dùng
- **I want:** hệ thống ngăn chặn truy cập trái phép và hiển thị thông báo lỗi rõ ràng khi thông tin đăng nhập bị thiếu, sai hoặc tài khoản bị khóa
- **So that:** bảo vệ an toàn tài khoản và giúp người dùng biết lý do đăng nhập thất bại để sửa đổi
- **Acceptance Criteria:**
  - **AC1:** Nhấn 'Login' khi để trống cả Username và Password hiển thị thông báo lỗi: 'Epic sadface: Username is required'.
  - **AC2:** Nhập Username nhưng để trống Password hiển thị thông báo lỗi: 'Epic sadface: Password is required'.
  - **AC3:** Nhập Username không tồn tại hoặc sai Password hiển thị thông báo lỗi: 'Epic sadface: Username and password do not match any user in this service'.
  - **AC4:** Nhập tài khoản bị khóa 'locked_out_user' và 'secret_sauce' hiển thị thông báo lỗi: 'Epic sadface: Sorry, this user has been locked out.'.
  - **AC5:** Nhấp vào nút 'X' trên thông báo lỗi sẽ đóng thông báo lỗi đó.

#### [US-03] Đăng xuất tài khoản an toàn và hủy phiên làm việc
- **Priority:** High
- **As a:** Người dùng đã đăng nhập
- **I want:** đăng xuất khỏi tài khoản của mình thông qua menu điều hướng
- **So that:** phiên làm việc của tôi kết thúc an toàn và người khác không thể truy cập trái phép vào tài khoản của tôi
- **Acceptance Criteria:**
  - **AC1:** Nhấp vào liên kết 'Logout' trong sidebar menu sẽ kết thúc phiên làm việc và điều hướng về trang đăng nhập 'https://www.saucedemo.com/'.
  - **AC2:** Sau khi đăng xuất, nếu cố tình truy cập trực tiếp URL '/inventory.html' qua thanh địa chỉ, hệ thống lập tức chuyển hướng về trang đăng nhập với thông báo lỗi: 'Epic sadface: You can only access \'/inventory.html\' when you are logged in.'.

### 3. Key Risks & QA Strategy
Rò rỉ phiên làm việc (Session Hijacking), bỏ qua bước đăng nhập khi truy cập URL trực tiếp (/inventory.html), và hiển thị thông báo lỗi không chính xác đối với tài khoản bị khóa (locked_out_user).
