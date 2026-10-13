# 08 — Risk & Responsible AI

| Input | Process | Output → khâu sau |
|---|---|---|
| PRD ([03](03-prd.md)) | Liệt kê cách AI có thể gây hại, chấm mức độ, đặt biện pháp | Yêu cầu ngược lại cho **03 PRD** (non-goals, chuyển người) và **04** (mức tự chủ của AI) |

> Nguyên tắc: tách **sự kiện** và **nhận định**, hỏi ai chịu thiệt khi AI sai.

## 1. Ma trận rủi ro

| # | Rủi ro | Ai chịu thiệt | Khả năng | Mức độ | Biện pháp |
|---|---|---|---|---|---|
| R1 | AI **báo sai giá hoặc tồn kho** | Khách, uy tín shop | Trung bình | **Cao** | Chỉ trả lời từ dữ liệu Haravan đọc tại thời điểm hỏi; thiếu dữ liệu thì chuyển người; eval 300 hội thoại trước khi mở rộng, yêu cầu 0 lỗi sai giá |
| R2 | AI **tự chốt đơn sai** | Shop mất tiền | Thấp | **Cao** | AI chỉ tạo **đơn nháp**, chủ shop luôn xác nhận (non-goal trong PRD) |
| R3 | AI **trả lời khiếu nại** không phù hợp | Khách, uy tín shop | Trung bình | Trung bình | Phát hiện ý định khiếu nại/đổi trả → chuyển người ngay |
| R4 | **Lộ dữ liệu cá nhân** của khách (tên, SĐT, địa chỉ) | Khách | Thấp | **Cao** | Chỉ lưu khi có đơn nháp; xoá hội thoại sau 90 ngày; không dùng dữ liệu khách để huấn luyện model; tuân thủ quy định bảo vệ dữ liệu cá nhân của Việt Nam |
| R5 | **Khách không biết đang chat với AI** | Khách | Cao | Trung bình | Câu chào đầu ca: "Shop đang dùng trợ lý tự động, cần gặp người anh/chị nhắn 'gặp shop'" |
| R6 | **Prompt injection**: khách dụ AI giảm giá, tiết lộ thông tin shop | Shop | Trung bình | Trung bình | AI không có quyền đổi giá; chặn câu trả lời ngoài phạm vi; ghi log để chủ shop xem |
| R7 | **Phụ thuộc nhà cung cấp LLM** (giá tăng, model đổi) | Biên lợi nhuận | Trung bình | Trung bình | Theo dõi chi phí / job theo shop; luật 3 ở [07](07-gtm-growth.md); có phương án model thay thế |

## 2. Cần con người ở đâu

| Thời điểm | Ai | Làm gì |
|---|---|---|
| **Trước khi mở rộng** | PM + QA | Eval 300 hội thoại gán nhãn, kiểm tra lỗi sai giá / tồn kho |
| **Khi vận hành** | Chủ shop | Xác nhận mọi đơn; xử lý ca chuyển; đánh dấu câu trả lời sai |
| **Hằng tuần** | PM | Đọc mẫu 50 hội thoại ngẫu nhiên + toàn bộ ca bị đánh dấu sai |
