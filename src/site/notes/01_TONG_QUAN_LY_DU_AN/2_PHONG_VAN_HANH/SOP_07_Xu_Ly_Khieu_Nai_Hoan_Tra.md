---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/2-phong-van-hanh/sop-07-xu-ly-khieu-nai-hoan-tra/","title":"SOP 07 — QUY TRÌNH XỬ LÝ KHIẾU NẠI & HOÀN TRẢ","dg-note-properties":{"title":"SOP 07 — QUY TRÌNH XỬ LÝ KHIẾU NẠI & HOÀN TRẢ"}}
---


# 🛡️ SOP 07 — QUY TRÌNH XỬ LÝ KHIẾU NẠI & HOÀN TRẢ

> **Dự án:** Web ETZ — Khotot.vn
> **Mục tiêu:** Xử lý nhanh chóng các khiếu nại về hàng lỗi, tem hỏng và thực hiện quy trình hoàn tiền/trừ nợ chính xác.
> **Phiên bản:** 1.0 | **Cập nhật:** 2026-04-02

---

## 🎯 MỤC TIÊU
Đảm bảo quyền lợi cho khách hàng (Đại lý lẻ) khi gặp sự cố sản phẩm, đồng thời kiểm soát chặt chẽ việc nhập lại kho và đối soát tài chính.

---

## 🔄 SƠ ĐỒ QUY TRÌNH (FLOWCHART)

```mermaid
graph TD
    %% Định nghĩa nhân vật %%
    classDef client fill:#F3E5F5,stroke:#9C27B0,color:#4A148C;
    classDef admin fill:#E3F2FD,stroke:#2196F3,color:#0D47A1;
    classDef warehouse fill:#ECEFF1,stroke:#607D8B,color:#263238;
    classDef accounting fill:#FFF3E0,stroke:#FF9800,color:#E65100;

    A([Bắt đầu: Khách báo khiếu nại qua Zalo]) --> B[Admin tiếp nhận & Check Video đối soát]
    B --> C{Video & SN hợp lệ?}
    
    C -- "Không hợp lệ" --> D[Từ chối & Giải thích khách]
    C -- "OK" --> E[Admin báo Kho/Sếp check lại hàng]
    
    E --> F[Kho check thực tế & Nhập lại kho]
    F --> G[Kho xác nhận lại cho Admin]
    
    G --> H[Admin báo Group Kế toán_Sale Admin]
    H --> I[Xác nhận: Hoàn tiền hoặc Trừ nợ đơn sau]
    
    I --> J[Kế toán thực hiện Trừ nợ/Hoàn trả]
    J --> K([Kết thúc: Thông báo kết quả cho Khách])

    class A client;
    class B,E,H,K admin;
    class F,G warehouse;
    class I,J accounting;
```

---

## 📝 CHI TIẾT CÁC BƯỚC THỰC HIỆN

### 1. Tiếp nhận Khiếu nại (Admin)
- **Kênh tiếp nhận:** Khách hàng (Đại lý lẻ) gửi yêu cầu và Video link qua Zalo cho Admin.
- **Tiêu chuẩn Video:** 
    - Phải quay rõ quá trình quét Serial Number (SN).
    - Quay rõ tình trạng tem bảo hành (lỗi, hỏng) hoặc hàng lỗi.
- **Thao tác:** Admin kiểm tra link video. Nếu hợp lệ, chuyển sang bước tiếp theo.

### 2. Kiểm tra & Nhập kho (Kho)
- **Báo cáo:** Admin báo trực tiếp cho Sếp hoặc Nghĩa (Kho) để chuẩn bị kiểm hàng.
- **Thực hiện:** Kho (Nghĩa) kiểm tra thực tế hàng lỗi/trả về.
- **Xác nhận:** Sau khi kiểm tra đạt yêu cầu nhập lại, Kho xác nhận lại cho Admin để tiến hành bước tài chính.

### 3. Đối soát & Xử lý tài chính (Kế toán)
- **Thông báo:** Admin gửi thông tin xác nhận từ Kho vào **Group Zalo: Kế toán & Sale Admin**.
- **Hình thức xử lý:** Admin và Kế toán thống nhất phương án:
    1. **Hoàn tiền:** Chuyển trả trực tiếp cho khách.
    2. **Trừ nợ:** Khấu trừ vào giá trị đơn hàng tiếp theo.
- **Thực hiện:** Kế toán thực hiện nghiệp vụ trên phần mềm và chứng từ.

### 4. Hoàn tất (Admin)
- Thông báo kết quả cuối cùng cho khách hàng qua Zalo.

---

## ⚠️ LƯU Ý QUAN TRỌNG
- **Yếu tố Video:** Đây là bằng chứng quan trọng nhất để Admin duyệt khiếu nại. Tuyệt đối không duyệt nếu thiếu video quét SN/Tem BH.
- **Xác nhận Kho:** Chỉ được báo Kế toán hoàn tiền khi đã có xác nhận "Đã nhận hàng - OK" từ Kho.

---
*Tài liệu này là quy chuẩn xử lý khiếu nại chính thức của Web ETZ.*
