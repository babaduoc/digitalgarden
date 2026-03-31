---
{"dg-publish":true,"permalink":"/01-tong-hanh-dinh-quan-ly/10-meeting/2026-03-30-bbh-lan-1-trien-khai-web-detail/","title":"CHI TIẾT NGUYÊN BẢN: BIÊN BẢN HỌP LẦN 1","dg-note-properties":{"title":"CHI TIẾT NGUYÊN BẢN: BIÊN BẢN HỌP LẦN 1"}}
---


# 📄 NỘI DUNG NGUYÊN BẢN (LAYER 02)

> **File gốc (RAW):** [02_KHO_DU_LIEU_THO_RAW/10_MEETING/18_1- LẦN 1- BIÊN BẢN HỌP & KẾ HOẠCH TRIỂN KHAI WEB KHOTOT - ETZ & Team IT.pdf](/img/user/02_KHO_DU_LIEU_THO_RAW/10_MEETING/18_1-%20L%E1%BA%A6N%201-%20BI%C3%8AN%20B%E1%BA%A2N%20H%E1%BB%8CP%20&%20K%E1%BA%BE%20HO%E1%BA%A0CH%20TRI%E1%BB%82N%20KHAI%20WEB%20KHOTOT%20-%20ETZ%20&%20Team%20IT.pdf)

---

18/1- LẦN 1- BIÊN BẢN HỌP & KẾ HOẠCH TRIỂN KHAI WEB KHOTOT - ETZ & Team IT

BIÊN BẢN HỌP & KẾ HOẠCH TRIỂN KHAI WEB ETZ
Ngày họp: 18/01/2026 - Chủ Nhật - Hình thức Zoom
Thành phần: Team IT – ETZ
Mục tiêu: Hoàn thiện flow thanh toán – giỏ hàng – thông báo – sẵn sàng viết SOP & demo SD

I. PHÂN CÔNG TỔNG QUAN (NHÌN NHANH)
• Team IT: Code – fix logic – tích hợp – demo kỹ thuật
• Admin ETZ (bạn): Nội dung, quy trình, text hiển thị, SOP, pháp lý, trải nghiệm người dùng
• Phối hợp: Các phần cần IT build nhưng Admin cung cấp nội dung / rule

II. CHI TIẾT THEO TỪNG MODULE

1. GIAO DIỆN MOBILE
Hiện trạng
• Giao diện mobile chưa hoàn thiện, team IT báo lại sẽ hoàn thiện sau
Các mục team ETZ mới nhìn nhận thấy, giao diện: Không thấy mục "Khuyến mãi" - "Liên hệ" - "Bài viết" trên giao diện Mobile

Việc cần làm:
- Tối ưu UI/UX mobile (Phụ trách: IT, Thời gian dự kiến: 2–3 tuần, Ghi chú: Làm song song với fix thanh toán)
- Test lại toàn bộ flow mobile (Phụ trách: IT + Admin, Thời gian: Sau khi fix, Ghi chú: Admin test nghiệp vụ)

2. THÔNG BÁO HỆ THỐNG & ZALO OA
2.1 Thông báo trong web
Vấn đề
• Phần thông báo trên web chưa hiển thị ổn định
• Không gửi được riêng cho từng user (gửi SD cho MD => mới gửi toàn bộ, chưa chỉ định được user nào cả)

Phân công:
- Fix hiển thị thông báo (IT, Ngắn hạn)
- Cho phép gửi thông báo theo user - test (IT, Sau khi fix core, Họp 27/1: Sau khi fix core xong mới gửi lại)
- Xác định các loại thông báo (Admin, Song song)

Admin ETZ cần chuẩn bị
• Danh sách loại thông báo:
◦ Thông báo hệ thống
◦ Thông báo tài khoản
◦ Thông báo khuyến mãi
◦ Thông báo vi phạm / khóa tài khoản
• Nội dung mẫu từng loại (text)

1. Bật chức năng xác thực trước khi mua hàng (bắt buộc), để không cần tiện cho bước sau
2. Ở mục đăng nhập Thêm cái cái chức năng khi khách hàng quên mật khẩu => gửi lấy lại mk qua lấy mã OTP qua zalo OA (phần này IT sẽ review lại),
3. Mã OTP của khách cho admin thấy - ngoài hợp đồng hiện chưa hỗ trợ

2.2 Zalo OA
Timeline: Trong tuần này (19-24/1)
- Fix kết nối Zalo OA (IT, Ưu tiên cao)
- Test thông báo đơn hàng (IT + Admin, Test end-to-end, Họp 27/1: Ở bước "thêm sp vào giỏ hàng" Có thêm nút "thêm địa chỉ" để nhập địa chỉ)
- Soạn nội dung tin nhắn (Admin, Dùng lâu dài, Họp 27/1: Hiện tại OA - không hỗ trợ, hoặc nếu có phải đợi duyệt lâu theo mẫu của nó)

3. GIÁ SẢN PHẨM & PHÂN LOẠI
• Trao đổi giá hiển thị của sản phẩm = giá thấp nhất
Việc cần làm
- Ràng buộc không cho giá = 0đ (IT)
- Cảnh báo nhập giá bất thường (IT)
- Xác định rule giá hiển thị (Admin)

