# 03 — Product ROI Dashboard v2

**Học viên:** Hà Huy Hoàng — 2A202600054  
**Sản phẩm:** AI Study Assistant — trợ lý học tập AI cho sinh viên đọc tài liệu học thuật  
**Version:** v2 (sau red-team)

---

## Part A — Adoption Context

### A.1 Thách thức nhóm chọn

| Trường | Trả lời |
|---|---|
| **Thách thức áp dụng AI** | Sinh viên đại học dành quá nhiều thời gian đọc tài liệu học thuật dài (giáo trình, paper, slide) nhưng khả năng ghi nhớ và vận dụng thấp. Học nhiều nhưng hiểu ít, chuẩn bị thi kém hiệu quả. |
| **Tình huống xuất phát từ ai / ở đâu?** | Bộ phận Academic Affairs và giảng viên nhận phản hồi sinh viên gặp khó khăn tự học với tài liệu tiếng Anh kỹ thuật. Survey đầu kỳ cho thấy 68% sinh viên đọc tài liệu lần đầu mà không ghi chép hoặc ôn lại. |
| **Dấu hiệu bị kẹt** | Tool AI đã được giới thiệu trong orientation nhưng sau 4 tuần chỉ 22% sinh viên còn dùng hằng tuần. Phần lớn dùng 1-2 lần rồi bỏ. Không có cơ chế nhắc nhở hoặc tích hợp vào workflow học tập thực tế. |
| **Vì sao thách thức này đáng giải quyết?** | Kết quả học tập là outcome cốt lõi của trường đại học. Nếu AI giúp sinh viên hiểu sâu hơn và nhớ lâu hơn, GPA tăng, drop rate giảm, và trường chứng minh được giá trị giáo dục thật sự. |

### A.2 Sản phẩm / Công cụ AI

| Trường | Trả lời |
|---|---|
| **Tên sản phẩm / công cụ AI** | AI Study Assistant (tích hợp vào LMS nội bộ của trường) |
| **Người dùng chính** | Sinh viên đại học (năm 1-4), ưu tiên các môn có tài liệu kỹ thuật nặng |
| **Bối cảnh sử dụng** | Sinh viên upload tài liệu hoặc dùng tài liệu giảng viên đã tải lên LMS; dùng ngoài giờ học để tự ôn tập, chuẩn bị thi |
| **Mục tiêu học tập / vận hành** | Tăng comprehension rate (sinh viên hiểu đúng khái niệm chính); tăng retention rate (nhớ sau 1 tuần); giảm thời gian ôn tập cần thiết trước kỳ thi |
| **Không nằm trong phạm vi** | Không thay thế giảng viên; không chấm bài kiểm tra chính thức; không dùng để viết bài luận thay sinh viên |

### A.3 4 Workflow chính

| # | Tên workflow | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | **Tóm tắt tài liệu** | AI đọc PDF/slide và tạo bản tóm tắt có cấu trúc, highlight khái niệm chính | Sinh viên đọc lại và đối chiếu với tài liệu gốc trước khi lưu | Sinh viên báo lỗi qua nút "AI missed this"; giảng viên review sample hằng tuần |
| 2 | **Hỏi-đáp về tài liệu** | AI trả lời câu hỏi của sinh viên kèm trích dẫn đoạn cụ thể trong tài liệu gốc | Sinh viên bấm "Verify" để xem đoạn trích dẫn gốc; giảng viên xem Q&A log hằng tuần | Nếu AI không tìm được nguồn, tự động cảnh báo "Low confidence"; sinh viên được hướng đến tài liệu gốc |
| 3 | **Tạo quiz luyện tập** | AI tạo 5-10 câu hỏi trắc nghiệm / tự luận ngắn từ tài liệu; giải thích đáp án sau khi sinh viên trả lời | Sinh viên xem giải thích và đánh dấu câu nào AI giải thích sai; giảng viên review báo cáo lỗi | AI giải thích sai → sinh viên report → giảng viên xác nhận và cập nhật prompt rule |
| 4 | **Gợi ý kế hoạch ôn tập** | Dựa trên lịch thi và kết quả quiz, AI gợi ý nội dung cần ôn theo thứ tự ưu tiên | Sinh viên điều chỉnh kế hoạch theo lịch cá nhân và confirm trước khi lưu | Gợi ý không phù hợp → sinh viên chỉnh thủ công; hệ thống ghi lại để cải thiện model |

### A.4 Chẩn đoán nhanh ADKAR

