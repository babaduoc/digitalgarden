---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-2-xu-ly-don-hang-chuan/","title":"SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ĐA LUỒNG)","dg-note-properties":{"title":"SOP 01 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ĐA LUỒNG)"}}
---


# SOP 02 — QUY TRÌNH XỬ LÝ ĐƠN HÀNG

> **Dự án:** Web ETZ — Khotot.vn
> **Phiên bản:** 2.1 | **Cập nhật:** 2026-04-08
> **Phòng ban:** Phòng Vận Hành
> **Vùng dữ liệu:** Zone 01 — Tổng Hành Dinh

---

## 🎯 MỤC TIÊU
Đảm bảo mọi đơn hàng được xử lý chính xác thông qua hệ thống MISA, phân rõ vai trò giữa Sale Admin, Kế toán và Kho Admin, đảm bảo tính pháp lý hóa đơn và dòng tiền.

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

    Start((Bắt đầu)) --> SD_Order[SD đặt hàng & Chọn kho ETZ<br/>⚠️ BẮT BUỘC: Quay video mở hàng]

    %% Vai trò Sale Admin %%
    SD_Order --> SaleAdmin_Check{Sale Admin kiểm hàng trên MISA, vì hiện tại chưa kết nối misa}

    SaleAdmin_Check -- "HẾT HÀNG" --> OutOfStock[["SOP 03: Hủy đơn hết hàng"]]
    click OutOfStock "/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/sop-3-huy-don-het-hang/"
    SaleAdmin_Check -- "CÒN HÀNG" --> SaleAdmin_DH[Sale Admin tạo đơn MISA mã DH]
    SaleAdmin_DH --> Acc_Notify[Báo Kế toán có đơn mới]

    %% Vai trò Kế toán %%
    Acc_Notify --> Acc_CheckMoney{Kế toán kiểm tra tiền vào hệ thống thật, mặc dù đã có API trả kết quả về WEB}
    Acc_CheckMoney -- "KHÔNG OK" --> Acc_Reject[Báo Sale Admin kiểm tra lại]
    Acc_Reject --> SaleAdmin_Check
    Acc_CheckMoney -- "OK" --> Acc_BH[Đẩy thông tin MISA mã đơn BH]
    Acc_BH --> Ship_Type{Phân loại vận chuyển}

    %% Nhánh Chành xe %%
    Ship_Type -- "Chành xe" --> Check_5M{Đơn hàng trên 5 triệu?}
    Check_5M -- "Dưới 5 triệu" --> Reject_Chanh[Báo SD: Không đủ điều kiện chành xe]
    Check_5M -- "Trên 5 triệu" --> Acc_Inv_1[Kế toán xuất HĐ & Phiếu xuất kho]
    Acc_Inv_1 --> WH_Pack_1[Kho Admin đóng gói kèm HĐ & Phiếu xuất kho]
    WH_Pack_1 --> WH_Check[Kho Admin kiểm hàng & Giao Chành]
    WH_Check --> WH_Photo[Người chuyển hàng ra chành chụp ảnh Biên nhận & Kiện hàng]
    WH_Photo --> Admin_Upload[Sale Admin Upload ảnh lên Web & Báo SD]
    Admin_Upload --> Rule_2D{Sau 2 ngày không phản hồi?}
    Rule_2D -- "Tự động/Admin" --> Admin_Finish_1[Hoàn tất đơn hàng]

    %% Nhánh Tại kho %%
    Ship_Type -- "Khách lấy tại kho" --> WH_Print_PXK_2[Kho Admin tự in Phiếu xuất kho từ MISA]
    WH_Print_PXK_2 --> WH_Pack_2[Kho Admin đóng gói kèm Phiếu xuất kho]
    WH_Pack_2 --> SD_Pick[Khách tới nhận hàng]
    SD_Pick --> WH_Verify[Kho Admin xác nhận đúng người mua tới nhận hàng]
    WH_Verify --> SD_Sign[Khách ký & ghi họ tên vào PXK]
    SD_Sign --> WH_Finish_Web[Kho Admin hoàn tất đơn trên WEB Khotot.vn]
    WH_Finish_Web --> Admin_Check[Admin rà soát đơn treo]
    Admin_Check --> Acc_Inv_2[Kế toán kiểm tra & Xuất HĐ trước 17:00]

    %% Nhánh Viettel Post %%
    Ship_Type -- "Viettel Post" --> WH_Print_PXK[Kho Admin tự in Phiếu xuất kho từ MISA/Web]
    WH_Print_PXK --> WH_Pack_3[Kho Admin đóng gói kèm Phiếu xuất kho]
    WH_Pack_3 --> WH_Print_VT[In vận đơn: Web Viettel Post hoặc dss.khotot.vn]
    WH_Print_VT --> WH_Call_VT[Gọi bưu tá lấy hàng]
    WH_Call_VT --> API_Delivered{Web báo: Đã giao?}
    API_Delivered -- OK --> Acc_Inv_3[Kế toán kiểm tra và xuất HĐ hàng ngày trước 17:00]

    class SD_Order,SD_Pick,WH_Pack_1,WH_Pack_2,WH_Pack_3,WH_Check,WH_Confirm,WH_Confirm_2 sd;
    class Start,SaleAdmin_Check,SaleAdmin_DH,Acc_Reject,Admin_Upload,Admin_Finish_1,Admin_Finish_2 sale_admin;
    class Acc_Notify,Acc_CheckMoney,Acc_BH,Ship_Type,Acc_Inv_1,Acc_Inv_2,Acc_Inv_3 acc;
    class OutOfStock,Reject_Chanh error;
