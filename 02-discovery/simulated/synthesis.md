> ⚠️ **Tổng hợp mô phỏng — không phải dữ liệu thật.** Kết luận dưới đây là **giả thuyết cần kiểm chứng** khi phỏng vấn thật, không phải bằng chứng.

# Tổng hợp mô phỏng

## 1. Bảng so sánh

| Nội dung | Shop 1 | Shop 2 | Shop 3 | Pattern |
|---|---|---|---|---|
| Tin nhắn / ngày, giờ cao điểm | 35–50; 20:00–23:00 | 20–30; livestream, khuyến mãi | 40–60; 19:00–22:00 | Dồn tin buổi tối hoặc đợt livestream |
| Mất đơn vì trả lời chậm | Khách im lặng, chưa chắc mất đơn | Chưa ghi nhận | Có một ca khách mua nơi khác | Khách có thể bỏ đi, nhưng chủ shop khó đo số đơn mất |
| Workaround và chi phí | Part-time ~3 triệu/tháng, câu trả lời mẫu | Người nhà, quick reply, ghim size | Nhân viên theo ca, gắn nhãn | Người trực + công cụ thủ công |
| Báo nhầm thông tin | Còn màu nhưng kho hết | Nhầm bảng size | Tồn kho chưa cập nhật | Báo nhầm xuất hiện ở cả 3 kịch bản |
| Việc giữ lại cho mình | Tồn kho, đổi trả, khiếu nại | Tư vấn size, đổi hàng | Lịch giao, khiếu nại | Việc rủi ro luôn được giữ lại |

## 2. Giả thuyết cần kiểm chứng khi phỏng vấn thật

| Giả thuyết | Kịch bản mô phỏng gợi ý | Cần kiểm chứng gì |
|---|---|---|
| A — mất đơn vì chậm | Yếu hơn dự kiến: chủ shop khó chỉ ra đơn mất cụ thể | Hỏi kỹ câu 6–8; xin đối chiếu số tin tồn sau 21h với đơn thực tế |
| B — trả lời sai | Có thể là nỗi đau mạnh nhất | Hỏi câu 13: tần suất báo nhầm, hậu quả cụ thể |
| C — không tin AI tự trả lời | Có thể đúng với ca rủi ro, không đúng với câu hỏi có sẵn dữ liệu | Hỏi câu 14–15: ranh giới giữa việc giao cho người khác và việc giữ lại |

## 3. Nếu phỏng vấn thật xác nhận mô phỏng thì sửa gì

| Khâu | Thay đổi |
|---|---|
| [01 Problem](../../01-problem.md) | Đổi trọng tâm từ "trả lời kịp" sang "**trả lời nhanh và đúng**" |
| [03 PRD](../../03-prd.md) | Dữ liệu tồn kho và bảng size theo mẫu là điều kiện bắt buộc; AI chỉ tự trả lời khi dữ liệu khớp, còn lại chuyển người |
| [04 Solution](../../04-solution-options.md) | Thêm phương án lai: AI tự trả lời câu có dữ liệu, gợi ý cho người duyệt với câu chưa chắc |
| [05 Metrics](../../05-metrics.md) | Thêm chỉ số **tỷ lệ trả lời sai** bên cạnh containment |
| [06 Pricing](../../06-pricing.md) | Kiểm tra mức sẵn lòng chi trả so với chi phí part-time hiện tại (~3 triệu/tháng trong kịch bản) |
