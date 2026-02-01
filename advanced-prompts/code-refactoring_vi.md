Tôi có [component/module/system] cần refactoring đáng kể để cải thiện [maintainability/performance/testability]. Tôi cần một cách tiếp cận có hệ thống giúp duy trì chức năng trong khi cải thiện chất lượng code.

PHÂN TÍCH CODE (CODE ANALYSIS):
- Codebase hiện tại: [kích thước, độ phức tạp, ngôn ngữ/framework, tuổi thọ]
- Các vấn đề cụ thể: [code smells, nút thắt performance, khoảng trống test coverage]
- Mức độ quan trọng Business: [tác động đến người dùng nếu có lỗi, yêu cầu SLA]
- Tần suất thay đổi: [mức độ thường xuyên code này được sửa đổi, bởi ai]
- Dependencies: [các hệ thống/module khác phụ thuộc vào code này]

MỤC TIÊU REFACTORING:
- Mục tiêu chính: [cụ thể cần cải thiện cái gì và bao nhiêu]
- Metrics chất lượng: [hiện tại vs mục tiêu: cyclomatic complexity, test coverage, performance]
- Mục tiêu Maintainability: [giảm thời gian onboarding, tăng tốc độ phát triển]
- Các hạng mục Technical Debt: [các món nợ cụ thể cần giải quyết]

CÁC RÀNG BUỘC (CONSTRAINTS):
- Timeline: [thời gian có sẵn cho công việc refactoring]
- Tài nguyên Team: [ai có thể làm việc này, cấp độ kỹ năng của họ]
- Khả năng chấp nhận rủi ro: [rủi ro chấp nhận được khi tạo ra lỗi]
- Deployment: [bạn có thể phát hành tăng dần hay cần phát hành một lần (big bang)]

Vui lòng cung cấp chiến lược refactoring có hệ thống:

1. ĐÁNH GIÁ CHẤT LƯỢNG CODE:
   - Xác định các vi phạm tồi tệ nhất (độ phức tạp cao, test coverage thấp, nguồn lỗi thường xuyên)
   - Ưu tiên các mục tiêu refactoring theo tác động vs nỗ lực
   - Xác định các metrics chất lượng cụ thể để theo dõi sự cải thiện
   - Thiết lập các phép đo baseline để so sánh

2. CÁCH TIẾP CẬN REFACTORING:
   - Chia nhỏ refactoring thành các bước an toàn, tăng dần
   - Xác định các ranh giới tự nhiên cho các cải tiến tăng dần
   - Xác định các pattern refactoring nào áp dụng (Extract Method, Replace Conditional with Polymorphism, v.v.)
   - Lên kế hoạch trình tự để giảm thiểu rủi ro và duy trì chức năng

3. CHIẾN LƯỢC TESTING:
   - Cách tiếp cận Characterization testing cho legacy code
   - Chiến lược Unit testing cho các component được refactor
   - Integration testing để đảm bảo hành vi hệ thống không thay đổi
   - Performance testing nếu hiệu suất là mối quan tâm
   - Chiến lược Regression testing

4. KẾ HOẠCH THỰC HIỆN:
   - Trình tự refactoring từng bước
   - Các điểm kiểm tra (Checkpoints) để validate và review
   - Kế hoạch Rollback nếu phát hiện sự cố
   - Chiến lược Code review cho mỗi phần tăng thêm
   - Thu thập metrics và theo dõi tiến độ

5. QUALITY GATES:
   - Các kiểm tra chất lượng tự động để ngăn chặn sự thoái lui (regression)
   - Performance benchmarks cần duy trì
   - Các ngưỡng Code coverage
   - Các quy tắc và ngưỡng Static analysis
   - Định nghĩa "done" cho mỗi phần refactoring tăng thêm

6. CHUYỂN GIAO KIẾN THỨC:
   - Cần cập nhật Documentation
   - Giáo dục Team về các pattern/cách tiếp cận mới
   - Cải tiến Onboarding cho các thành viên mới trong team
   - Cập nhật các tiêu chuẩn Coding dựa trên các bài học refactoring

Tập trung vào sự cải thiện có thể đo lường được trong khi giảm thiểu rủi ro business.
