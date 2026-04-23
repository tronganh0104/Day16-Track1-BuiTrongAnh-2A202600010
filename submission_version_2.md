# Day 16 Submission
Bùi Trọng Anh - 2A202600010
---

## 1. Idea reframed

Original idea:
> Em muốn xây dựng một AI Chatbot tư vấn tuyển sinh cho trường học, có thể trả lời câu hỏi của phụ huynh và học sinh về chương trình học, học phí, cơ sở, hồ sơ và quy trình nhập học.

Reframed as a product opportunity:
> Trong giai đoạn tuyển sinh, phụ huynh có nhu cầu hỏi rất nhiều câu lặp lại nhưng vẫn mang tính cá nhân hóa cao: con tôi ở độ tuổi nào phù hợp, học phí ra sao, cơ sở nào gần nhà, cần chuẩn bị hồ sơ gì, khi nào nên gặp tư vấn viên. Khoảng trống hiện tại là website chỉ phù hợp để tra cứu tĩnh, còn đội ngũ tư vấn viên lại tốn thời gian xử lý quá nhiều câu hỏi lặp lại ở đầu phễu. Chúng em tin rằng cơ hội sản phẩm nằm ở việc biến khối thông tin tuyển sinh phân tán thành một lớp hội thoại thông minh, đáng tin cậy và có khả năng sàng lọc lead. Nếu làm tốt, sản phẩm không chỉ giảm tải support mà còn tăng tỷ lệ chuyển đổi từ quan tâm sang đăng ký.

---

## 2. Customer / Segment Card

- **Segment name:** Phụ huynh đang chủ động tìm trường cho con trong 3–6 tháng trước kỳ tuyển sinh
- **Operational context:** Họ đang so sánh 2–5 lựa chọn trường, thu thập thông tin nhanh để quyết định có nên để lại lead, đi campus tour hoặc nộp hồ sơ hay không
- **Recurring workflow:** Tìm trường qua Google/Facebook/website → đọc thông tin → hỏi học phí/chương trình/cơ sở → hỏi lại trên fanpage/Zalo/hotline → chờ phản hồi → tiếp tục so sánh với trường khác
- **Pain moment:** Khi phụ huynh có câu hỏi cụ thể theo hoàn cảnh của con nhưng website không trả lời trực tiếp, còn tư vấn viên chưa phản hồi kịp
- **Why now:** Hành vi người dùng đã quen với giao diện chat; các trường đang cần tối ưu chi phí tuyển sinh; LLM hiện đủ tốt để xử lý FAQ, phân loại intent và chuyển tiếp cho người thật khi vượt ngưỡng rủi ro
- **Access path:** Widget trên website tuyển sinh, fanpage, landing page chiến dịch, QR tại sự kiện open day, Zalo OA

One-sentence description:
> Đây là nhóm phụ huynh có nhu cầu ra quyết định trong thời gian ngắn, cần câu trả lời nhanh, đúng và mang tính cá nhân hóa tối thiểu trước khi họ sẵn sàng nói chuyện với tư vấn viên thật.

---

## 3. Need Map (2–3 needs)

### Need #1 (priority)
- **Statement (JTBD):** When I am evaluating whether a school fits my child, I want to ask questions in natural language and receive trustworthy answers immediately, so I can decide whether to continue exploring or leave my information.
- **Current workaround:** Đọc website, tải brochure, nhắn fanpage, gọi hotline, hỏi trong group phụ huynh
- **Pain signal:** Hỏi cùng một câu ở nhiều kênh; bỏ cuộc giữa chừng; quay lại hỏi những thông tin cơ bản như học phí, độ tuổi, chương trình, cơ sở
- **Evidence / proxy evidence:** Hầu hết đội tuyển sinh đều có FAQ, hotline, inbox fanpage và nhân sự chuyên xử lý câu hỏi đầu phễu; điều này cho thấy nhu cầu lặp lại với tần suất cao
- **Why underserved:** Kênh hiện tại bị chia cắt giữa nội dung tĩnh và phản hồi thủ công; website không hội thoại được, còn tư vấn viên không thể online 24/7 để trả lời tức thời

### Need #2
- **Statement (JTBD):** When I have a partially matched interest, I want the school to guide me to the most relevant next step, so I can move forward without bị ngợp bởi quá nhiều thông tin.
- **Current workaround:** Tự đọc hết website hoặc chờ nhân viên gửi thêm thông tin
- **Pain signal:** Phụ huynh nhận quá nhiều nội dung nhưng vẫn không biết nên làm gì tiếp theo: để lại số, đặt lịch tham quan, hỏi điều kiện đầu vào hay chuẩn bị hồ sơ
- **Evidence / proxy evidence:** Phễu tuyển sinh của trường thường rơi lead ở giai đoạn sau khi phụ huynh đã ghé website nhưng chưa thực hiện hành động tiếp theo
- **Why underserved:** Hệ thống hiện tại chủ yếu cung cấp thông tin, chưa chủ động điều hướng hội thoại theo intent và mức độ sẵn sàng của người dùng

### Need #3 (optional)
- **Statement (JTBD):** When my question becomes specific or high-stakes, I want to be handed off to the right human advisor with full context, so I do not have to repeat myself and can get a confident answer.
- **Current workaround:** Chatbot/fanpage trả lời chung chung rồi phụ huynh phải gọi lại hoặc nhắn lại từ đầu cho tư vấn viên
- **Pain signal:** Trải nghiệm đứt mạch; phải lặp lại thông tin của con, nhu cầu và lịch sử câu hỏi
- **Evidence / proxy evidence:** Trong tuyển sinh, các câu hỏi về hồ sơ cá nhân, ưu đãi, ngoại lệ đầu vào hoặc lịch hẹn thường cần con người xử lý
- **Why underserved:** Nhiều chatbot hiện nay chỉ dừng ở FAQ, chưa có cơ chế chuyển tuyến có ngữ cảnh sang tư vấn viên thật

