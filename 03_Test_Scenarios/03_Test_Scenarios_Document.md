# Test Scenarios Specification: SauceDemo Web Application

Document ID: TSD-SAUCEDEMO-01  
Target Application: SauceDemo (https://www.saucedemo.com/)  
Author: QA - Khổng Đức Anh  
Date: 18/09/2026  
Total Scenarios: 34 Test Scenarios  

---

## Mục Lục

- [1. Danh Sách 34 Test Scenarios](#1-danh-sach-34-test-scenarios)
- [2. Chi Tiết Các Test Scenarios](#2-chi-tiet-cac-test-scenarios)

---

<a id="1-danh-sach-34-test-scenarios"></a>
## 1. Danh Sách 34 Test Scenarios

| Scenario ID | Title | User Story | Epic | Path Type | Risk Priority |
|:---|:---|:---|:---|:---|:---:|
| [TS-01](#ts-01) | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ | [US-01_AC1, US-01_AC2, US-01_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-01) | [EPIC-01](../00_Epics/EPIC-01.md) | Happy Path | High |
| [TS-02](#ts-02) | Kiểm tra thông báo lỗi khi để trống thông tin đăng nhập | [US-02_AC1, US-02_AC2](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [EPIC-01](../00_Epics/EPIC-01.md) | Negative Path | High |
| [TS-03](#ts-03) | Kiểm tra từ chối đăng nhập khi nhập sai tài khoản hoặc mật khẩu | [US-02_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [EPIC-01](../00_Epics/EPIC-01.md) | Negative Path | High |
| [TS-04](#ts-04) | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa | [US-02_AC4](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [EPIC-01](../00_Epics/EPIC-01.md) | Negative Path | High |
| [TS-05](#ts-05) | Kiểm tra đăng xuất an toàn và chặn truy cập trực tiếp URL nội bộ | [US-03_AC1, US-03_AC2](../01_Requirements/01_Requirement_Document_User_Stories.md#us-03) | [EPIC-01](../00_Epics/EPIC-01.md) | Happy Path | High |
| [TS-06](#ts-06) | Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và thông tin giá cả | [US-04_AC1](../01_Requirements/01_Requirement_Document_User_Stories.md#us-04) | [EPIC-02](../00_Epics/EPIC-02.md) | Happy Path | High |
| [TS-07](#ts-07) | Kiểm tra xem trang chi tiết sản phẩm và chức năng quay lại danh mục | [US-04_AC2, US-04_AC3, US-04_AC4](../01_Requirements/01_Requirement_Document_User_Stories.md#us-04) | [EPIC-02](../00_Epics/EPIC-02.md) | Happy Path | Medium |
| [TS-08](#ts-08) | Kiểm tra sắp xếp danh mục sản phẩm theo bảng chữ cái (A-Z và Z-A) | [US-05_AC1, US-05_AC2](../01_Requirements/01_Requirement_Document_User_Stories.md#us-05) | [EPIC-02](../00_Epics/EPIC-02.md) | Happy Path | Medium |
| [TS-09](#ts-09) | Kiểm tra sắp xếp danh mục sản phẩm theo giá số học (thấp đến cao và cao đến thấp) | [US-05_AC3, US-05_AC4](../01_Requirements/01_Requirement_Document_User_Stories.md#us-05) | [EPIC-02](../00_Epics/EPIC-02.md) | Happy Path | Medium |
| [TS-10](#ts-10) | Kiểm tra tính toàn vẹn hình ảnh và độ ổn định giao diện danh mục sản phẩm | [US-04_AC1](../01_Requirements/01_Requirement_Document_User_Stories.md#us-04) | [EPIC-02](../00_Epics/EPIC-02.md) | Negative Path | Medium |
| [TS-11](#ts-11) | Kiểm tra thêm sản phẩm vào giỏ hàng và tăng số lượng trên huy hiệu giỏ | [US-06_AC1, US-06_AC2](../01_Requirements/01_Requirement_Document_User_Stories.md#us-06) | [EPIC-03](../00_Epics/EPIC-03.md) | Happy Path | High |
| [TS-12](#ts-12) | Kiểm tra xóa sản phẩm khỏi giỏ hàng ngay tại trang danh mục | [US-07_AC1, US-07_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-07) | [EPIC-03](../00_Epics/EPIC-03.md) | Happy Path | High |
| [TS-13](#ts-13) | Kiểm tra trang giỏ hàng hiển thị đúng danh sách, số lượng và giá sản phẩm | [US-08_AC1](../01_Requirements/01_Requirement_Document_User_Stories.md#us-08) | [EPIC-03](../00_Epics/EPIC-03.md) | Happy Path | High |
| [TS-14](#ts-14) | Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng | [US-07_AC2, US-07_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-07) | [EPIC-03](../00_Epics/EPIC-03.md) | Happy Path | High |
| [TS-15](#ts-15) | Kiểm tra tính bền vững của giỏ hàng khi tải lại trang hoặc điều hướng | [US-08_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-08) | [EPIC-03](../00_Epics/EPIC-03.md) | Happy Path | High |
| [TS-16](#ts-16) | Kiểm tra chuyển từ giỏ hàng sang trang thanh toán Bước 1 | [US-09_AC1](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [EPIC-04](../00_Epics/EPIC-04.md) | Happy Path | High |
| [TS-17](#ts-17) | Kiểm tra bắt buộc nhập thông tin khách hàng tại Bước 1 khi để trống trường | [US-09_AC2, US-09_AC3, US-09_AC4](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [EPIC-04](../00_Epics/EPIC-04.md) | Negative Path | High |
| [TS-18](#ts-18) | Kiểm tra xử lý các định dạng mã bưu điện đặc biệt tại Bước 1 | [US-09_AC5](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [EPIC-04](../00_Epics/EPIC-04.md) | Negative Path | Medium |
| [TS-19](#ts-19) | Kiểm tra nút Cancel tại Bước 1 quay lại giỏ hàng an toàn | [US-09_AC6](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [EPIC-04](../00_Epics/EPIC-04.md) | Happy Path | Medium |
| [TS-20](#ts-20) | Kiểm tra tính toán chính xác tiền hàng, thuế 8% và tổng tiền tại Bước 2 | [US-10_AC1, US-10_AC2, US-10_AC3, US-10_AC4](../01_Requirements/01_Requirement_Document_User_Stories.md#us-10) | [EPIC-04](../00_Epics/EPIC-04.md) | Happy Path | High |
| [TS-21](#ts-21) | Kiểm tra nút Cancel tại Bước 2 hủy thanh toán và về trang danh mục | [US-10_AC5](../01_Requirements/01_Requirement_Document_User_Stories.md#us-10) | [EPIC-04](../00_Epics/EPIC-04.md) | Happy Path | Medium |
| [TS-22](#ts-22) | Kiểm tra hoàn tất đơn hàng Bước 3, hiển thị biên lai và làm sạch giỏ | [US-11_AC1, US-11_AC2, US-11_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-11) | [EPIC-04](../00_Epics/EPIC-04.md) | Happy Path | High |
| [TS-23](#ts-23) | Kiểm tra hành vi hệ thống khi tiến hành thanh toán với giỏ hàng rỗng | [US-09_AC1](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [EPIC-04](../00_Epics/EPIC-04.md) | Negative Path | Medium |
| [TS-24](#ts-24) | Kiểm tra mở và đóng menu Sidebar dạng trượt | [US-12_AC1, US-12_AC5](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [EPIC-05](../00_Epics/EPIC-05.md) | Happy Path | Medium |
| [TS-25](#ts-25) | Kiểm tra liên kết 'All Items' trong sidebar chuyển về trang sản phẩm | [US-12_AC2](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [EPIC-05](../00_Epics/EPIC-05.md) | Happy Path | Medium |
| [TS-26](#ts-26) | Kiểm tra liên kết 'About' trong sidebar mở website Sauce Labs | [US-12_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [EPIC-05](../00_Epics/EPIC-05.md) | Happy Path | Low |
| [TS-27](#ts-27) | Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng | [US-12_AC4](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [EPIC-05](../00_Epics/EPIC-05.md) | Happy Path | High |
| [TS-28](#ts-28) | Kiểm tra toàn diện quy trình mua sắm End-to-End với nhiều sản phẩm | [US-13_AC1, US-13_AC2](../01_Requirements/01_Requirement_Document_User_Stories.md#us-13) | [EPIC-06](../00_Epics/EPIC-06.md) | Happy Path | High |
| [TS-29](#ts-29) | Kiểm tra luồng mua sắm kết hợp sắp xếp giá và xóa bớt sản phẩm trong giỏ | [US-13_AC1, US-13_AC2](../01_Requirements/01_Requirement_Document_User_Stories.md#us-13) | [EPIC-06](../00_Epics/EPIC-06.md) | Happy Path | High |
| [TS-30](#ts-30) | Kiểm tra tính an toàn dữ liệu khi đặt lại trạng thái ứng dụng giữa chừng thanh toán | [US-13_AC1, US-13_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-13) | [EPIC-06](../00_Epics/EPIC-06.md) | Negative Path | Medium |
| [TS-31](#ts-31) | Kiểm thử các giao thức hợp đồng và xử lý phản hồi mã lỗi RESTful API | [US-14_AC1, US-14_AC2, US-14_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-14) | [EPIC-07](../00_Epics/EPIC-07.md) | Contract / Integration Path | High |
| [TS-32](#ts-32) | Kiểm thử tính toàn vẹn dữ liệu và giao dịch ACID trong cơ sở dữ liệu quan hệ (SQL) | [US-15_AC1, US-15_AC2, US-15_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-15) | [EPIC-07](../00_Epics/EPIC-07.md) | Database / Data Integrity Path | High |
| [TS-33](#ts-33) | Kiểm thử bảo mật phiên làm việc và phòng chống tấn công tiêm mã (Security & XSS) | [US-16_AC1, US-16_AC2, US-16_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-16) | [EPIC-08](../00_Epics/EPIC-08.md) | Security / Defensive Path | High |
| [TS-34](#ts-34) | Kiểm thử các thuộc tính phi chức năng: Hiệu năng SLA, Tiếp cận WCAG, Usability và Tương thích | [US-17_AC1, US-17_AC2, US-17_AC3](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [EPIC-08](../00_Epics/EPIC-08.md) | Non-Functional Quality Path | Medium |

---

<a id="2-chi-tiet-cac-test-scenarios"></a>
## 2. Chi Tiết Các Test Scenarios

<a id="ts-01"></a>

## Test Scenario: TS-01 - Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-01 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-01_AC1, US-01_AC2, US-01_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang đăng nhập (https://www.saucedemo.com/) với trình duyệt sạch (chưa có cookie phiên). |

### 1. Objective
Đảm bảo người dùng hợp lệ có thể đăng nhập thành công bằng tài khoản tiêu chuẩn ('standard_user' / 'secret_sauce') và truy cập vào trang danh mục sản phẩm bình thường.

### 2. Expected Outcome
Đăng nhập thành công, chuyển hướng đến '/inventory.html', tiêu đề hiển thị 'Products' và biểu tượng giỏ hàng hiển thị bình thường.


Xem chi tiết: [TS-01.md](EPIC_01_Authentication/TS-01.md)


---

<a id="ts-02"></a>

## Test Scenario: TS-02 - Kiểm tra thông báo lỗi khi để trống thông tin đăng nhập

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-02 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-02_AC1, US-02_AC2 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang đăng nhập. |

### 1. Objective
Đảm bảo hệ thống chặn đăng nhập và hiển thị đúng thông báo lỗi yêu cầu khi người dùng để trống Username hoặc Password.

### 2. Expected Outcome
Hiển thị thông báo lỗi tương ứng ('Epic sadface: Username is required' hoặc 'Epic sadface: Password is required') và không tạo phiên làm việc.


Xem chi tiết: [TS-02.md](EPIC_01_Authentication/TS-02.md)


---

<a id="ts-03"></a>

## Test Scenario: TS-03 - Kiểm tra từ chối đăng nhập khi nhập sai tài khoản hoặc mật khẩu

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-03 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-02_AC3 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang đăng nhập. |

### 1. Objective
Đảm bảo hệ thống từ chối xác thực khi nhập tài khoản không tồn tại hoặc sai mật khẩu và cảnh báo người dùng an toàn.

### 2. Expected Outcome
Hiển thị thông báo lỗi 'Epic sadface: Username and password do not match any user in this service'.


Xem chi tiết: [TS-03.md](EPIC_01_Authentication/TS-03.md)


---

<a id="ts-04"></a>

## Test Scenario: TS-04 - Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-04 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-02_AC4 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang đăng nhập. |

### 1. Objective
Đảm bảo tài khoản nằm trong danh sách bị khóa ('locked_out_user') bị từ chối truy cập và nhận được thông báo cụ thể.

### 2. Expected Outcome
Hiển thị thông báo lỗi 'Epic sadface: Sorry, this user has been locked out.' và không cho phép truy cập.


Xem chi tiết: [TS-04.md](EPIC_01_Authentication/TS-04.md)


---

<a id="ts-05"></a>

## Test Scenario: TS-05 - Kiểm tra đăng xuất an toàn và chặn truy cập trực tiếp URL nội bộ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-05 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-03_AC1, US-03_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang đăng nhập hợp lệ tại trang '/inventory.html'. |

### 1. Objective
Đảm bảo người dùng có thể đăng xuất qua menu sidebar và không thể dùng URL trực tiếp để truy cập các trang nội bộ sau khi đã đăng xuất.

### 2. Expected Outcome
Phiên làm việc bị hủy, quay về trang đăng nhập và chặn truy cập trái phép bằng URL trực tiếp.


Xem chi tiết: [TS-05.md](EPIC_01_Authentication/TS-05.md)


---

<a id="ts-06"></a>

## Test Scenario: TS-06 - Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và thông tin giá cả

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-06 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-04_AC1 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đăng nhập thành công bằng tài khoản standard_user. |

### 1. Objective
Kiểm tra trang danh mục sản phẩm hiển thị chính xác 6 mặt hàng với đầy đủ tên, ảnh đại diện, mô tả và giá tiền chuẩn định dạng.

### 2. Expected Outcome
Tất cả 6 sản phẩm hiển thị đầy đủ, không bị thiếu sót thông tin hay sai định dạng giá.


Xem chi tiết: [TS-06.md](EPIC_02_Product_Catalog/TS-06.md)


---

<a id="ts-07"></a>

## Test Scenario: TS-07 - Kiểm tra xem trang chi tiết sản phẩm và chức năng quay lại danh mục

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-07 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-04_AC2, US-04_AC3, US-04_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang danh mục '/inventory.html'. |

### 1. Objective
Xác minh khi nhấp vào tên hoặc ảnh sản phẩm sẽ mở đúng trang chi tiết của sản phẩm đó và nút quay lại hoạt động tốt.

### 2. Expected Outcome
Mở đúng trang chi tiết với thông số đầy đủ, nút 'Back to products' đưa người dùng quay lại danh mục.


Xem chi tiết: [TS-07.md](EPIC_02_Product_Catalog/TS-07.md)


---

<a id="ts-08"></a>

## Test Scenario: TS-08 - Kiểm tra sắp xếp danh mục sản phẩm theo bảng chữ cái (A-Z và Z-A)

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-08 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-05_AC1, US-05_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang danh mục sản phẩm. |

### 1. Objective
Đảm bảo bộ chọn sắp xếp có thể thay đổi thứ tự hiển thị sản phẩm chính xác theo thứ tự chữ cái A đến Z và ngược lại từ Z đến A.

### 2. Expected Outcome
Danh sách sản phẩm tự động sắp xếp lại chuẩn xác theo đúng thứ tự chữ cái đã chọn.


Xem chi tiết: [TS-08.md](EPIC_02_Product_Catalog/TS-08.md)


---

<a id="ts-09"></a>

## Test Scenario: TS-09 - Kiểm tra sắp xếp danh mục sản phẩm theo giá số học (thấp đến cao và cao đến thấp)

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-09 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-05_AC3, US-05_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang danh mục sản phẩm. |

### 1. Objective
Đảm bảo bộ chọn sắp xếp có thể thay đổi thứ tự sản phẩm dựa trên giá tiền thực tế (từ thấp nhất \$7.99 đến cao nhất \$49.99 và ngược lại).

### 2. Expected Outcome
Sản phẩm được sắp xếp chuẩn theo giá trị số học của đơn giá, không bị lỗi so sánh chuỗi ký tự.


Xem chi tiết: [TS-09.md](EPIC_02_Product_Catalog/TS-09.md)


---

<a id="ts-10"></a>

## Test Scenario: TS-10 - Kiểm tra tính toàn vẹn hình ảnh và độ ổn định giao diện danh mục sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-10 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-04_AC1 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra thấp) |
| **Preconditions** | Đăng nhập bằng tài khoản 'problem_user'. |

### 1. Objective
Xác minh các phần tử hình ảnh trên danh mục sản phẩm hiển thị đầy đủ, đồng nhất và không có hình ảnh bị vỡ hoặc trỏ sai đường dẫn tài nguyên.

### 2. Expected Outcome
Hình ảnh của tất cả sản phẩm hiển thị rõ nét, đúng tỷ lệ và đúng tài nguyên tương ứng với từng mặt hàng.


Xem chi tiết: [TS-10.md](EPIC_02_Product_Catalog/TS-10.md)


---

<a id="ts-11"></a>

## Test Scenario: TS-11 - Kiểm tra thêm sản phẩm vào giỏ hàng và tăng số lượng trên huy hiệu giỏ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-11 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-06_AC1, US-06_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang danh mục với giỏ hàng rỗng. |

### 1. Objective
Đảm bảo nhấp vào nút 'Add to cart' đổi nhãn nút thành 'Remove' và tăng số lượng hiển thị trên huy hiệu giỏ hàng.

### 2. Expected Outcome
Nút đổi sang 'Remove' và huy hiệu giỏ hàng cập nhật số lượng tăng dần chính xác.


Xem chi tiết: [TS-11.md](EPIC_03_Shopping_Cart/TS-11.md)


---

<a id="ts-12"></a>

## Test Scenario: TS-12 - Kiểm tra xóa sản phẩm khỏi giỏ hàng ngay tại trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-12 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-07_AC1, US-07_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Đã có ít nhất 1 sản phẩm trong giỏ hàng. |

### 1. Objective
Đảm bảo nhấp vào nút 'Remove' của sản phẩm đã thêm sẽ đưa sản phẩm ra khỏi giỏ và giảm số lượng trên huy hiệu giỏ hàng.

### 2. Expected Outcome
Nút đổi về lại 'Add to cart' và huy hiệu giỏ hàng giảm tương ứng (hoặc biến mất nếu hết sản phẩm).


Xem chi tiết: [TS-12.md](EPIC_03_Shopping_Cart/TS-12.md)


---

<a id="ts-13"></a>

## Test Scenario: TS-13 - Kiểm tra trang giỏ hàng hiển thị đúng danh sách, số lượng và giá sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-13 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-08_AC1 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đã thêm 2 sản phẩm vào giỏ hàng. |

### 1. Objective
Đảm bảo khi mở trang giỏ hàng ('/cart.html'), toàn bộ sản phẩm đã chọn đều hiển thị đủ với số lượng QTY = 1 và giá tiền chính xác.

### 2. Expected Outcome
Hiển thị đúng 2 sản phẩm với đầy đủ tên, giá và số lượng quy định.


Xem chi tiết: [TS-13.md](EPIC_03_Shopping_Cart/TS-13.md)


---

<a id="ts-14"></a>

## Test Scenario: TS-14 - Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-14 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-07_AC2, US-07_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/cart.html' có sản phẩm. |

### 1. Objective
Đảm bảo nhấp vào nút 'Remove' cạnh sản phẩm trong trang giỏ hàng sẽ xóa dòng sản phẩm đó khỏi bảng và cập nhật huy hiệu.

### 2. Expected Outcome
Dòng sản phẩm bị xóa khỏi danh sách và số lượng trên huy hiệu giỏ hàng giảm đi 1 đơn vị.


Xem chi tiết: [TS-14.md](EPIC_03_Shopping_Cart/TS-14.md)


---

<a id="ts-15"></a>

## Test Scenario: TS-15 - Kiểm tra tính bền vững của giỏ hàng khi tải lại trang hoặc điều hướng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-15 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-08_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Đã có sản phẩm trong giỏ hàng. |

### 1. Objective
Đảm bảo dữ liệu giỏ hàng không bị mất khi người dùng chuyển qua lại giữa các màn hình hoặc nhấn phím F5 làm mới trình duyệt.

### 2. Expected Outcome
Giỏ hàng và huy hiệu số lượng giữ nguyên trạng thái dữ liệu nguyên vẹn sau khi tải lại trang.


Xem chi tiết: [TS-15.md](EPIC_03_Shopping_Cart/TS-15.md)


---

<a id="ts-16"></a>

## Test Scenario: TS-16 - Kiểm tra chuyển từ giỏ hàng sang trang thanh toán Bước 1

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-16 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC1 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang giỏ hàng với ít nhất 1 sản phẩm. |

### 1. Objective
Đảm bảo nút 'Checkout' tại trang giỏ hàng mở thành công màn hình nhập thông tin người nhận hàng ('/checkout-step-one.html').

### 2. Expected Outcome
Mở trang Checkout Bước 1 với đầy đủ các ô nhập liệu First Name, Last Name và Postal Code.


Xem chi tiết: [TS-16.md](EPIC_04_Checkout/TS-16.md)


---

<a id="ts-17"></a>

## Test Scenario: TS-17 - Kiểm tra bắt buộc nhập thông tin khách hàng tại Bước 1 khi để trống trường

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-17 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC2, US-09_AC3, US-09_AC4 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-one.html'. |

### 1. Objective
Đảm bảo hệ thống chặn tiếp tục thanh toán và báo lỗi cụ thể khi bỏ trống First Name, Last Name hoặc Zip/Postal Code.

### 2. Expected Outcome
Hiển thị thông báo lỗi tương ứng với trường bị thiếu và không cho phép sang Bước 2.


Xem chi tiết: [TS-17.md](EPIC_04_Checkout/TS-17.md)


---

<a id="ts-18"></a>

## Test Scenario: TS-18 - Kiểm tra xử lý các định dạng mã bưu điện đặc biệt tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-18 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC5 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-one.html'. |

### 1. Objective
Khảo sát và kiểm tra cách form xử lý đối với các mã bưu điện gồm chữ, số quốc tế hoặc ký tự khoảng trắng.

### 2. Expected Outcome
Hệ thống tiếp nhận thông tin hợp lệ hoặc xử lý các chuỗi ký tự theo đúng quy chuẩn ứng dụng.


Xem chi tiết: [TS-18.md](EPIC_04_Checkout/TS-18.md)


---

<a id="ts-19"></a>

## Test Scenario: TS-19 - Kiểm tra nút Cancel tại Bước 1 quay lại giỏ hàng an toàn

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-19 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC6 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-one.html'. |

### 1. Objective
Đảm bảo nút 'Cancel' tại Checkout Bước 1 đưa người dùng trở lại trang giỏ hàng và không làm mất các sản phẩm đã chọn.

### 2. Expected Outcome
Quay về trang '/cart.html', dữ liệu các sản phẩm trong giỏ vẫn được giữ nguyên vẹn.


Xem chi tiết: [TS-19.md](EPIC_04_Checkout/TS-19.md)


---

<a id="ts-20"></a>

## Test Scenario: TS-20 - Kiểm tra tính toán chính xác tiền hàng, thuế 8% và tổng tiền tại Bước 2

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-20 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-10_AC1, US-10_AC2, US-10_AC3, US-10_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Đã hoàn thành Bước 1 và chuyển sang '/checkout-step-two.html'. |

### 1. Objective
Kiểm tra tính toán tài chính tại màn hình tổng quan đơn hàng: Item total, Tax (8%) và Total bảo đảm chính xác từng xu.

### 2. Expected Outcome
Hiển thị đúng mã thẻ 'SauceCard #31437', đơn vị vận chuyển 'Free Pony Express Delivery!' và công thức toán học chính xác.


Xem chi tiết: [TS-20.md](EPIC_04_Checkout/TS-20.md)


---

<a id="ts-21"></a>

## Test Scenario: TS-21 - Kiểm tra nút Cancel tại Bước 2 hủy thanh toán và về trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-21 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-10_AC5 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-two.html'. |

### 1. Objective
Đảm bảo nút 'Cancel' tại Bước 2 đưa người dùng về lại trang danh mục '/inventory.html' mà không xóa giỏ hàng.

### 2. Expected Outcome
Chuyển về trang danh mục sản phẩm, giỏ hàng vẫn giữ nguyên các mặt hàng đã chọn.


Xem chi tiết: [TS-21.md](EPIC_04_Checkout/TS-21.md)


---

<a id="ts-22"></a>

## Test Scenario: TS-22 - Kiểm tra hoàn tất đơn hàng Bước 3, hiển thị biên lai và làm sạch giỏ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-22 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-11_AC1, US-11_AC2, US-11_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở màn hình Bước 2. |

### 1. Objective
Đảm bảo nhấp vào nút 'Finish' sẽ chốt đơn hàng, hiển thị thông điệp cảm ơn và tự động dọn sạch giỏ hàng.

### 2. Expected Outcome
Hiển thị thông điệp 'Thank you for your order!', huy hiệu giỏ hàng biến mất và đơn hàng hoàn tất.


Xem chi tiết: [TS-22.md](EPIC_04_Checkout/TS-22.md)


---

<a id="ts-23"></a>

## Test Scenario: TS-23 - Kiểm tra hành vi hệ thống khi tiến hành thanh toán với giỏ hàng rỗng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-23 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC1 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng cao, Khả năng xảy ra thấp) |
| **Preconditions** | Giỏ hàng hoàn toàn không có sản phẩm (0 items). |

### 1. Objective
Kiểm tra xem hệ thống có cho phép người dùng thanh toán khi không có sản phẩm nào trong giỏ hay không để phát hiện lỗi logic.

### 2. Expected Outcome
Ghi nhận phản ứng của hệ thống (nếu cho phép checkout đơn hàng \$0.00 không có hàng thì ghi nhận là lỗi logic nghiệp vụ).


Xem chi tiết: [TS-23.md](EPIC_04_Checkout/TS-23.md)


---

<a id="ts-24"></a>

## Test Scenario: TS-24 - Kiểm tra mở và đóng menu Sidebar dạng trượt

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-24 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC1, US-12_AC5 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đã đăng nhập vào hệ thống. |

### 1. Objective
Đảm bảo nhấp vào biểu tượng 3 dấu gạch ngang mở menu trượt với 4 liên kết chức năng và nhấp nút 'X' để đóng menu.

### 2. Expected Outcome
Menu trượt hiển thị mượt mà đầy đủ 4 liên kết và đóng lại bình thường khi nhấp vào nút 'X'.


Xem chi tiết: [TS-24.md](EPIC_05_Sidebar_Navigation/TS-24.md)


---

<a id="ts-25"></a>

## Test Scenario: TS-25 - Kiểm tra liên kết 'All Items' trong sidebar chuyển về trang sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-25 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/cart.html'. |

### 1. Objective
Đảm bảo khi đang ở các trang con (như Giỏ hàng, Chi tiết sản phẩm), nhấp vào 'All Items' sẽ đưa người dùng về trang danh mục.

### 2. Expected Outcome
Chuyển hướng thành công về trang danh mục sản phẩm '/inventory.html'.


Xem chi tiết: [TS-25.md](EPIC_05_Sidebar_Navigation/TS-25.md)


---

<a id="ts-26"></a>

## Test Scenario: TS-26 - Kiểm tra liên kết 'About' trong sidebar mở website Sauce Labs

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-26 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | Low (Mức độ nghiêm trọng thấp, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đã đăng nhập. |

### 1. Objective
Đảm bảo nhấp vào 'About' sẽ điều hướng đúng ra website chính thức của Sauce Labs.

### 2. Expected Outcome
Trình duyệt điều hướng thành công đến 'https://saucelabs.com/'.


Xem chi tiết: [TS-26.md](EPIC_05_Sidebar_Navigation/TS-26.md)


---

<a id="ts-27"></a>

## Test Scenario: TS-27 - Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-27 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Đã thêm ít nhất 2 sản phẩm vào giỏ hàng. |

### 1. Objective
Đảm bảo chức năng 'Reset App State' xóa sạch toàn bộ sản phẩm đang có trong giỏ hàng và đặt lại toàn bộ nút trên danh mục về 'Add to cart'.

### 2. Expected Outcome
Huy hiệu giỏ hàng biến mất, toàn bộ các nút 'Remove' quay về trạng thái ban đầu 'Add to cart'.


Xem chi tiết: [TS-27.md](EPIC_05_Sidebar_Navigation/TS-27.md)


---

<a id="ts-28"></a>

## Test Scenario: TS-28 - Kiểm tra toàn diện quy trình mua sắm End-to-End với nhiều sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-28 |
| **Epic** | EPIC-06 - End-to-End E-Commerce Workflow |
| **UserStoryID** | US-13_AC1, US-13_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Trình duyệt sạch, tài khoản standard_user hợp lệ. |

### 1. Objective
Xác minh luồng mua hàng xuyên suốt từ đăng nhập, thêm nhiều món hàng, kiểm tra giỏ, nhập địa chỉ, thanh toán đến hoàn tất biên lai.

### 2. Expected Outcome
Quy trình thực hiện thông suốt từ đầu đến cuối, số tiền tính toán chuẩn xác và kết thúc bằng thông báo thành công.


Xem chi tiết: [TS-28.md](EPIC_06_End_to_End/TS-28.md)


---

<a id="ts-29"></a>

## Test Scenario: TS-29 - Kiểm tra luồng mua sắm kết hợp sắp xếp giá và xóa bớt sản phẩm trong giỏ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-29 |
| **Epic** | EPIC-06 - End-to-End E-Commerce Workflow |
| **UserStoryID** | US-13_AC1, US-13_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đăng nhập thành công. |

### 1. Objective
Xác minh hành vi người dùng lướt lọc sản phẩm theo giá, thêm 2 món, vào giỏ hàng bỏ bớt 1 món rồi thanh toán món còn lại.

### 2. Expected Outcome
Dữ liệu hóa đơn ở các bước thanh toán phản ánh chính xác các thay đổi sau khi đã bỏ bớt sản phẩm.


Xem chi tiết: [TS-29.md](EPIC_06_End_to_End/TS-29.md)


---

<a id="ts-30"></a>

## Test Scenario: TS-30 - Kiểm tra tính an toàn dữ liệu khi đặt lại trạng thái ứng dụng giữa chừng thanh toán

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-30 |
| **Epic** | EPIC-06 - End-to-End E-Commerce Workflow |
| **UserStoryID** | US-13_AC1, US-13_AC3 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng cao, Khả năng xảy ra thấp) |
| **Preconditions** | Người dùng đang ở bước Checkout Bước 2. |

### 1. Objective
Thử nghiệm kích hoạt 'Reset App State' khi đang ở màn hình thanh toán Bước 2 để kiểm tra khả năng kiểm soát dữ liệu của hệ thống.

### 2. Expected Outcome
Ghi nhận cách ứng dụng xử lý khi giỏ hàng bị xóa trong lúc đơn hàng đang chờ xác nhận thanh toán.


Xem chi tiết: [TS-30.md](EPIC_06_End_to_End/TS-30.md)


---

<a id="ts-31"></a>

## Test Scenario: TS-31 - Kiểm thử các giao thức hợp đồng và xử lý phản hồi mã lỗi RESTful API

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-31 |
| **Epic** | EPIC-07 - Backend Services & Database Data Integrity |
| **UserStoryID** | US-14_AC1, US-14_AC2, US-14_AC3 |
| **Path Type** | Contract / Integration Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Môi trường giả lập API Backend hoặc tài liệu Swagger/OpenAPI được cung cấp. |

### 1. Objective
Kiểm tra cấu trúc và tính hợp lệ của các endpoint RESTful API cốt lõi (Đăng nhập, Danh mục sản phẩm, Giỏ hàng, Đặt hàng) qua phương thức HTTP POST/GET và mã trạng thái chuẩn.

### 2. Expected Outcome
Các API trả về đúng HTTP status (200, 201, 401, 423) cùng payload JSON phản hồi đúng định dạng schema.


Xem chi tiết: [TS-31.md](EPIC_07_Backend_Database/TS-31.md)


---

<a id="ts-32"></a>

## Test Scenario: TS-32 - Kiểm thử tính toàn vẹn dữ liệu và giao dịch ACID trong cơ sở dữ liệu quan hệ (SQL)

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-32 |
| **Epic** | EPIC-07 - Backend Services & Database Data Integrity |
| **UserStoryID** | US-15_AC1, US-15_AC2, US-15_AC3 |
| **Path Type** | Database / Data Integrity Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Có quyền kết nối và truy vấn vào máy chủ cơ sở dữ liệu (PostgreSQL/MySQL). |

### 1. Objective
Thực thi truy vấn SQL để xác minh tính nhất quán dữ liệu người dùng, tính chính xác của giá sản phẩm và tính toàn vẹn khóa ngoại trong giao dịch đặt hàng.

### 2. Expected Outcome
Mật khẩu được băm an toàn, dữ liệu giá khớp giao diện, các giao dịch đơn hàng commit đầy đủ theo tính chất ACID.


Xem chi tiết: [TS-32.md](EPIC_07_Backend_Database/TS-32.md)


---

<a id="ts-33"></a>

## Test Scenario: TS-33 - Kiểm thử bảo mật phiên làm việc và phòng chống tấn công tiêm mã (Security & XSS)

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-33 |
| **Epic** | EPIC-08 - Non-Functional Quality Attributes & Security Standards |
| **UserStoryID** | US-16_AC1, US-16_AC2, US-16_AC3 |
| **Path Type** | Security / Defensive Path |
| **Risk Priority** | High (Mức độ nghiêm trọng rất cao, Khả năng xảy ra thấp) |
| **Preconditions** | Người dùng ở trang đăng nhập hoặc các biểu mẫu nhập thông tin thanh toán. |

### 1. Objective
Xác minh các biện pháp bảo vệ chống tấn công XSS qua form nhập liệu, cờ bảo mật cookie phiên và cơ chế ngăn chặn xem lại trang bảo mật sau khi đăng xuất.

### 2. Expected Outcome
Script độc hại bị mã hóa an toàn, cookie được bảo vệ, và không thể truy cập lại trang nội bộ bằng nút Back sau khi logout.


Xem chi tiết: [TS-33.md](EPIC_08_Non_Functional_Quality/TS-33.md)


---

<a id="ts-34"></a>

## Test Scenario: TS-34 - Kiểm thử các thuộc tính phi chức năng: Hiệu năng SLA, Tiếp cận WCAG, Usability và Tương thích

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-34 |
| **Epic** | EPIC-08 - Non-Functional Quality Attributes & Security Standards |
| **UserStoryID** | US-17_AC1, US-17_AC2, US-17_AC3 |
| **Path Type** | Non-Functional Quality Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Trình duyệt được thiết lập DevTools (Performance, Lighthouse) và các viewport thử nghiệm. |

### 1. Objective
Đo lường thời gian tải trang theo SLA, kiểm tra hỗ trợ bàn phím/aria-label theo WCAG 2.1 AA, tính nhất quán UX và độ co giãn trên màn hình di động.

### 2. Expected Outcome
Trang đạt SLA tải dưới 2s cho người dùng bình thường, điều hướng bàn phím rõ nét, và giao diện hiển thị chuẩn xác trên mobile.


Xem chi tiết: [TS-34.md](EPIC_08_Non_Functional_Quality/TS-34.md)


---