| Stage | Câu hỏi | Nhận định nhóm |
|---|---|---|
| Awareness | Sinh viên có biết AI Study Assistant giúp gì không? | Có — tool đã được giới thiệu trong orientation, nhưng chỉ demo chung chung, chưa show được lợi ích cụ thể cho từng môn học |
| Desire | Sinh viên có muốn dùng không? | Trung bình — sinh viên thấy "hay" nhưng chưa thấy đủ lý do để đổi thói quen học (đọc PDF thủ công, highlight màu) |
| Knowledge | Sinh viên có biết dùng đúng không? | Thiếu — phần lớn chỉ dùng tính năng tóm tắt, không biết cách dùng quiz và hỏi-đáp hiệu quả |
| Ability | Sinh viên có đủ access, thời gian, kỹ năng không? | Đủ — tool tích hợp LMS, không cần cài thêm; nhưng giao diện còn nhiều bước |
| Reinforcement | Có cơ chế khiến họ quay lại dùng không? | **Thiếu hoàn toàn** — không có notification nhắc ôn bài, không có gamification, không có feedback loop nào cho thấy "tuần này bạn học tốt hơn" |

**Barrier chính:**

```markdown
Reinforcement — Sinh viên không có lý do rõ ràng để quay lại dùng sau lần đầu. 
Không có điểm thưởng, không có nhắc nhở, không có bằng chứng học tốt hơn sau khi dùng tool. 
Khi không cảm nhận được kết quả, sinh viên tự nhiên quay về thói quen cũ.
```

### A.5 3 Tactic áp dụng

| Tactic | Nhắm vào barrier nào? | Áp dụng cho workflow nào? | Người phụ trách | Khi nào hoàn thành? |
|---|---|---|---|---|
| **1. Weekly Progress Digest** — Mỗi thứ Hai, sinh viên nhận email/notification tóm tắt: quiz score tuần trước, so sánh với tuần trước đó, nội dung gợi ý ôn tuần này | Reinforcement | Workflow 3 (Quiz) + Workflow 4 (Kế hoạch ôn tập) | Product Lead + Academic Affairs | Sprint 2 — 2 tuần sau go-live |
| **2. First-Session Onboarding Video tích hợp trong LMS** — Video 3 phút hướng dẫn cụ thể cho từng môn học (Calculus, Physics...), sinh viên xem trực tiếp khi mở tài liệu môn đó lần đầu | Knowledge + Desire | Tất cả 4 workflow | Content Team + Giảng viên môn học | Sprint 1 — trước go-live |
| **3. Giảng viên giao bài tập dùng quiz AI** — Giảng viên thiết kế 1 bài kiểm tra nhỏ hằng tuần yêu cầu sinh viên làm quiz từ AI Study Assistant và nộp screenshot kết quả | Reinforcement + Desire | Workflow 3 (Quiz) | Giảng viên + Academic Affairs | Tuần 3 sau go-live |

---

## Part B — ROI Dashboard

### B.1 Chỉ số toàn sản phẩm

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % sinh viên hoàn thành ít nhất 1 workflow đầy đủ trong tuần đầu | 22% (sau 4 tuần) | 60% sau 4 tuần | LMS session log | Product Lead | Chỉ đo người dùng 1 lần, không biết có quay lại không | v2: thêm cột Retention 30 ngày |
| Retention / Value | % sinh viên dùng ít nhất 1 tính năng/tuần sau 30 ngày | Chưa đo | 45% sau 30 ngày | LMS weekly active log | Academic Affairs | Dùng 1 tính năng dễ nhất (tóm tắt) không có nghĩa là học tốt hơn | v2: tách metric theo tính năng, ưu tiên quiz completion |
| Trust / Quality | % sinh viên đánh giá tóm tắt AI "accurate enough to use" (rating ≥ 4/5) | Chưa đo | 75% | In-app rating sau mỗi summary | QA Lead | Rating có thể bị bias (sinh viên không biết tóm tắt sai) | v2: ghép với giảng viên review 10% sample hằng tuần |

### B.2 Chỉ số theo từng workflow

