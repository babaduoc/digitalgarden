---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/9-luu-tru-tien-do/tien-do-web-etz/","title":"🚀 BẢNG NGHIỆM THU (UAT) WEB ETZ","dg-note-properties":{"cssclasses":"dashboard","title":"🚀 BẢNG NGHIỆM THU (UAT) WEB ETZ","cap_nhat":"2026-03-31","loai":"Quan_Ly_Tien_Do"}}
---


# 🚀 BẢNG NGHIỆM THU (UAT) WEB ETZ (KHOTOT.VN)
> **Trạng thái cốt lõi:** Developer (IT) đã bàn giao 100% Code tính năng. Đang thuộc Phase NGHIỆM THU (UAT) bởi Ban Quản Quản Trị Khotot.vn.
> **Ngày cập nhật:** 31/03/2026 | **Phiên bản:** v1.1 (Chuyển sang Giai đoạn Nghiệm thu)

> [!important] 🎯 HƯỚNG DẪN TEST DÀNH CHO SẾP (VÀ ADMIN)
> Cột lập trình đã xong, giờ là việc của sếp ở **Cột Kết Quả Test (QC/UAT)**:
> 1. Tính năng nào sếp test chạy trơn tru, không lỗi: Sếp gõ chữ `[PASS]` xanh lè vào cột cuối.
> 2. Tính năng nào thao tác bị đơ, hiển thị ngu, sai luồng logic: Sếp gõ thẻ cực gắt `[BUG: + Mô tả nhanh lỗi]` để quăng lại cho Dev đập đi làm lại.
> 3. Tuyệt đối không thoả hiệp, UAT là khâu quyết định sự sống còn của Web!

---

## 🏛️ GIAI ĐOẠN 1: TỔNG QUẢN TRỊ KHO TỔNG (DSS)
🌍 **Tên miền:** `dss.khotot.vn` | **Tiến độ Dev Code:** `[====================] 100%`
🕵️‍♂️ **Tiến độ Kiểm_Thử_Chất_Lượng (UAT):** `[                    ] 0%` (Chờ sếp Test)

