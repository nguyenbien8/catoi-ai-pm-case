# 02 — Discovery

| Input | Process | Output → khâu sau |
|---|---|---|
| Problem statement ([01](../01-problem.md)) | Viết giả thuyết + evidence map → phỏng vấn 3–5 chủ shop → tổng hợp | Pain đã kiểm chứng hoặc bị bác bỏ → **03 PRD** chỉ đưa vào MVP những gì có bằng chứng |

> **Trạng thái:** 🔧 Đã có giả thuyết và bộ câu hỏi. **Chưa phỏng vấn.** Kết quả sẽ ghi vào `interviews/` và [synthesis.md](synthesis.md).

## 1. Giả thuyết

**JTBD:** *"Khi khách nhắn hỏi hàng vào buổi tối mà tôi đang bận đóng gói, tôi muốn khách được trả lời đúng ngay, để không mất đơn mà không phải thuê thêm người."*

| # | Giả thuyết | Vì sao điều tra |
|---|---|---|
| **A (chính)** | Ca tối, chủ shop **không trả lời kịp** tin nhắn hỏi hàng, dẫn đến **mất đơn** | Nếu sai, cả sản phẩm không có lý do tồn tại |
| B (cạnh tranh) | Vấn đề thật không phải tốc độ mà là **trả lời sai** (báo nhầm còn hàng, nhầm giá) khi có nhiều người trực | Nếu B mạnh hơn A, sản phẩm nên tập trung vào độ chính xác thay vì trực 24/7 |
| C (rủi ro) | Chủ shop **không tin** để AI trả lời khách thay mình | Nếu đúng, chỉ có thể làm AI gợi ý câu trả lời, không tự gửi |

## 2. Evidence map

| Cần kiểm tra | Làm A mạnh hơn | Làm A yếu đi |
|---|---|---|
| Tình huống có thật | Kể được tối cụ thể gần đây inbox dồn | Tối thường vắng tin |
| Có hậu quả | Kể được đơn bị mất, khách "seen" rồi đi | Khách chờ được, sáng trả lời vẫn chốt |
| Có workaround | Thuê người, nhờ người nhà, tin nhắn tự động, câu trả lời mẫu | Không làm gì vì không cần |
| Có chi phí | Có số tiền lương hoặc số giờ bỏ ra | Không tốn gì đáng kể |
| Lặp lại | Xảy ra nhiều tối mỗi tuần | Chỉ dịp sale |

## 3. Tài liệu

- [recruiting.md](recruiting.md): tìm người, tin nhắn mời, bảng theo dõi
- [interview-guide.md](interview-guide.md): tiêu chí chọn người và bộ câu hỏi
- [interview-notes-template.md](interview-notes-template.md): mẫu ghi chép mỗi buổi
- [synthesis.md](synthesis.md): tổng hợp sau khi có ít nhất 3 buổi
