# VietDraft Offline 2.0 – Bộ diễn đạt V3

VietDraft Offline là công cụ biên tập tiếng Việt chạy hoàn toàn trong trình duyệt. Công cụ không gọi API, không tải thư viện ngoài và không gửi văn bản lên máy chủ.

## Cách dùng nhanh

1. Giải nén ZIP và mở `index.html`.
2. Dán văn bản vào cột **Văn bản gốc**.
3. Chọn chế độ, người đọc, phạm vi và bật **Khóa dữ kiện**.
4. Nếu có tên mô hình, thang đo hoặc thuật ngữ buộc giữ, nhập vào ô **Thuật ngữ phải giữ**, cách nhau bằng dấu chấm phẩy.
5. Nhấn **Xử lý văn bản**.
6. Đọc **Nhật ký sửa**, **Gợi ý** và **So sánh** trước khi sao chép hoặc tải TXT.

Phím tắt: `Ctrl + Enter` để kiểm tra; `Ctrl + Shift + Enter` để xử lý; `Ctrl + Shift + C` để sao chép bản làm việc.

## Các chế độ

- **Mức A – Chỉnh câu:** sửa lời dẫn thừa, câu vòng, lỗi gõ, nhịp và một số cách diễn đạt khó đọc; giữ gần trật tự ý.
- **Mức A+ – Cân bằng:** thêm bước gọn động từ, giảm liên từ lặp và tách câu dài tại ranh giới logic.
- **Mức B – Viết lại sâu:** đổi cấu trúc phù hợp, làm rõ một số cách chỉ trỏ khi chủ thể nằm ngay trước đó và tổ chức lại đoạn quá dài.
- **Mức C – Kiểm toán:** không sửa văn bản; chỉ chạy hệ thống phân tích và nêu phần cần người viết kiểm tra.

## Chọn người đọc

Ứng dụng hỗ trợ các cấu hình chung, học sinh, phụ huynh, giáo viên, quản lý, học thuật, hành chính và truyền thông. Cấu hình này điều chỉnh ngưỡng tách câu và độ dài đoạn; không tự thêm vai trò, trách nhiệm, ví dụ hoặc kiến thức.

## Chỉ sửa vùng được chọn

1. Chọn **Phạm vi – Vùng bôi chọn**.
2. Bôi đúng đoạn cần sửa trong ô **Văn bản gốc**.
3. Nhấn **Xử lý văn bản**.

Phần trước và sau vùng chọn được ghép lại nguyên từng ký tự. Nếu chưa bôi chọn, ứng dụng sẽ dừng và yêu cầu chọn vùng.

## Cổng bảo toàn

Khi bật **Khóa dữ kiện**, ứng dụng đối chiếu đầu vào và đầu ra đối với:

- số liệu, phần trăm, ngày tháng và biểu thức có dấu so sánh;
- trích dẫn có tác giả/năm;
- tên riêng nhiều thành tố;
- URL, DOI và email;
- nội dung trong dấu nháy;
- thuật ngữ do người dùng nhập.

Nếu một mục bất biến bị mất hoặc đổi, cổng bảo toàn chặn đầu ra và trả lại phần gốc. Đây là kiểm tra ký tự, không phải kiểm chứng tính đúng của dữ kiện.

## Bộ quy tắc V3

- Quét đúng 100 cụm diễn đạt theo khuôn.
- Quét riêng đúng 35 cách chỉ trỏ mơ hồ.
- Không quét nội dung trong trích dẫn nguyên văn, URL, email hoặc đoạn mã.
- Có thể gộp “Nghiên cứu này…”, “Quan điểm này…” hoặc “Điều này giúp…” với câu ngay trước khi chủ thể đã rõ.
- Khi thiếu chủ thể, công cụ không đoán và đưa cảnh báo **Cần làm rõ chủ thể**.
- Giữ mức thận trọng của các câu như “gợi ý rằng”, “có liên hệ với”; không tự biến liên hệ thành nguyên nhân – kết quả.
- Không tự hạ hoặc nâng mức khẳng định. Các từ tuyệt đối, so sánh nhất hoặc kết luận rộng chỉ được đánh dấu để người viết tự quyết định.

## Phân tích toàn diện

Ngoài 100 + 35 bộ lọc V3, ứng dụng giữ 30 tiêu chí về Unicode, dấu câu, câu/đoạn, nhịp, lặp từ, liên từ, nguồn, viết tắt, danh sách, trải nghiệm cần xác minh và dữ liệu riêng tư. Điểm rõ ràng là điểm quy tắc nội bộ, không phải xác suất AI.

## Dữ liệu và quyền riêng tư

- Mặc định, nội dung chỉ tồn tại trong trang đang mở.
- **Lưu cục bộ** dùng `localStorage` trên chính thiết bị; tùy chọn chế độ, người đọc, phạm vi và thuật ngữ cũng được lưu cùng văn bản.
- Không có `fetch`, WebSocket, API AI, bộ theo dõi hoặc CDN trong `index.html`.

## Đưa lên GitHub Pages

1. Tải các tệp bên trong thư mục này lên gốc repository, bảo đảm `index.html` nằm ở thư mục gốc.
2. Vào **Settings → Pages** và chọn triển khai từ nhánh mặc định.
3. Sau khi thay bản cũ, dùng `Ctrl + F5` để xóa bộ nhớ đệm của trình duyệt.

## Giới hạn cần hiểu

- Thuật toán offline không hiểu ngữ nghĩa như một biên tập viên hoặc mô hình ngôn ngữ; các mẫu không đủ chắc chắn chỉ được cảnh báo.
- Công cụ không kiểm chứng sự thật, kiến thức chuyên ngành, bản quyền hoặc sự tồn tại của nguồn.
- Không tự tạo trải nghiệm, khảo sát, số liệu, trích dẫn hoặc ví dụ.
- Công cụ không xác định tác giả và không cam kết thay đổi kết quả của Turnitin hay bất kỳ bộ dò AI nào.
- Luôn đọc lại bản cuối và tuân thủ quy định của cơ sở giáo dục hoặc nơi xuất bản.
