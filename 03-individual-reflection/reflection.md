# 03 — Individual Reflection

> Viết bằng lời của bạn (Phase 7 trong `01-worksheet.md`). Có thể dùng AI gợi ý câu hỏi tự soi, không dùng AI viết thay. 8-12 câu, có chuyện cụ thể.

## Thông tin cá nhân

- Họ và tên: Nguyễn Trọng Minh
- Mã học viên: 2A202602496
- Nhóm: AIBC- Zone B
- Candidate problem nhóm chọn: **Vinhomes Resident Amenity Booking Bot / Script Exploit — bài toán công bằng khi đặt các slot tiện ích thể thao khan hiếm**

---

## 1. Tôi đã tham gia vào phần nào?

Ghi việc cụ thể + kết quả cụ thể. Không ghi chung chung kiểu "tham gia thảo luận".

| Hoạt động | Tôi đã làm gì? (việc cụ thể) | Kết quả / ảnh hưởng tới nhóm |
|---|---|---|
| Scan cá nhân | Tôi khảo sát các vấn đề vận hành ở nhiều đơn vị Vingroup và xây dựng 6 candidate problems, trong đó có bài toán Vinhomes Resident booking bot. | Cung cấp bộ vấn đề đầu vào cho quá trình hội tụ của nhóm; bài toán Vinhomes trở thành một trong các candidate được đưa ra shortlist. |
| Pitch Problem Card | Tôi trình bày Problem Card về Vinhomes Resident, tập trung vào actor, bối cảnh mở booking, bottleneck ở request admission và impact đối với tính công bằng của cư dân. | Giúp nhóm nhìn bài toán như một vấn đề về fair access vào tài nguyên khan hiếm thay vì chỉ là một lỗi của app. |
| Challenge bài của bạn khác | Tôi xem và so sánh các candidate của các thành viên, đặc biệt về mức độ evidence, workflow, metric và mức cần thiết của AI. | Nhóm có cơ sở loại các bài toán có thể giải tốt bằng Rule/Script hoặc đã có giải pháp riêng, thay vì chọn chỉ vì ý tưởng nghe “AI”. |
| Gom trùng / cluster | Tôi tham gia nhóm các candidate theo các pattern như customer/operations automation, resource/transaction fairness, finance/back-office và knowledge assistance. | Làm rõ vị trí khác biệt của bài toán Vinhomes: vấn đề fairness và cạnh tranh tài nguyên khan hiếm, không chỉ automation nội bộ. |
| Chọn candidate problem | Tôi đóng góp evidence và lập luận để chọn Vinhomes Resident Booking Bot / Script Exploit làm candidate nhóm. | Nhóm thống nhất đây là bài toán có pain trực tiếp, có thể kiểm chứng bằng booking logs và có không gian so sánh Rule/Workflow/AI. |
| Validation / research | Tôi rà soát App Store reviews, tài liệu xử lý khiếu nại Vinhomes và research các pattern anti-bot như rate limiting, behavioral scoring và challenge. | Nhóm điều chỉnh cách diễn đạt từ “bot chắc chắn đang hack hệ thống” thành “resident-reported problem, root cause cần xác minh bằng logs”, giúp report an toàn hơn về mặt evidence. |
| Workflow nhóm | Tôi tham gia xây dựng current/future workflow và đặc biệt tinh chỉnh điểm can thiệp của AI: sau eligibility/rule checks và trước atomic slot reservation. | Workflow cuối phân biệt rõ Rule, AI, human boundary và fallback; AI không trực tiếp quyết định commit slot. |
| Problem Statement | Tôi giúp chốt Problem Statement theo hướng “fair booking admission and allocation” thay vì chỉ nói “anti-bot”. | Problem Statement rõ actor, bottleneck, impact, metric và boundary; đồng thời không overclaim root cause khi chưa có server-side data. |
| Rule / Workflow / Agent | Tôi phản biện việc dùng Agent và đề xuất kiến trúc Rule + Workflow + ML Risk Scoring. | Nhóm thống nhất Workflow là mức phù hợp nhất; Rule xử lý case rõ ràng, AI chỉ hỗ trợ case mơ hồ và Agent không cần thiết. |
| Decision | Tôi tham gia đưa ra quyết định “Not Yet — pilot validation” thay vì coi giải pháp đã sẵn sàng triển khai. | Nhóm xác định rõ các dữ liệu còn thiếu: booking/server logs, baseline legitimate booking success, false-positive rate và bằng chứng xác minh root cause. |