#### Workflow 1 — Tóm tắt tài liệu

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % tài liệu được upload có phiên tóm tắt hoàn thành (không bỏ nửa chừng) | Chưa đo | 70% | LMS upload + summary completion log | Product Lead | Upload nhiều nhưng không đọc tóm tắt | v2: đo thêm "time spent reading summary" |
| Engagement | Số lần sinh viên quay lại đọc tóm tắt cũ (không phải tóm tắt mới) | Chưa đo | Tăng 20% so với tuần 1 sau 4 tuần | LMS revisit log | Product Lead | Chỉ đo lần mở, không biết có đọc không | v2: thêm scroll depth tracking |
| Productivity | Thời gian đọc hiểu 1 chương (trước và sau khi dùng AI tóm tắt) | ~45 phút/chương (survey) | 30 phút/chương | Pre/post survey + timer tích hợp | Academic Affairs | Thời gian giảm nhưng comprehension có thể giảm theo | v2: ghép với quiz score của cùng nội dung |
| Quality | % tóm tắt được giảng viên đánh giá là "không bỏ sót khái niệm quan trọng" | Chưa đo | 80% | Giảng viên review 10% sample/tuần | Subject Lecturer | Giảng viên review tốn thời gian, không bền vững | v2: giảng viên chỉ review 5% nhưng ghi lý do cụ thể khi fail |
| Trust | Tỷ lệ sinh viên chọn "dùng tóm tắt AI" vs "bỏ qua, đọc gốc" | Chưa đo | 60% chọn dùng sau tuần 4 | In-app choice tracking | Product Lead | Dùng vì bắt buộc (giảng viên giao), không phải vì tin | v2: thêm exit survey "vì sao bạn bỏ qua tóm tắt" |
| Value | Điểm quiz cuối chương của sinh viên dùng AI summary vs không dùng | Chưa đo | Nhóm dùng AI ≥ +5 điểm so với nhóm không dùng | LMS quiz result + AI usage log | Academic Affairs | Selection bias (sinh viên chăm mới dùng AI) | v2: controlled experiment với 2 nhóm random |

#### Workflow 2 — Hỏi-đáp về tài liệu

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % sinh viên đặt ≥ 3 câu hỏi trong 1 phiên học | Chưa đo | 40% | Q&A session log | Product Lead | 3 câu có thể là câu test linh tinh, không phải học thật | v2: đo % câu hỏi có liên quan đến tài liệu (keyword matching) |
| Engagement | Số câu hỏi trung bình/sinh viên/tuần | Chưa đo | 8 câu/tuần | Q&A log | Product Lead | Câu hỏi nhiều chưa chắc hiệu quả | v2: ghép với quiz score tuần đó |
| Productivity | Thời gian từ khi đặt câu hỏi đến khi sinh viên confirm "đã hiểu" | Chưa đo | Dưới 3 phút/câu hỏi | Session timer | Product Lead | "Confirm hiểu" không đo được hiểu thật | v2: theo dõi câu hỏi tương tự có bị hỏi lại trong tuần không |
| Quality | Tỷ lệ câu trả lời được AI tag "Low confidence" (không tìm được nguồn rõ) | Chưa đo | Dưới 15% tổng câu hỏi | AI confidence score log | QA Lead | AI có thể confident nhưng sai | v2: giảng viên spot-check 10 câu/tuần ngẫu nhiên |
| Trust | Override rate — % câu trả lời sinh viên đánh dấu "AI sai, tôi tra lại tài liệu gốc" | Chưa đo | 10-20% (healthy skepticism zone) | In-app feedback | QA Lead | Override rate quá thấp = sinh viên không kiểm tra; quá cao = AI không tin được | v2: alert khi override rate >30% hoặc <5% |
| Value | Điểm câu hỏi tự luận trên thi cuối kỳ so với cohort không dùng AI Q&A | Chưa đo | +8 điểm trung bình | Exam result + AI usage cohort split | Academic Affairs | Nhiều biến ngoại lai ảnh hưởng điểm thi | v2: so sánh trong cùng lớp, kiểm soát GPA ban đầu |

#### Workflow 3 — Tạo quiz luyện tập

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % sinh viên hoàn thành ít nhất 1 quiz đầy đủ sau khi đọc tài liệu | 22% (từ pilot) | 55% sau 4 tuần | Quiz completion log | Product Lead | Hoàn thành 1 quiz không đủ để nói adoption | v2: đo % hoàn thành ≥ 3 quiz/tuần |
| Engagement | % sinh viên làm lại quiz sau khi thấy điểm thấp (retry rate) | Chưa đo | 40% | Quiz retry log | Product Lead | Retry vì muốn học hay vì muốn điểm cao? | v2: theo dõi improvement rate giữa lần 1 và lần 2 |
| Productivity | Thời gian trung bình làm 1 bộ quiz 10 câu | Chưa đo | 15 phút | Quiz timer | Product Lead | Nhanh có thể là chọn đại, không phải hiểu | v2: ghép với accuracy rate |
| Quality | Tỷ lệ câu quiz bị giảng viên đánh giá "sai nội dung hoặc misleading" | Chưa đo | Dưới 5%/tuần | Giảng viên review báo cáo lỗi sinh viên report | Subject Lecturer | Sinh viên không report câu sai nếu không nhận ra | v2: giảng viên chủ động review 1 bộ quiz mỗi tuần |
| Trust | % sinh viên report ít nhất 1 câu sai/tháng (healthy engagement rate) | Chưa đo | 20% sinh viên active | Report button log | QA Lead | Không report ≠ quiz đúng; có thể sinh viên không để ý | v2: hiển thị nút report nổi hơn, kèm incentive nhỏ |
| Value | Điểm kiểm tra giữa kỳ của nhóm dùng quiz AI ≥ 5 lần/tuần vs nhóm không dùng | Chưa đo | +10 điểm trung bình | Midterm result + quiz usage log | Academic Affairs | Correlation không phải causation | v2: survey thêm "bạn cảm thấy tự tin hơn trước thi không?" |

