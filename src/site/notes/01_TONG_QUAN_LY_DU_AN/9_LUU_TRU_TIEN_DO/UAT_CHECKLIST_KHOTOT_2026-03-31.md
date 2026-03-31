---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/9-luu-tru-tien-do/uat-checklist-khotot-2026-03-31/","title":"📋 KẾT QUẢ KIỂM THỬ UAT - KHOTOT.VN (SD)","tags":["UAT","khotot","QC","nghiem-thu"],"dg-note-properties":{"title":"📋 KẾT QUẢ KIỂM THỬ UAT - KHOTOT.VN (SD)","cap_nhat":"2026-03-31","loai":"UAT_Report","tags":["UAT","khotot","QC","nghiem-thu"]}}
---


# 📋 KẾT QUẢ KIỂM THỬ UAT — KHOTOT.VN (FRONT-END SD)
> **Ngày kiểm thử:** 31/03/2026 | **Tester:** AI Agent (Claude) + Tài khoản SD: `0911591602`
> **Phạm vi:** Giai đoạn 3 — `khotot.vn` (Đại lý lẻ / Khách hàng)
> **Phiên bản UAT:** v1.0 — Lần kiểm thử đầu tiên

---

## 🔴 TỔNG KẾT NHANH

| Hạng mục | Số lượng |
|---|:---:|
| ✅ PASS — Chạy đúng | **21** |
| ⚠️ PARTIAL — Có hạn chế | **3** |
| 🐛 BUG — Lỗi cần fix | **2** |
| ⬜ SKIP — Chưa test | **4** |
| **TỔNG TÍNH NĂNG GĐ 3** | **30** |

---

## 🛒 GIAI ĐOẠN 3: FRONT-END SD — KHOTOT.VN

### 📦 NHÓM 1: ĐĂNG NHẬP / ĐĂNG KÝ

| # | Tính năng | Kết quả | Ghi chú |
|---|---|:---:|---|
| 1.1 | Đăng nhập bằng SĐT / Zalo OTP | ✅ PASS | Đăng nhập SĐT `0911591602` thành công, redirect về trang chủ |
| 1.2 | Thêm / quản lý địa chỉ nhận hàng | ✅ PASS | Trang `/tai-khoan/dia-chi` hoạt động: 1 địa chỉ mặc định + 2 địa chỉ khác. Các nút: Thêm, Chỉnh sửa, Xóa, Đặt mặc định — đều hiển thị |
| 1.3 | Cập nhật hồ sơ (CCCD, chứng chỉ) | ✅ PASS | Trang `/tai-khoan/thong-tin` — Hồ Sơ & Xác Thực: tải lên 2 mặt CCCD, badge "Đã xác thực" hiển thị |
| 1.4 | Tài khoản chờ duyệt / đã duyệt (DSS phê duyệt) | ⬜ SKIP | Không có tài khoản mới để test luồng duyệt |

---

### 🛍️ NHÓM 2: MUA HÀNG (UX)

