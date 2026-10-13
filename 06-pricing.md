# 06 — Pricing & Unit Economics

| Input | Process | Output → khâu sau |
|---|---|---|
| Định nghĩa "job xong" ([05](05-metrics.md)) | Tính chi phí mỗi job, đặt giá sàn, chọn value metric, stress test | Giá + điểm gãy → **07** đặt ngưỡng đèn và luật quyết định |

> **Số mô hình**, chưa phải số thực tế. Giá API kiểm tra ngày 08/10/2026, tỷ giá 26.190 ₫/USD.

## 1. Năm con số

| Chỉ số | Giá trị | Ghi chú |
|---|---|---|
| Chi phí / job | **1.232 ₫** ($0,047) | Chia cho job **hoàn thành** (1.050), không phải tổng hội thoại (1.500) |
| Giá sàn (3× chi phí) | 3.696 ₫ | |
| **Giá bán** | **3.900 ₫ / hội thoại xử lý xong** | 3,17× chi phí |
| Biên lợi nhuận gộp | **68,4%** | Chưa trừ phần chia cho Haravan |
| Containment hoà vốn (GM 60%) | **55,3%** | So với mức ước tính 70%, **chưa có eval** |

## 2. Value metric

**Hybrid:** phí tối thiểu **1.560.000 ₫/tháng** (đã gồm 400 hội thoại xử lý xong) + **3.900 ₫** cho mỗi hội thoại từ thứ 401.

| Vì sao chọn | Vì sao không chọn cách khác |
|---|---|
| Shop chỉ trả khi **AI làm xong việc**, gắn tiền với giá trị thật | **Theo tin nhắn:** shop trả cả khi AI trả lời sai hoặc phải chuyển người |
| Phí tối thiểu đảm bảo doanh thu nền và lọc shop quá nhỏ | **Gói cố định:** shop ít tin nhắn thấy đắt, shop nhiều tin nhắn làm lỗ |

## 3. Mô hình gãy khi nào (stress test)

| Biến | Ngưỡng gãy | Ví dụ |
|---|---|---|
| Containment | **< 44%** | AI xử lý được ít hội thoại hơn, chi phí dồn lên job hoàn thành |
| Chi phí LLM / job | **tăng ≥ 1,8×** | Phải nâng từ Haiku 4.5 lên Sonnet 5.5 để đủ chất lượng → GM còn **46,6%** |

→ Vì vậy [07](07-gtm-growth.md) có luật: **không** nâng model lên Sonnet để cứu containment. Phải sửa nguyên nhân hội thoại thất bại trước.

## 4. Hệ quả đầu cuối

- **Containment** vừa là chỉ số sản phẩm, vừa quyết định biên lợi nhuận. Đội AI và đội kinh doanh phải nhìn cùng một con số.
- Nếu Haravan lấy **20% doanh thu**, containment hoà vốn tăng từ 55,3% lên **69,1%**, gần sát mức ước tính 70%. Câu trả lời của Haravan là **rủi ro lớn nhất** của mô hình giá.
