# VietDraft Offline 1.2

VietDraft Offline là công cụ biên tập tiếng Việt chạy hoàn toàn trong trình duyệt. Công cụ không gọi API, không nạp thư viện ngoài và không gửi văn bản lên máy chủ.

## Khởi động

1. Giải nén gói ZIP.
2. Mở `index.html` bằng Chrome, Edge, Firefox hoặc Safari hiện đại.
3. Dán văn bản vào cột **Văn bản gốc**.
4. Chọn **Dọn định dạng an toàn** nếu chỉ muốn sửa lỗi kỹ thuật.
5. Muốn thay đổi rõ hơn, chọn mức **Sửa nhẹ / Sửa cân bằng / Sửa sâu**, rồi nhấn **Biên tập sâu**.
6. Mở thẻ **Nhật ký sửa** để biết chính xác từng nhóm thay đổi đã được áp dụng.
7. Chọn **Phân tích 30 tiêu chí**, đọc gợi ý và tự rà soát bản làm việc trước khi sao chép hoặc tải TXT.

Phím tắt: `Ctrl + Enter` để phân tích; `Ctrl + Shift + Enter` để biên tập sâu; `Ctrl + Shift + C` để sao chép bản làm việc.

## Đưa lên GitHub Pages

1. Tạo một repository mới.
2. Tải các tệp trong thư mục này lên nhánh mặc định, bảo đảm `index.html` nằm ở thư mục gốc.
3. Vào **Settings → Pages**.
4. Chọn triển khai từ nhánh mặc định và thư mục gốc.
5. Khi GitHub cung cấp địa chỉ trang, mở địa chỉ đó trên máy tính hoặc điện thoại.

Ứng dụng vẫn xử lý văn bản tại thiết bị kể cả khi được mở qua GitHub Pages. Vì không dùng tài nguyên ngoài, có thể lưu tệp `index.html` về máy để dùng khi mất mạng.

## Dữ liệu và quyền riêng tư

- Mặc định, nội dung chỉ tồn tại trong ô nhập của trang hiện tại.
- Tùy chọn **Lưu cục bộ** dùng `localStorage` của chính trình duyệt và chỉ lưu trên thiết bị đang dùng.
- Tắt tùy chọn **Lưu cục bộ** sẽ xóa bản lưu của ứng dụng trên thiết bị đó.
- Không có lệnh `fetch`, WebSocket, API AI, bộ theo dõi hoặc tài nguyên CDN trong `index.html`.

## Những gì công cụ tự sửa

Nút **Dọn định dạng an toàn** chỉ thực hiện các thay đổi cơ học:

- chuẩn hóa Unicode NFC;
- loại ký tự ẩn/điều khiển thường gây lỗi;
- chuẩn hóa xuống dòng và khoảng trắng;
- sửa khoảng cách phổ biến quanh dấu câu;
- rút gọn dấu câu bị lặp;
- xóa từ bị lặp liền nhau do lỗi gõ.

Các thay đổi về lập luận, giọng văn, mức độ khẳng định, trải nghiệm, số liệu và trích dẫn luôn do người viết quyết định.

## Ba mức biên tập

- **Sửa nhẹ:** bỏ lời dẫn thừa, mở đầu khuôn mẫu và một số sáo ngữ rõ ràng; không tự hạ mức khẳng định.
- **Sửa cân bằng:** thêm bước gọn động từ vòng, giảm liên từ bị lặp và tách câu dài tại ranh giới logic.
- **Sửa sâu:** thực hiện toàn bộ bước trên, đồng thời đổi nhịp câu mở đầu khi có cấu trúc phù hợp, giảm khẳng định tuyệt đối, thu hẹp khái quát thiếu bằng chứng, giảm so sánh nhất và chia đoạn quá dài.

Biên tập sâu không chèn ngẫu nhiên từ đồng nghĩa. Mỗi thay đổi thuộc một quy tắc xác định và được ghi lại trong thẻ **Nhật ký sửa**. Nội dung đặt trong dấu nháy, URL và đoạn mã được bảo vệ khỏi các phép sửa ngữ nghĩa.

Phiên bản 1.2 xử lý cấu trúc theo từng câu thay vì bỏ qua cả đoạn khi đoạn có trích dẫn, URL hoặc dấu nháy. Một khối văn bản dài sẽ được tổ chức lại thành nhiều đoạn khoảng 130 từ tại ranh giới câu an toàn. Các viết tắt, số thập phân, email, DOI và URL được che tạm khi xác định ranh giới câu để tránh tách nhầm.

Nhãn **Đã sửa sâu** chỉ xuất hiện khi đầu ra có thay đổi thực chất, chẳng hạn có nhiều phép sửa, có thay đổi cấu trúc đủ lớn hoặc một đoạn quá dài đã được chia lại. Nếu thuật toán chỉ sửa rất ít hoặc không tìm thấy cấu trúc phù hợp, trạng thái sẽ nói rõ để người dùng không hiểu nhầm.

Khi gặp số liệu hoặc lời kể trải nghiệm, công cụ chỉ tạo câu hỏi xác minh. Nó không tự thêm nguồn, cỡ mẫu, cuộc phỏng vấn, quan sát hoặc câu chuyện cá nhân.

## Giới hạn bắt buộc phải hiểu

- Điểm rõ ràng là điểm quy tắc nội bộ, không phải xác suất AI.
- Công cụ không xác định tác giả và không cam kết kết quả trên Turnitin hay bất kỳ bộ dò nào.
- Công cụ không kiểm chứng sự thật, kiến thức chuyên ngành hoặc bản quyền nguồn dẫn.
- Không thêm trải nghiệm, khảo sát, phỏng vấn, quan sát hoặc trích dẫn nếu chúng không thật sự tồn tại.
- Với văn bản quan trọng, luôn đọc lại toàn bộ bản cuối và tuân thủ quy định của cơ sở giáo dục.
