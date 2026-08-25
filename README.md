# Track 1 - Day 23 — Product Metrics Lab: Từ Core Action tới Tracking

## 1. Thông tin cá nhân & Bài nộp

- **Họ và tên:** Trần Tuấn Anh
- **Mã sinh viên (MHV):** 2A202601086
- **Lớp / Track:** Track 1 - Day 23 — Product Metrics Lab
- **Dự án chọn làm:** **P-103** — Nền tảng AI hỗ trợ sinh viên trong quá trình tìm kiếm & chuẩn bị cho kỳ thực tập (*CV - Internship Matching*)

---

## 2. Đường dẫn tệp Metrics Pack (Tệp trình bày trực quan chính)

Tệp Metrics Pack chính thức được trình bày chi tiết và trực quan dưới dạng HTML giao diện cao cấp tại:

👉 **LINK tệp Metrics Pack:** [`product-metrics-lab.html`](./product-metrics-lab.html)

*(Tệp bao gồm đầy đủ 8 phần từ `00 — Phạm vi` đến `07 — Tự soi lỗi & Revision` cùng bảng tổng hợp AI Support Log).*

---

## 3. Cấu trúc Repository

```text
K4-Track1-DAY23-2A202601086-TranTuanAnh/
├── README.md                 # Thông tin cá nhân, MHV, dự án, Link Metrics Pack & Thu hoạch
├── product-metrics-lab.html  # Tệp Metrics Pack trình bày chi tiết (00 - 07)
└── ai-support-log.md         # Nhật ký hỗ trợ AI và đánh giá chi tiết quá trình đồng hành cùng AI
```

---

## 4. Điều tôi mang về áp dụng cho dự án thật (Key Takeaways)

1. **Phân biệt triệt để giữa Core Action và System Output:**
   - Trong dự án P-103, hệ thống tự động tạo ra gợi ý (`match_result_generated`) chỉ là *Output của AI*.
   - **Value thực sự** chỉ xuất hiện khi sinh viên dành thời gian xem, đọc giải thích và đánh giá kết quả matching (`match_result_reviewed`). Tránh bẫy ngộ nhận metric "AI đã chạy" thành "người dùng đã nhận giá trị".

2. **Nối Cadence từ Natural Intent thay vì ép chu kỳ cố định (Nature vs. Nurture):**
   - Không mặc định ép người dùng sử dụng ứng dụng hàng ngày (Daily Habit) khi sản phẩm thuộc dạng *Event-driven* (tìm kiếm thực tập theo đợt/mùa).
   - Định nghĩa Retention theo **Custom Search-Cycle Window (30 ngày)** giúp đo lường chính xác tỷ lệ quay lại khi có nhu cầu thật, tránh dán nhãn "user rời bỏ" sai lệch.

3. **North Star Metric (NSM) phải gắn với Quality Threshold:**
   - NSM không chỉ là con số đếm lượt click hời hợt mà phải đo **Qualified Match Reviews** (sinh viên đọc phần giải thích điểm mạnh/khoảng thiếu hụt và ghi nhận quyết định shortlisted/dismiss).
   - Luôn đi kèm **Counter-Metric** (`Negative Match Feedback Rate`) để bảo vệ chất lượng AI, ngăn ngừa việc tối ưu số lượng match nhưng tạo ra nhiều match rác.

4. **Thiết kế Product Loop gắn kết trực tiếp với Telemetry & Acceptance Criteria:**
   - Mọi giả thuyết vòng lặp (Metric Hypothesis) phải đo lường được thông qua North Star Metric.
   - Khi thiết kế bảng Tracking, tuân thủ nghiêm ngặt **Acceptance Criteria**: Không bắn event sớm khi hành vi chưa hoàn thành và loại bỏ hoàn toàn trùng lặp do reload/retry.