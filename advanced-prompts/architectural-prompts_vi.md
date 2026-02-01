Tôi cần đưa ra quyết định kiến trúc quan trọng cho [project/system description]. Trước khi đề xuất bất kỳ giải pháp nào, tôi cần bạn suy nghĩ thông qua việc này một cách có hệ thống giống như một senior architect.

TÌNH HÌNH HIỆN TẠI (CURRENT SITUATION):
- System: [mô tả hệ thống hiện tại]
- Scale: [số lượng người dùng, lưu lượng truy cập, khối lượng dữ liệu]
- Tech Stack: [các công nghệ hiện tại]
- Team Size: [số lượng kỹ sư, cấp độ kinh nghiệm]
- Timeline: [deadline dự án, các ràng buộc]
- Budget: [các ràng buộc chi phí, ngân sách vận hành]

TUYÊN BỐ VẤN ĐỀ (PROBLEM STATEMENT):
[Mô tả chi tiết về vấn đề bao gồm các triệu chứng, tác động đến người dùng/business, và tại sao giải pháp hiện tại không hoạt động]

CÁC RÀNG BUỘC BUSINESS (BUSINESS CONSTRAINTS):
- Performance requirements: [SLA cụ thể, thời gian phản hồi, nhu cầu throughput]
- Availability requirements: [SLA uptime, cửa sổ bảo trì]
- Security/Compliance: [các yêu cầu cụ thể như SOC2, GDPR, HIPAA]
- Scalability targets: [dự báo tăng trưởng, kịch bản tải cao điểm]
- Integration requirements: [các hệ thống hiện có phải tích hợp]

CÁC RÀNG BUỘC KỸ THUẬT (TECHNICAL CONSTRAINTS):
- Không thể thay đổi: [hệ thống, database, giao thức không thể thay đổi]
- Phải duy trì: [tương thích ngược, tính toàn vẹn dữ liệu, các API hiện có]
- Team expertise: [công nghệ nhóm biết vs không biết]
- Infrastructure: [nhà cung cấp cloud, các ràng buộc on-prem, networking]

Vui lòng phân tích tình huống này và cung cấp:

1. PHÂN TÍCH VẤN ĐỀ (PROBLEM ANALYSIS): Chia nhỏ các nguyên nhân gốc rễ và xác định loại vấn đề kiến trúc này là gì (scalability, complexity, performance, maintainability, v.v.)

2. CÁC TÙY CHỌN GIẢI PHÁP (SOLUTION OPTIONS): Trình bày 3 phương pháp kiến trúc khác nhau, mỗi phương pháp có:
   - Phương pháp thiết kế cấp cao
   - Các lựa chọn công nghệ chính và tại sao
   - Độ phức tạp thực hiện (thang điểm 1-10)
   - Timeline ước tính và yêu cầu nhóm
   - Đánh giá rủi ro và chiến lược giảm thiểu
   - Các tác động bảo trì dài hạn
   - Phân tích chi phí sơ bộ (phát triển + vận hành)

3. KHUYẾN NGHỊ (RECOMMENDATION): Lựa chọn hàng đầu của bạn với lý do chi tiết bao gồm:
   - Tại sao phương pháp này phù hợp nhất với các ràng buộc
   - Chiến lược Migration/thực hiện
   - Các Success metrics và phương pháp giám sát
   - Các điểm thất bại tiềm năng và kế hoạch dự phòng

4. KHUNG QUYẾT ĐỊNH (DECISION FRAMEWORK): Các câu hỏi tôi nên hỏi các bên liên quan (stakeholders) để xác thực phương pháp này

Không bắt đầu thực hiện cho đến khi tôi đã xem xét và phê duyệt định hướng kiến trúc.
