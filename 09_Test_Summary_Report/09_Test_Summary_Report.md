# Test Summary Report: SauceDemo E-Commerce Web Application

Document ID: TSR-SAUCEDEMO-01  
Target Application: SauceDemo (https://www.saucedemo.com/)  
Author: QA - Khổng Đức Anh  
Execution Cycle: Test Cycle 1 (Round 1)  
Date: 30/09/2026  
Overall Recommendation: No-Go for Production / Go with Reservations for Staging Demo  

---

## Mục Lục

- [1. Executive Summary](#1-executive-summary)
- [2. Execution Metrics](#2-execution-metrics)
- [3. Defect Highlights](#3-defect-highlights)
- [4. Go / No-Go Recommendation](#4-go--no-go-recommendation)
- [5. Known Issues and Deferred Bugs](#5-known-issues-and-deferred-bugs)
- [6. Conclusion](#6-conclusion)

---

<a id="1-executive-summary"></a>
## 1. Executive Summary

Quá trình thực thi kiểm thử Vòng 1 cho ứng dụng SauceDemo đã hoàn tất với 71 ca kiểm thử được đánh giá chi tiết (51 Passed, 10 Failed, 10 Blocked), đạt tỷ lệ vượt qua 83.6% trên các ca thực thi và độ bao phủ yêu cầu nghiệp vụ đạt 100% (17/17 User Stories).

Mặc dù quy trình mua hàng cốt lõi với tài khoản tiêu chuẩn hoạt động ổn định, đợt kiểm thử đã phát hiện 10 lỗi thực tế—trong đó có 1 lỗi nghiêm trọng cấp độ Critical làm sập luồng đặt hàng tại nút Finish và 4 lỗi High tại giỏ hàng và thanh toán.

Báo cáo này đưa ra khuyến nghị **No-Go** đối với việc phát hành lên Production và đề xuất **Go with Reservations** (cho phép demo nội bộ / staging) kèm theo các giải pháp né lỗi tạm thời.

<br>

---

<a id="2-execution-metrics"></a>
## 2. Execution Metrics

Dưới đây là số liệu định lượng tổng hợp kết quả thực thi kiểm thử Vòng 1:

| Test Status | Count | Percentage |
|:---|:---:|:---:|
| Passed | 51 | 71.8% (83.6% ca thực thi) |
| Failed | 10 | 14.1% |
| Blocked | 10 | 14.1% |
| **Total Planned** | **71** | **100.0%** |

<br>

- **Độ bao phủ yêu cầu (Requirements Coverage):** Đạt 100% (17/17 User Stories đều có ca kiểm thử tương ứng trên Ma trận RTM).
- **Mật độ lỗi tổng thể (Defect Density):** 0.14 lỗi / test case (10 lỗi / 71 ca kiểm thử).

Chi tiết phân tích biểu đồ trực quan và so sánh mật độ lỗi từng phân hệ được trình bày độc lập tại [Quality Dashboard](../10_Quality_Dashboard/Quality_Dashboard.md).

<br>

---

<a id="3-defect-highlights"></a>
## 3. Defect Highlights

Danh sách các lỗi nghiêm trọng nhất ảnh hưởng trực tiếp đến quyết định phát hành sản phẩm:

- [BUG-06](../08_Bugs_Report/BUG-06.md): Nhấp nút Finish tại Checkout Bước 2 gây lỗi ngoại lệ Runtime `TypeError: La.cesetRart is not a function`, làm sập hoàn toàn luồng hoàn tất đơn hàng. (Status: Open / Critical)

- [BUG-04](../08_Bugs_Report/BUG-04.md): Hệ thống cho phép thanh toán giỏ hàng rỗng $0.00 mà không hiển thị cảnh báo hay chặn chuyển hướng. (Status: Open / High)

- [BUG-05](../08_Bugs_Report/BUG-05.md): Dữ liệu nhập vào ô Last Name bị ghi đè vào state First Name, chặn đứng quy trình thanh toán của problem_user. (Status: Open / High)

- [BUG-03](../08_Bugs_Report/BUG-03.md): Nút Remove không hoạt động khi xóa sản phẩm Fleece Jacket khỏi giỏ hàng đối với problem_user. (Status: Open / High)

- [BUG-09](../08_Bugs_Report/BUG-09.md): Cookie phiên session-username thiếu cờ bảo mật HttpOnly và Secure, gây nguy cơ rò rỉ phiên làm việc. (Status: Open / High)

<br>

---

<a id="4-go--no-go-recommendation"></a>
## 4. Go / No-Go Recommendation

Dựa trên cây quyết định phát hành tiêu chuẩn (Decision tree: Go/No-go logic):

**1. Tất cả các lỗi Critical đã được giải quyết chưa?**
- Chưa (No): Lỗi Critical BUG-06 vẫn đang mở, gây crash hoàn toàn giao dịch thanh toán khi người dùng nhấn Finish.
- **Phán quyết Production:** **No-Go** (Dừng phát hành ra môi trường thực tế).

**2. Có lỗi High nào chưa được xử lý không?**
- Có (Yes): Còn 4 lỗi High (BUG-03, BUG-04, BUG-05, BUG-09), tuy nhiên các lỗi này chỉ kích hoạt trên các tài khoản persona lỗi (problem_user, error_user), trong khi luồng standard_user vẫn hoạt động đạt 100%.
- **Phán quyết Staging / Internal Demo:** **Go with Reservations** (Cho phép trình diễn nội bộ) với điều kiện người dùng tuân thủ các giải pháp né lỗi đã công bố.

<br>

---

<a id="5-known-issues-and-deferred-bugs"></a>
## 5. Known Issues and Deferred Bugs

Bảng theo dõi các lỗi đã biết được bảo lưu hoặc tạm hoãn sang chu kỳ tiếp theo:

| Bug ID | Summary | Severity | Status | Workaround |
|:---:|:---|:---:|:---:|:---|
| [BUG-06](../08_Bugs_Report/BUG-06.md) | Sập luồng runtime khi nhấn Finish đối với error_user | Critical | Known Issue | Sử dụng tài khoản standard_user để mua hàng. |
| [BUG-03](../08_Bugs_Report/BUG-03.md) | Nút Remove không xóa được Fleece Jacket trong giỏ | High | Deferred | Mở Sidebar chọn Reset App State để xóa giỏ hàng. |
| [BUG-04](../08_Bugs_Report/BUG-04.md) | Cho phép thanh toán đơn hàng rỗng $0.00 | High | Deferred | Thêm ít nhất 1 sản phẩm vào giỏ trước khi Checkout. |
| [BUG-05](../08_Bugs_Report/BUG-05.md) | Không điền được Last Name tại Checkout Bước 1 | High | Deferred | Sử dụng tài khoản standard_user để đặt hàng. |
| [BUG-09](../08_Bugs_Report/BUG-09.md) | Cookie phiên thiếu cờ HttpOnly và Secure | High | Deferred | Đăng xuất ngay khi kết thúc phiên; không dùng máy công cộng. |
| [BUG-01](../08_Bugs_Report/BUG-01.md) | Hình ảnh sản phẩm hiển thị ảnh chó 404 cho problem_user | Medium | Known Issue | Đăng nhập tài khoản standard_user để xem ảnh chuẩn. |
| [BUG-02](../08_Bugs_Report/BUG-02.md) | Sắp xếp sản phẩm bắn popup alert Sorting is broken! | Medium | Known Issue | Nhấn OK để đóng alert; tránh đổi sắp xếp khi dùng error_user. |
| [BUG-07](../08_Bugs_Report/BUG-07.md) | Menu About trong Sidebar trỏ nhầm link 404 | Medium | Known Issue | Truy cập trực tiếp địa chỉ chính thức https://saucelabs.com/. |
| [BUG-08](../08_Bugs_Report/BUG-08.md) | Vòng lặp trễ 5.09s làm treo giao diện danh mục | Medium | Deferred | Chờ đủ 5.1s để trang tải xong hoặc dùng standard_user. |
| [BUG-10](../08_Bugs_Report/BUG-10.md) | Lệch vị trí icon giỏ hàng và nút Checkout | Low | Won't Fix | Không ảnh hưởng chức năng; vẫn click chuột bình thường. |

<br>

---

<a id="6-conclusion"></a>
## 6. Conclusion

Báo cáo tổng kết kiểm thử Vòng 1 phản ánh trung thực năng lực vận hành và các rủi ro kỹ thuật hiện tại của SauceDemo. Hệ thống chứng minh tính ổn định cao ở luồng người dùng tiêu chuẩn nhưng xuất hiện các điểm gãy nghiêm trọng ở các kịch bản ngoại lệ.

Đội ngũ kiểm thử khuyến nghị Developer ưu tiên xử lý dứt điểm BUG-06 và BUG-05 trong Sprint 2 trước khi tiến hành đợt kiểm thử hồi quy (Regression Test) để tái đánh giá điều kiện phát hành chính thức.
