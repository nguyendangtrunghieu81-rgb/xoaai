# Báo cáo kiểm thử VietDraft Offline 2.1

Ngày kiểm thử: 24-08-2026.

## Kết quả

Tất cả 92 phép kiểm thử tự động của bản 2.1 đều đạt.

### Cấu trúc và offline

- HTML5, tiếng Việt, viewport, hai vùng soạn thảo và cân bằng thẻ bố cục hợp lệ.
- Có đúng 30 tiêu chí phân tích, 100 cụm khuôn V3 và 35 cách chỉ trỏ mơ hồ.
- Không có script/CSS ngoài, URL tải tài nguyên, `fetch` hoặc WebSocket.
- Mọi ID JavaScript tham chiếu đều tồn tại; toàn bộ mã giao diện khởi tạo được trong DOM giả lập.
- Nhập TXT/MD, lưu cục bộ, hoàn tác, sao chép, tải TXT và xuất JSON của bản trước được giữ nguyên.

### Bảo toàn nội dung

- Cổng nghĩa đối chiếu toàn bộ chuỗi từ đầu vào và đầu ra, không chỉ số liệu hoặc trích dẫn.
- Phát hiện đúng trường hợp “được hình thành nhờ” bị đổi thành “hình thành từ”.
- Cho phép đổi ranh giới dấu câu khi toàn bộ từ vẫn còn nguyên và đúng thứ tự.
- Giữ `n = 30`, `r = 0,42`, `p = 0,03`, tác giả/năm, câu trong dấu nháy và URL.
- Cổng bảo toàn phát hiện đúng khi `p = 0,03` bị đổi thành `p = 0,05`.
- Cổng bảo toàn phát hiện thay đổi bên trong trích dẫn nguyên văn và trả lại phần gốc.
- Nút Dọn định dạng cũng phải đi qua cổng bảo toàn, không được bỏ qua lớp khóa.
- Thuật ngữ do người dùng khai báo được khóa riêng.
- Giữ mức thận trọng “gợi ý rằng”, “có liên hệ với”; không tự tạo quan hệ nhân quả.
- Không tự hạ hoặc nâng các cụm khẳng định, phạm vi và so sánh nhất trong đầu vào.
- Chỉ sửa vùng bôi chọn; phần trước và sau vùng chọn giữ nguyên từng ký tự trong bài thử.

### Bộ diễn đạt V3

- Phát hiện các cụm khuôn V3 và loại nội dung trích dẫn nguyên văn khỏi phép quét.
- PT-41: giữ nguyên câu “Nghiên cứu này…” để không tự gộp và thay quan hệ nghĩa.
- PT-42: giữ nguyên Nguyễn Văn A (2024) cùng lời quy chiếu “Quan điểm này…”.
- PT-43: không tự đặt lại chủ thể của “Điều này giúp…”.
- PT-44: không đoán “Kết quả này…” khi câu đứng riêng; tạo cảnh báo `Cần làm rõ chủ thể`.
- Phát hiện hai giá trị 80 người và 120 người cần đối chiếu; không tự chọn hay tính trung bình.
- Các cụm “tại thời điểm hiện tại”, “tiến hành kiểm tra”, “đưa ra sự hỗ trợ”, “một số lượng lớn” được đánh dấu nhưng không tự thay bằng từ gần nghĩa.
- Ngưỡng tách câu thay đổi theo người đọc: học sinh ưu tiên câu ngắn hơn học thuật.

### Ba chế độ và giao diện

- Mức A dọn kỹ thuật; Mức A+ và B dùng ngưỡng tách câu/đoạn khác nhau nhưng đều giữ nguyên chuỗi từ.
- Mức C giữ nguyên văn bản và chuyển sang phần gợi ý kiểm toán.
- Trạng thái chỉ báo Mức B khi có thay đổi thực chất.
- Văn bản ngắn không có mẫu cần sửa không bị báo thành công giả.
- Cổng khóa nghĩa hiển thị số từ và số mục bất biến đã kiểm tra hoặc số sai lệch bị chặn.
- Bộ đếm hiển thị thêm số cụm khuôn V3 và số cách chỉ trỏ mơ hồ.

### Văn bản dài

- Bài học thuật thử nghiệm 844 từ được dồn thành 1 đoạn; đầu ra vẫn đúng 844 từ và được chia thành 6 đoạn.
- Ghi nhận 5 ranh giới đoạn được bổ sung; không thêm, xóa hoặc thay một từ nào.
- Giữ nguyên các cụm “huy động tổng hợp”, “được hình thành, phát triển”, “không chỉ… mà còn…” và câu “Năng lực chính vì vậy…”.
- Kiểm thử hồi quy xác nhận không còn lỗi “lượng kiến thức lượng kiến thức”.
- Giữ nguyên `(Bộ Giáo dục và Đào tạo, 2018a)`, `Trần Thị Kim Cúc (2021)`, URL, số thập phân và câu trong ngoặc kép.
- Phân tích 30.000 từ hoàn thành khoảng 0,27 giây; xử lý sâu khoảng 0,12 giây trong lần kiểm thử nguồn gần nhất.

## Phạm vi kiểm thử

Bộ kiểm thử tự động xác nhận hành vi quy tắc và bảo toàn ký tự. Nó không thể chứng minh tính đúng chuyên môn, sự tồn tại của nguồn, bản quyền, danh tính tác giả hoặc kết quả của một bộ dò bên thứ ba. Văn bản cuối vẫn cần người viết đọc và kiểm tra.
