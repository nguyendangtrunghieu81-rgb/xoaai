# Cơ sở nghiên cứu và phạm vi thiết kế

## Kết luận chính

Không có tập hợp dấu hiệu bề mặt nào có thể chứng minh chắc chắn một văn bản là “do AI” hoặc “do người”. Cùng một đặc điểm như câu đều, từ vựng ít biến thiên, cấu trúc chặt hoặc giọng văn thận trọng có thể xuất hiện trong văn bản mẫu, văn bản hành chính, văn bản của người học ngôn ngữ và văn bản do mô hình sinh ra.

Vì vậy, VietDraft Offline không tạo điểm “AI/người” và không tối ưu văn bản để né một bộ dò cụ thể. Ứng dụng dùng các đặc điểm ngôn ngữ đó theo mục đích hợp lệ hơn: hỗ trợ người viết đọc lại độ rõ, mạch ý, tính cụ thể, nguồn dẫn và lỗi trình bày.

## Những điểm đã đối chiếu

1. Tài liệu Turnitin thừa nhận có thể xảy ra dương tính giả và âm tính giả; kết quả AI không nên là căn cứ duy nhất cho hành động bất lợi với người học.
2. Turnitin không hiển thị tỷ lệ cụ thể trong vùng 1–19% vì vùng điểm thấp có nguy cơ bị diễn giải sai và có tỷ lệ dương tính giả cao hơn.
3. Theo yêu cầu tệp được Turnitin công bố tại thời điểm biên soạn, báo cáo AI hỗ trợ tiếng Anh, tiếng Tây Ban Nha và tiếng Nhật; tiếng Việt không nằm trong danh sách ngôn ngữ hỗ trợ chính thức của báo cáo đó.
4. Nghiên cứu của Liang và cộng sự cho thấy nhiều bộ dò GPT có xu hướng gắn nhãn sai văn bản tiếng Anh của người không phải bản ngữ. Điều này cho thấy đặc điểm “đều” hoặc “đơn giản” không thể được xem là bằng chứng tác giả.
5. Nghiên cứu của Krishna và cộng sự cho thấy diễn đạt lại làm suy yếu nhiều bộ dò. Kết quả này phản ánh giới hạn kỹ thuật của phương pháp phát hiện, không tạo cơ sở để cam kết “bẻ gãy tuyệt đối” hay xác nhận một văn bản là nguyên bản của con người.

## Nguồn chính

- Turnitin Guides, **Using the AI Writing Report**: https://guides.turnitin.com/hc/en-us/articles/22774058814093-Using-the-AI-Writing-Report
- Turnitin Guides, **File requirements for an AI Writing Report**: https://guides.turnitin.com/hc/en-us/articles/28234943089933-File-requirements-for-an-AI-Writing-Report
- Turnitin Guides, **Release notes archive**: https://guides.turnitin.com/hc/en-us/articles/33092161932045-Release-notes-archive
- Liang et al. (2023), **GPT detectors are biased against non-native English writers**, *Patterns*: https://doi.org/10.1016/j.patter.2023.100779
- Krishna et al. (2023), **Paraphrasing evades detectors of AI-generated text, but retrieval is an effective defense**, *NeurIPS 2023*: https://openreview.net/forum?id=WbFhFvjjKj

## Ba nguyên tắc thiết kế

### 1. Chẩn đoán minh bạch

Mọi cảnh báo đều gắn với một quy tắc có thể hiểu được: số từ trong câu, mật độ cụm từ, dấu câu, độ lệch chuẩn độ dài câu, số đoạn hoặc mẫu biểu thức chính quy. Không có mô hình bí mật hoặc điểm tác giả.

### 2. Bảo toàn quyền quyết định của người viết

Ứng dụng tự sửa rất ít: chỉ lỗi kỹ thuật có rủi ro thấp. Những thay đổi có thể tác động đến nghĩa được trình bày dưới dạng gợi ý để người viết tự quyết định.

### 3. Không tạo bằng chứng giả

Ứng dụng cảnh báo khi gặp các câu kiểu “chúng tôi đã khảo sát/phỏng vấn/quan sát” và yêu cầu xác minh. Nó không chèn câu chuyện, trải nghiệm, số liệu hoặc nguồn dẫn giả nhằm làm văn bản có vẻ tự nhiên hơn.

## Cách chuyển các gợi ý trong tài liệu tham chiếu thành chức năng an toàn

