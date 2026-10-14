# QA Manual Tester Portfolio: SauceDemo E-Commerce Testing

![QA Role](https://img.shields.io/badge/QA_Role-Manual_Tester-brightgreen)
![Tester](https://img.shields.io/badge/Author-QA_Kh%E1%BB%95ng_%C4%90%E1%BB%A9c_Anh-blue)
![Standard](https://img.shields.io/badge/Standard-ISO%2FIEC%2FIEEE_29119-blue)
![Coverage](https://img.shields.io/badge/Requirement_Coverage-100%25-success)
![Phase 1](https://img.shields.io/badge/Phase_1-Completed-blue)

Chào mừng bạn đến với **Portfolio Dự Án Kiểm Thử Phần Mềm Chuyên Nghiệp (QA Manual Testing)** cho hệ thống thương mại điện tử **SauceDemo** ([https://www.saucedemo.com/](https://www.saucedemo.com/)).

Portfolio này được thực hiện bởi **QA - Khổng Đức Anh**, thiết kế và xây dựng theo chuẩn mực thực tế của các doanh nghiệp phần mềm và các tổ chức kiểm thử quốc tế (ISTQB, IEEE 829, ISO/IEC/IEEE 29119), thể hiện đầy đủ năng lực phân tích nghiệp vụ, thiết kế ca kiểm thử, kiểm thử thăm dò, quản lý lỗi và truy xuất nguồn gốc yêu cầu của một QA Manual Tester chuyên nghiệp.

---

## 🗂️ Cấu Trúc Tổng Thể Dự Án (Project Architecture)

Dự án được triển khai bài bản qua 3 giai đoạn (Phases):
- **Phase 1: Test Planning and Design Test Case (Hoàn thành)** ➔ Lập kế hoạch, phân tích Epics & User Stories, thiết kế Scenarios & Test Cases, lập Kế hoạch kiểm thử thăm dò và Ma trận RTM.
- **Phase 2: Test Execution, Bug Reporting & Test Summary Report (Kế hoạch tiếp theo)** ➔ Thực thi kiểm thử, chạy Exploratory Sessions, báo cáo Bug chi tiết kèm Evidence và lập Báo cáo tổng kết TSR.
- **Phase 3: Jira Kanban & Zephyr Test Management Setup (Kế hoạch tiếp theo)** ➔ Tổ chức Epics, Stories, Bugs, Tasks trên Jira Kanban và cấu trúc Test Library trên Zephyr.

---

## 📑 Danh Mục Tài Liệu Bàn Giao (Phase 1 Deliverables)

Tất cả các tài liệu chính đều được cung cấp song song dưới 2 định dạng: **Markdown (.md)** phục vụ đọc trực quan trên GitHub và **CSV (.csv)** phục vụ import trực tiếp vào Jira / Zephyr hoặc mở trong Excel / Google Sheets:

| Tài Liệu / Thư Mục | Định Dạng | Mô Tả Tóm Tắt |
|:---|:---:|:---|
| [Import_Epic&UserStory.csv](Import_Epic&UserStory.csv) | `.csv` | File CSV hợp nhất 6 Epics & 13 Stories chuẩn Jira Cloud Importer (tự động liên kết phân cấp 100% qua Work Item ID). |
| [📁 Epics/](Epics/) | Thư mục phân cấp | Thư mục chứa 6 Epics độc lập (`EPIC-01.md` -> `EPIC-06.md`) và file `00_Epics_Document.csv` tra cứu danh sách Epic dạng bảng. |
| [00_Epics_Document.md](00_Epics_Document.md) | `.md` / `.csv` | Bảng đặc tả tổng hợp 6 Epics, cấu trúc phân cấp, phạm vi nghiệp vụ và hướng dẫn import Jira. |
| [📁 Requirements/](Requirements/) | Thư mục phân cấp | Thư mục chứa 13 User Stories độc lập phân chia theo từng Epic (`EPIC_01` -> `EPIC_06`). |
| [01_Requirement_Document_User_Stories.md](01_Requirement_Document_User_Stories.md) | `.md` / `.csv` | Bảng đặc tả tổng hợp 13 User Stories được phân chia theo 6 Epics kèm AC bold, TOC và CSV tra cứu danh sách Story dạng bảng. |
| [02_Test_Plan_Document.md](02_Test_Plan_Document.md) | `.md` | Kế hoạch kiểm thử chuẩn ISO 29119 & IEEE 829 (Phạm vi, Chiến lược, RACI, Entry/Exit criteria). |
| [📁 Test_Scenarios/](Test_Scenarios/) | Thư mục phân cấp | Chứa các thư mục con theo từng Epic, mỗi file `.md` chứa đúng 1 Test Scenario (bảng **Field**/**Value**, UserStoryID kèm AC). |
| [03_Test_Scenarios_Document.md](03_Test_Scenarios_Document.md) | `.md` / `.csv` | 30 Test Scenarios phân loại Happy Path & Negative Path kèm Risk Matrix, TOC và xử lý an toàn ký tự giá tiền. |
| [📁 Test_Cases/](Test_Cases/) | Thư mục phân cấp | Cấu trúc phân cấp theo Module Zephyr (`01_Authentication` -> `06_End_to_End`), mỗi file `.md` chứa đúng 1 Test Case (bảng **Field**/**Value**). |
| [04_Test_Cases_Document.md](04_Test_Cases_Document.md) | `.md` / `.csv` | 42 Test Cases chi tiết tương thích chuẩn các trường Zephyr (Field/Value, TOC, CSV tối ưu 11 cột cốt lõi đầu tiên). |
| [05_Exploratory_Test_Plan.md](05_Exploratory_Test_Plan.md) | `.md` | Kế hoạch kiểm thử thăm dò gồm 6 Charters, Heuristics (Goldilocks, Interruption, Rapid Input, SFDIPOT). |
| [06_Requirement_Traceability_Matrix_RTM.md](06_Requirement_Traceability_Matrix_RTM.md) | `.md` / `.csv` | Ma trận truy xuất nguồn gốc 2 chiều, xác thực độ bao phủ 100% (Zero Coverage Gap). |
| [📁 Tai_Lieu_Tham_Khao/](Tai_Lieu_Tham_Khao/) | PDF References | Các tài liệu chuẩn mực về Test Case, Bug Report, RTM, Charters & Heuristics đã tham chiếu. |

---

## 🎯 Điểm Nổi Bật Về Kỹ Thuật QA Trong Portfolio

1. **Chuẩn hóa trường thông tin tương thích hoàn toàn với Jira Cloud & Zephyr Scale / Squad:**
   - File `Import_Epic&UserStory.csv` tối ưu cấu trúc Jira Cloud Import chuẩn nhất: phân cấp tự động 6 Epics và 13 Stories thông qua `Work item ID` nội bộ.
   - File `00_Epics_Document.csv` & `01_Requirement_Document_User_Stories.csv` phục vụ tra cứu tổng quan danh sách Epics và User Stories dạng bảng trực quan (Work Item ID, Summary, Parent dạng `EPIC-01`, Acceptance Criteria, Priority, Status).
   - File `04_Test_Cases_Document.csv` tối ưu các cột quan trọng nhất ở đầu: `Test Case ID`, `Name`, `Objective`, `Priority`, `Severity`, `Test Type`, `Owner`, `Folder`, `Component`, `UserStoryID`, `TestScenarioID`, `Test Steps`, `Test Data`, `Expected Result`.
   - Toàn bộ Acceptance Criteria được tô đậm định danh (`**AC1:**`, `**AC2:**`...) rõ ràng, thẩm mỹ.
   - Cơ chế xử lý ký tự đặc biệt (`\$`) ngăn chặn triệt để lỗi hiển thị toán học KaTeX trên mọi trình xem Markdown.
   - Tất cả các bảng metadata hiển thị chuẩn 2 cột **Field** và **Value**, tên Field được **in đậm** rõ ràng, thẩm mỹ cao.
   - Toàn bộ link Table of Contents sử dụng anchor IDs độc lập, hỗ trợ chuyển hướng mượt mà trên mọi trình xem Markdown.

2. **Kỹ thuật thiết kế ca kiểm thử hộp đen (Black-box Test Design Techniques):**
   - **Equivalence Partitioning (EP):** Phân vùng giá trị đầu vào cho form đăng nhập và form thanh toán (hợp lệ, bỏ trống, ký tự lạ).
   - **Boundary Value Analysis (BVA):** Kiểm tra giá trị biên cho bộ đếm giỏ hàng (1 về 0), mã bưu điện, tính toán thuế 8% làm tròn.
   - **Negative Testing & Error Guessing:** Kiểm tra tài khoản bị khóa, giỏ hàng rỗng, spam click, ngắt quãng phiên làm việc.

3. **Chiến lược kiểm thử thăm dò định hướng Heuristics (Exploratory Testing):**
   - Áp dụng cấu trúc Charter chuẩn: `Explore [System] with [Resources] to discover [Information]`.
   - Khai thác trọn vẹn 7 khía cạnh của **SFDIPOT** (Structure, Function, Data, Interfaces, Platform, Operations, Time) và 6 user personas đặc trưng của Sauce Labs (`standard_user`, `locked_out_user`, `problem_user`, `performance_glitch_user`, `error_user`, `visual_user`).

4. **Độ bao phủ yêu cầu 100% (100% Requirement Traceability):**
   - Không có khoảng trống kiểm thử nào tồn tại giữa User Stories và Test Cases.

---
*Portfolio được duy trì và phát triển bởi QA - Khổng Đức Anh.*
