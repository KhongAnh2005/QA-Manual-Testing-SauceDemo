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
| **Total Epics** | 6 | 100% |
| **Total User Stories** | 13 | 100% Covered |
| **Total Test Scenarios** | 30 | 100% Mapped |
| **Total Test Cases** | 42 | 100% Designed |
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
| EPIC-01 | **US-02** | TS-03 | **TC-05** | Kiểm tra từ chối đăng nhập khi nhập tài khoản hoặc mật khẩu không đúng | High | Approved |
| EPIC-01 | **US-02** | TS-04 | **TC-06** | Kiểm tra chặn đăng nhập đối với tài khoản đã bị khóa (locked_out_user) | High | Approved |
| EPIC-01 | **US-02** | TS-02 | **TC-07** | Kiểm tra đóng thông báo lỗi đăng nhập bằng nút biểu tượng 'X' | Low | Approved |
| EPIC-01 | **US-03** | TS-05 | **TC-08** | Kiểm tra đăng xuất tài khoản thành công qua menu Sidebar | High | Approved |
| EPIC-01 | **US-03** | TS-05 | **TC-09** | Kiểm tra chặn truy cập trực tiếp URL nội bộ (/inventory.html) khi chưa đăng nhập | High | Approved |
| EPIC-02 | **US-04** | TS-06 | **TC-10** | Kiểm tra hiển thị đầy đủ 6 sản phẩm kèm tên, mô tả và giá bán | High | Approved |
| EPIC-02 | **US-04** | TS-07 | **TC-11** | Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào tên sản phẩm và quay lại danh mục | High | Approved |
| EPIC-02 | **US-04** | TS-07 | **TC-12** | Kiểm tra mở trang chi tiết sản phẩm bằng cách nhấp vào hình ảnh sản phẩm | Medium | Approved |
| EPIC-02 | **US-05** | TS-08 | **TC-13** | Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái tăng dần (A to Z) | Medium | Approved |
| EPIC-02 | **US-05** | TS-08 | **TC-14** | Kiểm tra sắp xếp sản phẩm theo tên theo thứ tự bảng chữ cái giảm dần (Z to A) | Medium | Approved |
| EPIC-02 | **US-05** | TS-09 | **TC-15** | Kiểm tra sắp xếp sản phẩm theo giá số học tăng dần (Price low to high) | High | Approved |
| EPIC-02 | **US-05** | TS-09 | **TC-16** | Kiểm tra sắp xếp sản phẩm theo giá số học giảm dần (Price high to low) | High | Approved |
| EPIC-03 | **US-06** | TS-11 | **TC-17** | Kiểm tra nhấp 'Add to cart' đổi nút thành 'Remove' và hiện huy hiệu giỏ hàng '1' | High | Approved |
| EPIC-03 | **US-06** | TS-11 | **TC-18** | Kiểm tra thêm nhiều sản phẩm làm tăng dần số lượng trên huy hiệu giỏ hàng | High | Approved |
| EPIC-03 | **US-06** | TS-11 | **TC-19** | Kiểm tra thêm sản phẩm vào giỏ hàng từ trang chi tiết sản phẩm | High | Approved |
| EPIC-03 | **US-07** | TS-12 | **TC-20** | Kiểm tra xóa sản phẩm ngay tại trang danh mục làm giảm số lượng trên huy hiệu giỏ | High | Approved |
| EPIC-03 | **US-07** | TS-12 | **TC-21** | Kiểm tra xóa sản phẩm duy nhất còn lại làm biến mất hoàn toàn huy hiệu giỏ hàng (Biên 1 về 0) | High | Approved |
| EPIC-03 | **US-07** | TS-14 | **TC-23** | Kiểm tra xóa sản phẩm trực tiếp từ bên trong trang giỏ hàng | High | Approved |
| EPIC-03 | **US-08** | TS-13 | **TC-22** | Kiểm tra trang giỏ hàng (/cart.html) hiển thị đúng sản phẩm, số lượng 1 và đơn giá | High | Approved |
| EPIC-03 | **US-08** | TS-13 | **TC-24** | Kiểm tra nút 'Continue Shopping' đưa người dùng quay lại danh mục và giữ nguyên giỏ hàng | Medium | Approved |
| EPIC-03 | **US-08** | TS-15 | **TC-25** | Kiểm tra dữ liệu giỏ hàng vẫn giữ nguyên khi tải lại trang (F5) hoặc chuyển trang | High | Approved |
| EPIC-04 | **US-09** | TS-16 | **TC-26** | Kiểm tra nút 'Checkout' trên giỏ hàng chuyển sang trang thanh toán Bước 1 | High | Approved |
| EPIC-04 | **US-09** | TS-17 | **TC-27** | Kiểm tra thông báo lỗi khi để trống toàn bộ thông tin tại Checkout Bước 1 | High | Approved |
| EPIC-04 | **US-09** | TS-17 | **TC-28** | Kiểm tra thông báo lỗi khi nhập First Name nhưng để trống Last Name | High | Approved |
| EPIC-04 | **US-09** | TS-17 | **TC-29** | Kiểm tra thông báo lỗi khi nhập First Name, Last Name nhưng để trống Postal Code | High | Approved |
| EPIC-04 | **US-09** | TS-18 | **TC-30** | Kiểm tra xử lý các định dạng mã bưu điện đặc biệt và quốc tế (BVA & EP) | Medium | Approved |
| EPIC-04 | **US-09** | TS-19 | **TC-31** | Kiểm tra nút 'Cancel' tại Bước 1 quay lại giỏ hàng và giữ nguyên các sản phẩm | Medium | Approved |
| EPIC-04 | **US-09** | TS-16 | **TC-32** | Kiểm tra nhập thông tin hợp lệ tại Bước 1 chuyển sang màn hình Bước 2 | High | Approved |
| EPIC-04 | **US-10** | TS-20 | **TC-33** | Kiểm tra màn hình Bước 2 hiển thị đúng sản phẩm, thông tin thanh toán và giao hàng | High | Approved |
| EPIC-04 | **US-10** | TS-20 | **TC-34** | Kiểm tra tính toán chính xác Item Total, Tax (8%) và Grand Total tại Checkout Bước 2 | High | Approved |
| EPIC-04 | **US-10** | TS-21 | **TC-35** | Kiểm tra nút 'Cancel' tại Bước 2 đưa người dùng về trang danh mục và giữ nguyên giỏ hàng | Medium | Approved |
| EPIC-04 | **US-11** | TS-22 | **TC-36** | Kiểm tra nhấp 'Finish' tại Bước 2 hoàn tất đơn hàng và hiển thị thông điệp thành công | High | Approved |
| EPIC-04 | **US-11** | TS-22 | **TC-37** | Kiểm tra làm mới và xóa huy hiệu giỏ hàng sau khi hoàn tất đặt hàng | High | Approved |
| EPIC-04 | **US-11** | TS-22 | **TC-38** | Kiểm tra nút 'Back Home' trên màn hình hoàn tất đưa người dùng về lại trang danh mục | Medium | Approved |
| EPIC-05 | **US-12** | TS-24 | **TC-39** | Kiểm tra mở menu Sidebar bằng biểu tượng hamburger và đóng bằng nút 'X' | Medium | Approved |
| EPIC-05 | **US-12** | TS-27 | **TC-40** | Kiểm tra chức năng 'Reset App State' xóa sạch giỏ hàng và đặt lại các nút về 'Add to cart' | High | Approved |
| EPIC-05 | **US-12** | TS-26 | **TC-41** | Kiểm tra liên kết 'About' trong Sidebar điều hướng ra website chính thức của Sauce Labs | Low | Approved |
| EPIC-06 | **US-13** | TS-28 | **TC-42** | Kiểm tra toàn diện quy trình mua sắm End-to-End từ đăng nhập đến thanh toán và đăng xuất | High | Approved |

---

<a id="rtm-section-4"></a>
## 4. Traceability Integrity Verification

> **Quality Verification:** Tất cả 13 User Stories từ `US-01` đến `US-13` đều đã được liên kết trực tiếp với các Test Scenarios (bao gồm cả Happy Path và Negative Path) và 42 Test Cases chi tiết. Không có yêu cầu nào bị bỏ sót (**Zero Coverage Gap**).
