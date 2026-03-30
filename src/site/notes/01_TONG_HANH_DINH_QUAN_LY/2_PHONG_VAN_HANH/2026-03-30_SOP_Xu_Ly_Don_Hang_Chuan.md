---
{"dg-publish":true,"permalink":"/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/2026-03-30-sop-xu-ly-don-hang-chuan/","title":"SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ĐA LUỒNG)","dg-note-properties":{"title":"SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ĐA LUỒNG)"}}
---


# 📦 SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ĐA LUỒNG)

> **Dự án:** Web ETZ — Khotot.vn
> **Phiên bản:** 1.1 | **Cập nhật:** 2026-03-30
> **Tác giả:** Antigravity AI
> **Phòng ban:** Phòng Vận Hành
> **Vùng dữ liệu:** Zone 01 — Tổng Hành Dinh

---

## 🎯 MỤC TIÊU
Đảm bảo mọi đơn hàng được xử lý chính xác từ khâu SD đặt hàng, Admin điều phối đến Kế toán xuất hóa đơn đúng thời điểm cho từng loại hình vận chuyển.

---

## 🔄 SƠ ĐỒ PHỐI HỢP (SWIMLANE FLOWCHART)

```mermaid
graph TD
    %% Định nghĩa màu tương phản cao %%
    classDef sd fill:#F3E5F5,stroke:#9C27B0,color:#4A148C;
    classDef admin fill:#E3F2FD,stroke:#2196F3,color:#0D47A1;
    classDef acc fill:#E8F5E9,stroke:#4CAF50,color:#1B5E20;
    classDef wh fill:#FFF3E0,stroke:#FF9800,color:#E65100;
    classDef error fill:#FFEBEE,stroke:#D32F2F,color:#B71C1C;

    Start((Bắt đầu)) --> SD_Order[SD đặt hàng & Chọn kho ETZ]
    SD_Order --> Admin_Check{Admin kiểm tra hàng}
    
    Admin_Check -- "HẾT HÀNG" --> OutOfStock[[SOP 02: Hủy đơn hết hàng]]
    click OutOfStock "/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/2026-03-30-sop-huy-don-het-hang/"
    Admin_Check -- "CÒN HÀNG" --> Set_Prep[Chuyển trạng thái: Chuẩn bị hàng]
    
    Set_Prep --> Ship_Type{Loại vận chuyển?}

    %% Nhánh Chành xe %%
    Ship_Type -- Chành xe --> Acc_Inv_1[Kế toán xuất hóa đơn]
    Acc_Inv_1 --> WH_Pack_1[Kho đóng gói kèm Hóa đơn]
    WH_Pack_1 --> WH_Check[Kho kiểm hàng & Giao Chành]

    %% Nhánh Tại kho %%
    Ship_Type -- Khách lấy tại kho --> WH_Pack_2[Kho chuẩn bị hàng]
    WH_Pack_2 --> SD_Pick[Khách nhận hàng]
    SD_Pick --> Acc_Inv_2[Kế toán xuất hóa đơn trong ngày]

    %% Nhánh Viettel Post %%
    Ship_Type -- Viettel Post --> WH_Pack_3[Kho đóng gói & Gửi hàng]
    WH_Pack_3 --> API_Delivered{Web báo: Đã giao?}
    API_Delivered -- OK --> Acc_Inv_3[Kế toán xuất HĐ trước 17:00]

    class SD_Order,SD_Pick sd;
    class Admin_Check,Set_Prep admin;
    class Acc_Inv_1,Acc_Inv_2,Acc_Inv_3 acc;
    class WH_Pack_1,WH_Pack_2,WH_Pack_3,WH_Check wh;
    class OutOfStock error;
```

---

## 👁️ CHI TIẾT CÁC GIAI ĐOẠN

### 1. GIAI ĐOẠN 1: KHÁCH HÀNG (SD) ĐẶT HÀNG
- SD chọn sản phẩm và chọn **Kho ETZ Miền Nam** (lộ trình giai đoạn 1).
- Chọn hình thức: Thanh toán, Phương thức vận chuyển, và **Yêu cầu xuất hóa đơn**.

### 2. GIAI ĐOẠN 2: ADMIN ĐIỀU PHỐI (GATEKEEPER)
- Tiếp nhận thông tin đơn hàng từ Dashboard.
- Kiểm tra tồn kho vật lý và khớp lệnh.
- **Tình huống Hết hàng:** Chuyển ngay sang quy trình xử lý tại [[01_TONG_HANH_DINH_QUAN_LY/2_PHONG_VAN_HANH/2026-03-30_SOP_Huy_Don_Het_Hang\|SOP 02: Hủy đơn hết hàng]].
- **Tình huống Còn hàng:** Đổi trạng thái đơn sang **"Chuẩn bị hàng"**.

### 3. GIAI ĐOẠN 3: PHÂN LUỒNG HÓA ĐƠN & VẬN CHUYỂN

| Hình thức | Kế toán (Hóa đơn) | Kho (Đóng gói & Giao) |
|---|---|---|
| **Chành xe** | Xuất ngay sau khi Admin duyệt đơn. Gửi thông tin cho Kho. | **Bắt buộc** đóng gói kèm Hóa đơn chứng từ. Kiểm tra đủ mới bàn giao vận chuyển. |
| **Lấy tại kho** | Xuất linh hoạt bất kỳ lúc nào trong ngày (trong cùng ngày SD lấy hàng). | Chuẩn bị hàng sẵn chờ SD đến lấy. |
| **Viettel Post** | Cuối ngày (trước 17:00), kiểm tra API báo *Đã giao thành công* để xuất HĐ hàng loạt. | Đóng gói theo chuẩn, dán vận đơn và gửi hàng cho bưu tá. |

---

## 📊 KPI THEO DÕI
- **Kế toán:** Mọi đơn Viettel Post thành công phải được xuất HĐ trước 17:00 hàng ngày.
- **Kho:** Đơn Chành xe không được xuất kho nếu thiếu hóa đơn kèm theo.

---
