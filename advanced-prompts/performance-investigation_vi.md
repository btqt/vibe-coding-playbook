Tôi có vấn đề về performance trong [system/application] cần điều tra một cách có hệ thống. Hãy hành động như một senior performance engineer và giúp tôi chẩn đoán việc này một cách đúng đắn.

CÁC TRIỆU CHỨNG PERFORMANCE (PERFORMANCE SYMPTOMS):
- Hành vi quan sát được: [những gì người dùng/monitoring đang thấy]
- Các metrics cụ thể: [thời gian phản hồi, throughput, tỷ lệ lỗi với các con số thực tế]
- Khi nào nó xảy ra: [các mẫu lưu lượng truy cập, thời gian trong ngày, hành động cụ thể của người dùng]
- Các component bị ảnh hưởng: [những phần nào của hệ thống hiển thị vấn đề]
- Những thay đổi gần đây: [các deployment, thay đổi config, thay đổi dữ liệu trong 2 tuần qua]

NGỮ CẢNH HỆ THỐNG (SYSTEM CONTEXT):
- Kiến trúc: [microservices/monolith, các component chính]
- Tech Stack: [ngôn ngữ, frameworks, databases, các lớp cache]
- Cơ sở hạ tầng (Infrastructure): [nhà cung cấp cloud, các loại instance, thiết lập network]
- Quy mô (Scale): [yêu cầu/giây, khối lượng dữ liệu, số lượng người dùng]
- Giám sát (Monitoring): [các công cụ hiện có như DataDog, New Relic, custom dashboards]

CÁC RÀNG BUỘC ĐIỀU TRA (INVESTIGATION CONSTRAINTS):
- Hạn chế debugging trong production: [những gì tôi có thể/không thể làm trong prod]
- Các môi trường có sẵn: [staging, dev environments và độ trung thực của chúng so với prod]
- Áp lực thời gian: [đây là sự cố ngừng hoạt động nghiêm trọng hay hạng mục điều tra]
- Tài nguyên team: [ai có thể giúp đỡ, mức độ chuyên môn của họ]

Vui lòng cung cấp kế hoạch điều tra có hệ thống:

1. HÌNH THÀNH GIẢ THUYẾT (HYPOTHESIS FORMATION): Dựa trên các triệu chứng và ngữ cảnh, top 3 nguyên nhân gốc rễ có khả năng nhất là gì, được xếp hạng theo xác suất? Đối với mỗi giả thuyết, hãy giải thích lý do của bạn và bằng chứng nào sẽ chứng minh/bác bỏ nó.

2. TRÌNH TỰ ĐIỀU TRA (INVESTIGATION SEQUENCE): Cách tiếp cận debugging từng bước, được ưu tiên bởi:
   - Những cuộc điều tra nào có thể chạy song song
   - Công cụ/query/test nào để sử dụng cho mỗi bước
   - Thời gian đầu tư dự kiến cho mỗi cuộc điều tra
   - Mức độ rủi ro của mỗi kỹ thuật điều tra

3. CHIẾN LƯỢC THU THẬP DỮ LIỆU (DATA COLLECTION STRATEGY):
   - Các metrics chính cần nắm bắt và cách nắm bắt chúng
   - Các yêu cầu Logging/tracing
   - Cách tiếp cận Load testing nếu cần
   - Thiết lập Baseline để so sánh

4. CÁC CÁCH TIẾP CẬN GIẢI QUYẾT (RESOLUTION APPROACHES): Đối với mỗi nguyên nhân gốc rễ có khả năng, hãy phác thảo:
   - Các chiến lược giảm thiểu ngay lập tức (các giải pháp tạm thời để giảm tác động)
   - Cách tiếp cận thực hiện sửa lỗi đúng đắn
   - Chiến lược Testing để validate các sửa lỗi
   - Chiến lược Deployment cho các sửa lỗi

5. CHIẾN LƯỢC PHÒNG NGỪA (PREVENTION STRATEGY): Làm thế nào để ngăn chặn loại vấn đề này trong tương lai thông qua monitoring, testing, hoặc các thay đổi architectural

Bắt đầu với kế hoạch điều tra - đừng nhảy đến các giải pháp cho đến khi chúng ta có dữ liệu.
