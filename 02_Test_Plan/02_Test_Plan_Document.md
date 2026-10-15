# Test Plan: SauceDemo E-Commerce Web Application

Document ID: TP_SauceDemo_v1.0  
Target Application: SauceDemo (https://www.saucedemo.com/)  
Author: QA - Khổng Đức Anh  
Date: 12/09/2026  
Status: Approved  

---

## Mục Lục

- [1. Test Plan ID](#1-test-plan-id)
- [2. Introduction & Objective](#2-introduction--objective)
- [3. Test Scope](#3-test-scope)
  - [3.1 In-scope (Phạm vi kiểm thử)](#31-in-scope-pham-vi-kiem-thu)
  - [3.2 Out-of-scope (Ngoài phạm vi kiểm thử)](#32-out-of-scope-ngoai-pham-vi-kiem-thu)
- [4. Test Strategy](#4-test-strategy)
- [5. Test Environment](#5-test-environment)
- [6. Resources & Team](#6-resources--team)
- [7. Schedule & Estimation](#7-schedule--estimation)
- [8. Test Deliverables](#8-test-deliverables)
- [9. Suspension & Resumption Criteria](#9-suspension--resumption-criteria)
- [10. Exit Criteria (Tiêu chí kết thúc)](#10-exit-criteria-tieu-chi-ket-thuc)
- [11. Risks & Mitigation](#11-risks--mitigation)

---

<a id="1-test-plan-id"></a>
## 1. Test Plan ID

Mã định danh tài liệu: TP_SauceDemo_v1.0


<a id="2-introduction--objective"></a>
## 2. Introduction & Objective

Mục tiêu của đợt kiểm thử là đánh giá chất lượng toàn diện của ứng dụng web thương mại điện tử SauceDemo (Swag Labs) trước khi phát hành, bao gồm:

- Kiểm thử chức năng (Functional Testing): Đảm bảo các luồng mua sắm cốt lõi (đăng nhập, duyệt danh mục, quản lý giỏ hàng, đặt hàng thanh toán và điều hướng sidebar) hoạt động chính xác theo yêu cầu nghiệp vụ.
- Kiểm thử phi chức năng (Non-Functional Testing): Đánh giá tính tương thích trình duyệt và giao diện di động (Compatibility / Responsive), kiểm tra thời gian tải trang và độ trễ phản hồi (Performance SLA < 2.0s), kiểm tra an toàn phiên và thuộc tính Cookie (Security), cùng các tiêu chí tiếp cận giao diện cơ bản (Accessibility / UX).
- Phát hiện sớm các rủi ro và khiếm khuyết tiềm ẩn trên các luồng nghiệp vụ và trường hợp biên (Edge Cases).
- Cung cấp số liệu định lượng (QA Metrics) và bằng chứng kiểm thử thực tế phục vụ quyết định phát hành (Go/No-Go Decision).


<a id="3-test-scope"></a>
## 3. Test Scope

<a id="31-in-scope-pham-vi-kiem-thu"></a>
### 3.1 In-scope (Phạm vi kiểm thử)

Các tính năng và khu vực chức năng được kiểm thử chi tiết trong đợt này:

- Xác thực và phiên làm việc (Authentication & Session): Đăng nhập thành công với tài khoản tiêu chuẩn, đăng nhập không hợp lệ, xử lý tài khoản bị khóa, đăng xuất và bảo vệ đường dẫn nội bộ.
- Danh mục sản phẩm (Product Catalog): Hiển thị đầy đủ 6 sản phẩm, xem trang chi tiết sản phẩm, thuật ngữ và bộ lọc sắp xếp (Tên A-Z, Z-A; Giá Low-High, High-Low).
- Quản lý giỏ hàng (Shopping Cart): Thêm/xóa sản phẩm từ trang danh mục và trang chi tiết, đồng bộ huy hiệu số lượng (Cart Badge Counter), kiểm tra giỏ hàng rỗng.
- Quy trình thanh toán nhiều bước (Checkout Workflow):
  - Bước 1: Nhập và xác thực thông tin khách hàng (First Name, Last Name, Postal Code).
  - Bước 2: Hiển thị danh sách tóm tắt món hàng, tính toán Item Total, tính thuế 8% (Tax) và Tổng tiền thanh toán (Total).
  - Bước 3: Hoàn tất đơn hàng và hiển thị trang cảm ơn (Checkout: Complete!).
- Menu điều hướng và trạng thái ứng dụng (Sidebar Navigation & App State): Mở/đóng menu trượt, All Items, About link, Logout, Reset App State.
- Luồng trải nghiệm xuyên suốt (End-to-End Core Journey): Quy trình mua hàng hoàn chỉnh từ đăng nhập đến thanh toán thành công và đăng xuất.
- Kiểm thử phi chức năng: Hiệu năng tải trang, kiểm tra cờ bảo mật cookie phiên (HttpOnly, Secure), chống mã độc XSS cơ bản trong form nhập liệu, và hiển thị responsive trên màn hình di động (375x812).

<a id="32-out-of-scope-ngoai-pham-vi-kiem-thu"></a>
### 3.2 Out-of-scope (Ngoài phạm vi kiểm thử)

Các nội dung không thực hiện kiểm thử trong đợt này:

- Kiểm thử trực tiếp máy chủ cơ sở dữ liệu backend và câu lệnh SQL (do hệ thống SauceDemo là Single Page Application client-side thuần túy, không cung cấp kết nối DBMS trực tiếp). Các ca kiểm thử SQL được thiết kế sẵn và đánh dấu trạng thái Blocked.
- Kiểm thử tích hợp RESTful API backend công khai (do hệ thống không expose REST API endpoints công khai). Các ca kiểm thử API được thiết kế sẵn và đánh dấu trạng thái Blocked.
- Kiểm thử tải chịu tải lớn (Load & Stress Testing với hàng nghìn concurrent users).
- Tích hợp cổng thanh toán ngân hàng thực tế (sử dụng luồng thanh toán mô phỏng).


<a id="4-test-strategy"></a>
## 4. Test Strategy

Phương pháp tiếp cận kiểm thử kết hợp chặt chẽ giữa các kỹ thuật:

- Kiểm thử thủ công (Manual Testing): Đóng vai trò chủ đạo trong toàn bộ quá trình kiểm thử. QA trực tiếp tương tác trên giao diện người dùng (UI), đánh giá trải nghiệm thực tế (UX), kiểm tra tính đúng đắn của logic nghiệp vụ và phát hiện khiếm khuyết trong các luồng vận hành.
- Kỹ thuật thiết kế kiểm thử hộp đen (Black-box Test Design Techniques):
  - Phân vùng tương đương (Equivalence Partitioning): Áp dụng cho các trường nhập liệu tên, mật khẩu, mã bưu chính.
  - Phân tích giá trị biên (Boundary Value Analysis): Áp dụng cho giỏ hàng 0 sản phẩm, 1 sản phẩm và tối đa 6 sản phẩm; kiểm tra tính toán thuế và làm tròn tiền tệ.
  - Phân tích bảng quyết định (Decision Table Testing): Áp dụng cho ma trận tài khoản người dùng và trạng thái cho phép đăng nhập / hiển thị lỗi.
- Kiểm thử thăm dò (Session-Based Exploratory Testing): Áp dụng các Charters và Heuristics (Goldilocks, Interruption, Rapid Input, Follow the Data, SFDIPOT) để tìm kiếm các lỗi biên và hành vi bất thường ngoài kịch bản định sẵn.
- Các loại kiểm thử thực hiện:
  - Functional Testing: Smoke Testing, Sanity Testing, Functional Regression Testing.
  - Non-Functional Testing: UI/UX Testing, Accessibility Testing cơ bản, Security Cookie Inspection, Performance Latency Inspection, Mobile Compatibility Testing.


<a id="5-test-environment"></a>
## 5. Test Environment

- Môi trường phần cứng và hệ điều hành: macOS Sonoma (v14.4+) và Windows 11 Desktop, độ phân giải màn hình chuẩn 1920x1080.
- Trình duyệt kiểm thử chính: Google Chrome Desktop (v124+), Mozilla Firefox (v125+), Safari Desktop.
- Môi trường di động mô phỏng: Viewport di động kích thước 375x812 (iPhone X/12) trên Chrome DevTools Device Mode.
- Công cụ hỗ trợ:
  - Google Chrome Desktop (v124+): Trình duyệt thực thi kiểm thử chính.
  - Chrome DevTools: Giám sát Console errors, Network tab (kiểm tra độ trễ và mã HTTP), Application tab (kiểm tra Cookie, LocalStorage, SessionStorage).
  - Postman: Thiết kế và kiểm tra các giao thức RESTful API.
  - macOS Screenshot Utility / Snipping Tool: Công cụ chụp ảnh màn hình và quản lý bằng chứng kiểm thử thủ công.


<a id="6-resources--team"></a>
## 6. Resources & Team

Phân bổ nhân sự và trách nhiệm:

- QA Lead / Manual Tester (Khổng Đức Anh):
  - Chịu trách nhiệm toàn bộ vòng đời kiểm thử: Lập kế hoạch kiểm thử (Test Plan), phân tích User Stories, thiết kế 34 Test Scenarios và 71 Test Cases chi tiết.
  - Trực tiếp thực thi kiểm thử thủ công 100% ca kiểm thử trên trình duyệt Chrome, quan sát hành vi UI/UX, phân tích Console/Network trên Chrome DevTools, ghi nhận kết quả và chụp ảnh bằng chứng (Evidence) thủ công.
  - Lập báo cáo lỗi (Bug Reports), phân tích nguyên nhân gốc rễ (RCA) và đánh giá mức độ nghiêm trọng (Severity vs Priority) khi phát sinh khiếm khuyết trong quá trình thực thi.
  - Xây dựng Bảng điều khiển chất lượng (Quality Dashboard) và viết Báo cáo tổng kết kiểm thử (Test Summary Report).
- Product Owner / Stakeholder:
  - Rà soát đặc tả yêu cầu và tiêu chí nghiệm thu (Acceptance Criteria).
  - Xem xét khuyến nghị Go/No-Go trong Test Summary Report để đưa ra quyết định phát hành sản phẩm.
- Development Team:
  - Tiếp nhận các báo cáo lỗi đã được kiểm chứng (Rule of 3), tiến hành sửa lỗi trong Sprint tiếp theo và cung cấp bản vá để kiểm thử hồi quy.


<a id="7-schedule--estimation"></a>
## 7. Schedule & Estimation

Lộ trình thời gian triển khai chi tiết:

- 10/09/2026 - 12/09/2026: Phân tích nghiệp vụ ứng dụng, xây dựng Test Plan (TP_SauceDemo_v1.0).
- 13/09/2026 - 15/09/2026: Rà soát 8 Epics, đặc tả 17 User Stories và chi tiết hóa Acceptance Criteria.
- 16/09/2026 - 19/09/2026: Thiết kế danh sách 34 Test Scenarios (Happy Path và Negative Path).
- 20/09/2026 - 24/09/2026: Thiết kế 71 Test Cases chi tiết theo tiêu chuẩn và thiết lập Ma trận RTM đạt 100% độ bao phủ.
- 25/09/2026 - 28/09/2026: Thực thi toàn bộ ca kiểm thử trên ứng dụng thực tế, ghi nhận kết quả vào Test Execution Results, thu thập bằng chứng hình ảnh và lập báo cáo lỗi (Bug Reports) cho các khiếm khuyết phát sinh.
- 29/09/2026 - 30/09/2026: Tổng hợp dữ liệu QA Metrics, xây dựng Quality Dashboard, phân tích cây quyết định Go/No-Go và hoàn thiện Test Summary Report.


<a id="8-test-deliverables"></a>
## 8. Test Deliverables

Danh mục tài liệu bàn giao dự kiến trong toàn bộ quy trình kiểm thử:

### 8.1 Tài liệu giai đoạn Lập kế hoạch & Thiết kế kiểm thử (Planning & Design Phase)
- Kế hoạch kiểm thử tổng thể: [02_Test_Plan_Document.md](02_Test_Plan_Document.md)
- Bảng đặc tả Epics: [00_Epics_Document.md](../00_Epics/00_Epics_Document.md) | [00_Epics_Document.csv](../00_Epics/00_Epics_Document.csv) | [Import_Epic&UserStory.csv](../00_Epics/Import_Epic&UserStory.csv)
- Đặc tả yêu cầu (User Stories): [01_Requirement_Document_User_Stories.md](../01_Requirements/01_Requirement_Document_User_Stories.md) | [01_Requirement_Document_User_Stories.csv](../01_Requirements/01_Requirement_Document_User_Stories.csv)
- Kịch bản kiểm thử: [03_Test_Scenarios_Document.md](../03_Test_Scenarios/03_Test_Scenarios_Document.md) | [03_Test_Scenarios_Document.csv](../03_Test_Scenarios/03_Test_Scenarios_Document.csv)
- Bộ ca kiểm thử chi tiết: [04_Test_Cases_Document.md](../04_Test_Cases/04_Test_Cases_Document.md) | [04_Test_Cases_Document.csv](../04_Test_Cases/04_Test_Cases_Document.csv)
- Kế hoạch kiểm thử thăm dò: [05_Exploratory_Test_Plan.md](../05_Exploratory_Testing/05_Exploratory_Test_Plan.md)
- Ma trận truy xuất nguồn gốc yêu cầu: [06_Requirement_Traceability_Matrix_RTM.md](../06_Traceability_Matrix/06_Requirement_Traceability_Matrix_RTM.md) | [06_Requirement_Traceability_Matrix_RTM.csv](../06_Traceability_Matrix/06_Requirement_Traceability_Matrix_RTM.csv)

### 8.2 Tài liệu giai đoạn Thực thi & Đóng kiểm thử (Execution & Closure Phase)
- Nhật ký kết quả thực thi: [07_Test_Execution_Results.md](../07_Test_Execution_Result/07_Test_Execution_Results.md) | [07_Test_Execution_Results.csv](../07_Test_Execution_Result/07_Test_Execution_Results.csv)
- Báo cáo lỗi và theo dõi khiếm khuyết: [08_Bugs_Report_Document.md](../08_Bugs_Report/08_Bugs_Report_Document.md) | [08_Bugs_Report_Document.csv](../08_Bugs_Report/08_Bugs_Report_Document.csv) (thư mục quản lý lỗi [08_Bugs_Report/](../08_Bugs_Report/))
- Báo cáo tổng kết kiểm thử: [09_Test_Summary_Report.md](../09_Test_Summary_Report/09_Test_Summary_Report.md)
- Bảng điều khiển chất lượng: [Quality_Dashboard.md](../10_Quality_Dashboard/Quality_Dashboard.md) | [Quality_Dashboard_Metrics.csv](../10_Quality_Dashboard/Quality_Dashboard_Metrics.csv) | [Quality_Dashboard_Pivot_Source.csv](../10_Quality_Dashboard/Quality_Dashboard_Pivot_Source.csv)
- Thư mục lưu trữ bằng chứng kiểm thử: [Evidence/Screenshots/](../Evidence/Screenshots/)


<a id="9-suspension--resumption-criteria"></a>
## 9. Suspension & Resumption Criteria

- Điều kiện tạm dừng kiểm thử (Suspension Criteria):
  - Trang đăng nhập hoặc trang chủ sập hoàn toàn (HTTP 500 hoặc Crash), không thể truy cập vào ứng dụng.
  - Tỷ lệ ca kiểm thử thất bại (Fail) trong phân hệ xác thực vượt quá 40%, gây nghẽn toàn bộ các ca kiểm thử phía sau.
  - Môi trường kiểm thử bị thay đổi bất ngờ làm mất tính ổn định của dữ liệu mô phỏng.
- Điều kiện tiếp tục kiểm thử (Resumption Criteria):
  - Sự cố chặn luồng được khắc phục, ứng dụng hoạt động trở lại ổn định.
  - Vượt qua vòng kiểm thử khói (Smoke Test) xác nhận luồng đăng nhập và chuyển hướng hoạt động bình thường.


<a id="10-exit-criteria-tieu-chi-ket-thuc"></a>
## 10. Exit Criteria (Tiêu chí kết thúc)

Đợt kiểm thử được coi là hoàn thành khi đáp ứng đầy đủ các tiêu chí sau:

- 100% ca kiểm thử theo kế hoạch (71/71 TCs) được thực thi hoặc ghi nhận trạng thái rõ ràng (Passed, Failed, Blocked).
- Tỷ lệ đạt (Pass Rate) trên các ca thực thi đạt tối thiểu 90%.
- Độ bao phủ yêu cầu nghiệp vụ (Requirements Coverage) đạt 100% trên Ma trận RTM (tất cả 17 User Stories đều có ca kiểm thử bao phủ).
- 100% lỗi phát hiện trong quá trình kiểm thử được ghi nhận chi tiết vào hệ thống quản lý lỗi (Bugs Report), có đầy đủ bằng chứng hình ảnh (Evidence) và đã kiểm chứng tính tái lập 3 lần (Rule of 3).
- Không còn bất kỳ lỗi mức độ Blocker/Critical nào chưa được xử lý hoặc chưa có phương án né lỗi tạm thời (Workaround) được phê duyệt.


<a id="11-risks--mitigation"></a>
## 11. Risks & Mitigation

- Rủi ro 1: Ứng dụng SauceDemo là Single Page Application client-side thuần túy, không có RESTful API backend và DBMS công khai.
  - Phương án xử lý: Thiết kế đầy đủ bộ ca kiểm thử API và SQL để chứng minh năng lực kiểm thử, đồng thời ghi nhận trạng thái Blocked kèm lý do kiến trúc rõ ràng, không làm sai lệch số liệu thực thi.
- Rủi ro 2: Các tài khoản người dùng lỗi (problem_user, error_user, performance_glitch_user) làm phát sinh popup alert hoặc treo giao diện.
  - Phương án xử lý: Đóng các alert popup ngay khi xuất hiện; sử dụng tính năng Reset App State trong Sidebar hoặc xóa cookie phiên để dọn dẹp trạng thái trước khi chuyển sang ca kiểm thử khác.
- Rủi ro 3: Độ trễ phản hồi trang có thể bị hiểu nhầm là lỗi treo ứng dụng đối với tài khoản performance_glitch_user.
  - Phương án xử lý: Thiết lập thời gian chờ (timeout) tối thiểu 10 giây và sử dụng Performance API / DevTools Network để đo chính xác thời gian trễ thực tế.
