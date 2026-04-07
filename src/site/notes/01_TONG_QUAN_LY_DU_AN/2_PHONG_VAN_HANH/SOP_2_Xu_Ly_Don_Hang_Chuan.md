---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-2-xu-ly-don-hang-chuan/","title":"SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ĐA LUỒNG)","dg-note-properties":{"title":"SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ĐA LUỒNG)"}}
---



# 📦 SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG 

> **Dự án:** Web ETZ — Khotot.vn
> **Phiên bản:** 2.0 | **Cập nhật:** 2026-04-06
> **Phòng ban:** Phòng Vận Hành
> **Vùng dữ liệu:** Zone 01

---

## 🎯 MỤC TIÊU
Đảm bảo mọi đơn hàng được xử lý chính xác thông qua hệ thống MISA, phân rõ vai trò giữa Sale Admin, Kế toán và Kho, đảm bảo tính pháp lý hóa đơn và dòng tiền.

---

## 🔄 SƠ ĐỒ PHỐI HỢP 

```mermaid

graph TD
    %% Định nghĩa bảng màu Pastel nguyên bản (Classic Style) %%
    classDef sd fill:#F3E5F5,stroke:#9C27B0,color:#4A148C;
    classDef sale_admin fill:#E3F2FD,stroke:#2196F3,color:#0D47A1;
    classDef acc fill:#E8F5E9,stroke:#4CAF50,color:#1B5E20;
    classDef wh fill:#FFF3E0,stroke:#FF9800,color:#E65100;
    classDef error fill:#FFEBEE,stroke:#D32F2F,color:#B71C1C;

    Start((Bắt đầu)) --> SD_Order[SD đặt hàng & Chọn kho ETZ]
    
    %% Vai trò Sale Admin %%
    SD_Order --> SaleAdmin_Check{Sale Admin kiểm hàng trên MISA}
    
    SaleAdmin_Check -- "HẾT HÀNG" --> OutOfStock[["SOP 03: Hủy đơn hết hàng"]]
    click OutOfStock "/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-3-huy-don-het-hang/"
    SaleAdmin_Check -- "CÒN HÀNG" --> SaleAdmin_DH[Sale Admin tạo đơn MISA mã DH]
    SaleAdmin_DH --> Acc_Notify[Báo Kế toán có đơn mới]

    %% Vai trò Kế toán %%
    Acc_Notify --> Acc_CheckMoney{Kế toán kiểm tra tiền vào hệ thống}
    
    Acc_CheckMoney -- "KHÔNG OK" --> Acc_Reject[Báo Sale Admin kiểm tra lại]
    Acc_Reject --> SaleAdmin_Check
    
    Acc_CheckMoney -- "OK" --> Acc_BH[Đẩy thông tin MISA mã đơn BH]
    Acc_BH --> Ship_Type{Phân loại vận chuyển}

    %% Nhánh Chành xe %%
    Ship_Type -- "Chành xe (SD trả cước)" --> Acc_Inv_1[Kế toán xuất HĐ & Phiếu xuất kho]
    Acc_Inv_1 --> WH_Pack_1[Kho đóng gói kèm HĐ & Phiếu xuất kho]
    WH_Pack_1 --> WH_Check[Kho kiểm hàng & Giao Chành]
    WH_Check --> WH_Photo[Shipper chụp ảnh Biên nhận & Kiện hàng]
    WH_Photo --> Admin_Upload[Sale Admin Upload ảnh lên Web & Báo SD]
    Admin_Upload --> WH_Confirm[Kho/Shipper báo Admin đã giao xong]
    WH_Confirm --> Admin_Finish_1[Sale Admin hoàn tất đơn thủ công]

    %% Nhánh Tại kho %%
    Ship_Type -- "Khách lấy tại kho" --> WH_Pack_2[Kho chuẩn bị hàng]
    WH_Pack_2 --> SD_Pick[Khách nhận hàng]
    SD_Pick --> WH_Confirm_2[Kho báo Admin khách đã lấy hàng]
    WH_Confirm_2 --> Admin_Finish_2[Sale Admin hoàn tất đơn thủ công]
    SD_Pick --> Acc_Inv_2[Kế toán xuất hóa đơn trong ngày]

    %% Nhánh Viettel Post %%
    Ship_Type -- "Viettel Post" --> WH_Pack_3[Kho đóng gói & Gửi hàng]
    WH_Pack_3 --> API_Delivered{Web báo: Đã giao?}
    API_Delivered -- OK --> Acc_Inv_3[Kế toán xuất HĐ trước 17:00]

    class SD_Order,SD_Pick,WH_Pack_1,WH_Pack_2,WH_Pack_3,WH_Check,WH_Confirm,WH_Confirm_2 sd;
    class Start,SaleAdmin_Check,SaleAdmin_DH,Acc_Reject,Admin_Upload,Admin_Finish_1,Admin_Finish_2 sale_admin;
    class Acc_Notify,Acc_CheckMoney,Acc_BH,Ship_Type,Acc_Inv_1,Acc_Inv_2,Acc_Inv_3 acc;
    class OutOfStock error;
```

---

## 👁️ CHI TIẾT CÁC GIAI ĐOẠN