| Nhóm chức năng            | Tên tính năng chi tiết                                                          | Trạng thái Code  | Kết Quả Test (Sếp Điền) |
| ------------------------- | ------------------------------------------------------------------------------- | :--------------: | ----------------------- |
| **1. Đăng nhập xác thực** | Đăng nhập bằng số điện thoại (hoặc tài khoản email)                             | [x] Dev Hoàn Tất |                         |
|                           | Phân quyền chức năng theo module, Theo kho                                      | [x] Dev Hoàn Tất |                         |
| **2. Quản lý người dùng** | Bộ lọc tìm kiếm theo tên                                                        | [x] Dev Hoàn Tất |                         |
|                           | Xem/ thêm/ xóa/ sửa employee DSS (phân quyền)                                   | [x] Dev Hoàn Tất |                         |
|                           | Xem/ thêm/ xóa/ sửa MD                                                          | [x] Dev Hoàn Tất |                         |
|                           | Xem/ thêm/ xóa/ sửa/ duyệt SD (On/off duyệt)                                    | [x] Dev Hoàn Tất |                         |
|                           | Danh sách riêng DSS, MD, SD: Tên, SDT, Địa chỉ, Ngày tạo, Đăng nhập cuối, GD... | [x] Dev Hoàn Tất |                         |
|                           | Bộ lọc: theo vai trò, trạng thái (hoạt động / chưa KQ / khóa)                   | [x] Dev Hoàn Tất |                         |
|                           | Ghi log thay đổi thông tin người dùng                                           | [x] Dev Hoàn Tất |                         |
| **3. Quản lý danh mục**   | Bộ lọc tìm kiếm theo tên                                                        | [x] Dev Hoàn Tất |                         |
|                           | Xem/ thêm/ xóa/ sửa danh mục theo 2 tầng (VD: Tivi -> Xiaomi)                   | [x] Dev Hoàn Tất |                         |
|                           | List danh sách sản phẩm thuộc danh mục                                          | [x] Dev Hoàn Tất |                         |
| **4. Quản lý sản phẩm**   | Lọc theo tên/ sku/ kho/ Tỉnh thành/ Đang bán/ Tạm ẩn                            | [x] Dev Hoàn Tất |                         |
|                           | Xem/thêm/xóa/sửa (DSS Không cho tạo trùng)                                      | [x] Dev Hoàn Tất |                         |
|                           | Cho phép gắn nhãn sản phẩm (nổi bật, hàng mới lên X ngày)                       | [x] Dev Hoàn Tất |                         |
|                           | Log thay đổi giá/khuyến mãi theo thời gian                                      | [x] Dev Hoàn Tất |                         |
|                           | Cập nhật nhanh Tên/giá/giá Km hàng loạt bằng excel                              | [x] Dev Hoàn Tất |                         |
| **5. Phê duyệt SP MD**    | Bộ lọc SP theo tên/ MD                                                          | [x] Dev Hoàn Tất |                         |
|                           | Xem/ thêm/ duyệt/ sản phẩm phân phối cho SD                                     | [x] Dev Hoàn Tất |                         |
|                           | Luồng duyệt: MD tạo SP -> DSS nhận YC -> Duyệt/từ chối phản hồi                 | [x] Dev Hoàn Tất |                         |
|                           | Duyệt nhiều sản phẩm cùng lúc                                                   | [x] Dev Hoàn Tất |                         |
| **6. Quản lý kho DSS**    | Bộ lọc tìm kiếm theo tên                                                        | [x] Dev Hoàn Tất |                         |
|                           | Xem/ thêm/ xóa/ sửa Kho DSS                                                     | [x] Dev Hoàn Tất |                         |
|                           | **Cảnh báo tồn kho thấp với từng SKU**                                          | [x] Dev Hoàn Tất |                         |
|                           | Cập nhật số lượng tồn kho SP theo kho                                           | [x] Dev Hoàn Tất |                         |
|                           | Tạo phiếu nhập / xuất kho theo SKU (phân loại)                                  | [x] Dev Hoàn Tất |                         |
|                           | Import phiếu nhập hàng loạt bằng Excel                                          | [x] Dev Hoàn Tất |                         |
|                           | Lịch sử nhập/ xuất kho                                                          | [x] Dev Hoàn Tất |                         |
| **7. Quản lý ĐH DSS**     | Lọc theo sdt/ mã đơn/Thời gian/Chờ xử lý / Đang giao / Hoàn tất/ Hủy            | [x] Dev Hoàn Tất |                         |
|                           | Xem/ thêm đơn hàng mới                                                          | [x] Dev Hoàn Tất |                         |
|                           | Sửa/ cập nhật trạng thái đơn hàng cũ                                            | [x] Dev Hoàn Tất |                         |
|                           | Xem lịch sử thao tác sửa đơn                                                    | [x] Dev Hoàn Tất |                         |
| **8. Quản lý ĐH MD**      | Xem/ kiểm duyệt đơn hàng MD (read-only)                                         | [x] Dev Hoàn Tất |                         |
|                           | Bộ lọc tìm kiếm đa dạng, theo kho                                               | [x] Dev Hoàn Tất |                         |
| **9. Quản lý KM**         | Xem/ thêm/ xóa/ sửa/ copy giảm giá (Thời gian/ Combo/ Giá trị)                  | [x] Dev Hoàn Tất |                         |
|                           | KM theo thời gian/ KM theo kho                                                  | [x] Dev Hoàn Tất |                         |
|                           | KM theo giá trị (MD thấy popup, ĐK chạy theo)                                   | [x] Dev Hoàn Tất |                         |
|                           | KM theo combo DSS (MD thấy popup, ĐK chạy theo)                                 | [x] Dev Hoàn Tất |                         |
|                           | Hẹn lịch lên KM / Lưu lịch sử / Tự ẩn sau khi hết hạn                           | [x] Dev Hoàn Tất |                         |
| **10. Cài đặt hệ thống**  | Phí ship, OTP, Giao diện liên hệ... (nếu có)                                    | [x] Dev Hoàn Tất |                         |
|                           | Tùy chọn xác thực đăng ký tài khoản OTP/SMS/ Duyệt SD                           | [x] Dev Hoàn Tất |                         |
|                           | Cài sdt nhận thông báo có đơn hàng mới qua zalo (10 sdt)                        | [x] Dev Hoàn Tất |                         |
|                           | Cài cảnh báo DSS & MD đơn chưa xử lý                                            | [x] Dev Hoàn Tất |                         |
|                           | Cài Quy tắc gợi ý sản phẩm liên quan                                            | [x] Dev Hoàn Tất |                         |
| **11. Thông báo & QC**    | Banner quảng cáo của DSS cho MD/SD/All                                          | [x] Dev Hoàn Tất |                         |
|                           | Tạo thông báo đến MD/SD                                                         | [x] Dev Hoàn Tất |                         |
|                           | Xem Danh sách “đã đọc” để check MD                                              | [x] Dev Hoàn Tất |                         |
| **12. Báo cáo**           | Tổng hợp doanh thu, lượng người online MD, SD                                   | [x] Dev Hoàn Tất |                         |

---

## 🏭 GIAI ĐOẠN 2: FRONT-END NHÀ PHÂN PHỐI (MD)
🌍 **Tên miền:** `md.khotot.vn` | **Tiến độ Dev Code:** `[====================] 100%`
🕵️‍♂️ **Tiến độ Kiểm_Thử_Chất_Lượng (UAT):** `[                    ] 0%` (Chờ sếp Test)

