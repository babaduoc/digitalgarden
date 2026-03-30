---
{"dg-publish":true,"permalink":"/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/2026-03-30-sop-huy-don-het-hang/","title":"SOP 02 — QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ","dg-note-properties":{"title":"SOP 02 — QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ"}}
---


# 📦 SOP 02 -QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ

> **Dự án:** Web ETZ — Khotot.vn
> **Phiên bản:** 1.0 | **Cập nhật:** 2026-03-30
> **Tác giả:** Antigravity AI
> **Phòng ban:** Phòng Vận Hành
> **Vùng dữ liệu:** Zone 01 — Tổng Hành Dinh

---

## 🎯 MỤC TIÊU
Hướng dẫn xử lý các tình huống tồn kho thực tế lệch so với Web, nhằm giữ chân khách hàng hoặc thực hiện hoàn tiền đúng quy định 7 ngày làm việc.

---

## 🔄 SƠ ĐỒ XỬ LÝ NGOẠI LỆ (FLOWCHART)

```mermaid
graph TD
    %% Định nghĩa bảng màu Tương phản cao %%
    classDef admin fill:#E3F2FD,stroke:#2196F3,stroke-width:2px,color:#0D47A1;
    classDef acc fill:#E8F5E9,stroke:#4CAF50,stroke-width:2px,color:#1B5E20;
    classDef sd fill:#F3E5F5,stroke:#9C27B0,stroke-width:2px,color:#4A148C;
    classDef highlight fill:#FFF9C4,stroke:#FBC02D,stroke-width:1px,color:#F57F17;

    Start[[SOP 01: Bước Kiểm tra hết hàng]] --> Admin_Call[Admin gọi điện tư vấn SD]
    click Start "/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/2026-03-30-sop-xu-ly-don-hang-chuan/"
    
    Admin_Call --> SD_Choice{SD lựa chọn?}
    
    %% Nhánh 1: Đổi sản phẩm %%
    SD_Choice -- "Đồng ý đổi SP" --> Web_Cancel_1[Hủy đơn trên Web]
    Web_Cancel_1 --> Offline_Order[Tạo đơn mới xử lý NGOÀI WEB]
    Offline_Order --> End((Hoàn tất))

    %% Nhánh 2: Hủy đơn & Hoàn tiền %%
    SD_Choice -- "Không đồng ý đổi" --> Web_Cancel_2[Hủy đơn trên Web]
    Web_Cancel_2 --> Inform_Refund[Thông báo: Hoàn tiền trong 7 ngày]
    Inform_Refund --> Acc_Process[Kế toán thực hiện hoàn tiền NGOÀI WEB]
    Acc_Process --> End

    class Admin_Call,Web_Cancel_1,Web_Cancel_2 admin;
    class Acc_Process acc;
    class SD_Choice sd;
    class Inform_Refund highlight;
```

---

## 👁️ CHI TIẾT CÁC BƯỚC THỰC HIỆN

### 1. BƯỚC 1: XÁC MINH & LIÊN HỆ (ADMIN)
- Sau khi Kho báo hết hàng thực tế, Admin tuyệt đối không tự ý hủy đơn ngay.
- Admin gọi điện trực tiếp cho SD để báo tình trạng và tư vấn:
    - Tìm sản phẩm tương đương về tính năng/giá tiền.
    - Đề xuất giải pháp thay thế.

### 2. BƯỚC 2: PHÂN NHÁNH XỬ LÝ THEO Ý KHÁCH (SD)

#### **Trường hợp A: SD đồng ý đổi sản phẩm khác**
- **Thao tác Web:** Admin nhấn **Hủy đơn** cũ với lý do *"Đổi sang sản phẩm khác"*.
- **Vận hành:** Mọi giao dịch sau đó (chênh lệch tiền, đóng gói SP mới) sẽ được trao đổi và xử lý **ngoài luồng Web** (qua Zalo/Điện thoại) để đảm bảo linh hoạt.

#### **Trường hợp B: SD không đồng ý và muốn hủy đơn**
- **Thao tác Web:** Admin nhấn **Hủy đơn** chính thức. Hệ thống gửi thông báo hủy cho SD.
- **Cam kết hoàn tiền:** Admin thông báo rõ: *"Tiền đã chuyển khoản sẽ được hoàn trả vào số tài khoản của quý khách trong vòng 7 ngày làm việc"*.

### 3. BƯỚC 3: HOÀN TIỀN (KẾ TOÁN)
- Admin gửi thông báo hủy đơn kèm thông tin tài khoản SD cho bộ phận Kế toán.
- Kế toán thực hiện lệnh chuyển khoản hoàn tiền cho SD.
- Chụp ảnh biên lai gửi cho SD qua Zalo OA để hoàn tất quy trình.

---

## 📊 KPI & LƯU Ý QUAN TRỌNG
- **Thời gian xử lý:** CS phải gọi điện cho SD trong vòng **< 1 giờ** kể từ khi Kho báo hết hàng.
- **Tính đồng bộ:** Mọi đơn hủy trên Web phải được phản ánh ngay vào báo cáo ngày của Kế toán để tránh quên hoàn tiền.
- **Mong muốn tương lai:** Ưu tiên phát triển API kết nối trực tiếp tồn kho thực tế từ ERP lên Web để giảm thiểu quy trình hủy đơn này xuống **< 1%**.

---