**Dấu tay rõ nhất của tôi trong artifact cuối (1-2 câu):**

```text
Dấu tay rõ nhất của tôi là phần định hình bài toán Vinhomes từ một “bot exploit” thành bài toán công bằng trong booking admission và allocation. Tôi cũng góp phần làm rõ rằng AI không phải trung tâm của toàn bộ giải pháp; Rule + Workflow là nền tảng, còn AI chỉ xử lý những trường hợp hành vi mơ hồ.
```

---

## 2. Bảng dùng AI (mỗi dòng 1 phase có dùng AI — 2 cột cuối bắt buộc)

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Dùng AI để phản biện và mở rộng các painpoint đã scan, đồng thời gợi ý các điểm nghẽn có thể đo được. | Hữu ích trong việc nhóm các dấu hiệu rời rạc thành problem candidates và phát hiện các hướng AI có thể áp dụng. | AI dễ suy diễn nguyên nhân kỹ thuật từ complaint, ví dụ mặc định rằng slot hết nhanh chắc chắn là bot. | Tôi quay lại nguồn gốc evidence và phân biệt resident report với verified backend fact; những claim chưa có logs được đánh dấu là hypothesis. |
| Problem Card | Dùng AI để kiểm tra actor, workflow, bottleneck, impact, metric và scope của Problem Card Vinhomes. | Hữu ích khi tìm các field còn thiếu và phát hiện câu mô tả quá rộng. | AI ban đầu có xu hướng đưa các con số như “hàng trăm request/giây” hoặc “50ms” vào workflow dù chưa có production logs xác minh. | Tôi loại các con số chưa kiểm chứng khỏi factual claims và chuyển chúng thành dữ liệu cần lấy ở pilot/server logs. |
| Workflow | Dùng AI để so sánh current state với future state và tìm vị trí nên đặt AI. | Hữu ích trong việc làm rõ nhánh allow/challenge/block, human boundary và fallback. | Nếu đặt AI quá sớm, workflow trở nên “AI-first” và có nguy cơ dùng model cho những quyết định vốn deterministic. | Tôi đổi thành kiến trúc eligibility → deterministic controls → behavioral risk scoring → challenge/allow/block → atomic slot allocation. |
| Research | Dùng AI để tìm và tổng hợp các pattern anti-bot như rate limiting, fingerprinting, behavioral analysis và challenge. | Hữu ích để mở rộng phạm vi research và tìm các pattern có thể áp dụng cho booking system. | Một số benchmark và con số ngành trong draft không có link nguồn gốc đủ mạnh để kiểm chứng độc lập. | Tôi không đưa những benchmark đó thành fact trong final report; chỉ giữ các pattern có nguồn rõ hoặc ghi là assumption cần verify. |
| Problem Statement | Dùng AI để phản biện câu mô tả problem, metric và boundary. | Hữu ích để làm câu problem ngắn hơn và buộc phải nói rõ “đang làm gì / không làm gì”. | AI có xu hướng biến “anti-bot” thành solution statement quá sớm. | Tôi đổi framing thành “fair booking admission/allocation” và giữ root cause là vấn đề cần validation. |
| Rule / Workflow / Agent | Dùng AI để challenge xem bài toán có thực sự cần Agent hay không. | Hữu ích để so sánh Rule, Workflow và Agent theo độ mơ hồ, độ phức tạp, branching và risk. | AI có thể làm Agent nghe hấp dẫn hơn chỉ vì bài có yếu tố AI. | Tôi kết luận Agent không phù hợp: Rule xử lý case rõ, Workflow điều phối các bước, ML chỉ hỗ trợ risk scoring ở case mơ hồ. |
| Decision | Dùng AI để stress-test các metric, false positive risk, fallback và rollback conditions. | Hữu ích để phát hiện rằng solution chưa đủ production-ready vì thiếu server-side baseline. | AI vẫn có thể làm giải pháp trông “đã sẵn sàng” nếu chỉ nhìn vào design mà không nhìn vào data availability. | Tôi cùng nhóm chọn “Not Yet — pilot validation”, yêu cầu đo baseline và xác minh root cause trước khi triển khai AI thật. |

