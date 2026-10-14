# Requirement Traceability Matrix (RTM): SauceDemo Application

**Target Application:** SauceDemo ([https://www.saucedemo.com/](https://www.saucedemo.com/))  
**Standard Compliance:** The Requirement Traceability Matrix (RTM) & ISTQB Traceability Standard  
**Author / Owner:** QA - Khổng Đức Anh  
**Status:** Baseline Verified - 100% Requirement Coverage  

---

## Table of Contents

- [1. Executive Summary & Purpose](#rtm-section-1)
- [2. Coverage Metrics & Gap Analysis](#rtm-section-2)
- [3. Bi-Directional Traceability Matrix Table](#rtm-section-3)
- [4. Traceability Integrity Verification](#rtm-section-4)

---

<a id="rtm-section-1"></a>
## 1. Executive Summary & Purpose

Requirement Traceability Matrix (RTM) là tài liệu trọng yếu kết nối mục tiêu kinh doanh/yêu cầu người dùng với quy trình kiểm thử thực tế. Bảng RTM trả lời câu hỏi cốt lõi của Project Manager và Stakeholders: **"Are we covered?" (Chúng ta đã bao phủ hết tất cả các yêu cầu chưa?)**

### Các lợi ích cốt lõi của tài liệu RTM này:
1. **Chứng minh độ bao phủ 100% (Prove Full Coverage):** Xác thực 100% User Stories đều có ít nhất 1 kịch bản kiểm thử (Test Scenario) và Test Case tương ứng, hoàn toàn không có khoảng trống (Zero Coverage Gap).
2. **Đánh giá tác động (Assess Impact):** Khi yêu cầu thay đổi, lập tức xác định chính xác các Test Case cần cập nhật.
3. **Truy xuất hai chiều (Bi-directional Traceability):** Từ User Story ➔ Test Scenario ➔ Test Case ➔ Defect (Forward) và từ Defect ➔ Test Case ➔ User Story (Backward).

<a id="rtm-section-2"></a>
## 2. Coverage Metrics & Gap Analysis

| **Metrics Indicator** | **Count** | **Coverage Ratio** |
|:---|:---:|:---:|
| **Total Epics** | 8 | 100% |
| **Total User Stories** | 17 | 100% Covered |
| **Total Test Scenarios** | 34 | 100% Mapped |
| **Total Test Cases** | 71 | 100% Designed |
| **Coverage Gaps Detected** | **0** | **0% Gaps (Full Coverage)** |

---

<a id="rtm-section-3"></a>
## 3. Bi-Directional Traceability Matrix Table

| **Epic** | **UserStoryID** | **TestScenarioID** | **Test Case ID** | **Test Case Name** | **Priority** | **Status** |
|:---|:---|:---|:---|:---|:---:|:---:|
| EPIC-01 | **US-01** | TS-01 | **TC-01** | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ | High | Approved |
| EPIC-01 | **US-02** | TS-02 | **TC-02** | Kiểm tra thông báo lỗi khi để trống cả Username và Password | High | Approved |
| EPIC-01 | **US-02** | TS-02 | **TC-03** | Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password | High | Approved |
| EPIC-01 | **US-02** | TS-02 | **TC-04** | Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password | Medium | Approved |
| EPIC-01 | **US-02** | TS-03 | **TC-05** | Kiểm tra từ chối đăng nhập khi nhập sai thông tin tài khoản hoặc mật khẩu | High | Approved |
| EPIC-01 | **US-02** | TS-04 | **TC-06** | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) | High | Approved |
| EPIC-01 | **US-02** | TS-02 | **TC-07** | Kiểm tra thao tác đóng thông báo lỗi đăng nhập bằng nút 'X' | Low | Approved |
| EPIC-01 | **US-03** | TS-05 | **TC-08** | Kiểm tra đăng xuất tài khoản an toàn thông qua menu điều hướng Sidebar | High | Approved |
| EPIC-01 | **US-03** | TS-05 | **TC-09** | Kiểm tra chặn truy cập trực tiếp URL trang nội bộ khi chưa đăng nhập | High | Approved |
| EPIC-02 | **US-04** | TS-06 | **TC-10** | Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và các thông tin chi tiết | High | Approved |
| EPIC-02 | **US-04** | TS-07 | **TC-11** | Kiểm tra xem trang chi tiết sản phẩm khi nhấp vào tên hoặc ảnh sản phẩm | Medium | Approved |
| EPIC-02 | **US-04** | TS-07 | **TC-12** | Kiểm tra nút 'Back to products' quay lại trang danh mục từ trang chi tiết | Medium | Approved |
| EPIC-02 | **US-04** | TS-06 | **TC-17** | Kiểm tra tính toàn vẹn của liên kết hình ảnh danh mục sản phẩm đối với tài khoản problem_user | Medium | Approved |
| EPIC-02 | **US-05** | TS-08 | **TC-13** | Kiểm tra sắp xếp danh mục sản phẩm theo tên từ A đến Z | Medium | Approved |
| EPIC-02 | **US-05** | TS-08 | **TC-14** | Kiểm tra sắp xếp danh mục sản phẩm theo tên đảo ngược từ Z đến A | Medium | Approved |
| EPIC-02 | **US-05** | TS-09 | **TC-15** | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ thấp đến cao (Price low to high) | High | Approved |
| EPIC-02 | **US-05** | TS-09 | **TC-16** | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ cao đến thấp (Price high to low) | High | Approved |
| EPIC-02 | **US-05** | TS-08 | **TC-18** | Kiểm tra bộ lọc sắp xếp danh mục sản phẩm không phát sinh lỗi ngoại lệ JavaScript khi đăng nhập bằng error_user | High | Approved |
| EPIC-03 | **US-06** | TS-10 | **TC-19** | Kiểm tra thêm 1 sản phẩm vào giỏ hàng từ trang danh mục | High | Approved |
| EPIC-03 | **US-06** | TS-10 | **TC-20** | Kiểm tra thêm nhiều sản phẩm vào giỏ hàng và đồng bộ bộ đếm | High | Approved |
| EPIC-03 | **US-06** | TS-11 | **TC-21** | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm | Medium | Approved |
| EPIC-03 | **US-06** | TS-12 | **TC-22** | Kiểm tra xóa sản phẩm khỏi giỏ hàng trực tiếp từ trang danh mục | High | Approved |
| EPIC-03 | **US-06** | TS-12 | **TC-23** | Kiểm tra xóa sản phẩm khỏi giỏ hàng từ trang chi tiết sản phẩm | Medium | Approved |
| EPIC-03 | **US-06** | TS-12 | **TC-28** | Kiểm tra chức năng xóa sản phẩm khỏi giỏ hàng đối với sản phẩm Fleece Jacket khi đăng nhập bằng problem_user | High | Approved |
| EPIC-03 | **US-07** | TS-13 | **TC-24** | Kiểm tra mở trang giỏ hàng và hiển thị danh sách sản phẩm đã thêm | High | Approved |
| EPIC-03 | **US-07** | TS-14 | **TC-25** | Kiểm tra xóa trực tiếp sản phẩm trên trang giỏ hàng (Cart Page) | High | Approved |
| EPIC-03 | **US-07** | TS-15 | **TC-26** | Kiểm tra chức năng nút 'Continue Shopping' quay lại trang mua hàng | Medium | Approved |
| EPIC-03 | **US-08** | TS-16 | **TC-27** | Kiểm tra duy trì trạng thái giỏ hàng khi tải lại trang trình duyệt (F5 / Refresh) | High | Approved |
| EPIC-03 | **US-08** | TS-17 | **TC-29** | Kiểm tra chặn quy trình thanh toán khi giỏ hàng không có sản phẩm nào (Empty Cart Checkout) | High | Approved |
| EPIC-04 | **US-09** | TS-18 | **TC-30** | Kiểm tra chuyển hướng từ giỏ hàng sang Checkout Bước 1 | High | Approved |
| EPIC-04 | **US-09** | TS-19 | **TC-31** | Kiểm tra nhập thông tin khách hàng hợp lệ tại Checkout Bước 1 | High | Approved |
| EPIC-04 | **US-09** | TS-20 | **TC-32** | Kiểm tra thông báo lỗi khi để trống trường First Name tại Bước 1 | High | Approved |
| EPIC-04 | **US-09** | TS-20 | **TC-33** | Kiểm tra thông báo lỗi khi để trống trường Last Name tại Bước 1 | High | Approved |
| EPIC-04 | **US-09** | TS-20 | **TC-34** | Kiểm tra thông báo lỗi khi để trống trường Postal Code tại Bước 1 | High | Approved |
| EPIC-04 | **US-09** | TS-19 | **TC-35** | Kiểm tra nhập các định dạng mã bưu chính đặc biệt (Ký tự chữ và dấu gạch nối) | Medium | Approved |
| EPIC-04 | **US-09** | TS-21 | **TC-36** | Kiểm tra hủy bỏ quy trình thanh toán tại Bước 1 bằng nút 'Cancel' | Medium | Approved |
| EPIC-04 | **US-09** | TS-19 | **TC-43** | Kiểm tra nhập liệu và lưu trữ giá trị tại trường Last Name trong form Checkout Step 1 với problem_user | High | Approved |
| EPIC-04 | **US-10** | TS-22 | **TC-37** | Kiểm tra hiển thị danh sách sản phẩm và tổng quan đơn hàng tại Checkout Bước 2 | High | Approved |
| EPIC-04 | **US-10** | TS-22 | **TC-38** | Kiểm tra hiển thị thông tin thanh toán và thông tin giao hàng tại Bước 2 | Medium | Approved |
| EPIC-04 | **US-10** | TS-23 | **TC-39** | Kiểm tra tính toán tài chính: Tổng tiền hàng, Thuế 8% và Tổng thanh toán tại Bước 2 | High | Approved |
| EPIC-04 | **US-10** | TS-24 | **TC-40** | Kiểm tra hủy bỏ thanh toán tại Bước 2 bằng nút 'Cancel' | Medium | Approved |
| EPIC-04 | **US-10** | TS-24 | **TC-44** | Kiểm tra hoàn tất đơn hàng tại Checkout Step 2 không bị chặn bởi lỗi Runtime khi đăng nhập bằng error_user | High | Approved |
| EPIC-04 | **US-11** | TS-25 | **TC-41** | Kiểm tra hoàn tất đặt hàng thành công tại Checkout Bước 3 | High | Approved |
| EPIC-04 | **US-11** | TS-26 | **TC-42** | Kiểm tra nút 'Back Home' đưa người dùng quay về trang chủ sau khi hoàn tất mua hàng | Medium | Approved |
| EPIC-05 | **US-12** | TS-27 | **TC-45** | Kiểm tra mở và đóng menu Sidebar | Medium | Approved |
| EPIC-05 | **US-12** | TS-27 | **TC-46** | Kiểm tra mục 'All Items' trong Sidebar đưa người dùng về trang danh mục | Medium | Approved |
| EPIC-05 | **US-12** | TS-27 | **TC-47** | Kiểm tra mục 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs | Low | Approved |
| EPIC-05 | **US-12** | TS-27 | **TC-48** | Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng và xóa sạch giỏ hàng | High | Approved |
| EPIC-05 | **US-12** | TS-27 | **TC-49** | Kiểm tra tính hợp lệ của liên kết điều hướng 'About' trong Sidebar đối với problem_user | Low | Approved |
| EPIC-06 | **US-13** | TS-28 | **TC-50** | Kiểm tra toàn diện quy trình mua sắm thương mại điện tử End-to-End từ đăng nhập đến nhận biên lai | High | Approved |
| EPIC-07 | **US-14** | TS-31 | **TC-51** | Kiểm tra API POST /api/v1/auth/login xác thực đăng nhập thành công với tài khoản hợp lệ | High | Approved |
| EPIC-07 | **US-14** | TS-31 | **TC-52** | Kiểm tra API POST /api/v1/auth/login xử lý từ chối đăng nhập đối với tài khoản bị khóa (HTTP 423 Locked) | High | Approved |
| EPIC-07 | **US-14** | TS-31 | **TC-53** | Kiểm tra API GET /api/v1/products lấy danh mục sản phẩm và kiểm tra Schema JSON | High | Approved |
| EPIC-07 | **US-14** | TS-31 | **TC-54** | Kiểm tra API POST /api/v1/cart/items thêm sản phẩm vào giỏ hàng và cập nhật tổng số lượng | High | Approved |
| EPIC-07 | **US-14** | TS-31 | **TC-55** | Kiểm tra API POST /api/v1/checkout/orders hoàn tất đơn hàng và tính toán tài chính tự động | High | Approved |
| EPIC-07 | **US-15** | TS-32 | **TC-56** | Kiểm tra CSDL: Xác minh mật khẩu người dùng được băm an toàn trong bảng users | High | Approved |
| EPIC-07 | **US-15** | TS-32 | **TC-57** | Kiểm tra CSDL: Xác minh trạng thái khóa tài khoản trong bảng users đối với locked_out_user | High | Approved |
| EPIC-07 | **US-15** | TS-32 | **TC-58** | Kiểm tra CSDL: Xác minh tính nhất quán của bảng danh mục sản phẩm và giá niêm yết | High | Approved |
| EPIC-07 | **US-15** | TS-32 | **TC-59** | Kiểm tra CSDL: Xác minh ghi nhận bản ghi đơn hàng mới vào bảng orders sau khi thanh toán thành công | High | Approved |
| EPIC-07 | **US-15** | TS-32 | **TC-60** | Kiểm tra CSDL: Xác minh chi tiết các mặt hàng trong bảng order_items liên kết đúng với đơn hàng | High | Approved |
| EPIC-08 | **US-16** | TS-33 | **TC-63** | Kiểm tra phi chức năng: Kiểm tra các cờ bảo mật của Cookie phiên làm việc (Secure, HttpOnly, SameSite) | High | Approved |
| EPIC-08 | **US-16** | TS-33 | **TC-64** | Kiểm tra phi chức năng: Kiểm tra khả năng chống tấn công Cross-Site Scripting (XSS) trên form Checkout Step 1 | High | Approved |
| EPIC-08 | **US-16** | TS-33 | **TC-65** | Kiểm tra phi chức năng: Kiểm tra chống rò rỉ phiên làm việc khi sử dụng nút 'Back' của trình duyệt sau khi đăng xuất | High | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-61** | Kiểm tra phi chức năng: Đo lường thời gian phản hồi (Response Time SLA < 2.0s) khi tải trang danh mục sản phẩm | Medium | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-62** | Kiểm tra phi chức năng: Phát hiện vi phạm SLA thời gian phản hồi nghiêm trọng (>5.0s) đối với performance_glitch_user | Medium | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-66** | Kiểm tra phi chức năng: Kiểm tra điều hướng tuần tự bằng bàn phím (Keyboard Tab Order & Focus Ring) | Medium | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-67** | Kiểm tra phi chức năng: Kiểm tra tên trợ năng (Accessible Names / aria-label) và độ tương phản màu sắc | Medium | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-68** | Kiểm tra phi chức năng: Tính nhất quán của phản hồi trực quan trên bộ đếm giỏ hàng | Medium | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-69** | Kiểm tra phi chức năng: Phát hiện lỗi căn chỉnh layout và vị trí các thành phần trên thanh Header khi đăng nhập bằng visual_user | Low | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-70** | Kiểm tra phi chức năng: Kiểm tra tính tương thích hiển thị Responsive UI trên màn hình Mobile Viewport | Medium | Approved |
| EPIC-08 | **US-17** | TS-34 | **TC-71** | Kiểm tra phi chức năng: Kiểm tra khả năng tương thích hiển thị và hoạt động trên nhiều trình duyệt (Cross-Browser) | Medium | Approved |

---

<a id="rtm-section-4"></a>
## 4. Traceability Integrity Verification

> **Quality Verification:** Tất cả 17 User Stories từ `US-01` đến `US-17` đều đã được liên kết trực tiếp với các Test Scenarios (bao gồm cả Happy Path và Negative Path) và 71 Test Cases chi tiết (bao gồm 50 Functional Test Cases, 5 API Test Cases, 5 Database SQL Test Cases và 11 Non-Functional Test Cases). Không có yêu cầu nào bị bỏ sót (**Zero Coverage Gap**).
