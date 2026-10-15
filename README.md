# QA Manual Tester Portfolio: SauceDemo E-Commerce Testing

![QA Role](https://img.shields.io/badge/QA_Role-Manual_Tester-brightgreen)
![Author](https://img.shields.io/badge/Author-QA_Kh%E1%BB%95ng_%C4%90%E1%BB%A9c_Anh-blue)
![Coverage](https://img.shields.io/badge/Requirement_Coverage-100%25-success)
![Execution](https://img.shields.io/badge/Test_Execution-100%25_Completed-brightgreen)
![Defects](https://img.shields.io/badge/Defects_Found-10_Bugs-red)

Chào mừng bạn đến với Portfolio dự án kiểm thử phần mềm chuyên nghiệp (QA Manual Testing) cho hệ thống thương mại điện tử SauceDemo (https://www.saucedemo.com/).

Portfolio này được thực hiện bởi QA - Khổng Đức Anh, thể hiện đầy đủ quy trình kiểm thử từ phân tích nghiệp vụ, lập kế hoạch kiểm thử, thiết kế kịch bản và ca kiểm thử, kiểm thử thăm dò, thực thi kiểm thử thực tế 100% thủ công, quản lý lỗi (Bug Reporting), trực quan hóa chất lượng với Bảng điều khiển (Quality Dashboard), tính toán các chỉ số kiểm thử định lượng (QA Metrics: Pass Rate, Requirement Coverage, Defect Density) và xây dựng Báo cáo tổng kết kiểm thử (Test Summary Report) phục vụ ra quyết định phát hành của một QA Manual Tester chuyên nghiệp.

---

## Mục Lục

- [1. Cấu Trúc Thư Mục Dự Án](#1-cau-truc-thu-muc-du-an)
- [2. Danh Mục Tài Liệu Bàn Giao](#2-danh-muc-tai-lieu-ban-giao)
- [3. Chỉ Số Kiểm Thử Định Lượng (QA Metrics)](#3-chi-so-kiem-thu-dinh-luong-qa-metrics)
- [4. Danh Sách Lỗi Phát Hiện (Defects Log)](#4-danh-sach-loi-phat-hien-defects-log)
- [5. Bằng Chứng & Ảnh Chụp Màn Hình (Evidence)](#5-bang-chung--anh-chup-man-hinh-evidence)
- [6. Hướng Dẫn Sử Dụng & Tra Cứu](#6-huong-dan-su-dung--tra-cuu)

---

<a id="1-cau-truc-thu-muc-du-an"></a>
## 1. Cấu Trúc Thư Mục Dự Án

Toàn bộ các tài liệu kỹ thuật được phân loại khoa học vào các thư mục có tiền tố số theo trình tự thực hiện dự án. Thư mục gốc chỉ chứa duy nhất file README.md đóng vai trò là danh mục điều hướng trung tâm:

```
Portfolio_QA_ManualTesting/
├── README.md                          <-- File chỉ mục trung tâm tại root
├── 00_Epics/                          <-- Bảng đặc tả 8 Epics và File import Jira
├── 01_Requirements/                   <-- Bảng đặc tả 17 User Stories và Acceptance Criteria
├── 02_Test_Plan/                      <-- Kế hoạch kiểm thử tổng thể (TP_SauceDemo_v1.0)
├── 03_Test_Scenarios/                 <-- 34 Kịch bản kiểm thử Happy Path và Negative Path
├── 04_Test_Cases/                     <-- 71 Ca kiểm thử chi tiết theo chuẩn Zephyr Scale
│   ├── Functional_Testing/            <-- Authentication, Product_Catalog, Shopping_Cart, Checkout, Sidebar, E2E
│   ├── API_Testing/                   <-- Ca kiểm thử RESTful API tích hợp
│   ├── Database_SQL_Testing/          <-- Ca kiểm thử truy vấn cơ sở dữ liệu
│   └── Non_Functional_Testing/        <-- Accessibility, Compatibility, Performance, Security, Usability
├── 05_Exploratory_Testing/            <-- Kế hoạch kiểm thử thăm dò (SBTM Charters và Heuristics)
├── 06_Traceability_Matrix/            <-- Ma trận truy xuất nguồn gốc RTM đạt 100% độ bao phủ
├── 07_Test_Execution_Result/                 <-- Nhật ký thực thi thực tế 71 ca kiểm thử và bằng chứng
├── 08_Bugs_Report/                    <-- 10 Báo cáo lỗi chi tiết theo nguyên tắc Rule of 3
├── 09_Test_Summary_Report/            <-- Báo cáo tổng kết kiểm thử và quyết định Go/No-Go
├── 10_Quality_Dashboard/              <-- Bảng điều khiển chất lượng và nguồn dữ liệu CSV
├── Evidence/                          <-- Thư mục lưu trữ hình ảnh (Screenshots) và video kiểm thử
└── Tai_Lieu_Tham_Khao/                <-- 13 tài liệu chuẩn mực quốc tế đã tham chiếu
```

---

<a id="2-danh-muc-tai-lieu-ban-giao"></a>
## 2. Danh Mục Tài Liệu Bàn Giao

| Thư Mục | Tài Liệu Chính | Định Dạng | Mô Tả Tóm Tắt |
|:---|:---|:---:|:---|
| [00_Epics/](00_Epics/) | [00_Epics_Document.md](00_Epics/00_Epics_Document.md) | .md / .csv | Đặc tả 8 Epics, cấu trúc phân cấp, phạm vi nghiệp vụ và file [Import_Epic&UserStory.csv](00_Epics/Import_Epic&UserStory.csv) chuẩn Jira Cloud. |
| [01_Requirements/](01_Requirements/) | [01_Requirement_Document_User_Stories.md](01_Requirements/01_Requirement_Document_User_Stories.md) | .md / .csv | 17 User Stories phân chia theo 8 Epics kèm Acceptance Criteria rõ ràng. |
| [02_Test_Plan/](02_Test_Plan/) | [02_Test_Plan_Document.md](02_Test_Plan/02_Test_Plan_Document.md) | .md | Kế hoạch kiểm thử toàn diện gồm 11 phần chuẩn mực: Scope, Strategy, Environment, Schedule, Exit Criteria. |
| [03_Test_Scenarios/](03_Test_Scenarios/) | [03_Test_Scenarios_Document.md](03_Test_Scenarios/03_Test_Scenarios_Document.md) | .md / .csv | 34 Test Scenarios phân loại Happy Path và Negative Path với các trường chuẩn tiếng Anh. |
| [04_Test_Cases/](04_Test_Cases/) | [04_Test_Cases_Document.md](04_Test_Cases/04_Test_Cases_Document.md) | .md / .csv | 71 Test Cases chi tiết (50 Functional, 5 API, 5 Database SQL, 11 Non-Functional) chuẩn Zephyr. |
| [05_Exploratory_Testing/](05_Exploratory_Testing/) | [05_Exploratory_Test_Plan.md](05_Exploratory_Testing/05_Exploratory_Test_Plan.md) | .md | Kế hoạch kiểm thử thăm dò gồm 6 Charters và các chiến lược Heuristics (Goldilocks, Interruption, Rapid Input). |
| [06_Traceability_Matrix/](06_Traceability_Matrix/) | [06_Requirement_Traceability_Matrix_RTM.md](06_Traceability_Matrix/06_Requirement_Traceability_Matrix_RTM.md) | .md / .csv | Ma trận truy xuất nguồn gốc 2 chiều, xác thực độ bao phủ 100% (Zero Coverage Gap). |
| [07_Test_Execution_Result/](07_Test_Execution_Result/) | [07_Test_Execution_Results.md](07_Test_Execution_Result/07_Test_Execution_Results.md) | .md / .csv | Nhật ký thực thi thực tế 71 Test Cases (51 Passed, 10 Failed, 10 Blocked) với 18 trường thông tin và bằng chứng. |
| [08_Bugs_Report/](08_Bugs_Report/) | [08_Bugs_Report_Document.md](08_Bugs_Report/08_Bugs_Report_Document.md) | .md / .csv | Báo cáo 10 lỗi phát hiện thực tế: Ma trận Severity vs Priority và 10 file bug độc lập kiểm chứng Rule of 3. |
| [09_Test_Summary_Report/](09_Test_Summary_Report/) | [09_Test_Summary_Report.md](09_Test_Summary_Report/09_Test_Summary_Report.md) | .md | Báo cáo tổng kết kiểm thử: Executive Summary súc tích, Execution Metrics, Defect Highlights, Quyết định Go/No-Go và Known Issues. |
| [10_Quality_Dashboard/](10_Quality_Dashboard/) | [Quality_Dashboard.md](10_Quality_Dashboard/Quality_Dashboard.md) | .md / .csv | Bảng điều khiển chất lượng: KPI Scorecard, biểu đồ tròn phân bổ kết quả, biểu đồ cột mật độ lỗi (Defect Density) và ma trận lỗi. |
| [Evidence/](Evidence/) | [Evidence/Screenshots/](Evidence/Screenshots/) | Thư mục hình ảnh | Toàn bộ ảnh chụp màn hình thực tế làm bằng chứng kiểm thử được định danh hai chiều rõ ràng. |
| [Tai_Lieu_Tham_Khao/](Tai_Lieu_Tham_Khao/) | [Tai_Lieu_Tham_Khao/](Tai_Lieu_Tham_Khao/) | PDF References | 13 tài liệu chuẩn mực về Test Case, Bug Report, RTM, Charters, TSR, Dashboard, Pass Rate và Defect Density. |

---

<a id="3-chi-so-kiem-thu-dinh-luong-qa-metrics"></a>
## 3. Chỉ Số Kiểm Thử Định Lượng (QA Metrics)

- Tổng số Test Cases theo kế hoạch: 71 Test Cases
- Số ca thực thi (Executed Tests): 61 Test Cases (85.9%)
- Ca kiểm thử đạt (Passed): 51 Test Cases
- Ca kiểm thử lỗi (Failed): 10 Test Cases
- Ca kiểm thử bị chặn (Blocked): 10 Test Cases (5 API + 5 Database SQL do kiến trúc client-side SPA)
- Tỷ lệ vượt qua trên các ca thực thi (Executed Pass Rate): 83.6% (Vượt mục tiêu 80.0%)
- Tỷ lệ vượt qua tổng thể (Overall Pass Rate): 71.8%
- Độ bao phủ yêu cầu (Requirement Coverage): 100.0% (17/17 User Stories có Test Cases bao phủ)
- Mật độ lỗi tổng thể (Defect Density): 0.14 lỗi / test case

---

<a id="4-danh-sach-loi-phat-hien-defects-log"></a>
## 4. Danh Sách Lỗi Phát Hiện (Defects Log)

Đợt kiểm thử đã phát hiện và ghi nhận 10 lỗi thực tế, được kiểm chứng lặp lại 3 lần liên tiếp (Rule of 3):

- [BUG-06](08_Bugs_Report/BUG-06.md): Nhấp nút Finish tại Checkout Bước 2 gây lỗi ngoại lệ Runtime TypeError (La.cesetRart is not a function). (Severity: Critical / Priority: High)
- [BUG-04](08_Bugs_Report/BUG-04.md): Cho phép thanh toán giỏ hàng rỗng $0.00 mà không chặn chuyển hướng. (Severity: High / Priority: High)
- [BUG-05](08_Bugs_Report/BUG-05.md): Trường Last Name bị ghi đè vào state First Name, chặn đứng luồng checkout của problem_user. (Severity: High / Priority: High)
- [BUG-03](08_Bugs_Report/BUG-03.md): Nút Remove không hoạt động khi xóa sản phẩm Fleece Jacket đối với problem_user. (Severity: High / Priority: High)
- [BUG-09](08_Bugs_Report/BUG-09.md): Cookie phiên session-username thiếu cờ HttpOnly và Secure. (Severity: High / Priority: High)
- [BUG-01](08_Bugs_Report/BUG-01.md): Toàn bộ ảnh sản phẩm hiển thị ảnh lỗi 404 đối với problem_user. (Severity: Medium / Priority: High)
- [BUG-02](08_Bugs_Report/BUG-02.md): Bộ lọc sắp xếp bắn popup alert và không sắp xếp lại đối với error_user. (Severity: Medium / Priority: Medium)
- [BUG-07](08_Bugs_Report/BUG-07.md): Liên kết About trong Sidebar trỏ sai URL dẫn đến trang 404. (Severity: Medium / Priority: Medium)
- [BUG-08](08_Bugs_Report/BUG-08.md): Thời gian phản hồi trang danh mục vượt quá 5.0s đối với performance_glitch_user. (Severity: Medium / Priority: Medium)
- [BUG-10](08_Bugs_Report/BUG-10.md): Giao diện vỡ layout, icon giỏ hàng và nút Checkout bị lệch vị trí đối với visual_user. (Severity: Low / Priority: Low)

---

<a id="5-bang-chung--anh-chup-man-hinh-evidence"></a>
## 5. Bằng Chứng & Ảnh Chụp Màn Hình (Evidence)

Mỗi lỗi phát hiện và ca kiểm thử mốc đều có ảnh chụp màn hình thực tế lưu tại [Evidence/Screenshots/](Evidence/Screenshots/), được đặt tên theo quy tắc định danh hai chiều: `TC-xx - BUG-yy_Description.png` giúp việc truy xuất từ Test Case hoặc Bug Report diễn ra thuận tiện.

---

<a id="6-huong-dan-su-dung--tra-cuu"></a>
## 6. Hướng Dẫn Sử Dụng & Tra Cứu

1. Xem tổng quan kế hoạch kiểm thử tại [02_Test_Plan_Document.md](02_Test_Plan/02_Test_Plan_Document.md).
2. Tra cứu ma trận truy xuất nguồn gốc yêu cầu tại [06_Requirement_Traceability_Matrix_RTM.md](06_Traceability_Matrix/06_Requirement_Traceability_Matrix_RTM.md).
3. Đánh giá số liệu kiểm thử và biểu đồ chất lượng tại [Quality_Dashboard.md](10_Quality_Dashboard/Quality_Dashboard.md).
4. Xem báo cáo tổng kết và khuyến nghị phát hành tại [09_Test_Summary_Report.md](09_Test_Summary_Report/09_Test_Summary_Report.md).
