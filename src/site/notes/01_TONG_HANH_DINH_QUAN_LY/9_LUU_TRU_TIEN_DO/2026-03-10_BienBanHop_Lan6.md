---
{"dg-publish":true,"permalink":"/01-tong-hanh-dinh-quan-ly/9-luu-tru-tien-do/2026-03-10-bien-ban-hop-lan6/","dg-note-properties":{"permalink":"/index/"}}
---


# BIÊN BẢN CUỘC HỌP — Lần 6 (10/03/2026)

**Dự án:** Website TMĐT DSS / ETZ (khotot.vn)  
**Hình thức:** Họp trực tuyến (Zoom)  
**Thời gian:** 10/03/2026  
**Tham dự:** Hoàng An (Team IT – N2), Anh Được, Thu Châm (ETZ – Admin vận hành)

---

## I. MỤC TIÊU CUỘC HỌP
- Kiểm tra và trao đổi các chức năng hệ thống Website
- Rà soát: Quản lý đơn hàng, Thanh toán, Ngân hàng, Tồn kho, Hủy đơn, OTP, Giao diện

---

## II. NỘI DUNG THẢO LUẬN CHÍNH

### 1. Tích hợp thanh toán & Bộ Công Thương
- Hệ thống đã có chức năng đăng ký thông tin với Bộ Công Thương
- Tích hợp thanh toán **chưa hoàn thiện**
- Cần hoàn thiện logic xác nhận thanh toán và chuẩn hóa quy trình kiểm tra đơn hàng

### 2. Quy trình hủy đơn hàng
- Hiện tại: có thể hủy trước khi xuất kho; sau xuất kho cần xử lý riêng
- Thiếu cơ chế rõ ràng cho: cập nhật trạng thái, đồng bộ tồn kho, xử lý khi đang vận chuyển
- Cần bổ sung logic: hủy trước/sau xuất kho, hủy khi đang vận chuyển

### 3. Liên kết ngân hàng & Thanh toán
- Đã thử nghiệm: ACB, MB Bank, VPBank
- Một số ngân hàng chưa hỗ trợ đầy đủ
- **Kết quả:** Test chuyển khoản thành công ✅

### 4. Quản lý tồn kho
- Lỗi: Tồn kho = 0 khách vẫn đặt được
- Đề xuất: Khóa đặt hàng khi tồn = 0, hiển thị thông báo hết hàng, giới hạn số lượng đặt

### 5. Lỗi OTP xác thực
- Hệ thống gửi OTP **trùng lặp 2 lần**
- Cần kiểm tra lại logic gửi OTP và cấu hình hệ thống xác thực

### 6. Giao diện & Trải nghiệm người dùng
- Tên danh mục dài gây tràn chữ
- Hình ảnh hiển thị khác nhau giữa điện thoại và laptop
- Layout sản phẩm chưa tối ưu
- Cần: chuẩn hóa responsive, kích thước ảnh, giới hạn ký tự danh mục

---

## III. VIỆC CẦN LÀM TIẾP THEO

- [ ] Hoàn thiện logic xác nhận thanh toán
- [ ] Bổ sung quy trình hủy đơn theo từng trạng thái
- [ ] Fix lỗi OTP gửi trùng
- [ ] Khóa đặt hàng khi tồn kho = 0
- [ ] Chuẩn hóa UI responsive & kích thước ảnh sản phẩm
- [ ] Hoàn thiện lịch sử giao dịch và đồng bộ trạng thái ngân hàng

---

## IV. KẾT LUẬN
Cuộc họp đã rà soát các chức năng chính của hệ thống TMĐT DSS. Các bên thống nhất tiếp tục điều chỉnh để đảm bảo nền tảng vận hành ổn định trước khi triển khai chính thức.


---
[🏠 Trang chủ](../../index)