# Test Cases Specification: SauceDemo Web Application

Document ID: TCD-SAUCEDEMO-01  
Target Application: SauceDemo (https://www.saucedemo.com/)  
Author: QA - Khổng Đức Anh  
Date: 24/09/2026  
Total Test Cases: 71 Ca kiểm thử  

---

## Mục Lục

- [1. Danh Sách 71 Test Cases](#1-danh-sach-71-test-cases)
- [2. Chi Tiết Các Test Cases](#2-chi-tiet-cac-test-cases)

---

<a id="1-danh-sach-71-test-cases"></a>
## 1. Danh Sách 71 Test Cases

| Test Case ID | Test Case Title | Folder | Priority | Severity | User Story | Test Scenario |
|:---|:---|:---|:---:|:---:|:---|:---|
| [TC-01](#tc-01) | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ | Functional_Testing/Authentication | High | Critical | [US-01](../01_Requirements/01_Requirement_Document_User_Stories.md#us-01) | [TS-01](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-01) |
| [TC-02](#tc-02) | Kiểm tra thông báo lỗi khi để trống cả Username và Password | Functional_Testing/Authentication | High | Medium | [US-02](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [TS-02](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-02) |
| [TC-03](#tc-03) | Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password | Functional_Testing/Authentication | High | Medium | [US-02](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [TS-02](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-02) |
| [TC-04](#tc-04) | Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password | Functional_Testing/Authentication | Medium | Medium | [US-02](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [TS-02](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-02) |
| [TC-05](#tc-05) | Kiểm tra từ chối đăng nhập khi nhập sai thông tin tài khoản hoặc mật khẩu | Functional_Testing/Authentication | High | High | [US-02](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [TS-03](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-03) |
| [TC-06](#tc-06) | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) | Functional_Testing/Authentication | High | High | [US-02](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [TS-04](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-04) |
| [TC-07](#tc-07) | Kiểm tra thao tác đóng thông báo lỗi đăng nhập bằng nút 'X' | Functional_Testing/Authentication | Low | Low | [US-02](../01_Requirements/01_Requirement_Document_User_Stories.md#us-02) | [TS-02](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-02) |
| [TC-08](#tc-08) | Kiểm tra đăng xuất tài khoản an toàn thông qua menu điều hướng Sidebar | Functional_Testing/Authentication | High | Critical | [US-03](../01_Requirements/01_Requirement_Document_User_Stories.md#us-03) | [TS-05](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-05) |
| [TC-09](#tc-09) | Kiểm tra chặn truy cập trực tiếp URL trang nội bộ khi chưa đăng nhập | Functional_Testing/Authentication | High | Critical | [US-03](../01_Requirements/01_Requirement_Document_User_Stories.md#us-03) | [TS-05](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-05) |
| [TC-10](#tc-10) | Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và các thông tin chi tiết | Functional_Testing/Product_Catalog | High | High | [US-04](../01_Requirements/01_Requirement_Document_User_Stories.md#us-04) | [TS-06](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-06) |
| [TC-11](#tc-11) | Kiểm tra xem trang chi tiết sản phẩm khi nhấp vào tên hoặc ảnh sản phẩm | Functional_Testing/Product_Catalog | Medium | Medium | [US-04](../01_Requirements/01_Requirement_Document_User_Stories.md#us-04) | [TS-07](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-07) |
| [TC-12](#tc-12) | Kiểm tra nút 'Back to products' quay lại trang danh mục từ trang chi tiết | Functional_Testing/Product_Catalog | Medium | Low | [US-04](../01_Requirements/01_Requirement_Document_User_Stories.md#us-04) | [TS-07](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-07) |
| [TC-13](#tc-13) | Kiểm tra sắp xếp danh mục sản phẩm theo tên từ A đến Z | Functional_Testing/Product_Catalog | Medium | Medium | [US-05](../01_Requirements/01_Requirement_Document_User_Stories.md#us-05) | [TS-08](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-08) |
| [TC-14](#tc-14) | Kiểm tra sắp xếp danh mục sản phẩm theo tên đảo ngược từ Z đến A | Functional_Testing/Product_Catalog | Medium | Medium | [US-05](../01_Requirements/01_Requirement_Document_User_Stories.md#us-05) | [TS-08](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-08) |
| [TC-15](#tc-15) | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ thấp đến cao (Price low to high) | Functional_Testing/Product_Catalog | High | High | [US-05](../01_Requirements/01_Requirement_Document_User_Stories.md#us-05) | [TS-09](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-09) |
| [TC-16](#tc-16) | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ cao đến thấp (Price high to low) | Functional_Testing/Product_Catalog | High | High | [US-05](../01_Requirements/01_Requirement_Document_User_Stories.md#us-05) | [TS-09](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-09) |
| [TC-17](#tc-17) | Kiểm tra tính toàn vẹn của liên kết hình ảnh danh mục sản phẩm đối với tài khoản problem_user | Functional_Testing/Product_Catalog | Medium | Medium | [US-04](../01_Requirements/01_Requirement_Document_User_Stories.md#us-04) | [TS-06](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-06) |
| [TC-18](#tc-18) | Kiểm tra bộ lọc sắp xếp danh mục sản phẩm không phát sinh lỗi ngoại lệ JavaScript khi đăng nhập bằng error_user | Functional_Testing/Product_Catalog | High | High | [US-05](../01_Requirements/01_Requirement_Document_User_Stories.md#us-05) | [TS-08](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-08) |
| [TC-19](#tc-19) | Kiểm tra thêm 1 sản phẩm vào giỏ hàng từ trang danh mục | Functional_Testing/Shopping_Cart | High | Critical | [US-06](../01_Requirements/01_Requirement_Document_User_Stories.md#us-06) | [TS-10](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-10) |
| [TC-20](#tc-20) | Kiểm tra thêm nhiều sản phẩm vào giỏ hàng và đồng bộ bộ đếm | Functional_Testing/Shopping_Cart | High | High | [US-06](../01_Requirements/01_Requirement_Document_User_Stories.md#us-06) | [TS-10](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-10) |
| [TC-21](#tc-21) | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm | Functional_Testing/Shopping_Cart | Medium | Medium | [US-06](../01_Requirements/01_Requirement_Document_User_Stories.md#us-06) | [TS-11](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-11) |
| [TC-22](#tc-22) | Kiểm tra xóa sản phẩm khỏi giỏ hàng trực tiếp từ trang danh mục | Functional_Testing/Shopping_Cart | High | High | [US-06](../01_Requirements/01_Requirement_Document_User_Stories.md#us-06) | [TS-12](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-12) |
| [TC-23](#tc-23) | Kiểm tra xóa sản phẩm khỏi giỏ hàng từ trang chi tiết sản phẩm | Functional_Testing/Shopping_Cart | Medium | Medium | [US-06](../01_Requirements/01_Requirement_Document_User_Stories.md#us-06) | [TS-12](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-12) |
| [TC-24](#tc-24) | Kiểm tra mở trang giỏ hàng và hiển thị danh sách sản phẩm đã thêm | Functional_Testing/Shopping_Cart | High | Critical | [US-07](../01_Requirements/01_Requirement_Document_User_Stories.md#us-07) | [TS-13](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-13) |
| [TC-25](#tc-25) | Kiểm tra xóa trực tiếp sản phẩm trên trang giỏ hàng (Cart Page) | Functional_Testing/Shopping_Cart | High | High | [US-07](../01_Requirements/01_Requirement_Document_User_Stories.md#us-07) | [TS-14](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-14) |
| [TC-26](#tc-26) | Kiểm tra chức năng nút 'Continue Shopping' quay lại trang mua hàng | Functional_Testing/Shopping_Cart | Medium | Low | [US-07](../01_Requirements/01_Requirement_Document_User_Stories.md#us-07) | [TS-15](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-15) |
| [TC-27](#tc-27) | Kiểm tra duy trì trạng thái giỏ hàng khi tải lại trang trình duyệt (F5 / Refresh) | Functional_Testing/Shopping_Cart | High | High | [US-08](../01_Requirements/01_Requirement_Document_User_Stories.md#us-08) | [TS-16](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-16) |
| [TC-28](#tc-28) | Kiểm tra chức năng xóa sản phẩm khỏi giỏ hàng đối với sản phẩm Fleece Jacket khi đăng nhập bằng problem_user | Functional_Testing/Shopping_Cart | High | High | [US-06](../01_Requirements/01_Requirement_Document_User_Stories.md#us-06) | [TS-12](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-12) |
| [TC-29](#tc-29) | Kiểm tra chặn quy trình thanh toán khi giỏ hàng không có sản phẩm nào (Empty Cart Checkout) | Functional_Testing/Shopping_Cart | High | High | [US-08](../01_Requirements/01_Requirement_Document_User_Stories.md#us-08) | [TS-17](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-17) |
| [TC-30](#tc-30) | Kiểm tra chuyển hướng từ giỏ hàng sang Checkout Bước 1 | Functional_Testing/Checkout | High | Critical | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-18](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-18) |
| [TC-31](#tc-31) | Kiểm tra nhập thông tin khách hàng hợp lệ tại Checkout Bước 1 | Functional_Testing/Checkout | High | Critical | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-19](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-19) |
| [TC-32](#tc-32) | Kiểm tra thông báo lỗi khi để trống trường First Name tại Bước 1 | Functional_Testing/Checkout | High | Medium | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-20](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-20) |
| [TC-33](#tc-33) | Kiểm tra thông báo lỗi khi để trống trường Last Name tại Bước 1 | Functional_Testing/Checkout | High | Medium | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-20](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-20) |
| [TC-34](#tc-34) | Kiểm tra thông báo lỗi khi để trống trường Postal Code tại Bước 1 | Functional_Testing/Checkout | High | Medium | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-20](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-20) |
| [TC-35](#tc-35) | Kiểm tra nhập các định dạng mã bưu chính đặc biệt (Ký tự chữ và dấu gạch nối) | Functional_Testing/Checkout | Medium | Low | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-19](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-19) |
| [TC-36](#tc-36) | Kiểm tra hủy bỏ quy trình thanh toán tại Bước 1 bằng nút 'Cancel' | Functional_Testing/Checkout | Medium | Low | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-21](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-21) |
| [TC-37](#tc-37) | Kiểm tra hiển thị danh sách sản phẩm và tổng quan đơn hàng tại Checkout Bước 2 | Functional_Testing/Checkout | High | High | [US-10](../01_Requirements/01_Requirement_Document_User_Stories.md#us-10) | [TS-22](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-22) |
| [TC-38](#tc-38) | Kiểm tra hiển thị thông tin thanh toán và thông tin giao hàng tại Bước 2 | Functional_Testing/Checkout | Medium | Low | [US-10](../01_Requirements/01_Requirement_Document_User_Stories.md#us-10) | [TS-22](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-22) |
| [TC-39](#tc-39) | Kiểm tra tính toán tài chính: Tổng tiền hàng, Thuế 8% và Tổng thanh toán tại Bước 2 | Functional_Testing/Checkout | High | Critical | [US-10](../01_Requirements/01_Requirement_Document_User_Stories.md#us-10) | [TS-23](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-23) |
| [TC-40](#tc-40) | Kiểm tra hủy bỏ thanh toán tại Bước 2 bằng nút 'Cancel' | Functional_Testing/Checkout | Medium | Low | [US-10](../01_Requirements/01_Requirement_Document_User_Stories.md#us-10) | [TS-24](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-24) |
| [TC-41](#tc-41) | Kiểm tra hoàn tất đặt hàng thành công tại Checkout Bước 3 | Functional_Testing/Checkout | High | Critical | [US-11](../01_Requirements/01_Requirement_Document_User_Stories.md#us-11) | [TS-25](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-25) |
| [TC-42](#tc-42) | Kiểm tra nút 'Back Home' đưa người dùng quay về trang chủ sau khi hoàn tất mua hàng | Functional_Testing/Checkout | Medium | Low | [US-11](../01_Requirements/01_Requirement_Document_User_Stories.md#us-11) | [TS-26](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-26) |
| [TC-43](#tc-43) | Kiểm tra nhập liệu và lưu trữ giá trị tại trường Last Name trong form Checkout Step 1 với problem_user | Functional_Testing/Checkout | High | Critical | [US-09](../01_Requirements/01_Requirement_Document_User_Stories.md#us-09) | [TS-19](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-19) |
| [TC-44](#tc-44) | Kiểm tra hoàn tất đơn hàng tại Checkout Step 2 không bị chặn bởi lỗi Runtime khi đăng nhập bằng error_user | Functional_Testing/Checkout | High | Blocker | [US-10](../01_Requirements/01_Requirement_Document_User_Stories.md#us-10) | [TS-24](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-24) |
| [TC-45](#tc-45) | Kiểm tra mở và đóng menu Sidebar | Functional_Testing/Sidebar_Navigation | Medium | Low | [US-12](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [TS-27](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-27) |
| [TC-46](#tc-46) | Kiểm tra mục 'All Items' trong Sidebar đưa người dùng về trang danh mục | Functional_Testing/Sidebar_Navigation | Medium | Low | [US-12](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [TS-27](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-27) |
| [TC-47](#tc-47) | Kiểm tra mục 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs | Functional_Testing/Sidebar_Navigation | Low | Low | [US-12](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [TS-27](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-27) |
| [TC-48](#tc-48) | Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng và xóa sạch giỏ hàng | Functional_Testing/Sidebar_Navigation | High | High | [US-12](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [TS-27](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-27) |
| [TC-49](#tc-49) | Kiểm tra tính hợp lệ của liên kết điều hướng 'About' trong Sidebar đối với problem_user | Functional_Testing/Sidebar_Navigation | Low | Low | [US-12](../01_Requirements/01_Requirement_Document_User_Stories.md#us-12) | [TS-27](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-27) |
| [TC-50](#tc-50) | Kiểm tra toàn diện quy trình mua sắm thương mại điện tử End-to-End từ đăng nhập đến nhận biên lai | Functional_Testing/End_to_End | High | Critical | [US-13](../01_Requirements/01_Requirement_Document_User_Stories.md#us-13) | [TS-28](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-28) |
| [TC-51](#tc-51) | Kiểm tra API POST /api/v1/auth/login xác thực đăng nhập thành công với tài khoản hợp lệ | API_Testing | High | Critical | [US-14](../01_Requirements/01_Requirement_Document_User_Stories.md#us-14) | [TS-31](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-31) |
| [TC-52](#tc-52) | Kiểm tra API POST /api/v1/auth/login xử lý từ chối đăng nhập đối với tài khoản bị khóa (HTTP 423 Locked) | API_Testing | High | High | [US-14](../01_Requirements/01_Requirement_Document_User_Stories.md#us-14) | [TS-31](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-31) |
| [TC-53](#tc-53) | Kiểm tra API GET /api/v1/products lấy danh mục sản phẩm và kiểm tra Schema JSON | API_Testing | High | High | [US-14](../01_Requirements/01_Requirement_Document_User_Stories.md#us-14) | [TS-31](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-31) |
| [TC-54](#tc-54) | Kiểm tra API POST /api/v1/cart/items thêm sản phẩm vào giỏ hàng và cập nhật tổng số lượng | API_Testing | High | High | [US-14](../01_Requirements/01_Requirement_Document_User_Stories.md#us-14) | [TS-31](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-31) |
| [TC-55](#tc-55) | Kiểm tra API POST /api/v1/checkout/orders hoàn tất đơn hàng và tính toán tài chính tự động | API_Testing | High | Critical | [US-14](../01_Requirements/01_Requirement_Document_User_Stories.md#us-14) | [TS-31](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-31) |
| [TC-56](#tc-56) | Kiểm tra CSDL: Xác minh mật khẩu người dùng được băm an toàn trong bảng users | Database_SQL_Testing | High | Critical | [US-15](../01_Requirements/01_Requirement_Document_User_Stories.md#us-15) | [TS-32](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-32) |
| [TC-57](#tc-57) | Kiểm tra CSDL: Xác minh trạng thái khóa tài khoản trong bảng users đối với locked_out_user | Database_SQL_Testing | High | High | [US-15](../01_Requirements/01_Requirement_Document_User_Stories.md#us-15) | [TS-32](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-32) |
| [TC-58](#tc-58) | Kiểm tra CSDL: Xác minh tính nhất quán của bảng danh mục sản phẩm và giá niêm yết | Database_SQL_Testing | High | High | [US-15](../01_Requirements/01_Requirement_Document_User_Stories.md#us-15) | [TS-32](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-32) |
| [TC-59](#tc-59) | Kiểm tra CSDL: Xác minh ghi nhận bản ghi đơn hàng mới vào bảng orders sau khi thanh toán thành công | Database_SQL_Testing | High | Critical | [US-15](../01_Requirements/01_Requirement_Document_User_Stories.md#us-15) | [TS-32](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-32) |
| [TC-60](#tc-60) | Kiểm tra CSDL: Xác minh chi tiết các mặt hàng trong bảng order_items liên kết đúng với đơn hàng | Database_SQL_Testing | High | High | [US-15](../01_Requirements/01_Requirement_Document_User_Stories.md#us-15) | [TS-32](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-32) |
| [TC-61](#tc-61) | Kiểm tra phi chức năng: Đo lường thời gian phản hồi (Response Time SLA < 2.0s) khi tải trang danh mục sản phẩm | Non_Functional_Testing/Performance_Testing | Medium | Medium | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |
| [TC-62](#tc-62) | Kiểm tra phi chức năng: Phát hiện vi phạm SLA thời gian phản hồi nghiêm trọng (>5.0s) đối với performance_glitch_user | Non_Functional_Testing/Performance_Testing | Medium | Medium | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |
| [TC-63](#tc-63) | Kiểm tra phi chức năng: Kiểm tra các cờ bảo mật của Cookie phiên làm việc (Secure, HttpOnly, SameSite) | Non_Functional_Testing/Security_Testing | High | High | [US-16](../01_Requirements/01_Requirement_Document_User_Stories.md#us-16) | [TS-33](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-33) |
| [TC-64](#tc-64) | Kiểm tra phi chức năng: Kiểm tra khả năng chống tấn công Cross-Site Scripting (XSS) trên form Checkout Step 1 | Non_Functional_Testing/Security_Testing | High | Critical | [US-16](../01_Requirements/01_Requirement_Document_User_Stories.md#us-16) | [TS-33](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-33) |
| [TC-65](#tc-65) | Kiểm tra phi chức năng: Kiểm tra chống rò rỉ phiên làm việc khi sử dụng nút 'Back' của trình duyệt sau khi đăng xuất | Non_Functional_Testing/Security_Testing | High | High | [US-16](../01_Requirements/01_Requirement_Document_User_Stories.md#us-16) | [TS-33](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-33) |
| [TC-66](#tc-66) | Kiểm tra phi chức năng: Kiểm tra điều hướng tuần tự bằng bàn phím (Keyboard Tab Order & Focus Ring) | Non_Functional_Testing/Accessibility_Testing | Medium | Medium | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |
| [TC-67](#tc-67) | Kiểm tra phi chức năng: Kiểm tra tên trợ năng (Accessible Names / aria-label) và độ tương phản màu sắc | Non_Functional_Testing/Accessibility_Testing | Medium | Low | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |
| [TC-68](#tc-68) | Kiểm tra phi chức năng: Tính nhất quán của phản hồi trực quan trên bộ đếm giỏ hàng | Non_Functional_Testing/Usability_Testing | Medium | Low | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |
| [TC-69](#tc-69) | Kiểm tra phi chức năng: Phát hiện lỗi căn chỉnh layout và vị trí các thành phần trên thanh Header khi đăng nhập bằng visual_user | Non_Functional_Testing/Usability_Testing | Low | Low | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |
| [TC-70](#tc-70) | Kiểm tra phi chức năng: Kiểm tra tính tương thích hiển thị Responsive UI trên màn hình Mobile Viewport | Non_Functional_Testing/Compatibility_Testing | Medium | Medium | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |
| [TC-71](#tc-71) | Kiểm tra phi chức năng: Kiểm tra khả năng tương thích hiển thị và hoạt động trên nhiều trình duyệt (Cross-Browser) | Non_Functional_Testing/Compatibility_Testing | Medium | Medium | [US-17](../01_Requirements/01_Requirement_Document_User_Stories.md#us-17) | [TS-34](../03_Test_Scenarios/03_Test_Scenarios_Document.md#ts-34) |

---

<a id="2-chi-tiet-cac-test-cases"></a>
## 2. Chi Tiết Các Test Cases

<a id="tc-01"></a>

## Test Case: TC-01 - Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-01 |
| **Name** | Kiểm tra đăng nhập thành công với tài khoản tiêu chuẩn hợp lệ |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-01 |
| **TestScenarioID** | TS-01 |
| **Test Type** | Functional / Smoke |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt đang mở tại địa chỉ 'https://www.saucedemo.com/'; chưa có cookie phiên làm việc nào. |
| **Test Data** | Username: standard_user | Password: secret_sauce |
| **Postcondition** | Người dùng đăng nhập thành công, phiên làm việc hoạt động trên trang '/inventory.html'. |

### 1. Objective
Xác minh người dùng hợp lệ có thể đăng nhập thành công bằng thông tin tài khoản tiêu chuẩn và được chuyển hướng vào trang danh mục sản phẩm.

### 2. Test Steps

1. Truy cập vào trang web 'https://www.saucedemo.com/'.
2. Nhập 'standard_user' vào ô 'Username'.
3. Nhập 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

### 3. Expected Result

Đăng nhập thành công và chuyển hướng đến 'https://www.saucedemo.com/inventory.html'. Tiêu đề trang hiển thị 'Products', biểu tượng giỏ hàng xuất hiện và cookie 'session-username=standard_user' được thiết lập.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử Smoke quan trọng cho chức năng đăng nhập.


Xem chi tiết: [TC-01.md](Functional_Testing/Authentication/TC-01.md)


---

<a id="tc-02"></a>

## Test Case: TC-02 - Kiểm tra thông báo lỗi khi để trống cả Username và Password

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-02 |
| **Name** | Kiểm tra thông báo lỗi khi để trống cả Username và Password |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. Cả hai ô nhập liệu đều trống. |
| **Test Data** | Username: '' (để trống) | Password: '' (để trống) |
| **Postcondition** | Không có phiên làm việc nào được tạo; thông báo lỗi hiển thị rõ ràng. |

### 1. Objective
Đảm bảo hệ thống chặn đăng nhập và hiển thị đúng thông báo lỗi yêu cầu khi người dùng để trống cả hai ô nhập liệu (Kỹ thuật phân vùng tương đương: Dữ liệu rỗng).

### 2. Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Để trống ô 'Username'.
3. Để trống ô 'Password'.
4. Nhấp vào nút 'Login'.

### 3. Expected Result

Hệ thống từ chối đăng nhập. Người dùng vẫn ở lại trang đăng nhập. Hộp thông báo màu đỏ hiển thị chính xác nội dung: 'Epic sadface: Username is required'. Các ô nhập liệu hiển thị biểu tượng cảnh báo màu đỏ.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Chuỗi rỗng / Không nhập dữ liệu.


Xem chi tiết: [TC-02.md](Functional_Testing/Authentication/TC-02.md)


---

<a id="tc-03"></a>

## Test Case: TC-03 - Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-03 |
| **Name** | Kiểm tra thông báo lỗi khi nhập Username nhưng để trống Password |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. |
| **Test Data** | Username: standard_user | Password: '' (để trống) |
| **Postcondition** | Không tạo cookie phiên; người dùng ở lại trang đăng nhập. |

### 1. Objective
Xác minh khi người dùng đã nhập tên đăng nhập hợp lệ nhưng bỏ trống mật khẩu, hệ thống phải yêu cầu nhập mật khẩu.

### 2. Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập 'standard_user' vào ô 'Username'.
3. Để trống hoàn toàn ô 'Password'.
4. Nhấp vào nút 'Login'.

### 3. Expected Result

Hệ thống từ chối đăng nhập. Xuất hiện thông báo lỗi màu đỏ với nội dung: 'Epic sadface: Password is required'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Thiếu trường bắt buộc Password.


Xem chi tiết: [TC-03.md](Functional_Testing/Authentication/TC-03.md)


---

<a id="tc-04"></a>

## Test Case: TC-04 - Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-04 |
| **Name** | Kiểm tra thông báo lỗi khi để trống Username nhưng có nhập Password |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Negative / Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. |
| **Test Data** | Username: '' (để trống) | Password: secret_sauce |
| **Postcondition** | Không tạo phiên làm việc; người dùng ở lại trang đăng nhập. |

### 1. Objective
Xác minh khi người dùng bỏ trống ô tên đăng nhập nhưng có nhập mật khẩu, hệ thống ưu tiên thông báo yêu cầu Username.

### 2. Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Để trống ô 'Username'.
3. Nhập 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

### 3. Expected Result

Hệ thống từ chối đăng nhập. Xuất hiện thông báo lỗi màu đỏ: 'Epic sadface: Username is required'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phân vùng EP: Thiếu trường bắt buộc Username.


Xem chi tiết: [TC-04.md](Functional_Testing/Authentication/TC-04.md)


---

<a id="tc-05"></a>

## Test Case: TC-05 - Kiểm tra từ chối đăng nhập khi nhập sai thông tin tài khoản hoặc mật khẩu

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-05 |
| **Name** | Kiểm tra từ chối đăng nhập khi nhập sai thông tin tài khoản hoặc mật khẩu |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-03 |
| **Test Type** | Negative / Security |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang 'https://www.saucedemo.com/'. |
| **Test Data** | Username: invalid_user | Password: wrong_password |
| **Postcondition** | Không cấp quyền truy cập; người dùng ở lại trang đăng nhập. |

### 1. Objective
Đảm bảo hệ thống bảo vệ tài khoản người dùng bằng cách từ chối truy cập và đưa ra thông báo an toàn khi nhập sai thông tin.

### 2. Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập 'invalid_user' vào ô 'Username'.
3. Nhập 'wrong_password' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

### 3. Expected Result

Hệ thống từ chối đăng nhập và hiển thị thông báo lỗi màu đỏ: 'Epic sadface: Username and password do not match any user in this service'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra bảo mật: Không tiết lộ cụ thể sai ở username hay password.


Xem chi tiết: [TC-05.md](Functional_Testing/Authentication/TC-05.md)


---

<a id="tc-06"></a>

## Test Case: TC-06 - Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-06 |
| **Name** | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-04 |
| **Test Type** | Negative / Security |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Tài khoản 'locked_out_user' đã được đánh dấu trạng thái bị khóa trên hệ thống. |
| **Test Data** | Username: locked_out_user | Password: secret_sauce |
| **Postcondition** | Tài khoản bị khóa không được phép truy cập trang mua hàng. |

### 1. Objective
Xác minh tài khoản người dùng bị khóa trong hệ thống không thể đăng nhập và nhận được thông báo giải thích cụ thể.

### 2. Test Steps

1. Truy cập trang 'https://www.saucedemo.com/'.
2. Nhập 'locked_out_user' vào ô 'Username'.
3. Nhập 'secret_sauce' vào ô 'Password'.
4. Nhấp vào nút 'Login'.

### 3. Expected Result

Hệ thống ngăn chặn đăng nhập và hiển thị thông báo lỗi chính xác: 'Epic sadface: Sorry, this user has been locked out.'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra xử lý phân quyền và tài khoản bị vô hiệu hóa.


Xem chi tiết: [TC-06.md](Functional_Testing/Authentication/TC-06.md)


---

<a id="tc-07"></a>

## Test Case: TC-07 - Kiểm tra thao tác đóng thông báo lỗi đăng nhập bằng nút 'X'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-07 |
| **Name** | Kiểm tra thao tác đóng thông báo lỗi đăng nhập bằng nút 'X' |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Login Page |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-02 |
| **TestScenarioID** | TS-02 |
| **Test Type** | Functional / UI Interaction |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang có thông báo lỗi đăng nhập hiển thị trên màn hình. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Giao diện trang đăng nhập trở về trạng thái sạch sẽ không có thông báo lỗi. |

### 1. Objective
Xác minh khi xuất hiện thông báo lỗi, người dùng có thể nhấp vào biểu tượng 'X' để tắt thông báo lỗi.

### 2. Test Steps

1. Để trống thông tin và nhấp 'Login' để làm xuất hiện thông báo lỗi.
2. Quan sát thấy hộp thông báo lỗi màu đỏ có biểu tượng 'X' ở góc phải.
3. Nhấp vào nút biểu tượng 'X'.

### 3. Expected Result

Hộp thông báo lỗi màu đỏ biến mất hoàn toàn khỏi giao diện màn hình đăng nhập.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính tương tác giao diện (Usability).


Xem chi tiết: [TC-07.md](Functional_Testing/Authentication/TC-07.md)


---

<a id="tc-08"></a>

## Test Case: TC-08 - Kiểm tra đăng xuất tài khoản an toàn thông qua menu điều hướng Sidebar

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-08 |
| **Name** | Kiểm tra đăng xuất tài khoản an toàn thông qua menu điều hướng Sidebar |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Sidebar Navigation / Session |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-03 |
| **TestScenarioID** | TS-05 |
| **Test Type** | Functional / Security |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang đăng nhập bằng tài khoản 'standard_user' tại trang '/inventory.html'. |
| **Test Data** | Tài khoản đang hoạt động: standard_user |
| **Postcondition** | Phiên làm việc kết thúc hoàn toàn; người dùng không còn quyền truy cập dữ liệu mua sắm. |

### 1. Objective
Xác minh người dùng đã đăng nhập có thể đăng xuất khỏi hệ thống an toàn qua tùy chọn Logout trên thanh menu điều hướng.

### 2. Test Steps

1. Nhấp vào biểu tượng 3 dấu gạch ngang (hamburger menu) ở góc trên bên trái.
2. Chờ menu trượt mở ra hoàn toàn.
3. Nhấp vào liên kết 'Logout'.
4. Kiểm tra URL trình duyệt và kiểm tra Cookie 'session-username' trong Application tab.

### 3. Expected Result

Hệ thống hủy phiên làm việc, xóa cookie hoặc vô hiệu hóa phiên, và chuyển hướng người dùng quay trở về trang đăng nhập 'https://www.saucedemo.com/'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử an toàn phiên làm việc cốt lõi.


Xem chi tiết: [TC-08.md](Functional_Testing/Authentication/TC-08.md)


---

<a id="tc-09"></a>

## Test Case: TC-09 - Kiểm tra chặn truy cập trực tiếp URL trang nội bộ khi chưa đăng nhập

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-09 |
| **Name** | Kiểm tra chặn truy cập trực tiếp URL trang nội bộ khi chưa đăng nhập |
| **Folder** | Functional_Testing/Authentication |
| **Component** | Access Control / Session |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-03 |
| **TestScenarioID** | TS-05 |
| **Test Type** | Security / Authorization |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt ở chế độ ẩn danh (Incognito) hoặc chưa đăng nhập (không có cookie phiên). |
| **Test Data** | URL trực tiếp: https://www.saucedemo.com/inventory.html |
| **Postcondition** | Không cấp quyền truy cập vào dữ liệu sản phẩm. |

### 1. Objective
Đảm bảo người dùng chưa xác thực không thể bỏ qua trang đăng nhập bằng cách gõ trực tiếp URL '/inventory.html' trên thanh địa chỉ trình duyệt.

### 2. Test Steps

1. Mở cửa sổ trình duyệt mới hoàn toàn sạch cookie.
2. Nhập trực tiếp đường dẫn 'https://www.saucedemo.com/inventory.html' vào thanh địa chỉ và nhấn Enter.

### 3. Expected Result

Hệ thống chặn truy cập, tự động chuyển hướng về trang chủ đăng nhập và hiển thị thông báo lỗi màu đỏ: 'Epic sadface: You can only access \'/inventory.html\' when you are logged in.'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bảo vệ tài nguyên nội bộ chống truy cập trái phép (URL Tampering / Direct Object Reference).


Xem chi tiết: [TC-09.md](Functional_Testing/Authentication/TC-09.md)


---

<a id="tc-10"></a>

## Test Case: TC-10 - Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và các thông tin chi tiết

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-10 |
| **Name** | Kiểm tra hiển thị đầy đủ danh mục 6 sản phẩm và các thông tin chi tiết |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Catalog |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-06 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập thành công bằng tài khoản 'standard_user'. |
| **Test Data** | Số lượng sản phẩm: 6 sản phẩm niêm yết |
| **Postcondition** | Người dùng xem được đầy đủ danh mục hàng hóa. |

### 1. Objective
Xác minh trang danh mục sản phẩm hiển thị chính xác toàn bộ 6 sản phẩm với đầy đủ ảnh, tên, mô tả và giá bán chuẩn định dạng tiền tệ.

### 2. Test Steps

1. Đăng nhập và đi đến trang '/inventory.html'.
2. Đếm số lượng sản phẩm hiển thị trên trang danh mục.
3. Kiểm tra từng sản phẩm phải có đủ: Ảnh đại diện, Tên sản phẩm dạng liên kết, Đoạn văn mô tả chi tiết, Giá tiền bắt đầu bằng ký hiệu '\$', và Nút 'Add to cart'.

### 3. Expected Result

Hiển thị đúng 6 sản phẩm không thiếu sót; định dạng giá tiền chuẩn xác (\$29.99, \$9.99, \$15.99, \$49.99, \$7.99, \$15.99); hình ảnh rõ nét không bị vỡ.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính toàn vẹn dữ liệu hiển thị trên giao diện người dùng.


Xem chi tiết: [TC-10.md](Functional_Testing/Product_Catalog/TC-10.md)


---

<a id="tc-11"></a>

## Test Case: TC-11 - Kiểm tra xem trang chi tiết sản phẩm khi nhấp vào tên hoặc ảnh sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-11 |
| **Name** | Kiểm tra xem trang chi tiết sản phẩm khi nhấp vào tên hoặc ảnh sản phẩm |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Details |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-07 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục '/inventory.html'. |
| **Test Data** | Sản phẩm chọn: Sauce Labs Backpack (\$29.99) |
| **Postcondition** | Người dùng xem được chi tiết của sản phẩm đã chọn. |

### 1. Objective
Xác minh khi người dùng nhấp vào tiêu đề hoặc ảnh của một sản phẩm, hệ thống điều hướng chính xác đến trang chi tiết của sản phẩm đó.

### 2. Test Steps

1. Tại trang danh mục, nhấp vào tên sản phẩm 'Sauce Labs Backpack'.
2. Quan sát URL trên thanh địa chỉ.
3. Kiểm tra thông tin hiển thị tại trang chi tiết: Tên sản phẩm, Ảnh lớn, Mô tả, Giá tiền \$29.99 và Nút 'Add to cart'.

### 3. Expected Result

Trình duyệt chuyển hướng đến '/inventory-item.html?id=4', thông tin sản phẩm hiển thị đồng nhất và chuẩn xác với trang danh mục ngoài.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra liên kết điều hướng và truyền tham số ID sản phẩm.


Xem chi tiết: [TC-11.md](Functional_Testing/Product_Catalog/TC-11.md)


---

<a id="tc-12"></a>

## Test Case: TC-12 - Kiểm tra nút 'Back to products' quay lại trang danh mục từ trang chi tiết

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-12 |
| **Name** | Kiểm tra nút 'Back to products' quay lại trang danh mục từ trang chi tiết |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Details |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-07 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang xem trang chi tiết của một sản phẩm bất kỳ. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng tiếp tục duyệt danh mục sản phẩm bình thường. |

### 1. Objective
Xác minh nút điều hướng quay lại hoạt động mượt mà và đưa người dùng trở về đúng trang danh mục ban đầu.

### 2. Test Steps

1. Đang ở trang chi tiết sản phẩm '/inventory-item.html?id=4'.
2. Nhấp vào nút 'Back to products' ở góc trên bên trái nội dung.

### 3. Expected Result

Trình duyệt quay trở lại trang danh mục '/inventory.html' và hiển thị lại đầy đủ 6 sản phẩm.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra trải nghiệm điều hướng người dùng (UX Navigation).


Xem chi tiết: [TC-12.md](Functional_Testing/Product_Catalog/TC-12.md)


---

<a id="tc-13"></a>

## Test Case: TC-13 - Kiểm tra sắp xếp danh mục sản phẩm theo tên từ A đến Z

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-13 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo tên từ A đến Z |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Name (A to Z)' |
| **Postcondition** | Danh mục duy trì thứ tự sắp xếp A-Z. |

### 1. Objective
Đảm bảo bộ chọn sắp xếp sắp xếp lại các sản phẩm theo thứ tự chữ cái tên sản phẩm từ A đến Z một cách chính xác.

### 2. Test Steps

1. Nhấp vào menu dropdown sắp xếp (Product sort container).
2. Chọn tùy chọn 'Name (A to Z)'.
3. Đọc danh sách tên các sản phẩm từ trên xuống dưới.

### 3. Expected Result

Danh sách sản phẩm được sắp xếp đúng thứ tự: 1. Sauce Labs Backpack, 2. Sauce Labs Bike Light, 3. Sauce Labs Bolt T-Shirt, 4. Sauce Labs Fleece Jacket, 5. Sauce Labs Onesie, 6. Test.allTheThings() T-Shirt (Red).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Sắp xếp theo thứ tự bảng chữ cái mặc định.


Xem chi tiết: [TC-13.md](Functional_Testing/Product_Catalog/TC-13.md)


---

<a id="tc-14"></a>

## Test Case: TC-14 - Kiểm tra sắp xếp danh mục sản phẩm theo tên đảo ngược từ Z đến A

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-14 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo tên đảo ngược từ Z đến A |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Functional / Sorting |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Name (Z to A)' |
| **Postcondition** | Danh mục hiển thị theo thứ tự tên Z đến A. |

### 1. Objective
Đảm bảo bộ chọn sắp xếp sắp xếp lại các sản phẩm theo thứ tự chữ cái đảo ngược từ Z đến A một cách chính xác.

### 2. Test Steps

1. Nhấp vào dropdown sắp xếp.
2. Chọn tùy chọn 'Name (Z to A)'.
3. Kiểm tra tên sản phẩm đầu tiên và sản phẩm cuối cùng trong danh sách.

### 3. Expected Result

Sản phẩm đầu tiên là 'Test.allTheThings() T-Shirt (Red)' và sản phẩm cuối cùng là 'Sauce Labs Backpack'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra thuật toán sắp xếp chuỗi ký tự ngược.


Xem chi tiết: [TC-14.md](Functional_Testing/Product_Catalog/TC-14.md)


---

<a id="tc-15"></a>

## Test Case: TC-15 - Kiểm tra sắp xếp danh mục sản phẩm theo giá từ thấp đến cao (Price low to high)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-15 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ thấp đến cao (Price low to high) |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-09 |
| **Test Type** | Functional / Business Logic |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Price (low to high)' |
| **Postcondition** | Sản phẩm sắp xếp theo giá tăng dần. |

### 1. Objective
Xác minh thuật toán sắp xếp giá so sánh theo giá trị số thực (numeric value), đảm bảo sản phẩm rẻ nhất xếp đầu và đắt nhất xếp cuối.

### 2. Test Steps

1. Nhấp vào dropdown sắp xếp.
2. Chọn tùy chọn 'Price (low to high)'.
3. Trích xuất giá của toàn bộ 6 sản phẩm theo thứ tự hiển thị.

### 3. Expected Result

Dãy giá hiển thị tăng dần chuẩn xác: \$7.99 (Onesie) <= \$9.99 (Bike Light) <= \$15.99 (Bolt T-Shirt) <= \$15.99 (Red T-Shirt) <= \$29.99 (Backpack) <= \$49.99 (Fleece Jacket).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Phát hiện lỗi thường gặp: So sánh chuỗi (lexicographical) thay vì so sánh số học.


Xem chi tiết: [TC-15.md](Functional_Testing/Product_Catalog/TC-15.md)


---

<a id="tc-16"></a>

## Test Case: TC-16 - Kiểm tra sắp xếp danh mục sản phẩm theo giá từ cao đến thấp (Price high to low)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-16 |
| **Name** | Kiểm tra sắp xếp danh mục sản phẩm theo giá từ cao đến thấp (Price high to low) |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-09 |
| **Test Type** | Functional / Business Logic |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang danh mục sản phẩm. |
| **Test Data** | Tùy chọn: 'Price (high to low)' |
| **Postcondition** | Sản phẩm sắp xếp theo giá giảm dần. |

### 1. Objective
Xác minh sản phẩm có giá cao nhất xếp ở vị trí đầu tiên và giảm dần cho đến sản phẩm có giá thấp nhất.

### 2. Test Steps

1. Nhấp vào dropdown sắp xếp.
2. Chọn tùy chọn 'Price (high to low)'.
3. Kiểm tra sản phẩm đầu tiên và sản phẩm cuối cùng.

### 3. Expected Result

Sản phẩm đầu tiên có giá \$49.99 (Sauce Labs Fleece Jacket) và sản phẩm cuối cùng có giá \$7.99 (Sauce Labs Onesie).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra thuật toán sắp xếp số học giảm dần.


Xem chi tiết: [TC-16.md](Functional_Testing/Product_Catalog/TC-16.md)


---

<a id="tc-17"></a>

## Test Case: TC-17 - Kiểm tra tính toàn vẹn của liên kết hình ảnh danh mục sản phẩm đối với tài khoản problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-17 |
| **Name** | Kiểm tra tính toàn vẹn của liên kết hình ảnh danh mục sản phẩm đối với tài khoản problem_user |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Catalog / Asset Integrity |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-04 |
| **TestScenarioID** | TS-06 |
| **Test Type** | UI / Asset Integrity / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt chưa có phiên làm việc. |
| **Test Data** | Username: problem_user | Password: secret_sauce |
| **Postcondition** | Giao diện hiển thị trực quan, hình ảnh sản phẩm chính xác. |

### 1. Objective
Xác minh tất cả hình ảnh sản phẩm trên trang danh mục tải lên chính xác ảnh thực của từng sản phẩm, không bị hỏng hoặc trỏ sai đường dẫn tài nguyên.

### 2. Test Steps

1. Truy cập 'https://www.saucedemo.com/'.
2. Đăng nhập bằng 'problem_user' / 'secret_sauce'.
3. Quan sát hình ảnh đại diện của cả 6 sản phẩm trên trang danh mục '/inventory.html'.
4. Kiểm tra thuộc tính 'src' của các thẻ <img> và đối chiếu với tên sản phẩm.

### 3. Expected Result

Tất cả 6 sản phẩm hiển thị đúng hình ảnh tương ứng (Balo hiển thị ảnh Balo, Đèn xe đạp hiển thị ảnh Đèn...). Không có hình ảnh nào bị vỡ hoặc trỏ đến đường dẫn tài nguyên lỗi.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Toàn bộ ảnh sản phẩm của problem_user bị trỏ về ảnh con chó lỗi /static/media/sl-404.168b1cce.jpg.


Xem chi tiết: [TC-17.md](Functional_Testing/Product_Catalog/TC-17.md)


---

<a id="tc-18"></a>

## Test Case: TC-18 - Kiểm tra bộ lọc sắp xếp danh mục sản phẩm không phát sinh lỗi ngoại lệ JavaScript khi đăng nhập bằng error_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-18 |
| **Name** | Kiểm tra bộ lọc sắp xếp danh mục sản phẩm không phát sinh lỗi ngoại lệ JavaScript khi đăng nhập bằng error_user |
| **Folder** | Functional_Testing/Product_Catalog |
| **Component** | Product Catalog / Sorting |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-05 |
| **TestScenarioID** | TS-08 |
| **Test Type** | Error Handling / UI Exception / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'error_user'; đang ở trang '/inventory.html'. |
| **Test Data** | Username: error_user | Tùy chọn sắp xếp: 'Price (low to high)' |
| **Postcondition** | Sản phẩm hiển thị theo đúng tiêu chí sắp xếp. |

### 1. Objective
Xác minh khi người dùng thay đổi tùy chọn sắp xếp danh mục, hệ thống sắp xếp mượt mà và không phát sinh cửa sổ cảnh báo unhandled exception.

### 2. Test Steps

1. Đăng nhập bằng 'error_user' / 'secret_sauce'.
2. Nhấp vào dropdown sắp xếp sản phẩm (mặc định 'Name (A to Z)').
3. Chọn tùy chọn 'Price (low to high)'.

### 3. Expected Result

Danh sách sản phẩm được sắp xếp lại theo giá tiền tăng dần (\$7.99 -> \$49.99). Không có hộp thoại popup alert nào của trình duyệt xuất hiện làm gián đoạn người dùng.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Khi error_user đổi bộ lọc, mã JavaScript kích hoạt lệnh window.alert('Sorting is broken! This error has been reported to Backtrace.'), danh sách không được sắp xếp lại.


Xem chi tiết: [TC-18.md](Functional_Testing/Product_Catalog/TC-18.md)


---

<a id="tc-19"></a>

## Test Case: TC-19 - Kiểm tra thêm 1 sản phẩm vào giỏ hàng từ trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-19 |
| **Name** | Kiểm tra thêm 1 sản phẩm vào giỏ hàng từ trang danh mục |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-10 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập; giỏ hàng ban đầu đang trống (không có huy hiệu số lượng). |
| **Test Data** | Sản phẩm: Sauce Labs Backpack |
| **Postcondition** | Giỏ hàng có 1 món hàng; trạng thái lưu vào bộ nhớ trình duyệt. |

### 1. Objective
Xác minh khi người dùng nhấn 'Add to cart' tại một sản phẩm trên trang danh mục, nút đổi sang 'Remove' và huy hiệu giỏ hàng hiển thị số '1'.

### 2. Test Steps

1. Đang ở trang danh mục sản phẩm '/inventory.html'.
2. Tìm sản phẩm 'Sauce Labs Backpack'.
3. Nhấp vào nút 'Add to cart' tương ứng với sản phẩm này.

### 3. Expected Result

Nút bấm lập tức chuyển thành chữ 'Remove' với viền đỏ. Biểu tượng giỏ hàng ở góc trên bên phải xuất hiện huy hiệu màu đỏ hiển thị số '1'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra đồng bộ giao diện và cập nhật trạng thái giỏ hàng (State Management).


Xem chi tiết: [TC-19.md](Functional_Testing/Shopping_Cart/TC-19.md)


---

<a id="tc-20"></a>

## Test Case: TC-20 - Kiểm tra thêm nhiều sản phẩm vào giỏ hàng và đồng bộ bộ đếm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-20 |
| **Name** | Kiểm tra thêm nhiều sản phẩm vào giỏ hàng và đồng bộ bộ đếm |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-10 |
| **Test Type** | Functional / Boundary |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Giỏ hàng đang trống. |
| **Test Data** | 3 sản phẩm: Backpack, Bike Light, Bolt T-Shirt |
| **Postcondition** | Giỏ hàng lưu trữ đúng 3 sản phẩm đã chọn. |

### 1. Objective
Xác minh bộ đếm huy hiệu giỏ hàng tự động tăng theo đúng số lượng sản phẩm được thêm vào (kiểm tra với 3 sản phẩm khác nhau).

### 2. Test Steps

1. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Backpack -> Huy hiệu hiển thị 1.
2. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Bike Light -> Huy hiệu hiển thị 2.
3. Nhấp 'Add to cart' tại sản phẩm Sauce Labs Bolt T-Shirt -> Huy hiệu hiển thị 3.

### 3. Expected Result

Huy hiệu giỏ hàng tăng tuần tự từ 1 -> 2 -> 3; cả 3 nút của 3 sản phẩm đều chuyển thành 'Remove'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính lũy kế của biến đếm giỏ hàng.


Xem chi tiết: [TC-20.md](Functional_Testing/Shopping_Cart/TC-20.md)


---

<a id="tc-21"></a>

## Test Case: TC-21 - Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-21 |
| **Name** | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Product Details / Cart |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-11 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang xem trang chi tiết '/inventory-item.html?id=0' (Sauce Labs Bike Light). |
| **Test Data** | Sản phẩm: Sauce Labs Bike Light (\$9.99) |
| **Postcondition** | Trạng thái giỏ hàng đồng bộ giữa trang chi tiết và trang danh mục ngoài. |

### 1. Objective
Xác minh nút 'Add to cart' trên trang chi tiết sản phẩm hoạt động chính xác và đồng bộ huy hiệu giỏ hàng.

### 2. Test Steps

1. Mở trang chi tiết sản phẩm Bike Light.
2. Nhấp vào nút 'Add to cart'.
3. Nhấp vào nút 'Back to products' để quay lại trang danh mục.

### 3. Expected Result

Tại trang chi tiết: Nút chuyển thành 'Remove', huy hiệu giỏ hàng tăng thêm 1. Khi quay lại trang danh mục: Nút tương ứng của sản phẩm đó cũng hiển thị đúng trạng thái 'Remove'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra đồng bộ dữ liệu liên trang (Cross-page State Sync).


Xem chi tiết: [TC-21.md](Functional_Testing/Shopping_Cart/TC-21.md)


---

<a id="tc-22"></a>

## Test Case: TC-22 - Kiểm tra xóa sản phẩm khỏi giỏ hàng trực tiếp từ trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-22 |
| **Name** | Kiểm tra xóa sản phẩm khỏi giỏ hàng trực tiếp từ trang danh mục |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Shopping Cart |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang có 1 sản phẩm trong giỏ hàng (nút đang ở trạng thái 'Remove', huy hiệu hiển thị '1'). |
| **Test Data** | Sản phẩm: Sauce Labs Backpack |
| **Postcondition** | Giỏ hàng rỗng; dữ liệu được cập nhật sạch sẽ. |

### 1. Objective
Xác minh khi người dùng nhấp 'Remove' trên trang danh mục, sản phẩm được loại bỏ và huy hiệu giỏ hàng giảm tương ứng.

### 2. Test Steps

1. Tại trang danh mục, nhấp vào nút 'Remove' của sản phẩm 'Sauce Labs Backpack'.
2. Quan sát nút bấm và biểu tượng giỏ hàng.

### 3. Expected Result

Nút 'Remove' chuyển lại thành nút 'Add to cart'. Huy hiệu số lượng trên biểu tượng giỏ hàng biến mất hoàn toàn (giỏ hàng về 0).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra giá trị biên: Bộ đếm giảm từ 1 về 0 (BVA - Boundary Value Analysis).


Xem chi tiết: [TC-22.md](Functional_Testing/Shopping_Cart/TC-22.md)


---

<a id="tc-23"></a>

## Test Case: TC-23 - Kiểm tra xóa sản phẩm khỏi giỏ hàng từ trang chi tiết sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-23 |
| **Name** | Kiểm tra xóa sản phẩm khỏi giỏ hàng từ trang chi tiết sản phẩm |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Product Details / Cart |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Functional / State Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Sản phẩm đang được thêm trong giỏ hàng và người dùng đang ở trang chi tiết của sản phẩm đó. |
| **Test Data** | Sản phẩm: Sauce Labs Fleece Jacket (\$49.99) |
| **Postcondition** | Sản phẩm được loại bỏ thành công khỏi giỏ. |

### 1. Objective
Xác minh việc nhấn nút 'Remove' tại trang chi tiết hoạt động chính xác và làm biến mất huy hiệu giỏ hàng.

### 2. Test Steps

1. Đang ở trang chi tiết với nút hiển thị 'Remove'.
2. Nhấp vào nút 'Remove'.
3. Quan sát trạng thái nút và huy hiệu giỏ hàng.

### 3. Expected Result

Nút bấm đổi lại thành 'Add to cart' và huy hiệu số lượng trên giỏ hàng được cập nhật giảm đi 1.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực chức năng xóa tại trang chi tiết.


Xem chi tiết: [TC-23.md](Functional_Testing/Shopping_Cart/TC-23.md)


---

<a id="tc-24"></a>

## Test Case: TC-24 - Kiểm tra mở trang giỏ hàng và hiển thị danh sách sản phẩm đã thêm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-24 |
| **Name** | Kiểm tra mở trang giỏ hàng và hiển thị danh sách sản phẩm đã thêm |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Cart Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-13 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã thêm 2 sản phẩm (Backpack \$29.99 và Bike Light \$9.99) vào giỏ hàng. |
| **Test Data** | 2 mặt hàng trong giỏ hàng |
| **Postcondition** | Người dùng xem được tổng quan giỏ hàng trước khi thanh toán. |

### 1. Objective
Xác minh khi người dùng nhấp vào biểu tượng giỏ hàng, hệ thống điều hướng đến '/cart.html' và hiển thị đúng các mặt hàng đã chọn kèm số lượng và đơn giá.

### 2. Test Steps

1. Nhấp vào biểu tượng giỏ hàng ở góc trên bên phải trang web.
2. Kiểm tra URL trang đích chuyển đến '/cart.html'.
3. Kiểm tra tiêu đề hiển thị 'Your Cart'.
4. Kiểm tra danh sách hiển thị đúng 2 dòng sản phẩm với cột 'QTY' = 1 và giá tiền chính xác của từng món.

### 3. Expected Result

Trang giỏ hàng hiển thị đầy đủ thông tin của 2 sản phẩm đã thêm, có đủ các nút 'Continue Shopping' và 'Checkout'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính chính xác của dữ liệu giỏ hàng.


Xem chi tiết: [TC-24.md](Functional_Testing/Shopping_Cart/TC-24.md)


---

<a id="tc-25"></a>

## Test Case: TC-25 - Kiểm tra xóa trực tiếp sản phẩm trên trang giỏ hàng (Cart Page)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-25 |
| **Name** | Kiểm tra xóa trực tiếp sản phẩm trên trang giỏ hàng (Cart Page) |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Cart Page |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-14 |
| **Test Type** | Functional / List Update |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/cart.html' với 2 sản phẩm. |
| **Test Data** | Sản phẩm xóa: Sauce Labs Bike Light |
| **Postcondition** | Giỏ hàng cập nhật còn lại 1 sản phẩm. |

### 1. Objective
Xác minh khi nhấp nút 'Remove' ngay trên trang giỏ hàng, sản phẩm đó lập tức bị xóa khỏi danh sách và cập nhật huy hiệu.

### 2. Test Steps

1. Đang ở trang '/cart.html'.
2. Nhấp nút 'Remove' tương ứng với dòng sản phẩm 'Sauce Labs Bike Light'.
3. Quan sát danh sách giỏ hàng và huy hiệu trên biểu tượng giỏ.

### 3. Expected Result

Dòng sản phẩm 'Sauce Labs Bike Light' lập tức biến mất khỏi bảng giỏ hàng. Chỉ còn lại 1 sản phẩm 'Sauce Labs Backpack'. Huy hiệu giỏ hàng giảm từ 2 xuống 1.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra tính năng CRUD: Thao tác Delete trực tiếp trong giỏ hàng.


Xem chi tiết: [TC-25.md](Functional_Testing/Shopping_Cart/TC-25.md)


---

<a id="tc-26"></a>

## Test Case: TC-26 - Kiểm tra chức năng nút 'Continue Shopping' quay lại trang mua hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-26 |
| **Name** | Kiểm tra chức năng nút 'Continue Shopping' quay lại trang mua hàng |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Cart Page |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-07 |
| **TestScenarioID** | TS-15 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/cart.html' với ít nhất 1 sản phẩm. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng quay lại mua sắm tiếp mà không bị mất dữ liệu giỏ hàng. |

### 1. Objective
Xác minh nút 'Continue Shopping' đưa người dùng quay lại trang danh mục sản phẩm và giữ nguyên các mặt hàng hiện có trong giỏ.

### 2. Test Steps

1. Đang ở trang giỏ hàng '/cart.html'.
2. Nhấp vào nút 'Continue Shopping'.

### 3. Expected Result

Hệ thống điều hướng quay trở lại trang danh mục sản phẩm '/inventory.html'. Huy hiệu giỏ hàng vẫn giữ nguyên số lượng sản phẩm đang có.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra khả năng tiếp tục trải nghiệm mua sắm.


Xem chi tiết: [TC-26.md](Functional_Testing/Shopping_Cart/TC-26.md)


---

<a id="tc-27"></a>

## Test Case: TC-27 - Kiểm tra duy trì trạng thái giỏ hàng khi tải lại trang trình duyệt (F5 / Refresh)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-27 |
| **Name** | Kiểm tra duy trì trạng thái giỏ hàng khi tải lại trang trình duyệt (F5 / Refresh) |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Shopping Cart / Storage |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-08 |
| **TestScenarioID** | TS-16 |
| **Test Type** | Functional / State Persistence |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã thêm 2 sản phẩm vào giỏ hàng (huy hiệu hiển thị '2'). |
| **Test Data** | 2 sản phẩm bất kỳ |
| **Postcondition** | Dữ liệu giỏ hàng không bị xóa khi trang web được tải lại. |

### 1. Objective
Xác minh dữ liệu giỏ hàng được lưu trữ bền vững (State Persistence) và không bị mất khi người dùng bấm phím F5 hoặc làm mới trình duyệt.

### 2. Test Steps

1. Thêm 2 sản phẩm vào giỏ hàng tại trang danh mục.
2. Nhấn phím F5 hoặc nhấp nút 'Reload this page' trên trình duyệt.
3. Kiểm tra huy hiệu số lượng trên giỏ hàng và trạng thái các nút bấm.
4. Chuyển sang trang '/cart.html' và kiểm tra danh sách sản phẩm.

### 3. Expected Result

Sau khi tải lại trang, huy hiệu giỏ hàng vẫn hiển thị số '2', các nút của 2 sản phẩm đó vẫn ở trạng thái 'Remove', và danh sách trong giỏ hàng vẫn còn nguyên vẹn.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra khả năng lưu trữ trạng thái vào LocalStorage / SessionStorage.


Xem chi tiết: [TC-27.md](Functional_Testing/Shopping_Cart/TC-27.md)


---

<a id="tc-28"></a>

## Test Case: TC-28 - Kiểm tra chức năng xóa sản phẩm khỏi giỏ hàng đối với sản phẩm Fleece Jacket khi đăng nhập bằng problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-28 |
| **Name** | Kiểm tra chức năng xóa sản phẩm khỏi giỏ hàng đối với sản phẩm Fleece Jacket khi đăng nhập bằng problem_user |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Shopping Cart Management |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-06 |
| **TestScenarioID** | TS-12 |
| **Test Type** | Functional / Negative / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'problem_user'; đã thêm 'Sauce Labs Fleece Jacket' vào giỏ hàng. |
| **Test Data** | Username: problem_user | Sản phẩm: Sauce Labs Fleece Jacket (\$49.99) |
| **Postcondition** | Sản phẩm được xóa thành công khỏi giỏ hàng. |

### 1. Objective
Xác minh nút 'Remove' hoạt động chính xác khi người dùng muốn loại bỏ áo khoác Fleece Jacket ra khỏi giỏ hàng.

### 2. Test Steps

1. Đăng nhập bằng 'problem_user' / 'secret_sauce'.
2. Tìm sản phẩm 'Sauce Labs Fleece Jacket' và nhấp 'Add to cart'.
3. Xác nhận nút chuyển thành 'Remove' và huy hiệu giỏ hàng hiển thị '1'.
4. Nhấp vào nút 'Remove' của sản phẩm 'Sauce Labs Fleece Jacket'.

### 3. Expected Result

Nút 'Remove' chuyển lại thành 'Add to cart' và huy hiệu giỏ hàng giảm từ 1 về 0 (biến mất hoàn toàn).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Nút Remove của áo Fleece Jacket bị vô hiệu hóa sự kiện onClick, người dùng không thể xóa món hàng này.


Xem chi tiết: [TC-28.md](Functional_Testing/Shopping_Cart/TC-28.md)


---

<a id="tc-29"></a>

## Test Case: TC-29 - Kiểm tra chặn quy trình thanh toán khi giỏ hàng không có sản phẩm nào (Empty Cart Checkout)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-29 |
| **Name** | Kiểm tra chặn quy trình thanh toán khi giỏ hàng không có sản phẩm nào (Empty Cart Checkout) |
| **Folder** | Functional_Testing/Shopping_Cart |
| **Component** | Shopping Cart / Checkout |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-08 |
| **TestScenarioID** | TS-17 |
| **Test Type** | Functional / Negative / Business Logic / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đã đăng nhập với 'standard_user', giỏ hàng đang trống hoàn toàn (huy hiệu giỏ hàng không hiển thị). |
| **Test Data** | User: standard_user | Giỏ hàng: 0 sản phẩm |
| **Postcondition** | Quy trình thanh toán bị chặn; người dùng không thể tạo đơn hàng ảo 0 đồng. |

### 1. Objective
Xác minh hệ thống e-commerce phải ngăn chặn người dùng tiến hành thanh toán khi giỏ hàng đang rỗng (0 sản phẩm, tổng tiền \$0.00).

### 2. Test Steps

1. Truy cập trang web và đăng nhập bằng tài khoản 'standard_user'.
2. Nhấp vào biểu tượng giỏ hàng để chuyển đến trang '/cart.html'.
3. Xác nhận danh sách giỏ hàng không có sản phẩm nào.
4. Nhấp vào nút 'Checkout'.

### 3. Expected Result

Nút 'Checkout' bị vô hiệu hóa (disabled), hoặc khi nhấp vào hệ thống hiển thị thông báo cảnh báo 'Your cart is empty. Please add items before checkout.' và giữ người dùng ở lại trang giỏ hàng, không cho phép chuyển tiếp sang trang thanh toán.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Lỗi logic nghiệp vụ trên SauceDemo: Hệ thống cho phép checkout giỏ hàng rỗng và hoàn tất đơn hàng \$0.00.


Xem chi tiết: [TC-29.md](Functional_Testing/Shopping_Cart/TC-29.md)


---

<a id="tc-30"></a>

## Test Case: TC-30 - Kiểm tra chuyển hướng từ giỏ hàng sang Checkout Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-30 |
| **Name** | Kiểm tra chuyển hướng từ giỏ hàng sang Checkout Bước 1 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-18 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/cart.html' và giỏ hàng có chứa ít nhất 1 sản phẩm. |
| **Test Data** | Sản phẩm trong giỏ: 1 món |
| **Postcondition** | Người dùng bước vào quy trình thanh toán. |

### 1. Objective
Xác minh khi người dùng nhấp 'Checkout' trên trang giỏ hàng có chứa sản phẩm, hệ thống mở đúng trang điền thông tin khách hàng Bước 1.

### 2. Test Steps

1. Tại trang giỏ hàng '/cart.html', nhấp vào nút 'Checkout'.
2. Quan sát sự chuyển trang của trình duyệt.

### 3. Expected Result

Trình duyệt điều hướng thành công đến '/checkout-step-one.html'. Tiêu đề trang hiển thị 'Checkout: Your Information' với 3 ô nhập: First Name, Last Name, Zip/Postal Code.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bắt đầu chu trình thanh toán đơn hàng.


Xem chi tiết: [TC-30.md](Functional_Testing/Checkout/TC-30.md)


---

<a id="tc-31"></a>

## Test Case: TC-31 - Kiểm tra nhập thông tin khách hàng hợp lệ tại Checkout Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-31 |
| **Name** | Kiểm tra nhập thông tin khách hàng hợp lệ tại Checkout Bước 1 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-19 |
| **Test Type** | Functional / Form Submission |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: Doe | Zip/Postal Code: 10001 |
| **Postcondition** | Thông tin giao hàng được lưu tạm để tính thuế và phí tại Bước 2. |

### 1. Objective
Xác minh khi điền đầy đủ và hợp lệ First Name, Last Name và Zip/Postal Code, hệ thống chuyển tiếp thành công sang Bước 2.

### 2. Test Steps

1. Nhập 'John' vào ô 'First Name'.
2. Nhập 'Doe' vào ô 'Last Name'.
3. Nhập '10001' vào ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

### 3. Expected Result

Hệ thống xác thực form thành công và điều hướng mượt mà sang trang tổng quan đơn hàng '/checkout-step-two.html'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Luồng chuẩn (Happy Path) cho bước điền thông tin thanh toán.


Xem chi tiết: [TC-31.md](Functional_Testing/Checkout/TC-31.md)


---

<a id="tc-32"></a>

## Test Case: TC-32 - Kiểm tra thông báo lỗi khi để trống trường First Name tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-32 |
| **Name** | Kiểm tra thông báo lỗi khi để trống trường First Name tại Bước 1 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Negative / Form Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: '' (để trống) | Last Name: Doe | Postal Code: 10001 |
| **Postcondition** | Người dùng vẫn ở tại Bước 1; không chuyển trang. |

### 1. Objective
Đảm bảo hệ thống chặn tiếp tục và cảnh báo cụ thể khi người dùng bỏ trống trường bắt buộc First Name (Kỹ thuật phân vùng tương đương: Thiếu trường bắt buộc).

### 2. Test Steps

1. Để trống ô 'First Name'.
2. Nhập 'Doe' vào ô 'Last Name'.
3. Nhập '10001' vào ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

### 3. Expected Result

Hệ thống chặn chuyển trang. Hộp thông báo màu đỏ hiển thị chính xác nội dung: 'Error: First Name is required'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực trường bắt buộc First Name.


Xem chi tiết: [TC-32.md](Functional_Testing/Checkout/TC-32.md)


---

<a id="tc-33"></a>

## Test Case: TC-33 - Kiểm tra thông báo lỗi khi để trống trường Last Name tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-33 |
| **Name** | Kiểm tra thông báo lỗi khi để trống trường Last Name tại Bước 1 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Negative / Form Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: '' (để trống) | Postal Code: 10001 |
| **Postcondition** | Người dùng vẫn ở tại Bước 1. |

### 1. Objective
Đảm bảo hệ thống cảnh báo rõ ràng khi người dùng bỏ trống trường bắt buộc Last Name.

### 2. Test Steps

1. Nhập 'John' vào ô 'First Name'.
2. Để trống hoàn toàn ô 'Last Name'.
3. Nhập '10001' vào ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

### 3. Expected Result

Hệ thống chặn chuyển trang và hiển thị thông báo lỗi màu đỏ: 'Error: Last Name is required'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực trường bắt buộc Last Name.


Xem chi tiết: [TC-33.md](Functional_Testing/Checkout/TC-33.md)


---

<a id="tc-34"></a>

## Test Case: TC-34 - Kiểm tra thông báo lỗi khi để trống trường Postal Code tại Bước 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-34 |
| **Name** | Kiểm tra thông báo lỗi khi để trống trường Postal Code tại Bước 1 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-20 |
| **Test Type** | Negative / Form Validation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: John | Last Name: Doe | Postal Code: '' (để trống) |
| **Postcondition** | Người dùng vẫn ở tại Bước 1. |

### 1. Objective
Đảm bảo hệ thống cảnh báo rõ ràng khi người dùng bỏ trống trường bắt buộc Zip/Postal Code.

### 2. Test Steps

1. Nhập 'John' vào ô 'First Name'.
2. Nhập 'Doe' vào ô 'Last Name'.
3. Để trống hoàn toàn ô 'Zip/Postal Code'.
4. Nhấp vào nút 'Continue'.

### 3. Expected Result

Hệ thống chặn chuyển trang và hiển thị thông báo lỗi màu đỏ: 'Error: Postal Code is required'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực trường bắt buộc Postal Code.


Xem chi tiết: [TC-34.md](Functional_Testing/Checkout/TC-34.md)


---

<a id="tc-35"></a>

## Test Case: TC-35 - Kiểm tra nhập các định dạng mã bưu chính đặc biệt (Ký tự chữ và dấu gạch nối)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-35 |
| **Name** | Kiểm tra nhập các định dạng mã bưu chính đặc biệt (Ký tự chữ và dấu gạch nối) |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-19 |
| **Test Type** | Functional / Boundary |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | Postal Code: K1A-0B1 |
| **Postcondition** | Chuyển tiếp đến Bước 2 bình thường. |

### 1. Objective
Xác minh ô Postal Code chấp nhận các định dạng mã bưu điện quốc tế hợp lệ có chứa chữ cái hoặc dấu gạch nối (Ví dụ định dạng Canada: K1A 0B1 hoặc UK: SW1A 1AA).

### 2. Test Steps

1. Nhập 'John' vào ô First Name.
2. Nhập 'Doe' vào ô Last Name.
3. Nhập 'K1A-0B1' vào ô Zip/Postal Code.
4. Nhấp vào nút 'Continue'.

### 3. Expected Result

Hệ thống chấp nhận mã bưu điện quốc tế hợp lệ và chuyển tiếp thành công sang màn hình Bước 2.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hỗ trợ định dạng mã bưu điện quốc tế (Equivalence Partitioning: Ký tự chữ số hỗn hợp).


Xem chi tiết: [TC-35.md](Functional_Testing/Checkout/TC-35.md)


---

<a id="tc-36"></a>

## Test Case: TC-36 - Kiểm tra hủy bỏ quy trình thanh toán tại Bước 1 bằng nút 'Cancel'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-36 |
| **Name** | Kiểm tra hủy bỏ quy trình thanh toán tại Bước 1 bằng nút 'Cancel' |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 1 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-21 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-one.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Quay về trang giỏ hàng; không phát sinh thay đổi dữ liệu. |

### 1. Objective
Xác minh khi người dùng nhấp 'Cancel' tại Bước 1, hệ thống hủy thao tác và đưa người dùng quay lại trang xem giỏ hàng.

### 2. Test Steps

1. Đang ở màn hình Bước 1.
2. Nhấp vào nút 'Cancel'.

### 3. Expected Result

Hệ thống điều hướng quay trở lại trang giỏ hàng '/cart.html'. Dữ liệu các sản phẩm trong giỏ hàng được giữ nguyên vẹn.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra luồng thoát hủy bỏ (Cancel flow).


Xem chi tiết: [TC-36.md](Functional_Testing/Checkout/TC-36.md)


---

<a id="tc-37"></a>

## Test Case: TC-37 - Kiểm tra hiển thị danh sách sản phẩm và tổng quan đơn hàng tại Checkout Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-37 |
| **Name** | Kiểm tra hiển thị danh sách sản phẩm và tổng quan đơn hàng tại Checkout Bước 2 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-22 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã hoàn thành Bước 1 với 2 sản phẩm trong giỏ (Backpack \$29.99 và Bike Light \$9.99); đang ở '/checkout-step-two.html'. |
| **Test Data** | 2 sản phẩm đang thanh toán |
| **Postcondition** | Người dùng nắm rõ tóm tắt mặt hàng trước khi trả tiền. |

### 1. Objective
Xác minh trang Checkout Bước 2 hiển thị chính xác toàn bộ các mặt hàng chuẩn bị mua kèm số lượng và đơn giá từng món.

### 2. Test Steps

1. Quan sát phần danh sách sản phẩm trên trang Bước 2.
2. Kiểm tra tên, số lượng (QTY=1) và đơn giá của từng sản phẩm đối chiếu với lúc chọn trong giỏ hàng.

### 3. Expected Result

Hiển thị đúng 2 sản phẩm: Sauce Labs Backpack (\$29.99) và Sauce Labs Bike Light (\$9.99). Không có sản phẩm nào bị sai giá hay thiếu thông tin.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Xác thực tính toàn vẹn danh sách đơn hàng.


Xem chi tiết: [TC-37.md](Functional_Testing/Checkout/TC-37.md)


---

<a id="tc-38"></a>

## Test Case: TC-38 - Kiểm tra hiển thị thông tin thanh toán và thông tin giao hàng tại Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-38 |
| **Name** | Kiểm tra hiển thị thông tin thanh toán và thông tin giao hàng tại Bước 2 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-22 |
| **Test Type** | Functional / UI Verification |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-two.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Các thông tin tĩnh hiển thị đầy đủ, minh bạch. |

### 1. Objective
Xác minh các khối thông tin cố định Payment Information và Shipping Information hiển thị chính xác theo quy định của hệ thống.

### 2. Test Steps

1. Cuộn trang đến phần 'Payment Information'.
2. Kiểm tra mã thẻ hiển thị.
3. Cuộn đến phần 'Shipping Information'.
4. Kiểm tra phương thức vận chuyển hiển thị.

### 3. Expected Result

Payment Information hiển thị chuẩn xác mã: 'SauceCard #31437'. Shipping Information hiển thị chuẩn xác: 'Free Pony Express Delivery!'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hiển thị văn bản tĩnh và định dạng thẻ thanh toán.


Xem chi tiết: [TC-38.md](Functional_Testing/Checkout/TC-38.md)


---

<a id="tc-39"></a>

## Test Case: TC-39 - Kiểm tra tính toán tài chính: Tổng tiền hàng, Thuế 8% và Tổng thanh toán tại Bước 2

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-39 |
| **Name** | Kiểm tra tính toán tài chính: Tổng tiền hàng, Thuế 8% và Tổng thanh toán tại Bước 2 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-23 |
| **Test Type** | Functional / Calculation & Boundary |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang Bước 2 với 2 sản phẩm: Sauce Labs Backpack (\$29.99) và Sauce Labs Bike Light (\$9.99). |
| **Test Data** | Item 1: \$29.99 | Item 2: \$9.99 | Kỳ vọng Item total: \$39.98 | Thuế 8%: \$39.98 * 0.08 = \$3.20 | Kỳ vọng Total: \$43.18 |
| **Postcondition** | Số liệu tài chính hoàn toàn minh bạch và chuẩn xác từng xu. |

### 1. Objective
Xác minh công thức tính toán tài chính: Item total = Tổng giá các sản phẩm; Tax = 8% của Item total (làm tròn 2 chữ số thập phân); Total = Item total + Tax.

### 2. Test Steps

1. Đọc giá trị tại dòng 'Item total:'.
2. Đọc giá trị tại dòng 'Tax:'.
3. Đọc giá trị tại dòng 'Total:'.
4. So sánh các giá trị thực tế với công thức tính toán toán học chuẩn.

### 3. Expected Result

Item total hiển thị chính xác 'Item total: \$39.98'. Thuế hiển thị chính xác 'Tax: \$3.20' (làm tròn từ 3.1984 lên 3.20). Tổng cộng hiển thị chính xác 'Total: \$43.18'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử cốt lõi cho tính toán tài chính và làm tròn số thập phân (BVA & Financial Calculation).


Xem chi tiết: [TC-39.md](Functional_Testing/Checkout/TC-39.md)


---

<a id="tc-40"></a>

## Test Case: TC-40 - Kiểm tra hủy bỏ thanh toán tại Bước 2 bằng nút 'Cancel'

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-40 |
| **Name** | Kiểm tra hủy bỏ thanh toán tại Bước 2 bằng nút 'Cancel' |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 2 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-24 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-two.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Quay về trang danh mục mà không làm mất giỏ hàng. |

### 1. Objective
Xác minh khi nhấp 'Cancel' tại Bước 2, người dùng được đưa quay trở về trang danh mục sản phẩm và giỏ hàng vẫn giữ nguyên.

### 2. Test Steps

1. Tại trang Bước 2, nhấp vào nút 'Cancel'.

### 3. Expected Result

Hệ thống điều hướng người dùng quay lại trang danh mục sản phẩm '/inventory.html'. Giỏ hàng vẫn duy trì nguyên vẹn các sản phẩm đã chọn.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra hành vi nút Cancel tại Bước 2.


Xem chi tiết: [TC-40.md](Functional_Testing/Checkout/TC-40.md)


---

<a id="tc-41"></a>

## Test Case: TC-41 - Kiểm tra hoàn tất đặt hàng thành công tại Checkout Bước 3

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-41 |
| **Name** | Kiểm tra hoàn tất đặt hàng thành công tại Checkout Bước 3 |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 3 |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-11 |
| **TestScenarioID** | TS-25 |
| **Test Type** | Functional / Transaction |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/checkout-step-two.html' với thông tin tài chính hợp lệ. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Đơn hàng hoàn tất; giỏ hàng giải phóng sạch sẽ. |

### 1. Objective
Xác minh khi người dùng nhấp 'Finish' tại Bước 2, hệ thống hoàn tất đơn hàng, chuyển sang Bước 3, hiển thị thông điệp cảm ơn và tự động xóa sạch giỏ hàng.

### 2. Test Steps

1. Tại trang Bước 2, nhấp vào nút 'Finish'.
2. Kiểm tra URL trang web chuyển sang '/checkout-complete.html'.
3. Kiểm tra thông điệp hoàn tất hiển thị trên trang.
4. Kiểm tra biểu tượng giỏ hàng ở góc trên bên phải.

### 3. Expected Result

Chuyển hướng thành công đến '/checkout-complete.html'. Hiển thị tiêu đề lớn 'Thank you for your order!' và thông điệp 'Your order has been dispatched...'. Huy hiệu số lượng trên giỏ hàng biến mất hoàn toàn (giỏ hàng đã được làm sạch sau mua hàng).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử then chốt cho giao dịch mua hàng thành công.


Xem chi tiết: [TC-41.md](Functional_Testing/Checkout/TC-41.md)


---

<a id="tc-42"></a>

## Test Case: TC-42 - Kiểm tra nút 'Back Home' đưa người dùng quay về trang chủ sau khi hoàn tất mua hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-42 |
| **Name** | Kiểm tra nút 'Back Home' đưa người dùng quay về trang chủ sau khi hoàn tất mua hàng |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Step 3 |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-11 |
| **TestScenarioID** | TS-26 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang xác nhận hoàn tất đơn hàng '/checkout-complete.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng sẵn sàng cho một chu trình mua hàng mới. |

### 1. Objective
Xác minh nút 'Back Home' tại trang hoàn tất đơn hàng đưa người dùng trở về trang danh mục và giỏ hàng vẫn ở trạng thái trống.

### 2. Test Steps

1. Tại trang hoàn tất đơn hàng, nhấp vào nút 'Back Home'.

### 3. Expected Result

Hệ thống điều hướng về trang danh mục sản phẩm '/inventory.html'. Giỏ hàng rỗng, tất cả các nút sản phẩm hiển thị 'Add to cart'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kết thúc chu trình đặt hàng.


Xem chi tiết: [TC-42.md](Functional_Testing/Checkout/TC-42.md)


---

<a id="tc-43"></a>

## Test Case: TC-43 - Kiểm tra nhập liệu và lưu trữ giá trị tại trường Last Name trong form Checkout Step 1 với problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-43 |
| **Name** | Kiểm tra nhập liệu và lưu trữ giá trị tại trường Last Name trong form Checkout Step 1 với problem_user |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Workflow / Form Handling |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-09 |
| **TestScenarioID** | TS-19 |
| **Test Type** | Functional / Form Validation / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'problem_user'; giỏ hàng có ít nhất 1 sản phẩm; đang ở trang '/checkout-step-one.html'. |
| **Test Data** | First Name: 'Alex' | Last Name: 'Smith' | Postal Code: '90001' |
| **Postcondition** | Chuyển sang màn hình xác nhận đơn hàng Bước 2. |

### 1. Objective
Xác minh trường 'Last Name' nhận đúng ký tự người dùng gõ vào và cho phép chuyển tiếp sang Bước 2.

### 2. Test Steps

1. Đăng nhập 'problem_user' và thêm 1 sản phẩm vào giỏ.
2. Đi đến '/cart.html' và nhấp 'Checkout'.
3. Nhập 'Alex' vào ô 'First Name'.
4. Nhập 'Smith' vào ô 'Last Name'.
5. Nhập '90001' vào ô 'Postal Code'.
6. Nhấp vào nút 'Continue'.

### 3. Expected Result

Ô 'Last Name' hiển thị đầy đủ chuỗi 'Smith'. Khi nhấp 'Continue', hệ thống lưu trữ thông tin và điều hướng thành công đến '/checkout-step-two.html'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug Critical cố tình của SauceDemo: Trường Last Name bị khóa hoặc tự động ghi đè, hệ thống luôn báo lỗi 'Error: Last Name is required', chặn đứng toàn bộ luồng thanh toán của problem_user.


Xem chi tiết: [TC-43.md](Functional_Testing/Checkout/TC-43.md)


---

<a id="tc-44"></a>

## Test Case: TC-44 - Kiểm tra hoàn tất đơn hàng tại Checkout Step 2 không bị chặn bởi lỗi Runtime khi đăng nhập bằng error_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-44 |
| **Name** | Kiểm tra hoàn tất đơn hàng tại Checkout Step 2 không bị chặn bởi lỗi Runtime khi đăng nhập bằng error_user |
| **Folder** | Functional_Testing/Checkout |
| **Component** | Checkout Workflow / Transaction |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Blocker |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-10 |
| **TestScenarioID** | TS-24 |
| **Test Type** | Functional / Transaction Integrity / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'error_user'; đã điền xong Bước 1; đang ở '/checkout-step-two.html'. |
| **Test Data** | Username: error_user | Sản phẩm trong giỏ: 1 món bất kỳ |
| **Postcondition** | Đơn hàng được ghi nhận, giỏ hàng được làm mới. |

### 1. Objective
Xác minh nút 'Finish' tại trang tổng quan đơn hàng xử lý thành công giao dịch và đưa người dùng đến trang hoàn tất mà không gặp lỗi JavaScript.

### 2. Test Steps

1. Đăng nhập bằng 'error_user' và thêm 1 sản phẩm vào giỏ.
2. Đi qua Checkout Bước 1 với thông tin hợp lệ.
3. Tại trang Checkout Bước 2, nhấp vào nút 'Finish'.

### 3. Expected Result

Hệ thống tiếp nhận đơn hàng thành công và chuyển hướng đến '/checkout-complete.html' kèm thông báo 'Thank you for your order!'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug Blocker cố tình của SauceDemo: Nhấp nút Finish văng lỗi runtime exception không bắt được, chặn người dùng hoàn tất giao dịch.


Xem chi tiết: [TC-44.md](Functional_Testing/Checkout/TC-44.md)


---

<a id="tc-45"></a>

## Test Case: TC-45 - Kiểm tra mở và đóng menu Sidebar

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-45 |
| **Name** | Kiểm tra mở và đóng menu Sidebar |
| **Folder** | Functional_Testing/Sidebar_Navigation |
| **Component** | Sidebar Navigation |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / UI Animation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang đăng nhập tại trang '/inventory.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Menu đóng lại; người dùng trở lại màn hình chính. |

### 1. Objective
Xác minh menu Sidebar có thể mở trượt mượt mà khi nhấp vào biểu tượng hamburger và đóng lại khi nhấp vào nút biểu tượng 'X'.

### 2. Test Steps

1. Nhấp vào biểu tượng 3 dấu gạch ngang ở góc trên bên trái.
2. Xác nhận menu trượt hiển thị đủ 4 mục: 'All Items', 'About', 'Logout', 'Reset App State'.
3. Nhấp vào biểu tượng dấu 'X' (Close menu) ở góc trên bên phải menu trượt.

### 3. Expected Result

Menu trượt mở ra đầy đủ không bị che khuất và đóng lại mượt mà khi bấm 'X'. Giao diện trang chính hoạt động bình thường.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra UI component trượt (Slide-out navigation drawer).


Xem chi tiết: [TC-45.md](Functional_Testing/Sidebar_Navigation/TC-45.md)


---

<a id="tc-46"></a>

## Test Case: TC-46 - Kiểm tra mục 'All Items' trong Sidebar đưa người dùng về trang danh mục

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-46 |
| **Name** | Kiểm tra mục 'All Items' trong Sidebar đưa người dùng về trang danh mục |
| **Folder** | Functional_Testing/Sidebar_Navigation |
| **Component** | Sidebar Navigation |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / Navigation |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang ở trang giỏ hàng '/cart.html'. |
| **Test Data** | Không cần dữ liệu đặc biệt. |
| **Postcondition** | Người dùng quay về trang danh mục sản phẩm. |

### 1. Objective
Xác minh khi người dùng đang ở bất kỳ trang nào (ví dụ trang giỏ hàng), nhấp vào 'All Items' trong Sidebar sẽ điều hướng về trang danh mục sản phẩm.

### 2. Test Steps

1. Đang ở trang '/cart.html'.
2. Mở Sidebar menu.
3. Nhấp vào liên kết 'All Items'.

### 3. Expected Result

Hệ thống điều hướng về trang danh mục '/inventory.html' và hiển thị đầy đủ danh sách các mặt hàng.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra điều hướng nội bộ từ Sidebar.


Xem chi tiết: [TC-46.md](Functional_Testing/Sidebar_Navigation/TC-46.md)


---

<a id="tc-47"></a>

## Test Case: TC-47 - Kiểm tra mục 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-47 |
| **Name** | Kiểm tra mục 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs |
| **Folder** | Functional_Testing/Sidebar_Navigation |
| **Component** | Sidebar Navigation |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / External Link |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Người dùng đang đăng nhập và mở menu Sidebar. |
| **Test Data** | URL đích: https://saucelabs.com/ |
| **Postcondition** | Người dùng tiếp cận được trang giới thiệu bên ngoài. |

### 1. Objective
Xác minh liên kết 'About' trong Sidebar trỏ đúng địa chỉ trang chủ chính thức của Sauce Labs (https://saucelabs.com/).

### 2. Test Steps

1. Mở menu Sidebar.
2. Nhấp vào mục 'About'.
3. Kiểm tra URL đích trên thanh địa chỉ của trình duyệt.

### 3. Expected Result

Trình duyệt điều hướng thành công đến website chính thức 'https://saucelabs.com/' mà không gặp lỗi kết nối.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra liên kết ngoại tuyến (Outbound link).


Xem chi tiết: [TC-47.md](Functional_Testing/Sidebar_Navigation/TC-47.md)


---

<a id="tc-48"></a>

## Test Case: TC-48 - Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng và xóa sạch giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-48 |
| **Name** | Kiểm tra chức năng 'Reset App State' đặt lại trạng thái ứng dụng và xóa sạch giỏ hàng |
| **Folder** | Functional_Testing/Sidebar_Navigation |
| **Component** | App State / Local Storage |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Functional / State Reset |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã thêm 2 sản phẩm vào giỏ hàng (huy hiệu hiển thị '2'); đang ở trang '/inventory.html'. |
| **Test Data** | 2 sản phẩm đang có trong giỏ hàng |
| **Postcondition** | Trạng thái ứng dụng được khôi phục về mặc định như lúc mới đăng nhập. |

### 1. Objective
Xác minh khi người dùng kích hoạt 'Reset App State', toàn bộ sản phẩm trong giỏ hàng bị xóa sạch, huy hiệu giỏ hàng biến mất và các nút 'Remove' quay về 'Add to cart'.

### 2. Test Steps

1. Mở menu Sidebar.
2. Nhấp vào mục 'Reset App State'.
3. Đóng menu Sidebar và quan sát giao diện trang danh mục.

### 3. Expected Result

Huy hiệu số lượng giỏ hàng biến mất hoàn toàn. Các nút 'Remove' của các sản phẩm đã chọn trước đó chuyển lại thành 'Add to cart'.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra khả năng reset trạng thái phiên kiểm thử.


Xem chi tiết: [TC-48.md](Functional_Testing/Sidebar_Navigation/TC-48.md)


---

<a id="tc-49"></a>

## Test Case: TC-49 - Kiểm tra tính hợp lệ của liên kết điều hướng 'About' trong Sidebar đối với problem_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-49 |
| **Name** | Kiểm tra tính hợp lệ của liên kết điều hướng 'About' trong Sidebar đối với problem_user |
| **Folder** | Functional_Testing/Sidebar_Navigation |
| **Component** | Sidebar Navigation / Broken Link |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-12 |
| **TestScenarioID** | TS-27 |
| **Test Type** | Navigation / Broken Link / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đã đăng nhập bằng 'problem_user'. |
| **Test Data** | Username: problem_user |
| **Postcondition** | Trang web đích tải thành công không bị lỗi kết nối. |

### 1. Objective
Xác minh liên kết 'About' trong menu trượt điều hướng người dùng đến đúng trang giới thiệu chính thức của Sauce Labs.

### 2. Test Steps

1. Đăng nhập bằng 'problem_user' / 'secret_sauce'.
2. Nhấp vào biểu tượng 3 dấu gạch ngang (hamburger menu) để mở Sidebar.
3. Nhấp vào mục 'About' trong danh sách menu.

### 3. Expected Result

Trình duyệt chuyển hướng thành công đến trang chủ chính thức 'https://saucelabs.com/' với mã trạng thái HTTP 200 OK.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: Đường dẫn About bị gắn sai URL dẫn đến trang lỗi 404 Not Found.


Xem chi tiết: [TC-49.md](Functional_Testing/Sidebar_Navigation/TC-49.md)


---

<a id="tc-50"></a>

## Test Case: TC-50 - Kiểm tra toàn diện quy trình mua sắm thương mại điện tử End-to-End từ đăng nhập đến nhận biên lai

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-50 |
| **Name** | Kiểm tra toàn diện quy trình mua sắm thương mại điện tử End-to-End từ đăng nhập đến nhận biên lai |
| **Folder** | Functional_Testing/End_to_End |
| **Component** | End-to-End Workflow |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-13 |
| **TestScenarioID** | TS-28 |
| **Test Type** | Functional / End-to-End System Integration |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt sạch không có cookie phiên; tài khoản 'standard_user' hợp lệ. |
| **Test Data** | User: standard_user | Sản phẩm: Sauce Labs Backpack (\$29.99) & Sauce Labs Onesie (\$7.99) | Khách: Khong Duc Anh, Post: 100000 |
| **Postcondition** | Đơn hàng hoàn tất, phiên làm việc đóng an toàn. |

### 1. Objective
Xác minh luồng trải nghiệm khách hàng xuyên suốt: Đăng nhập -> Sắp xếp lọc hàng -> Thêm 2 sản phẩm -> Kiểm tra giỏ -> Điền thông tin giao hàng -> Xác thực hóa đơn thanh toán -> Nhận biên lai hoàn tất và Đăng xuất.

### 2. Test Steps

1. Đăng nhập bằng tài khoản 'standard_user' / 'secret_sauce'.
2. Tại trang danh mục, chọn sắp xếp theo 'Price (low to high)'.
3. Nhấp 'Add to cart' tại sản phẩm 'Sauce Labs Onesie' (\$7.99).
4. Nhấp 'Add to cart' tại sản phẩm 'Sauce Labs Backpack' (\$29.99).
5. Nhấp vào biểu tượng giỏ hàng để chuyển sang '/cart.html', đối chiếu đủ 2 sản phẩm.
6. Nhấp nút 'Checkout' để vào Bước 1.
7. Điền First Name: 'Khong', Last Name: 'Duc Anh', Zip: '100000' rồi nhấn 'Continue'.
8. Tại Bước 2, kiểm tra: Item total = \$37.98, Tax (8%) = \$3.04, Total = \$41.02.
9. Nhấp nút 'Finish' để hoàn tất đơn hàng.
10. Xác nhận màn hình hiển thị 'Thank you for your order!'.
11. Mở menu Sidebar và nhấp 'Logout' để kết thúc phiên an toàn.

### 3. Expected Result

Toàn bộ chu trình mua hàng thực hiện trơn tru từ đầu đến cuối không phát sinh bất kỳ lỗi gián đoạn nào. Số liệu tính toán khớp từng xu, giỏ hàng được làm sạch và người dùng đăng xuất an toàn.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Ca kiểm thử tích hợp toàn diện quan trọng nhất của hệ thống e-commerce.


Xem chi tiết: [TC-50.md](Functional_Testing/End_to_End/TC-50.md)


---

<a id="tc-51"></a>

## Test Case: TC-51 - Kiểm tra API POST /api/v1/auth/login xác thực đăng nhập thành công với tài khoản hợp lệ

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-51 |
| **Name** | Kiểm tra API POST /api/v1/auth/login xác thực đăng nhập thành công với tài khoản hợp lệ |
| **Folder** | API_Testing |
| **Component** | Authentication API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Integration Testing |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Máy chủ API hoạt động bình thường, endpoint '/api/v1/auth/login' sẵn sàng nhận request. |
| **Test Data** | Headers: {'Content-Type': 'application/json'} | Body: {'username': 'standard_user', 'password': 'secret_sauce'} |
| **Postcondition** | Phiên làm việc được khởi tạo trên backend token store. |

### 1. Objective
Xác minh API xác thực trả về mã trạng thái HTTP 200 OK kèm token xác thực JWT và thông tin phiên làm việc khi gửi credentials hợp lệ.

### 2. Test Steps

1. Gửi HTTP POST request đến endpoint '/api/v1/auth/login'.
2. Kiểm tra mã trạng thái HTTP response status code.
3. Kiểm tra JSON response body chứa trường 'accessToken', 'tokenType': 'Bearer', và 'expiresIn'.
4. Xác thực response header chứa 'Set-Cookie' với cờ Secure và HttpOnly.

### 3. Expected Result

Mã phản hồi HTTP 200 OK. JSON Response trả về cấu trúc hợp lệ chứa access token và thời hạn phiên; không để lộ thông tin nhạy cảm của mật khẩu trong body.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked do hệ thống frontend SauceDemo là Single Page App thuần client-side, không expose public REST API endpoints.


Xem chi tiết: [TC-51.md](API_Testing/TC-51.md)


---

<a id="tc-52"></a>

## Test Case: TC-52 - Kiểm tra API POST /api/v1/auth/login xử lý từ chối đăng nhập đối với tài khoản bị khóa (HTTP 423 Locked)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-52 |
| **Name** | Kiểm tra API POST /api/v1/auth/login xử lý từ chối đăng nhập đối với tài khoản bị khóa (HTTP 423 Locked) |
| **Folder** | API_Testing |
| **Component** | Authentication API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Negative Testing |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Tài khoản 'locked_out_user' có cờ trạng thái 'is_locked = true' trong CSDL. |
| **Test Data** | Headers: {'Content-Type': 'application/json'} | Body: {'username': 'locked_out_user', 'password': 'secret_sauce'} |
| **Postcondition** | Yêu cầu bị từ chối; không có phiên làm việc nào được cấp phát. |

### 1. Objective
Xác minh API phản hồi mã lỗi HTTP 423 Locked hoặc 403 Forbidden và thông điệp lỗi rõ ràng khi người dùng cố gắng xác thực với tài khoản bị khóa.

### 2. Test Steps

1. Gửi HTTP POST request đến endpoint '/api/v1/auth/login'.
2. Kiểm tra mã trạng thái HTTP response status code.
3. Kiểm tra mã lỗi nghiệp vụ trong body: 'error_code': 'ACCOUNT_LOCKED'.
4. Kiểm tra thông điệp mô tả: 'message': 'Sorry, this user has been locked out.'.

### 3. Expected Result

HTTP Status 423 Locked (hoặc 403 Forbidden). Body chứa mã lỗi 'ACCOUNT_LOCKED' và không sinh ra bất kỳ token xác thực nào.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked do kiến trúc client-side SPA.


Xem chi tiết: [TC-52.md](API_Testing/TC-52.md)


---

<a id="tc-53"></a>

## Test Case: TC-53 - Kiểm tra API GET /api/v1/products lấy danh mục sản phẩm và kiểm tra Schema JSON

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-53 |
| **Name** | Kiểm tra API GET /api/v1/products lấy danh mục sản phẩm và kiểm tra Schema JSON |
| **Folder** | API_Testing |
| **Component** | Catalog API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Schema Validation |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Header request chứa Bearer Token hợp lệ của 'standard_user'. |
| **Test Data** | Endpoint: GET /api/v1/products | Headers: {'Authorization': 'Bearer <token>'} |
| **Postcondition** | Dữ liệu trả về sẵn sàng cho client render. |

### 1. Objective
Xác minh endpoint trả về danh sách đầy đủ 6 sản phẩm kèm đúng kiểu dữ liệu (Schema Validation: id, name, price, stock, image_url).

### 2. Test Steps

1. Gửi HTTP GET request đến '/api/v1/products'.
2. Kiểm tra HTTP Status Code là 200 OK.
3. Kiểm tra mảng dữ liệu 'data' chứa chính xác 6 đối tượng sản phẩm.
4. Xác thực kiểu dữ liệu từng trường: 'id' (integer), 'name' (string), 'price' (float > 0), 'image_url' (url string hợp lệ).

### 3. Expected Result

HTTP Status 200 OK. JSON response tuân thủ 100% JSON Schema định nghĩa, mảng chứa đúng 6 sản phẩm với giá niêm yết chính xác.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked do kiến trúc client-side SPA.


Xem chi tiết: [TC-53.md](API_Testing/TC-53.md)


---

<a id="tc-54"></a>

## Test Case: TC-54 - Kiểm tra API POST /api/v1/cart/items thêm sản phẩm vào giỏ hàng và cập nhật tổng số lượng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-54 |
| **Name** | Kiểm tra API POST /api/v1/cart/items thêm sản phẩm vào giỏ hàng và cập nhật tổng số lượng |
| **Folder** | API_Testing |
| **Component** | Cart API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Functional Testing |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Người dùng có giỏ hàng đang trống. |
| **Test Data** | Headers: {'Authorization': 'Bearer <token>'} | Body: {'product_id': 1, 'quantity': 1} |
| **Postcondition** | Trạng thái giỏ hàng được cập nhật trong Redis / Database session. |

### 1. Objective
Xác minh endpoint xử lý thêm mặt hàng vào giỏ và trả về tổng số lượng cập nhật tức thì.

### 2. Test Steps

1. Gửi POST request đến '/api/v1/cart/items' với product_id=1, quantity=1.
2. Kiểm tra HTTP Status Code 201 Created.
3. Kiểm tra response body chứa 'cart_items_count': 1 và 'total_amount': 29.99.

### 3. Expected Result

HTTP Status 201 Created. Giỏ hàng trên server ghi nhận sản phẩm mới và cập nhật bộ đếm giỏ hàng thành 1.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked do kiến trúc client-side SPA.


Xem chi tiết: [TC-54.md](API_Testing/TC-54.md)


---

<a id="tc-55"></a>

## Test Case: TC-55 - Kiểm tra API POST /api/v1/checkout/orders hoàn tất đơn hàng và tính toán tài chính tự động

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-55 |
| **Name** | Kiểm tra API POST /api/v1/checkout/orders hoàn tất đơn hàng và tính toán tài chính tự động |
| **Folder** | API_Testing |
| **Component** | Checkout API |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-14 |
| **TestScenarioID** | TS-31 |
| **Test Type** | API / Transaction & Calculation |
| **Execution Environment** | Postman / Newman CLI / REST Client API Sandbox |
| **Precondition** | Giỏ hàng có sản phẩm, người dùng đã hoàn tất thông tin giao hàng. |
| **Test Data** | Headers: {'Authorization': 'Bearer <token>'} | Body: {'firstName': 'John', 'lastName': 'Doe', 'postalCode': '10001', 'items': [{'id': 4, 'qty': 1, 'price': 29.99}]} |
| **Postcondition** | Đơn hàng được lưu vào cơ sở dữ liệu backend. |

### 1. Objective
Xác minh endpoint tiếp nhận đơn hàng, tự động tính thuế 8%, tạo mã đơn hàng duy nhất và phản hồi mã 201 Created.

### 2. Test Steps

1. Gửi POST request đến '/api/v1/checkout/orders'.
2. Kiểm tra HTTP Status Code là 201 Created.
3. Kiểm tra trường 'orderId' không rỗng và có định dạng UUID/Mã đơn chuẩn.
4. Kiểm tra 'itemTotal': 29.99, 'tax': 2.40 (8%), 'grandTotal': 32.39.

### 3. Expected Result

HTTP Status 201 Created. Tạo đơn hàng thành công, số liệu tài chính tính toán chuẩn xác, mã đơn hàng được sinh ra duy nhất.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked do kiến trúc client-side SPA.


Xem chi tiết: [TC-55.md](API_Testing/TC-55.md)


---

<a id="tc-56"></a>

## Test Case: TC-56 - Kiểm tra CSDL: Xác minh mật khẩu người dùng được băm an toàn trong bảng users

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-56 |
| **Name** | Kiểm tra CSDL: Xác minh mật khẩu người dùng được băm an toàn trong bảng users |
| **Folder** | Database_SQL_Testing |
| **Component** | Users Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Security Verification |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có quyền kết nối và truy vấn CSDL quản trị hệ thống. |
| **Test Data** | SQL Query: SELECT username, password_hash, salt FROM users WHERE username = 'standard_user'; |
| **Postcondition** | Đảm bảo tuân thủ tiêu chuẩn an toàn bảo mật dữ liệu người dùng (OWASP / GDPR). |

### 1. Objective
Xác minh hệ thống không bao giờ lưu trữ mật khẩu dưới dạng văn bản thuần (Plaintext), mật khẩu phải được băm an toàn bằng thuật toán chuẩn (BCrypt / Argon2 / SHA-256).

### 2. Test Steps

1. Mở kết nối Database Client (DBeaver / MySQL Workbench).
2. Thực thi câu lệnh SQL truy vấn thông tin người dùng 'standard_user'.
3. Kiểm tra giá trị cột 'password_hash'.
4. Xác nhận giá trị không trùng với chuỗi 'secret_sauce' và có độ dài tối thiểu 60 ký tự (chuẩn hash bcrypt).

### 3. Expected Result

Mật khẩu được lưu trữ dưới dạng chuỗi băm không thể dịch ngược (ví dụ \$2b\$12\$e8...), không xuất hiện chuỗi 'secret_sauce' trong bất kỳ trường dữ liệu nào.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked do SauceDemo không cung cấp quyền kết nối direct database.


Xem chi tiết: [TC-56.md](Database_SQL_Testing/TC-56.md)


---

<a id="tc-57"></a>

## Test Case: TC-57 - Kiểm tra CSDL: Xác minh trạng thái khóa tài khoản trong bảng users đối với locked_out_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-57 |
| **Name** | Kiểm tra CSDL: Xác minh trạng thái khóa tài khoản trong bảng users đối với locked_out_user |
| **Folder** | Database_SQL_Testing |
| **Component** | Users Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Data Consistency |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có quyền truy vấn bảng 'users'. |
| **Test Data** | SQL Query: SELECT username, is_locked, account_status FROM users WHERE username = 'locked_out_user'; |
| **Postcondition** | Dữ liệu trạng thái người dùng đồng bộ. |

### 1. Objective
Xác minh bản ghi của 'locked_out_user' có cờ trạng thái 'is_locked = 1' hoặc 'status = LOCKED' trong cơ sở dữ liệu.

### 2. Test Steps

1. Kết nối vào CSDL.
2. Thực thi câu lệnh truy vấn trạng thái tài khoản 'locked_out_user'.
3. Kiểm tra giá trị trường 'is_locked' bằng 1 (True).
4. Đối chiếu với 'standard_user' có trường 'is_locked' bằng 0 (False).

### 3. Expected Result

Cơ sở dữ liệu lưu trữ chính xác trạng thái khóa của tài khoản: is_locked = 1, giải thích nguyên nhân hệ thống từ chối đăng nhập trên giao diện.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked.


Xem chi tiết: [TC-57.md](Database_SQL_Testing/TC-57.md)


---

<a id="tc-58"></a>

## Test Case: TC-58 - Kiểm tra CSDL: Xác minh tính nhất quán của bảng danh mục sản phẩm và giá niêm yết

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-58 |
| **Name** | Kiểm tra CSDL: Xác minh tính nhất quán của bảng danh mục sản phẩm và giá niêm yết |
| **Folder** | Database_SQL_Testing |
| **Component** | Product Catalog Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Data Consistency |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có quyền truy vấn bảng 'products'. |
| **Test Data** | SQL Query: SELECT product_id, name, price, stock_quantity FROM products WHERE is_active = 1 ORDER BY price ASC; |
| **Postcondition** | Dữ liệu danh mục đạt chuẩn toàn vẹn. |

### 1. Objective
Xác minh bảng 'products' chứa đầy đủ 6 sản phẩm với giá bán chính xác và số lượng tồn kho (stock) lớn hơn 0.

### 2. Test Steps

1. Thực thi câu lệnh: SELECT COUNT(*) FROM products WHERE is_active = 1;
2. Xác nhận COUNT(*) bằng 6.
3. Thực thi câu lệnh: SELECT name, price FROM products ORDER BY price ASC;
4. Đối chiếu mức giá thấp nhất là 7.99 (Onesie) và cao nhất là 49.99 (Fleece Jacket).

### 3. Expected Result

Đủ 6 sản phẩm, giá tiền khớp 100% với giao diện UI (\$7.99, \$9.99, \$15.99, \$15.99, \$29.99, \$49.99).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked.


Xem chi tiết: [TC-58.md](Database_SQL_Testing/TC-58.md)


---

<a id="tc-59"></a>

## Test Case: TC-59 - Kiểm tra CSDL: Xác minh ghi nhận bản ghi đơn hàng mới vào bảng orders sau khi thanh toán thành công

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-59 |
| **Name** | Kiểm tra CSDL: Xác minh ghi nhận bản ghi đơn hàng mới vào bảng orders sau khi thanh toán thành công |
| **Folder** | Database_SQL_Testing |
| **Component** | Orders Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Transaction Verification |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Vừa thực hiện thành công một đơn hàng trên UI bằng 'standard_user'. |
| **Test Data** | SQL Query: SELECT order_id, user_id, item_total, tax_amount, grand_total, order_status FROM orders WHERE user_id = 'standard_user' ORDER BY created_at DESC LIMIT 1; |
| **Postcondition** | Giao dịch thanh toán được lưu trữ bền vững (ACID compliance). |

### 1. Objective
Xác minh sau khi người dùng nhấn 'Finish' trên giao diện, một bản ghi mới được tạo trong bảng 'orders' với đầy đủ thông tin thanh toán và thuế.

### 2. Test Steps

1. Thực hiện thanh toán đơn hàng trên UI.
2. Mở SQL client và thực thi truy vấn lấy đơn hàng mới nhất của 'standard_user'.
3. Đối chiếu các trường 'item_total', 'tax_amount', 'grand_total' với màn hình Checkout Step 2.
4. Kiểm tra trường 'order_status' có giá trị 'COMPLETED' hoặc 'DISPATCHED'.

### 3. Expected Result

Bản ghi đơn hàng được tạo thành công, dữ liệu tài chính khớp chính xác từng xu, trạng thái đơn hàng được cập nhật hợp lệ.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked.


Xem chi tiết: [TC-59.md](Database_SQL_Testing/TC-59.md)


---

<a id="tc-60"></a>

## Test Case: TC-60 - Kiểm tra CSDL: Xác minh chi tiết các mặt hàng trong bảng order_items liên kết đúng với đơn hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-60 |
| **Name** | Kiểm tra CSDL: Xác minh chi tiết các mặt hàng trong bảng order_items liên kết đúng với đơn hàng |
| **Folder** | Database_SQL_Testing |
| **Component** | Order Items Table |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-15 |
| **TestScenarioID** | TS-32 |
| **Test Type** | Database / Relational Integrity |
| **Execution Environment** | DBeaver / MySQL Workbench / Terminal SQL Client |
| **Precondition** | Có mã 'order_id' vừa tạo từ câu lệnh TC-59. |
| **Test Data** | SQL Query: SELECT oi.item_id, oi.product_id, p.name, oi.unit_price, oi.quantity FROM order_items oi JOIN products p ON oi.product_id = p.product_id WHERE oi.order_id = :latest_order_id; |
| **Postcondition** | Toàn vẹn quan hệ giữa bảng đơn hàng và bảng chi tiết sản phẩm. |

### 1. Objective
Xác minh bảng chi tiết 'order_items' lưu đúng từng sản phẩm, số lượng và đơn giá theo khóa ngoại 'order_id'.

### 2. Test Steps

1. Lấy mã order_id từ đơn hàng mới nhất.
2. Thực thi câu lệnh truy vấn liên kết bảng order_items với products.
3. Kiểm tra số lượng dòng sản phẩm trả về khớp với số mặt hàng khách đã chọn.
4. Kiểm tra đơn giá từng món bằng với giá niêm yết tại thời điểm mua.

### 3. Expected Result

Toàn bộ các mặt hàng được liên kết chuẩn xác qua khóa ngoại (Foreign Key constraint), không có dữ liệu mồ côi (orphan records).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Trạng thái thực thi khi thực thi: Blocked.


Xem chi tiết: [TC-60.md](Database_SQL_Testing/TC-60.md)


---

<a id="tc-61"></a>

## Test Case: TC-61 - Kiểm tra phi chức năng: Đo lường thời gian phản hồi (Response Time SLA < 2.0s) khi tải trang danh mục sản phẩm

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-61 |
| **Name** | Kiểm tra phi chức năng: Đo lường thời gian phản hồi (Response Time SLA < 2.0s) khi tải trang danh mục sản phẩm |
| **Folder** | Non_Functional_Testing/Performance_Testing |
| **Component** | Performance / Response Time |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Performance Testing |
| **Execution Environment** | Chrome Desktop DevTools / Lighthouse Audit / macOS Sonoma |
| **Precondition** | Trình duyệt sạch, không có cache (Disable cache trong DevTools), kết nối mạng ổn định (Fast 3G / 4G / Broadband). |
| **Test Data** | Tài khoản: standard_user | Tiêu chuẩn: Response Time < 2000ms |
| **Postcondition** | Hệ thống đáp ứng tiêu chuẩn hiệu năng trải nghiệm người dùng. |

### 1. Objective
Xác minh hiệu năng tải trang danh mục sản phẩm '/inventory.html' đáp ứng tiêu chuẩn thời gian phản hồi dưới 2.0 giây trong điều kiện mạng tiêu chuẩn.

### 2. Test Steps

1. Mở Chrome DevTools -> tab 'Network', tích chọn 'Disable cache'.
2. Mở tab 'Lighthouse' hoặc 'Performance'.
3. Đăng nhập bằng 'standard_user' / 'secret_sauce'.
4. Ghi nhận thời gian DOMContentLoaded, Time to First Byte (TTFB), và Fully Loaded Time của trang '/inventory.html'.

### 3. Expected Result

Thời gian tải toàn bộ trang danh mục dưới 2.0 giây. Điểm hiệu năng Lighthouse đạt trên 90 điểm. Các tài nguyên tĩnh (static assets) tải nhanh chóng không bị nghẽn.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử hiệu năng phi chức năng đo lường chỉ số Web Vitals (FCP, LCP, CLS).


Xem chi tiết: [TC-61.md](Non_Functional_Testing/Performance_Testing/TC-61.md)


---

<a id="tc-62"></a>

## Test Case: TC-62 - Kiểm tra phi chức năng: Phát hiện vi phạm SLA thời gian phản hồi nghiêm trọng (>5.0s) đối với performance_glitch_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-62 |
| **Name** | Kiểm tra phi chức năng: Phát hiện vi phạm SLA thời gian phản hồi nghiêm trọng (>5.0s) đối với performance_glitch_user |
| **Folder** | Non_Functional_Testing/Performance_Testing |
| **Component** | Performance / Latency Glitch |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Performance SLA / Response Time / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Trình duyệt chưa có phiên làm việc; kết nối mạng ổn định (High-speed Broadband). |
| **Test Data** | Username: performance_glitch_user | Password: secret_sauce |
| **Postcondition** | Người dùng chuyển trang nhanh chóng. |

### 1. Objective
Xác minh thời gian từ lúc nhấn 'Login' đến khi trang danh mục hiển thị đầy đủ phải đáp ứng tiêu chuẩn hiệu năng phần mềm (Response Time SLA < 2 giây), bẫy lỗi nghẽn mạng nhân tạo.

### 2. Test Steps

1. Mở DevTools Network Tab.
2. Nhập 'performance_glitch_user' và 'secret_sauce'.
3. Nhấp 'Login' và đo lường thời gian từ lúc gửi yêu cầu đến khi sự kiện DOMContentLoaded / trang '/inventory.html' hoàn tất tải.

### 3. Expected Result

Trang danh mục tải xong hoàn toàn trong thời gian dưới 2.0 giây, mang lại trải nghiệm mượt mà không có độ trễ bất thường.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của SauceDemo: performance_glitch_user bị chèn độ trễ nhân tạo 5 giây (5000ms delay), vi phạm nghiêm trọng SLA trải nghiệm người dùng.


Xem chi tiết: [TC-62.md](Non_Functional_Testing/Performance_Testing/TC-62.md)


---

<a id="tc-63"></a>

## Test Case: TC-63 - Kiểm tra phi chức năng: Kiểm tra các cờ bảo mật của Cookie phiên làm việc (Secure, HttpOnly, SameSite)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-63 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra các cờ bảo mật của Cookie phiên làm việc (Secure, HttpOnly, SameSite) |
| **Folder** | Non_Functional_Testing/Security_Testing |
| **Component** | Security / Session Cookie |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-16 |
| **TestScenarioID** | TS-33 |
| **Test Type** | Security Testing |
| **Execution Environment** | Chrome Desktop DevTools / Application Tab |
| **Precondition** | Người dùng đăng nhập thành công vào hệ thống. |
| **Test Data** | Cookie: session-username | Kỳ vọng cờ: Secure=True, HttpOnly=True, SameSite=Lax/Strict |
| **Postcondition** | Phiên làm việc được bảo vệ chống lộ lọt cookie qua các cuộc tấn công XSS. |

### 1. Objective
Xác minh các cookie quản lý phiên làm việc như 'session-username' được thiết lập đầy đủ các thuộc tính bảo mật để chống tấn công đánh cắp cookie (Session Hijacking / XSS).

### 2. Test Steps

1. Đăng nhập bằng 'standard_user' / 'secret_sauce'.
2. Mở Chrome DevTools -> tab 'Application' -> mục 'Cookies' -> 'https://www.saucedemo.com'.
3. Kiểm tra cột 'HttpOnly': xem có dấu tích hay không.
4. Kiểm tra cột 'Secure': xem có được bật hay không.
5. Mở tab 'Console' và gõ lệnh: document.cookie để kiểm tra xem mã JavaScript có thể đọc được cookie phiên hay không.

### 3. Expected Result

Cookie phiên phải có cờ 'HttpOnly' được bật (ngăn chặn JavaScript client đọc cookie qua document.cookie) và cờ 'Secure' được bật (chỉ truyền qua HTTPS).

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Lỗ hổng bảo mật thực tế trên SauceDemo: Cookie 'session-username' hoàn toàn không có cờ HttpOnly, JavaScript client có thể đọc và sửa đổi tự do qua document.cookie.


Xem chi tiết: [TC-63.md](Non_Functional_Testing/Security_Testing/TC-63.md)


---

<a id="tc-64"></a>

## Test Case: TC-64 - Kiểm tra phi chức năng: Kiểm tra khả năng chống tấn công Cross-Site Scripting (XSS) trên form Checkout Step 1

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-64 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra khả năng chống tấn công Cross-Site Scripting (XSS) trên form Checkout Step 1 |
| **Folder** | Non_Functional_Testing/Security_Testing |
| **Component** | Security / Form Sanitization |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | Critical |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-16 |
| **TestScenarioID** | TS-33 |
| **Test Type** | Security Testing |
| **Execution Environment** | Chrome Desktop DevTools / Security Testing |
| **Precondition** | Đang ở trang '/checkout-step-one.html' với 1 sản phẩm trong giỏ. |
| **Test Data** | Payload XSS: <script>alert('XSS_VULNERABILITY')</script> hoặc <img src=x onerror=alert(1)> |
| **Postcondition** | Dữ liệu được hiển thị dưới dạng văn bản thuần an toàn. |

### 1. Objective
Xác minh các ô nhập liệu First Name, Last Name, Postal Code thực hiện làm sạch dữ liệu đầu vào (Input Sanitization), không thực thi mã JavaScript độc hại khi người dùng nhập chuỗi payload XSS.

### 2. Test Steps

1. Nhập '<script>alert("XSS")</script>' vào ô 'First Name'.
2. Nhập '<img src=x onerror=alert(1)>' vào ô 'Last Name'.
3. Nhập '12345' vào ô 'Postal Code'.
4. Nhấp nút 'Continue' và quan sát màn hình Bước 2.

### 3. Expected Result

Hệ thống mã hóa thực thể HTML (HTML entity encoding) hoặc loại bỏ thẻ độc hại. Tuyệt đối không có hộp thoại alert popup nào của mã JavaScript được thực thi trên trình duyệt.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử bảo mật hộp đen (OWASP Top 10 - Injection / Cross-Site Scripting).


Xem chi tiết: [TC-64.md](Non_Functional_Testing/Security_Testing/TC-64.md)


---

<a id="tc-65"></a>

## Test Case: TC-65 - Kiểm tra phi chức năng: Kiểm tra chống rò rỉ phiên làm việc khi sử dụng nút 'Back' của trình duyệt sau khi đăng xuất

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-65 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra chống rò rỉ phiên làm việc khi sử dụng nút 'Back' của trình duyệt sau khi đăng xuất |
| **Folder** | Non_Functional_Testing/Security_Testing |
| **Component** | Security / Session Invalidation |
| **Status** | Approved |
| **Priority** | High |
| **Severity** | High |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-16 |
| **TestScenarioID** | TS-33 |
| **Test Type** | Security / Session Management |
| **Execution Environment** | Chrome Desktop / Firefox / Safari |
| **Precondition** | Người dùng đang đăng nhập và vừa thực hiện 'Logout'. |
| **Test Data** | Tài khoản: standard_user |
| **Postcondition** | Phiên làm việc được hủy bỏ hoàn toàn cả trên server và client cache. |

### 1. Objective
Xác minh sau khi người dùng chọn 'Logout', việc nhấn nút Back trên trình duyệt không cho phép truy cập lại các thông tin nhạy cảm đã lưu trong bộ nhớ đệm (Cache Control & Session Invalidation).

### 2. Test Steps

1. Đăng nhập bằng 'standard_user' và thêm sản phẩm vào giỏ.
2. Mở Sidebar và nhấp 'Logout' để kết thúc phiên (quay về trang '/').
3. Nhấp vào nút 'Back' (Quay lại trang trước) trên thanh công cụ của trình duyệt web.
4. Quan sát phản hồi của trang web.

### 3. Expected Result

Hệ thống ngăn chặn truy cập, kiểm tra thấy không có cookie phiên hợp lệ sẽ lập tức điều hướng về trang đăng nhập với thông báo lỗi 'Epic sadface: You can only access \'/inventory.html\' when you are logged in.'. Không hiển thị trang sản phẩm từ bộ nhớ đệm.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra cơ chế Cache-Control: no-cache, no-store, must-revalidate.


Xem chi tiết: [TC-65.md](Non_Functional_Testing/Security_Testing/TC-65.md)


---

<a id="tc-66"></a>

## Test Case: TC-66 - Kiểm tra phi chức năng: Kiểm tra điều hướng tuần tự bằng bàn phím (Keyboard Tab Order & Focus Ring)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-66 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra điều hướng tuần tự bằng bàn phím (Keyboard Tab Order & Focus Ring) |
| **Folder** | Non_Functional_Testing/Accessibility_Testing |
| **Component** | Accessibility / Keyboard Navigation |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Accessibility Testing |
| **Execution Environment** | Chrome Desktop / macOS Sonoma / Keyboard Only Navigation |
| **Precondition** | Trang chủ hoặc trang đăng nhập được mở; không sử dụng chuột máy tính. |
| **Test Data** | Phím bấm: Tab, Shift+Tab, Enter, Spacebar |
| **Postcondition** | Trang web hỗ trợ tốt khả năng tiếp cận (Accessibility compliance). |

### 1. Objective
Xác minh người dùng khuyết tật hoặc người dùng chỉ sử dụng bàn phím có thể nhấn phím 'Tab' để di chuyển tuần tự qua các nút bấm, ô nhập liệu và nhấn 'Enter'/'Space' để kích hoạt hành động.

### 2. Test Steps

1. Truy cập trang đăng nhập 'https://www.saucedemo.com/'.
2. Nhấn phím 'Tab' liên tục và quan sát viền con trỏ lấy nét (Focus Ring / Outline).
3. Xác nhận thứ tự lấy nét: Ô Username -> Ô Password -> Nút Login.
4. Gõ thông tin tài khoản và nhấn phím 'Enter' tại nút Login.
5. Trên trang sản phẩm, nhấn Tab để di chuyển qua từng thẻ sản phẩm và nút 'Add to cart'.

### 3. Expected Result

Vị trí con trỏ lấy nét (focus indicator) hiển thị viền rõ ràng, thứ tự Tab di chuyển tự nhiên từ trên xuống dưới, từ trái sang phải theo tiêu chuẩn WCAG 2.1 Level AA.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử tiêu chuẩn khả năng tiếp cận WCAG 2.1 (Web Content Accessibility Guidelines).


Xem chi tiết: [TC-66.md](Non_Functional_Testing/Accessibility_Testing/TC-66.md)


---

<a id="tc-67"></a>

## Test Case: TC-67 - Kiểm tra phi chức năng: Kiểm tra tên trợ năng (Accessible Names / aria-label) và độ tương phản màu sắc

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-67 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra tên trợ năng (Accessible Names / aria-label) và độ tương phản màu sắc |
| **Folder** | Non_Functional_Testing/Accessibility_Testing |
| **Component** | Accessibility / Screen Reader |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Accessibility Testing |
| **Execution Environment** | Chrome DevTools / Lighthouse Accessibility Audit |
| **Precondition** | Đang ở trang '/inventory.html'. |
| **Test Data** | Công cụ kiểm tra: Axe DevTools / Chrome Lighthouse Accessibility Audit |
| **Postcondition** | Trang web thân thiện với người dùng trợ năng. |

### 1. Objective
Xác minh các biểu tượng icon (nút mở menu, giỏ hàng, mạng xã hội footer) có gắn thuộc tính 'aria-label' hoặc 'title' để trình đọc màn hình (Screen Reader) có thể đọc được cho người khiếm thị.

### 2. Test Steps

1. Mở Chrome DevTools -> Inspect phần tử biểu tượng giỏ hàng và nút hamburger menu.
2. Kiểm tra sự hiện diện của thuộc tính 'aria-label' hoặc 'title' hoặc văn bản ẩn (screen-reader text).
3. Chạy Lighthouse Audit mục 'Accessibility'.
4. Kiểm tra tỷ lệ tương phản màu sắc (Color Contrast Ratio >= 4.5:1) giữa màu chữ và màu nền.

### 3. Expected Result

Điểm trợ năng Lighthouse đạt trên 90 điểm. Các nút dạng icon có nhãn mô tả rõ ràng, tỷ lệ tương phản màu sắc đạt chuẩn WCAG 2.1 AA.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Đảm bảo tuân thủ tiêu chuẩn tiếp cận phổ quát (Universal Accessibility).


Xem chi tiết: [TC-67.md](Non_Functional_Testing/Accessibility_Testing/TC-67.md)


---

<a id="tc-68"></a>

## Test Case: TC-68 - Kiểm tra phi chức năng: Tính nhất quán của phản hồi trực quan trên bộ đếm giỏ hàng

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-68 |
| **Name** | Kiểm tra phi chức năng: Tính nhất quán của phản hồi trực quan trên bộ đếm giỏ hàng |
| **Folder** | Non_Functional_Testing/Usability_Testing |
| **Component** | Usability / Visual Feedback |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Usability Testing |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma |
| **Precondition** | Đang ở trang '/inventory.html'. |
| **Test Data** | Sản phẩm: Sauce Labs Backpack |
| **Postcondition** | Trải nghiệm người dùng đạt độ hài lòng cao. |

### 1. Objective
Xác minh khi thêm hoặc xóa sản phẩm, biểu tượng giỏ hàng và huy hiệu số lượng cập nhật phản hồi trực quan ngay lập tức, không gây nhầm lẫn cho người dùng.

### 2. Test Steps

1. Nhấp 'Add to cart' tại sản phẩm Balo.
2. Quan sát sự thay đổi màu sắc và chữ trên nút (từ chữ đen viền xám sang chữ đỏ viền đỏ 'Remove').
3. Quan sát huy hiệu đỏ trên icon giỏ hàng ở thanh header.
4. Nhấp 'Remove' và quan sát sự biến mất tức thì của huy hiệu mà không giật màn hình.

### 3. Expected Result

Phản hồi thị giác diễn ra mượt mà tức thì (<100ms), người dùng nhận biết rõ ràng sản phẩm đã được thêm/xóa khỏi giỏ hàng mà không cần kiểm tra lại.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm tra nguyên lý phản hồi tức thời của Jakob Nielsen (Visibility of system status).


Xem chi tiết: [TC-68.md](Non_Functional_Testing/Usability_Testing/TC-68.md)


---

<a id="tc-69"></a>

## Test Case: TC-69 - Kiểm tra phi chức năng: Phát hiện lỗi căn chỉnh layout và vị trí các thành phần trên thanh Header khi đăng nhập bằng visual_user

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-69 |
| **Name** | Kiểm tra phi chức năng: Phát hiện lỗi căn chỉnh layout và vị trí các thành phần trên thanh Header khi đăng nhập bằng visual_user |
| **Folder** | Non_Functional_Testing/Usability_Testing |
| **Component** | UI Layout / Header Alignment |
| **Status** | Approved |
| **Priority** | Low |
| **Severity** | Low |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Visual Regression / UI Layout / Defect Detection |
| **Execution Environment** | Chrome Desktop (v124+) / macOS Sonoma / Screen 1920x1080 |
| **Precondition** | Đang ở trang '/inventory.html'. |
| **Test Data** | Username: visual_user | Password: secret_sauce |
| **Postcondition** | Giao diện trực quan đẹp mắt, đúng chuẩn thiết kế. |

### 1. Objective
Xác minh tính nhất quán của giao diện người dùng (Pixel-perfect & Visual Alignment), phát hiện lỗi biểu tượng giỏ hàng và menu bị xô lệch tọa độ so với thiết kế chuẩn.

### 2. Test Steps

1. Đăng nhập bằng 'visual_user' / 'secret_sauce'.
2. Kiểm tra thanh Header phía trên cùng của trang '/inventory.html'.
3. Đối chiếu vị trí, margin, padding của biểu tượng giỏ hàng và nút menu so với giao diện chuẩn của 'standard_user'.

### 3. Expected Result

Toàn bộ các biểu tượng căn chỉnh ngay ngắn, đúng lề phải và lề trái theo CSS Grid/Flexbox chuẩn. Không có phần tử nào bị thụt lề, lệch vị trí hoặc chèn đè lên nhau.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Bug cố tình của visual_user: Biểu tượng giỏ hàng bị dịch chuyển vị trí bất thường và nút bấm bị áp dụng CSS class sai lệch.


Xem chi tiết: [TC-69.md](Non_Functional_Testing/Usability_Testing/TC-69.md)


---

<a id="tc-70"></a>

## Test Case: TC-70 - Kiểm tra phi chức năng: Kiểm tra tính tương thích hiển thị Responsive UI trên màn hình Mobile Viewport

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-70 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra tính tương thích hiển thị Responsive UI trên màn hình Mobile Viewport |
| **Folder** | Non_Functional_Testing/Compatibility_Testing |
| **Component** | Compatibility / Mobile Responsive |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Compatibility / Responsive Testing |
| **Execution Environment** | Chrome Device Mode / Emulated Mobile Viewports (iOS & Android) |
| **Precondition** | Mở trang web trên trình duyệt Chrome. |
| **Test Data** | Thiết bị mô phỏng: iPhone 14 / Samsung Galaxy S20 (Viewport 375x812 và 412x915) |
| **Postcondition** | Trải nghiệm mượt mà trên nền tảng di động. |

### 1. Objective
Xác minh bố cục giao diện trang danh mục sản phẩm và giỏ hàng tự động co giãn linh hoạt, không bị vỡ khung hình hoặc mất nút bấm khi xem trên màn hình điện thoại di động.

### 2. Test Steps

1. Bật chế độ mô phỏng thiết bị di động (Toggle Device Toolbar - Ctrl+Shift+M).
2. Chọn thiết bị 'iPhone 14' (độ phân giải 390x844 px).
3. Đăng nhập và quan sát trang danh mục sản phẩm '/inventory.html'.
4. Kiểm tra lưới sản phẩm chuyển từ 2 cột sang 1 cột duy nhất (Single Column Layout).
5. Kiểm tra biểu tượng giỏ hàng, menu sidebar và các nút bấm 'Add to cart' có kích thước vùng chạm (Touch Target > 44x44 px) phù hợp cho ngón tay hay không.

### 3. Expected Result

Giao diện hiển thị cân đối, không xuất hiện thanh cuộn ngang (Horizontal scrollbar). Chữ đọc rõ ràng không bị đè chữ, các nút bấm bấm dễ dàng trên màn hình cảm ứng.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử tính tương thích đa thiết bị (Cross-device Responsive Testing).


Xem chi tiết: [TC-70.md](Non_Functional_Testing/Compatibility_Testing/TC-70.md)


---

<a id="tc-71"></a>

## Test Case: TC-71 - Kiểm tra phi chức năng: Kiểm tra khả năng tương thích hiển thị và hoạt động trên nhiều trình duyệt (Cross-Browser)

| **Field** | **Value** |
|:---|:---|
| **Test Case ID** | TC-71 |
| **Name** | Kiểm tra phi chức năng: Kiểm tra khả năng tương thích hiển thị và hoạt động trên nhiều trình duyệt (Cross-Browser) |
| **Folder** | Non_Functional_Testing/Compatibility_Testing |
| **Component** | Compatibility / Cross-Browser |
| **Status** | Approved |
| **Priority** | Medium |
| **Severity** | Medium |
| **Owner** | QA - Khổng Đức Anh |
| **UserStoryID** | US-17 |
| **TestScenarioID** | TS-34 |
| **Test Type** | Compatibility / Cross-Browser |
| **Execution Environment** | Multi-browser: Chrome / Firefox / Safari on macOS Sonoma |
| **Precondition** | Cài đặt sẵn các trình duyệt Chrome, Firefox, Safari trên máy trạm. |
| **Test Data** | Trình duyệt: Chrome v124+, Firefox v125+, Safari v17+ |
| **Postcondition** | Ứng dụng tương thích hoàn hảo với các trình duyệt thông dụng. |

### 1. Objective
Xác minh quy trình đăng nhập, thêm hàng và thanh toán hoạt động ổn định và nhất quán trên các trình duyệt phổ biến (Google Chrome, Mozilla Firefox, Apple Safari).

### 2. Test Steps

1. Mở lần lượt từng trình duyệt: Google Chrome, Mozilla Firefox, Apple Safari.
2. Truy cập 'https://www.saucedemo.com/' trên từng trình duyệt.
3. Đăng nhập bằng 'standard_user'.
4. Thêm sản phẩm vào giỏ, kiểm tra giao diện giỏ hàng và form checkout.

### 3. Expected Result

Giao diện hiển thị nhất quán trên cả 3 trình duyệt; các hiệu ứng chuyển động, nút bấm và form nhập liệu hoạt động đồng bộ không có sự sai khác về tính năng.

### 4. Execution Tracking

- **Actual Result:** -
- **Execution Date & Time:** -
- **Linked Bug / Defect ID:** -
- **Comments / Notes:** Kiểm thử khả năng tương thích trình duyệt (Cross-browser Compatibility).


Xem chi tiết: [TC-71.md](Non_Functional_Testing/Compatibility_Testing/TC-71.md)


---
