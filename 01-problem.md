# 01 — Problem

| Input | Process | Output → khâu sau |
|---|---|---|
| Quan sát về shop thời trang online, giả thuyết ban đầu | Hỏi "vì sao vấn đề tồn tại", tách người trả tiền và người dùng, chọn cách đo | Problem statement + chỉ số thành công → **02 Discovery** dùng để kiểm chứng |

## 1. Vì sao vấn đề này tồn tại (First Principles)

- Shop thời trang nhỏ bán chủ yếu qua **Fanpage + Messenger**. Khách không đặt hàng qua giỏ hàng mà **hỏi trước** (giá, size, còn hàng, ship) rồi mới chốt.
- Câu hỏi lặp lại rất nhiều nhưng **câu trả lời nằm sẵn trong dữ liệu** (catalog, tồn kho, bảng phí ship trên Haravan).
- Khung **21h–23h30** là lúc khách rảnh để mua, cũng là lúc chủ shop vừa đóng gói đơn trong ngày vừa trực inbox. **[Giả thuyết]**
- Trả lời chậm → khách hỏi shop khác → **mất đơn**. Thuê người trực ca tối thì tốn lương cố định cho khung giờ ngắn.

> Bản chất: không phải "shop cần chatbot", mà là **khoảng trống giữa lúc khách muốn mua và lúc shop đủ người trả lời**.

## 2. Ai là ai

| Vai | Là ai | Được gì |
|---|---|---|
| **Người trả tiền + người dùng** | Chủ shop thời trang (hộ kinh doanh, doanh nghiệp nhỏ) dùng Haravan | Không mất đơn ca tối, không phải thuê người trực |
| Người tương tác | Khách mua hàng, chat với Fanpage dưới tên shop | Được trả lời nhanh và đúng |
| Kênh | Haravan (kho ứng dụng) | Không trả tiền, chỉ phân phối |

→ Đây là **B2B SMB**, không phải B2C hay B2B2C. Toàn bộ chỉ số đo theo **shop**.

## 3. Problem statement

> **Chủ shop thời trang bán qua Fanpage** mất đơn trong **ca tối** vì **không trả lời kịp** các câu hỏi lặp lại về giá, size, tồn kho và phí ship trong lúc đang bận đóng gói, trong khi thuê người trực ca tối thì tốn chi phí cố định cho khung giờ ngắn.

## 4. Đo thành công bằng gì

| Câu hỏi | Chỉ số |
|---|---|
| Shop có thấy giá trị không? | **TTFV** (số ngày đến lúc có 50 hội thoại AI xử lý xong + 1 đơn nháp được xác nhận) |
| AI có làm được việc không? | **Containment**: tỷ lệ hội thoại AI tự xử lý xong, không cần người |
| Kinh doanh có sống được không? | Biên lợi nhuận gộp ≥ 60%, tỷ lệ pilot chuyển sang trả tiền ≥ 60% |

Chi tiết ở [05-metrics.md](05-metrics.md).

## 5. AI Readiness — có nên dùng AI không?

| Câu hỏi | Trả lời |
|---|---|
| Có dữ liệu để AI trả lời đúng không? | Có: catalog, size, tồn kho, phí ship trên Haravan qua API |
| Câu trả lời có đúng-sai rõ ràng không? | Có với giá/size/tồn kho/ship. **Không** với tư vấn phối đồ, khiếu nại → chuyển người |
| Sai thì hậu quả thế nào? | Báo sai giá hoặc tồn kho → mất uy tín, tranh chấp. Giảm bằng cách AI **chỉ đọc dữ liệu Haravan** và **chỉ tạo đơn nháp** |
| Làm không cần AI được không? | Chatbot kịch bản cứng làm được câu hỏi đơn giản nhưng gãy khi khách hỏi tự nhiên ("áo này mặc 55kg vừa không?"). LLM có lợi thế rõ ở phần hiểu câu hỏi |

→ **Đủ điều kiện dùng AI cho phần hỏi đáp có dữ liệu; giữ con người ở bước xác nhận đơn và các ca khó.**
