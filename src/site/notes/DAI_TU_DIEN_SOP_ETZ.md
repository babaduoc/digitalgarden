---
{"dg-publish":true,"permalink":"/dai-tu-dien-sop-etz/","title":"🧠 ĐẠI TỪ ĐIỂN SOP & VẬN HÀNH WEB ETZ","dg-note-properties":{"title":"🧠 ĐẠI TỪ ĐIỂN SOP & VẬN HÀNH WEB ETZ"}}
---

# 🧠 ĐẠI TỪ ĐIỂN SOP & VẬN HÀNH WEB ETZ (MASTER KNOWLEDGE)

Tài liệu này là "Bộ não" trung tâm giúp Claude và nhân sự vận hành hiểu toàn bộ dự án mà không cần đọc lại hàng chục file nhỏ lẻ.

---

## 1. TỔNG QUAN DỰ ÁN (PROJECT CORE)
- **Tên dự án:** DSS WEB SALE PLATFORM (Web ETZ).
- **Mô hình:** B2B nội bộ (DSS -> MD -> SD). Không bán lẻ.
- **Giai đoạn hiện tại:** Giai đoạn 1 (Chỉ chạy kho ETZ, chưa kích hoạt kho MD).

## 2. NHÂN VẬT & CHIẾN TUYẾN (ROLES)
- **ADMIN (DSS):** "Nhạc trưởng" điều phối, duyệt sản phẩm, quản lý pháp lý/thuế.
- **MD (Master Dealer):** Đối tác kho tỉnh. Phụ trách tồn kho cục bộ và đóng gói tại chỗ.
- **SD (Sub-Dealer):** Khách hàng đại lý. Mua hàng qua Web, nhận thông báo qua Zalo OA.

## 3. CÁC QUY TẮC VẬN HÀNH VÀNG (GOLDEN RULES)
### A. Luồng Đơn hàng (Order Flow)
- Đơn hàng mới -> Xác nhận (30p) -> In Pick List -> Nhặt hàng -> Đóng gói (Chụp ảnh bằng chứng) -> Bàn giao Shipper -> Gửi thông báo Zalo.

### B. SLA Kiểm soát (Service Level Agreement)
- **Xác nhận đơn:** ≤ 4 giờ làm việc.
- **Xuất kho:** ≤ 24 giờ kể từ khi xác nhận.
- **Tồn kho:** Phải cập nhật tối thiểu 1 lần/ngày.

### C. Pháp lý & Thuế (Critical)
- Tiền đơn MD **không được** đi qua tài khoản ETZ để tránh rủi ro VAT 10% doanh thu MD.
- Phải phân định rõ: "Sản phẩm do ETZ bán" và "Sản phẩm do Đối tác phân phối".

## 4. DANH MỤC SOP ĐÃ THIẾT LẬP
1.  **SOP Kho Giai đoạn 1**: [SOP_Kho_ETZ_Giai_Doan_1.md](file:///D:/01%20Google%20DahuaDSS/01%20DSS%20CLUB/18%20Web%20b%C3%A1n%20h%C3%A0ng%20SD/SOP_Kho_ETZ_Giai_Doan_1.md)
2.  **Checklist Vận hành**: [Checklist_Giai_Doan_1_Kho_ETZ.md](file:///D:/01%20Google%20DahuaDSS/01%20DSS%20CLUB/18%20Web%20b%C3%A1n%20h%C3%A0ng%20SD/Checklist_Giai_Doan_1_Kho_ETZ.md)
3.  **Tài liệu Dự án Chuẩn**: [Tai_Lieu_Du_An_Chuan.md](file:///D:/01%20Google%20DahuaDSS/01%20DSS%20CLUB/18%20Web%20b%C3%A1n%20h%C3%A0ng%20SD/Tai_Lieu_Du_An_Chuan.md)

---
> [!IMPORTANT]
> **Hướng dẫn cho AI:** Mỗi khi người dùng hỏi về bất kỳ SOP hay quy trình nào của Web ETZ, hãy tham soát file này trước tiên để lấy ngữ cảnh chuẩn nhất.