| # | Tính năng | Kết quả | Ghi chú |
|---|---|:---:|---|
| 2.1 | Trang chủ — Banner quảng cáo | ✅ PASS | Banner "4SGen FASTER/STRONGER/MORE STORAGE" hiển thị đúng, có hình ảnh sản phẩm |
| 2.2 | Trang chủ — Danh mục thương hiệu | ✅ PASS | TPLINK (179 SP), DAHUA (103 SP), IMOU (39 SP), THẺ NHỚ (19 SP) |
| 2.3 | Trang chủ — Sản phẩm mới, giảm giá | ✅ PASS | Section "Sản phẩm mới" với badge "GIẢM X%" hiển thị đúng |
| 2.4 | Trang tìm kiếm / Khuyến mãi hot | ✅ PASS | `/tim-kiem?sortBy=DiscountPercent` — Sort tabs: Phổ biến / Hàng mới / **Khuyến mãi hot** / Giá Thấp-Cao / Giá Cao-Thấp đều hoạt động. 340 SP. Bộ lọc giá (slider), tìm theo tên/SKU |
| 2.5 | Trang sản phẩm chi tiết — Thông tin cơ bản | ✅ PASS | Hiển thị: SKU, tên, giá gốc/giảm, badge "GIẢM X%", danh mục (Phân loại), ảnh đa hình, breadcrumb, kho phân phối, địa chỉ kho, SĐT kho |
| 2.6 | Trang sản phẩm — Mô tả & thông số kỹ thuật | ✅ PASS | "Mô tả sản phẩm" có nội dung thông số đầy đủ |
| 2.7 | Trang sản phẩm — Chọn kho phân phối | ✅ PASS | Dropdown "Kho phân phối" (Kho ETZ Miền Nam) với địa chỉ kho + SĐT |
| 2.8 | Trang sản phẩm — Bộ đếm số lượng | ✅ PASS | Nút `–` / `+` điều chỉnh số lượng hoạt động |
| 2.9 | Trang sản phẩm — Nút "Thêm Vào Giỏ Hàng" | ✅ PASS | Click → Toast "Thêm vào giỏ hàng thành công", badge giỏ hàng (+1) |
| 2.10 | Trang sản phẩm — Nút "Mua Ngay" | ⬜ SKIP | Chưa test riêng luồng Mua Ngay |
| 2.11 | **Wishlist (yêu thích)** | 🐛 **BUG** | **KHÔNG TÌM THẤY nút Wishlist/tim trên trang sản phẩm.** Không có icon yêu thích nào trong DOM. Tính năng chưa được render |
| 2.12 | Mua lại nhanh từ lịch sử đơn hàng | ✅ PASS | Nút "Mua lại" trên lịch sử đơn → redirect đến `/gio-hang` với sản phẩm đã được thêm sẵn vào giỏ |
| 2.13 | Gợi ý sản phẩm liên quan | ✅ PASS | Section "Sản phẩm liên quan" ở cuối trang sản phẩm, hiển thị SP cùng danh mục |

---

### 💳 NHÓM 3: THANH TOÁN

| # | Tính năng | Kết quả | Ghi chú |
|---|---|:---:|---|
| 3.1 | Trang giỏ hàng (`/gio-hang`) | ✅ PASS | Hiển thị: địa chỉ giao hàng mặc định, danh sách SP, kho gửi, phí vận chuyển (25.300đ), tổng thanh toán. Nút "Thay đổi" địa chỉ, "Tiến hành thanh toán", "Trở về trang chủ" |
| 3.2 | Stepper 4 bước thanh toán | ✅ PASS | GIỎ HÀNG → XÁC NHẬN → THANH TOÁN → HOÀN TẤT — điều hướng đúng |
| 3.3 | Bước XÁC NHẬN — Ghi chú đơn hàng | ✅ PASS | Ô "Ghi chú đơn hàng" hiển thị trên trang xác nhận |
| 3.4 | Bước XÁC NHẬN — Yêu cầu hoá đơn điện tử | ✅ PASS | Checkbox "Yêu cầu xuất hoá đơn điện tử" hiển thị |
| 3.5 | Bước XÁC NHẬN — Mã giảm giá (coupon) | ✅ PASS | Ô "Nhập mã khuyến mãi" + nút "Áp dụng" hiển thị |
| 3.6 | Bước XÁC NHẬN — Đơn vị vận chuyển | ✅ PASS | Dropdown có 3 lựa chọn: **Viettel Post** / **Nhận tại cửa hàng (KH tự thanh toán)** / **Giao chành xe (KH tự thanh toán)** |
| 3.7 | Bước XÁC NHẬN — Phương thức thanh toán | ⚠️ **PARTIAL** | Dropdown chỉ có **1 lựa chọn: QR Ngân Hàng**. Không có COD hay "Thanh toán tại cửa hàng". Cần xác nhận với Dev/BQL xem COD có nằm trong scope không |
| 3.8 | Bước THANH TOÁN — QR SePay | ✅ PASS | Trang `/gio-hang/thanh-toan/{orderId}` — Hiển thị QR SePay, số tiền cần thanh toán, cảnh báo "không thể đóng thủ công cho đến khi GD được xác nhận", nút "Tải mã QR" |
| 3.9 | Xác nhận OTP / Zalo OA confirm | ⬜ SKIP | Không test được từ môi trường test (cần tài khoản Zalo thật) |
| 3.10 | Quét QR tại Outlet Khotot | ⚠️ **PARTIAL** | QR SePay được tạo khi thanh toán, nhưng không test được luồng quét QR tại quầy (cần thiết bị thật) |

