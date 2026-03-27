---
{"dg-publish":true,"permalink":"/checklist-giai-doan-1-kho-etz/","title":"Checklist Giai Đoạn 1 Vận Hành Kho Nội Bộ ETZ","dg-note-properties":{"title":"Checklist Giai Đoạn 1 Vận Hành Kho Nội Bộ ETZ"}}
---

# CHECKLIST GIAI ĐOẠN 1: VẬN HÀNH KHO NỘI BỘ ETZ

Giai đoạn này tập trung 100% vào việc vận hành kho hàng của ETZ (không có kho MD), đảm bảo luồng hàng đi nhanh, chính xác và chuyên nghiệp ngay từ đầu.

## 📦 1. QUẢN LÝ KHO & TỒN KHO (INVENTORY)
- [ ] **Kiểm kê đầu kỳ:** Thực hiện đếm thực tế toàn bộ sản phẩm tại kho ETZ và đối soát với số lượng trên hệ thống website.
- [ ] **Phát triển mã SKU:** Đặt mã SKU chuẩn cho từng sản phẩm để tránh nhầm lẫn khi nhặt hàng (Picking).
- [ ] **In nhãn mã vạch (Barcode):** Dán mã vạch lên từng sản phẩm/kệ hàng để chuẩn hóa việc quét hàng khi xuất kho.
- [ ] **Thiết lập Ngưỡng cảnh báo:** Cài đặt thông báo tự động khi tồn kho một mặt hàng xuống dưới mức tối thiểu (ví dụ: còn 5 sản phẩm).

## 🛒 2. QUY TRÌNH XỬ LÝ ĐƠN HÀNG (ORDER FULFILLMENT)
- [ ] **Xác nhận đơn hàng (CS):** Liên hệ khách hàng xác nhận thông tin giao hàng trong vòng 30 phút kể từ khi có đơn.
- [ ] **In Phiếu soạn hàng (Pick list):** Tự động tạo danh sách sản phẩm cần nhặt từ kho theo từng đơn.
- [ ] **Đóng gói chuẩn (Packing):** 
    - [ ] Thùng carton chịu lực + Chống sốc (PE/Xốp).
    - [ ] Dán băng keo có logo ETZ (nếu có) để tăng nhận diện thương hiệu.
- [ ] **Bằng chứng xuất kho:** Chụp ảnh kiện hàng đã đóng gói kèm vận đơn trước khi giao cho đối tác vận chuyển.

## 🚚 3. VẬN CHUYỂN & GIAO NHẬN (LOGISTICS)
- [ ] **Kết nối Carrier:** Thiết lập tài khoản và kết nối API với các bên vận chuyển (Viettel Post, GHTK, v.v.).
- [ ] **Bàn giao đơn hàng:** Có ký nhận biên bản bàn giao danh sách đơn hàng cho shipper hàng ngày.
- [ ] **Theo dõi Tracking:** Kiểm tra trạng thái đơn hàng định kỳ 2 lần/ngày để xử lý kịp thời các đơn giao chậm hoặc gặp sự cố.

## 📑 4. CHỨNG TỪ & KẾ TOÁN
- [ ] **In Phiếu xuất kho:** Kèm theo đơn hàng khi gửi cho khách (Ghi rõ tên, số lượng, giá và thông tin bảo hành).
- [ ] **Hóa đơn điện tử:** Cấu hình luồng xuất hóa đơn đỏ (VAT) tự động (nếu khách yêu cầu).
- [ ] **Đối soát COD:** Thực hiện kiểm tra dòng tiền từ các đơn vị vận chuyển trả về hàng tuần.

## 🛠️ 5. QUY TRÌNH HÀNG HOÀN (RMA)
- [ ] **Kiểm tra hàng trả:** Quy định bước kiểm tra trạng thái hàng khi khách trả về (Còn nguyên seal? Trầy xước?).
- [ ] **Nhập kho ngược:** SOP đưa hàng trả về lại tồn kho hệ thống sau khi đã kiểm tra chất lượng.

---
> [!IMPORTANT]
> **Ưu tiên số 1:** Hoàn thiện khâu **In Phiếu soạn hàng** và **Bằng chứng xuất kho** để tránh nhầm lẫn và giảm thiểu rủi ro khiếu nại từ khách hàng.
