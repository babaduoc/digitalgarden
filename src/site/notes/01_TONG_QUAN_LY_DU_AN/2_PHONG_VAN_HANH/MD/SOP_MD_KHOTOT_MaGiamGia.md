---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/md/sop-md-khotot-ma-giam-gia/","title":"SOP-MD-04 | Mã Giảm Giá & Khuyến Mãi — md.khotot.vn","dg-note-properties":{"title":"SOP-MD-04 | Mã Giảm Giá & Khuyến Mãi — md.khotot.vn","cap_nhat":"2026-03-31","loai":"SOP","phong_ban":"Vận Hành","he_thong":"md.khotot.vn"}}
---


# SOP-MD-04 | Mã Giảm Giá & Khuyến Mãi MD
> **Áp dụng cho:** Nhân viên/Admin vai trò MD tại `md.khotot.vn`
> **Phiên bản:** v1.0 | **Ngày tạo:** 31/03/2026
> **Nguồn:** Tổng hợp từ UAT kiểm thử thực tế

---

## 🎯 Mục đích
Hướng dẫn MD tạo và quản lý mã giảm giá (coupon) và chương trình khuyến mãi (CTKM) áp dụng cho khách hàng SD.

---

## 📌 Thông tin truy cập

| Module | URL | Sidebar |
|---|---|---|
| Mã giảm giá | `/app/sale/coupons` | BÁN HÀNG → Mã giảm giá |
| Khuyến mãi | `/app/sale/promotions` | BÁN HÀNG → Khuyến mãi |

---

## 🔄 LUỒNG 1: Tạo Mã Giảm Giá (Coupon Code)

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Vào BÁN HÀNG → Mã giảm giá]
    B --> C[Nhấn 'Thêm mã giảm giá' góc phải]
    C --> D[Modal 'Tạo chương trình khuyến mãi' hiện ra]
    D --> E{Cài đặt cơ bản}
    E --> F[Toggle 'Hiển thị công khai':\nBật = SD thấy mã trên web]
    F --> G[Toggle 'Đang hoạt động':\nBật = mã có hiệu lực]
    G --> H[Điền 'Tên chương trình']
    H --> I{Tạo mã giảm giá}
    I -- Tự nhập --> J[Gõ mã vào ô 'Mã giảm giá']
    I -- Auto-generate --> K[Nhấn nút 'Tạo mã'\nhệ thống tự sinh mã ngẫu nhiên]
    J & K --> L[Chọn Thời gian hiệu lực\nNgày bắt đầu → Ngày kết thúc]
    L --> M{Chọn Loại giảm giá}
    M -- Phần trăm --> N[Điền % giảm giá\nVD: 10%]
    M -- Số tiền cố định --> O[Điền số tiền giảm\nVD: 50.000đ]
    N & O --> P[Điền Số lượng mã\nVD: 100 lượt dùng]
    P --> Q[Điền Giá trị giảm tối đa VNĐ\nnếu cần giới hạn]
    Q --> R[Điền Đơn hàng tối thiểu VNĐ\nVD: 200.000đ]
    R --> S{Áp dụng cho SP cụ thể?}
    S -- Tất cả SP --> T[Bỏ qua phần Danh sách SP]
    S -- SP cụ thể --> U[Nhấn '+ Thêm sản phẩm'\nchọn SP áp dụng]
    T & U --> V{Kiểm tra lại}
    V -- Chưa đúng --> H
    V -- OK --> W[Nhấn 'Lưu']
    W --> X[Mã giảm giá được tạo\nhiển thị trong danh sách]
    X --> Y([✅ Hoàn tất])
```

---

## 🔄 LUỒNG 2: Tạo Chương Trình Khuyến Mãi (CTKM)

> **Khác với Mã giảm giá:** CTKM là giảm giá theo sản phẩm (không cần nhập mã), SD thấy giá gạch + giá KM trực tiếp trên web.

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Vào BÁN HÀNG → Khuyến mãi]
    B --> C[Nhấn 'Thêm CTKM' góc phải]
    C --> D[Modal 'Tạo chương trình khuyến mãi' hiện ra]
    D --> E[Toggle 'Đang hoạt động': Bật]
    E --> F[Điền Tên chương trình khuyến mãi]
    F --> G[Chọn Thời gian hiệu lực\nNgày bắt đầu → Ngày kết thúc]
    G --> H[Nhấn '+ Thêm sản phẩm'\nchọn SP vào CTKM]
    H --> I[Điền % giảm hoặc giá KM\ncho từng SP được chọn]
    I --> J{Thêm SP khác?}
    J -- Có --> H
    J -- Không --> K[Kiểm tra lại danh sách SP & giá KM]
    K --> L[Nhấn 'Lưu']
    L --> M[CTKM được tạo\nSP liên quan hiển thị giá KM trên web]
    M --> N([✅ Hoàn tất])
```

---

## 🔄 LUỒNG 3: Quản lý & Theo Dõi Hiệu Quả

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Vào Mã giảm giá / Khuyến mãi]
    B --> C[Bảng danh sách hiển thị:\nTên, Mã, Thời gian, Đã dùng/Tổng,\nDoanh thu, Giảm trừ, Trạng thái]
    C --> D{Lọc theo trạng thái}
    D -- Đang hoạt động --> E[Xem CTKM đang chạy]
    D -- Hết hạn --> F[Xem CTKM đã kết thúc]
    E & F --> G{Hành động cần thiết}
    G -- Xem hiệu quả --> H[Kiểm tra cột:\nSố ĐH / Doanh thu / Giảm trừ]
    G -- Tạm dừng --> I[Toggle 'Đang hoạt động' → Tắt]
    G -- Xuất báo cáo --> J[Nhấn 'Xuất Excel']
    H & I & J --> K([✅ Hoàn tất])
```

---

## 📋 So Sánh: Mã Giảm Giá vs Khuyến Mãi

| Tiêu chí | Mã Giảm Giá | Khuyến Mãi (CTKM) |
|---|---|---|
| **Cách dùng** | SD nhập mã khi checkout | Tự động hiển thị giá KM |
| **Trường bắt buộc** | Mã, Thời gian, Loại giảm, Giá trị, SL | Tên, Thời gian, SP áp dụng |
| **Hiển thị công khai** | Có toggle | Luôn hiển thị |
| **Giới hạn đơn tối thiểu** | Có | Không |
| **Theo dõi lượt dùng** | Có (đã dùng/tổng SL) | Theo SP bán được |
| **Phù hợp cho** | Flash sale, quà tặng riêng | Giảm giá toàn bộ danh mục |

---

## ⚠️ Lưu ý quan trọng
- **Mã không trùng:** Hệ thống không cho phép 2 mã giảm giá trùng nhau
- **Thời hạn rõ ràng:** Luôn cài ngày hết hạn — mã không bao giờ tự tắt nếu không có ngày kết thúc
- **Kiểm tra đơn tối thiểu:** Cài đúng để tránh lỗ khi SD dùng mã cho đơn nhỏ
- **CTKM từ DSS:** MD có thể đăng ký tham gia CTKM do DSS tạo (tại tab Kho hàng → Banner DSS)

---

## 📞 Liên quan
- [[01_TONG_QUAN_LY_DU_AN/2_PHONG_VAN_HANH/MD/SOP_MD_KHOTOT_XuLyDonHang\|SOP-MD-03: Xử lý Đơn hàng MD]]
- [[01_TONG_QUAN_LY_DU_AN/9_LUU_TRU_TIEN_DO/UAT_CHECKLIST_MD_KHOTOT_2026-03-31\|📋 UAT Checklist MD (31/03/2026)]]
