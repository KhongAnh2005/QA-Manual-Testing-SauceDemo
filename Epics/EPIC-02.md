## Epic: EPIC-02 - Product Catalog & Inventory Browsing

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-02 |
| **Name** | Product Catalog & Inventory Browsing |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Status** | Approved |
| **Total User Stories** | 2 Stories (US-04, US-05) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

### 1. Scope & Business Objective
Hiển thị danh mục sản phẩm, hình ảnh, thông tin mô tả, xem trang chi tiết sản phẩm và các bộ lọc sắp xếp hàng hóa.

### 2. Included User Stories Breakdown

#### [US-04] Hiển thị danh mục sản phẩm và xem chi tiết sản phẩm
- **Priority:** High
- **As a:** Khách hàng mua sắm
- **I want:** xem danh sách tất cả các sản phẩm có sẵn trên trang danh mục và nhấp vào xem thông tin chi tiết từng sản phẩm
- **So that:** tôi có thể tìm hiểu đầy đủ thông số, hình ảnh và giá cả trước khi quyết định mua hàng
- **Acceptance Criteria:**
  - **AC1:** Trang danh mục hiển thị đầy đủ 6 sản phẩm tiêu chuẩn kèm tên, mô tả, ảnh đại diện và giá tiền định dạng '\$XX.YY'.
  - **AC2:** Nhấp vào tên sản phẩm hoặc hình ảnh sản phẩm sẽ mở trang chi tiết tương ứng ('/inventory-item.html?id=<id>').
  - **AC3:** Trang chi tiết hiển thị hình ảnh chất lượng cao, tên, mô tả đầy đủ, giá bán và nút 'Back to products'.
  - **AC4:** Nhấp vào 'Back to products' đưa người dùng quay lại đúng danh mục sản phẩm.

#### [US-05] Sắp xếp danh mục sản phẩm theo tên và giá tiền
- **Priority:** Medium
- **As a:** Khách hàng mua sắm
- **I want:** sắp xếp danh sách sản phẩm theo Tên (A-Z, Z-A) và Giá tiền (thấp đến cao, cao đến thấp)
- **So that:** tôi nhanh chóng tìm được sản phẩm phù hợp với nhu cầu và khả năng tài chính của mình
- **Acceptance Criteria:**
  - **AC1:** Thứ tự sắp xếp mặc định là 'Name (A to Z)', danh sách sản phẩm hiển thị theo thứ tự bảng chữ cái tăng dần.
  - **AC2:** Chọn 'Name (Z to A)' sắp xếp danh sách sản phẩm theo thứ tự bảng chữ cái giảm dần.
  - **AC3:** Chọn 'Price (low to high)' sắp xếp sản phẩm theo giá số học tăng dần (từ \$7.99 đến \$49.99).
  - **AC4:** Chọn 'Price (high to low)' sắp xếp sản phẩm theo giá số học giảm dần (từ \$49.99 đến \$7.99).

### 3. Key Risks & QA Strategy
Lỗi thuật toán sắp xếp giá so sánh theo chuỗi ký tự thay vì số học, hỏng liên kết ảnh sản phẩm (problem_user), và mất đồng bộ dữ liệu khi quay lại từ trang chi tiết sản phẩm.
