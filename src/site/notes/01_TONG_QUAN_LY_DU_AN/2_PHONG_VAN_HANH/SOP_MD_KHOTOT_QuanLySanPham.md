---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-md-khotot-quan-ly-san-pham/","title":"SOP-MD-01 | Quản lý Sản phẩm — md.khotot.vn","dg-note-properties":{"title":"SOP-MD-01 | Quản lý Sản phẩm — md.khotot.vn","cap_nhat":"2026-03-31","loai":"SOP","phong_ban":"Vận Hành","he_thong":"md.khotot.vn"}}
---


# SOP-MD-01 | Quản lý Sản phẩm MD
> **Áp dụng cho:** Nhân viên/Admin vai trò MD tại `md.khotot.vn`
> **Phiên bản:** v1.0 | **Ngày tạo:** 31/03/2026
> **Nguồn:** Tổng hợp từ UAT kiểm thử thực tế

---

## 🎯 Mục đích
Hướng dẫn MD (Nhà phân phối) quản lý danh mục sản phẩm trên hệ thống: xem sản phẩm từ DSS, tạo sản phẩm mới, kiểm soát trạng thái hiển thị.

---

## 📌 Thông tin truy cập
- **URL:** `https://md.khotot.vn/app/sale/products`
- **Sidebar:** BÁN HÀNG → Sản phẩm

---

## 🔄 LUỒNG 1: Xem & Lọc Sản Phẩm

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Đăng nhập md.khotot.vn]
    B --> C[Vào sidebar: BÁN HÀNG → Sản phẩm]
    C --> D[Trang danh sách sản phẩm hiển thị]
    D --> E{Cần lọc?}
    E -- Có --> F[Chọn dropdown Trạng thái]
    F --> G{Chọn loại}
    G -- Đang bán --> H[Hiển thị SP đang active]
    G -- Tạm ẩn --> I[Hiển thị SP đã ẩn]
    G -- Chờ duyệt --> J[Hiển thị SP chờ DSS phê duyệt]
    H & I & J --> K[Xem chi tiết SP]
    E -- Không --> K
    K --> L([✅ Hoàn tất])
```

---

## 🔄 LUỒNG 2: Tạo Sản Phẩm Mới & Gửi DSS Phê Duyệt

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Vào /app/sale/products]
    B --> C[Nhấn nút 'Thêm sản phẩm' màu xanh]
    C --> D[Modal 'Tạo mới sản phẩm' hiện ra]
    D --> E[Tab 1: Thông tin cơ bản]
    E --> F[Điền: Tên SP, Danh mục, Mô tả ngắn]
    F --> G[Điền: Giá bán, SKU, Mã vạch]
    G --> H[Upload ảnh sản phẩm]
    H --> I[Chuyển sang Tab 2: Thuộc tính sản phẩm]
    I --> J[Sử dụng Rich Text Editor\nđiền mô tả chi tiết / thuộc tính]
    J --> K{Kiểm tra lại thông tin}
    K -- Chưa đúng --> E
    K -- Đúng rồi --> L[Nhấn 'Lưu']
    L --> M[SP được tạo với trạng thái\n'Chờ duyệt']
    M --> N[Hệ thống gửi yêu cầu phê duyệt lên DSS]
    N --> O{DSS xem xét}
    O -- Duyệt --> P[SP chuyển sang 'Đang bán'\nhiển thị cho SD]
    O -- Từ chối --> Q[MD nhận thông báo từ chối\nvà lý do]
    Q --> R[MD chỉnh sửa và gửi lại]
    R --> N
    P --> S([✅ Hoàn tất — SP live])
```

---

## 🔄 LUỒNG 3: Ẩn / Hiện Sản Phẩm

```mermaid
flowchart TD
    A([▶ Bắt đầu]) --> B[Vào danh sách sản phẩm]
    B --> C[Tìm SP cần thay đổi trạng thái]
    C --> D{Hành động}
    D -- Ẩn SP --> E[Toggle trạng thái → Tạm ẩn]
    D -- Hiện lại --> F[Toggle trạng thái → Đang bán]
    E --> G[SP không còn hiển thị\ntrên khotot.vn cho SD]
    F --> H[SP hiển thị lại\ncho SD trên khotot.vn]
    G & H --> I([✅ Hoàn tất])
```

---

## ⚠️ Lưu ý quan trọng
- **Không trùng tên:** Hệ thống không cho phép tạo SP trùng tên với SP đã có (kể cả SP của DSS)
- **Chờ duyệt:** SP mới tạo sẽ ở trạng thái "Chờ duyệt" — SD chưa thấy cho đến khi DSS duyệt
- **Ẩn tạm thời ≠ Xóa:** Ẩn SP không xóa dữ liệu, chỉ ẩn khỏi kho SD

---

## 📞 Liên quan
- [[01_TONG_QUAN_LY_DU_AN/2_PHONG_VAN_HANH/SOP_MD_KHOTOT_XuLyDonHang\|SOP-MD-03: Xử lý Đơn hàng MD]]
- [[01_TONG_QUAN_LY_DU_AN/9_LUU_TRU_TIEN_DO/UAT_CHECKLIST_MD_KHOTOT_2026-03-31\|📋 UAT Checklist MD (31/03/2026)]]
