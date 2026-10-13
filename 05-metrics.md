# 05 — Metrics

| Input | Process | Output → khâu sau |
|---|---|---|
| Core action từ PRD ([03](03-prd.md)) | Định nghĩa "job xong", chọn North Star, đặt nhịp đo, viết tracking plan | Định nghĩa job xong → **06** tính giá theo job; các đèn → **07** dashboard |

> Nguyên tắc: tách **thao tác UI**, **output của AI** và **giá trị của người dùng**.

## 1. Định nghĩa "job xong"

Một **hội thoại xử lý xong** là hội thoại hỏi mua mà **khách nhận đủ thông tin hoặc có đơn nháp**, **không có người can thiệp** và **khách không hỏi lại trong 24 giờ**.

**Không đếm:** tin nhắn thử của shop, hội thoại chuyển người, đơn nháp bị huỷ.

> Vì sao quan trọng: đây là đơn vị **tính giá** ([06](06-pricing.md)). Định nghĩa lỏng thì doanh thu ảo và shop mất niềm tin.

## 2. North Star

**TTFV trung vị** (Time to First Value): số ngày từ lúc shop **kết nối xong** đến lúc **lần đầu đạt cả hai**: 50 hội thoại xử lý xong **và** 1 đơn nháp được xác nhận. **Mục tiêu ≤ 7 ngày.**

Lý do: pilot miễn phí 28 ngày. Shop không thấy giá trị sớm thì sẽ không trả tiền khi hết pilot.

## 3. Đèn báo

| Tầng | Chỉ số | Ngưỡng 🟢 / 🟡 / 🔴 | Báo trước cho |
|---|---|---|---|
| Sớm | TTFV ⭐ | ≤ 7 / 8–14 / > 14 ngày | Tỷ lệ chuyển sang trả tiền |
| Sớm | Containment | ≥ 70% / 55,3–69,9% / < 55,3% | Biên lợi nhuận |
| Sớm | Chi phí AI / job (p95 theo shop) | ≤ 1.355 / 1.356–1.560 / > 1.560 ₫ | Biên lợi nhuận |
| Vận hành | Pilot → trả tiền | ≥ 60% / 40–59% / < 40% | Thời gian hoàn vốn CAC |
| Vận hành | Hội thoại xử lý xong / shop / tháng | ≥ 1.050 / 400–1.049 / < 400 | Doanh thu mỗi shop |
| Vận hành | Giờ triển khai / shop | ≤ 3,1 / 3,2–6,2 / > 6,2 giờ | Năng lực phục vụ |
| Kết quả | Biên lợi nhuận gộp ròng | ≥ 60% / 53–59,9% / < 53% | |
| Kết quả | Thời gian hoàn vốn CAC | ≤ 3 / 3,1–5,9 / > 5,9 tháng | |

**Nhịp đo:** chủ shop dùng theo **ca tối hằng ngày**, nên các đèn sớm xem **hằng ngày/tuần**; đèn kết quả xem **hằng quý**.

## 4. Tracking plan

| Event | Bắn khi | Thuộc tính | Dùng cho |
|---|---|---|---|
| `shop_connected` | OAuth Haravan + webhook Fanpage nhận tin thật đầu tiên | shop_id, thời điểm | TTFV (mốc đầu) |
| `conversation_started` | Khách gửi tin đầu tiên trong khung giờ AI bật | shop_id, conversation_id | Mẫu số containment |
| `conversation_resolved` | Đủ điều kiện "job xong" (kiểm tra lại sau 24h) | shop_id, conversation_id, số lượt, chi phí token | Containment, chi phí / job, doanh thu |
| `handoff_to_human` | AI chuyển người | lý do chuyển | Containment, cải thiện AI |
| `draft_order_created` | AI tạo đơn nháp | shop_id, order_id, giá trị | TTFV |
| `draft_order_confirmed` | Chủ shop xác nhận | order_id | TTFV (mốc cuối) |
| `answer_flagged_wrong` | Chủ shop đánh dấu câu trả lời sai | loại lỗi | Độ chính xác |

**Quy tắc:** event chỉ bắn khi server **đã ghi nhận** hành vi hoàn tất; có **khoá chống trùng** khi retry. Mỗi chỉ số trên đều có event để tính, và mỗi event đều phục vụ ít nhất một chỉ số.
