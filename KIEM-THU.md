# Báo cáo kiểm thử VietDraft Offline 1.1

Ngày kiểm thử: 24-08-2026.

## Kết quả

Tất cả 48 phép kiểm thử tự động hiện tại đều đạt.

- Cấu trúc HTML5, khai báo tiếng Việt và viewport mobile hợp lệ.
- Có đúng hai vùng soạn thảo và đúng 30 thẻ phương pháp.
- Không có script ngoài, CSS ngoài, URL HTTP(S), `fetch` hoặc WebSocket trong `index.html`.
- Tất cả ID mà JavaScript tham chiếu đều tồn tại trong HTML.
- Mã JavaScript nội tuyến biên dịch thành công và toàn bộ trình khởi tạo chạy được trong DOM giả lập.
- Giữ nguyên dấu tiếng Việt sau chuẩn hóa.
- Loại được ký tự ẩn, khoảng trắng lỗi và cụm từ bị lặp liền nhau trong bài thử.
- Phát hiện đúng các mẫu thử về lặp từ, liên từ dày, số liệu thiếu nguồn cụ thể, tuyên bố trải nghiệm cần xác minh và dữ liệu riêng tư.
- Ba mức Sửa nhẹ, Sửa cân bằng và Sửa sâu tạo phạm vi thay đổi khác nhau đúng thiết kế.
- Với đúng đoạn văn mẫu trong giao diện, Sửa sâu tạo 13 nhóm thay đổi: bỏ mở đầu khuôn mẫu, đổi nhịp câu lặp chủ thể, giảm liên từ lặp, gọn động từ vòng, tách câu khảo sát tại “nhưng”, giảm khẳng định tuyệt đối và so sánh thiếu tiêu chí.
- Giữ nguyên chủ đề chính, số liệu 87%, nội dung trích dẫn và URL trong các bài thử.
- Không tự tạo lời kể “tôi/chúng tôi đã phỏng vấn” hoặc trải nghiệm không có trong đầu vào.
- Tách đúng hai câu trong trường hợp có viết tắt `TS.`.
- Điểm rõ ràng luôn nằm trong miền 0–100.
- Xử lý an toàn đầu vào rỗng.
- Bài thử phân tích 30.000 từ hoàn thành dưới 0,2 giây; biên tập sâu cùng dung lượng hoàn thành dưới 0,1 giây trên môi trường đóng gói. Thời gian thực tế phụ thuộc thiết bị và trình duyệt.
- Đã mô phỏng thao tác giao diện: nạp văn bản mẫu, chọn Sửa sâu, nhấn nút Biên tập sâu, nhận đầu ra khác và cập nhật nhật ký 19 lượt sửa.
- Biên tập sâu 30.000 từ không làm mất số lượng từ trong bài thử không chứa mẫu cần rút gọn.
- Số thẻ bố cục chính mở/đóng cân bằng: 74/74.

## Kiểm tra offline

Phân tích tĩnh xác nhận `index.html` không chứa:

- thẻ `script` có thuộc tính `src`;
- thẻ stylesheet ngoài;
- URL bắt đầu bằng `http://` hoặc `https://`;
- lệnh gọi `fetch`;
- lệnh gọi WebSocket.

Vì vậy, mọi CSS, JavaScript và biểu tượng cần thiết đều nằm trong chính `index.html`.

## Phạm vi chưa thể chứng minh bằng kiểm thử tự động

- Tính đúng của dữ kiện chuyên môn trong văn bản người dùng.
- Chất lượng tu từ theo từng môn học hoặc thể loại cụ thể.
- Danh tính tác giả hoặc việc một bộ dò bên thứ ba sẽ gắn nhãn thế nào.
- Khả năng tương thích với trình duyệt quá cũ không hỗ trợ biểu thức chính quy Unicode.

Khuyến nghị dùng Chrome, Edge, Firefox hoặc Safari phiên bản hiện đại và đọc lại toàn bộ văn bản cuối trước khi xuất bản.
