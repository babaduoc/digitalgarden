---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-12-quy-trinh-doi-soat-ke-toan-hang-thang/","title":"SOP 12 — QUY TRÌNH ĐỐI SOÁT KẾ TOÁN HÀNG THÁNG","tags":["SOP","Kế toán","Đối soát","Vận hành"],"dg-note-properties":{"title":"SOP 12 — QUY TRÌNH ĐỐI SOÁT KẾ TOÁN HÀNG THÁNG","tags":["SOP","Kế toán","Đối soát","Vận hành"]}}
---


# 🛡️ SOP 12 — QUY TRÌNH ĐỐI SOÁT KẾ TOÁN HÀNG THÁNG

> **Dự án:** Web ETZ — Khotot.vn
> **Mục tiêu:** Đảm bảo khớp dữ liệu 100% giữa Website (Web Admin), Phần mềm kế toán (MISA), và Dòng tiền thực tế (Ngân hàng).
> **Phiên bản:** 1.0 | **Cập nhật:** 2026-04-10
> **Phòng ban:** Kế toán & Vận hành

---

## 🎯 MỤC TIÊU
- Kiểm soát doanh thu thực tế so với doanh thu ghi nhận trên hệ thống.
- Phát hiện và xử lý các đơn hàng lỗi, đơn hàng chưa thanh toán hoặc sai lệch công nợ.
- Đảm bảo tính pháp lý về hóa đơn điện tử cho 100% giao dịch thành công.

---

## 🔄 SƠ ĐỒ QUY TRÌNH (FLOWCHART)

```mermaid
graph TD
    %% Định nghĩa nhân vật %%
    classDef acc fill:#E8F5E9,stroke:#4CAF50,color:#1B5E20;
    classDef admin fill:#E3F2FD,stroke:#2196F3,color:#0D47A1;
    classDef system fill:#ECEFF1,stroke:#607D8B,color:#263238;

    Start([Ngày 30/31 hàng tháng]) --> Step1[Bước 1: Chốt dữ liệu & Xuất báo cáo]
    Step1 --> Step2[Bước 2: Đối soát Doanh thu WEB vs MISA]
    
    Step2 --> Check1{Khớp số?}
    Check1 -- "Sai lệch" --> Fix1[Sale Admin rà soát đơn treo/hủy]
    Check1 -- "Khớp" --> Step3[Bước 3: Đối soát Dòng tiền MISA vs Ngân hàng]
    
    Fix1 --> Step2
    
    Step3 --> Check2{Khớp tiền?}
    Check2 -- "Sai lệch" --> Fix2[Kế toán check phí bưu điện/phí ngân hàng]
    Check2 -- "Khớp" --> Step3a[Bước 3.1: Đối soát Phí ngân hàng & Ship]
    
    Step3a --> Step4[Bước 4: Đối soát Hóa đơn & Thuế]
    
    Fix2 --> Step3
    
    Step4 --> Step5[Bước 5: Hoàn tất biên bản & Lưu trữ]
    Step5 --> End([Kết thúc chu kỳ])

    class Start,End,Step1,Step3,Step4,Step5 acc;
    class Step2,Fix1 admin;
    class Check1,Check2,API system;
```

---

## 📝 CHI TIẾT CÁC BƯỚC THỰC HIỆN

### 1. Giai đoạn 1: Chốt dữ liệu & Xuất báo cáo (Cut-off)
**Thời điểm:** Sau 17:00 ngày cuối cùng của tháng.
- **Kế toán:** Xuất báo cáo **Bán hàng chi tiết** theo ngày trên MISA (Lọc mã BH).
- **Sale Admin:** Xuất danh sách đơn hàng hoàn thành (Completed) trên **Web Admin Dashboard**.
- **Công cụ:** Excel/Google Sheet.

### 2. Giai đoạn 2: Đối soát Doanh thu (Web vs MISA)
- **Mục tiêu:** Đảm bảo mọi đơn hoàn thành trên Web đều đã được tạo mã BH trên MISA.
- **Thực hiện:**
    - So sánh **Mã đơn hàng** giữa Web và MISA.
    - Kiểm tra tổng giá trị doanh thu (sau giảm giá).
- **Xử lý sai lệch:** Nếu có đơn trên Web nhưng không có trên MISA, Sale Admin phải bổ sung hoặc giải trình lý do (ví dụ: đơn đổi hàng ngoài hệ thống).

### 3. Giai đoạn 3: Đối soát Dòng tiền & Chi phí liên quan
- **Mục tiêu:** Khớp dòng tiền thực tế thu về và kiểm soát các chi phí giao dịch/vận hành đơn hàng.
- **3.1. Đối soát Phí giao dịch (Bank/SePay fees):**
    - So khớp tổng số tiền của các mã đơn **BH** trên MISA với số dư tăng thêm trên tài khoản Ngân hàng.
    - Khấu trừ biểu phí dịch vụ (SePay/Phí chuyển khoản) để khớp số dư Net.
- **3.2. Đối soát Phí vận chuyển (Shipment fees):**
    - Tập hợp danh sách mã vận đơn (Waybill) đã giao thành công trong tháng.
    - Đối chiếu phí ship thực tế bưu điện (Viettel Post) thu với số tiền phí ship đã thu của khách trên đơn hàng.
    - Ghi nhận chênh lệch phí ship (nếu có) vào báo cáo chi phí vận hành.
- **Lưu ý:** Nếu có đơn đã giao nhưng tiền chưa về (đơn Viettel Post đang đối soát phí), Kế toán ghi nhận vào danh sách **"Công nợ đang treo"**.

### 4. Giai đoạn 4: Đối soát Hóa đơn & Thuế
- **Mục tiêu:** Đảm bảo tính pháp lý.
- **Thực hiện:**
    - Đối chiếu danh sách đơn BH đã hoàn tất với danh sách hóa đơn điện tử đã phát hành.
    - Đảm bảo 100% đơn hàng khách hàng yêu cầu hóa đơn đều đã được gửi link HĐĐT.
    - Rà soát các biên bản hủy hóa đơn (nếu có đơn bị trả hàng/hoàn tiền trong tháng).

### 5. Giai đoạn 5: Hoàn tất biên bản & Báo cáo tổng hợp
- Lập **Biên bản đối soát tháng** (Theo mẫu 08-BBDS).
- **Báo cáo Lợi nhuận Net:** Tổng doanh thu - [Giá vốn hàng bán + Phí ngân hàng + Phí vận chuyển].
- Chốt số dư tồn kho cuối tháng trên MISA để đối chiếu với Kho thực tế.
- Lưu trữ file Excel đối soát vào thư mục: `Nam_2026/Thang_X`.

---

## ⚠️ LƯU Ý QUAN TRỌNG
- **Nguyên tắc "Đơn nào, Tiền nấy":** Tuyệt đối không gộp chung nhiều tháng khi đối soát.
- **Xử lý hoàn tiền:** Các đơn hàng hoàn tiền (Refund) theo [SOP 07](SOP_07_Xu_Ly_Khieu_Nai_Hoan_Tra) phải có chứng từ hoàn tiền đính kèm vào báo cáo đối soát tháng.
- **Thời hạn:** Hoàn tất đối soát trước ngày 05 của tháng kế tiếp.

---
*Tài liệu này là quy chuẩn đối soát chính thức của bộ phận Kế toán Web ETZ.*