| Nhóm chức năng | Tên tính năng chi tiết | Trạng thái Code | Kết Quả Test (Sếp Điền) |
|---|---|:---:|---|
| **1. Đăng nhập** | Được DSS cấp tài khoản, log in bằng sđt/email | [x] Dev Hoàn Tất | |
| | Phân giao diện và chức năng xử lý theo vai trò MD | [x] Dev Hoàn Tất | |
| **2. Quản lý Sản phẩm** | Xem ds sản phẩm DSS cấp quyền, chọn thêm vào kho của mình | [x] Dev Hoàn Tất | |
| | MD Tạo sản phẩm mới và gửi DSS phê duyệt (Không trùng tên) | [x] Dev Hoàn Tất | |
| | Lọc Đang bán/ Tạm ẩn/ Chờ duyệt | [x] Dev Hoàn Tất | |
| | Ẩn tạm thời SP khỏi danh mục mà không xóa | [x] Dev Hoàn Tất | |
| **3. Quản lý kho MD** | Cập nhật số lượng tồn kho (do DSS cấp 1 kho định danh) | [x] Dev Hoàn Tất | |
| | Phiếu xuất/nhập, import excel | [x] Dev Hoàn Tất | |
| | Tra cứu lịch sử nhập xuất tuần/ ngày/ tháng | [x] Dev Hoàn Tất | |
| | Xem banner DSS và đăng ký KM theo DSS | [x] Dev Hoàn Tất | |
| **4. Xử lý Đơn hàng** | SD đặt hàng -> Gửi thông báo zalo cho MD | [x] Dev Hoàn Tất | |
| | Bảng đơn hàng chờ xử lý | [x] Dev Hoàn Tất | |
| | In phiếu, chọn Vận chuyển (GHTK/Viettel) - Đẩy Status | [x] Dev Hoàn Tất | |
| | Khách nhận hàng -> Hoàn tất -> Trừ tồn kho thực tế | [x] Dev Hoàn Tất | |
| **5. Tương tác báo cáo**| Popup đơn chưa xử lý, Thông báo zalo/web từ DSS | [x] Dev Hoàn Tất | |
| | Doanh số / Tỷ lệ hoàn tất / Tồn nhanh / SP Best-seller từ SD | [x] Dev Hoàn Tất | |
| **6. Cài đặt MD** | Cài sđt nhận Zalo, đổi địa chỉ lấy hàng (API Shipping), đổi pass | [x] Dev Hoàn Tất | |

---

## 🛒 GIAI ĐOẠN 3: FONT-END ĐẠI LÝ LẺ / KHÁCH HÀNG (SD)
🌍 **Tên miền:** `khotot.vn` | **Tiến độ Dev Code:** `[====================] 100%`
🕵️‍♂️ **Tiến độ Kiểm_Thử_Chất_Lượng (UAT):** `[                    ] 0%` (Chờ sếp Test)

| Nhóm chức năng | Tên tính năng chi tiết | Trạng thái Code | QC / Ghi chú Test |
|---|---|:---:|---|
| **1. Đăng nhập / ĐK** | Zalo OTP / SĐT. | [x] Dev Hoàn Tất | |
| | Thêm địa chỉ nhận hàng mặc định | [x] Dev Hoàn Tất | |
| | Cập nhật hồ sơ (chứng chỉ hành nghề, CCCD) | [x] Dev Hoàn Tất | |
| | Tùy chọn tài khoản Chờ duyệt / Đã duyệt (từ DSS) | [x] Dev Hoàn Tất | |
| **2. Mua hàng (UX)** | Lọc SP theo giá, kho, KM - Xem chi tiết tồn kho khả dụng | [x] Dev Hoàn Tất | |
| | Wishlist / mua lại nhanh | [x] Dev Hoàn Tất | |
| | Gợi ý SP liên quan, cùng danh mục | [x] Dev Hoàn Tất | |
| **3. Thanh toán** | Giỏ hàng, Ghi chú đơn -> Thanh toán (COD/Online/Cửa Hàng) | [x] Dev Hoàn Tất | |
| | Xác nhận OTP, Nhận Zalo OA confirm | [x] Dev Hoàn Tất | |
| | Quét QR tại Outlet Khotot | [x] Dev Hoàn Tất | |
| **4. QL Đơn hàng SD** | Track: Đã xác nhận / Đang giao / Đã giao | [x] Dev Hoàn Tất | |
| | Ấn hủy đơn (chỉ khi đang "Chờ xử lý") | [x] Dev Hoàn Tất | |
| | Lịch sử mua hàng, mã vận đơn | [x] Dev Hoàn Tất | |

---

> [!check] 1 CHỮ PASS - BƯỚC SANG TRANG MỚI
> Sếp nhớ nhé, dev đẻ ra code, sếp mới là người gọt code. Bảng này đã được tôi chuyển thể thành Format Nghiệm Thu. Cứ xong một luồng, sếp quất chữ `PASS` vào là đẹp. Chúc sếp Test ít Bug!
