---
{"dg-publish":true,"permalink":"/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/sop-3-huy-don-het-hang/","title":"SOP 02 — QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ","dg-note-properties":{"title":"SOP 02 — QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ"}}
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

    Start[[SOP 02: Bước Kiểm tra hết hàng]] --> Admin_Call[Admin gọi điện tư vấn SD]
    click Start "/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/sop-2-xu-ly-don-hang-chuan/"
    
    Admin_Call --> SD_Choice{SD lựa chọn?}
    
    %% Nhánh 1: Đổi sản phẩm %%
    SD_Choice -- "Đồng ý đổi SP" --> Web_Cancel_1[Hủy đơn trên Web]
    Web_Cancel_1 --> Offline_Order[Tạo đơn mới xử lý NGOÀI WEB]
    Offline_Order --> End((Hoàn tất))

    %% Nhánh 2: Hủy đơn & Hoàn tiền %%
    SD_Choice -- "Không đồng ý đổi" --> Inform_Refund[Thông báo: Hoàn tiền trong 7 ngày]
    Inform_Refund --> Acc_Process[Kế toán thực hiện hoàn tiền NGOÀI WEB]
    Acc_Process --> Admin_Web_Update[Admin cập nhật Trạng thái: ĐÃ HOÀN TIỀN + Ghi chú]
    Admin_Web_Update --> Web_Cancel_2[Admin thực hiện HỦY ĐƠN trên Web]
    Web_Cancel_2 --> End

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
1.  **Thông báo:** CS báo rõ: *"Tiền đã chuyển khoản sẽ được hoàn trả vào số tài khoản của quý khách trong vòng 7 ngày làm việc"*.
2.  **Lệnh hoàn tiền:** Chuyển thông tin cho Kế toán để thực hiện chuyển khoản ngoài luồng.
3.  **Cập nhật Web (Quan trọng):** Sau khi Kế toán xác nhận đã hoàn xong, Admin quay lại đơn hàng trên Web:
    - Thay đổi trạng thái thanh toán thành: **"Đã hoàn tiền" (Refunded)**.
    - Nhập **Ghi chú (Notes)**: Mã giao dịch ngân hàng, ngày giờ hoàn tiền để SD đối soát.
4.  **Hủy đơn:** Tiến hành nhấn nút **Hủy đơn** chính thức. Hệ thống sẽ gửi thông báo "Đã hoàn tiền & Đã hủy" cho SD.

### 3. BƯỚC 3: HOÀN TIỀN & ĐỐI SOÁT (KẾ TOÁN & ADMIN)
- **Kế toán:** Thực hiện lệnh chuyển khoản hoàn tiền -> Gửi ảnh biên lai cho Admin.
- **Admin:** Đảm bảo mọi đơn hủy có hoàn tiền đều phải được cập nhật trạng thái "Đã hoàn tiền" trên Web trước khi đóng đơn.

---

## 📊 KPI & LƯU Ý QUAN TRỌNG
- **Thời gian xử lý:** CS phải gọi điện cho SD trong vòng **< 1 giờ** kể từ khi Kho báo hết hàng.
- **Tính đồng bộ:** Mọi đơn hủy trên Web phải được phản ánh ngay vào báo cáo ngày của Kế toán để tránh quên hoàn tiền.
- **Mong muốn tương lai:** Ưu tiên phát triển API kết nối trực tiếp tồn kho thực tế từ ERP lên Web để giảm thiểu quy trình hủy đơn này xuống **< 1%**.

---
