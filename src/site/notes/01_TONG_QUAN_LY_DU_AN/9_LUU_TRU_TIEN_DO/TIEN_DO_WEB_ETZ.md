---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/9-luu-tru-tien-do/tien-do-web-etz/","title":"🚀 BẢNG THEO DÕI TIẾN ĐỘ CODE WEB ETZ","dg-note-properties":{"cssclasses":"dashboard","title":"🚀 BẢNG THEO DÕI TIẾN ĐỘ CODE WEB ETZ","cap_nhat":"2026-03-31","loai":"Quan_Ly_Tien_Do"}}
---


# 🚀 BẢNG THEO DÕI TIẾN ĐỘ CODE WEB ETZ (KHOTOT.VN)
> **Ngày thiết lập AI Tracking:** 31/03/2026 | **Phiên bản:** v1.0

> [!warning] HƯỚNG DẪN DÀNH CHO TEAM IT CẬP NHẬT TRẠNG THÁI
> - Cột **Xong (Checkbox)**: Nhấn tick `[x]` khi chức năng đã code & deploy thành công.
> - Cột **Kết Quả Test (QC/UAT)**: Ghi `[PASS]` nếu Kế toán, Admin vận hành hoặc Sếp test chạy mượt. Ghi `[BUG: ...]` nếu có lỗi cần fix lại.
> - Bất kỳ khi nào có cập nhật bôi đỏ tên chức năng hoặc check tính năng, Bảng `Tiến độ` ngoài `index.md` sẽ bị tự đánh dấu để sếp vào xem.

---

## 🏛️ GIAI ĐOẠN 1: TỔNG QUẢN TRỊ KHO TỔNG (DSS)
🌍 **Tên miền:** `dss.khotot.vn` | **Tiến độ (Demo):** `[==========          ] 50%`

