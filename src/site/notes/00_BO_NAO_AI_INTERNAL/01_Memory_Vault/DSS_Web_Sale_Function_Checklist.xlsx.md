---
{"dg-publish":true,"permalink":"/00-bo-nao-ai-internal/01-memory-vault/dss-web-sale-function-checklist-xlsx/","dg-note-properties":{}}
---


# RAW DATA: DSS_Web_Sale_Function_Checklist.xlsx

### Sheet: Sheet2
STT	Nhóm chức năng	Tên chức năng	Mô tả	Trạng thái	Ghi chú
	DSS				
1	Đăng nhập xác thực				
		Đăng nhập bằng số điện thoại (hoặc tài khoản email)			
		Phân quyền chức năng theo module, Theo kho			
2	Quản lý người dùng				
		Bộ lọc tìm kiếm theo tên			
		Xem/ thêm/ xóa/ sửa employee DSS (phân quyền)			
		Xem/ thêm/ xóa/ sửa MD			
		Xem/ thêm/ xóa/ sửa/ duyệt SD (On/off duyệt)			
		Danh sách riêng DSS, MD, SD: Tên, SDT, Địa chỉ, Ngày tạo, Đăng nhập cuối, số giao dịch, tỷ lệ thành công, tỷ lệ phẩn hồi			
		Bộ lọc: theo vai trò, trạng thái (hoạt động / chưa kích hoạt / đã khoá)			
		Ghi log thay đổi thông tin người dùng			
3	Quản lý danh mục				
		Bộ lọc tìm kiếm theo tên			
		Xem/ thêm/ xóa/ sửa danh mục theo 2 tầng. Vd: Tivi (Xiaomi, Samsung, ..)			
		List danh sách sản phẩm thuộc danh mục			
4	Quản lý sản phẩm 				
		Bộ lọc tìm kiếm sản phẩm theo tên/ sku/kho/Tỉnh thành/Đang bán / Tạm ẩn 			
		Xem/ thêm/ xóa/ sửa sản phẩm (thông tin mô tả, danh mục, hình ảnh, thuộc tính sản phẩm, phân loại sản phẩm, giá) DSS Không cho tạo trùng			
		Cho phép gắn nhãn sản phẩm (nổi bật, hàng mới lên X ngày)			
		Log thay đổi giá/khuyến mãi theo thời gian			
		Cập nhật nhanh Tên/giá/giá Km hàng loạt bằng excel được			
5	Quản lý sản phẩm MD Đăng ký bán và duyệt tạo mới				
		Bộ lọc tìm kiếm sản phẩm theo tên/ MD			
		Xem/ thêm/ duyệt/ sản phẩm phân phối cho SD			
		Mô tả rõ luồng duyệt bao gồm tạo mới và chỉnh sửa:
→ MD tạo sản phẩm → DSS nhận yêu cầu → Duyệt/từ chối + phản hồi			
		Duyệt nhiều sản phẩm cùng lúc			
6	Quản lý kho DSS				
		Bộ lọc tìm kiếm theo tên			
		Xem/ thêm/ xóa/ sửa Kho DSS			
		Cảnh báo tồn kho thấp với từng SKU			
		Cập nhật số lượng tồn kho theo từng sản phẩm theo từng kho			
		Tạo phiếu nhập kho/ xuất kho theo SKU (phân loại)			
		Cho phép import phiếu nhập hàng loạt bằng Excel			
		Lịch sử nhập/ xuất kho			
7	Quản lý đơn hàng DSS				
		Bộ lọc tìm kiếm theo tên/ sdt/ mã đơn/Thời gian/Chờ xử lý / Đang giao / Hoàn tất / Bị huỷ			
		Xem/ thêm đơn hàng mới			
		Sửa/ cập nhật trạng thái đơn hàng cũ			
		Xem lịch sử thao tác sửa đơn			
8	Quản lý đơn hàng MD				
		Xem/ kiểm duyệt đơn hàng MD (read-only)			
		Bộ lọc tìm kiếm theo tên/ sdt/ mã đơn/Thời gian/Chờ xử lý / Đang giao / Hoàn tất / Bị huỷ/ kho			
