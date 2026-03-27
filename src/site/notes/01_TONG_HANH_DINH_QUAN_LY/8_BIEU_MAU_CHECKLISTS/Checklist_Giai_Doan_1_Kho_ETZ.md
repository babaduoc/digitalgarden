---
{"dg-publish":true,"permalink":"/01-tong-hanh-dinh-quan-ly/8-bieu-mau-checklists/checklist-giai-doan-1-kho-etz/","title":"🚀 Checklist Giai Đoạn 1:Vận Hành Kho Nội Bộ ETZ (Cập nhật)","dg-note-properties":{"title":"🚀 Checklist Giai Đoạn 1:Vận Hành Kho Nội Bộ ETZ (Cập nhật)"}}
---

# CHECKLIST GIAI ĐOẠN 1: VẬN HÀNH KHO NỘI BỘ ETZ

Dưới đây là các đầu việc đã được đối soát với tài liệu hiện có trong thư mục **Web ETZ**. Những mục đánh dấu **[x]** là đã có quy trình/tài liệu tương ứng.

## 📦 1. QUẢN LÝ KHO & TỒN KHO (INVENTORY)
- [ ] **Kiểm kê đầu kỳ:** Chưa có báo cáo kiểm kê thực tế.
- [x] **Phát triển mã SKU:** (Đã hoàn thành) - Dựa trên tài liệu `DSSMN-BaoGia...` có mã sản phẩm chi tiết.
- [ ] **In nhãn mã vạch (Barcode):** Chưa triển khai thực tế.
- [ ] **Thiết lập Ngưỡng cảnh báo:** Chưa có cơ chế cảnh báo tự động trên hệ thống.

## 🛒 2. QUY TRÌNH XỬ XLÝ ĐƠN HÀNG (ORDER FULFILLMENT)
- [x] **Xác nhận đơn hàng (CS):** (Đã hoàn thành) - Đã định nghĩa rõ trong tài liệu `NHÂN VIÊN VẬN HÀNH...`.
- [ ] **In Phiếu soạn hàng (Pick list):** Chưa có mẫu phiếu soạn hàng chuẩn.
- [ ] **Đóng gói chuẩn (Packing):** Cần văn bản hóa tiêu chuẩn đóng gói (PE/Xốp).
- [ ] **Bằng chứng xuất kho:** Chưa có quy trình chụp ảnh/quay video kiện hàng.

## 🚚 3. VẬN CHUYỂN & GIAO NHẬN (LOGISTICS)
- [ ] **Kết nối Carrier:** Cần xác nhận API với Viettel Post/GHTK.
- [ ] **Bàn giao đơn hàng:** Cần mẫu biên bản bàn giao cho Shipper.
- [ ] **Theo dõi Tracking:** Chưa thiết lập lịch trình kiểm tra đơn định kỳ.

## 📑 4. CHỨNG TỪ & KẾ TOÁN
- [ ] **In Phiếu xuất kho:** Cần mẫu phiếu xuất kho gửi khách hàng.
- [ ] **Hóa đơn điện tử:** Cần cấu hình luồng xuất VAT tự động.
- [x] **Đối soát COD:** (Đã hoàn thành) - Đã nằm trong mô tả công việc (JD) của nhân sự vận hành.

## 🛠️ 5. QUY TRÌNH HÀNG HOÀN (RMA)
- [x] **Chính sách đổi trả:** (Đã hoàn thành) - Có file `2. Chính sách đổi trả sản phẩm` trong thư mục 4. QTT & Chính sách.
- [ ] **Kiểm tra hàng trả:** Cần SOP kiểm tra thực tế hàng lỗi/hàng nguyên seal khi nhận lại.
- [ ] **Nhập kho ngược:** Chưa có quy trình cập nhật tồn kho sau đổi trả.

---
> [!IMPORTANT]
> **Nhận xét:** Sếp đã hoàn thành tốt phần **Khung nhân sự (JD)** và **Chính sách (Policy)**. Hiện tại cần tập trung "vũ trang" cho nhân viên bằng các **Mẫu biểu (Template)**: Phiếu soạn hàng, Phiếu xuất kho và Biên bản bàn giao.
