## Epic: EPIC-03 - Shopping Cart Management

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-03 |
| **Name** | Shopping Cart Management |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 3 Stories (US-06, US-07, US-08) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Thêm/xóa sản phẩm khỏi giỏ hàng, đồng bộ huy hiệu số lượng (Badge Counter), trang xem giỏ hàng và duy trì trạng thái dữ liệu.

### 2. Included User Stories Breakdown

#### [US-06] Thêm sản phẩm vào giỏ hàng và cập nhật số lượng
- **Priority:** High
- **As a:** Khách hàng mua sắm
- **I want:** thêm một hoặc nhiều sản phẩm vào giỏ hàng từ trang danh mục hoặc trang chi tiết
- **So that:** các sản phẩm tôi muốn mua được lưu lại để chuẩn bị tiến hành thanh toán
- **Acceptance Criteria:**
  - **AC1:** Nhấp vào 'Add to cart' đổi nhãn nút thành 'Remove' với định dạng màu sắc viền đỏ phù hợp.
  - **AC2:** Biểu tượng giỏ hàng ở góc phải trên cùng cập nhật số lượng tức thời (hiển thị số 1, 2, ...).
  - **AC3:** Người dùng có thể thêm sản phẩm từ cả trang danh mục chính và trang chi tiết sản phẩm với trạng thái đồng bộ.

#### [US-07] Xóa sản phẩm khỏi giỏ hàng
- **Priority:** High
- **As a:** Khách hàng mua sắm
- **I want:** xóa sản phẩm đã chọn khỏi giỏ hàng trực tiếp tại trang danh mục hoặc trong trang giỏ hàng
- **So that:** tôi có thể điều chỉnh lại danh sách mua hàng trước khi thanh toán
- **Acceptance Criteria:**
  - **AC1:** Nhấp vào 'Remove' tại trang danh mục sẽ loại bỏ sản phẩm khỏi giỏ hàng và giảm số lượng trên huy hiệu giỏ hàng.
  - **AC2:** Nhấp vào 'Remove' tại trang xem giỏ hàng ('/cart.html') sẽ xóa dòng sản phẩm đó và giảm số trên huy hiệu giỏ hàng.
  - **AC3:** Khi xóa toàn bộ sản phẩm khỏi giỏ hàng, huy hiệu số lượng trên biểu tượng giỏ hàng sẽ biến mất hoàn toàn.

#### [US-08] Xem giỏ hàng và duy trì trạng thái dữ liệu khi chuyển trang
- **Priority:** High
- **As a:** Khách hàng mua sắm
- **I want:** truy cập vào trang giỏ hàng để kiểm tra danh sách sản phẩm đã chọn và giữ nguyên dữ liệu này khi tải lại trang hoặc điều hướng
- **So that:** tôi không bị mất giỏ hàng khi đang lướt xem các mục khác
- **Acceptance Criteria:**
  - **AC1:** Nhấp vào biểu tượng giỏ hàng điều hướng đến '/cart.html', hiển thị danh sách sản phẩm với số lượng QTY (1), tên, mô tả và giá tiền.
  - **AC2:** Nút 'Continue Shopping' đưa người dùng quay lại trang danh mục '/inventory.html' mà không làm mất sản phẩm trong giỏ.
  - **AC3:** Dữ liệu giỏ hàng và huy hiệu số lượng vẫn giữ nguyên khi tải lại trang (F5) hoặc điều hướng qua lại giữa các màn hình.

### 3. Key Risks & QA Strategy
Không đồng bộ huy hiệu số lượng giỏ hàng giữa trang danh mục và trang giỏ hàng, mất giỏ hàng khi tải lại trình duyệt (F5), và lỗi giao diện khi giỏ hàng trở về 0 sản phẩm.
