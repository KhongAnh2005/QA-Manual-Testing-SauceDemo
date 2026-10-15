### [BUG-02] Bộ lọc sắp xếp kích hoạt popup alert 'Sorting is broken!' và không sắp xếp lại đối với tài khoản error_user

| **Field** | **Value** |
|:---|:---|
| **Bug ID** | BUG-02 |
| **Title** | Bộ lọc sắp xếp kích hoạt popup alert 'Sorting is broken!' và không sắp xếp lại đối với tài khoản error_user |
| **Component** | Inventory Sorting |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | New |
| **Reporter** | QA - Khổng Đức Anh |
| **Date Logged** | 26/09/2026 |
| **Linked Test Case** | [TC-18](../07_Test_Execution_Result/07_Test_Execution_Results.md) |
| **Linked User Story** | [US-04](../01_Requirements/01_Requirement_Document_User_Stories.md) |
| **Linked Test Scenario** | [TS-08](../03_Test_Scenarios/03_Test_Scenarios_Document.md) |

---
#### 1. Description & Defect Overview

Trình duyệt bắn ra một popup alert chặn luồng người dùng với nội dung: 'Sorting is broken! This error has been reported to Backtrace.' và danh sách sản phẩm không được sắp xếp lại.

#### 2. Environment Details

- Operating System: macOS Sonoma (v14.4+)
- Browser: Google Chrome Desktop (v124+)
- User Account (Persona): error_user / Password: secret_sauce

#### 3. Preconditions

- Trình duyệt Chrome đã mở tại trang https://www.saucedemo.com/.
- Đăng nhập vào hệ thống bằng tài khoản persona error_user.

#### 4. Steps to Reproduce (Rule of 3 Verified)

1. Đăng nhập bằng tài khoản 'error_user' và password 'secret_sauce'.
2. Tại trang danh mục '/inventory.html', nhấp vào dropdown sắp xếp ('data-test=product-sort-container').
3. Chọn tùy chọn sắp xếp 'Price (low to high)'.

Quy tắc kiểm chứng (Rule of 3): Đã kiểm chứng lặp lại 3 lần liên tiếp và xảy ra nhất quán 100%.

#### 5. Expected Result vs Actual Result

| Expected Result | Actual Result |
|:---|:---|
| Danh sách sản phẩm được sắp xếp lại theo giá tiền tăng dần (\$7.99 -> \$49.99). Không có hộp thoại popup alert nào của trình duyệt xuất hiện làm gián đoạn người dùng. | Trình duyệt bắn ra một popup alert chặn luồng người dùng với nội dung: 'Sorting is broken! This error has been reported to Backtrace.' và danh sách sản phẩm không được sắp xếp lại. |

#### 6. Visual Evidence

![BUG-02 Evidence](../Evidence/Screenshots/TC-18%20-%20BUG-02_Error_User_Sort_Alert_Popup.png)

#### 7. Business Impact

- Severity (Medium): Ảnh hưởng đến luồng vận hành của phân hệ Inventory Sorting.
- Priority (Medium): Cần được ưu tiên khắc phục trong chu kỳ phát hành tương ứng.

Xem tổng quan tác động phát hành tại [Test Summary Report](../09_Test_Summary_Report/09_Test_Summary_Report.md#3-defect-highlights).
