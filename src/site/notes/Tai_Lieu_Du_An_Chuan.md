---
{"dg-publish":true,"permalink":"/tai-lieu-du-an-chuan/","title":"🏗️ Tài Liệu Dự Án Chuẩn DSS WEB SALE PLATFORM","dg-note-properties":{"title":"🏗️ Tài Liệu Dự Án Chuẩn DSS WEB SALE PLATFORM"}}
---

# 🏗️ TÀI LIỆU DỰ ÁN: DSS WEB SALE PLATFORM

**Mục tiêu:** Xây dựng nền tảng B2B chuyên biệt để DSS phân phối hàng hóa trực tiếp tới Sub-Dealer (SD) thông qua mạng lưới Master Dealer (MD) tỉnh, loại bỏ khách lẻ và tối ưu hóa chuỗi cung ứng.

---

## 1. MÔ HÌNH HOẠT ĐỘNG TỔNG THỂ
- **Trung tâm điều phối:** DSS Admin (Hà Nội/TP.HCM).
- **Điểm phân phối:** Kho tổng DSS & Các kho MD vệ tinh tại các tỉnh.
- **Khách hàng:** Chỉ dành cho Sub-Dealer (SD) đã được định danh và xác thực.
- **Luồng tiền:** Tích hợp cổng thanh toán 9Pay, QR Code, COD hoặc thanh toán tại quầy.

---

## 2. PHÂN QUYỀN VAI TRÒ (ROLES)

### 👤 DSS ADMIN (Tổng quản trị)
- Duyệt sản phẩm niêm yết của MD.
- Quản lý danh mục, giá bán và các chương trình khuyến mãi toàn hệ thống.
- Theo dõi báo cáo doanh thu, tồn kho và hiệu suất của từng MD.
- Cài đặt quy tắc gợi ý sản phẩm và kết nối API (ViettelPost, GHTK, 9Pay, Zalo OA).

### 👥 MASTER DEALER (MD - Đối tác kho tỉnh)
- Quản lý kho riêng: Thêm/sửa số lượng tồn kho.
- Nhận đơn, in phiếu giao hàng và xử lý đóng gói đơn hàng từ SD trong khu vực.
- Theo dõi báo cáo doanh số và tỷ lệ hoàn tất đơn hàng của cá nhân.

### 💼 SUB-DEALER (SD - Khách hàng đại lý)
- Đăng nhập qua OTP Zalo để mua hàng.
- Xem sản phẩm theo kho gần nhất hoặc theo tỉnh thành.
- Theo dõi trạng thái đơn hàng thời gian thực qua Zalo OA.

---

## 3. CHECKLIST TÍNH NĂNG TRỌNG YẾU

### 🔐 Xác thực & Bảo mật
- [ ] Đăng nhập số điện thoại + OTP Zalo OA.
- [ ] Kiểm duyệt tài khoản SD thủ công từ Admin trước khi cho phép đặt hàng.
- [ ] Ghi Log toàn bộ thao tác thêm/xóa/sửa của Admin và MD.

### 📦 Quản lý Kho & Sản phẩm
- [ ] Hệ thống đa kho (Multi-warehouse logic).
- [ ] Tự động ẩn sản phẩm khi tồn kho = 0.
- [ ] Bộ lọc nâng cao: Theo SKU, Tỉnh thành, Kho, Danh mục.

### 🛒 Quy trình Đơn hàng
- [ ] Trạng thái đơn: Chờ xử lý -> Đã xác nhận -> Đang giao -> Hoàn tất.
- [ ] Hỗ trợ đơn hàng "Mix" (nhiều kho) - Dự kiến nâng cấp.
- [ ] In phiếu nhặt hàng (Pick list) và Phiếu giao hàng tự động.

### 🔔 Thông báo & Tương tác
- [ ] Gửi thông báo đơn mới tới MD qua Zalo OA.
- [ ] Cập nhật hành trình đơn hàng tới SD qua Zalo OA.
- [ ] Pop-up cảnh báo đơn hàng trễ SLA cho Admin.

---

## 4. KỸ THUẬT & TÍCH HỢP
- **Nền tảng:** Web-based (Dark/Light mode), giao diện chuẩn TMĐT.
- **Thanh toán:** 9Pay (QR, ATM, Credit Card).
- **Vận chuyển:** API Viettel Post, GHTK.
- **Giao tiếp:** Zalo OA API.

---

## 🚀 LỘ TRÌNH PHÁT TRIỂN (ROADMAP)
1. **Giai đoạn 1:** Vận hành kho nội bộ ETZ, chạy thử nghiệm với nhóm SD thân thiết.
2. **Giai đoạn 2:** Mở rộng kết nối kho MD tỉnh, kích hoạt hệ thống chấm điểm SLA.
3. **Giai đoạn 3:** Xây dựng App Mobile và tích hợp CRM chuyên sâu.

---
> [!NOTE]
> Tài liệu này được tổng hợp từ `DSS_Web_Sale_Platform_1.docx` và `Function_Checklist.xlsx` để phục vụ công tác lập trình và vận hành chuẩn hóa.
