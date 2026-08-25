# AI Support Log — Track 1 - Day 23 (Product Metrics Lab)

**Học viên:** Trần Tuấn Anh  
**Mã sinh viên:** 2A202601086  
**Dự án chọn làm:** P-103 — Nền tảng AI hỗ trợ sinh viên trong quá trình tìm kiếm & chuẩn bị cho kỳ thực tập (CV - Internship Matching)

---

## 1. Nhật ký hỗ trợ theo Phase (AI Support Log Matrix)

| Phase | AI được sử dụng để | Quyết định của người học (Trần Tuấn Anh - 2A202601086) |
| :--- | :--- | :--- |
| **Phase 00 — Phạm vi (Scope)** | AI hỗ trợ kiểm tra cấu trúc phạm vi, đề xuất cách diễn đạt Core Job theo chuẩn Jobs-to-be-Done (JTBD) từ góc nhìn của sinh viên. | Xác nhận dự án P-103, persona sinh viên tìm thực tập, và thu hẹp phạm vi use case cốt lõi: **CV - Internship Matching**. |
| **Phase 01 — Core Action Card** | AI hỗ trợ brainstorm các ứng viên Core Action, giúp phân biệt giữa Core Action (hành vi người dùng nhận value) và System Output (`match_result_generated`). Hỗ trợ chạy 5 tiêu chí tự kiểm. | Chọn hành vi `match_result_reviewed` (xem và đánh giá kết quả matching hoàn chỉnh) làm Core Action duy nhất đạt 5/5 tiêu chí tự kiểm (thay vì "đăng nhập", "hỏi AI" hay "mở app"). |
| **Phase 02 — Nature & Cadence** | AI hỗ trợ phân tích Action Nature Card (Actor, Intent, Trigger, Effort, Value timing...), phản biện thói quen mặc định Daily/Weekly cadence. | Xác định bản chất hành vi là **Event-driven (phản ứng theo sự kiện)**. Cadence không ép daily habit mà gắn với từng phiên tìm kiếm và số lượng cơ hội thực tập phát sinh. |
| **Phase 03 — Metric System & Retention** | AI hỗ trợ định nghĩa Activation Rate (Start event, Activation event, Window 7 ngày), Engagement (Frequency & Depth), North Star Metric (NSM), Leading Indicators và Counter-Metric. | Chốt định nghĩa Retention 6 thành phần với **30-day Custom Search-Cycle Window** (chống dán nhãn "rời bỏ" sai lầm khi không phải daily app), NSM đạt chuẩn Quality Threshold & Unit of Value. |
| **Phase 04 — Product Loop & Tracking** | AI hỗ trợ đề xuất cấu trúc 2 chu kỳ Product Loop (Natural trigger, Core action, Value, Decision, Saved state) và danh sách 6 Core Events dạng `object_action`. | Đã duyệt bộ 6 Core Events map 1-1 với Metric System, loại bỏ vanity click, thiết lập 4 Acceptance Criteria chặt chẽ chống bắn event sớm/trùng lặp. |
| **Phase 05 — Tự soi lỗi & Revision** | AI hỗ trợ đối chiếu toàn bộ hệ thống metric & tracking với 7 câu checklist kiểm lỗi phổ biến (vanity metrics, missing events, arbitrary windows). | Phát hiện Leading Indicator "thời gian chọn internship -> review" bị thiếu event đo lường. Điều chỉnh lại thành `match_result_generated` -> `match_result_reviewed` để đo lường chính xác từ telemetry. |

---

## 2. Đánh giá & Thu hoạch khi làm việc với AI

### 2.1. AI đã giúp tôi ở đâu?
- **Phân biệt sắc nét giữa System Output và Core Action:** AI giúp làm rõ sự khác biệt giữa `match_result_generated` (hệ thống tự chạy) và `match_result_reviewed` (hành vi người dùng thực sự đọc & hấp thụ giá trị).
- **Chuẩn hóa hệ thống Tracking Event:** Gợi ý cách đặt tên chuẩn dạng `object_action` (như `internship_search_started`, `match_result_reviewed`, `match_decision_recorded`) và xây dựng Acceptance Criteria để ngăn ngừa telemetry rác.
- **Xây dựng khung bài trình bày trực quan:** Hỗ trợ chuẩn hóa file `product-metrics-lab.html` đẹp mắt, khoa học, thể hiện đầy đủ 8 mục (00 đến 07) phục vụ đánh giá 5 Gates.

### 2.2. AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?
- **Đề xuất thói quen dùng Daily/Weekly Retention mặc định:** Ban đầu AI có xu hướng gợi ý đo D7/D30 retention theo lịch cố định của calendar. Điều này sai với nature của sản phẩm tìm việc/thực tập (vốn theo mùa hoặc theo đợt ứng tuyển).
- **Metric thiếu telemetry để tính:** AI từng đề xuất một Leading Indicator đo khoảng thời gian từ khi sinh viên "click chọn cơ hội thực tập" đến "hoàn thành review", nhưng lại quên không đưa event `internship_selected` vào bảng tracking.

### 2.3. Tôi đã tự sửa hoặc quyết định lại điều gì?
- **Thay đổi Retention Window:** Tôi quyết định đổi định nghĩa Retention sang **30-day Custom Search-Cycle Window** thay vì dán nhãn "churned" nếu sinh viên không đăng nhập ở Day 7.
- **Revision cho Leading Indicator:** Tôi chủ động điều chỉnh lại Leading Indicator đo khoảng thời gian từ `match_result_generated` sang `match_result_reviewed` để đảm bảo 100% metric đều có telemetry tương ứng để tính toán.
- **Bảo vệ Counter-Metric:** Quyết định đưa `Negative Match Feedback Rate` (`match_feedback_submitted` với `feedback_type = negative`) vào bộ metric để đảm bảo đội ngũ không chạy theo số lượng match mà làm giảm chất lượng gợi ý.