---

## 4. Strategy Statement

For phụ huynh đang ở giai đoạn đầu và giữa của hành trình chọn trường cho con  
who struggle with việc nhận câu trả lời tuyển sinh nhanh, đúng và đủ định hướng hành động,  
our product helps them tiến nhanh hơn từ “đang tìm hiểu” sang “sẵn sàng đăng ký hoặc gặp tư vấn viên”  
through một AI admission copilot kết hợp trả lời dựa trên knowledge base, gợi ý bước tiếp theo theo intent, và handoff có ngữ cảnh sang người thật,  
unlike website FAQ tĩnh, form để lại lead hoặc chatbot rule-based đơn giản,  
because we can leverage dữ liệu câu hỏi tuyển sinh thực tế, log hội thoại, human review và kiến trúc escalation phù hợp với nghiệp vụ trường học.

---

## 5. Moat Hypothesis

**Moat mechanism:** workflow-and-data flywheel trong ngữ cảnh tuyển sinh

If we deploy 20 times in school admission contexts, the following improve:
1. Bộ intent tuyển sinh đặc thù ngày càng đầy đủ hơn (học phí, độ tuổi, chương trình, campus fit, hồ sơ, timeline, scholarship, campus visit)
2. Hệ thống handoff và policy routing chính xác hơn: câu nào AI trả lời được, câu nào phải chuyển người thật, chuyển cho ai
3. Conversion playbook tốt hơn theo từng loại trường: trường phổ thông, quốc tế, liên cấp, đại học, trung tâm đào tạo

Why competitors cannot easily replicate this:
> Đối thủ có thể sao chép giao diện chatbot, nhưng khó sao chép tập dữ liệu hội thoại tuyển sinh chất lượng cao, taxonomy intent theo ngành dọc, ngưỡng chuyển tuyến an toàn và các tối ưu vận hành được rút ra từ nhiều lần triển khai thực tế. Giá trị không chỉ nằm ở model mà nằm ở dữ liệu, luồng nghiệp vụ và vòng lặp human review gắn chặt với ngữ cảnh tuyển sinh.

---

## 6. Initial TAM / SAM / SOM view

| Layer | Estimate | Key assumptions | Confidence |
|---|---|---|---|
| TAM | $8M–$25M/year | Bao gồm các trường K-12 tư thục, quốc tế, hệ liên cấp và một phần đại học/tổ chức giáo dục tại Việt Nam có nhu cầu số hóa tuyển sinh | low |
| SAM | $2M–$6M/year | Tập trung trước vào các trường có học phí trung bình-cao, có volume lead số đáng kể và đã có team tuyển sinh riêng | low |
| SOM | $150K–$400K/year | Mục tiêu 12–24 tháng là bán cho nhóm nhỏ trường tiên phong, pricing theo setup + subscription + hỗ trợ vận hành | low |

**Top 3 unknowns requiring further research:**
1. Ai là economic buyer thực sự: ban giám hiệu, phòng marketing hay phòng tuyển sinh?
2. Mức ROI nào đủ thuyết phục trường chi tiền: giảm tải nhân sự, tăng tốc phản hồi hay tăng conversion lead?
3. Vertical beachhead nào nên vào trước để có tỷ lệ thắng cao nhất: trường quốc tế, trường tư thục K-12 hay đại học ngoài công lập?

**Judgment:**
- [x] Worth pursuing now
- [ ] Worth pursuing but not now (need to validate [...] first)
- [ ] Not worth pursuing as currently framed

---

## 7. Positioning Note (2 sentences)

**What we are:**
> Một AI admission copilot giúp trường học trả lời câu hỏi tuyển sinh đầu phễu, điều hướng phụ huynh đến bước tiếp theo phù hợp và chuyển tiếp mượt mà sang tư vấn viên thật khi cần.

**What we are not / not yet:**
> Chúng tôi chưa phải là hệ thống CRM tuyển sinh hoàn chỉnh, cũng chưa nên được dùng để tự động trả lời hoàn toàn các tình huống ngoại lệ hoặc quyết định có tính chính sách cao.

---

## 8. Self-assessment before Day 17

Trong 6 mắt xích (Idea → Customer → Need → Strategy → Moat → Market Size), mắt xích nào đang yếu nhất?

> Đang yếu nhất ở mắt xích Moat → Market Size. Bọn em đã có một ý tưởng hợp lý và customer khá rõ, nhưng chưa chứng minh được rằng đây là một thị trường đủ lớn và đủ “đau” để trường sẵn sàng trả tiền, cũng như chưa chỉ ra được lợi thế khó sao chép ngoài việc dùng LLM.

Open questions tôi muốn khám phá thêm ở Day 17:
1. Chỉ số nào là bằng chứng mạnh nhất cho ROI của sản phẩm này trong tuyển sinh?
2. Điểm cắt giữa AI self-serve và human advisor nên được thiết kế như thế nào để vừa an toàn vừa hiệu quả?
3. Nên wedge vào bài toán “trả lời FAQ”, “lead qualification” hay “advisor handoff” để có khả năng bán tốt nhất?