📌 Admin lưu ý: Rule này sẽ đưa vào Điều khoản SD/MD

4. LỊCH SỬ ĐƠN HÀNG & HỦY ĐƠN
Việc cần làm:
- Thêm mục “Đơn đã hủy” (IT, (19-24/1), Hiển thị: Thêm tab hoặc filter: Đơn đã hủy. Mỗi đơn hiển thị trạng thái: Đã hủy)
- Hiển thị điều kiện hủy trước khi hủy (IT, (19-24/1))

Soạn nội dung điều kiện hủy (Admin, 21/1 thứ 4):
Popup xác nhận hủy đơn hàng
Trigger: Khi user bấm nút “Hủy đơn”
Hiển thị popup gồm Title "Xác nhận hủy đơn hàng"

Nội dung text hiển thị ở dưới:
"Điều kiện hủy đơn hàng:
• Chỉ cho phép hủy khi đơn hàng chưa được xác nhận xử lý hoặc chưa bàn giao cho đơn vị vận chuyển.
• Đơn hàng đã giao hoặc đang vận chuyển không thể hủy."

Action Checkbox: Tôi đã đọc và hiểu điều kiện hủy đơn hàng
Button: Hủy đơn (disable nếu chưa tick checkbox), Quay lại

5. GIỎ HÀNG (ĐA KHO)
Hiện trạng
• SP từ nhiều kho → tách đơn & thanh toán riêng
Phân công:
- Fix & demo flow giỏ hàng đa kho (IT)
- Hiển thị cảnh báo cho user (IT)
- Soạn nội dung cảnh báo (Admin)

Text Admin đề xuất (dùng luôn):
“Đơn hàng của bạn bao gồm sản phẩm từ nhiều kho khác nhau. Hệ thống sẽ tách đơn và thanh toán riêng theo từng kho để đảm bảo tiến độ giao hàng.”

6. MÃ GIẢM GIÁ & VÍ VOUCHER
Định hướng
• Có ví voucher riêng cho user
• Quản lý tập trung, không phát mã thủ công
Phân công:
- Xây cấu trúc ví voucher (IT)
- Phân quyền voucher (MD / SD / kho) (IT)
- Xác định rule khuyến mãi (Admin)

Admin check làm rõ lại:
• Voucher dùng khi nào
• Voucher gắn user hay gắn kho
• Có thời hạn / điều kiện gì

7. VẬN CHUYỂN
- Duy trì Viettel Post mặc định (hiện tại) (IT và DSS)
- Tìm & đề xuất thêm ĐVVC (DSS / Admin)
- Chuẩn bị tích hợp thêm (IT)
📌 Ghi chú: chưa ưu tiên cao, làm sau thanh toán

8. THANH TOÁN (ƯU TIÊN CAO NHẤT)
Thiếu hiện tại
• Chưa có “Thanh toán lại”
• Một số case không hiển thị thành công
Phân công:
- Fix trạng thái thanh toán (IT)
- Thêm chức năng "thanh toán lại" (IT)
- Test full flow đầu-cuối (IT + Admin)
- Soạn nội dung hướng dẫn thanh toán (Admin)

⚠️ Nếu chưa xong: không thể mở SD

9. QUẢN LÝ TÀI KHOẢN & LỊCH SỬ
- Tạo role Admin / Nhân viên (IT)
- Lưu lịch sử thao tác (IT)
- Quy định phân quyền (Admin)

10. SẢN PHẨM & KHO
- Lưu lịch sử thay đổi giá (IT)
- Import Excel (chưa ưu tiên) (IT)
- Fix trạng thái đơn (IT)
- Yêu cầu hóa đơn điện tử (form) (IT)
- Soạn nội dung yêu cầu HĐ (Admin)

11. DUYỆT SẢN PHẨM MD
- Tab duyệt sản phẩm MD (IT)
- Quy định giấy tờ MD (Admin)
- Điều khoản trách nhiệm MD (Admin)
Giai đoạn đầu chưa mở MD đại trà

12. BÁO CÁO – PHÁP LÝ – GÓP Ý
- Truy xuất dữ liệu báo cáo (IT)
- Soạn khung báo cáo (Admin)
- Form góp ý gửi IT (IT)
- Quy trình xử lý góp ý (Admin/IT)

III. TIMELINE CHỐT
• Tuần sau: demo giỏ hàng + thanh toán SD
• Chủ nhật tuần sau: demo flow thanh toán hoàn chỉnh
• Trước Tết: fix xong thanh toán + Zalo OA
• Mỗi tuần: 1 buổi họp fix nhanh

IV. VIỆC ADMIN ETZ TRIỂN KHAI SONG SONG
• Viết ~9 bài giới thiệu web
• Chuẩn bị ảnh sản phẩm
• Soạn SOP SD / MD (check trước, chuẩn bị)
• Viết tuyên bố thương hiệu – tạo niềm tin
• Chuẩn bị điều khoản pháp lý

---
*Bản Mirror Layer 02: Nguyên văn 100% từ PDF gốc.*
