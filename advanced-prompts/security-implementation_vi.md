Tôi cần thực hiện [security feature/requirement] trong một hệ thống production. Tôi cần bạn suy nghĩ thông qua việc này với tư duy ưu tiên bảo mật (security-first) và mô hình hóa mối đe dọa (threat modeling) toàn diện.

NGỮ CẢNH HỆ THỐNG (SYSTEM CONTEXT):
- Application: [loại ứng dụng, cơ sở người dùng, dữ liệu được xử lý]
- Tư thế bảo mật hiện tại (Current Security Posture): [auth hiện có, encryption, monitoring, compliance]
- Tech Stack: [frameworks, databases, cơ sở hạ tầng, dịch vụ bên thứ ba]
- Các yêu cầu Business: [SOC2, GDPR, HIPAA, PCI-DSS, đặc thù ngành]
- Môi trường mối đe dọa (Threat Environment): [các mối đe dọa nội bộ/bên ngoài, các vector tấn công mà bạn lo ngại]

YÊU CẦU BẢO MẬT (SECURITY REQUIREMENT):
[Mô tả chi tiết về khả năng bảo mật nào cần được thực hiện và tại sao]

NGỮ CẢNH BUSINESS (BUSINESS CONTEXT):
- Khả năng chấp nhận rủi ro: [hệ thống này quan trọng về mặt bảo mật như thế nào]
- Các ràng buộc về trải nghiệm người dùng: [mức độ ma sát chấp nhận được]
- Yêu cầu Performance: [độ trễ, các ràng buộc throughput]
- Các ràng buộc vận hành: [chuyên môn bảo mật của team, ngân sách, timeline]

Vui lòng cung cấp chiến lược thực hiện bảo mật toàn diện:

1. MÔ HÌNH MỐI ĐE DỌA (THREAT MODEL):
   - Việc thực hiện này giải quyết những mối đe dọa cụ thể nào?
   - Những vector tấn công nào vẫn chưa được giải quyết?
   - Các tác động business/kỹ thuật là gì nếu biện pháp bảo mật này thất bại?
   - Mô hình bảo mật này đang đưa ra những giả định nào?

2. THIẾT KẾ BẢO MẬT (SECURITY DESIGN):
   - Các lớp phòng thủ chuyên sâu (Defense-in-depth) và cách chúng tương tác
   - Mô hình Authentication/authorization
   - Chiến lược bảo vệ dữ liệu (at rest, in transit, in use)
   - Chiến lược quản lý và xoay vòng Key
   - Các chính sách quản lý Session và timeout
   - Cách tiếp cận Input validation và output encoding

3. CÁCH TIẾP CẬN THỰC HIỆN:
   - Các thư viện/framework bảo mật để sử dụng và tại sao (tránh tự tạo crypto của riêng bạn)
   - Quản lý cấu hình (Configuration management) cho các cài đặt bảo mật
   - Chiến lược quản lý Secrets
   - Quản lý và gia hạn Certificate
   - Cấu hình bảo mật Database
   - Các yêu cầu bảo mật Network

4. CHIẾN LƯỢC XÁC THỰC (VALIDATION STRATEGY):
   - Cách tiếp cận Unit testing cho code bảo mật
   - Integration testing cho các luồng auth
   - Các công cụ và kỹ thuật Security testing
   - Kế hoạch Penetration testing hoặc review bảo mật
   - Checklist xác minh Compliance

5. BẢO MẬT VẬN HÀNH (OPERATIONAL SECURITY):
   - Logging và monitoring cho các sự kiện bảo mật
   - Quy trình phản ứng sự cố (Incident response)
   - Các metrics bảo mật và cảnh báo (alerting)
   - Các cân nhắc về Backup và khôi phục thảm họa (disaster recovery)
   - Tài liệu bảo mật và nhu cầu đào tạo team

6. CHIẾN LƯỢC ROLLOUT:
   - Cách tiếp cận Deployment (blue-green, canary, feature flags)
   - Quy trình Rollback nếu phát hiện sự cố bảo mật
   - Truyền thông người dùng về các thay đổi bảo mật
   - Các bước xác minh sau deployment

Ưu tiên hiệu quả bảo mật hơn sự tiện lợi, nhưng giải thích rõ ràng các sự đánh đổi (trade-offs).
