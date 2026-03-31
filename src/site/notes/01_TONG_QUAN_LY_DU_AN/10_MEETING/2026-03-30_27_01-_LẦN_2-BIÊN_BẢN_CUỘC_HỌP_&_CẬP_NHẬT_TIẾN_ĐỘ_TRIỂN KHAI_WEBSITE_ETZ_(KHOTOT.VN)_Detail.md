---
{"dg-publish":true,"permalink":"/01-tong-quan-ly-du-an/10-meeting/2026-03-30-27-01-lan-2-bien-ban-cuoc-hop-and-cap-nhat-tien-do-trien-khai-website-etz-khotot-vn-detail/","title":"CHI TIẾT GỐC BIÊN BẢN HỌP","dg-note-properties":{"title":"CHI TIẾT GỐC BIÊN BẢN HỌP"}}
---


# 📄 NỘI DUNG CHI TIẾT GỐC (LAYER 02)

> **File gốc (RAW):** [[02_KHO_DU_LIEU_THO_RAW/10_MEETING/27_01- LẦN 2-BIÊN BẢN CUỘC HỌP & CẬP NHẬT TIẾN ĐỘ TRIỂN KHAI WEBSITE ETZ (KHOTOT.VN).docx]]

27/01- LẦN 2-BIÊN BẢN CUỘC HỌP & CẬP NHẬT TIẾN ĐỘ TRIỂN KHAI WEBSITE ETZ (KHOTOT.VN)


I. THÔNG TIN CHUNG
Dự án: Website ETZ (khotot.vn)
Lần họp 1: 18/01/2026 – Họp Zoom (khởi động & rà soát tổng thể)
Lần họp 2 (cập nhật): 27/01/2026 – Họp Zoom (Follow - chốt yêu cầu & tiến độ)
Biên bản này:Bản cập nhật mới nhất sau họp ngày 27/01/2026
Thành phần:
Team IT (N3 Hoàng An)
Team ETZ (A. Được - Thu Châm)
Mục tiêu giai đoạn hiện tại:
Tổng hợp tiến độ sau họp 18/01
Cập nhật các yêu cầu mới – yêu cầu điều chỉnh – yêu cầu chốt tại ngày 27/01
Phân công – nhiệm vụ – hành động tiếp theo để hai bên triển khai thuận tiện

II. TỔNG QUAN TIẾN ĐỘ SAU 2 LẦN HỌP
Sau cuộc họp 18/01, hai bên đã thống nhất định hướng tổng thể cho các module:thanh toán – giỏ hàng đa kho – thông báo – lịch sử đơn – voucher – log dữ liệu.
Đến cuộc họp 27/01, nhiều hạng mục đã:
Được triển khai bước đầu
Phát sinh vấn đề thực tế khi test
Cần bổ sung rule, UX, log & ràng buộc vận hành
👉 Biên bản này ghi nhận:
Những phần đã làm
Những phần đang làm
Những phần cần làm tiếp & chốt rõ trách nhiệm

III. PHÂN CÔNG TỔNG QUAN (GIỮ NGUYÊN)

Click the image to view the sheet.

IV. NỘI DUNG CHI TIẾT THEO MODULE (CẬP NHẬT ĐẾN 27/01)

1. GIAO DIỆN MOBILE
Tiến độ hiện tại
Giao diện mobile đang cập nhật, dần hoàn thiện
Khi review thực tế, ETZ ghi nhận các mục đã được bổ sung và các mục thiếu:
Tag Khuyến mãi - Đã có ✅
Tag Liên hệ - Đã có ✅
Tag Bài viết - Đã có ✅
Phần trạng thái/lịch sử hủy đơn - cập nhật sau - chưa có ❌
Cập nhật 27/01
Các menu trên cần được bổ sung đầy đủ trên mobile trước khi mở SD.
Giao diện mobile cần đảm bảo: Dễ thao tác/Không ẩn các mục quan trọng so với desktop

IT: Hoàn tiếp tục hoàn thiện UI mobile, bổ sung menu còn thiếu
Admin ETZ: Review UX, phản hồi bố cục & thứ tự ưu tiênDeadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT

