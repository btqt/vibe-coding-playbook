Tôi cần mở rộng (scale) [system/application] để xử lý [target scale] trong khi vẫn duy trì [performance/reliability requirements]. Điều này đòi hỏi lập kế hoạch dung lượng (capacity planning) có hệ thống và sự phát triển kiến trúc.

TRẠNG THÁI HIỆN TẠI (CURRENT STATE):
- Kiến trúc hệ thống: [thiết kế hiện tại, nút thắt (bottlenecks), hạn chế mở rộng]
- Metrics Performance: [throughput hiện tại, thời gian phản hồi, sử dụng tài nguyên]
- Cơ sở hạ tầng: [servers, databases, caches, CDN, các công cụ monitoring]
- Cấu trúc chi phí: [chi phí vận hành hiện tại, chi phí cho mỗi người dùng/giao dịch]
- Khả năng Team: [chuyên môn ops, dung lượng on-call, mức độ trưởng thành tự động hóa]

CÁC MỤC TIÊU MỞ RỘNG (SCALING TARGETS):
- Timeline tăng trưởng: [khi nào bạn cần đạt đến quy mô mục tiêu, đường cong tăng trưởng]
- Metrics mục tiêu: [user, request/giây, khối lượng dữ liệu, phân bố địa lý]
- Yêu cầu Performance: [mục tiêu SLA ở quy mô lớn, suy giảm chấp nhận được]
- Ràng buộc chi phí: [giới hạn ngân sách, mục tiêu cost-per-user, yêu cầu ROI]
- Mục tiêu độ tin cậy: [SLA thời gian hoạt động, khôi phục thảm họa, yêu cầu multi-region]

CÁC THÁCH THỨC MỞ RỘNG (SCALING CHALLENGES):
- Nút thắt đã biết: [hạn chế hệ thống hiện tại, hạn chế tài nguyên]
- Thách thức dữ liệu: [mở rộng database, tính nhất quán dữ liệu, backup/khôi phục ở quy mô lớn]
- Thách thức vận hành: [monitoring, debugging, deployment ở quy mô lớn]
- Mở rộng Team: [nhu cầu tuyển dụng, phân phối kiến thức, tính bền vững on-call]

Vui lòng phát triển chiến lược mở rộng toàn diện:

1. PHÂN TÍCH NÚT THẮT (BOTTLENECK ANALYSIS):
   - Xác định các nút thắt hiện tại và dự kiến theo thứ tự tác động
   - Định lượng giới hạn mở rộng của từng component hệ thống
   - Xác định nút thắt nào thuộc về kiến trúc vs vận hành
   - Ưu tiên các nút thắt theo timeline và tác động business

2. KIẾN TRÚC MỞ RỘNG (SCALING ARCHITECTURE):
   - Chiến lược mở rộng ngang (Horizontal) vs dọc (vertical) cho từng component
   - Cách tiếp cận mở rộng Database (sharding, read replicas, chiến lược caching)
   - Phân tách Microservices nếu có lợi
   - Chiến lược CDN và edge computing
   - Cấu hình Auto-scaling và quản lý tài nguyên

3. PHÁT TRIỂN CƠ SỞ HẠ TẦNG (INFRASTRUCTURE EVOLUTION):
   - Chiến lược Cloud và deployment multi-region
   - Cân nhắc Container orchestration và service mesh
   - Load balancing và quản lý lưu lượng
   - Mở rộng lưu trữ và chiến lược lưu trữ dữ liệu
   - Lập kế hoạch dung lượng mạng và băng thông

4. MỞ RỘNG VẬN HÀNH (OPERATIONAL SCALING):
   - Monitoring và khả năng quan sát (observability) ở quy mô lớn
   - Phản ứng sự cố tự động và tự phục hồi (self-healing)
   - Tự động hóa Deployment và quy trình canary release
   - Lập kế hoạch dung lượng và tối ưu hóa chi phí
   - Cấu trúc Team và lập kế hoạch luân phiên on-call

5. LỘ TRÌNH THỰC HIỆN:
   - Cách tiếp cận theo giai đoạn với các cột mốc rõ ràng và tiêu chí thành công
   - Load testing và chiến lược xác thực cho mỗi giai đoạn
   - Đánh giá rủi ro và kế hoạch rollback
   - Timeline đầu tư và yêu cầu tài nguyên
   - Metrics thành công và dashboard monitoring

6. TỐI ƯU HÓA CHI PHÍ:
   - Mô hình hóa chi phí ở quy mô mục tiêu
   - Cơ hội tối ưu hóa tài nguyên
   - Chiến lược dung lượng dành riêng (Reserved capacity) vs theo yêu cầu (on-demand)
   - Giám sát chi phí và cảnh báo
   - Xác thực ROI và cập nhật trường hợp business

Thiết kế cho sự tăng trưởng bền vững duy trì độ tin cậy của hệ thống và sự tỉnh táo của team.