| Nhóm chức năng | Tên tính năng chi tiết | Trạng thái Dev | Kết Quả Test / Ghi chú |
|---|---|:---:|---|
| **1. Đăng nhập xác thực** | Đăng nhập bằng số điện thoại (hoặc tài khoản email) | [ ] Chờ xử lý | |
| | Phân quyền chức năng theo module, Theo kho | [ ] Chờ xử lý | |
| **2. Quản lý người dùng** | Bộ lọc tìm kiếm theo tên | [ ] Chờ xử lý | |
| | Xem/ thêm/ xóa/ sửa employee DSS (phân quyền) | [ ] Chờ xử lý | |
| | Xem/ thêm/ xóa/ sửa MD | [ ] Chờ xử lý | |
| | Xem/ thêm/ xóa/ sửa/ duyệt SD (On/off duyệt) | [ ] Chờ xử lý | |
| | Danh sách riêng DSS, MD, SD: Tên, SDT, Địa chỉ, Ngày tạo, Đăng nhập cuối, GD... | [ ] Chờ xử lý | |
| | Bộ lọc: theo vai trò, trạng thái (hoạt động / chưa KQ / khóa) | [ ] Chờ xử lý | |
| | Ghi log thay đổi thông tin người dùng | [ ] Chờ xử lý | |
| **3. Quản lý danh mục** | Bộ lọc tìm kiếm theo tên | [ ] Chờ xử lý | |
| | Xem/ thêm/ xóa/ sửa danh mục theo 2 tầng (VD: Tivi -> Xiaomi) | [ ] Chờ xử lý | |
| | List danh sách sản phẩm thuộc danh mục | [ ] Chờ xử lý | |
| **4. Quản lý sản phẩm** | Lọc theo tên/ sku/ kho/ Tỉnh thành/ Đang bán/ Tạm ẩn | [ ] Chờ xử lý | |
| | Xem/thêm/xóa/sửa (DSS Không cho tạo trùng) | [ ] Chờ xử lý | |
| | Cho phép gắn nhãn sản phẩm (nổi bật, hàng mới lên X ngày) | [ ] Chờ xử lý | |
| | Log thay đổi giá/khuyến mãi theo thời gian | [ ] Chờ xử lý | |
| | Cập nhật nhanh Tên/giá/giá Km hàng loạt bằng excel | [ ] Chờ xử lý | |
| **5. Phê duyệt SP MD** | Bộ lọc SP theo tên/ MD | [ ] Chờ xử lý | |
| | Xem/ thêm/ duyệt/ sản phẩm phân phối cho SD | [ ] Chờ xử lý | |
| | Luồng duyệt: MD tạo SP -> DSS nhận YC -> Duyệt/từ chối phản hồi | [ ] Chờ xử lý | |
| | Duyệt nhiều sản phẩm cùng lúc | [ ] Chờ xử lý | |
| **6. Quản lý kho DSS** | Bộ lọc tìm kiếm theo tên | [ ] Chờ xử lý | |
| | Xem/ thêm/ xóa/ sửa Kho DSS | [ ] Chờ xử lý | |
| | **Cảnh báo tồn kho thấp với từng SKU** | [ ] Chờ xử lý | |
| | Cập nhật số lượng tồn kho SP theo kho | [ ] Chờ xử lý | |
| | Tạo phiếu nhập / xuất kho theo SKU (phân loại) | [ ] Chờ xử lý | |
| | Import phiếu nhập hàng loạt bằng Excel | [ ] Chờ xử lý | |
| | Lịch sử nhập/ xuất kho | [ ] Chờ xử lý | |
| **7. Quản lý ĐH DSS** | Lọc theo sdt/ mã đơn/Thời gian/Chờ xử lý / Đang giao / Hoàn tất/ Hủy | [ ] Chờ xử lý | |
| | Xem/ thêm đơn hàng mới | [ ] Chờ xử lý | |
| | Sửa/ cập nhật trạng thái đơn hàng cũ | [ ] Chờ xử lý | |
| | Xem lịch sử thao tác sửa đơn | [ ] Chờ xử lý | |
| **8. Quản lý ĐH MD** | Xem/ kiểm duyệt đơn hàng MD (read-only) | [ ] Chờ xử lý | |
| | Bộ lọc tìm kiếm đa dạng, theo kho | [ ] Chờ xử lý | |
| **9. Quản lý KM** | Xem/ thêm/ xóa/ sửa/ copy giảm giá (Thời gian/ Combo/ Giá trị) | [ ] Chờ xử lý | |
| | KM theo thời gian/ KM theo kho | [ ] Chờ xử lý | |
| | KM theo giá trị (MD thấy popup, ĐK chạy theo) | [ ] Chờ xử lý | |
| | KM theo combo DSS (MD thấy popup, ĐK chạy theo) | [ ] Chờ xử lý | |
| | Hẹn lịch lên KM / Lưu lịch sử / Tự ẩn sau khi hết hạn | [ ] Chờ xử lý | |
| **10. Cài đặt hệ thống** | Phí ship, OTP, Giao diện liên hệ... (nếu có) | [ ] Chờ xử lý | |
| | Tùy chọn xác thực đăng ký tài khoản OTP/SMS/ Duyệt SD | [ ] Chờ xử lý | |
| | Cài sdt nhận thông báo có đơn hàng mới qua zalo (10 sdt) | [ ] Chờ xử lý | |
| | Cài cảnh báo DSS & MD đơn chưa xử lý | [ ] Chờ xử lý | |
| | Cài Quy tắc gợi ý sản phẩm liên quan | [ ] Chờ xử lý | |
| **11. Thông báo & QC** | Banner quảng cáo của DSS cho MD/SD/All | [ ] Chờ xử lý | |
| | Tạo thông báo đến MD/SD | [ ] Chờ xử lý | |
| | Xem Danh sách “đã đọc” để check MD | [ ] Chờ xử lý | |
| **12. Báo cáo** | Tổng hợp doanh thu, lượng người online MD, SD | [ ] Chờ xử lý | |

---

## 🏭 GIAI ĐOẠN 2: FRONT-END NHÀ PHÂN PHỐI (MD)
🌍 **Tên miền:** `md.khotot.vn` | **Tiến độ (Demo):** `[=                   ] 0%`

