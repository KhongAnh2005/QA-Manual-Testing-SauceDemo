# QA Manual Testing Portfolio: SauceDemo E-Commerce Web Application

![QA Role](https://img.shields.io/badge/QA_Role-Manual_Tester-brightgreen)
![Author](https://img.shields.io/badge/Author-QA_Kh%E1%BB%95ng_%C4%90%E1%BB%A9c_Anh-blue)
![Domain](https://img.shields.io/badge/Domain-E--Commerce_Web-orange)
![STLC](https://img.shields.io/badge/STLC-Full_Cycle_Compliant-purple)
![Coverage](https://img.shields.io/badge/Requirement_Coverage-100%25-success)
![Designed](https://img.shields.io/badge/Test_Cases_Designed-71_TCs-brightgreen)
![Executed](https://img.shields.io/badge/Test_Cases_Executed-61_TCs-blue)
![Defects](https://img.shields.io/badge/Defects_Found-10_Bugs_Logged-red)

Dự án kiểm thử phần mềm thủ công (QA Manual Testing) toàn diện trên nền tảng thương mại điện tử [SauceDemo](https://www.saucedemo.com/).

Dự án đóng vai trò là một tài liệu dự án chuyên nghiệp (Project Landing Page), thể hiện trọn vẹn năng lực thực thi chu trình kiểm thử phần mềm chuẩn mực (STLC): từ tiếp nhận phân tích yêu cầu, thiết lập kế hoạch kiểm thử, thiết kế kịch bản và ca kiểm thử, xây dựng ma trận truy xuất nguồn gốc (RTM), thực thi kiểm thử thực tế, quản lý lỗi theo nguyên tắc Rule of 3, trực quan hóa chất lượng và xây dựng báo cáo tổng kết phục vụ quyết định phát hành.

---

## Mục Lục

- [01. Project Title & Overview](#01-project-title--overview)
- [02. Objectives & Scope](#02-objectives--scope)
- [03. Testing Approach, Tools & STLC Process](#03-testing-approach-tools--stlc-process)
- [04. Repository Structure & Deliverables](#04-repository-structure--deliverables)
- [05. Test Results & Metrics](#05-test-results--metrics)
- [06. Key Learnings, Limitations & Disclaimer](#06-key-learnings-limitations--disclaimer)

---

<a id="01-project-title--overview"></a>
## 01. Project Title & Overview

- **Tên dự án:** SauceDemo E-Commerce Web Application Testing.
- **Hệ thống mục tiêu:** Ứng dụng web thương mại điện tử [SauceDemo](https://www.saucedemo.com/) do Sauce Labs phát triển nhằm mô phỏng luồng mua sắm trực tuyến thực tế kèm các kịch bản ngoại lệ giả lập.
- **Vai trò đảm nhiệm:** QA Manual Tester (Khổng Đức Anh) — Chịu trách nhiệm độc lập 100% toàn bộ các hoạt động đảm bảo chất lượng phần mềm trong suốt vòng đời dự án.
- **Mục đích Portfolio:**
  - Chứng minh kỹ năng thực tế của một Manual Tester trong việc phân tích tài liệu đặc tả, bóc tách kịch bản kiểm thử và thiết kế ca kiểm thử theo tiêu chuẩn.
  - Thể hiện tư duy kiểm thử dựa trên rủi ro (Risk-Based Testing), kỹ thuật đoán lỗi (Error Guessing) và kiểm thử thăm dò (Exploratory Testing).
  - Cung cấp bộ tài liệu bàn giao hoàn chỉnh, sẵn sàng tích hợp vào hệ thống quản lý kiểm thử doanh nghiệp theo tiêu chuẩn chuyên nghiệp.

---

<a id="02-objectives--scope"></a>
## 02. Objectives & Scope

### Testing Objectives

1. Xác minh tính đúng đắn và độ tin cậy của các luồng nghiệp vụ cốt lõi: Xác thực tài khoản, duyệt danh mục hàng hóa, quản lý giỏ hàng và quy trình thanh toán 3 bước.
2. Kiểm tra tính toàn vẹn của dữ liệu tính toán tài chính: Giá từng sản phẩm, tổng tiền hàng, thuế làm tròn 8% và tổng tiền thanh toán đơn hàng.
3. Đánh giá các kịch bản rủi ro cao, kiểm tra khả năng xử lý ngoại lệ và độ ổn định của hệ thống trước các luồng thao tác bất thường hoặc dữ liệu không hợp lệ.
4. Đánh giá các khía cạnh phi chức năng: Hiệu năng tải trang (SLA < 2.0s), tính tương thích giao diện Responsive trên thiết bị di động, khả năng tiếp cận (Accessibility) và an toàn phiên làm việc (Session Security).

### In-Scope

- **Authentication & Session (EPIC-01):** Đăng nhập thành công, từ chối dữ liệu trống hoặc sai định dạng, xử lý tài khoản bị khóa, đăng xuất và chặn truy cập trái phép URL nội bộ.
- **Product Catalog & Browsing (EPIC-02):** Hiển thị danh mục 6 sản phẩm, xem chi tiết, quay lại danh mục, 4 bộ lọc sắp xếp (Tên A-Z, Z-A, Giá Low-High, High-Low) và tính toàn vẹn hình ảnh.
- **Shopping Cart Management (EPIC-03):** Thêm hoặc xóa sản phẩm từ catalog và trang chi tiết, đồng bộ huy hiệu giỏ hàng (Badge Counter), hiển thị trang giỏ hàng và duy trì trạng thái khi refresh trang.
- **Checkout Workflow (EPIC-04):** Xác thực thông tin khách hàng Bước 1, tổng quan đơn hàng và kiểm tra công thức tài chính Bước 2, hoàn tất đơn hàng Bước 3.
- **Sidebar Navigation & App State (EPIC-05):** Mở và đóng menu trượt, các liên kết điều hướng và chức năng làm mới trạng thái hệ thống (Reset App State).
- **End-to-End System Journey (EPIC-06):** Chu trình mua sắm tích hợp xuyên suốt từ đăng nhập đến nhận biên lai xác nhận.
- **Non-Functional Quality (EPIC-08):** Kiểm thử hiệu năng, độ tương thích đa thiết bị, trợ năng bàn phím và bảo mật cookie phiên.

### Out-of-Scope

- Tích hợp cổng thanh toán trực tuyến của bên thứ ba (Third-party Payment Gateways như Stripe, PayPal, Visa Gateway) do môi trường kiểm thử là sandbox mô phỏng.
- Xây dựng bộ kiểm thử tự động quy mô lớn trong pipeline CI/CD (Dự án tập trung chuyên sâu vào kỹ năng Manual Testing và phương pháp luận STLC).
- Thực thi kiểm thử Backend REST API (TC-51 đến TC-55) và Database SQL (TC-56 đến TC-60) trên môi trường thật do ứng dụng hoạt động dạng Single Page Application (SPA) phía client không có backend và cơ sở dữ liệu độc lập. Các ca kiểm thử này được thiết kế đầy đủ phục vụ tài liệu và ghi nhận trạng thái Blocked.

---

<a id="03-testing-approach-tools--stlc-process"></a>
## 03. Testing Approach, Tools & STLC Process

Dự án tuân thủ nghiêm ngặt mô hình Vòng Đời Kiểm Thử Phần Mềm (Software Testing Life Cycle - STLC) gồm 6 giai đoạn chuẩn mực:

```
+-----------------------------------------------------------------------------------+
|                        SOFTWARE TESTING LIFE CYCLE (STLC)                         |
+-----------------------------------------------------------------------------------+
|  1. Requirement Analysis  -->  Rà soát SRS/Stories, xác định Test Conditions      |
|  2. Test Planning         -->  Xây dựng Kế hoạch kiểm thử tổng thể (Test Plan)    |
|  3. Test Case Design      -->  Xác định Scenarios (WHAT), thiết kế Cases (HOW)    |
|  4. Environment Setup     -->  Cấu hình Chrome Desktop & Mobile Viewport chuẩn    |
|  5. Test Execution        -->  Thực thi 61/71 TCs (85.9%), 10 Blocked & log bugs   |
|  6. Test Closure          -->  QA Metrics, Quality Dashboard & Test Summary Report|
+-----------------------------------------------------------------------------------+
```

### STLC Phases Implementation

1. **Requirement Analysis (Phân tích yêu cầu):**
   - Tiếp nhận tài liệu yêu cầu nghiệp vụ đầu vào gồm [00_Epics_Document.md](00_Epics/00_Epics_Document.md) (8 Epics) và [01_Requirement_Document_User_Stories.md](01_Requirements/01_Requirement_Document_User_Stories.md) (17 User Stories kèm tiêu chí nghiệm thu Acceptance Criteria).
   - Đọc kỹ tài liệu đặc tả, phân tích tính khả thi kiểm thử (Testability), làm rõ các điểm mơ hồ với BA/Product Owner và xác định các điều kiện kiểm thử (Test Conditions) cùng phạm vi kiểm thử (Scope).

2. **Test Planning (Lập kế hoạch kiểm thử):**
   - Hoàn thiện tài liệu [02_Test_Plan_Document.md](02_Test_Plan/02_Test_Plan_Document.md) theo chuẩn IEEE 829 / ISO 29119.
   - Xác định rõ mục tiêu, chiến lược kiểm thử, môi trường, nhân lực, lịch trình triển khai, tiêu chí dừng hoặc tiếp tục (Suspension/Resumption Criteria) và tiêu chí kết thúc kiểm thử (Exit Criteria với mục tiêu Pass Rate > 90%).

3. **Test Case Development (Thiết kế kịch bản & ca kiểm thử):**
   - Dựa trên các yêu cầu và điều kiện đã phân tích, xác định 34 kịch bản kiểm thử [03_Test_Scenarios_Document.md](03_Test_Scenarios/03_Test_Scenarios_Document.md) nhằm trả lời cho câu hỏi WHAT to test (kiểm tra cái gì ở mức tổng quan cho cả Happy Path và Negative Path).
   - Chi tiết hóa thành 71 ca kiểm thử cụ thể [04_Test_Cases_Document.md](04_Test_Cases/04_Test_Cases_Document.md) theo định dạng tiêu chuẩn nhằm trả lời cho câu hỏi HOW to test (các bước thực hiện chi tiết, dữ liệu kiểm thử Test Data, điều kiện tiên quyết Preconditions và kết quả mong đợi Expected Results).
   - Xây dựng kế hoạch kiểm thử thăm dò [05_Exploratory_Test_Plan.md](05_Exploratory_Testing/05_Exploratory_Test_Plan.md) với 6 Session Charters theo phương pháp Session-Based Test Management (SBTM).
   - Thiết lập Ma trận truy xuất nguồn gốc [06_Requirement_Traceability_Matrix_RTM.md](06_Traceability_Matrix/06_Requirement_Traceability_Matrix_RTM.md) đạt 100% độ bao phủ (Zero Coverage Gap) giữa User Stories, Test Scenarios và Test Cases.

4. **Test Environment Setup (Chuẩn bị môi trường kiểm thử):**
   - Trình duyệt chính: Google Chrome Desktop (v124+) trên hệ điều hành macOS Sonoma (1920x1080).
   - Môi trường di động mô phỏng: Chrome DevTools Device Mode (iPhone Viewport 375x812).

5. **Test Execution & Defect Logging (Thực thi kiểm thử & Quản lý lỗi):**
   - Phân định rõ giữa chỉ số hoàn thành kế hoạch thiết kế (71/71 TCs Designed - 100%) và tiến độ thực thi thực tế (61/71 TCs Executed - 85.9%). 10 ca kiểm thử Backend API và Database SQL được bảo lưu trạng thái Blocked do ứng dụng client-side SPA không có backend và cơ sở dữ liệu công khai.
   - Trực tiếp thực thi thủ công 61 ca kiểm thử trên ứng dụng thực tế, ghi nhận kết quả chi tiết qua 18 trường thông tin chuẩn tại [07_Test_Execution_Results.md](07_Test_Execution_Result/07_Test_Execution_Results.md).
   - Phát hiện 10 lỗi thực tế, biên soạn 10 hồ sơ lỗi chuẩn mực theo nguyên tắc kiểm chứng lặp lại 3 lần (Rule of 3) tại [08_Bugs_Report_Document.md](08_Bugs_Report/08_Bugs_Report_Document.md) và thu thập bằng chứng hình ảnh tại [Evidence/Screenshots/](Evidence/Screenshots/).

6. **Test Closure & Quality Reporting (Đóng kiểm thử & Báo cáo chất lượng):**
   - Đo lường các chỉ số kiểm thử cốt lõi: Pass Rate trên số ca thực thi (83.6%), Pass Rate trên tổng số ca dự kiến (71.8%), Requirement Coverage (100%), Defect Density (0.14).
   - Trực quan hóa dữ liệu chất lượng trên [Quality_Dashboard.md](10_Quality_Dashboard/Quality_Dashboard.md).
   - Biên soạn Báo cáo tổng kết kiểm thử [09_Test_Summary_Report.md](09_Test_Summary_Report/09_Test_Summary_Report.md) kèm cây quyết định Go/No-Go phục vụ nghiệm thu phát hành.

### Test Design Techniques

- **Equivalence Partitioning (Phân vùng tương đương):** Phân chia tập dữ liệu hợp lệ và không hợp lệ cho thông tin đăng nhập, mã bưu chính và form khách hàng.
- **Boundary Value Analysis (Phân tích giá trị biên):** Kiểm tra giá trị biên của số lượng sản phẩm trong giỏ hàng (0, 1, 6 sản phẩm), độ dài ký tự tên và giới hạn tính toán tiền tệ.
- **State Transition Testing (Chuyển đổi trạng thái):** Kiểm tra vòng đời trạng thái của các nút thao tác (Add to cart / Remove), trạng thái giỏ hàng khi refresh hoặc chuyển trang.
- **Decision Table Testing (Bảng quyết định):** Thiết lập ma trận logic kiểm tra sự kết hợp giữa các trường dữ liệu đăng nhập và quyền truy cập hệ thống.
- **Error Guessing & Exploratory Heuristics:** Áp dụng các kỹ thuật phỏng đoán lỗi và kiểm thử thăm dò để phát hiện các lỗi bất thường ngoài kịch bản định sẵn.
- **Rule of 3 (Quy tắc kiểm chứng 3 lần):** Toàn bộ các lỗi phát hiện đều được QA tái hiện độc lập 3 lần liên tiếp trước khi lập báo cáo nhằm đảm bảo tính ổn định và tính xác thực 100%.

### Tools & Technologies

- **Test Management & Documentation:** Markdown, CSV, Test Case Template tiêu chuẩn, File Import Issue tiêu chuẩn.
- **Web Inspection & Analysis:** Google Chrome Developer Tools (Console, Network, Application Cookies, Elements, Responsive Device Mode).
- **Visualization & Reporting:** Mermaid.js Diagrams (Pie Charts, XY-Bar Charts), Microsoft Excel Pivot Tables.

---

<a id="04-repository-structure--deliverables"></a>
## 04. Repository Structure & Deliverables

Cấu trúc thư mục dự án được tổ chức khoa học với tiền tố số theo đúng trình tự thực hiện của chu trình kiểm thử STLC:

```
Project_QA_ManualTesting_ECommerceSauceDemo/
├── README.md                          <-- Project Landing Page (Tài liệu tổng quan dự án)
├── 00_Epics/                          <-- Đặc tả 8 Epics & File Import Issue tiêu chuẩn
├── 01_Requirements/                   <-- Đặc tả 17 User Stories & Acceptance Criteria
├── 02_Test_Plan/                      <-- Kế hoạch kiểm thử tổng thể (Test Plan Document)
├── 03_Test_Scenarios/                 <-- 34 Kịch bản kiểm thử Happy Path & Negative Path
├── 04_Test_Cases/                     <-- 71 Ca kiểm thử chi tiết theo tiêu chuẩn
│   ├── Functional_Testing/            <-- 50 Ca kiểm thử chức năng (6 Phân hệ nghiệp vụ)
│   ├── API_Testing/                   <-- 5 Ca kiểm thử RESTful API Contract & Response
│   ├── Database_SQL_Testing/          <-- 5 Ca kiểm thử truy vấn CSDL (Users, Orders, Items)
│   └── Non_Functional_Testing/        <-- 11 Ca kiểm thử phi chức năng (Performance, Security...)
├── 05_Exploratory_Testing/            <-- Kế hoạch kiểm thử thăm dò (SBTM Charters & Heuristics)
├── 06_Traceability_Matrix/            <-- Ma trận truy xuất nguồn gốc RTM đạt 100% độ bao phủ
├── 07_Test_Execution_Result/          <-- Nhật ký thực thi thực tế 71 Test Cases (18 trường dữ liệu)
├── 08_Bugs_Report/                    <-- 10 Báo cáo lỗi chi tiết chuẩn Rule of 3 (BUG-01 -> BUG-10)
├── 09_Test_Summary_Report/            <-- Báo cáo tổng kết kiểm thử & Cây quyết định Go/No-Go
├── 10_Quality_Dashboard/              <-- Bảng điều khiển chất lượng (QA Metrics & Mermaid Charts)
├── Evidence/                          <-- Thư mục lưu trữ hình ảnh (Screenshots) chụp thực tế
└── Tai_Lieu_Tham_Khao/                <-- 13 Tài liệu chuẩn mực quốc tế đã nghiên cứu áp dụng
```

### Deliverables Table

| **No.** | **Category** | **Deliverable** | **Format** | **Description** |
|:---:|:---|:---|:---:|:---|
| 1 | [00_Epics/](00_Epics/) | [00_Epics_Document.md](00_Epics/00_Epics_Document.md) | .md / .csv | 8 Epics hệ thống và tệp [Import_Epic&UserStory.csv](00_Epics/Import_Epic&UserStory.csv) định dạng tiêu chuẩn. |
| 2 | [01_Requirements/](01_Requirements/) | [01_Requirement_Document_User_Stories.md](01_Requirements/01_Requirement_Document_User_Stories.md) | .md / .csv | 17 User Stories kèm tiêu chí nghiệm thu Acceptance Criteria (AC). |
| 3 | [02_Test_Plan/](02_Test_Plan/) | [02_Test_Plan_Document.md](02_Test_Plan/02_Test_Plan_Document.md) | .md | Kế hoạch kiểm thử toàn diện chuẩn IEEE 829 / ISO 29119. |
| 4 | [03_Test_Scenarios/](03_Test_Scenarios/) | [03_Test_Scenarios_Document.md](03_Test_Scenarios/03_Test_Scenarios_Document.md) | .md / .csv | 34 Kịch bản kiểm thử bao phủ toàn diện luồng thuận và luồng nghịch. |
| 5 | [04_Test_Cases/](04_Test_Cases/) | [04_Test_Cases_Document.md](04_Test_Cases/04_Test_Cases_Document.md) | .md / .csv | 71 Ca kiểm thử chi tiết theo định dạng tiêu chuẩn. |
| 6 | [05_Exploratory_Testing/](05_Exploratory_Testing/) | [05_Exploratory_Test_Plan.md](05_Exploratory_Testing/05_Exploratory_Test_Plan.md) | .md | Kế hoạch kiểm thử thăm dò gồm 6 Charters và chiến lược Heuristics. |
| 7 | [06_Traceability_Matrix/](06_Traceability_Matrix/) | [06_Requirement_Traceability_Matrix_RTM.md](06_Traceability_Matrix/06_Requirement_Traceability_Matrix_RTM.md) | .md / .csv | Ma trận RTM 2 chiều đạt 100% độ bao phủ (Zero Coverage Gap). |
| 8 | [07_Test_Execution_Result/](07_Test_Execution_Result/) | [07_Test_Execution_Results.md](07_Test_Execution_Result/07_Test_Execution_Results.md) | .md / .csv | Nhật ký thực thi thực tế 71 TCs kèm 18 trường thông tin và liên kết bằng chứng. |
| 9 | [08_Bugs_Report/](08_Bugs_Report/) | [08_Bugs_Report_Document.md](08_Bugs_Report/08_Bugs_Report_Document.md) | .md / .csv | 10 Báo cáo lỗi độc lập ([BUG-01.md](08_Bugs_Report/BUG-01.md) -> [BUG-10.md](08_Bugs_Report/BUG-10.md)) xác thực Rule of 3. |
| 10 | [09_Test_Summary_Report/](09_Test_Summary_Report/) | [09_Test_Summary_Report.md](09_Test_Summary_Report/09_Test_Summary_Report.md) | .md | Báo cáo tổng kết kiểm thử: Metrics, Defect Highlights, Cây quyết định Go/No-Go. |
| 11 | [10_Quality_Dashboard/](10_Quality_Dashboard/) | [Quality_Dashboard.md](10_Quality_Dashboard/Quality_Dashboard.md) | .md / .csv | Bảng điều khiển trực quan: Scorecard KPI, biểu đồ tròn, biểu đồ cột mật độ lỗi. |
| 12 | [Evidence/](Evidence/) | [Evidence/Screenshots/](Evidence/Screenshots/) | Image Assets | Toàn bộ ảnh chụp màn hình thực tế làm bằng chứng kiểm thử được định danh hai chiều. |

---

<a id="05-test-results--metrics"></a>
## 05. Test Results & Metrics

### QA Scorecard

Bảng số liệu định lượng tổng hợp kết quả thực thi và đánh giá chất lượng sản phẩm:

| **Metric** | **Actual** | **Target** | **Status** |
|:---|:---:|:---:|:---:|
| Total Planned Tests | 71 TCs | - | Completed (100% Designed) |
| Executed Tests | 61 TCs | > 90.0% | 85.9% (10 Blocked) |
| Passed Tests | 51 TCs | - | 83.6% of Executed Tests |
| Failed Tests | 10 TCs | - | 16.4% of Executed Tests |
| Blocked Tests | 10 TCs | - | 14.1% of Planned (No Backend/DB) |
| Pass Rate (Executed Tests) | 83.6% | > 90.0% | Below Target (Critical Defect) |
| Pass Rate (All Planned Tests) | 71.8% | > 90.0% | Below Target (Includes Blocked) |
| Requirement Coverage | 100.0% | 100.0% | Target Met (Zero Coverage Gap) |
| Defect Density | 0.14 | < 0.20 | Target Met (10 Bugs / 71 TCs) |
| Open Critical Defects | 1 Bug (BUG-06) | 0 | Blocker for Production |

### Defect Highlights Table

Tổng hợp 10 khiếm khuyết được phát hiện và ghi nhận thực tế trong quá trình kiểm thử:

| **Bug ID** | **Summary** | **Component** | **Severity** | **Priority** | **Status** |
|:---:|:---|:---|:---:|:---:|:---:|
| [BUG-06](08_Bugs_Report/BUG-06.md) | Sập luồng runtime (La.cesetRart is not a function) khi nhấn nút Finish | Checkout Step Two | Critical | High | Open / Blocker |
| [BUG-03](08_Bugs_Report/BUG-03.md) | Nút Remove không hoạt động khi xóa sản phẩm Fleece Jacket | Shopping Cart & Inventory | High | High | Open / Deferred |
| [BUG-04](08_Bugs_Report/BUG-04.md) | Cho phép thanh toán giỏ hàng rỗng $0.00 mà không chặn chuyển hướng | Shopping Cart & Checkout | High | High | Open / Deferred |
| [BUG-05](08_Bugs_Report/BUG-05.md) | Ô Last Name bị ghi đè vào First Name, chặn đứng thanh toán của người dùng | Checkout Step One | High | High | Open / Deferred |
| [BUG-09](08_Bugs_Report/BUG-09.md) | Cookie phiên session-username thiếu cờ bảo mật HttpOnly và Secure | Security / Session Cookie | High | High | Open / Deferred |
| [BUG-01](08_Bugs_Report/BUG-01.md) | Toàn bộ 6 sản phẩm hiển thị ảnh lỗi 404 trên danh mục sản phẩm | Inventory / Product Catalog | Medium | High | Open / Known Issue |
| [BUG-02](08_Bugs_Report/BUG-02.md) | Đổi bộ lọc sắp xếp kích hoạt popup alert ngoại lệ JavaScript | Inventory Sorting | Medium | Medium | Open / Known Issue |
| [BUG-07](08_Bugs_Report/BUG-07.md) | Menu About trong Sidebar trỏ nhầm URL dẫn đến trang lỗi 404 | Menu & Navigation Sidebar | Medium | Medium | Open / Known Issue |
| [BUG-08](08_Bugs_Report/BUG-08.md) | Độ trễ tải trang bất thường 5.09s làm treo giao diện người dùng | Performance SLA | Medium | Medium | Open / Deferred |
| [BUG-10](08_Bugs_Report/BUG-10.md) | Giao diện bị lệch icon giỏ hàng và méo style nút Checkout | UI Layout / Header | Low | Low | Open / Won't Fix |

### Release Recommendation

- **Môi trường Production:** NO-GO — Dừng phát hành ra môi trường thực tế do tồn tại lỗi cấp độ Critical [BUG-06](08_Bugs_Report/BUG-06.md) làm gián đoạn hoàn toàn luồng hoàn tất đơn hàng tại bước cuối cùng.
- **Môi trường Staging / Internal Demo:** GO WITH RESERVATIONS — Cho phép triển khai thử nghiệm nội bộ với điều kiện người dùng thao tác trên tài khoản tiêu chuẩn standard_user và tuân thủ các giải pháp khắc phục tạm thời (Workaround) đã công bố tại [09_Test_Summary_Report.md](09_Test_Summary_Report/09_Test_Summary_Report.md).

---

<a id="06-key-learnings-limitations--disclaimer"></a>
## 06. Key Learnings, Limitations & Disclaimer

### Key Learnings

1. **Tư duy kiểm thử dựa trên rủi ro (Risk-Based Testing):** Phân tích và ưu tiên kiểm thử các vùng có mức độ rủi ro cao (xử lý thanh toán, tính toán tiền tệ, xử lý ngoại lệ giao diện) giúp tối ưu hóa nguồn lực kiểm thử và phát hiện sớm các khiếm khuyết nghiêm trọng.
2. **Kỷ luật truy xuất nguồn gốc (Requirement Traceability Rigor):** Duy trì ma trận RTM giúp đảm bảo 100% yêu cầu kinh doanh đều có ca kiểm thử bao phủ, đồng thời hỗ trợ việc phân tích tác động (Impact Analysis) khi có yêu cầu thay đổi.
3. **Chuẩn mực báo cáo lỗi và kiểm chứng tái lặp (Defect Reporting & Rule of 3):** Một báo cáo lỗi xuất sắc cần cung cấp đầy đủ các bước tái hiện, điều kiện tiên quyết, dữ liệu kiểm thử, phân định rạch ròi giữa Expected và Actual Result, đính kèm bằng chứng ảnh chụp rõ ràng và được kiểm chứng tính ổn định 3 lần liên tiếp.

### Limitations

- Ứng dụng SauceDemo hoạt động hoàn toàn ở tầng Frontend dưới dạng Single Page Application (SPA), không kết nối với cơ sở dữ liệu quan hệ phía máy chủ hay hệ thống Backend thực tế.
- Các ca kiểm thử RESTful API (TC-51 đến TC-55) và Database SQL (TC-56 đến TC-60) được thiết kế nhằm chuẩn hóa tài liệu nghiệp vụ hoàn chỉnh của một dự án thương mại điện tử, và được đánh dấu trạng thái Blocked theo đúng nguyên tắc vận hành kiểm thử khi môi trường chưa sẵn sàng.

### Disclaimer

- Dự án này là sản phẩm kiểm thử phi thương mại phục vụ xây dựng Hồ sơ Năng lực (Portfolio) cá nhân của QA Manual Tester - Khổng Đức Anh.
- Toàn bộ thương hiệu, giao diện và tài nguyên của ứng dụng SauceDemo thuộc quyền sở hữu của Sauce Labs Inc.

---

**Liên hệ tác giả / QA Manual Tester:**
- **Họ và tên:** Khổng Đức Anh
- **Vị trí ứng tuyển:** QA Manual Tester / Software Quality Assurance Engineer
- **Dự án mẫu:** [SauceDemo E-Commerce Testing Portfolio](https://github.com/khonganh/Project_QA_ManualTesting_ECommerceSauceDemo)
