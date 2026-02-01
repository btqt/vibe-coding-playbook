Tôi cần hiện đại hóa [legacy system description] trong khi vẫn duy trì tính liên tục của kinh doanh (business continuity). Điều này đòi hỏi cách tiếp cận cẩn thận của một người đã di chuyển (migrate) thành công nhiều hệ thống legacy.

PHÂN TÍCH HỆ THỐNG LEGACY (LEGACY SYSTEM ANALYSIS):
- Hệ thống hiện tại: [technology stack, kiến trúc, tuổi thọ, độ phức tạp]
- Mức độ quan trọng Business: [tác động doanh thu, số lượng người dùng, yêu cầu SLA]
- Technical Debt: [các điểm đau cụ thể, gánh nặng bảo trì, các vấn đề đã biết]
- Trạng thái tài liệu: [những gì tồn tại, những gì còn thiếu, kiến thức bộ lạc (tribal knowledge)]
- Kiến thức Team: [ai hiểu hệ thống, rủi ro chuyển giao kiến thức]

CÁC ĐỘNG LỰC HIỆN ĐẠI HÓA (MODERNIZATION DRIVERS):
- Động lực chính: [chi phí, hiệu suất, khả năng bảo trì, bảo mật, tuân thủ (compliance)]
- Timeline Business: [deadline bên ngoài, các ràng buộc theo mùa]
- Khả năng chấp nhận rủi ro: [thời gian chết chấp nhận được, yêu cầu rollback]
- Tiêu chí thành công: [cần cải thiện cụ thể có thể đo lường được]

CÁC RÀNG BUỘC VÀ YÊU CẦU:
- Dữ liệu: [khối lượng, độ phức tạp di chuyển, yêu cầu toàn vẹn]
- Tích hợp: [các hệ thống khác, API, file feeds phụ thuộc vào cái này]
- Compliance: [audit trails, yêu cầu quy định trong quá trình chuyển đổi]
- Team: [tài nguyên sẵn có, kỹ năng hỗn hợp, nhu cầu đào tạo]
- Budget: [chi phí phát triển, cơ sở hạ tầng, tài nguyên bên ngoài]

TẦM NHÌN MỤC TIÊU (TARGET VISION):
- Trạng thái cuối mong muốn: [technology stack mới, kiến trúc, khả năng]
- Các yêu cầu không thể thương lượng: [các tính năng phải có, mục tiêu hiệu suất]
- Các cải tiến Nice-to-have: [các tính năng thêm giá trị nhưng không quan trọng]

Vui lòng thiết kế chiến lược hiện đại hóa toàn diện:

1. PHÂN TÍCH CHIẾN LƯỢC MIGRATION:
   So sánh các cách tiếp cận này cho tình huống cụ thể này:
   - Strangler Fig Pattern (thay thế dần dần)
   - Big Bang Migration (viết lại hoàn toàn)
   - Hybrid Approach (lift-and-shift sau đó hiện đại hóa)
   - Event-Driven Migration (thông qua event streaming)
   
   Đối với mỗi cách tiếp cận, phân tích: mức độ rủi ro, timeline, yêu cầu tài nguyên, gián đoạn business, độ phức tạp kỹ thuật.

2. CÁCH TIẾP CẬN ĐƯỢC KHUYẾN NGHỊ với lý do chi tiết:
   - Phân chia giai đoạn với các cột mốc rõ ràng
   - Chiến lược vận hành song song (cách hệ thống cũ và mới cùng tồn tại)
   - Chiến lược đồng bộ hóa dữ liệu trong quá trình chuyển đổi
   - Cách tiếp cận xác thực Feature parity
   - Kế hoạch so sánh và benchmarking hiệu suất

3. CHIẾN LƯỢC GIẢM THIỂU RỦI RO:
   - Rủi ro kỹ thuật và kế hoạch giảm thiểu
   - Kế hoạch liên tục business trong quá trình migration
   - Chiến lược Rollback cho mỗi giai đoạn
   - Kế hoạch truyền thông cho các bên liên quan (stakeholders)
   - Lập kế hoạch tài nguyên dự phòng (contingency resource planning)

4. LỘ TRÌNH THỰC HIỆN:
   - Timeline chi tiết với các phụ thuộc
   - Kế hoạch mở rộng team và phát triển kỹ năng
   - Cung cấp cơ sở hạ tầng và testing
   - Phối hợp với nhà cung cấp bên thứ ba nếu cần
   - Tiêu chí Go-live và xác thực thành công

5. CHUYỂN GIAO KIẾN THỨC VÀ TÀI LIỆU:
   - Kế hoạch khôi phục tài liệu hệ thống legacy
   - Trích xuất kiến thức từ nhân sự chủ chốt
   - Chiến lược tài liệu hệ thống mới
   - Kế hoạch đào tạo và onboarding cho team

Tập trung vào việc giảm thiểu rủi ro business trong khi đạt được các mục tiêu hiện đại hóa.