#### Workflow 4 — Gợi ý kế hoạch ôn tập

| Lớp đo | Chỉ số | Baseline | Target | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % sinh viên có lịch thi trong 2 tuần đã mở và xem kế hoạch ôn tập AI gợi ý | Chưa đo | 50% | Study plan view log + calendar integration | Product Lead | Xem nhưng không làm theo | v2: đo % mark "đã ôn xong" cho từng mục |
| Engagement | % kế hoạch AI gợi ý được sinh viên chỉnh sửa ít nhất 1 mục trước khi confirm | Chưa đo | 60% (chỉnh sửa = đang suy nghĩ thật) | Edit log | Product Lead | Chỉnh 1 mục nhỏ không có nghĩa là kế hoạch phù hợp | v2: track số mục chỉnh sửa trung bình |
| Productivity | Thời gian sinh viên lập kế hoạch ôn tập thủ công (trước) vs dùng AI (sau) | ~30 phút/kỳ thi (survey) | Dưới 10 phút | Pre/post survey | Academic Affairs | Nhanh hơn nhưng kế hoạch kém chất lượng hơn | v2: ghép với quiz coverage (ôn đủ chương chưa) |
| Quality | % kế hoạch AI gợi ý cover đủ các chương có trong đề cương thi | Chưa đo | 90% | Syllabus coverage check (auto-compare) | QA Lead | Đề cương có thể thay đổi sát ngày thi | v2: sync kế hoạch với syllabus live |
| Trust | % sinh viên chọn "dùng kế hoạch AI" vs "lập kế hoạch tự mình" khi có cả 2 lựa chọn | Chưa đo | 55% chọn dùng AI sau 4 tuần | In-app choice log | Product Lead | Chọn vì lười hay vì tin? | v2: thêm câu hỏi "bạn có điều chỉnh gì không?" |
| Value | Tỷ lệ sinh viên dùng kế hoạch AI đạt điểm pass (≥60/100) trong kỳ thi | Chưa đo | 85% pass rate | Exam result + study plan usage log | Academic Affairs | Pass rate ảnh hưởng bởi nhiều yếu tố khác | v2: kiểm soát bằng cách so sánh với cohort tương đương GPA |

---

## Part C — Dashboard Mock

```text
┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH               │ │ TILE 2: WORKFLOW 1 — TÓM TẮT        │
│ Metric: Weekly Active Rate           │ │ Metric: Summary Quality (Lecturer)   │
│ Current: 22%  Target: 45%            │ │ Current: N/A   Target: ≥80% pass     │
│ Status: RED                          │ │ Status: AMBER (chưa đo)              │
│ Action if red:                       │ │ Action if red:                        │
│   → Kích hoạt tactic 1 (Weekly       │ │   → Tăng tần suất giảng viên review;  │
│     Digest) + tactic 3 (bài tập)     │ │     điều chỉnh prompt tóm tắt         │
└──────────────────────────────────────┘ └──────────────────────────────────────┘

┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ TILE 3: WORKFLOW 3 — QUIZ            │ │ TILE 4: TRUST / QUALITY              │
│ Metric: Quiz Completion Rate         │ │ Metric: AI Override Rate (Q&A)       │
│ Current: 22%  Target: 55%            │ │ Current: N/A   Target: 10-20%        │
│ Status: RED                          │ │ Status: AMBER (chưa đo)              │
│ Action if red:                       │ │ Action if red:                        │
│   → Tích hợp quiz vào bài tập tuần;  │ │   → Review câu trả lời AI sai;        │
│     gamification nhỏ (streak badge)  │ │     cập nhật prompt rule tuần đó      │
└──────────────────────────────────────┘ └──────────────────────────────────────┘

┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ TILE 5: VALUE — LEARNING OUTCOME     │ │ TILE 6: DECISION                     │
│ Metric: Quiz Score vs Non-AI Cohort  │ │ Continue / Pivot / Kill: CONTINUE    │
│ Current: N/A   Target: +10 điểm     │ │   với guardrails                      │
│ Status: AMBER (cần 4 tuần data)      │ │ Metric mạnh nhất: Quiz completion    │
│ Action if red:                       │ │   rate + Midterm score gap            │
│   → Review tính năng quiz; xem xét  │ │ Before scale:                         │
│     redesign lại UX và onboarding    │ │   Giảng viên xác nhận quiz quality;  │
└──────────────────────────────────────┘ │   Đạt 45% WAR + learning outcome data│
                                         └──────────────────────────────────────┘
```

