---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sd/sop-sd-khotot-thanh-toan/","title":"SOP-SD-03 | Thanh Toán (Checkout) — khotot.vn","dg-note-properties":{"title":"SOP-SD-03 | Thanh Toán (Checkout) — khotot.vn","cap_nhat":"2026-05-18","loai":"SOP","phong_ban":"Vận Hành","he_thong":"khotot.vn"}}
---


# SOP-SD-03 | Thanh Toán (Checkout) SD
> **Áp dụng cho:** Đại lý lẻ / Khách hàng (SD) tại `khotot.vn`
> **Phiên bản:** v1.1 | **Ngày tạo:** 31/03/2026 | **Cập nhật:** 18/05/2026
> **Nguồn:** Tổng hợp từ UAT kiểm thử thực tế (Phase 3 SD)
> **Thay đổi v1.1:** Thêm bước thu thập thông tin hóa đơn VAT tại trang Xác nhận đơn hàng

---

## 🎯 Mục đích
Hướng dẫn SD thực hiện quy trình thanh toán đơn hàng từ Giỏ hàng → Xác nhận → Chọn vận chuyển → Thanh toán QR.

---

## 📌 Thông tin truy cập
- **Giỏ hàng:** Biểu tượng 🛒 trên header hoặc `/gio-hang`
- **Thanh toán:** `/xac-nhan-don-hang`
- **Phương thức thanh toán hiện tại:** QR Ngân Hàng (SePay) *(COD chưa hỗ trợ)*
- **Đơn vị vận chuyển:** Viettel Post | Nhận tại cửa hàng | Giao chành xe

---

## 🔄 LUỒNG CHÍNH: Checkout Đầy Đủ

```mermaid
flowchart TD
    A([🛒 Có SP trong giỏ hàng]) --> B[Nhấn biểu tượng Giỏ hàng]
    B --> C[Trang Giỏ hàng hiển thị\nDanh sách SP, SL, Giá]
    C --> D{Kiểm tra giỏ hàng}
    D -- Cần điều chỉnh --> E[Thay đổi số lượng\nhoặc xóa SP không cần]
    E --> C
    D -- Ổn rồi --> F[Nhấn 'Thanh toán' / 'Đặt hàng']
    F --> G[Trang Xác nhận đơn hàng]
    G --> H[Chọn / Xác nhận\nĐịa chỉ nhận hàng]
    H --> I{Địa chỉ đúng?}
    I -- Không --> J[Nhấn 'Thay đổi địa chỉ'\nChọn địa chỉ khác]
    J --> H
    I -- Đúng --> K[Chọn Phương thức vận chuyển]
    K --> L{Chọn ĐVVC}
    L -- Viettel Post --> M1[Giao tận nhà\nPhí ship tính theo km]
    L -- Nhận tại cửa hàng --> M2[Đến cửa hàng\nKhotot nhận trực tiếp]
    L -- Giao chành xe --> M3[Giao qua chành\nPhù hợp đơn số lượng lớn]
    M1 & M2 & M3 --> N[Điền Ghi chú đơn hàng\nnếu có yêu cầu đặc biệt]
    N --> HD[Phần HÓA ĐƠN VAT\nBắt buộc chọn CÓ hoặc KHÔNG]
    HD -- KHÔNG --> HD_No[Đọc cảnh báo miễn trách nhiệm\nTick xác nhận không cần HĐ]
    HD -- CÓ --> HD_Yes{Chọn loại hóa đơn}
    HD_Yes -- Cá nhân --> HD_P[Điền: Họ tên + CCCD + Email]
    HD_Yes -- DN / HKD --> HD_B[Điền: Tên đơn vị + MST\n+ Địa chỉ + Email]
    HD_No & HD_P & HD_B --> O[Xem tóm tắt đơn:\nSP + Phí ship + Tổng thanh toán]
    O --> P[Nhấn 'Xác nhận đặt hàng']
    P --> Q[Màn hình QR Thanh Toán\nhiển thị mã QR SePay]
    Q --> R[SD mở app ngân hàng\nQuét mã QR]
    R --> S[Nhập số tiền đúng\nvà xác nhận chuyển khoản]
    S --> T{Thanh toán thành công?}
    T -- Thất bại --> U[⚠️ Kiểm tra:\n- Đủ số dư?\n- QR còn hạn?\nThử lại hoặc liên hệ MD]
    U --> R
    T -- Thành công --> V[Hệ thống xác nhận thanh toán\nĐơn hàng chuyển sang 'Đã xác nhận']
    V --> W[SD nhận xác nhận\nqua Zalo OA]
    W --> X([✅ Đặt hàng thành công])
```

