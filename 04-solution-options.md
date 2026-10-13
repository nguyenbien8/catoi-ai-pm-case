# 04 — Solution Options & Test Plan

| Input | Process | Output → khâu sau |
|---|---|---|
| PRD ([03](03-prd.md)), giả thuyết C về niềm tin | Thiết kế 3 phương án khác nhau ở **mức tự chủ của AI**, test với chủ shop thật | Phương án được chọn → **05** chốt core action, **06** tính lại giá nếu giá trị thay đổi |

> Nguyên tắc: giữ cùng một tình huống cho cả 3 phương án, chỉ thay cơ chế, để so sánh công bằng.

## 1. Giữ nguyên cho cả 3 phương án

| Thành phần | Quyết định |
|---|---|
| Người dùng | Chủ shop thời trang, 21h30, đang đóng gói đơn |
| Tình huống | 6 tin nhắn đến trong 10 phút: 3 hỏi size, 2 hỏi còn hàng, 1 muốn đổi hàng |
| Kết quả mong muốn | Khách được trả lời đúng, không mất đơn, chủ shop không bị gián đoạn quá nhiều |

## 2. Ba phương án

| | **A — AI gợi ý, người gửi** | **B — AI tự trả lời, người duyệt đơn** | **C — AI tự trả lời và tự chốt đơn** |
|---|---|---|---|
| Cơ chế | AI soạn sẵn câu trả lời, chủ shop bấm gửi | AI gửi câu trả lời có dữ liệu, tạo đơn nháp; ca khó chuyển người | AI gửi trả lời và xác nhận đơn luôn |
| Chủ shop làm gì | Đọc và gửi từng tin | Duyệt đơn nháp sau ca, xử lý ca chuyển | Gần như không làm gì |
| Ưu điểm | Kiểm soát hoàn toàn, rủi ro thấp | Đỡ gián đoạn, vẫn giữ quyền với đơn | Tiết kiệm thời gian nhất |
| Nhược điểm | Vẫn bị gián đoạn, giá trị thấp | Phải tin AI trả lời đúng | Sai một đơn là mất tiền và uy tín |
| Dự đoán | Dễ được chấp nhận nhưng ít người trả tiền | **Phương án dự kiến chọn** | Bị loại nếu chủ shop không tin |

## 3. Kế hoạch test

| Mục | Nội dung |
|---|---|
| Người test | 3 chủ shop (lấy từ danh sách phỏng vấn), mỗi người thử cả 3 phương án, **xoay thứ tự** |
| Prototype | Màn hình giả lập inbox với 6 tin nhắn cố định, câu trả lời AI soạn sẵn |
| Quan sát | Thao tác đầu tiên, chỗ do dự, có đọc lại câu trả lời AI không, thời gian xử lý hết 6 tin |
| Hỏi sau test | Phương án nào chọn dùng thật? Phương án nào **không bao giờ** dùng? Vì sao? |
| Quyết định | Chọn phương án có **≥ 2/3** người chọn dùng thật; nếu không có, giữ A và quay lại discovery |

## 4. Kết quả

> 🔧 Chưa test. Ghi theo 4 lớp: **Đã thấy** → **Diễn giải** → **Thay đổi tiếp theo** → **Vẫn chưa chứng minh**.
