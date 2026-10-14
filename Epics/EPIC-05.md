## Epic: EPIC-05 - Sidebar Navigation & App State

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-05 |
| **Name** | Sidebar Navigation & App State |
| **Issue Type** | Epic |
| **Priority** | Medium |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 1 Stories (US-12) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Menu trượt điều hướng (All Items, liên kết About, Logout, Reset App State) và chức năng làm mới trạng thái ứng dụng.

### 2. Included User Stories Breakdown

#### [US-12] Sử dụng menu điều hướng Sidebar và khôi phục trạng thái ứng dụng
- **Priority:** Medium
- **As a:** Người dùng / QA Tester
- **I want:** sử dụng menu trượt để chuyển trang và đặt lại trạng thái ứng dụng (Reset App State)
- **So that:** tôi có thể di chuyển nhanh giữa các tính năng hoặc khôi phục dữ liệu ban đầu để kiểm thử
- **Acceptance Criteria:**
  - **AC1:** Nhấp biểu tượng hamburger mở menu trượt gồm 4 mục: 'All Items', 'About', 'Logout', 'Reset App State'.
  - **AC2:** Nhấp 'All Items' điều hướng về trang danh mục sản phẩm '/inventory.html'.
  - **AC3:** Nhấp 'About' điều hướng ra website chính thức 'https://saucelabs.com/'.
  - **AC4:** Nhấp 'Reset App State' xóa sạch toàn bộ sản phẩm trong giỏ hàng, xóa huy hiệu giỏ hàng và chuyển các nút 'Remove' về lại 'Add to cart'.
  - **AC5:** Nhấp nút 'X' để đóng menu trượt.

### 3. Key Risks & QA Strategy
Menu sidebar bị kẹt khi mở/đóng, chức năng Reset App State không xóa sạch toàn bộ trạng thái trong session/local storage, và liên kết ngoài (About) làm gián đoạn phiên.