---

## 🔄 LUỒNG PHỤ: Nhận tại Cửa Hàng (Quét QR Outlet)

```mermaid
flowchart TD
    A([▶ SD đến cửa hàng Khotot]) --> B[Nhân viên mở đơn hàng\ncần thanh toán trực tiếp]
    B --> C[Màn hình hiển thị\nQR Outlet Khotot]
    C --> D[SD quét QR bằng app ngân hàng]
    D --> E[Xác nhận thanh toán]
    E --> F[Đơn hàng hoàn tất\nNhận hàng ngay tại quầy]
    F --> G([✅ Giao dịch hoàn tất])
```

---

## 📋 Chi Tiết Màn Hình Xác Nhận Đơn Hàng

```
┌─────────────────────────────────────────────────┐
│            XÁC NHẬN ĐƠN HÀNG                    │
├─────────────────────────────────────────────────┤
│ 📍 ĐỊA CHỈ NHẬN HÀNG                            │
│    [Tên] — [SĐT]                                │
│    [Địa chỉ đầy đủ]          [Thay đổi]         │
├─────────────────────────────────────────────────┤
│ 🚚 PHƯƠNG THỨC VẬN CHUYỂN                        │
│    ○ Viettel Post      Phí: [X]đ                │
│    ○ Nhận tại cửa hàng  Phí: 0đ                 │
│    ○ Giao chành xe     Phí: [Thỏa thuận]        │
├─────────────────────────────────────────────────┤
│ 📝 GHI CHÚ ĐƠN HÀNG                             │
│    [Ô nhập ghi chú]                             │
├═════════════════════════════════════════════════╡
│ 🧾 HÓA ĐƠN VAT                                  │
│    Bạn có cần xuất hóa đơn VAT không?           │
│    ┌──────────┐  ┌────────────┐                 │
│    │  ✅ CÓ   │  │  ❌ KHÔNG  │                 │
│    └──────────┘  └────────────┘                 │
│    (Bắt buộc chọn — nút đặt hàng bị khóa)      │
│                                                 │
│    ── Khi chọn KHÔNG: ──                        │
│    ⚠️ Cảnh báo miễn trách nhiệm                 │
│    ☐ Tôi xác nhận không cần hóa đơn            │
│                                                 │
│    ── Khi chọn CÓ: ──                           │
│    Loại: ○ Cá nhân  ○ DN/HKD                    │
│    [Form tương ứng — xem mục bên dưới]          │
│    ☐ Lưu thông tin vào hồ sơ để dùng lần sau   │
├─────────────────────────────────────────────────┤
│ 💰 TÓM TẮT THANH TOÁN                           │
│    Tổng SP:          [X]đ                       │
│    Phí vận chuyển:   [X]đ                       │
│    Giảm giá:         [X]đ                       │
│    ─────────────────────                        │
│    TỔNG THANH TOÁN:  [X]đ                       │
├─────────────────────────────────────────────────┤
│         [ XÁC NHẬN ĐẶT HÀNG ]                   │
└─────────────────────────────────────────────────┘
```

---

## 🧾 Hướng Dẫn Phần Hóa Đơn VAT

> Phần này bắt buộc phải chọn trước khi đặt hàng. Nút **"Xác nhận đặt hàng"** bị khóa cho đến khi hoàn thành bước này.

