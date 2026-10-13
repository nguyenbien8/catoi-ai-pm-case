# 03 — PRD: CaTối MVP

| Input | Process | Output → khâu sau |
|---|---|---|
| Pain đã kiểm chứng ([02](02-discovery/)) | Chọn phạm vi nhỏ nhất tạo được giá trị, viết user stories + tiêu chí nghiệm thu, ghi rõ không làm gì | MVP scope → **04** thiết kế phương án, **05** định nghĩa core action, **09** lập kế hoạch |

> **Bản nháp v0.1.** Viết trước discovery để biết cần kiểm chứng gì. Sẽ sửa theo [synthesis](02-discovery/synthesis.md).

## 1. Mục tiêu

| | |
|---|---|
| **Mục tiêu người dùng** | Chủ shop không mất đơn ca tối mà không phải thuê người trực |
| **Mục tiêu kinh doanh** | ≥ 60% shop pilot chuyển sang trả tiền, biên lợi nhuận gộp ≥ 60% |
| **Đo bằng** | TTFV ≤ 7 ngày, containment ≥ 70% (xem [05](05-metrics.md)) |

## 2. Phạm vi MVP

| Làm | Không làm (non-goals) và lý do |
|---|---|
| Trả lời **giá, size, còn hàng, phí ship** từ dữ liệu Haravan | **Tư vấn phối đồ, khiếu nại, đổi trả**: không có đáp án đúng-sai rõ, sai thì hậu quả lớn → chuyển người |
| Tạo **đơn nháp** trong Haravan | **Tự chốt đơn / thu tiền**: chủ shop phải xác nhận, để giữ quyền kiểm soát |
| Bật/tắt theo **khung giờ** (mặc định 21h–23h30) | **Trực 24/7**: chưa có bằng chứng ban ngày là vấn đề |
| **Chuyển người** khi AI không chắc hoặc khách yêu cầu | **Kênh ngoài Messenger** (Zalo, TikTok Shop): làm sau khi Messenger chứng minh được |
| Báo cáo cuối ca: số hội thoại xử lý xong, đơn nháp chờ duyệt | **Dashboard phân tích nâng cao** |

## 3. User stories và tiêu chí nghiệm thu

| ID | User story | Tiêu chí nghiệm thu |
|---|---|---|
| US-01 | Là chủ shop, tôi muốn **kết nối Haravan và Fanpage trong vài phút**, để bắt đầu mà không cần kỹ thuật | Kết nối xong trong ≤ 15 phút; catalog đồng bộ tự động; báo lỗi rõ nếu sản phẩm thiếu size hoặc tồn kho |
| US-02 | Là chủ shop, tôi muốn AI **trả lời đúng giá, size, tồn kho, phí ship**, để khách không phải chờ | Câu trả lời chỉ lấy từ dữ liệu Haravan tại thời điểm hỏi; không có dữ liệu thì **không đoán**, chuyển người |
| US-03 | Là chủ shop, tôi muốn AI **tạo đơn nháp** khi khách chốt, để sáng ra tôi chỉ việc duyệt | Đơn nháp có đủ sản phẩm, size, số lượng, địa chỉ, số điện thoại; chủ shop xác nhận hoặc huỷ bằng 1 thao tác |
| US-04 | Là chủ shop, tôi muốn **AI chuyển cho tôi** các ca khó, để không làm mất lòng khách | Chuyển khi: khiếu nại, đổi trả, khách yêu cầu gặp người, AI hỏi lại 2 lần vẫn không hiểu; khách nhận được câu báo "shop sẽ trả lời sớm" |
| US-05 | Là chủ shop, tôi muốn **bật/tắt AI theo giờ**, để chỉ dùng khi bận | Đặt được khung giờ; tắt ngay lập tức khi bấm |
| US-06 | Là chủ shop, tôi muốn **xem lại AI đã trả lời gì**, để tin và sửa khi cần | Xem được toàn bộ hội thoại AI xử lý; đánh dấu câu trả lời sai; báo cáo cuối ca |

## 4. Bảng chia việc giữa người và AI

| Việc | AI | Chủ shop |
|---|---|---|
| Hiểu câu hỏi của khách | ✅ | |
| Tra giá, size, tồn kho, phí ship | ✅ (chỉ đọc Haravan) | |
| Trả lời câu hỏi có dữ liệu | ✅ | Xem lại sau ca |
| Tư vấn, khiếu nại, đổi trả | ❌ Chuyển người | ✅ |
| Tạo đơn nháp | ✅ | |
| **Xác nhận đơn** | ❌ | ✅ **Luôn luôn** |

## 5. Yêu cầu phi chức năng

| Yêu cầu | Ngưỡng |
|---|---|
| Thời gian trả lời | ≤ 10 giây cho 95% tin nhắn |
| Độ chính xác giá / tồn kho | 0 lỗi báo sai giá trên bộ eval 300 hội thoại trước khi mở rộng |
| Chi phí AI | ≤ 1.560 ₫ / hội thoại xử lý xong (p95 theo shop), xem [06](06-pricing.md) |
| Dữ liệu cá nhân | Chỉ lưu tên, SĐT, địa chỉ khi có đơn nháp; xoá hội thoại sau 90 ngày, xem [08](08-risk.md) |

## 6. Câu hỏi mở

- Chủ shop có chấp nhận để AI **tự gửi** câu trả lời không, hay chỉ muốn AI **gợi ý**? → giả thuyết C, chờ discovery
- Haravan có cho listing app và tỷ lệ chia doanh thu bao nhiêu? → ảnh hưởng [06](06-pricing.md), [07](07-gtm-growth.md)