| Nhóm chức năng | Tên tính năng chi tiết | Trạng thái | Lịch sử / Ghi chú Test |
|---|---|:---:|---|
| **1. Đăng nhập** | Được DSS cấp tài khoản, log in bằng sđt/email | [ ] Chờ xử lý | |
| | Phân giao diện và chức năng xử lý theo vai trò MD | [ ] Chờ xử lý | |
| **2. Quản lý Sản phẩm** | Xem ds sản phẩm DSS cấp quyền, chọn thêm vào kho của mình | [ ] Chờ xử lý | |
| | MD Tạo sản phẩm mới và gửi DSS phê duyệt (Không trùng tên) | [ ] Chờ xử lý | |
| | Lọc Đang bán/ Tạm ẩn/ Chờ duyệt | [ ] Chờ xử lý | |
| | Ẩn tạm thời SP khỏi danh mục mà không xóa | [ ] Chờ xử lý | |
| **3. Quản lý kho MD** | Cập nhật số lượng tồn kho (do DSS cấp 1 kho định danh) | [ ] Chờ xử lý | |
| | Phiếu xuất/nhập, import excel | [ ] Chờ xử lý | |
| | Tra cứu lịch sử nhập xuất tuần/ ngày/ tháng | [ ] Chờ xử lý | |
| | Xem banner DSS và đăng ký KM theo DSS | [ ] Chờ xử lý | |
| **4. Xử lý Đơn hàng** | SD đặt hàng -> Gửi thông báo zalo cho MD | [ ] Chờ xử lý | |
| | Bảng đơn hàng chờ xử lý | [ ] Chờ xử lý | |
| | In phiếu, chọn Vận chuyển (GHTK/Viettel) - Đẩy Status | [ ] Chờ xử lý | |
| | Khách nhận hàng -> Hoàn tất -> Trừ tồn kho thực tế | [ ] Chờ xử lý | |
| **5. Tương tác báo cáo**| Popup đơn chưa xử lý, Thông báo zalo/web từ DSS | [ ] Chờ xử lý | |
| | Doanh số / Tỷ lệ hoàn tất / Tồn nhanh / SP Best-seller từ SD | [ ] Chờ xử lý | |
| **6. Cài đặt MD** | Cài sđt nhận Zalo, đổi địa chỉ lấy hàng (API Shipping), đổi pass | [ ] Chờ xử lý | |

---

## 🛒 GIAI ĐOẠN 3: FONT-END ĐẠI LÝ LẺ / KHÁCH HÀNG (SD)
🌍 **Tên miền:** `khotot.vn` | **Tiến độ (Demo):** `[=                   ] 0%`

| Nhóm chức năng | Tên tính năng chi tiết | Trạng thái | QC / Ghi chú Test |
|---|---|:---:|---|
| **1. Đăng nhập / ĐK** | Zalo OTP / SĐT. | [ ] Chờ xử lý | |
| | Thêm địa chỉ nhận hàng mặc định | [ ] Chờ xử lý | |
| | Cập nhật hồ sơ (chứng chỉ hành nghề, CCCD) | [ ] Chờ xử lý | |
| | Tùy chọn tài khoản Chờ duyệt / Đã duyệt (từ DSS) | [ ] Chờ xử lý | |
| **2. Mua hàng (UX)** | Lọc SP theo giá, kho, KM - Xem chi tiết tồn kho khả dụng | [ ] Chờ xử lý | |
| | Wishlist / mua lại nhanh | [ ] Chờ xử lý | |
| | Gợi ý SP liên quan, cùng danh mục | [ ] Chờ xử lý | |
| **3. Thanh toán** | Giỏ hàng, Ghi chú đơn -> Thanh toán (COD/Online/Cửa Hàng) | [ ] Chờ xử lý | |
| | Xác nhận OTP, Nhận Zalo OA confirm | [ ] Chờ xử lý | |
| | Quét QR tại Outlet Khotot | [ ] Chờ xử lý | |
| **4. QL Đơn hàng SD** | Track: Đã xác nhận / Đang giao / Đã giao | [ ] Chờ xử lý | |
| | Ấn hủy đơn (chỉ khi đang "Chờ xử lý") | [ ] Chờ xử lý | |
| | Lịch sử mua hàng, mã vận đơn | [ ] Chờ xử lý | |

---

> [!tip] MẸO QUẢN LÝ
> Phân chia luồng công việc này trực tiếp cho Quản lý dự án để sếp nghiệm thu. Chức năng nào Test bị lỗi, sếp yêu cầu ghi Đỏ dòng `Ghi chú` là hoàn hảo.
