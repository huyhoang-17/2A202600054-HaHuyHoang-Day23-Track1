# 04 — Reflection

**Học viên:** Hà Huy Hoàng — 2A202600054  
**Ngày:** 2026-05-11

---

## Reflection cá nhân sau lớp

Điều tôi thay đổi sau buổi học hôm nay là cách tôi nghĩ về metric "người dùng hài lòng".

Trước buổi học, tôi mặc nhiên cho rằng nếu người dùng nói họ hài lòng với AI, đó là bằng chứng tool đang hoạt động tốt. Trong dashboard v1 của nhóm, tôi đặt "% sinh viên hài lòng với tóm tắt AI" làm chỉ số Quality chính. Tôi nghĩ đơn giản: sinh viên dùng, sinh viên thấy ổn, vậy là AI có giá trị.

Red-team đã chỉ ra lỗ hổng này ngay lập tức. Vai Risk hỏi: "Làm sao sinh viên biết tóm tắt AI sai nếu họ chưa đọc tài liệu gốc?" Câu hỏi đó làm tôi nhận ra rằng self-report satisfaction chỉ đo cảm giác của người dùng, không đo chất lượng output. Người dùng hài lòng với thứ họ không đủ khả năng kiểm tra không phải là tín hiệu tốt — đó là rủi ro ẩn.

Bài học cụ thể tôi sẽ mang theo: bất kỳ metric nào đo "người dùng cảm thấy" đều cần được ghép với một metric đo "output thực tế". Hài lòng + quality score của chuyên gia = evidence đáng tin. Hài lòng đơn độc = vanity metric dễ gây ảo giác thành công.

---

*Day 23 — VinUni A20 — AI Thực Chiến*