Các ảnh tham chiếu và bộ quy tắc diễn đạt V3 đề cập việc thay đổi nhịp câu, sửa câu mở/kết, đổi chủ thể, làm rõ cách chỉ trỏ và thêm trải nghiệm cụ thể. Thử nghiệm ở phiên bản 2.0 cho thấy thay từ dựa trên mẫu có thể làm lệch sắc thái hoặc quan hệ nghĩa dù số liệu và trích dẫn vẫn còn nguyên. Phiên bản 2.1 vì vậy dùng nguyên tắc chặt hơn:

- không tự thay từ đồng nghĩa, không xóa lời dẫn và không đổi động từ chỉ dựa trên biểu thức chính quy;
- đối chiếu toàn bộ chuỗi từ trước và sau xử lý; một từ bị mất, thêm, thay hoặc đảo vị trí đều khiến đầu ra bị chặn;
- tách câu dài ở ranh giới “nhưng/tuy nhiên/vì vậy/đồng thời…” khi hai vế đều đủ ý, đồng thời giữ nguyên chính từ nối gốc;
- chia đoạn quá dài tại ranh giới câu mà không thêm hoặc xóa từ;
- giữ nguyên mức khẳng định, phạm vi, quan hệ đối chiếu, quan hệ nguyên nhân và sắc thái thận trọng;
- bảo vệ thêm số liệu, công thức, tên riêng, trích dẫn, URL, email, đoạn mã và thuật ngữ do người dùng khai báo ở cấp ký tự;
- quét độc lập 100 cụm diễn đạt theo khuôn và 35 cách chỉ trỏ mơ hồ nhưng chỉ đưa cảnh báo;
- không tự gộp “Nghiên cứu này”, “Quan điểm này” hoặc “Điều này giúp”, vì việc đặt lại chủ thể có thể thay đổi quy chiếu;
- giữ nguyên toàn bộ phần ngoài vùng bôi chọn khi người dùng chọn xử lý một phần;
- đưa số liệu và trải nghiệm vào danh sách cần người viết xác minh, không tự tạo nội dung thay thế.

Các phép sửa này nhằm cải thiện độ rõ và tính tự nhiên của văn bản. Chúng không được dùng để xác nhận tác giả hoặc cam kết thay đổi kết quả của một bộ dò bên thứ ba.

## 30 lớp phân tích được cài đặt

1. Unicode và ký tự ẩn.
2. Khoảng trắng.
3. Khoảng cách dấu câu.
4. Dấu câu lặp.
5. Cặp ngoặc và dấu nháy.
6. Lặp từ liền nhau.
7. Câu quá dài.
8. Câu rất ngắn.
9. Nhịp độ dài câu.
10. Mở đầu câu lặp.
11. Từ nội dung lặp dày.
12. Cụm ba từ lặp.
13. Liên từ quá dày.
14. Tín hiệu chuyển ý quá ít.
15. Sáo ngữ/cụm chung chung.
16. Khẳng định tuyệt đối.
17. Tuyên bố so sánh nhất.
18. Cụm động từ vòng hoặc yếu.
19. Tham chiếu mơ hồ.
20. Mật độ cấu trúc bị động.
21. Đoạn quá dài.
22. Nhiều đoạn một câu liên tiếp.
23. Độ dài đoạn quá đồng đều.
24. Mở đầu đoạn lặp.
25. Số liệu có thể thiếu nguồn/ngữ cảnh.
26. Trích dẫn có thể thiếu quy chiếu.
27. Viết tắt chưa diễn giải.
28. Dấu câu trong danh sách chưa nhất quán.
29. Tuyên bố trải nghiệm/nghiên cứu cần xác minh.
30. Email hoặc số điện thoại có nguy cơ lộ thông tin riêng tư.

## Giới hạn của thuật toán offline

- Tách câu tiếng Việt dựa trên dấu câu và danh sách viết tắt thông dụng nên vẫn có thể nhầm trong văn bản pháp lý, công thức, thơ hoặc dữ liệu bảng.
- Đa dạng từ vựng là tỷ lệ kiểu từ trên tổng số từ; chỉ số này giảm tự nhiên khi văn bản dài lên.
- Phát hiện nguồn dẫn chỉ dựa trên tín hiệu bề mặt, không xác nhận nguồn có tồn tại hay trích dẫn có chính xác.
- Cảnh báo không đồng nghĩa với lỗi. Một cấu trúc lặp, câu bị động hoặc đoạn dài có thể hoàn toàn phù hợp với mục đích tu từ và thể loại.
