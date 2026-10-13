# 07 — GTM & Growth

| Input | Process | Output → khâu sau |
|---|---|---|
| Giá + điểm gãy ([06](06-pricing.md)), đèn báo ([05](05-metrics.md)) | Chọn 1 kênh, dựng dashboard vận hành, viết luật quyết định trước khi có số | Luật và cổng 90 ngày → **10** ghi quyết định khi chạy thật |

> **Số mô hình**, chưa phải số thực tế. Ngày trong kế hoạch là **[Giả định]** cho kịch bản pilot.

## 1. Kênh

**Partner-led qua kho ứng dụng Haravan.** Chỉ chọn **một** kênh để đo được rõ.

| Vì sao | Rủi ro |
|---|---|
| Shop đã dùng Haravan, cài app không cần gặp sales | Haravan chưa đồng ý listing; tỷ lệ chia doanh thu chưa biết |
| Ngân sách CAC theo mô hình là $1.284/shop, thấp hơn **19,6×** so với benchmark ICONIQ ($25.200) → không đủ tiền cho sales trực tiếp | Nếu Haravan từ chối: thử KiotViet, không mở nhiều kênh cùng lúc |

## 2. Năm luật quyết định (viết trước khi có số)

| # | Nếu | Thì | Không được làm |
|---|---|---|---|
| 1 ⏹ | TTFV > 14 ngày ở 2/3 shop onboard gần nhất | Dừng nhận shop mới, ngồi với 2 shop đó trong 48h, rút onboarding còn 1 luồng (giá/size/còn hàng) | Gia hạn pilot miễn phí để "kéo dài thêm" |
| 2 ⏹ | Containment < 55,3% trong 2 tuần liên tiếp, có ≥ 300 hội thoại/tuần từ ≥ 3 shop | Đóng băng tính năng mới 1 sprint, gán nhãn 100 ca thất bại, sửa 2 nguyên nhân lớn nhất | Nâng lên Sonnet 5.5 (GM 46,6%), nới định nghĩa "xử lý xong" |
| 3 | Chi phí AI / job p95 > 1.560 ₫ trong 1 tháng, shop đó có ≥ 300 job | Giới hạn 8 lượt / hội thoại, bỏ ảnh khỏi lịch sử sau lượt 2 | Tăng giá cho tất cả shop |
| 4 ⏹ | Pilot → trả tiền < 40% trên đợt ≥ 5 shop | Dừng pilot miễn phí, phỏng vấn mọi shop không trả trong 7 ngày; đợt sau pilot có phí, hoàn tiền nếu containment < 55,3% | Giảm giá |
| 5 | Giờ triển khai > 6,2 giờ / shop ở 3 shop liên tiếp | Viết script đồng bộ catalog + checklist onboarding, chỉ nhận shop có catalog đủ size / tồn kho | Thuê thêm người onboarding để chạy chỉ tiêu |

## 3. Cổng 90 ngày

| Mốc | Phải đạt | Bằng chứng | Nếu trượt |
|---|---|---|---|
| Ngày 30 | Containment đo thật ≥ 55,3% trên ≥ 300 hội thoại gán nhãn từ ≥ 3 shop | File eval + báo cáo tuần 4 | 44,2–55,2% có nguyên nhân rõ → **SỬA** (1 lần); < 44,2% → **ĐỔI** phân khúc |
| Ngày 60 | ≥ 3/5 shop pilot trả hoá đơn đầu | Hoá đơn + sao kê | 2/5 → **SỬA**: pilot có phí; ≤ 1/5 → **ĐỔI** value metric |
| Ngày 90 | Lãi gộp tháng ≥ chi phí vận hành tháng (burn) | P&L tháng | Đạt ½ burn → **SỬA** kênh; dưới ½ → **DỪNG** |

**Điều kiện dừng hẳn:** sau đúng một lần SỬA mà lãi gộp vẫn < ½ burn hoặc containment thật vẫn < 55,3% → dừng CaTối, giữ phần runway còn lại cho hướng khác.

## 4. Chưa đo được

Cả 8 đèn **chưa có số thật**. Cần pilot + log webhook. Chi phí theo shop cần gắn mã shop vào mọi lời gọi API. Phần chia doanh thu của Haravan chưa biết. Runway là **[Giả định]**.
