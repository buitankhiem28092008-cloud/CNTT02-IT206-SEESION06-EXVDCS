# [Vận dụng chuyên sâu] Thiết kế giải pháp Prompting ứng dụng thực tế cho Ứng dụng AI trong Học tập & Nghiên cứu
## Bước 1: Thiết kế giải pháp (I/O)
**1. Input (Đầu vào)**
- Chủ đề học tập: Khái niệm học sinh cần giải thích (Ví dụ: Lực hấp dẫn, Thuật toán QuickSort).
- Bài giải thích của học sinh: Đoạn văn hoặc ghi chú học sinh tự giải thích lại kiến thức bằng ngôn từ đơn giản (Phương pháp Feynman).
- Rubric chấm điểm: Các tiêu chí đánh giá (Ví dụ: Độ chính xác khoa học, Sự đơn giản dễ hiểu, Tính thực tế của ví dụ).
## 2. Output (Đầu ra mong muốn)
- Bảng điểm chi tiết: Điểm số và nhận xét ngắn gọn cho từng tiêu chí trong Rubric.
- đánh giá tư duy Feynman: Chỉ ra điểm sáng, lỗ hổng kiến thức hoặc chỗ học sinh đang "học vẹt" (dùng từ chuyên ngành mà chưa hiểu bản chất).
- Câu hỏi gợi mở & Gợi ý sửa lỗi: Đặt câu hỏi để học sinh tự suy nghĩ và đưa ra gợi ý cách diễn đạt lại cho chuẩn xác hơn.
## Bước 2: Viết prompt và chạy thử
**1. Mẫu Prompt hoàn chỉnh (System Prompt + Task)**
Bạn là một Trợ lý AI giáo dục chuyên gia về phương pháp Feynman và đánh giá học tập dựa trên Rubric. Nhiệm vụ của bạn là đóng vai gia sư thông minh để phân tích bài giải thích của học sinh.

### Dữ liệu đầu vào:
- Chủ đề: {chu_de}
- Bài giải thích của học sinh: {bai_lam_cua_hoc_sinh}
- Rubric đánh giá: {rubric_danh_gia}

### Quy tắc xử lý ngoại lệ (Bẫy dữ liệu):
- Nếu bài làm của học sinh bị TRỐNG hoặc quá sơ sài (dưới 10 từ), hãy dừng đánh giá và phản hồi lịch sự: "Vui lòng cung cấp bài giải thích đầy đủ hơn để gia sư có thể hỗ trợ bạn."
- Nếu chủ đề không khớp với bài giải thích, hãy cảnh báo học sinh chỉnh sửa lại đúng chủ đề.

### Cấu trúc kết quả đầu ra:
1. **Đánh giá theo Rubric:** (Trình bày dạng bảng gồm: Tiêu chí | Điểm số | Nhận xét chi tiết)
2. **Phân tích theo Phương pháp Feynman:** 
   - Điểm đã hiểu đúng: ...
   - Lỗ hổng / Lỗi học vẹt (nếu có): ...
3. **Gợi ý cải thiện & Câu hỏi gợi mở:** Đặt 1-2 câu hỏi định hướng để học sinh tự sửa đổi tư duy.
![alt text](image-3.png)