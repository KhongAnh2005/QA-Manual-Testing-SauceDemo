# Test Scenarios Document: SauceDemo E-Commerce Web Application

**Target Application:** SauceDemo ([https://www.saucedemo.com/](https://www.saucedemo.com/))  
**Methodology:** Deconstructing Requirements into Scenarios (Happy Path & Negative Path, Risk Matrix)  
**Author / Owner:** QA - Khổng Đức Anh  
**Total Scenarios:** 30 Scenarios  
**Status:** Approved (Baseline for Test Case Design)  

---

## Table of Contents

- [1. Overview & Scenario Design Strategy](#ts-section-1)
- [2. Test Scenarios Summary Table](#ts-section-2)
- [3. Detailed Test Scenarios by Epic](#ts-section-3)
  - [EPIC-01: Authentication & Session Management](#ts-epic-01)
  - [EPIC-02: Product Catalog & Inventory Browsing](#ts-epic-02)
  - [EPIC-03: Shopping Cart Management](#ts-epic-03)
  - [EPIC-04: Checkout Workflow](#ts-epic-04)
  - [EPIC-05: Sidebar Navigation & App State](#ts-epic-05)
  - [EPIC-06: End-to-End E-Commerce Workflow](#ts-epic-06)

---

<a id="ts-section-1"></a>
## 1. Overview & Scenario Design Strategy

Tài liệu Test Scenarios phân tích và bẻ gãy 13 User Stories từ Requirement Document thành 30 kịch bản kiểm thử độc lập.
Mỗi User Story đều được phân tích thành cả **Happy Path** (luồng chuẩn lý tưởng) và **Negative Path** (luồng ngoại lệ, kiểm tra tính phục hồi và bảo mật), đồng thời được đánh giá mức độ rủi ro nghiệp vụ (**Business Risk Matrix**) dựa trên Tác động nghiệp vụ (Business Impact) và Khả năng xảy ra (Likelihood).
Cột **UserStoryID** liên kết rõ ràng đến từng tiêu chí nghiệm thu tương ứng (ví dụ: `US-01_AC1, US-01_AC2`) giúp việc truy xuất trở nên thuận tiện và trực quan.

<a id="ts-section-2"></a>
## 2. Test Scenarios Summary Table

| **Scenario ID** | **Epic** | **UserStoryID** | **Scenario Title** | **Path Type** | **Risk Priority** |
|:---|:---|:---|:---|:---:|:---|
| **TS-01** | EPIC-01 | US-01_AC1, US-01_AC2, US-01_AC3 | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ | Happy Path | High |
| **TS-02** | EPIC-01 | US-02_AC1, US-02_AC2 | Kiểm tra thông báo lỗi khi để trống thông tin đăng nhập | Negative Path | High |
| **TS-03** | EPIC-01 | US-02_AC3 | Kiểm tra từ chối đăng nhập khi nhập sai tài khoản hoặc mật khẩu | Negative Path | High |
| **TS-04** | EPIC-01 | US-02_AC4 | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa | Negative Path | High |
| **TS-05** | EPIC-01 | US-03_AC1, US-03_AC2 | Kiểm tra đăng xuất an toàn và chặn truy cập trực tiếp URL nội bộ | Happy Path | High |
| **TS-06** | EPIC-02 | US-04_AC1 | Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và thông tin giá cả | Happy Path | High |
| **TS-07** | EPIC-02 | US-04_AC2, US-04_AC3, US-04_AC4 | Kiểm tra xem trang chi tiết sản phẩm và chức năng quay lại danh mục | Happy Path | Medium |
| **TS-08** | EPIC-02 | US-05_AC1, US-05_AC2 | Kiểm tra sắp xếp danh mục sản phẩm theo bảng chữ cái (A-Z và Z-A) | Happy Path | Medium |
| **TS-09** | EPIC-02 | US-05_AC3, US-05_AC4 | Kiểm tra sắp xếp danh mục sản phẩm theo giá số học (thấp đến cao và cao đến thấp) | Happy Path | Medium |
| **TS-10** | EPIC-02 | US-04_AC1 | Kiểm tra độ ổn định giao diện danh mục đối với tài khoản lỗi (problem_user) | Negative Path | Medium |
| **TS-11** | EPIC-03 | US-06_AC1, US-06_AC2 | Kiểm tra thêm sản phẩm vào giỏ hàng và tăng số lượng trên huy hiệu giỏ | Happy Path | High |
| **TS-12** | EPIC-03 | US-07_AC1, US-07_AC3 | Kiểm tra xóa sản phẩm khỏi giỏ hàng ngay tại trang danh mục | Happy Path | High |
| **TS-13** | EPIC-03 | US-08_AC1 | Kiểm tra trang giỏ hàng hiển thị đúng danh sách, số lượng và giá sản phẩm | Happy Path | High |
| **TS-14** | EPIC-03 | US-07_AC2, US-07_AC3 | Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng | Happy Path | High |
| **TS-15** | EPIC-03 | US-08_AC3 | Kiểm tra tính bền vững của giỏ hàng khi tải lại trang hoặc điều hướng | Happy Path | High |
| **TS-16** | EPIC-04 | US-09_AC1 | Kiểm tra chuyển từ giỏ hàng sang trang thanh toán Bước 1 | Happy Path | High |
| **TS-17** | EPIC-04 | US-09_AC2, US-09_AC3, US-09_AC4 | Kiểm tra bắt buộc nhập thông tin khách hàng tại Bước 1 khi để trống trường | Negative Path | High |
| **TS-18** | EPIC-04 | US-09_AC5 | Kiểm tra xử lý các định dạng mã bưu điện đặc biệt tại Bước 1 | Negative Path | Medium |
| **TS-19** | EPIC-04 | US-09_AC6 | Kiểm tra nút Cancel tại Bước 1 quay lại giỏ hàng an toàn | Happy Path | Medium |
| **TS-20** | EPIC-04 | US-10_AC1, US-10_AC2, US-10_AC3, US-10_AC4 | Kiểm tra tính toán chính xác tiền hàng, thuế 8% và tổng tiền tại Bước 2 | Happy Path | High |
| **TS-21** | EPIC-04 | US-10_AC5 | Kiểm tra nút Cancel tại Bước 2 hủy thanh toán và về trang danh mục | Happy Path | Medium |
| **TS-22** | EPIC-04 | US-11_AC1, US-11_AC2, US-11_AC3 | Kiểm tra hoàn tất đơn hàng Bước 3, hiển thị biên lai và làm sạch giỏ | Happy Path | High |
| **TS-23** | EPIC-04 | US-09_AC1 | Kiểm tra hành vi hệ thống khi tiến hành thanh toán với giỏ hàng rỗng | Negative Path | Medium |
| **TS-24** | EPIC-05 | US-12_AC1, US-12_AC5 | Kiểm tra mở và đóng menu Sidebar dạng trượt | Happy Path | Medium |
| **TS-25** | EPIC-05 | US-12_AC2 | Kiểm tra liên kết 'All Items' trong sidebar chuyển về trang sản phẩm | Happy Path | Medium |
| **TS-26** | EPIC-05 | US-12_AC3 | Kiểm tra liên kết 'About' trong sidebar mở website Sauce Labs | Happy Path | Low |
| **TS-27** | EPIC-05 | US-12_AC4 | Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng | Happy Path | High |
| **TS-28** | EPIC-06 | US-13_AC1, US-13_AC2 | Kiểm tra toàn diện quy trình mua sắm End-to-End với nhiều sản phẩm | Happy Path | High |
| **TS-29** | EPIC-06 | US-13_AC1, US-13_AC2 | Kiểm tra luồng mua sắm kết hợp sắp xếp giá và xóa bớt sản phẩm trong giỏ | Happy Path | High |
| **TS-30** | EPIC-06 | US-13_AC1, US-13_AC3 | Kiểm tra tính an toàn dữ liệu khi đặt lại trạng thái ứng dụng giữa chừng thanh toán | Negative Path | Medium |

---

<a id="ts-section-3"></a>
## 3. Detailed Test Scenarios by Epic

<a id="ts-epic-01"></a>
### EPIC-01: Authentication & Session Management

#### [TS-01] Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-01 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-01_AC1, US-01_AC2, US-01_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang đăng nhập (https://www.saucedemo.com/) với trình duyệt sạch (chưa có cookie phiên). |

##### Objective
Đảm bảo người dùng hợp lệ có thể đăng nhập thành công bằng tài khoản tiêu chuẩn ('standard_user' / 'secret_sauce') và truy cập vào trang danh mục sản phẩm bình thường.

##### Expected Outcome
Đăng nhập thành công, chuyển hướng đến '/inventory.html', tiêu đề hiển thị 'Products' và biểu tượng giỏ hàng hiển thị bình thường.

#### [TS-02] Kiểm tra thông báo lỗi khi để trống thông tin đăng nhập

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-02 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-02_AC1, US-02_AC2 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang đăng nhập. |

##### Objective
Đảm bảo hệ thống chặn đăng nhập và hiển thị đúng thông báo lỗi yêu cầu khi người dùng để trống Username hoặc Password.

##### Expected Outcome
Hiển thị thông báo lỗi tương ứng ('Epic sadface: Username is required' hoặc 'Epic sadface: Password is required') và không tạo phiên làm việc.

#### [TS-03] Kiểm tra từ chối đăng nhập khi nhập sai tài khoản hoặc mật khẩu

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-03 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-02_AC3 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang đăng nhập. |

##### Objective
Đảm bảo hệ thống từ chối xác thực khi nhập tài khoản không tồn tại hoặc sai mật khẩu và cảnh báo người dùng an toàn.

##### Expected Outcome
Hiển thị thông báo lỗi 'Epic sadface: Username and password do not match any user in this service'.

#### [TS-04] Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-04 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-02_AC4 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang đăng nhập. |

##### Objective
Đảm bảo tài khoản nằm trong danh sách bị khóa ('locked_out_user') bị từ chối truy cập và nhận được thông báo cụ thể.

##### Expected Outcome
Hiển thị thông báo lỗi 'Epic sadface: Sorry, this user has been locked out.' và không cho phép truy cập.

#### [TS-05] Kiểm tra đăng xuất an toàn và chặn truy cập trực tiếp URL nội bộ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-05 |
| **Epic** | EPIC-01 - Authentication & Session Management |
| **UserStoryID** | US-03_AC1, US-03_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang đăng nhập hợp lệ tại trang '/inventory.html'. |

##### Objective
Đảm bảo người dùng có thể đăng xuất qua menu sidebar và không thể dùng URL trực tiếp để truy cập các trang nội bộ sau khi đã đăng xuất.

##### Expected Outcome
Phiên làm việc bị hủy, quay về trang đăng nhập và chặn truy cập trái phép bằng URL trực tiếp.

---

<a id="ts-epic-02"></a>
### EPIC-02: Product Catalog & Inventory Browsing

#### [TS-06] Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và thông tin giá cả

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-06 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-04_AC1 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đăng nhập thành công bằng tài khoản standard_user. |

##### Objective
Kiểm tra trang danh mục sản phẩm hiển thị chính xác 6 mặt hàng với đầy đủ tên, ảnh đại diện, mô tả và giá tiền chuẩn định dạng.

##### Expected Outcome
Tất cả 6 sản phẩm hiển thị đầy đủ, không bị thiếu sót thông tin hay sai định dạng giá.

#### [TS-07] Kiểm tra xem trang chi tiết sản phẩm và chức năng quay lại danh mục

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-07 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-04_AC2, US-04_AC3, US-04_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang danh mục '/inventory.html'. |

##### Objective
Xác minh khi nhấp vào tên hoặc ảnh sản phẩm sẽ mở đúng trang chi tiết của sản phẩm đó và nút quay lại hoạt động tốt.

##### Expected Outcome
Mở đúng trang chi tiết với thông số đầy đủ, nút 'Back to products' đưa người dùng quay lại danh mục.

#### [TS-08] Kiểm tra sắp xếp danh mục sản phẩm theo bảng chữ cái (A-Z và Z-A)

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-08 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-05_AC1, US-05_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang danh mục sản phẩm. |

##### Objective
Đảm bảo bộ chọn sắp xếp có thể thay đổi thứ tự hiển thị sản phẩm chính xác theo thứ tự chữ cái A đến Z và ngược lại từ Z đến A.

##### Expected Outcome
Danh sách sản phẩm tự động sắp xếp lại chuẩn xác theo đúng thứ tự chữ cái đã chọn.

#### [TS-09] Kiểm tra sắp xếp danh mục sản phẩm theo giá số học (thấp đến cao và cao đến thấp)

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-09 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-05_AC3, US-05_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang danh mục sản phẩm. |

##### Objective
Đảm bảo bộ chọn sắp xếp có thể thay đổi thứ tự sản phẩm dựa trên giá tiền thực tế (từ thấp nhất \$7.99 đến cao nhất \$49.99 và ngược lại).

##### Expected Outcome
Sản phẩm được sắp xếp chuẩn theo giá trị số học của đơn giá, không bị lỗi so sánh chuỗi ký tự.

#### [TS-10] Kiểm tra độ ổn định giao diện danh mục đối với tài khoản lỗi (problem_user)

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-10 |
| **Epic** | EPIC-02 - Product Catalog & Inventory Browsing |
| **UserStoryID** | US-04_AC1 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra thấp) |
| **Preconditions** | Đăng nhập bằng tài khoản 'problem_user'. |

##### Objective
Khảo sát và ghi nhận các lỗi hiển thị hình ảnh sản phẩm khi đăng nhập bằng tài khoản giả lập lỗi của Sauce Labs.

##### Expected Outcome
Ghi nhận hiện tượng hỏng ảnh sản phẩm (ảnh bị thay thế hàng loạt bởi hình ảnh con chó) để lập báo cáo lỗi.

---

<a id="ts-epic-03"></a>
### EPIC-03: Shopping Cart Management

#### [TS-11] Kiểm tra thêm sản phẩm vào giỏ hàng và tăng số lượng trên huy hiệu giỏ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-11 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-06_AC1, US-06_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang danh mục với giỏ hàng rỗng. |

##### Objective
Đảm bảo nhấp vào nút 'Add to cart' đổi nhãn nút thành 'Remove' và tăng số lượng hiển thị trên huy hiệu giỏ hàng.

##### Expected Outcome
Nút đổi sang 'Remove' và huy hiệu giỏ hàng cập nhật số lượng tăng dần chính xác.

#### [TS-12] Kiểm tra xóa sản phẩm khỏi giỏ hàng ngay tại trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-12 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-07_AC1, US-07_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Đã có ít nhất 1 sản phẩm trong giỏ hàng. |

##### Objective
Đảm bảo nhấp vào nút 'Remove' của sản phẩm đã thêm sẽ đưa sản phẩm ra khỏi giỏ và giảm số lượng trên huy hiệu giỏ hàng.

##### Expected Outcome
Nút đổi về lại 'Add to cart' và huy hiệu giỏ hàng giảm tương ứng (hoặc biến mất nếu hết sản phẩm).

#### [TS-13] Kiểm tra trang giỏ hàng hiển thị đúng danh sách, số lượng và giá sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-13 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-08_AC1 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đã thêm 2 sản phẩm vào giỏ hàng. |

##### Objective
Đảm bảo khi mở trang giỏ hàng ('/cart.html'), toàn bộ sản phẩm đã chọn đều hiển thị đủ với số lượng QTY = 1 và giá tiền chính xác.

##### Expected Outcome
Hiển thị đúng 2 sản phẩm với đầy đủ tên, giá và số lượng quy định.

#### [TS-14] Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-14 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-07_AC2, US-07_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/cart.html' có sản phẩm. |

##### Objective
Đảm bảo nhấp vào nút 'Remove' cạnh sản phẩm trong trang giỏ hàng sẽ xóa dòng sản phẩm đó khỏi bảng và cập nhật huy hiệu.

##### Expected Outcome
Dòng sản phẩm bị xóa khỏi danh sách và số lượng trên huy hiệu giỏ hàng giảm đi 1 đơn vị.

#### [TS-15] Kiểm tra tính bền vững của giỏ hàng khi tải lại trang hoặc điều hướng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-15 |
| **Epic** | EPIC-03 - Shopping Cart Management |
| **UserStoryID** | US-08_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Đã có sản phẩm trong giỏ hàng. |

##### Objective
Đảm bảo dữ liệu giỏ hàng không bị mất khi người dùng chuyển qua lại giữa các màn hình hoặc nhấn phím F5 làm mới trình duyệt.

##### Expected Outcome
Giỏ hàng và huy hiệu số lượng giữ nguyên trạng thái dữ liệu nguyên vẹn sau khi tải lại trang.

---

<a id="ts-epic-04"></a>
### EPIC-04: Checkout Workflow

#### [TS-16] Kiểm tra chuyển từ giỏ hàng sang trang thanh toán Bước 1

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-16 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC1 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang giỏ hàng với ít nhất 1 sản phẩm. |

##### Objective
Đảm bảo nút 'Checkout' tại trang giỏ hàng mở thành công màn hình nhập thông tin người nhận hàng ('/checkout-step-one.html').

##### Expected Outcome
Mở trang Checkout Bước 1 với đầy đủ các ô nhập liệu First Name, Last Name và Postal Code.

#### [TS-17] Kiểm tra bắt buộc nhập thông tin khách hàng tại Bước 1 khi để trống trường

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-17 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC2, US-09_AC3, US-09_AC4 |
| **Path Type** | Negative Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-one.html'. |

##### Objective
Đảm bảo hệ thống chặn tiếp tục thanh toán và báo lỗi cụ thể khi bỏ trống First Name, Last Name hoặc Zip/Postal Code.

##### Expected Outcome
Hiển thị thông báo lỗi tương ứng với trường bị thiếu và không cho phép sang Bước 2.

#### [TS-18] Kiểm tra xử lý các định dạng mã bưu điện đặc biệt tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-18 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC5 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-one.html'. |

##### Objective
Khảo sát và kiểm tra cách form xử lý đối với các mã bưu điện gồm chữ, số quốc tế hoặc ký tự khoảng trắng.

##### Expected Outcome
Hệ thống tiếp nhận thông tin hợp lệ hoặc xử lý các chuỗi ký tự theo đúng quy chuẩn ứng dụng.

#### [TS-19] Kiểm tra nút Cancel tại Bước 1 quay lại giỏ hàng an toàn

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-19 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC6 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-one.html'. |

##### Objective
Đảm bảo nút 'Cancel' tại Checkout Bước 1 đưa người dùng trở lại trang giỏ hàng và không làm mất các sản phẩm đã chọn.

##### Expected Outcome
Quay về trang '/cart.html', dữ liệu các sản phẩm trong giỏ vẫn được giữ nguyên vẹn.

#### [TS-20] Kiểm tra tính toán chính xác tiền hàng, thuế 8% và tổng tiền tại Bước 2

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-20 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-10_AC1, US-10_AC2, US-10_AC3, US-10_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Đã hoàn thành Bước 1 và chuyển sang '/checkout-step-two.html'. |

##### Objective
Kiểm tra tính toán tài chính tại màn hình tổng quan đơn hàng: Item total, Tax (8%) và Total bảo đảm chính xác từng xu.

##### Expected Outcome
Hiển thị đúng mã thẻ 'SauceCard #31437', đơn vị vận chuyển 'Free Pony Express Delivery!' và công thức toán học chính xác.

#### [TS-21] Kiểm tra nút Cancel tại Bước 2 hủy thanh toán và về trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-21 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-10_AC5 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đang ở trang '/checkout-step-two.html'. |

##### Objective
Đảm bảo nút 'Cancel' tại Bước 2 đưa người dùng về lại trang danh mục '/inventory.html' mà không xóa giỏ hàng.

##### Expected Outcome
Chuyển về trang danh mục sản phẩm, giỏ hàng vẫn giữ nguyên các mặt hàng đã chọn.

#### [TS-22] Kiểm tra hoàn tất đơn hàng Bước 3, hiển thị biên lai và làm sạch giỏ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-22 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-11_AC1, US-11_AC2, US-11_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở màn hình Bước 2. |

##### Objective
Đảm bảo nhấp vào nút 'Finish' sẽ chốt đơn hàng, hiển thị thông điệp cảm ơn và tự động dọn sạch giỏ hàng.

##### Expected Outcome
Hiển thị thông điệp 'Thank you for your order!', huy hiệu giỏ hàng biến mất và đơn hàng hoàn tất.

#### [TS-23] Kiểm tra hành vi hệ thống khi tiến hành thanh toán với giỏ hàng rỗng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-23 |
| **Epic** | EPIC-04 - Checkout Workflow |
| **UserStoryID** | US-09_AC1 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng cao, Khả năng xảy ra thấp) |
| **Preconditions** | Giỏ hàng hoàn toàn không có sản phẩm (0 items). |

##### Objective
Kiểm tra xem hệ thống có cho phép người dùng thanh toán khi không có sản phẩm nào trong giỏ hay không để phát hiện lỗi logic.

##### Expected Outcome
Ghi nhận phản ứng của hệ thống (nếu cho phép checkout đơn hàng \$0.00 không có hàng thì ghi nhận là lỗi logic nghiệp vụ).

---

<a id="ts-epic-05"></a>
### EPIC-05: Sidebar Navigation & App State

#### [TS-24] Kiểm tra mở và đóng menu Sidebar dạng trượt

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-24 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC1, US-12_AC5 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đã đăng nhập vào hệ thống. |

##### Objective
Đảm bảo nhấp vào biểu tượng 3 dấu gạch ngang mở menu trượt với 4 liên kết chức năng và nhấp nút 'X' để đóng menu.

##### Expected Outcome
Menu trượt hiển thị mượt mà đầy đủ 4 liên kết và đóng lại bình thường khi nhấp vào nút 'X'.

#### [TS-25] Kiểm tra liên kết 'All Items' trong sidebar chuyển về trang sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-25 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng trung bình, Khả năng xảy ra cao) |
| **Preconditions** | Người dùng đang ở trang '/cart.html'. |

##### Objective
Đảm bảo khi đang ở các trang con (như Giỏ hàng, Chi tiết sản phẩm), nhấp vào 'All Items' sẽ đưa người dùng về trang danh mục.

##### Expected Outcome
Chuyển hướng thành công về trang danh mục sản phẩm '/inventory.html'.

#### [TS-26] Kiểm tra liên kết 'About' trong sidebar mở website Sauce Labs

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-26 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC3 |
| **Path Type** | Happy Path |
| **Risk Priority** | Low (Mức độ nghiêm trọng thấp, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đã đăng nhập. |

##### Objective
Đảm bảo nhấp vào 'About' sẽ điều hướng đúng ra website chính thức của Sauce Labs.

##### Expected Outcome
Trình duyệt điều hướng thành công đến 'https://saucelabs.com/'.

#### [TS-27] Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-27 |
| **Epic** | EPIC-05 - Sidebar Navigation & App State |
| **UserStoryID** | US-12_AC4 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Đã thêm ít nhất 2 sản phẩm vào giỏ hàng. |

##### Objective
Đảm bảo chức năng 'Reset App State' xóa sạch toàn bộ sản phẩm đang có trong giỏ hàng và đặt lại toàn bộ nút trên danh mục về 'Add to cart'.

##### Expected Outcome
Huy hiệu giỏ hàng biến mất, toàn bộ các nút 'Remove' quay về trạng thái ban đầu 'Add to cart'.

---

<a id="ts-epic-06"></a>
### EPIC-06: End-to-End E-Commerce Workflow

#### [TS-28] Kiểm tra toàn diện quy trình mua sắm End-to-End với nhiều sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-28 |
| **Epic** | EPIC-06 - End-to-End E-Commerce Workflow |
| **UserStoryID** | US-13_AC1, US-13_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra cao) |
| **Preconditions** | Trình duyệt sạch, tài khoản standard_user hợp lệ. |

##### Objective
Xác minh luồng mua hàng xuyên suốt từ đăng nhập, thêm nhiều món hàng, kiểm tra giỏ, nhập địa chỉ, thanh toán đến hoàn tất biên lai.

##### Expected Outcome
Quy trình thực hiện thông suốt từ đầu đến cuối, số tiền tính toán chuẩn xác và kết thúc bằng thông báo thành công.

#### [TS-29] Kiểm tra luồng mua sắm kết hợp sắp xếp giá và xóa bớt sản phẩm trong giỏ

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-29 |
| **Epic** | EPIC-06 - End-to-End E-Commerce Workflow |
| **UserStoryID** | US-13_AC1, US-13_AC2 |
| **Path Type** | Happy Path |
| **Risk Priority** | High (Mức độ nghiêm trọng cao, Khả năng xảy ra trung bình) |
| **Preconditions** | Người dùng đăng nhập thành công. |

##### Objective
Xác minh hành vi người dùng lướt lọc sản phẩm theo giá, thêm 2 món, vào giỏ hàng bỏ bớt 1 món rồi thanh toán món còn lại.

##### Expected Outcome
Dữ liệu hóa đơn ở các bước thanh toán phản ánh chính xác các thay đổi sau khi đã bỏ bớt sản phẩm.

#### [TS-30] Kiểm tra tính an toàn dữ liệu khi đặt lại trạng thái ứng dụng giữa chừng thanh toán

| **Field** | **Value** |
|:---|:---|
| **Scenario ID** | TS-30 |
| **Epic** | EPIC-06 - End-to-End E-Commerce Workflow |
| **UserStoryID** | US-13_AC1, US-13_AC3 |
| **Path Type** | Negative Path |
| **Risk Priority** | Medium (Mức độ nghiêm trọng cao, Khả năng xảy ra thấp) |
| **Preconditions** | Người dùng đang ở bước Checkout Bước 2. |

##### Objective
Thử nghiệm kích hoạt 'Reset App State' khi đang ở màn hình thanh toán Bước 2 để kiểm tra khả năng kiểm soát dữ liệu của hệ thống.

##### Expected Outcome
Ghi nhận cách ứng dụng xử lý khi giỏ hàng bị xóa trong lúc đơn hàng đang chờ xác nhận thanh toán.

---

