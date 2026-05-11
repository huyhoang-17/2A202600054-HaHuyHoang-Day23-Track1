# 02 — Case Comparison

**Học viên:** Hà Huy Hoàng — 2A202600054  
**Nhóm:** [Nhóm Day 23]

---

## B. Case Comparison — Nhóm

| Trường | Case thành công / tín hiệu tốt | Case cảnh báo / thất bại |
|---|---|---|
| **Case** | **Morgan Stanley AI Financial Advisor Assistant** — GPT-4 tích hợp vào knowledge base nội bộ phục vụ 16.000+ financial advisors | **IBM Watson / MD Anderson Oncology** — Watson for Oncology triển khai tại MD Anderson Cancer Center để hỗ trợ bác sĩ đưa ra phác đồ điều trị ung thư |
| **Workflow có AI** | Advisor hỏi bằng ngôn ngữ tự nhiên → AI tổng hợp từ 100.000+ trang tài liệu → trả lời có trích dẫn → advisor review và dùng trong tư vấn khách hàng | Oncologist nhập thông tin bệnh nhân → Watson phân tích và đề xuất phác đồ điều trị → bác sĩ review → áp dụng hoặc bác bỏ |
| **Metric chính** | % advisors dùng hằng tuần; thời gian tra cứu giảm; CSAT nội bộ của advisor | Tỷ lệ đồng thuận giữa Watson và chuyên gia nhân loại (concordance rate); số ca Watson xử lý |
| **Metric đó chứng minh được gì?** | AI giúp advisor truy cập thông tin nhanh hơn; người dùng chủ động dùng công cụ (adoption thật); giảm thời gian tìm kiếm thủ công | Watson có thể đưa ra gợi ý phù hợp với một phần quyết định của chuyên gia; hệ thống vận hành được ở môi trường y tế |
| **Metric đó chưa chứng minh được gì?** | Client outcome (khách hàng có tốt hơn không); quality của lời khuyên tài chính; advisor có tin AI hay chỉ dùng như search engine | Kết quả điều trị thực tế của bệnh nhân; safety khi Watson sai; khả năng xử lý các ca ung thư hiếm, phức tạp vượt training data |
| **Thiếu metric nào?** | Client NPS; tỷ lệ advisor dùng câu trả lời AI không chỉnh sửa; error rate khi AI trích dẫn sai | Patient outcome (sống sót, chất lượng sống); false positive / false negative rate của Watson; tỷ lệ bác sĩ reject gợi ý Watson vì lý do gì |
| **Bài học cho dashboard nhóm** | Đo adoption thật (dùng đúng nhịp, đúng workflow) chứ không chỉ đo "đã đăng ký". Phải có ít nhất 1 metric quality từ phía người dùng cuối | Concordance với chuyên gia không đủ để chứng minh AI an toàn. Cần đo outcome thật, failure mode, và phải có human-in-loop rõ ràng trước khi deploy ở domain rủi ro cao |

---

## Câu chốt

```markdown
Case thành công dạy nhóm tôi rằng:
Adoption thật sự phải đo bằng việc người dùng quay lại dùng đúng workflow, không chỉ là số lần đăng nhập. 
Morgan Stanley thành công vì AI giải quyết đúng pain point (tra cứu tài liệu mất thời gian) và có human 
review tại mỗi bước trước khi output đến khách hàng.

Case cảnh báo / thất bại dạy nhóm tôi rằng:
Concordance với chuyên gia không phải là evidence đủ để scale AI trong domain rủi ro cao. 
IBM Watson thất bại vì không đo được patient outcome thật, không có failure mode rõ ràng, 
và dừng lại ở việc chứng minh AI "đồng ý với bác sĩ" thay vì "bệnh nhân tốt hơn".

Vì vậy dashboard nhóm tôi phải:
1. Có ít nhất 1 metric đo outcome từ phía người dùng cuối (student learning outcome, không chỉ "dùng tool").
2. Có metric về quality và error rate, không chỉ đo volume sử dụng.
3. Xác định rõ điểm human review và failure path trước khi scale.
4. Tách metric theo độ phức tạp của task (không average toàn bộ), vì AI thường hoạt động tốt 
   ở task đơn giản nhưng fail ở task phức tạp.
```

---

## Tự kiểm tra

- [x] Không chỉ kể chuyện case.
- [x] Có nêu metric cụ thể cho cả hai case.
- [x] Có nói metric chứng minh được gì và chưa chứng minh được gì.
- [x] Có ít nhất 2 bài học cụ thể áp dụng vào dashboard nhóm.
