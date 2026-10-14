# Epics Document: SauceDemo E-Commerce Web Application

**Target Application:** SauceDemo ([https://www.saucedemo.com/](https://www.saucedemo.com/))  
**Role:** QA Manual Tester  
**Author / Owner:** QA - Khổng Đức Anh  
**Reporter:** 01-Anh Khổng  
**Total Epics:** 8 Epics  
**Total User Stories Covered:** 17 User Stories  
**Status:** Approved (Ready for Jira Import & Agile Tracking)  

---

## Table of Contents

- [1. Overview & Epic Architecture](#epic-section-1)
- [2. Epics Summary Table](#epic-section-2)
- [3. Detailed Epics Specification](#epic-section-3)
  - [EPIC-01: Authentication & Session Management](#epic-epic-01)
  - [EPIC-02: Product Catalog & Inventory Browsing](#epic-epic-02)
  - [EPIC-03: Shopping Cart Management](#epic-epic-03)
  - [EPIC-04: Checkout Workflow](#epic-epic-04)
  - [EPIC-05: Sidebar Navigation & App State](#epic-epic-05)
  - [EPIC-06: End-to-End E-Commerce Workflow](#epic-epic-06)
  - [EPIC-07: Backend Services & Database Data Integrity](#epic-epic-07)
  - [EPIC-08: Non-Functional Quality Attributes & Security Standards](#epic-epic-08)
- [4. Jira Epic & Story Import Guide](#epic-section-4)

---

<a id="epic-section-1"></a>
## 1. Overview & Epic Architecture

Trong mô hình Agile/Scrum, **Epic** là các khối công việc lớn (Large Work Items) bao bọc một cụm chức năng hoặc một miền nghiệp vụ cốt lõi của sản phẩm. Mỗi Epic được chia nhỏ thành nhiều **User Stories** cụ thể kèm tiêu chí nghiệm thu (**Acceptance Criteria**) để đội ngũ phát triển và kiểm thử có thể thực thi trong các Sprint.

Hệ thống SauceDemo được phân rã thành **8 Epics chính** bao phủ 100% các luồng chức năng, giao diện, các giao thức hợp đồng backend/CSDL và các thuộc tính chất lượng phi chức năng.

<a id="epic-section-2"></a>
## 2. Epics Summary Table

| **Epic ID** | **Epic Name** | **Priority** | **User Stories Count** | **Scope & Business Objective** |
|:---|:---|:---:|:---:|:---|
| **EPIC-01** | Authentication & Session Management | High | 3 Stories | Quản lý xác thực người dùng, đăng nhập, xử lý tài khoản bị khóa, đăng xuất và kiểm soát quyền truy cập phiên làm việc. |
| **EPIC-02** | Product Catalog & Inventory Browsing | High | 2 Stories | Hiển thị danh mục sản phẩm, hình ảnh, thông tin mô tả, xem trang chi tiết sản phẩm và các bộ lọc sắp xếp hàng hóa. |
| **EPIC-03** | Shopping Cart Management | High | 3 Stories | Thêm/xóa sản phẩm khỏi giỏ hàng, đồng bộ huy hiệu số lượng (Badge Counter), trang xem giỏ hàng và duy trì trạng thái dữ liệu. |
| **EPIC-04** | Checkout Workflow | High | 3 Stories | Quy trình thanh toán 3 bước: Xác thực thông tin khách hàng (Step 1), Tổng quan đơn hàng & tính toán tiền/thuế (Step 2), và Xác nhận hoàn tất đơn hàng (Step 3). |
| **EPIC-05** | Sidebar Navigation & App State | Medium | 1 Stories | Menu trượt điều hướng (All Items, liên kết About, Logout, Reset App State) và chức năng làm mới trạng thái ứng dụng. |
| **EPIC-06** | End-to-End E-Commerce Workflow | High | 1 Stories | Luồng trải nghiệm mua sắm tích hợp xuyên suốt từ đăng nhập, sắp xếp, chọn sản phẩm, giỏ hàng, thanh toán đến hoàn tất đơn hàng và đăng xuất. |
| **EPIC-07** | Backend Services & Database Data Integrity | Medium | 2 Stories | Kiểm thử các giao thức hợp đồng giao tiếp RESTful API và tính toàn vẹn của cơ sở dữ liệu quan hệ (Database/SQL) mô phỏng trong hệ sinh thái thương mại điện tử. |
| **EPIC-08** | Non-Functional Quality Attributes & Security Standards | Medium | 2 Stories | Đánh giá các tiêu chuẩn chất lượng phi chức năng bao gồm: Bảo mật phiên & đầu vào, Hiệu năng đáp ứng (SLA), Trải nghiệm người dùng (Usability), Khả năng tiếp cận (Accessibility - WCAG 2.1) và Tương thích đa thiết bị/đa trình duyệt. |

---

<a id="epic-section-3"></a>
## 3. Detailed Epics Specification

<a id="epic-epic-01"></a>
### EPIC-01: Authentication & Session Management

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-01 |
| **Name** | Authentication & Session Management |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-01 |
| **Status** | Approved |
| **Total User Stories** | 3 Stories (US-01, US-02, US-03) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Quản lý xác thực người dùng, đăng nhập, xử lý tài khoản bị khóa, đăng xuất và kiểm soát quyền truy cập phiên làm việc.

#### 2. Included User Stories Breakdown

- **[US-01] Đăng nhập thành công với thông tin tài khoản hợp lệ** (Priority: High)
  - **As a:** Khách hàng tiêu chuẩn (Standard Customer)
  - **I want:** đăng nhập vào hệ thống bằng tên người dùng và mật khẩu hợp lệ
  - **So that:** tôi có thể truy cập danh mục sản phẩm và tiến hành mua sắm
  - **Acceptance Criteria:**
    - **AC1:** Khi người dùng nhập Username 'standard_user' và Password 'secret_sauce' rồi nhấn nút 'Login', hệ thống điều hướng thành công đến trang '/inventory.html'.
    - **AC2:** Trang sản phẩm hiển thị tiêu đề 'Products' và biểu tượng giỏ hàng hiển thị rõ ràng.
    - **AC3:** Cookie phiên 'session-username=standard_user' được khởi tạo và lưu trữ an toàn trong trình duyệt.
- **[US-02] Xử lý lỗi khi đăng nhập không hợp lệ hoặc tài khoản bị khóa** (Priority: High)
  - **As a:** Chuyên viên kiểm thử hệ thống / Người dùng
  - **I want:** hệ thống ngăn chặn truy cập trái phép và hiển thị thông báo lỗi rõ ràng khi thông tin đăng nhập bị thiếu, sai hoặc tài khoản bị khóa
  - **So that:** bảo vệ an toàn tài khoản và giúp người dùng biết lý do đăng nhập thất bại để sửa đổi
  - **Acceptance Criteria:**
    - **AC1:** Nhấn 'Login' khi để trống cả Username và Password hiển thị thông báo lỗi: 'Epic sadface: Username is required'.
    - **AC2:** Nhập Username nhưng để trống Password hiển thị thông báo lỗi: 'Epic sadface: Password is required'.
    - **AC3:** Nhập Username không tồn tại hoặc sai Password hiển thị thông báo lỗi: 'Epic sadface: Username and password do not match any user in this service'.
    - **AC4:** Nhập tài khoản bị khóa 'locked_out_user' và 'secret_sauce' hiển thị thông báo lỗi: 'Epic sadface: Sorry, this user has been locked out.'.
    - **AC5:** Nhấp vào nút 'X' trên thông báo lỗi sẽ đóng thông báo lỗi đó.
- **[US-03] Đăng xuất tài khoản an toàn và hủy phiên làm việc** (Priority: High)
  - **As a:** Người dùng đã đăng nhập
  - **I want:** đăng xuất khỏi tài khoản của mình thông qua menu điều hướng
  - **So that:** phiên làm việc của tôi kết thúc an toàn và người khác không thể truy cập trái phép vào tài khoản của tôi
  - **Acceptance Criteria:**
    - **AC1:** Nhấp vào liên kết 'Logout' trong sidebar menu sẽ kết thúc phiên làm việc và điều hướng về trang đăng nhập 'https://www.saucedemo.com/'.
    - **AC2:** Sau khi đăng xuất, nếu cố tình truy cập trực tiếp URL '/inventory.html' qua thanh địa chỉ, hệ thống lập tức chuyển hướng về trang đăng nhập với thông báo lỗi: 'Epic sadface: You can only access \'/inventory.html\' when you are logged in.'.

#### 3. Key Risks & QA Heuristics Considerations
Rò rỉ phiên làm việc (Session Hijacking), bỏ qua bước đăng nhập khi truy cập URL trực tiếp (/inventory.html), và hiển thị thông báo lỗi không chính xác đối với tài khoản bị khóa (locked_out_user).

---

<a id="epic-epic-02"></a>
### EPIC-02: Product Catalog & Inventory Browsing

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-02 |
| **Name** | Product Catalog & Inventory Browsing |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-02 |
| **Status** | Approved |
| **Total User Stories** | 2 Stories (US-04, US-05) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Hiển thị danh mục sản phẩm, hình ảnh, thông tin mô tả, xem trang chi tiết sản phẩm và các bộ lọc sắp xếp hàng hóa.

#### 2. Included User Stories Breakdown

- **[US-04] Hiển thị danh mục sản phẩm và xem chi tiết sản phẩm** (Priority: High)
  - **As a:** Khách hàng mua sắm
  - **I want:** xem danh sách tất cả các sản phẩm có sẵn trên trang danh mục và nhấp vào xem thông tin chi tiết từng sản phẩm
  - **So that:** tôi có thể tìm hiểu đầy đủ thông số, hình ảnh và giá cả trước khi quyết định mua hàng
  - **Acceptance Criteria:**
    - **AC1:** Trang danh mục hiển thị đầy đủ 6 sản phẩm tiêu chuẩn kèm tên, mô tả, ảnh đại diện và giá tiền định dạng '\$XX.YY'.
    - **AC2:** Nhấp vào tên sản phẩm hoặc hình ảnh sản phẩm sẽ mở trang chi tiết tương ứng ('/inventory-item.html?id=<id>').
    - **AC3:** Trang chi tiết hiển thị hình ảnh chất lượng cao, tên, mô tả đầy đủ, giá bán và nút 'Back to products'.
    - **AC4:** Nhấp vào 'Back to products' đưa người dùng quay lại đúng danh mục sản phẩm.
- **[US-05] Sắp xếp danh mục sản phẩm theo tên và giá tiền** (Priority: Medium)
  - **As a:** Khách hàng mua sắm
  - **I want:** sắp xếp danh sách sản phẩm theo Tên (A-Z, Z-A) và Giá tiền (thấp đến cao, cao đến thấp)
  - **So that:** tôi nhanh chóng tìm được sản phẩm phù hợp với nhu cầu và khả năng tài chính của mình
  - **Acceptance Criteria:**
    - **AC1:** Thứ tự sắp xếp mặc định là 'Name (A to Z)', danh sách sản phẩm hiển thị theo thứ tự bảng chữ cái tăng dần.
    - **AC2:** Chọn 'Name (Z to A)' sắp xếp danh sách sản phẩm theo thứ tự bảng chữ cái giảm dần.
    - **AC3:** Chọn 'Price (low to high)' sắp xếp sản phẩm theo giá số học tăng dần (từ \$7.99 đến \$49.99).
    - **AC4:** Chọn 'Price (high to low)' sắp xếp sản phẩm theo giá số học giảm dần (từ \$49.99 đến \$7.99).

#### 3. Key Risks & QA Heuristics Considerations
Lỗi thuật toán sắp xếp giá so sánh theo chuỗi ký tự thay vì số học, hỏng liên kết ảnh sản phẩm (problem_user), và mất đồng bộ dữ liệu khi quay lại từ trang chi tiết sản phẩm.

---

<a id="epic-epic-03"></a>
### EPIC-03: Shopping Cart Management

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-03 |
| **Name** | Shopping Cart Management |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-03 |
| **Status** | Approved |
| **Total User Stories** | 3 Stories (US-06, US-07, US-08) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Thêm/xóa sản phẩm khỏi giỏ hàng, đồng bộ huy hiệu số lượng (Badge Counter), trang xem giỏ hàng và duy trì trạng thái dữ liệu.

#### 2. Included User Stories Breakdown

- **[US-06] Thêm sản phẩm vào giỏ hàng và cập nhật số lượng** (Priority: High)
  - **As a:** Khách hàng mua sắm
  - **I want:** thêm một hoặc nhiều sản phẩm vào giỏ hàng từ trang danh mục hoặc trang chi tiết
  - **So that:** các sản phẩm tôi muốn mua được lưu lại để chuẩn bị tiến hành thanh toán
  - **Acceptance Criteria:**
    - **AC1:** Nhấp vào 'Add to cart' đổi nhãn nút thành 'Remove' với định dạng màu sắc viền đỏ phù hợp.
    - **AC2:** Biểu tượng giỏ hàng ở góc phải trên cùng cập nhật số lượng tức thời (hiển thị số 1, 2, ...).
    - **AC3:** Người dùng có thể thêm sản phẩm từ cả trang danh mục chính và trang chi tiết sản phẩm với trạng thái đồng bộ.
- **[US-07] Xóa sản phẩm khỏi giỏ hàng** (Priority: High)
  - **As a:** Khách hàng mua sắm
  - **I want:** xóa sản phẩm đã chọn khỏi giỏ hàng trực tiếp tại trang danh mục hoặc trong trang giỏ hàng
  - **So that:** tôi có thể điều chỉnh lại danh sách mua hàng trước khi thanh toán
  - **Acceptance Criteria:**
    - **AC1:** Nhấp vào 'Remove' tại trang danh mục sẽ loại bỏ sản phẩm khỏi giỏ hàng và giảm số lượng trên huy hiệu giỏ hàng.
    - **AC2:** Nhấp vào 'Remove' tại trang xem giỏ hàng ('/cart.html') sẽ xóa dòng sản phẩm đó và giảm số trên huy hiệu giỏ hàng.
    - **AC3:** Khi xóa toàn bộ sản phẩm khỏi giỏ hàng, huy hiệu số lượng trên biểu tượng giỏ hàng sẽ biến mất hoàn toàn.
- **[US-08] Xem giỏ hàng và duy trì trạng thái dữ liệu khi chuyển trang** (Priority: High)
  - **As a:** Khách hàng mua sắm
  - **I want:** truy cập vào trang giỏ hàng để kiểm tra danh sách sản phẩm đã chọn và giữ nguyên dữ liệu này khi tải lại trang hoặc điều hướng
  - **So that:** tôi không bị mất giỏ hàng khi đang lướt xem các mục khác
  - **Acceptance Criteria:**
    - **AC1:** Nhấp vào biểu tượng giỏ hàng điều hướng đến '/cart.html', hiển thị danh sách sản phẩm với số lượng QTY (1), tên, mô tả và giá tiền.
    - **AC2:** Nút 'Continue Shopping' đưa người dùng quay lại trang danh mục '/inventory.html' mà không làm mất sản phẩm trong giỏ.
    - **AC3:** Dữ liệu giỏ hàng và huy hiệu số lượng vẫn giữ nguyên khi tải lại trang (F5) hoặc điều hướng qua lại giữa các màn hình.

#### 3. Key Risks & QA Heuristics Considerations
Không đồng bộ huy hiệu số lượng giỏ hàng giữa trang danh mục và trang giỏ hàng, mất giỏ hàng khi tải lại trình duyệt (F5), và lỗi giao diện khi giỏ hàng trở về 0 sản phẩm.

---

<a id="epic-epic-04"></a>
### EPIC-04: Checkout Workflow

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-04 |
| **Name** | Checkout Workflow |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-04 |
| **Status** | Approved |
| **Total User Stories** | 3 Stories (US-09, US-10, US-11) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Quy trình thanh toán 3 bước: Xác thực thông tin khách hàng (Step 1), Tổng quan đơn hàng & tính toán tiền/thuế (Step 2), và Xác nhận hoàn tất đơn hàng (Step 3).

#### 2. Included User Stories Breakdown

- **[US-09] Thanh toán Bước 1 - Kiểm tra và xác thực thông tin khách hàng** (Priority: High)
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
- **[US-10] Thanh toán Bước 2 - Xem tổng quan đơn hàng và kiểm tra tính toán tiền, thuế** (Priority: High)
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
- **[US-11] Thanh toán Bước 3 - Xác nhận đơn hàng thành công và làm mới giỏ hàng** (Priority: High)
  - **As a:** Khách hàng mua sắm
  - **I want:** nhận được thông báo xác nhận đặt hàng thành công sau khi hoàn tất thanh toán
  - **So that:** tôi yên tâm rằng đơn hàng đã được tiếp nhận và sẵn sàng được giao
  - **Acceptance Criteria:**
    - **AC1:** Trang hiển thị thông điệp hoàn tất: 'Thank you for your order!' và dòng mô tả giao vận: 'Your order has been dispatched, and will arrive just as fast as the pony can get there!'.
    - **AC2:** Hình ảnh minh họa gói hàng giao vận hiển thị rõ ràng.
    - **AC3:** Huy hiệu số lượng trên giỏ hàng được làm mới hoàn toàn (giỏ hàng trở về trạng thái trống).
    - **AC4:** Nhấp nút 'Back Home' đưa người dùng quay lại trang danh mục '/inventory.html'.

#### 3. Key Risks & QA Heuristics Considerations
Sai lệch tính toán tiền thuế 8% làm tròn, cho phép thanh toán khi giỏ hàng trống (\$0.00), và không làm sạch giỏ hàng sau khi hoàn tất đơn hàng.

---

<a id="epic-epic-05"></a>
### EPIC-05: Sidebar Navigation & App State

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-05 |
| **Name** | Sidebar Navigation & App State |
| **Issue Type** | Epic |
| **Priority** | Medium |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-05 |
| **Status** | Approved |
| **Total User Stories** | 1 Stories (US-12) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Menu trượt điều hướng (All Items, liên kết About, Logout, Reset App State) và chức năng làm mới trạng thái ứng dụng.

#### 2. Included User Stories Breakdown

- **[US-12] Sử dụng menu điều hướng Sidebar và khôi phục trạng thái ứng dụng** (Priority: Medium)
  - **As a:** Người dùng / QA Tester
  - **I want:** sử dụng menu trượt để chuyển trang và đặt lại trạng thái ứng dụng (Reset App State)
  - **So that:** tôi có thể di chuyển nhanh giữa các tính năng hoặc khôi phục dữ liệu ban đầu để kiểm thử
  - **Acceptance Criteria:**
    - **AC1:** Nhấp biểu tượng hamburger mở menu trượt gồm 4 mục: 'All Items', 'About', 'Logout', 'Reset App State'.
    - **AC2:** Nhấp 'All Items' điều hướng về trang danh mục sản phẩm '/inventory.html'.
    - **AC3:** Nhấp 'About' điều hướng ra website chính thức 'https://saucelabs.com/'.
    - **AC4:** Nhấp 'Reset App State' xóa sạch toàn bộ sản phẩm trong giỏ hàng, xóa huy hiệu giỏ hàng và chuyển các nút 'Remove' về lại 'Add to cart'.
    - **AC5:** Nhấp nút 'X' để đóng menu trượt.

#### 3. Key Risks & QA Heuristics Considerations
Menu sidebar bị kẹt khi mở/đóng, chức năng Reset App State không xóa sạch toàn bộ trạng thái trong session/local storage, và liên kết ngoài (About) làm gián đoạn phiên.

---

<a id="epic-epic-06"></a>
### EPIC-06: End-to-End E-Commerce Workflow

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-06 |
| **Name** | End-to-End E-Commerce Workflow |
| **Issue Type** | Epic |
| **Priority** | High |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-06 |
| **Status** | Approved |
| **Total User Stories** | 1 Stories (US-13) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Luồng trải nghiệm mua sắm tích hợp xuyên suốt từ đăng nhập, sắp xếp, chọn sản phẩm, giỏ hàng, thanh toán đến hoàn tất đơn hàng và đăng xuất.

#### 2. Included User Stories Breakdown

- **[US-13] Trải nghiệm quy trình mua hàng thương mại điện tử End-to-End hoàn chỉnh** (Priority: High)
  - **As a:** Khách hàng mua hàng trực tuyến
  - **I want:** thực hiện một luồng mua sắm trọn vẹn từ đăng nhập, sắp xếp sản phẩm, thêm vào giỏ, nhập địa chỉ, xác nhận đơn hàng đến nhận biên lai
  - **So that:** tôi có một trải nghiệm mua sắm mượt mà, chính xác và không bị gián đoạn
  - **Acceptance Criteria:**
    - **AC1:** Hoàn thành luồng mua hàng: Đăng nhập -> Lọc sản phẩm -> Thêm nhiều sản phẩm -> Xem giỏ hàng -> Nhập thông tin Bước 1 -> Xác thực tổng tiền Bước 2 -> Nhấn Hoàn tất Bước 3 -> Quay về trang chủ.
    - **AC2:** Dữ liệu sản phẩm, số lượng, tiền hàng và thuế đồng bộ chính xác qua mọi bước mà không phát sinh lỗi hệ thống.
    - **AC3:** Giỏ hàng được giải phóng sạch sau khi thanh toán và người dùng có thể đăng xuất an toàn.

#### 3. Key Risks & QA Heuristics Considerations
Lỗi gián đoạn luồng liên module (Broken Flow), sai lệch số liệu tài chính tổng thể, và rủi ro phiên làm việc không được dọn dẹp sạch sau khi hoàn tất đơn hàng.

---

<a id="epic-epic-07"></a>
### EPIC-07: Backend Services & Database Data Integrity

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-07 |
| **Name** | Backend Services & Database Data Integrity |
| **Issue Type** | Epic |
| **Priority** | Medium |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-07 |
| **Status** | Approved |
| **Total User Stories** | 2 Stories (US-14, US-15) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Kiểm thử các giao thức hợp đồng giao tiếp RESTful API và tính toàn vẹn của cơ sở dữ liệu quan hệ (Database/SQL) mô phỏng trong hệ sinh thái thương mại điện tử.

#### 2. Included User Stories Breakdown

- **[US-14] Xác thực hợp đồng và phản hồi giao diện lập trình ứng dụng RESTful API** (Priority: Medium)
  - **As a:** Kỹ sư kiểm thử backend / Lập trình viên tích hợp
  - **I want:** kiểm tra các điểm cuối REST API (Authentication, Inventory, Cart, Order) phản hồi đúng mã trạng thái HTTP và cấu trúc JSON chuẩn
  - **So that:** đảm bảo tính ổn định, tin cậy và khả năng tích hợp của hệ thống dịch vụ backend
  - **Acceptance Criteria:**
    - **AC1:** Endpoint POST /api/v1/auth/login trả về HTTP 200 OK kèm Bearer Token khi thông tin hợp lệ; trả về HTTP 401 Unauthorized khi sai mật khẩu; trả về HTTP 423 Locked khi tài khoản bị khóa.
    - **AC2:** Endpoint GET /api/v1/products trả về HTTP 200 OK với mảng 6 sản phẩm đúng schema (id, name, price, image_url).
    - **AC3:** Endpoint POST /api/v1/cart/items và POST /api/v1/checkout/orders xử lý thêm sản phẩm và tạo đơn hàng với HTTP 201 Created cùng mã đơn hàng duy nhất.
- **[US-15] Đảm bảo tính nhất quán, toàn vẹn dữ liệu và giao dịch trong cơ sở dữ liệu quan hệ** (Priority: Medium)
  - **As a:** Quản trị viên dữ liệu / QA Database Tester
  - **I want:** truy vấn và xác minh dữ liệu trong các bảng users, products, orders và order_items tuân thủ các ràng buộc khóa chính, khóa ngoại và tính chất ACID
  - **So that:** dữ liệu kinh doanh và tài chính của người dùng không bị sai lệch, mất mát hoặc trùng lặp
  - **Acceptance Criteria:**
    - **AC1:** Bảng 'users' lưu trữ mật khẩu dưới dạng băm an toàn (BCrypt/Argon2); cờ 'is_locked' được phản ánh chính xác với tài khoản bị khóa.
    - **AC2:** Dữ liệu đơn giá và tên sản phẩm trong bảng 'products' khớp 100% với giao diện hiển thị.
    - **AC3:** Giao dịch tạo đơn hàng tuân thủ thuộc tính ACID: Bản ghi bảng 'orders' và các dòng chi tiết trong 'order_items' được commit đồng thời, có ràng buộc Foreign Key toàn vẹn.

#### 3. Key Risks & QA Heuristics Considerations
Sai lệch schema JSON, rò rỉ mã lỗi 500 kèm stack trace, vi phạm ràng buộc khóa ngoại (Foreign Key), vi phạm tính ACID trong giao dịch thanh toán đơn hàng.

---

<a id="epic-epic-08"></a>
### EPIC-08: Non-Functional Quality Attributes & Security Standards

| **Field** | **Value** |
|:---|:---|
| **Epic ID** | EPIC-08 |
| **Name** | Non-Functional Quality Attributes & Security Standards |
| **Issue Type** | Epic |
| **Priority** | Medium |
| **Owner / Assignee** | QA - Khổng Đức Anh |
| **Reporter** | 01-Anh Khổng |
| **Parent (Epic ID)** | EPIC-08 |
| **Status** | Approved |
| **Total User Stories** | 2 Stories (US-16, US-17) |
| **Target Application** | SauceDemo (https://www.saucedemo.com/) |

#### 1. Scope & Business Objective
Đánh giá các tiêu chuẩn chất lượng phi chức năng bao gồm: Bảo mật phiên & đầu vào, Hiệu năng đáp ứng (SLA), Trải nghiệm người dùng (Usability), Khả năng tiếp cận (Accessibility - WCAG 2.1) và Tương thích đa thiết bị/đa trình duyệt.

#### 2. Included User Stories Breakdown

- **[US-16] Bảo mật thông tin phiên làm việc và chống tiêm mã độc hại (XSS/Session Security)** (Priority: High)
  - **As a:** Chuyên viên kiểm thử bảo mật (Security Tester)
  - **I want:** hệ thống bảo vệ cookie phiên và làm sạch các dữ liệu đầu vào người dùng
  - **So that:** ngăn ngừa rủi ro đánh cắp phiên và tấn công tiêm mã Cross-Site Scripting (XSS)
  - **Acceptance Criteria:**
    - **AC1:** Cookie phiên 'session-username' và các cookie nhạy cảm phải được gắn cờ Secure, HttpOnly và SameSite=Strict.
    - **AC2:** Các trường nhập liệu (Username, First Name, Last Name, Postal Code) phải làm sạch hoặc mã hóa ký tự HTML/Script nguy hiểm (<script>, img onerror), không kích hoạt mã độc hại.
    - **AC3:** Sau khi đăng xuất, các trang nhạy cảm phía sau đăng nhập (/inventory.html, /cart.html) không thể được khôi phục hoặc xem lại thông qua bộ nhớ đệm lịch sử trình duyệt (Browser Cache / History Back).
- **[US-17] Tối ưu hiệu năng, khả năng tiếp cận, trải nghiệm người dùng và tương thích đa nền tảng** (Priority: Medium)
  - **As a:** Khách hàng truy cập đa thiết bị và người dùng có nhu cầu trợ năng
  - **I want:** ứng dụng tải nhanh dưới 2 giây, giao diện hiển thị chuẩn xác trên mobile/desktop, tương phản màu tốt và hỗ trợ điều hướng bàn phím
  - **So that:** tôi có thể mua sắm thuận tiện trên mọi thiết bị và điều kiện sử dụng
  - **Acceptance Criteria:**
    - **AC1:** Thời gian tải trang (Page Load Time / DOMContentLoaded) dưới điều kiện mạng thông thường phải nhỏ hơn hoặc bằng 2.0 giây đối với tài khoản tiêu chuẩn.
    - **AC2:** Ứng dụng hỗ trợ điều hướng hoàn toàn bằng phím Tab (Focus ring rõ nét) và các nút thao tác icon có thuộc tính aria-label / title theo chuẩn WCAG 2.1 AA.
    - **AC3:** Giao diện hiển thị phản hồi mượt mà, không bị vỡ layout, lệch hàng cột hoặc tràn nội dung trên các kích thước màn hình di động (Viewport 375x812) và các trình duyệt Chrome, Firefox, Safari.

#### 3. Key Risks & QA Heuristics Considerations
Tấn công Cross-Site Scripting (XSS), vi phạm thuộc tính Cookie bảo mật, vi phạm SLA thời gian phản hồi trang (>2s), lỗi giao diện trên thiết bị di động (Responsive), và rào cản tiếp cận cho người khuyết tật.

---

<a id="epic-section-4"></a>
## 4. Jira Epic & Story Import Guide

Có 2 phương án chuẩn xác để thiết lập toàn bộ Epics và User Stories trên Jira Cloud:

### Phương Án 1: Import 1-Click Hợp Nhất (Khuyên dùng cho dự án mới)
Trình import mới của Jira Cloud (*Map space fields*) thiết lập cây phân cấp (Hierarchy) bằng cách tham chiếu giá trị `Parent` đến `Work item ID` của dòng cha **nằm ngay trong cùng một file CSV**.
1. Sử dụng duy nhất file **`Import_Epic&UserStory.csv`**.
2. File đã cấu hình sẵn:
   - Dòng 1 đến 8: Các **Epics** có `Work item ID` từ `1` đến `8`, cột `Parent` để trống.
   - Dòng 9 đến 25: Các **User Stories** có `Work item ID` từ `9` đến `25`, cột `Parent` tham chiếu chính xác đến `1..8` của Epic cha tương ứng.
3. Map các trường trên Jira: `Work item ID` -> Work item ID, `Issue Type` -> Work Type, `Summary` -> Summary, `Description` -> Description, `Priority` -> Priority, `Component` -> Component, `Parent` -> Parent, `Assignee` -> Assignee, `Reporter` -> Reporter, `Status` -> Status.
4. Kết quả: Toàn bộ 8 Epics và 17 Stories được khởi tạo đồng thời và tự động liên kết phân cấp 100% không cần thao tác thủ công.

### Phương Án 2: Gắn Epic Trực Tiếp Trên Giao Diện Jira Backlog (Dành cho dự án đã import riêng lẻ)
Nếu đã import Epics và Stories qua 2 file CSV riêng biệt (`00_Epics_Document.csv` và `01_Requirement_Document_User_Stories.csv`):
1. Truy cập màn hình **Backlog** của dự án (`/boards/.../backlog`).
2. Bật panel **Epic** ở góc trái danh sách Backlog.
3. **Kéo & Thả (Drag & Drop):** Giữ chuột và kéo từng User Story từ danh sách Backlog thả trực tiếp vào thẻ Epic tương ứng ở cột bên trái (Ví dụ: kéo `US-01`, `US-02`, `US-03` thả vào `[EPIC-01]`).
4. **Hoặc chọn Parent ở cột chi tiết bên phải:** Nhấp vào từng User Story, ở mục `Details` -> `Parent`, bấm chọn Epic tương ứng từ dropdown.