9	Quản lý ctkm				
		Xem/ thêm/ xóa/ sửa /Copy chương trình giảm giá (theo thời gian/Theo combo sản phẩm/ theo giá trị đơn hàng) kết hợp theo tùy chọn sản phẩm/ theo kho			
		KM theo thời gian			
		KM theo kho			
		KM theo giá trị đơn hàng (MD có thể thấy popup và đăng ký chạy theo)			
		KM theo combo sản phẩm DSS (MD có thể thấy popup và đăng ký chạy theo)			
		Hẹn lịch lên KM			
		Lưu lịch sử các chương trình đã chạy			
		Tự động ẩn khuyến mãi sau thời gian kết thúc			
10	Quản lý cài đặt				
		Phí ship theo từng phương thức vận chuyển			
		Các cấu hình khác (nếu có)			
		Tùy chọn xác thực đăng ký tài khoản OTP/SMS			
		Tùy chọn cần duyệt hay không cần duyệt SD			
		Cài trang Liên hệ của SD và MD			
		Cài sdt nhận thông báo có đơn hàng mới qua zalo (10 sdt)			
		Cài thời gian nổi bật hàng mới X ngày			
	 	Cài thời gian cảnh báo tới DSS và MD khi có đơn chưa xử lý			
		Cài Thời gian tự động huỷ đơn chưa thanh toán			
		Cài Quy tắc gợi ý sản phẩm liên quan (dựa theo cùng danh mục, cùng MD,bán nhiều, đang giảm giá, sp mới thêm…...)			
11	Thông báo & quảng cáo				
		Tạo và quản lý Banner quảng cáo Của DSS dành cho  MD/SD/All			
		Tạo và quản lý thông báo Của DSS dành cho  MD/SD/All			
		Xem Danh sách “đã đọc” để Admin biết MD có xem thông báo chưa			
12	Báo cáo				
		Tổng hợp sau			
		Lượng người online MD, SD			
	MD				
1	Đăng nhập xác thực				
		DSS tạo tài khoản và cấp cho MD			
		Đăng nhập bằng số điện thoại (hoặc tài khoản email)			
		Cập nhật thông tin cá nhân			
		Sau đăng nhập, được phân giao diện và chức năng riêng theo vai trò MD			
2	Quản lý sản phẩm				
		- Danh sách sản phẩm được DSS Cho phép bán, MD chọn thêm sản phẩm tương ứng vào kho của mình
- MD Tạo sản phẩm mới của MD và gửi yêu cầu DSS phê duyệt để được thêm vào kho			
		Xem/ thêm/ xóa/ sửa/ copy sản phẩm (thông tin mô tả, danh mục, hình ảnh, thuộc tính sản phẩm, phân loại sản phẩm, giá) Không cho tạo trùng tên sản phẩm			
		Bộ lọc tìm kiếm sản phẩm theo tên/ sku/Đang bán / Tạm ẩn / Chờ duyệt			
		- MD Có thể ẩn tạm thời sản phẩm khỏi danh mục hiển thị nếu không muốn tiếp tục bán (mà chưa xoá khỏi hệ thống)			
3	Quản lý kho				
		Vì có 1 kho nên tạo sẵn 1 kho cho MD			
		Cập nhật số lượng tồn kho			
		Tạo phiếu nhập kho/ xuất kho theo SKU (phân loại) có ghi chú			
		Import/export tồn kho bằng excel được			
		- Tra cứu lịch sử nhập, xuất, tồn theo ngày, tuần, tháng
- Có bộ lọc theo thời gian, tên sản phẩm, Đang bán / Tạm ẩn 			
		Hiển thị Thông tin Khuyên mãi của DSS, MD có muốn chạy theo thì đăng ký			
		Banner quảng cáo Của DSS dành cho  MD			
4	Quản lý đơn hàng MD				
	1. Nhận đơn hàng	- Khi SD đặt hàng thuộc phạm vi kho MD, hệ thống gửi thông báo qua Zalo tới MD
- Đơn hàng hiển thị trong bảng “Đơn hàng chờ xử lý”			
	2. Chuẩn bị hàng & giao hàng	- In phiếu giao hàng
