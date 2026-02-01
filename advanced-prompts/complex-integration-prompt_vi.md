Tôi cần thiết kế một tích hợp giữa [System A] và [System B] để xử lý [business use case]. Đây là một tích hợp phức tạp cần độ tin cậy và khả năng bảo trì cấp doanh nghiệp (enterprise-grade).

NGỮ CẢNH TÍCH HỢP (INTEGRATION CONTEXT):
- System A: [công nghệ, định dạng dữ liệu, khả năng API, hạn chế, SLA]
- System B: [công nghệ, định dạng dữ liệu, khả năng API, hạn chế, SLA]
- Quy trình Business: [quy trình làm việc chi tiết mà tích hợp này cho phép]
- Khối lượng dữ liệu: [bản ghi mỗi ngày/giờ, tải cao điểm, biến động theo mùa]
- Yêu cầu độ trễ (Latency Requirements): [real-time, near real-time, chấp nhận batch]

CÁC RÀNG BUỘC KỸ THUẬT (TECHNICAL CONSTRAINTS):
- Hạn chế System A: [giới hạn tốc độ API (API rate limits), xác thực (authentication), hạn chế định dạng dữ liệu]
- Hạn chế System B: [giới hạn tốc độ API (API rate limits), xác thực (authentication), hạn chế định dạng dữ liệu]
- Mạng (Network): [băng thông, vùng bảo mật, quy tắc tường lửa, độ trễ]
- Cơ sở hạ tầng (Infrastructure): [nền tảng có sẵn, hạn chế deployment]
- Compliance: [cư trú dữ liệu, mã hóa, yêu cầu audit trail]

YÊU CẦU VỀ ĐỘ TIN CẬY (RELIABILITY REQUIREMENTS):
- Availability SLA: [yêu cầu uptime, cửa sổ downtime chấp nhận được]
- Data Consistency: [eventual consistency chấp nhận được hay cần strong consistency]
- Xử lý lỗi (Error Handling): [cách xử lý lỗi một phần, xung đột dữ liệu]
- Phục hồi (Recovery): [yêu cầu RTO/RPO, chiến lược backup]

Vui lòng thiết kế một giải pháp tích hợp toàn diện:

1. KIẾN TRÚC TÍCH HỢP (INTEGRATION ARCHITECTURE):
   - Mẫu tổng thể (point-to-point, hub-and-spoke, event-driven, API gateway)
   - Thiết kế luồng dữ liệu (Data flow design) với các điểm chuyển đổi rõ ràng
   - Xử lý lỗi và logic thử lại (retry logic)
   - Quản lý trạng thái và ranh giới giao dịch (transaction boundaries)
   - Chiến lược giám sát (monitoring) và khả năng quan sát (observability)

2. CHIẾN LƯỢC DỮ LIỆU (DATA STRATEGY):
   - Cách tiếp cận ánh xạ (mapping) và chuyển đổi dữ liệu
   - Chiến lược phát triển schema và versioning
   - Validation dữ liệu và kiểm tra chất lượng
   - Giải quyết xung đột cho các cập nhật đồng thời
   - Chính sách lưu trữ và lưu giữ dữ liệu

3. THỰC HIỆN ĐỘ TIN CẬY (RELIABILITY IMPLEMENTATION):
   - Cấu hình Circuit breaker và timeout
   - Quản lý Hàng đợi (Queue)/bộ đệm (buffer) để cân bằng tải (load leveling)
   - Dead letter queue và xử lý tin nhắn độc (poison message)
   - Idempotency và phát hiện trùng lặp
   - Suy giảm nhẹ nhàng (Graceful degradation) khi các dependency bị lỗi

4. CÁC CÂN NHẮC VẬN HÀNH (OPERATIONAL CONSIDERATIONS):
   - Chiến lược Deployment và rollout
   - Quản lý cấu hình (Configuration management)
   - Giám sát (Monitoring), cảnh báo (alerting), và theo dõi SLA
   - Cách tiếp cận khắc phục sự cố (Troubleshooting) và gỡ lỗi (debugging)
   - Performance testing và lập kế hoạch dung lượng (capacity planning)

5. CÁC KỊCH BẢN LỖI VÀ PHẢN HỒI (FAILURE SCENARIOS AND RESPONSES):
   Đối với mỗi kịch bản lỗi nghiêm trọng, hãy xác định:
   - Cơ chế phát hiện
   - Phản hồi tự động
   - Quy trình can thiệp thủ công
   - Tác động Business và kế hoạch truyền thông

6. CHIẾN LƯỢC PHÁT TRIỂN (EVOLUTION STRATEGY):
   - Cách xử lý các thay đổi API trong các hệ thống nguồn
   - Cách tiếp cận mở rộng (Scaling approach) khi khối lượng dữ liệu tăng lên
   - Thêm các hệ thống mới vào mẫu tích hợp
   - Lộ trình Migration cho các thay đổi nền tảng tích hợp

Thiết kế cho độ tin cậy cấp production ngay từ ngày đầu tiên.
