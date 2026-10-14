## Epic: EPIC-06 - End-to-End E-Commerce Workflow

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-06 |
| **Name** | End-to-End E-Commerce Workflow |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 1 Stories (US-13) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Luồng trải nghiệm mua sắm tích hợp xuyên suốt từ đăng nhập, sắp xếp, chọn sản phẩm, giỏ hàng, thanh toán đến hoàn tất đơn hàng và đăng xuất.

### 2. Included User Stories Breakdown

#### [US-13] Trải nghiệm quy trình mua hàng thương mại điện tử End-to-End hoàn chỉnh
- **Priority:** High
- **As a:** Khách hàng mua hàng trực tuyến
- **I want:** thực hiện một luồng mua sắm trọn vẹn từ đăng nhập, sắp xếp sản phẩm, thêm vào giỏ, nhập địa chỉ, xác nhận đơn hàng đến nhận biên lai
- **So that:** tôi có một trải nghiệm mua sắm mượt mà, chính xác và không bị gián đoạn
- **Acceptance Criteria:**
  - **AC1:** Hoàn thành luồng mua hàng: Đăng nhập -> Lọc sản phẩm -> Thêm nhiều sản phẩm -> Xem giỏ hàng -> Nhập thông tin Bước 1 -> Xác thực tổng tiền Bước 2 -> Nhấn Hoàn tất Bước 3 -> Quay về trang chủ.
  - **AC2:** Dữ liệu sản phẩm, số lượng, tiền hàng và thuế đồng bộ chính xác qua mọi bước mà không phát sinh lỗi hệ thống.
  - **AC3:** Giỏ hàng được giải phóng sạch sau khi thanh toán và người dùng có thể đăng xuất an toàn.

### 3. Key Risks & QA Strategy
Lỗi gián đoạn luồng liên module (Broken Flow), sai lệch số liệu tài chính tổng thể, và rủi ro phiên làm việc không được dọn dẹp sạch sau khi hoàn tất đơn hàng.