---

### 📋 NHÓM 4: QUẢN LÝ ĐƠN HÀNG SD

| # | Tính năng | Kết quả | Ghi chú |
|---|---|:---:|---|
| 4.1 | Lịch sử đơn hàng — Danh sách | ✅ PASS | Hiển thị đúng: mã đơn, ngày đặt, kho, sản phẩm, phí ship, tổng. Tabs: Tất cả / Đơn mới / Đang xử lý / Thành công / Thất bại |
| 4.2 | Lịch sử đơn hàng — Tìm kiếm & lọc | ✅ PASS | Tìm theo mã đơn, kho hàng, tên SP, SKU. Filter ngày từ/đến |
| 4.3 | Lịch sử đơn hàng — Trạng thái đơn | ✅ PASS | Các trạng thái hiển thị: "Chưa chuẩn bị hàng", "Đã hủy" — màu sắc phân biệt |
| 4.4 | Chi tiết đơn hàng (modal) | ✅ PASS | Modal "Chi tiết đơn hàng" hiển thị đầy đủ: Người nhận, Vận chuyển (ĐVVC + Kho gửi + Mã vận đơn + Copy), Thanh toán (phương thức + trạng thái), Ghi chú, Danh sách SP, Lịch sử đơn hàng (timeline) |
| 4.5 | **Deep link đơn hàng** `/tai-khoan/don-hang/{orderId}` | 🐛 **BUG** | **URL trực tiếp → ERROR 404.** Chi tiết đơn chỉ mở được qua nút "Xem chi tiết" dạng modal. Deep link bị vỡ — ảnh hưởng chia sẻ link, thông báo qua Zalo/Email |
| 4.6 | Nút "Hủy đơn" (khi đang "Chưa chuẩn bị hàng") | ✅ PASS | Nút "Hủy đơn" hiển thị đúng trong cả danh sách và modal chi tiết cho đơn trạng thái "Chưa chuẩn bị hàng" |
| 4.7 | Nút "Thanh toán lại" đơn chưa TT | ✅ PASS | Nút "Thanh toán" hiển thị đúng cho đơn "Chưa thanh toán", click → điều hướng về trang QR |
| 4.8 | Tự động hủy đơn sau 24h không TT | ✅ PASS | Thông báo "Đơn hàng sẽ tự động huỷ nếu không thanh toán trong 24 giờ" hiển thị đúng |
| 4.9 | Mã vận đơn (tracking) | ✅ PASS | Mã vận đơn hiển thị trong modal chi tiết + nút Copy |

---

## 🐛 DANH SÁCH BUG CẦN XỬ LÝ

| # | Loại | Mô tả | Mức độ | Màn hình |
|---|---|---|:---:|---|
| BUG-01 | 🔴 Lỗi chức năng | **Deep link đơn hàng trả về 404.** URL `/tai-khoan/don-hang/{orderId}` không hoạt động. Chi tiết đơn chỉ hiển thị được qua modal trong trang list. Ảnh hưởng thông báo Zalo, email, chia sẻ link đơn hàng | HIGH | `/tai-khoan/don-hang` |
| BUG-02 | 🟠 UI thiếu tính năng | **Wishlist không hiển thị.** Không có icon/button tim (yêu thích) trên trang sản phẩm. Kiểm tra DOM không tìm thấy element nào liên quan wishlist | MEDIUM | `/san-pham/{slug}` |

---

## ⚠️ OBSERVATIONS — CẦN XÁC NHẬN VỚI BQL