2. THÔNG BÁO HỆ THỐNG & ZALO OA
2.1. Thông báo trong web
Tiến độ
Hệ thống đã có thông báo cơ bản
Tuy nhiên, tại thời điểm 27/01:
Chưa gửi được theo từng user (SD, MD, admin). Phần này team IT sẽ review lại
Cập nhật 27/01 - Team IT 
Phân loại rõ các nhóm thông báo- cân nhắc:
Thông báo hệ thống
Thông báo tài khoản
Thông báo khuyến mãi
Thông báo vi phạm / khóa tài khoản
Bật xác thực bắt buộc trước khi mua hàng- (ví dụ như địa chỉ...) (Để không cần thao tác các bước sau khi mua hàng - giảm thao tác).
Bổ sung chức năng:
Khi khách hàng quên mật khẩu/lấy lại tài khoản → gửi OTP qua Zalo OA
OTP không hiển thị cho admin (Team IT báo ngoài phạm vi hợp đồng hiện tại - review lại).


IT: Xử lý logic gửi thông báo theo user, tích hợp OTP
Admin ETZ: Chuẩn bị nội dung mẫu (text) cho từng loại thông báo nếu IT cần gửi lạiDeadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT

2.2. Zalo OA (cập nhật tiến độ)/ Đơn hàng
Tiến độ
Đang trong giai đoạn tích hợp (theo kế hoạch 19–24/01).
Cập nhật bổ sung 27/01 - Team IT
Ở bước thêm sản phẩm vào giỏ hàng:
Bổ sung nút “Thêm địa chỉ” (dạng popup hoặc cân đối vị trí phù hợp để nhập địa chỉ).
    Hệ thống cần:
Tự gợi ý thông tin cũ
Giảm thao tác nhập lại cho user

Check lại đơn vị vận chuyển: nếu vận chuyển bằng chành xe hoặc tại cửa hàng (vì cập nhật thủ công) => admin vận hành
 Đơn hàng OA đổ về, để giá tiền còn số phẩy phía sau, check lại 

Xuất hóa đơn - Thông tin cần bổ sung
Thông tin xuất hóa đơn - Text - ETZ👉 Checkbox:
☐ Tôi có nhu cầu xuất hóa đơn
Khi tick vào thì hiện form hoặc ô để điền:
Tên công ty
Mã số thuế
Địa chỉ
Email nhận hóa đơn
Số điện thoại
Người liên hệ

IT: Hoàn thiện tích hợp Zalo OA & popup địa chỉ
Deadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT

3. VẬN CHUYỂN & TRẠNG THÁI ĐƠN HÀNG
Tiến độ
Đã có các trạng thái cơ bản.
Tuy nhiên, khi test thực tế phát sinh nhiều case cần cập nhật thủ công.
Cập nhật 27/01 
Với các đơn:Chành xe/Nhận tại cửa hàng → Admin ETZ vận hành cập nhật thủ công (cách vận hành admin cân nhắc lại)
Chuẩn hóa trạng thái - Team ITĐơn mới → Đang soạn hàng → Đã vận chuyển
Cần hiển thị timeline lịch sử đơn hàng chi tiết (thời gian – hành động – người thao tác).
Bổ sung: Phần đơn hàng - check, bổ sung lại lệnh cho phép duyệt hàng loạt "đang soạn hàng" trong 1 lần tích chọn 
Deadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT

4. GIÁ SẢN PHẨM – PHÂN LOẠI – DUYỆT SP
Tiến độ
Đã thống nhất logic:
Giá hiển thị = giá thấp nhất.
Rule giá đang để >0, chưa đủ an toàn.
Cập nhật 27/01
Nâng mức ràng buộc giá nhập sản phẩm (tránh rủi ro sau này) - Team ETZ gửi lại sau về mức giá ràng buộc
Voucher:- Giới hạn tối đa giảm 50%
      - Set thêm giới hạn số lần sử dụng voucher theo tài khoản - admin có quyền set
Duyệt sản phẩm của admin ETZ:
Bổ sung, cân nhắc phương án lưu lịch sử duyệt dưới dạng list - chi tiết càng lần bổ sung và chỉnh sửa .
Áp dụng cho Admin & MD
Deadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT

5. LỊCH SỬ ĐƠN HÀNG & HỦY ĐƠN
Tiến độ
Đã có chức năng mua lại đơn bị hủy
Thêm mục “Đơn đã hủy” - IT BỔ SUNG SAU - TRONG TUẦN TỚI
Cập nhật 27/01
Áp dụng tự động hủy đơn chưa thanh toán.Có thông báo / cảnh báo trước 24h (Tránh đơn treo gây ảnh hưởng tồn kho & vận hành
Thêm mục “Đơn đã hủy” - IT BỔ SUNG SAU - TRONG TUẦN TỚI
Bổ sung nội dung điều kiện hủy -Phần popup chưa thêm text bên cạnh cho khách xác nhận lại thông tin.Thông tin ở dưới: 
Popup xác nhận hủy đơn hàng
Trigger => Khi user bấm nút “Hủy đơn”=>Hiển thị popup gồm:Title "Xác nhận hủy đơn hàng"
 
Nội dung text hiển thị ở dưới hoặc là cố định ở phần đầu thanh toán luôn (e đề xuất nhờ các anh có kinh nghiệm cân nhắc góp ý thêm giúp em ạ)Text sử dụng - Team ETZ cập nhật
"Điều kiện hủy đơn hàng:
• Chỉ cho phép hủy khi đơn hàng chưa được xác nhận xử lý hoặc chưa bàn giao cho đơn vị vận chuyển.
• Đơn hàng đã giao hoặc đang vận chuyển không thể hủy."
Action
  Checkbox:
  Tôi đã đọc và hiểu điều kiện hủy đơn hàng
Button:
   Hủy đơn (disable nếu chưa tick checkbox)
   Quay lại


6. GIỎ HÀNG (ĐA KHO)
Tiến độ
Đã tách đơn theo kho khi thanh toán.
Cập nhật 27/1
Hiển thị rõ thông báo khi đơn có nhiều kho.
Text sử dụng - Team ETZ cập nhật
“Đơn hàng của bạn bao gồm sản phẩm từ nhiều kho khác nhau. Hệ thống sẽ tách đơn và thanh toán riêng theo từng kho để đảm bảo tiến độ giao hàng.”

Sau khi thanh toán 1 kho:
Hiển thị nút “Quay lại giỏ hàng để thanh toán đơn tiếp theo”.  Cho họ 1 lựa chọn tiếp tục thanh toán => hạn chế để họ thoát ra
Phần cài đặt chung - Phần hàng mới về để giới hạn thay từ 14 ngày thành 1 nămPhần cảnh báo đơn hàng chưa xử lý - Có popup trên web "đơn mới vừa đến" rồi. Cảnh báo" Đơn hàng cần xử lý" => set popup cảnh báo đơn hàng chưa xử lý hiển thị đến khi MD/ETZ xác nhận.

Deadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT

7. MÃ GIẢM GIÁ & VÍ VOUCHER
Tiến độ
Định hướng: có ví voucher riêng cho user.Cập nhật 27/01 - Bổ sung phần nào thay đổi dữ liệu là ghi lại hết - thêm phần ghi thêm lịch sử phần " mã giảm giá" - "khuyến mãi" - Team IT review lại
Deadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT




8. LOG – LỊCH SỬ – MINH CHỨNG (PHÁP LÝ)
Đề xuất cập nhật - bổ sung thêm
Ghi log toàn bộ thay đổi dữ liệu:
Giá
Voucher
Khuyến mãi
Trạng thái đơn
Mỗi tag nội dung/chỉ số cần thiết bổ sung có dấu (?) giải thích định nghĩa hoặc công thức.Deadline - Tuần sau demo lại (27/1-3/2) - Phụ trách fix - Team IT

PHẦN CÂN NHẮC CÁC BƯỚC TIẾP THEO - BỔ SUNG SAU NÀYCho phép lưu/đẩy các thông tin, ảnh để lưu trữ dữ liệu ví dụ như
Ảnh / video đóng gói
Minh chứng nhận hàng
Minh chứng hoàn tiềnGhi lại minh chứng dữ liệu đóng gói/hàng hóa, khi đã nhận hàng/sp đã nhận...để minh chứng ETZ giải quyết hoặc tranh chấp  (để nghiên cứu sau phần tính năng này)

VI. KẾT LUẬN
Biên bản này là bản cập nhật chính thức sau cuộc họp ngày 27/01/2026 bao gồm:
Tiến độ triển khai thực tế
Các yêu cầu mới phát sinh
Các điểm chốt cần hoàn thiện trước khi mở SD
VII. TIMELINE CHỐT
Tuần sau: Hoàn thiện
Họp tiếp theo: Dự tính 20h - Thứ 3 (3/2) - Tuần sau