### 1. GIAI ĐOẠN 1: KHÁCH HÀNG (SD) ĐẶT HÀNG
- SD chọn sản phẩm và chọn **Kho ETZ Miền Nam** (lộ trình giai đoạn 1).
- Chọn hình thức: Thanh toán, Phương thức vận chuyển, và **Yêu cầu xuất hóa đơn**.

### 2. GIAI ĐOẠN 2: SALE ADMIN KIỂM TRA & TẠO ĐƠN
- Sale Admin tiếp nhận thông tin đơn hàng từ Dashboard.
- **Kiểm tra trên MISA:** Xác định tồn kho vật lý và khớp lệnh trên phần mềm MISA.
- **Tình huống Hết hàng:** Chuyển ngay sang quy trình xử lý tại [[01_TONG_QUAN_LY_DU_AN/2_PHONG_VAN_HANH/SOP_3_Huy_Don_Het_Hang\|SOP 03: Hủy đơn hết hàng]].
- **Tình huống Còn hàng:** 
    1. Tạo đơn hàng trên MISA với **mã đơn DH**.
    2. Thông báo cho bộ phận Kế toán có đơn hàng mới cần kiểm tra thanh toán.

### 3. GIAI ĐOẠN 3: KẾ TOÁN KIỂM TRA TIỀN & PHÊ DUYỆT (BH)
- Kế toán tiếp nhận thông báo từ Sale Admin.
- **Kiểm tra thanh toán:** Xác nhận tiền đã vào hệ thống (SePay hoặc Chuyển khoản).
- **Phê duyệt:** 
    - Nếu **OK**: Đẩy thông tin qua MISA với **mã đơn BH**. Đây là lệnh cho phép Kho bắt đầu đóng gói hàng.
    - Nếu **KHÔNG OK**: Báo Sale Admin kiểm tra lại với khách hàng hoặc hệ thống.
- **Phân loại vận chuyển:** Dựa trên phương thức vận chuyển của đơn hàng để thực hiện xuất hóa đơn (như quy trình tại Giai đoạn 4).

### 4. GIAI ĐOẠN 4: PHÂN LUỒNG HÓA ĐƠN & VẬN CHUYỂN

| Hình thức | Kế toán (Hóa đơn) | Kho (Đóng gói & Giao) | Sale Admin (Hoàn tất đơn) |
|---|---|---|---|
| **Chành xe** | Sau khi tạo mã BH, xuất HĐ & Phiếu xuất kho ngay. | **Bắt buộc** kèm HĐ & Phiếu xuất kho. Giao xong phải chụp ảnh + báo ngay cho Admin. | **Thủ công:** Upload ảnh lên Web -> Hoàn tất đơn trên Web. |
| **Lấy tại kho** | Xuất linh hoạt bất kỳ lúc nào trong ngày. | Chuẩn bị hàng sẵn. Khách lấy xong phải báo ngay cho Admin. | **Thủ công:** Xác nhận từ Kho -> Hoàn tất đơn trên Web. |
| **Viettel Post** | Cuối ngày (trước 17:00), kiểm tra API báo *Đã giao thành công*. | Đóng gói theo chuẩn, gửi hàng cho bưu tá. | **Tự động:** Hệ thống tự đổi trạng thái dựa theo API nhà vận chuyển. |

---

## 📊 KPI THEO DÕI
- **Sale Admin:** Tốc độ tạo đơn DH trên MISA (< 30 phút từ khi có đơn Web). Chịu trách nhiệm theo dõi thông tin từ Kho để hoàn tất đơn hàng thủ công (tránh đơn treo).
- **Kế toán:** Kiểm tra tiền và đẩy mã BH kịp thời để Kho đóng gói. Mọi đơn Viettel Post thành công phải được xuất HĐ trước 17:00 hàng ngày.
- **Kho:** Tuyệt đối không đóng gói hàng khi chưa có mã BH trên MISA. Báo cáo Sale Admin ngay sau khi hàng rời kho/khách lấy hàng.

---
---

## 👁️ IV. CHI TIẾT GIAO HÀNG CHÀNH XE (ĐẶC THÙ)

Đối với các đơn hàng SD yêu cầu gửi qua nhà xe/xe khách:

1.  **Hồ sơ đi đường:** Kế toán phải hoàn tất **Hóa đơn** và **Phiếu xuất kho** trước khi hàng rời kho để đảm bảo tính pháp lý và đối soát sản phẩm khi nhà xe giao hàng.
2.  **Đóng gói & Nhãn:** Kho dán nhãn khổ lớn ghi rõ: *Tên SD - SĐT SD - Tên Chành - Nơi đến*.
3.  **Xác thực giao hàng (Bằng chứng):**
    - Shipper nội bộ lấy **Biên nhận (Vận đơn)** từ nhà xe.
    - Chụp ảnh thùng hàng đã đặt tại văn phòng Chành và ảnh Biên nhận rõ mã số liên hệ.
4.  **Thông báo & Thanh toán cước:**
    - Sale Admin upload ảnh bằng chứng lên Web để SD yên tâm.
    - **Lưu ý thanh toán:** SD (Người nhận) có trách nhiệm tự thanh toán tiền cước vận chuyển trực tiếp cho nhà xe khi nhận hàng.