- Chọn hình thức giao: Giao tại chỗ / Giao qua đối tác vận chuyển (GHTK, Viettel Post, API tự động)
- Cập nhật trạng thái: "xác nhận", "gọi vận chuyển", “Đang vận chuyển”, "Chờ khách qua lấy"….			
	3. Hoàn tất đơn hàng	- Sau khi hàng được giao và xác nhận (qua đơn vị vận chuyển), trạng thái chuyển “Đã giao”
- Ghi nhận đơn đã hoàn tất, cập nhật tồn kho trừ hàng thực tế			
		Bộ lọc tìm kiếm theo tên/ sdt/ mã đơn			
		Xem đơn hàng mới từ SD			
5	Thông báo & tương tác				
		- Pop-up cảnh báo đơn mới/ đơn chưa xử lý			
		Zalo và Web Thông báo			
		Lưu lịch sử thông báo đã gửi đến MD			
6	Báo cáo & Thống kê kho MD				
		Báo cáo doanh số theo tuần/tháng			
		Xem tổng đơn – tỷ lệ hoàn tất			
		- Xem nhanh số lượng còn lại của từng sản phẩm			
		- Xem sản phẩm nào được đặt nhiều từ SD theo sl và doanh thu			
7	Liên hệ				
		Hiển thị thông tin liên hệ DSS (1 bài viết tùy chỉnh đươc ở Admin)			
8	Cài đặt				
		Thay đổi địa chỉ lấy hàng			
		on/off nhận thông báo qua Zalo số đăng ký, mặc định On			
		on/off Thêm số dt nhận thông báo qua zalo (tối đa 2 số)			
		Chế độ hiển thị sáng/tối			
		Đổi pass			
	SD				
1	Đăng nhập xác thực				
		Đăng nhập bằng số điện thoại (hoặc tài khoản email)			
		Xác thực OTP SMS/ZALO			
		Đăng ký			
		Thêm thông tin địa chỉ 			
		Địa chỉ nhận hàng mặc định (ship tính trên địa chỉ này)			
		Cập nhật thông tin cá nhân, chứng chỉ hành nghề, CCCD			
		Tùy chọn kiểm duyệt có/không ở DSS			
		Trạng thái tài khoản: Đã duyệt / Chưa duyệt / Khoá			
2	Sản phẩm				
		Xem sản phẩm			
		Tìm kiếm sản phẩm kết hợp lọc theo danh mục, lọc theo giá, kho phân phối ,sản phẩm mới, giảm giá			
		Gợi ý sản phẩm liên quan: cùng danh mục, bán nhiều, đang giảm giá, sp mới thêm…			
	Thông tin sản phẩm hiển thị	- tên, ảnh, mô tả, giá bán, tồn kho khả dụng, khuyến mãi áp dụng			
		Lưu sản phẩm yêu thích để mua lại nhanh (wishlist)			
3	Mua hàng				
		Xem/ Thêm giỏ hàng			
		Cho phép ghi chú khi đặt hàng (ví dụ: cần gấp, gọi trước khi giao, v.v.)			
		Thanh toán (theo phương  thức)			
		Nhận thông báo OTP			
		Thanh toán qua nhiều phương thức (online, COD, tại cửa hàng)			
		Xác nhận đia chỉ giao hàng			
		 Gửi thông báo xác nhận thanh toán qua Zalo OA			
		Thanh toán tại cửa hàng → cần bổ sung quét mã QR tại quầy hoặc mã đơn để tra cứu nhanh			
	 Quản lý đơn hàng				
		Theo dõi trạng thái đơn hàng:
→ Đã xác nhận / Đang giao / Đã giao			
		Cho phép hủy đơn khi đang chờ xử lý, nhưng không cho hủy khi đã "xác nhận"			
		Xem chi tiết từng đơn: sản phẩm, số lượng, kho gửi, mã vận đơn			
		Ghi log đăng nhập và thao tác chính			
		Lọc & tra cứu lịch sử đơn hàng theo thời gian, trạng thái			
		Cho phép lặp lại đơn cũ (mua lại)			
	Cài đặt				
		Cập nhật họ tên, địa chỉ, địa chỉ nhận hàng, số điện thoại			
		Thay đổi mật khẩu 			
		Ghi log đăng nhập và thao tác chính			
		Có thể kiểm tra lịch sử đăng nhập			