# Exploratory Test Plan: SauceDemo Web Application

**Document ID:** ETP-SAUCEDEMO-01  
**Target Application:** SauceDemo ([https://www.saucedemo.com/](https://www.saucedemo.com/))  
**Author / Owner:** QA - Khổng Đức Anh  
**Status:** Approved (Ready for Exploratory Session Execution)  

---

## Mục Lục

- [1. Introduction to Exploratory Testing](#et-section-1)
- [2. Exploratory Charters by Epic](#et-section-2)
  - [ET-01: Authentication & Session Management](#et-charter-et-01)
  - [ET-02: Product Catalog & Inventory Browsing](#et-charter-et-02)
  - [ET-03: Shopping Cart Management](#et-charter-et-03)
  - [ET-04: Checkout Workflow](#et-charter-et-04)
  - [ET-05: Sidebar Navigation & App State](#et-charter-et-05)
  - [ET-06: End-to-End E-Commerce Workflow & System Resiliency](#et-charter-et-06)
- [3. Session Notes Template](#et-section-3)

---

<a id="et-section-1"></a>
## 1. Introduction to Exploratory Testing

Khác với Scripted Testing (kiểm thử tuần tự theo kịch bản cố định), **Exploratory Testing (Kiểm thử thăm dò)** là phương pháp tiếp cận chủ động, đề cao tính sáng tạo và trực giác kỹ thuật của Tester:
> **Học hỏi hệ thống (Learning) ➔ Thiết kế kiểm thử (Designing) ➔ Thực thi kiểm thử (Executing)** diễn ra đồng thời.

Mỗi phiên kiểm thử thăm dò đều được định hướng chặt chẽ bởi:
1. **Charter:** Định rõ mục tiêu trọng tâm theo cấu trúc:  
   *Explore [Target System] with [Resources] to discover [Information]*
2. **Heuristics (Quy tắc ngón tay cái):** Sử dụng các mô hình phán đoán lỗi đã được chứng minh hiệu quả:
   - **Goldilocks Testing:** Thử nghiệm tại biên, dưới biên và vượt giới hạn mong đợi.
   - **Interruption Testing:** Tải lại trang (Refresh), ấn Back/Forward, ngắt kết nối mạng giữa chừng, mở đa tab.
   - **Rapid Input:** Nhấp chuột liên tiếp tốc độ cao (spam click nút Submit/Add), gõ phím nhanh.
   - **Follow the Data:** Đảo lộn thứ tự thao tác CRUD dữ liệu giỏ hàng.
   - **SFDIPOT Framework (7 Dimensions):** Structure, Function, Data, Interfaces, Platform, Operations, Time.
3. **Timeboxing:** Giới hạn thời gian tập trung cao độ (45 - 60 phút) cho mỗi phiên.

---

<a id="et-section-2"></a>
## 2. Exploratory Charters by Epic
<a id="et-charter-et-01"></a>
### [ET-01] Charter: Authentication & Session Management (EPIC-01)

> **Mission Statement (Charter):**  
> *"Khảo sát hệ thống đăng nhập và quản lý phiên làm việc bằng các loại thông tin đăng nhập hợp lệ/không hợp lệ, các tài khoản người dùng mẫu và điều hướng URL trực tiếp để phát hiện các lỗ hổng xác thực, tính rõ ràng của thông báo lỗi và rò rỉ phiên."*

| **Field** | **Value** |
|:---|:---|
| **Charter ID** | ET-01 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **Timebox** | 45 phút |
| **In-Scope** | Trang đăng nhập ('/'), cookie xác thực, dải thông báo lỗi, thời gian hết hạn phiên và cơ chế bảo vệ route nội bộ. |
| **Out-of-Scope** | Tích hợp cổng thanh toán ngân hàng thực tế, xác thực đơn điểm SSO bên thứ ba. |

#### Heuristics Strategy & Test Ideas

- Goldilocks Testing: Nhập chuỗi 0 ký tự, độ dài thông thường và chuỗi cực dài (500+ ký tự) vào ô Username và Password.
- Interruption Testing: Nhấn phím Enter thay vì nhấp nút; nhấp đúp chuột liên tục vào nút Login; đóng tab và mở lại để kiểm tra cookie.
- SFDIPOT (Security & Interfaces): Kiểm tra cờ cookie ('session-username') và tiêu đề HTTP trên DevTools.

#### Personas & Test Data Setup

- standard_user: Người dùng chuẩn làm mốc đối chứng.
- locked_out_user: Tài khoản bị từ chối truy cập.
- problem_user: Kiểm tra xem đăng nhập có thành công dù các trang sau có lỗi hay không.
- visual_user & error_user: Đánh giá sự cố hiển thị hoặc lỗi mã JavaScript ngay khi đăng nhập.

#### Potential Risk & Vulnerability Targets

- Chiếm đoạt phiên hoặc truy cập trái phép vào trang nội bộ khi không có cookie.
- Thông báo lỗi mơ hồ khiến người dùng bối rối.
- Sập ứng dụng hoặc lỗi JavaScript không được bắt gọn khi nhập ký tự lạ.

---

<a id="et-charter-et-02"></a>
### [ET-02] Charter: Product Catalog & Inventory Browsing (EPIC-02)

> **Mission Statement (Charter):**  
> *"Khảo sát danh mục sản phẩm và trang chi tiết với các tài khoản người dùng khác nhau, các tùy chọn sắp xếp và kích thước màn hình để phát hiện lỗi hiển thị giao diện, sai lệch logic sắp xếp và hình ảnh bị vỡ."*

| **Field** | **Value** |
|:---|:---|
| **Charter ID** | ET-02 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **Timebox** | 45 phút |
| **In-Scope** | Trang danh mục ('/inventory.html'), các thẻ sản phẩm, trang chi tiết ('/inventory-item.html?id='), hộp chọn sắp xếp, hiển thị ảnh. |
| **Out-of-Scope** | Quản trị cơ sở dữ liệu phía máy chủ (môi trường mô phỏng phía client). |

#### Heuristics Strategy & Test Ideas

- Follow the Data: Đối chiếu tính nhất quán về tên, hình ảnh, mô tả và giá giữa danh mục và trang chi tiết.
- Rapid Input: Chuyển đổi liên tục giữa 4 chế độ sắp xếp để phát hiện tình trạng giật lag hoặc bất đồng bộ hiển thị.
- SFDIPOT (Platform & Structure): Co dãn kích thước trình duyệt từ Desktop (1920x1080) xuống màn hình di động (375px) để tìm lỗi vỡ giao diện.

#### Personas & Test Data Setup

- standard_user: Đối chứng chuẩn.
- problem_user: Tài khoản nổi tiếng với lỗi ảnh bị thay thế hàng loạt và liên kết hỏng.
- visual_user: Tài khoản gặp các lỗi lệch vị trí nút bấm và méo giao diện.
- performance_glitch_user: Đánh giá tác động của độ trễ mạng khi tải trang danh mục.

#### Potential Risk & Vulnerability Targets

- Hình ảnh bị vỡ hoặc không tải được (lỗi 404 / thiếu ảnh thay thế).
- Thuật toán sắp xếp giá so sánh theo chuỗi ký tự thay vì số học (ví dụ \$15.99 đứng trước \$7.99).
- Lỗi khi truyền ID sản phẩm không tồn tại trên đường dẫn URL.

---

<a id="et-charter-et-03"></a>
### [ET-03] Charter: Shopping Cart Management (EPIC-03)

> **Mission Statement (Charter):**  
> *"Khảo sát vòng đời giỏ hàng với nhiều mặt hàng, các thao tác thêm/xóa bất thường và thay đổi trạng thái trình duyệt để phát hiện lỗi đồng bộ trạng thái, sai lệch bộ đếm và mất dữ liệu."*

| **Field** | **Value** |
|:---|:---|
| **Charter ID** | ET-03 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **Timebox** | 45 phút |
| **In-Scope** | Các nút Add/Remove trên danh mục, huy hiệu số lượng, trang giỏ hàng ('/cart.html'), hiển thị số lượng, nút Continue Shopping. |
| **Out-of-Scope** | Tính năng lưu vào danh sách yêu thích (hệ thống chưa hỗ trợ). |

#### Heuristics Strategy & Test Ideas

- Follow the Data: Thêm hàng từ danh mục, vào giỏ hàng xóa 1 món, vào trang chi tiết thêm món khác để kiểm tra tính nhất quán dữ liệu.
- Rapid Input: Nhấp liên tiếp nhiều lần qua lại giữa 'Add to cart' và 'Remove' trên cùng một sản phẩm.
- Interruption Testing: Mở giỏ hàng trên 2 tab song song, tab 1 xóa hàng, tab 2 reload lại xem có cập nhật đúng không.
- SFDIPOT (Data & Time): Làm mới cứng trình duyệt (Ctrl+Shift+R) và sử dụng nút Back/Forward của trình duyệt.

#### Personas & Test Data Setup

- standard_user: Đối chứng chuẩn.
- problem_user: Kiểm tra lỗi không bấm được nút xóa hoặc sai lệch phản hồi.
- error_user: Kiểm tra xem có phát sinh lỗi đỏ trong Console khi thêm/xóa hàng hay không.

#### Potential Risk & Vulnerability Targets

- Bộ đếm giỏ hàng hiển thị số âm hoặc hiển thị số 0 thay vì ẩn đi.
- Mất dữ liệu giỏ hàng khi quay lại trang danh mục.
- Nút trên danh mục vẫn hiện 'Remove' dù sản phẩm đã bị xóa trong giỏ hàng.

---

<a id="et-charter-et-04"></a>
### [ET-04] Charter: Checkout Workflow (EPIC-04)

> **Mission Statement (Charter):**  
> *"Khảo sát quy trình thanh toán nhiều bước với dữ liệu khách hàng đa dạng, các trường hợp biên (thanh toán giỏ rỗng, ký tự lạ) và luồng hủy để phát hiện lỗi vượt rào xác thực, sai lệch tính tiền và kẹt màn hình."*

| **Field** | **Value** |
|:---|:---|
| **Charter ID** | ET-04 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **Timebox** | 60 phút |
| **In-Scope** | Checkout Bước 1 ('/checkout-step-one.html'), Bước 2 ('/checkout-step-two.html'), Bước 3 ('/checkout-complete.html'), dải thông báo lỗi, công thức tính toán. |
| **Out-of-Scope** | Thanh toán bằng tiền thật / kết nối ngân hàng thực tế. |

#### Heuristics Strategy & Test Ideas

- Goldilocks Testing: Thử chuỗi rỗng, chuỗi 1 ký tự, chuỗi 100 ký tự, mã bưu điện gồm chữ, số, ký tự đặc biệt (!@#\$%).
- Interruption Testing: Nhấn nút Back của trình duyệt khi đang ở Bước 2; nhấn nút 'Cancel' tại từng bước.
- SFDIPOT (Function & Data): So sánh tiền thuế hiển thị với giá trị tính toán 8% chuẩn trên các mức giá khác nhau (\$7.99, \$49.99 và tổng hợp).

#### Personas & Test Data Setup

- standard_user: Quy trình thanh toán chuẩn.
- problem_user: Được biết có lỗi tự động điền / khóa trường Last Name khi gửi form.
- error_user: Gặp lỗi không xác định khi nhấp nút 'Finish' hoặc 'Continue'.

#### Potential Risk & Vulnerability Targets

- Cho phép hoàn tất đặt hàng với giỏ hàng trống (đơn hàng \$0.00 không có sản phẩm).
- Lỗi làm tròn tiền thuế thập phân.
- Form chấp nhận chuỗi chỉ chứa toàn ký tự khoảng trắng.
- Người dùng bị kẹt lại Bước 1 khi thông báo lỗi không tự biến mất.

---

<a id="et-charter-et-05"></a>
### [ET-05] Charter: Sidebar Navigation & App State (EPIC-05)

> **Mission Statement (Charter):**  
> *"Khảo sát các liên kết trong menu Sidebar và chức năng 'Reset App State' ở các giai đoạn khác nhau của ứng dụng để phát hiện lỗi điều hướng, sót dữ liệu khi đặt lại trạng thái và kẹt lớp phủ giao diện."*

| **Field** | **Value** |
|:---|:---|
| **Charter ID** | ET-05 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **Timebox** | 45 phút |
| **In-Scope** | Menu Sidebar, nút hamburger, nút 'X', các liên kết All Items, About, Logout, Reset App State. |
| **Out-of-Scope** | Chức năng nội bộ trên trang web bên ngoài của Sauce Labs. |

#### Heuristics Strategy & Test Ideas

- Follow the Data: Thêm hàng vào giỏ, mở menu từ màn hình Checkout Bước 2, nhấp 'Reset App State' và kiểm tra dữ liệu có bị dọn sạch ngay không.
- Interruption Testing: Mở menu rồi thu nhỏ/phóng to màn hình; nhấn phím ESC xem menu có đóng không; nhấp chuột ra ngoài vùng tối (overlay).
- SFDIPOT (Interfaces & Structure): Kiểm tra thuộc tính z-index và lớp phủ '.bm-overlay' trong cấu trúc DOM.

#### Personas & Test Data Setup

- standard_user: Điều hướng menu cơ bản.
- visual_user: Kiểm tra lỗi lệch hiệu ứng chuyển động và căn lề menu.

#### Potential Risk & Vulnerability Targets

- Chức năng Reset App State xóa số lượng trên giỏ nhưng các nút trên danh mục vẫn hiển thị chữ 'Remove'.
- Lớp phủ mờ (overlay) vẫn chặn chuột dù menu đã đóng (lỗi z-index).
- Phím ESC không đóng được menu trượt.

---

<a id="et-charter-et-06"></a>
### [ET-06] Charter: End-to-End E-Commerce Workflow & System Resiliency (EPIC-06)

> **Mission Statement (Charter):**  
> *"Khảo sát toàn bộ hành trình mua sắm End-to-End kết hợp sắp xếp, lọc, chọn nhiều món, hoàn tất thanh toán và kiểm tra trạng thái sau mua để phát hiện rò rỉ dữ liệu và lỗi hồi quy luồng."*

| **Field** | **Value** |
|:---|:---|
| **Charter ID** | ET-06 |
| **Epic** | EPIC-06 - End-to-End E-Commerce Workflow & System Resiliency |
| **Timebox** | 60 phút |
| **In-Scope** | Vòng đời trọn vẹn: Login -> Catalog -> Cart -> Checkout 1 -> Checkout 2 -> Complete -> Reset -> Logout. |
| **Out-of-Scope** | Kiểm thử tải tự động quy mô lớn (tập trung vào kiểm thử thăm dò thủ công). |

#### Heuristics Strategy & Test Ideas

- SFDIPOT (Time & Operations): Thao tác dưới tài khoản performance_glitch_user để đánh giá độ trễ khi tải danh mục.
- Follow the Data: Mua trọn bộ cả 6 sản phẩm cùng một lúc và kiểm tra độ chính xác của tổng tiền và tiền thuế.
- Interruption Testing: Nhấn phím Back của trình duyệt sau khi đã nhận biên lai hoàn tất để kiểm tra xem có bị đặt trùng đơn hàng không.

#### Personas & Test Data Setup

- standard_user: Luồng trải nghiệm chuẩn mực.
- performance_glitch_user: Đánh giá cảm nhận độ trễ và khả năng ứng phó khi mạng chậm.
- error_user: Tìm kiếm các ngoại lệ JavaScript tiềm ẩn trong quá trình hoàn tất thanh toán.

#### Potential Risk & Vulnerability Targets

- Gửi trùng đơn hàng khi nhấn nút Back sau trang Checkout Complete.
- Độ trễ cao khiến người dùng mất kiên nhẫn nhấn nút nhiều lần gây lỗi.
- Sai lệch làm tròn số học khi cộng dồn toàn bộ 6 sản phẩm.

---

<a id="et-section-3"></a>
## 3. Session Notes Template (Chuẩn Bị Thực Thi Trong Test Execution Round 1)

Mỗi phiên kiểm thử thăm dò khi thực hiện tại Test Execution Round 1 sẽ được ghi nhận vào biên bản **Exploratory Session Notes** theo cấu trúc:

| **Session Field** | **Description / Record Format** |
|:---|:---|
| **Charter ID** | ET-01 đến ET-06 |
| **Tester Name** | QA - Khổng Đức Anh |
| **Date & Timebox** | DD/MM/YYYY - 45 hoặc 60 phút |
| **Environment** | Chrome v124+ / macOS Sonoma / DevTools Console |
| **Actions & Path Explored** | Trình tự các thao tác, màn hình và tương tác đột xuất đã thực hiện |
| **Data Sets Used** | Các giá trị nhập liệu biên, ký tự lạ, personas kiểm thử |
| **Observations & Behaviors** | Hành vi thực tế của web: console errors, layout shifting, network latency |
| **Defects Discovered** | Liên kết trực tiếp đến Bug ID (BUG-01, BUG-02...) nếu phát hiện lỗi |
| **Evidence Captured** | Ảnh chụp màn hình (Screenshots) / Video quay màn hình (Screencasts) |
