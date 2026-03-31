---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-5-tao-khuyen-mai-theo-thoi-gian/","title":"SOP 05: Tạo Khuyến Mãi (Giảm Giá Theo Thời Gian)","dg-note-properties":{"title":"SOP 05: Tạo Khuyến Mãi (Giảm Giá Theo Thời Gian)","loai":"SOP_Van_Hanh"}}
---


# 📝 SOP 05: QUY TRÌNH TẠO CHƯƠNG TRÌNH KHUYẾN MÃI (GIẢM GIÁ THEO THỜI GIAN)
> **Bộ phận:** Admin Vận Hành / Marketing
> **Hệ thống áp dụng:** `dss.khotot.vn` (DSS Admin Portal)

Trong hệ thống Web ETZ, tính năng này cho phép Admin thiết lập các campaign Sale giảm giá chớp nhoáng hoặc chạy dài ngày cho từng sản phẩm cụ thể nhằm thúc đẩy đơn hàng từ MD và SD.

---

## 🗺️ BIỂU ĐỒ QUY TRÌNH (FLOWCHART)

```mermaid
graph TD
    A([Bắt đầu làm Khuyến Mãi]) --> B[Đăng nhập DSS Admin]
    B --> C[Vào Quản Lý Khuyến Mãi]
    C --> D[Thêm Chương Trình]
    D --> E[Lập Tên & Đặt Thời Gian]
    E --> F[Chọn Kho Áp Dụng]
    F --> G[Chọn Sản Phẩm & Nhập Giảm Giá]
    G --> J[✅ Lưu & Kích hoạt KM]
    J --> N{Hệ thống Check: Trạng thái Tồn Kho}
    
    N -- Tồn kho = 0 --> H[🚫 SP tự động ẨN trên MD và SD]
    N -- Tồn kho > 0 --> K[Trang chủ SD tự động cập nhật Giá Sale]
    N -- Tồn kho > 0 --> L[Popup báo cho Đại lý MD đăng ký]
    
    H -.-> M([Theo dõi Doanh thu kết thúc])
    K --> M
    L --> M
    
    style A fill:#4CAF50,stroke:#fff,stroke-width:2px,color:#fff
    style H fill:#f44336,stroke:#fff,stroke-width:2px,color:#fff
    style J fill:#2196F3,stroke:#fff,stroke-width:2px,color:#fff
    style N fill:#FF9800,stroke:#fff,stroke-width:2px,color:#fff
    style M fill:#607D8B,stroke:#fff,stroke-width:2px,color:#fff
```

---

## ⚙️ CÁC BƯỚC THỰC HIỆN CHI TIẾT

### Bước 1: Quyền truy cập
- Đăng nhập vào trang quản trị Admin DSS (`dss.khotot.vn`).
- Trên thanh Menu, tìm và truy cập vào module **Quản lý Khuyến Mãi** (hoặc Ưu đãi).

### Bước 2: Khởi tạo chương trình mới
- Nhấp chọn nút **[Thêm chương trình khuyến mãi]** (hoặc Thêm mới).

### Bước 3: Điền thông tin cốt lõi
1. **Tên chương trình:** Đặt tên rõ ràng, dễ nhận diện (Ví dụ: *Flash Sale Cuối Tuần 15/4*, *Xả kho thẻ nhớ 32GB*...).
2. **Thời gian diễn ra:** Chọn chính xác thời điểm bắt đầu và kết thúc (Theo Giờ/Phút/Ngày/Tháng). **Quan trọng:** Ghi nhớ rằng chức năng này là *Khuyến mãi giảm giá theo thời gian*, chương trình sẽ tự động ẩn khi hết hạn.

### Bước 4: Thiết lập kho & Sản phẩm
1. **Chọn Kho áp dụng:** Chọn kho bãi cụ thể đang chạy chương trình giảm giá này (Kho tổng hoặc kho phân phối chỉ định).
2. **Chọn Sản phẩm & Giảm giá:** Tích chọn các sản phẩm nằm trong danh mục ưu đãi và nhập chi tiết Mức giảm giá (Tỉ lệ % hoặc Khấu trừ tiền mặt trực tiếp).
3. Nhấn **[Lưu & Kích hoạt]** chương trình trên hệ thống. 

### Bước 5: Cơ chế tự động Ẩn khi Hết Hàng (Out of Stock)
> [!info] 🤖 TỰ ĐỘNG HÓA TỪ HỆ THỐNG ETZ
> Logic cốt lõi: Để tránh khủng hoảng bão đơn không có hàng giao, hệ thống sẽ tự động chạy màng lọc **TỒN KHO THỰC TẾ**.
> Cụ thể: **Nếu sản phẩm hết hàng (Tồn = 0), sản phẩm đó sẽ TỰ ĐỘNG KHÔNG HIỂN THỊ trên màn hình của MD và SD.** Admin không sợ khách lẻ SD đặt lố đơn, mọi rủi ro về tồn ảo sẽ được chặn đứng bằng code.