---

## Part D — Decision Memo

```markdown
# Decision Memo — AI Study Assistant

1. Nhóm khuyến nghị: CONTINUE với guardrails.

   Tiếp tục triển khai nhưng không scale đến toàn trường cho đến khi có data 
   4 tuần đầy đủ về quiz completion rate và learning outcome. 
   Giữ phạm vi pilot trong 2-3 lớp có giảng viên chủ động tham gia.

2. Chỉ số mạnh nhất để bảo vệ quyết định là:
   
   **Quiz completion rate kết hợp với midterm score gap.**
   
   Đây là evidence quan trọng nhất vì:
   - Quiz completion rate đo được hành vi học tập thật (không chỉ đăng nhập).
   - Midterm score gap đo được outcome thật từ phía người học.
   - Hai metric này cùng xanh = AI tạo giá trị học thuật thật sự.
   - Nếu quiz completion cao nhưng score không tăng → pivot: sửa lại chất lượng quiz.
   - Nếu score tăng mà quiz completion thấp → tín hiệu tốt từ nhóm nhỏ, cần scale thêm.

3. Chỉ số hoặc giả định nhóm đã sửa sau red-team là:
   
   **Thay đổi 1:**
   V1 dùng "Weekly Active Users" (WAU) làm metric chính toàn sản phẩm.
   Red-team vai CFO phản biện: "WAU chỉ đo ai mở app, không đo ai học được gì. 
   Một sinh viên mở tóm tắt 3 giây rồi đóng vẫn tính là active."
   V2 sửa thành: tách WAU thành "% sinh viên hoàn thành ít nhất 1 workflow đầy đủ/tuần" 
   và ghép với "quiz score của tuần đó". V2 tốt hơn vì đo hành vi có kết quả, không chỉ 
   đo hiện diện.

   **Thay đổi 2:**
   V1 dùng "% sinh viên hài lòng với tóm tắt AI" (self-report) làm Quality metric.
   Red-team vai Risk phản biện: "Sinh viên không biết tóm tắt sai thì không report. 
   Self-report bias rất cao khi người đánh giá không có baseline để so sánh."
   V2 sửa thành: ghép self-report với giảng viên review 10% sample mỗi tuần và đo tỷ lệ 
   "% tóm tắt không bỏ sót khái niệm quan trọng" theo đánh giá chuyên môn. 
   V2 tốt hơn vì có external validation độc lập với cảm nhận sinh viên.

4. Trước khi scale, nhóm phải:
   1. **Đo và đạt learning outcome baseline** — Academic Affairs + Product Lead, deadline: cuối tuần 4 pilot
   2. **Giảng viên xác nhận quiz quality đạt <5% câu sai** — Subject Lecturers, deadline: tuần 3 pilot
   3. **Fix UX onboarding** để sinh viên hoàn thành workflow đầu đủ lần đầu đạt 60% — Product Team, deadline: tuần 2 pilot
```

---

## Ghi chú: Thay đổi từ v1 sang v2

| # | V1 có vấn đề gì? | V2 sửa thành gì? | Vì sao sửa này tốt hơn? |
|---|---|---|---|
| 1 | Metric chính là WAU — đo ai mở app, không đo ai học được gì | Đổi thành "% hoàn thành ≥ 1 workflow đầy đủ/tuần" + ghép quiz score | Đo hành vi có kết quả, tránh vanity metric |
| 2 | Quality metric dựa hoàn toàn vào self-report của sinh viên | Ghép với giảng viên review 10% sample + tỷ lệ "không bỏ sót khái niệm" | Có external validation độc lập, giảm self-report bias |

---

*Product ROI Dashboard v2 — AI Study Assistant — Hà Huy Hoàng 2A202600054*
