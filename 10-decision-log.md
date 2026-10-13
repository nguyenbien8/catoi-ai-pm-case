# 10 — Decision Log

Mỗi quyết định ghi kèm **hệ quả đầu cuối**: ảnh hưởng tới sản phẩm, giá, thị trường và tiến độ.

| # | Ngày | Quyết định | Vì sao | Sản phẩm | Giá | Thị trường | Tiến độ |
|---|---|---|---|---|---|---|---|
| D1 | 10/2026 | Chỉ làm **ca tối**, không làm 24/7 | Giả thuyết: khoảng trống lớn nhất nằm ở ca tối | Phạm vi nhỏ, dễ đo | Shop trả theo job nên không ảnh hưởng | Thông điệp rõ: "trực ca tối thay bạn" | Nhanh hơn |
| D2 | 10/2026 | AI **chỉ tạo đơn nháp**, chủ shop xác nhận | Giảm rủi ro R2, giữ niềm tin | Thêm màn hình duyệt đơn | Giá trị thấp hơn tự chốt một chút | Dễ thuyết phục shop thử | Thêm 1 tính năng ở sprint 2 |
| D3 | 10/2026 | Tính giá theo **hội thoại xử lý xong** + phí tối thiểu | Gắn tiền với giá trị thật | Phải định nghĩa và đo "job xong" thật chặt | GM 68,4% (mô hình) | Shop chỉ trả khi AI làm được việc | Phải làm tracking ngay sprint 2 |
| D4 | 10/2026 | **Không** nâng lên model lớn hơn để cứu containment | GM tụt còn 46,6% | Phải sửa nguyên nhân thất bại bằng dữ liệu / prompt | Giữ GM ≥ 60% | | Có thể chậm hơn nếu containment thấp |
| D5 | 10/2026 | Chỉ một kênh: **Haravan** | Đo được rõ, CAC thấp | Phải tích hợp sâu Haravan API | Phụ thuộc tỷ lệ chia doanh thu | Thị trường giới hạn trong shop dùng Haravan | Phụ thuộc thời gian Haravan duyệt |
| D6 | _chờ_ | Chọn phương án A / B / C | Theo kết quả test ở [04](04-solution-options.md) | | | | |

## Cách dùng

- Thêm dòng mới khi có quyết định ảnh hưởng **từ hai khâu trở lên**.
- Khi một quyết định bị đảo ngược, **không xoá**, thêm dòng mới ghi "đảo ngược D_x vì…".