```

---

### 1. GIAI ĐOẠN 1: KHÁCH HÀNG (SD) ĐẶT HÀNG
- SD chọn sản phẩm và chọn Kho ETZ Miền Nam (lộ trình giai đoạn 1).
- Chọn hình thức: Thanh toán, Phương thức vận chuyển, và Yêu cầu xuất hóa đơn.
- **YÊU CẦU BẮT BUỘC:** SD khi nhận hàng từ bất kỳ phương thức nào cũng viết phải quay video khi mở hàng để Khotot kiểm tra và chấp nhận khiếu nại (nếu có).

### 2. GIAI ĐOẠN 2: SALE ADMIN KIỂM TRA & TẠO ĐƠN
- Sale Admin tiếp nhận thông tin đơn hàng từ Dashboard.
- Kiểm tra trên MISA: Xác định tồn kho vật lý và khớp lệnh trên phần mềm MISA.
- Tình huống Hết hàng: Chuyển ngay sang quy trình xử lý tại [SOP 03: Hủy đơn hết hàng](https://brain.kholink.vn/01-tong-hanh-dinh-quan-ly/2-phong-van-hanh/sop-3-huy-don-het-hang/).
- Tình huống Còn hàng:
  1. Tạo đơn hàng trên MISA với mã đơn DH.
  2. Thông báo cho bộ phận Kế toán có đơn hàng mới cần kiểm tra thanh toán.

### 3. GIAI ĐOẠN 3: KẾ TOÁN KIỂM TRA TIỀN & PHÊ DUYỆT (BH)
- Kế toán tiếp nhận thông báo từ Sale Admin.
- Kiểm tra thanh toán: Xác nhận tiền đã vào hệ thống (SePay hoặc Chuyển khoản).
- Phê duyệt:
  - Nếu OK: Đẩy thông tin qua MISA với mã đơn BH. Đây là lệnh cho phép Kho Admin bắt đầu đóng gói hàng.
  - Nếu KHÔNG OK: Báo Sale Admin kiểm tra lại với khách hàng hoặc hệ thống.
  - Phân loại vận chuyển: Dựa trên phương thức vận chuyển của đơn hàng để thực hiện xuất hóa đơn (như quy trình tại Giai đoạn 4).

---

## 📊 KPI THEO DÕI
- Sale Admin: Tốc độ tạo đơn DH trên MISA (< 30 phút từ khi có đơn Web). Chịu trách nhiệm theo dõi thông tin từ Kho Admin để hoàn tất đơn hàng thủ công (tránh đơn treo).
- Kế toán: Kiểm tra tiền và đẩy mã BH kịp thời để Kho Admin đóng gói. Mọi đơn Viettel Post thành công phải được xuất HĐ trước 17:00 hàng ngày.
- Kho Admin: Tuyệt đối không đóng gói hàng khi chưa có mã BH trên MISA. Báo cáo Sale Admin ngay sau khi hàng rời kho/khách lấy hàng.

---
---

## 👁️ IV. CHI TIẾT GIAO HÀNG CHÀNH XE (ĐẶC THÙ)
Đối với các đơn hàng SD yêu cầu gửi qua nhà xe/xe khách:
1. **Điều kiện vận chuyển:** Chỉ áp dụng cho đơn hàng có giá trị từ **5.000.000 VNĐ trở lên**. Khotot hỗ trợ chi phí vận chuyển từ kho ra chành gom.
2. Hồ sơ đi đường: Kế toán phải hoàn tất Hóa đơn và Phiếu xuất kho trước khi hàng rời kho để đảm bảo tính pháp lý và đối soát sản phẩm khi nhà xe giao hàng.
3. Đóng gói & Nhãn: Kho Admin dán nhãn khổ lớn ghi rõ: Tên SD - SĐT SD - Tên Chành - Nơi đến.
4. Xác thực giao hàng (Bằng chứng):
   - **Người chuyển hàng ra chành chụp ảnh Biên nhận & Kiện hàng** (từ nhà xe).
   - Chụp ảnh thùng hàng đã đặt tại văn phòng Chành và ảnh Biên nhận rõ mã số liên hệ.
5. Thông báo & Thanh toán cước:
   - Sale Admin upload ảnh bằng chứng lên Web để SD yên tâm.
   - Lưu ý thanh toán: SD (Người nhận) có trách nhiệm tự thanh toán tiền cước vận chuyển trực tiếp cho nhà xe khi nhận hàng.
6. Quy tắc hoàn tất & Miễn trừ trách nhiệm:
   - SD **phải quay video khi mở hàng** ngay khi nhận hàng để được hỗ trợ khiếu nại.
   - Sau 02 ngày kể từ khi Kho Admin xác nhận đã gửi hàng (upload biên nhận), nếu khách hàng không phản hồi, đơn hàng được xem là đã nhận thành công.
   - Khotot sẽ không chịu trách nhiệm về bất kỳ khiếu nại nào liên quan đến hàng hóa sau thời hạn 02 ngày này.
   - Hệ thống sẽ tự động chuyển trạng thái hoặc Sale Admin thực hiện cập nhật thủ công thành "Hoàn thành".

---

## 👁️ V. CHI TIẾT GIAO HÀNG VIETTEL POST (THỰC TẾ)
Quy trình xử lý cho các đơn hàng vận chuyển qua bưu cục Viettel Post:
1. Chuẩn bị hồ sơ: Ngay khi có mã BH trên MISA/Web, Kho Admin chủ động in Phiếu xuất kho từ hệ thống nội bộ.
2. Đóng gói:
   - Kiểm tra hàng hóa đúng chủng loại, số lượng.
   - Đặt Phiếu xuất kho vào bên trong kiện hàng trước khi đóng băng keo.
3. Tạo vận đơn:
   - Truy cập vào Web Viettel Post hoặc [dss.khotot.vn](http://dss.khotot.vn) (tùy chọn tiện lợi).
   - Nhập thông tin đơn hàng, chọn dịch vụ và In vận đơn (Waybill).
   - Dán vận đơn chắc chắn lên mặt ngoài thùng hàng.
4. Bàn giao vận chuyển:
   - Sử dụng chức năng "Gọi bưu tá" trên Web hoặc liên hệ Hotline bưu tá khu vực để lấy hàng.
   - Ký nhận bàn giao (nếu có) và theo dõi trạng thái "Đang vận chuyển" trên hệ thống.

---

## 👁️ VI. CHI TIẾT KHÁCH LẤY TẠI KHO (THỰC TẾ)
Quy trình xử lý cho các đơn hàng Khách hàng (SD) trực tiếp đến nhận tại kho:
1. Chuẩn bị hàng: Ngay khi có mã BH, Kho Admin chủ động in Phiếu xuất kho từ hệ thống MISA và đóng gói hàng sẵn.
2. Xác minh khách hàng:
   - Khi khách tới nhận, Kho Admin yêu cầu cung cấp mã đơn hàng.
   - **Bắt buộc:** **Kho Admin xác nhận đúng người mua tới nhận hàng.**
3. Hoàn tất tại chỗ:
   - Kho Admin yêu cầu khách hàng ký và ghi rõ họ tên vào Phiếu xuất kho để làm bằng chứng đối soát.
   - Giao hàng xong, Kho Admin truy cập Web [Khotot.vn](http://Khotot.vn) để chuyển trạng thái "Hoàn thành" cho đơn hàng ngay lập tức.
4. Kiểm soát & Hóa đơn:
   - Sale Admin: Cuối buổi rà soát danh sách đơn "Chờ nhận hàng". Nếu còn đơn treo quá lâu, phải báo ngay cho Kho Admin để kiểm tra xem khách chưa tới hay Kho Admin quên cập nhật trên Web.
   - Kế toán: Kiểm tra danh sách đơn đã "Hoàn thành" (bao gồm cả Viettel Post và Lấy tại kho) để thực hiện xuất hóa đơn điện tử hàng loạt trước 17:00 hàng ngày.
