---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/10-meeting/2026-03-30-bbh-lan-6-trien-khai-web-detail/","title":"CHI TIẾT NGUYÊN BẢN (v9.1): BIÊN BẢN HỌP LẦN 6","dg-note-properties":{"title":"CHI TIẾT NGUYÊN BẢN (v9.1): BIÊN BẢN HỌP LẦN 6"}}
---


# 📄 NỘI DUNG NGUYÊN BẢN (LAYER 02)

> **File gốc (RAW):** [[02_KHO_DU_LIEU_THO_RAW/10_MEETING/10_3 - LẦN 6 - BIÊN BẢN CUỘC HỌP - CẬP NHẬT TIẾN ĐỘ TRIỂN KHAI WEBSITE ETZ (KHOTOT.VN).docx]]

10/3 - LẦN 6 - BIÊN BẢN CUỘC HỌP - CẬP NHẬT TIẾN ĐỘ TRIỂN KHAI WEBSITE ETZ (KHOTOT.VN)
BIÊN BẢN CUỘC HỌP
Dự án: Hệ thống Website TMĐT DSS / ETZHình thức: Họp trực tuyến (Zoom)Thời gian: 10/03/2026Đơn vị tham gia:
N2 – Hoàng An (đại diện team IT)
ETZ - Anh Được - Thu Châm – Admin vận hành hệ thống

I. MỤC TIÊU CUỘC HỌP
Cuộc họp được tổ chức nhằm:
Kiểm tra và trao đổi các chức năng hệ thống Website 
Rà soát các vấn đề liên quan đến:
Quản lý đơn hàng
Thanh toán
Hệ thống ngân hàng
Quản lý tồn kho
Quy trình hủy đơn
OTP xác thực tài khoản
Giao diện hiển thị sản phẩm
Thảo luận các vấn đề cần điều chỉnh để hệ thống sẵn sàng triển khai vận hành.

II. NỘI DUNG THẢO LUẬN CHÍNH
1. Chức năng đăng ký và tích hợp Bộ Công Thương
Hệ thống đã có chức năng đăng ký thông tin phục vụ đăng ký với Bộ Công Thương.
Tuy nhiên phần tích hợp thanh toán vẫn chưa hoàn thiện.
Vấn đề phát sinh
Quy trình xác nhận thanh toán còn cần kiểm tra thêm.
Cơ chế kiểm tra mã đơn hàng và xác nhận thanh toán có thể phải cập nhật thủ công trong một số trường hợp.
Đề xuất
Hoàn thiện logic xác nhận thanh toán.
Chuẩn hóa quy trình kiểm tra đơn hàng khi thanh toán.

2. Quy trình quản lý và hủy đơn hàng
Nhóm thảo luận về logic xử lý đơn hàng trong hệ thống.
Logic hiện tại
Đơn hàng có thể hủy trước khi hàng được xử lý hoặc xuất kho.
Sau khi hàng đã được vận chuyển, việc hủy đơn sẽ phức tạp hơn và cần xử lý riêng.
Vấn đề phát sinh
Hệ thống chưa có cơ chế rõ ràng để:
Cập nhật trạng thái đơn hàng
Đồng bộ tồn kho
Xử lý khi đơn đã giao vận chuyển
Hướng xử lý
Cần nghiên cứu bổ sung logic:
Hủy đơn trước xuất kho
Hủy đơn sau xuất kho
Xử lý đơn khi đang vận chuyển.

3. Cấu hình hệ thống ngân hàng và thanh toán
Hệ thống đang thử nghiệm liên kết tài khoản ngân hàng.
Các ngân hàng đã thử nghiệm
ACB
MB Bank
VPBank
Vấn đề ghi nhận
Một số ngân hàng chưa được hệ thống hỗ trợ đầy đủ.
Lịch sử giao dịch và trạng thái thanh toán cần được đồng bộ tốt hơn.
Kết quả
Đã thực hiện thử nghiệm giao dịch chuyển khoản thành công.

4. Quản lý tồn kho và đặt hàng
Nhóm trao đổi về cơ chế hiển thị tồn kho và đặt hàng.
Logic hiện tại
Khi tồn kho = 0 → khách hàng vẫn có thể đặt hàng vượt tồn.
Vấn đề
Điều này có thể gây:
Trải nghiệm không tốt cho khách hàng
Rủi ro thiếu hàng
Đề xuất
Xem xét:
Khóa đặt hàng khi tồn kho = 0
Hiển thị thông báo hết hàng
Giới hạn số lượng đặt.

5. Vấn đề OTP và xác thực tài khoản
Trong quá trình thử nghiệm phát hiện lỗi:
Lỗi phát sinh
Hệ thống gửi OTP trùng lặp 2 lần.
Hướng xử lý
IT cần kiểm tra lại:
Logic gửi OTP
Cấu hình hệ thống xác thực.

6. Giao diện hiển thị và trải nghiệm người dùng
Nhóm thảo luận các vấn đề về giao diện website.
Các vấn đề ghi nhận
Tên danh mục dài gây tràn chữ giao diện.
Hình ảnh hiển thị khác nhau giữa:
Điện thoại
Laptop
Layout sản phẩm chưa tối ưu.
Hướng cải tiến
Điều chỉnh giới hạn ký tự danh mục.
Chuẩn hóa kích thước hình ảnh.
Tối ưu hiển thị trên đa thiết bị.

7. Hiển thị hình ảnh sản phẩm
Phát hiện sự khác biệt giữa các thiết bị:

Click the image to view the sheet.
Đề xuất
Chuẩn hóa responsive layout.
Kiểm tra kích thước ảnh chuẩn cho toàn hệ thống.

III. CÁC VẤN ĐỀ CẦN TIẾP TỤC XỬ LÝ
Hoàn thiện tích hợp thanh toán hệ thống.
Rà soát quy trình hủy đơn hàng theo từng trạng thái.
Kiểm tra và sửa lỗi OTP gửi trùng.
Chuẩn hóa logic tồn kho và giới hạn đặt hàng.
Cải thiện giao diện hiển thị danh mục và sản phẩm.
Hoàn thiện liên kết tài khoản ngân hàng và lịch sử giao dịch.

IV. HÀNH ĐỘNG TIẾP THEO

Click the image to view the sheet.

V. KẾT LUẬN CUỘC HỌP
Cuộc họp đã rà soát các chức năng chính của hệ thống TMĐT DSS, đồng thời xác định một số vấn đề kỹ thuật và trải nghiệm người dùng cần tiếp tục cải thiện. Các bên thống nhất tiếp tục điều chỉnh hệ thống để đảm bảo nền tảng vận hành ổn định trước khi triển khai chính thức.