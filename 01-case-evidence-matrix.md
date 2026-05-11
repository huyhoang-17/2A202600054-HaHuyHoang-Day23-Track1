# 01 — Case Evidence Matrix

**Học viên:** Hà Huy Hoàng — 2A202600054  
**Case được giao:** Morgan Stanley AI Financial Advisor Assistant

---

## A. Case Evidence Matrix — Cá nhân

| Trường | Trả lời |
|---|---|
| **Case** | Morgan Stanley triển khai AI Assistant (GPT-4) cho 16.000+ financial advisors để truy cập knowledge base nội bộ gồm 100.000+ trang tài liệu nghiên cứu, báo cáo thị trường và hướng dẫn đầu tư. |
| **AI được dùng trong workflow nào?** | Advisor đặt câu hỏi bằng ngôn ngữ tự nhiên → AI tìm kiếm và tổng hợp từ knowledge base → trả về câu trả lời có trích dẫn nguồn cụ thể → advisor xem xét và dùng trong tư vấn khách hàng. |
| **Người dùng chính là ai?** | Financial advisors (các chuyên gia tư vấn tài chính) nội bộ Morgan Stanley. |
| **Họ đo metric gì?** | (1) Tỷ lệ adoption: % advisors dùng tool ít nhất 1 lần/tuần; (2) Thời gian trả lời câu hỏi của khách hàng (trước/sau); (3) Điểm hài lòng của advisor (CSAT nội bộ); (4) Số lượng câu hỏi được xử lý qua AI mỗi tuần. |
| **Metric đó thuộc layer nào?** | Activation (tỷ lệ dùng) + Productivity (thời gian trả lời) + Trust (CSAT nội bộ) + Engagement (số câu hỏi/tuần). |
| **Metric đó chứng minh được gì?** | Chứng minh AI giúp advisor tra cứu thông tin nhanh hơn đáng kể, không phải dành hàng giờ tìm tài liệu thủ công. Cho thấy tool được dùng thực sự (không chỉ đăng ký). |
| **Metric đó chưa chứng minh được gì?** | Chưa chứng minh: (1) Chất lượng lời khuyên đầu tư đưa ra cho khách hàng có tốt hơn không; (2) Khách hàng có hài lòng hơn không (client-side outcome); (3) Portfolio performance của khách có cải thiện không; (4) Advisor có thật sự tin tưởng AI hay chỉ dùng như một công cụ search nâng cao. |
| **Thiếu metric nào?** | Thiếu: (1) Client outcome metric — client retention rate, NPS từ phía khách hàng; (2) Quality metric — tỷ lệ câu trả lời AI được advisor sử dụng không qua chỉnh sửa vs chỉnh sửa nhiều; (3) Error rate — số lần AI trả lời sai hoặc trích dẫn sai nguồn; (4) Long-term retention — sau 6 tháng, advisor có dùng đều không. |
| **Rủi ro lớn nhất** | Advisor tin tưởng AI quá mức mà không kiểm tra nguồn, dẫn đến tư vấn sai cho khách hàng dựa trên thông tin AI tổng hợp nhưng thiếu ngữ cảnh. Rủi ro tài chính và pháp lý rất cao trong lĩnh vực này. |
| **Bài học cho dashboard nhóm** | Không dừng ở "người dùng dùng tool". Phải đo được output quality và outcome từ phía người nhận dịch vụ cuối (client/student). Cần có metric về error rate và human-override rate để biết AI có đáng tin không. |

---

## Tự kiểm tra

- [x] Không chỉ kể chuyện case.
- [x] Có nêu metric cụ thể.
- [x] Có nói metric chứng minh được gì và chưa chứng minh được gì.
- [x] Có ít nhất 1 bài học áp dụng vào dashboard nhóm.