> Nếu phase nào không dùng AI, ghi `Không dùng` và vì sao tự làm.

---

## 3. Reflection câu hỏi mở

Chọn 3-4 câu trong 6 câu dưới để viết thành đoạn 8-12 câu (không trả lời bullet 1 dòng):
- Tôi học được gì khi nghe top 3 problems của các bạn khác?
- Nhóm có lúc nào bị solution-first, đòi làm Agent cho ngầu không?
- Tôi có thay đổi ý kiến sau khi bị challenge không, vì sao đổi?
- Tôi đóng góp gì thật sự vào artifact cuối, phần nào có dấu tay của tôi?
- Điều khó nhất khi viết Problem Statement là gì, metric hay boundary?
- Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

**Reflection:**

```text
Khi nghe top 3 problems của các bạn khác, tôi nhận ra một painpoint tốt không chỉ là vấn đề “nghe khó” mà phải có actor, workflow và cách đo rõ ràng. Điều tôi thay đổi nhiều nhất trong quá trình làm nhóm là cách nhìn về AI: ban đầu bài toán anti-bot rất dễ bị kéo sang hướng “dùng AI để chặn bot”, nhưng sau khi phân tích workflow tôi thấy phần lớn quyết định có thể xử lý bằng rule và workflow deterministic. Tôi cũng nhận ra evidence quan trọng hơn việc làm cho solution nghe thông minh; resident reviews cho thấy có pain, nhưng chưa đủ để khẳng định backend thực sự có bot exploit hay nguyên nhân khác như race condition hoặc allocation logic. Vì vậy tôi góp phần đổi cách diễn đạt từ một kết luận chắc chắn về bot thành một hypothesis cần được xác minh bằng booking/server logs. Phần khó nhất khi viết Problem Statement với tôi không phải là mô tả pain mà là đặt metric và boundary sao cho không overclaim. Chẳng hạn, các target như legitimate booking success ≥95% hay false-positive ≤2% chỉ có ý nghĩa sau khi có baseline production để so sánh. Tôi cũng thấy rõ vì sao không nên dùng Agent chỉ để “có AI”: bài toán có logic, điều kiện và nhánh xử lý tương đối rõ nên Workflow là mức phù hợp hơn, còn AI chỉ nên hỗ trợ những case hành vi mơ hồ. Nếu làm lại, tôi sẽ challenge nhóm sớm hơn về bằng chứng của root cause và yêu cầu lấy log hoặc validation thực tế trước khi đi quá sâu vào kiến trúc AI. Bài học lớn nhất của tôi là một solution tốt không phải solution có nhiều AI nhất, mà là solution dùng đúng mức công nghệ để giải quyết đúng bottleneck và vẫn có fallback an toàn khi AI sai.
```

---

## 4. Tự kiểm cuối bài (check trước khi nộp repo)

- [x] [12đ] Cá nhân có 5+ problems + top 3 Problem Cards
- [x] [12đ] Tôi đã pitch rõ + challenge nhóm đúng trọng tâm (ghi ở bảng mục 1)
- [x] Nhóm có nhật ký hội tụ từ candidates về 1 bài
- [x] [15đ] Nhóm có workflow trước/sau
- [x] [20đ] Nhóm có PS v0/v1 với metric + boundary rõ
- [x] [15đ] Nhóm có so sánh No AI / Rule / Workflow / Agent
- [x] [10đ] Nhóm có Go / Not Yet / No-Go + lý do rõ
- [x] [10đ] Reflection này có vai trò thật + AI giúp/sai ở đâu + điều học được + nếu làm lại đổi gì
- [x] [6đ] Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp AI
