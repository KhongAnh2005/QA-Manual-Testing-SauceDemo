# Test Plan Document: SauceDemo E-Commerce Web Application

**Document ID:** TP-SAUCEDEMO-01  
**Target Application:** SauceDemo ([https://www.saucedemo.com/](https://www.saucedemo.com/))  
**Standard Compliance:** ISO/IEC/IEEE 29119 & IEEE 829 Software Test Documentation Standard  
**Author / Owner:** QA - Khổng Đức Anh  
**Version:** 1.0 (Baseline Phase 1)  
**Date:** October 2026  
**Status:** Approved (Ready for Test Execution)  

---

## Table of Contents

- [1. Document Control & Revision History](#tp-section-1)
- [2. Introduction & Purpose](#tp-section-2)
- [3. Test Scope](#tp-section-3)
  - [3.1 In-Scope](#tp-section-3-1)
  - [3.2 Out-of-Scope](#tp-section-3-2)
- [4. Test Strategy & Methodology](#tp-section-4)
  - [4.1 Methodology & Test Design Techniques](#tp-section-4-1)
  - [4.2 Test Levels](#tp-section-4-2)
  - [4.3 Test Types](#tp-section-4-3)
- [5. Test Environment & Configurations](#tp-section-5)
- [6. Entry & Exit Criteria](#tp-section-6)
- [7. RACI Matrix & Responsibilities](#tp-section-7)
- [8. Defect Management & Severity vs Priority Guidelines](#tp-section-8)
- [9. Test Deliverables](#tp-section-9)
- [10. Risks, Contingencies & Mitigation](#tp-section-10)
- [11. Approvals & Sign-Off](#tp-section-11)

---

<a id="tp-section-1"></a>
## 1. Document Control & Revision History

| **Version** | **Date** | **Author** | **Description of Changes** | **Approved By** |
|:---|:---|:---|:---|:---|
| 1.0 | 14/10/2026 | QA - Khổng Đức Anh | Initial Release of Master Test Plan for SauceDemo | QA Lead / Stakeholders |

---

<a id="tp-section-2"></a>
## 2. Introduction & Purpose

### 2.1 Background
SauceDemo (Swag Labs) là ứng dụng web thương mại điện tử chuyên biệt mô phỏng một cửa hàng trực tuyến bán các vật phẩm lưu niệm công nghệ. Ứng dụng cung cấp các tính năng cốt lõi của một hệ sinh thái e-commerce hiện đại gồm: Xác thực và quản lý phiên, Danh mục hàng hóa và sắp xếp sản phẩm, Quản lý giỏ hàng, Quy trình thanh toán nhiều bước (Checkout Step 1, Step 2, Step 3), Menu điều hướng mở rộng, và Quản lý trạng thái ứng dụng.

### 2.2 Purpose
Kế hoạch kiểm thử này đóng vai trò là kim chỉ nam chiến lược và quy trình kiểm thử toàn diện cho hệ thống SauceDemo nhằm:
1. Xác định phạm vi kiểm thử chi tiết (In-scope và Out-of-scope).
2. Thiết lập phương pháp tiếp cận kiểm thử (Test Methodology), các cấp độ kiểm thử (Test Levels) và các loại hình kiểm thử (Test Types).
3. Đảm bảo 100% các yêu cầu nghiệp vụ và Acceptance Criteria (AC) trong User Stories được bao phủ bởi các Test Scenarios và Test Cases.
4. Chuẩn bị kế hoạch kiểm thử thăm dò (Exploratory Testing Plan) theo các khung Heuristics và SFDIPOT.
5. Thiết lập tiêu chí bắt đầu (Entry Criteria), tiêu chí dừng/kết thúc (Exit Criteria), quy trình quản lý lỗi (Defect Management) và ma trận phân loại Mức độ nghiêm trọng (Severity) vs Mức độ ưu tiên (Priority).

---

<a id="tp-section-3"></a>
## 3. Test Scope

<a id="tp-section-3-1"></a>
### 3.1 In-Scope (Thuộc phạm vi kiểm thử)
- **Module Xác thực & Phiên (Authentication & Session):** Đăng nhập với các persona khác nhau (standard, locked_out, problem, performance_glitch, error, visual), xác thực lỗi bỏ trống, sai tài khoản/mật khẩu, kiểm soát cookie phiên `session-username`, bảo vệ URL nội bộ `/inventory.html`, và chức năng đăng xuất.
- **Module Danh mục Sản phẩm (Product Catalog):** Hiển thị danh sách 6 sản phẩm, thông tin hình ảnh, tên, giá bán định dạng `\$XX.YY`, trang chi tiết sản phẩm và 4 bộ lọc sắp xếp (A-Z, Z-A, Giá thấp đến cao, Giá cao đến thấp).
- **Module Giỏ hàng (Shopping Cart):** Thao tác thêm/xóa sản phẩm từ trang danh mục và trang chi tiết, bộ đếm huy hiệu giỏ hàng, kiểm tra trang `/cart.html`, duy trì trạng thái giỏ hàng khi làm mới trang (F5) hoặc chuyển hướng.
- **Module Quy trình Thanh toán (Checkout Workflow):**
  - **Step 1 - Information:** Xác thực form nhập liệu (First Name, Last Name, Postal Code), kiểm tra trường bắt buộc và xử lý mã bưu điện.
  - **Step 2 - Overview:** Kiểm tra hiển thị mặt hàng, mã thanh toán, đơn vị giao hàng, tính toán tài chính (Item Total, Thuế suất 8% làm tròn, Tổng cộng Grand Total).
  - **Step 3 - Complete:** Xác nhận hoàn tất đơn hàng, hiển thị thông điệp thành công, làm sạch giỏ hàng và nút quay về trang chủ.
- **Module Sidebar & Quản lý Trạng thái:** Menu trượt (All Items, About điều hướng ngoài, Logout, Reset App State làm mới giỏ hàng và các nút bấm).
- **Luồng nghiệp vụ liên Module (End-to-End E-Commerce Flow):** Chu trình hoàn chỉnh xuyên suốt từ Đăng nhập ➔ Lọc hàng ➔ Thêm giỏ hàng ➔ Thanh toán ➔ Hoàn tất ➔ Đăng xuất.

<a id="tp-section-3-2"></a>
### 3.2 Out-of-Scope (Nằm ngoài phạm vi kiểm thử)
- Kiểm thử hiệu năng tải chịu tải cao (Stress Testing / Load Testing với hàng ngàn người dùng đồng thời).
- Kiểm thử bảo mật chuyên sâu mã nguồn backend hoặc lỗ hổng hạ tầng máy chủ của bên thứ ba (Sauce Labs infrastructure).
- Tích hợp cổng thanh toán ngân hàng thực tế (Payment Gateway Integration) do ứng dụng là môi trường giả lập (Sandbox).

---

<a id="tp-section-4"></a>
## 4. Test Strategy & Methodology

<a id="tp-section-4-1"></a>
### 4.1 Methodology & Test Design Techniques
Áp dụng kết hợp giữa **Scripted Testing (Kiểm thử theo kịch bản chuẩn hóa)** và **Exploratory Testing (Kiểm thử thăm dò theo Heuristics & Charters)**:
1. **Phân vùng tương đương (Equivalence Partitioning - EP):** Phân chia dữ liệu đầu vào thành các lớp hợp lệ và không hợp lệ (ví dụ: các định dạng mã bưu chính, độ dài ký tự form thanh toán, tài khoản đăng nhập).
2. **Phân tích giá trị biên (Boundary Value Analysis - BVA):** Kiểm tra các điểm biên của hệ thống (ví dụ: giỏ hàng từ 1 về 0 sản phẩm, giỏ hàng chứa tối đa 6 sản phẩm, tính toán làm tròn số thập phân của thuế 8%).
3. **Đoán lỗi (Error Guessing):** Dựa trên kinh nghiệm thực tế để thử nghiệm các trường hợp bất thường như spam click nút thanh toán, tải lại trang liên tục giữa quy trình checkout.

<a id="tp-section-4-2"></a>
### 4.2 Test Levels (Các cấp độ kiểm thử)
- **Component / Functional Testing:** Kiểm thử độc lập từng chức năng đơn lẻ (ví dụ: nút Add to Cart, bộ lọc sắp xếp giá).
- **Integration Testing:** Kiểm thử sự liên kết dữ liệu giữa các module (ví dụ: Thêm hàng ở trang Inventory hiển thị đúng trong Cart; Thay đổi trong Cart cập nhật đúng tại Checkout Step 2).
- **System / End-to-End Testing:** Kiểm thử chu trình nghiệp vụ trọn vẹn của người dùng cuối.

<a id="tp-section-4-3"></a>
### 4.3 Test Types (Các loại hình kiểm thử)
- **Smoke Testing:** Bộ kiểm thử kiểm tra nhanh các chức năng cốt lõi (Đăng nhập, Thêm giỏ hàng, Thanh toán cơ bản).
- **Functional Testing:** Kiểm thử chi tiết từng chức năng nghiệp vụ theo AC.
- **Negative Testing:** Kiểm thử các tình huống dữ liệu sai, vi phạm quy tắc để đảm bảo hệ thống phản hồi lỗi an toàn và thân thiện.
- **UI/UX Testing:** Kiểm tra tính nhất quán của giao diện, hình ảnh hiển thị, căn chỉnh và phản hồi của các nút bấm.

---

<a id="tp-section-5"></a>
## 5. Test Environment & Configurations

| **Thuộc Tính** | **Chi Tiết Môi Trường** |
|:---|:---|
| **URL Kiểm Thử** | [https://www.saucedemo.com/](https://www.saucedemo.com/) |
| **Trình Duyệt Chính** | Google Chrome Desktop (Phiên bản mới nhất v124+) |
| **Trình Duyệt Phụ** | Apple Safari (macOS), Mozilla Firefox |
| **Hệ Điều Hành** | macOS Sonoma / Windows 11 |
| **Độ Phân Giải Chuẩn** | Full HD (1920x1080) và Responsive Tablet/Mobile Viewport |
| **Công Cụ Quản Lý** | Jira Kanban Board & Zephyr Scale / Squad |

---

<a id="tp-section-6"></a>
## 6. Entry & Exit Criteria

### 6.1 Entry Criteria (Tiêu chí bắt đầu kiểm thử)
- Tài liệu Requirement Document (User Stories & AC) đã được phê duyệt.
- Bộ kịch bản kiểm thử (Test Scenarios) và ca kiểm thử (Test Cases) đã hoàn thiện và đạt trạng thái `Approved`.
- Môi trường kiểm thử `https://www.saucedemo.com/` hoạt động ổn định, có thể truy cập được.

### 6.2 Exit Criteria (Tiêu chí kết thúc kiểm thử)
- 100% Test Cases theo kế hoạch đã được thực thi và ghi nhận kết quả.
- Tỷ lệ Pass đạt tối thiểu **95%** đối với các Test Cases chức năng thông thường.
- **0 lỗi nghiêm trọng (Blocker/Critical)** còn tồn đọng chưa được giải quyết hoặc chưa có giải pháp thay thế.
- Toàn bộ Bug phát hiện được mô tả chi tiết, phân loại Severity/Priority và có bằng chứng (Screenshots/Logs) đầy đủ.
- Báo cáo tổng kết kiểm thử (Test Summary Report) được hoàn thiện và ký duyệt.

---

<a id="tp-section-7"></a>
## 7. RACI Matrix & Responsibilities

| **Vai Trò** | **Người Đảm Nhận** | **Trách Nhiệm Chính** |
|:---|:---|:---|
| **QA Manual Tester** | **QA - Khổng Đức Anh** | Chịu trách nhiệm chính (Responsible) trong việc phân tích User Stories, thiết kế Test Cases, thực thi kiểm thử, thực hiện Exploratory Testing, báo cáo lỗi và lập ma trận RTM. |
| **QA Lead / PM** | Stakeholders | Tham vấn (Consulted) và Phê duyệt (Accountable) Kế hoạch kiểm thử, Báo cáo kiểm thử và Tiêu chí nghiệm thu sản phẩm. |

---

<a id="tp-section-8"></a>
## 8. Defect Management & Severity vs Priority Guidelines

- **Severity (Technical Impact):**
  - **Critical:** Lỗi làm sập hệ thống, chặn hoàn toàn quy trình nghiệp vụ chính (không thể đăng nhập, không thể thanh toán, vỡ tính toán tài chính).
  - **High:** Lỗi chức năng nghiêm trọng nhưng có cách xử lý tạm thời (workaround).
  - **Medium:** Lỗi chức năng không ảnh hưởng đến luồng chính (lỗi sắp xếp, lỗi hiển thị ảnh, thông báo lỗi thiếu thân thiện).
  - **Low:** Lỗi hiển thị giao diện, sai lệch chính tả nhỏ, thẩm mỹ.
- **Priority (Business Urgency):**
  - **High:** Cần khắc phục ngay trong đợt phát hành hiện tại.
  - **Medium:** Cần khắc phục trong các đợt phát hành định kỳ tiếp theo.
  - **Low:** Đưa vào backlog, xử lý khi có thời gian.

---

<a id="tp-section-9"></a>
## 9. Test Deliverables

1. **Epics/ Folder:** 6 Epics độc lập định dạng Markdown và CSV sẵn sàng nhập vào Jira.
2. **00_Epics_Document.md & .csv:** Bảng đặc tả tổng hợp 6 Epics và hướng dẫn import Jira.
3. **Requirements/ Folder:** 13 User Stories độc lập phân chia theo từng thư mục Epic.
4. **01_Requirement_Document_User_Stories.md & .csv:** Bảng đặc tả tổng hợp 13 User Stories và AC.
5. **02_Test_Plan_Document.md:** Kế hoạch kiểm thử tổng thể chuẩn quốc tế.
6. **Test_Scenarios/ Folder:** 30 Test Scenarios độc lập phân chia theo từng thư mục Epic.
7. **03_Test_Scenarios_Document.md & .csv:** Danh sách tổng hợp 30 Test Scenarios phân loại Happy Path & Negative Path.
8. **Test_Cases/ Folder:** 42 Test Cases độc lập theo cấu trúc thư viện Zephyr.
9. **04_Test_Cases_Document.md & .csv:** Bộ 42 Test Cases chi tiết theo chuẩn Zephyr và QA Portfolio.
10. **05_Exploratory_Test_Plan.md:** Kế hoạch kiểm thử thăm dò gồm 6 Charters và chiến lược Heuristics.
11. **06_Requirement_Traceability_Matrix_RTM.md & .csv:** Ma trận truy xuất nguồn gốc hai chiều đạt 100% độ bao phủ.

---

<a id="tp-section-10"></a>
## 10. Risks, Contingencies & Mitigation

| **Potential Risk** | **Likelihood & Impact** | **Mitigation Strategy** |
|:---|:---:|:---|
| Môi trường SauceDemo bị gián đoạn mạng bất ngờ | Thấp / Cao | Lưu trữ sẵn các ảnh chụp màn hình baseline; sử dụng các tài khoản persona chuyên biệt. |
| Tài khoản performance_glitch_user gây thời gian tải lâu | Trung bình / Thấp | Đặt timebox hợp lý và kiên nhẫn chờ tải trang, không tải lại vội vã để tránh sai lệch. |
| Thiếu tài liệu đặc tả API backend chính thức | Trung bình / Trung bình | Tập trung sâu vào giao diện người dùng (Black-box Manual Testing) và kiểm tra kỹ console logs. |

---

<a id="tp-section-11"></a>
## 11. Approvals & Sign-Off

**Prepared By:** QA - Khổng Đức Anh — Date: 14/10/2026  
**Reviewed & Approved By:** QA Lead — Date: 14/10/2026  
