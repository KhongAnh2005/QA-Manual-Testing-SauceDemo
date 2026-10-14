## Epic: EPIC-07 - Backend Services & Database Data Integrity

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-07 |
| **Name** | Backend Services & Database Data Integrity |
| **Issue Type** | Epic |
| **Priority** | Medium |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 2 Stories (US-14, US-15) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Kiểm thử các giao thức hợp đồng giao tiếp RESTful API và tính toàn vẹn của cơ sở dữ liệu quan hệ (Database/SQL) mô phỏng trong hệ sinh thái thương mại điện tử.

### 2. Included User Stories Breakdown

#### [US-14] Xác thực hợp đồng và phản hồi giao diện lập trình ứng dụng RESTful API
- **Priority:** Medium
- **As a:** Kỹ sư kiểm thử backend / Lập trình viên tích hợp
- **I want:** kiểm tra các điểm cuối REST API (Authentication, Inventory, Cart, Order) phản hồi đúng mã trạng thái HTTP và cấu trúc JSON chuẩn
- **So that:** đảm bảo tính ổn định, tin cậy và khả năng tích hợp của hệ thống dịch vụ backend
- **Acceptance Criteria:**
  - **AC1:** Endpoint POST /api/v1/auth/login trả về HTTP 200 OK kèm Bearer Token khi thông tin hợp lệ; trả về HTTP 401 Unauthorized khi sai mật khẩu; trả về HTTP 423 Locked khi tài khoản bị khóa.
  - **AC2:** Endpoint GET /api/v1/products trả về HTTP 200 OK với mảng 6 sản phẩm đúng schema (id, name, price, image_url).
  - **AC3:** Endpoint POST /api/v1/cart/items và POST /api/v1/checkout/orders xử lý thêm sản phẩm và tạo đơn hàng với HTTP 201 Created cùng mã đơn hàng duy nhất.

#### [US-15] Đảm bảo tính nhất quán, toàn vẹn dữ liệu và giao dịch trong cơ sở dữ liệu quan hệ
- **Priority:** Medium
- **As a:** Quản trị viên dữ liệu / QA Database Tester
- **I want:** truy vấn và xác minh dữ liệu trong các bảng users, products, orders và order_items tuân thủ các ràng buộc khóa chính, khóa ngoại và tính chất ACID
- **So that:** dữ liệu kinh doanh và tài chính của người dùng không bị sai lệch, mất mát hoặc trùng lặp
- **Acceptance Criteria:**
  - **AC1:** Bảng 'users' lưu trữ mật khẩu dưới dạng băm an toàn (BCrypt/Argon2); cờ 'is_locked' được phản ánh chính xác với tài khoản bị khóa.
  - **AC2:** Dữ liệu đơn giá và tên sản phẩm trong bảng 'products' khớp 100% với giao diện hiển thị.
  - **AC3:** Giao dịch tạo đơn hàng tuân thủ thuộc tính ACID: Bản ghi bảng 'orders' và các dòng chi tiết trong 'order_items' được commit đồng thời, có ràng buộc Foreign Key toàn vẹn.

### 3. Key Risks & QA Strategy
Sai lệch schema JSON, rò rỉ mã lỗi 500 kèm stack trace, vi phạm ràng buộc khóa ngoại (Foreign Key), vi phạm tính ACID trong giao dịch thanh toán đơn hàng.
