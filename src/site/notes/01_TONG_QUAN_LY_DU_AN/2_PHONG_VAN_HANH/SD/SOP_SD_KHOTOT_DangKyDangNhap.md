---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sd/sop-sd-khotot-dang-ky-dang-nhap/","title":"SOP-SD-01 | Đăng Ký & Đăng Nhập — khotot.vn","dg-note-properties":{"title":"SOP-SD-01 | Đăng Ký & Đăng Nhập — khotot.vn","cap_nhat":"2026-03-31","loai":"SOP","phong_ban":"Vận Hành","he_thong":"khotot.vn"}}
---


# SOP-SD-01 | Đăng Ký & Đăng Nhập SD
> **Áp dụng cho:** Đại lý lẻ / Khách hàng (SD) tại `khotot.vn`
> **Phiên bản:** v1.0 | **Ngày tạo:** 31/03/2026
> **Nguồn:** Tổng hợp từ UAT kiểm thử thực tế (Phase 3 SD)

---

## 🎯 Mục đích
Hướng dẫn SD (Đại lý lẻ/Khách hàng) thực hiện đăng ký tài khoản, đăng nhập, thiết lập hồ sơ và địa chỉ nhận hàng trên khotot.vn.

---

## 📌 Thông tin truy cập
- **URL:** `https://khotot.vn`
- **Phương thức đăng nhập:** Zalo OTP hoặc SĐT
- **Trạng thái tài khoản:** Chờ duyệt → Đã duyệt (do DSS phê duyệt)

---

## 🔄 LUỒNG 1: Đăng Ký Tài Khoản Mới

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Truy cập khotot.vn]
    B --> C[Nhấn 'Đăng ký' / 'Tài khoản']
    C --> D{Chọn phương thức đăng ký}
    D -- Zalo OTP --> E[Đăng nhập qua Zalo\ncho phép kết nối]
    D -- SĐT --> F[Nhập số điện thoại]
    F --> G[Nhận mã OTP qua SMS]
    G --> H[Nhập mã OTP xác thực]
    E & H --> I[Điền thông tin hồ sơ:\nHọ tên, Tên cửa hàng]
    I --> J[Upload: CCCD / Chứng chỉ hành nghề\nnếu hệ thống yêu cầu]
    J --> K[Thêm địa chỉ nhận hàng mặc định:\nTỉnh/Thành → Quận/Huyện → Phường → Số nhà]
    K --> L[Hoàn tất đăng ký]
    L --> M[Tài khoản ở trạng thái\n'Chờ duyệt']
    M --> N{DSS xem xét}
    N -- Duyệt --> O[Tài khoản 'Đã duyệt'\nSD có thể mua hàng]
    N -- Từ chối --> P[SD nhận thông báo\nvà lý do từ chối]
    P --> Q[Bổ sung thông tin / tài liệu]
    Q --> N
    O --> R([✅ Đăng ký thành công])
```

---

## 🔄 LUỒNG 2: Đăng Nhập Tài Khoản Hiện Có

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Truy cập khotot.vn]
    B --> C[Nhấn biểu tượng tài khoản\nhoặc 'Đăng nhập']
    C --> D{Chọn phương thức}
    D -- Zalo --> E[Nhấn 'Đăng nhập với Zalo'\nZalo mở ra xác nhận]
    D -- SĐT + OTP --> F[Nhập số điện thoại]
    F --> G[Nhận OTP qua SMS/Zalo]
    G --> H[Nhập mã OTP]
    E & H --> I{Tài khoản hợp lệ?}
    I -- Không --> J[⚠️ Thông báo lỗi\nKiểm tra SĐT / OTP]
    J --> C
    I -- Có --> K{Trạng thái tài khoản}
    K -- Chờ duyệt --> L[Hiển thị thông báo\n'Tài khoản đang chờ DSS duyệt']
    K -- Đã duyệt --> M[Vào trang chủ\nkhotot.vn đầy đủ tính năng]
    M --> N([✅ Đăng nhập thành công])
```

---

## 🔄 LUỒNG 3: Cập Nhật Hồ Sơ & Địa Chỉ

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Đăng nhập vào khotot.vn]
    B --> C[Nhấn biểu tượng tài khoản\n→ Hồ sơ / Tài khoản]
    C --> D{Cần cập nhật gì?}
    D -- Thông tin cá nhân --> E[Sửa: Tên, Tên cửa hàng\nSĐT liên hệ]
    D -- Chứng từ --> F[Upload lại CCCD / Chứng chỉ\nhành nghề mới]
    D -- Địa chỉ nhận hàng --> G[Vào mục 'Địa chỉ']
    G --> H{Hành động}
    H -- Thêm địa chỉ mới --> I[Điền địa chỉ đầy đủ\nĐặt làm mặc định nếu cần]
    H -- Sửa địa chỉ cũ --> J[Chọn địa chỉ → Sửa]
    H -- Xóa địa chỉ --> K[Chọn địa chỉ → Xóa\nKhông xóa được địa chỉ mặc định]
    E & F & I & J & K --> L[Lưu thay đổi]
    L --> M([✅ Hồ sơ đã cập nhật])
```

---

## ⚠️ Lưu ý quan trọng
- **Chờ duyệt:** Tài khoản mới sẽ bị giới hạn chức năng cho đến khi DSS duyệt — không mua được hàng
- **OTP hết hạn:** Mã OTP chỉ có hiệu lực trong **5 phút** — nếu hết hạn cần yêu cầu gửi lại
- **Zalo liên kết:** Nên đăng nhập qua Zalo để nhận thông báo đơn hàng nhanh nhất
- **Địa chỉ mặc định:** Luôn thiết lập ít nhất 1 địa chỉ mặc định để checkout nhanh hơn

---

## 📞 Liên quan
- [[01_TONG_QUAN_LY_DU_AN/2_PHONG_VAN_HANH/SD/SOP_SD_KHOTOT_TimKiemMuaHang\|SOP-SD-02: Tìm Kiếm & Mua Hàng]]
- [[01_TONG_QUAN_LY_DU_AN/2_PHONG_VAN_HANH/SD/SOP_SD_KHOTOT_ThanhToan\|SOP-SD-03: Thanh Toán (Checkout)]]
- [[01_TONG_QUAN_LY_DU_AN/9_LUU_TRU_TIEN_DO/UAT_CHECKLIST_KHOTOT_2026-03-31\|📋 UAT Checklist khotot.vn SD (31/03/2026)]]
