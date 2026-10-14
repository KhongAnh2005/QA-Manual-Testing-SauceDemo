## Epic: EPIC-04 - Checkout Workflow

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-04 |
| **Name** | Checkout Workflow |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 3 Stories (US-09, US-10, US-11) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Quy trình thanh toán 3 bước: Xác thực thông tin khách hàng (Step 1), Tổng quan đơn hàng & tính toán tiền/thuế (Step 2), và Xác nhận hoàn tất đơn hàng (Step 3).

### 2. Included User Stories Breakdown

#### [US-09] Thanh toán Bước 1 - Kiểm tra và xác thực thông tin khách hàng
- **Priority:** High
- **As a:** Khách hàng mua sắm
- **I want:** nhập thông tin giao hàng của tôi (First Name, Last Name, Postal Code) với các quy tắc kiểm tra tính hợp lệ chặt chẽ
- **So that:** hệ thống ghi nhận chính xác thông tin người nhận trước khi chuyển sang bước kiểm tra đơn hàng
- **Acceptance Criteria:**
  - **AC1:** Nhấp nút 'Checkout' tại trang giỏ hàng đưa người dùng đến '/checkout-step-one.html'.
  - **AC2:** Bỏ trống trường First Name và nhấn 'Continue' hiển thị lỗi: 'Error: First Name is required'.
  - **AC3:** Điền First Name nhưng bỏ trống Last Name hiển thị lỗi: 'Error: Last Name is required'.
  - **AC4:** Điền First Name, Last Name nhưng bỏ trống Postal Code hiển thị lỗi: 'Error: Postal Code is required'.
  - **AC5:** Nhập đầy đủ và hợp lệ cả 3 trường rồi nhấn 'Continue' sẽ điều hướng thành công đến '/checkout-step-two.html'.
  - **AC6:** Nhấp nút 'Cancel' sẽ quay về trang '/cart.html' và bảo toàn các sản phẩm trong giỏ hàng.

#### [US-10] Thanh toán Bước 2 - Xem tổng quan đơn hàng và kiểm tra tính toán tiền, thuế
- **Priority:** High
- **As a:** Khách hàng mua sắm
- **I want:** kiểm tra danh sách sản phẩm, phương thức thanh toán, đơn vị vận chuyển, tiền hàng, tiền thuế 8% và tổng tiền thanh toán
- **So that:** tôi xác nhận tính chính xác của hóa đơn trước khi hoàn tất đặt hàng
- **Acceptance Criteria:**
  - **AC1:** Trang hiển thị đúng danh sách các mặt hàng đã chọn kèm số lượng và đơn giá từng món.
  - **AC2:** Thông tin thanh toán hiển thị đúng mã 'SauceCard #31437'.
  - **AC3:** Thông tin giao hàng hiển thị đúng 'Free Pony Express Delivery!'.
  - **AC4:** Tính toán tài chính chính xác: Item total bằng tổng giá các sản phẩm; Tax được tính chính xác 8% (làm tròn 2 chữ số thập phân); Total bằng Item total + Tax.
  - **AC5:** Nhấp nút 'Cancel' đưa người dùng quay lại '/inventory.html' và giữ nguyên giỏ hàng.
  - **AC6:** Nhấp nút 'Finish' hoàn tất đặt hàng và điều hướng đến '/checkout-complete.html'.

#### [US-11] Thanh toán Bước 3 - Xác nhận đơn hàng thành công và làm mới giỏ hàng
- **Priority:** High
- **As a:** Khách hàng mua sắm
- **I want:** nhận được thông báo xác nhận đặt hàng thành công sau khi hoàn tất thanh toán
- **So that:** tôi yên tâm rằng đơn hàng đã được tiếp nhận và sẵn sàng được giao
- **Acceptance Criteria:**
  - **AC1:** Trang hiển thị thông điệp hoàn tất: 'Thank you for your order!' và dòng mô tả giao vận: 'Your order has been dispatched, and will arrive just as fast as the pony can get there!'.
  - **AC2:** Hình ảnh minh họa gói hàng giao vận hiển thị rõ ràng.
  - **AC3:** Huy hiệu số lượng trên giỏ hàng được làm mới hoàn toàn (giỏ hàng trở về trạng thái trống).
  - **AC4:** Nhấp nút 'Back Home' đưa người dùng quay lại trang danh mục '/inventory.html'.

### 3. Key Risks & QA Strategy
Sai lệch tính toán tiền thuế 8% làm tròn, cho phép thanh toán khi giỏ hàng trống (\$0.00), và không làm sạch giỏ hàng sau khi hoàn tất đơn hàng.