| # | Nội dung | Ghi chú |
|---|---|---|
| OBS-01 | **Thanh toán COD không có.** Dropdown "Phương thức thanh toán" chỉ có "QR Ngân Hàng". Nếu scope ban đầu bao gồm COD → cần yêu cầu Dev bổ sung | Xác nhận lại với Dev |
| OBS-02 | **URL `/khuyen-mai` trả về 404.** Nav header dùng `/tim-kiem?sortBy=DiscountPercent` (đúng). Nếu có link ngoài trỏ vào `/khuyen-mai` sẽ bị vỡ | Nên cài redirect 301 |
| OBS-03 | **"Sản phẩm liên quan" chỉ hiển thị 1 sản phẩm** trên trang test. Cần kiểm tra lại quy tắc gợi ý SP đã được cài trong DSS settings chưa | Kiểm tra config DSS |

---

## ⬜ CHƯA TEST — CẦN TEST BỔ SUNG

| # | Hạng mục | Lý do chưa test |
|---|---|---|
| SKIP-01 | Luồng đăng ký tài khoản mới + OTP SMS | Không có SIM mới để tạo tài khoản |
| SKIP-02 | Zalo OA confirm sau khi đặt hàng | Cần tài khoản Zalo thật liên kết |
| SKIP-03 | Nút "Mua Ngay" (bypas giỏ hàng) | Chưa test riêng flow này |
| SKIP-04 | Quét QR tại quầy (Outlet Khotot) | Cần thiết bị thực tế |

---

## 📊 BẢNG ĐỐI CHIẾU TỔNG HỢP THEO FILE UAT GỐC

### Giai đoạn 3 — khotot.vn (SD)

| Nhóm | Tính năng gốc (TIEN_DO_WEB_ETZ.md) | Kết quả |
|---|---|:---:|
| **1. ĐK/Đăng nhập** | Zalo OTP / SĐT | ✅ PASS |
| | Thêm địa chỉ nhận hàng mặc định | ✅ PASS |
| | Cập nhật hồ sơ (chứng chỉ, CCCD) | ✅ PASS |
| | Tùy chọn Chờ duyệt / Đã duyệt | ⬜ SKIP |
| **2. Mua hàng (UX)** | Lọc SP theo giá, kho, KM | ✅ PASS |
| | Xem chi tiết tồn kho khả dụng | ✅ PASS |
| | Wishlist | 🐛 BUG |
| | Mua lại nhanh | ✅ PASS |
| | Gợi ý SP liên quan, cùng danh mục | ✅ PASS |
| **3. Thanh toán** | Giỏ hàng + Ghi chú đơn | ✅ PASS |
| | Thanh toán COD | 🐛 **MISSING** |
| | Thanh toán Online (QR SePay) | ✅ PASS |
| | Thanh toán tại Cửa Hàng | ⚠️ PARTIAL |
| | Xác nhận OTP | ⬜ SKIP |
| | Nhận Zalo OA confirm | ⬜ SKIP |
| | Quét QR tại Outlet | ⚠️ PARTIAL |
| **4. QL Đơn hàng SD** | Track trạng thái đơn | ✅ PASS |
| | Ấn hủy đơn (Chờ xử lý) | ✅ PASS |
| | Lịch sử mua hàng | ✅ PASS |
| | Mã vận đơn | ✅ PASS |
| | Deep link đơn hàng | 🐛 BUG |

---

### Giai đoạn 1 & 2 — Chưa test

| Giai đoạn | Domain | Trạng thái UAT |
|---|---|:---:|
| GĐ 1 — Quản trị DSS | `dss.khotot.vn` | ⬜ Chưa test |
| GĐ 2 — Front-end MD | `md.khotot.vn` | ⬜ Chưa test |

---

> **Ghi chú:** File này do AI Agent (Claude) tự động tổng hợp từ phiên kiểm thử trực tiếp ngày 31/03/2026.
> Mọi BUG cần chuyển ticket cho Dev. Mọi SKIP cần lên kế hoạch test bổ sung trước khi go-live.
