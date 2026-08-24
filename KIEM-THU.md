# Báo cáo kiểm thử VietDraft Offline 1.2

Ngày kiểm thử: 24-08-2026.

## Kết quả

Tất cả 60 phép kiểm thử tự động hiện tại đều đạt.

- Cấu trúc HTML5, khai báo tiếng Việt, viewport mobile và 30 tiêu chí phân tích đều hợp lệ.
- Không có script ngoài, CSS ngoài, URL tải tài nguyên, `fetch` hoặc WebSocket trong `index.html`.
- Mọi ID mà JavaScript tham chiếu đều tồn tại; toàn bộ mã giao diện khởi tạo được trong DOM giả lập.
- Ba mức Sửa nhẹ, Sửa cân bằng và Sửa sâu tạo phạm vi thay đổi khác nhau đúng thiết kế.
- Bộ tách câu giữ đúng viết tắt `TS.`, URL có dấu chấm, email và số thập phân `3.14`.
- Nội dung trong dấu nháy, URL, tác giả và năm trích dẫn được giữ nguyên trong các bài thử.
- Không tự tạo lời kể “tôi/chúng tôi đã phỏng vấn” hoặc dữ kiện trải nghiệm không có trong đầu vào.
- Với bài học thuật thử nghiệm 844 từ được cố ý dồn thành 1 đoạn, Sửa sâu tạo đầu ra 862 từ và 6 đoạn, ghi nhận 35 phép sửa có giải thích.
- Bài học thuật thử nghiệm có trích dẫn `(Bộ Giáo dục và Đào tạo, 2018a)`, `Trần Thị Kim Cúc (2021)`, URL, số thập phân và câu trong ngoặc kép; tất cả các phần này còn nguyên sau khi tổ chức lại đoạn.
- Cấu trúc dài “không chỉ… mà còn…” và một số cụm học thuật vòng được đổi sang câu có trọng tâm rõ hơn mà không thêm luận điểm mới.
- Một câu ngắn vốn không có mẫu cần sửa vẫn giữ nguyên, và giao diện không báo sai “Đã sửa sâu”.
- Đã mô phỏng thao tác giao diện với cả văn bản mẫu và bài học thuật dài: nút Sửa sâu tạo đầu ra, nhật ký sửa cập nhật, bộ đếm báo đúng 6 đoạn.
- Phân tích 30.000 từ hoàn thành trong khoảng 0,15 giây; biên tập sâu cùng dung lượng trong khoảng 0,10 giây trên môi trường đóng gói. Thời gian thực tế phụ thuộc thiết bị và trình duyệt.
- Biên tập văn bản dài không làm mất lượng nội dung trong bài thử.
- Số thẻ bố cục chính mở/đóng cân bằng: 74/74.

## Lỗi hồi quy đã khóa

Phiên bản trước có thể bỏ qua cả một đoạn nếu trong đoạn xuất hiện dấu nháy, URL hoặc ký hiệu mã. Bài thử hồi quy mới đặt tất cả các yếu tố này trong cùng một khối học thuật dài. Kết quả phải đồng thời thỏa mãn:

1. khối dài vẫn được chia thành nhiều đoạn;
2. phần được bảo vệ giữ nguyên;
3. các câu không được bảo vệ vẫn được biên tập;
4. số từ đầu ra nằm trong khoảng an toàn so với đầu vào;
5. trạng thái giao diện phản ánh đúng mức thay đổi thực tế.

## Kiểm tra offline

Phân tích tĩnh xác nhận `index.html` không chứa:

- thẻ `script` có thuộc tính `src`;
- thẻ stylesheet ngoài;
- URL tải tài nguyên bắt đầu bằng `http://` hoặc `https://`;
- lệnh gọi `fetch`;
- lệnh gọi WebSocket.

Mọi CSS, JavaScript và biểu tượng cần thiết đều nằm trong chính `index.html`.

## Phạm vi chưa thể chứng minh bằng kiểm thử tự động

- Tính đúng của dữ kiện chuyên môn trong văn bản người dùng.
- Chất lượng tu từ theo từng môn học hoặc thể loại cụ thể.
- Danh tính tác giả hoặc việc một bộ dò bên thứ ba sẽ gắn nhãn thế nào.
- Khả năng tương thích với trình duyệt quá cũ không hỗ trợ biểu thức chính quy Unicode.

Khuyến nghị dùng Chrome, Edge, Firefox hoặc Safari phiên bản hiện đại và đọc lại toàn bộ văn bản cuối trước khi xuất bản.
