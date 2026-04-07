---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-3-huy-don-het-hang/","title":"SOP 03 — QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ","dg-note-properties":{"title":"SOP 03 — QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ"}}
---


# 📦 SOP 03 -QUY TRÌNH HỦY ĐƠN VÌ HẾT HÀNG THỰC TẾ

> **Dự án:** Web ETZ — Khotot.vn
> **Phiên bản:** 1.0 | **Cập nhật:** 2026-03-30
> **Phòng ban:** Phòng Vận Hành
> **Vùng dữ liệu:** Zone 01 — Tổng Hành Dinh

---

## 🎯 MỤC TIÊU
Hướng dẫn xử lý các tình huống tồn kho thực tế lệch so với Web, nhằm giữ chân khách hàng hoặc thực hiện hoàn tiền đúng quy định 7 ngày làm việc.

---

## 🔄 SƠ ĐỒ XỬ LÝ NGOẠI LỆ 

```mermaid
graph TD
    %% Định nghĩa bảng màu Pastel nguyên bản %%
    classDef admin fill:#E3F2FD,stroke:#2196F3,stroke-width:2px,color:#0D47A1;
    classDef acc fill:#E8F5E9,stroke:#4CAF50,stroke-width:2px,color:#1B5E20;
    classDef sd fill:#F3E5F5,stroke:#9C27B0,stroke-width:2px,color:#4A148C;
    classDef highlight fill:#FFF9C4,stroke:#FBC02D,stroke-width:1px,color:#F57F17;

    Start[[SOP 03: Bước Kiểm tra hết hàng]] --> Admin_Call[Admin gọi điện tư vấn SD]
    click Start "/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-2-xu-ly-don-hang-chuan/"
    
    Admin_Call --> SD_Choice{SD lựa chọn?}
    
    %% Nhánh 1: Đổi sản phẩm %%
    SD_Choice -- "Đồng ý đổi SP" --> Admin_Web_Cancel[Admin: Hủy đơn & Cập nhật TT Thanh toán là 'ĐỔI ĐƠN']
    Admin_Web_Cancel --> Offline_Deal[Xử lý chênh lệch & Giao dịch mới NGOÀI WEB]
    Offline_Deal --> End((Hoàn tất))

    %% Nhánh 2: Hủy đơn & Hoàn tiền %%
    SD_Choice -- "Không đồng ý đổi" --> Inform_Refund[Thông báo: Hoàn tiền trong 7 ngày]
    Inform_Refund --> Acc_Process[Kế toán thực hiện hoàn tiền NGOÀI WEB]
    Acc_Process --> Admin_Web_Update[Admin cập nhật Trạng thái chung: ĐÃ HOÀN TIỀN]
    Admin_Web_Update --> Web_Cancel_2[Admin thực hiện HỦY ĐƠN trên Web]
    Web_Cancel_2 --> End

    class Start,Admin_Call,Web_Cancel_2,Admin_Web_Cancel admin;
    class Acc_Process,SD_Choice acc;
    class Offline_Deal,End sd;
    class Inform_Refund highlight;
```

---

## 👁️ CHI TIẾT CÁC BƯỚC THỰC HIỆN

### 1. BƯỚC 1: XÁC MINH & LIÊN HỆ 
- Sau khi Kho báo hết hàng thực tế, Admin tuyệt đối không tự ý hủy đơn ngay.
- Admin gọi điện trực tiếp cho SD để báo tình trạng và tư vấn:
    - Tìm sản phẩm tương đương về tính năng/giá tiền.
    - Đề xuất giải pháp thay thế.

### 2. BƯỚC 2: PHÂN NHÁNH XỬ LÝ THEO Ý KHÁCH (SD)

#### **Trường hợp A: SD đồng ý đổi sản phẩm khác**
Để vận hành được tinh gọn, tránh hệ thống bị phức tạp hóa chéo nhau, Admin sẽ xử lý đơn đổi hoàn toàn theo hình thức **giao dịch ngoài luồng**:

**1. Thao tác đối với ĐƠN HÀNG CŨ trên Web:**
- **Trạng thái Đơn hàng:** Nhấn **Hủy đơn** cũ với lý do *"Đổi sang sản phẩm khác"*.
- **Trạng thái Thanh toán (Quan trọng):** Chuyển sang **`Đổi đơn`**. Kế toán sẽ nhìn vào trạng thái này để hiểu dòng tiền này không cần hoàn lại cho khách gốc, mà sẽ được quy hoạch sang đơn ngoài luồng. Tuỳệt đối không chọn trạng thái "Đã hoàn tiền".
- **Ghi chú (Notes):** Bắt buộc nhập: *"Đổi qua mã sản phẩm [Tên/Mã mới] - Xử lý ngoài luồng"*.

**2. Vận hành Ngoại lệ (Ngoài luồng Web):**
- Mọi giao dịch sau đó sẽ được Admin trao đổi trực tiếp với SD qua Zalo/Điện thoại.
- Thiết lập đóng gói, gửi Kho và đẩy mã vận đơn mới hoàn toàn qua kênh nội bộ công ty.
- **Xử lý chênh tiền:**
  - Nếu sản phẩm mới **Giá cao hơn:** Yêu cầu khách chuyển thêm và báo Kế toán đối soát.
  - Nếu sản phẩm mới **Giá thấp hơn:** Lấy STK của khách và báo Kế toán thực hiện chuyển hoàn tiền dư.

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