### Trường hợp KHÔNG cần hóa đơn

Sau khi nhấn "KHÔNG", hệ thống hiển thị cảnh báo — SD phải tick xác nhận:

> ⚠️ **Khotot.vn sẽ không xuất hóa đơn VAT cho đơn hàng này.** Theo Nghị định 70/2025/NĐ-CP, hóa đơn chỉ được lập tại thời điểm giao hàng — không thể bổ sung sau khi đơn hoàn thành.
> ☐ *Tôi đã hiểu, xác nhận không cần hóa đơn*

### Trường hợp CÓ cần hóa đơn — Loại Cá nhân

| Trường | Bắt buộc | Ghi chú |
|---|---|---|
| Họ và tên người mua | ✅ | Tự điền từ hồ sơ nếu đã có |
| Số CCCD/CMND | ✅ | 12 chữ số |
| Email nhận hóa đơn điện tử | ✅ | Để nhận file hóa đơn |

### Trường hợp CÓ cần hóa đơn — Loại DN/HKD

| Trường | Bắt buộc | Ghi chú |
|---|---|---|
| Tên đơn vị (tên pháp lý đầy đủ) | ✅ | Tự điền từ hồ sơ nếu đã có |
| Mã số thuế (MST) | ✅ | 10 số (DN) hoặc 12 số (CCCD thay MST từ 01/07/2025) |
| Địa chỉ đăng ký kinh doanh | ✅ | Tự điền từ hồ sơ nếu đã có |
| Email nhận hóa đơn điện tử | ✅ | Để nhận file hóa đơn |

> **Lưu ý:** Nếu đã từng điền thông tin hóa đơn trước đây, hệ thống tự động điền sẵn và hiển thị: *"Đã điền từ hồ sơ — vui lòng kiểm tra lại"*. SD kiểm tra và chỉnh sửa nếu cần trước khi xác nhận.

---

## 📋 Các Phương Thức Vận Chuyển

| ĐVVC | Phí | Thời gian | Phù hợp với |
|---|---|---|---|
| **Viettel Post** | Tính theo km/KG | 1-3 ngày | Đơn hàng thông thường |
| **Nhận tại cửa hàng** | Miễn phí | Ngay lập tức | SD gần cửa hàng Khotot |
| **Giao chành xe** | Thỏa thuận | 1-5 ngày | Đơn số lượng lớn, tỉnh xa |

---

## ⚠️ Lưu ý quan trọng
- **Chỉ QR Ngân Hàng:** Hiện tại khotot.vn chưa hỗ trợ COD — mọi đơn phải thanh toán qua QR SePay
- **QR có thời hạn:** Mã QR thanh toán chỉ có hiệu lực trong thời gian nhất định — quét ngay sau khi đặt hàng
- **Đơn tự hủy:** Nếu không thanh toán trong thời hạn, đơn sẽ tự động hủy
- **Xác nhận Zalo:** Sau khi thanh toán thành công, SD nhận thông báo qua Zalo OA — kiểm tra để chắc chắn
- **Hóa đơn bắt buộc chọn:** Phần HÓA ĐƠN VAT phải được điền hoàn chỉnh trước khi đặt hàng — sau khi đơn hoàn thành **không thể yêu cầu bổ sung hóa đơn**
- **MST từ 01/07/2025:** Hộ cá thể không có MST riêng được dùng số CCCD (12 chữ số) thay thế

---

## 📞 Liên quan
- [[01_TONG_QUAN_LY_DU_AN/2_PHONG_VAN_HANH/SD/SOP_SD_KHOTOT_TimKiemMuaHang\|SOP-SD-02: Tìm Kiếm & Mua Hàng]]
- [[01_TONG_QUAN_LY_DU_AN/2_PHONG_VAN_HANH/SD/SOP_SD_KHOTOT_QuanLyDonHang\|SOP-SD-04: Quản Lý Đơn Hàng SD]]
