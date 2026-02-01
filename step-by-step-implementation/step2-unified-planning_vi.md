# Universal Planning-First Template

## Cấu Trúc Prompt Planning Cốt Lõi

```xml
<planning_request>
  <objective>
    PLAN FIRST: Tạo [feature/system description] mà [specific requirements]
  </objective>
  
  <context>
    <tech_stack>
      - Framework: [Next.js/React/Vue/Angular]
      - Language: [TypeScript/JavaScript/Python]
      - Database: [PostgreSQL/MongoDB/MySQL]
      - State Management: [Redux/Zustand/Context]
      - Authentication: [NextAuth/Auth0/Custom]
      - Styling: [Tailwind/Styled Components/CSS Modules]
    </tech_stack>
    
    <existing_patterns>
      - API Structure: [các pattern REST/GraphQL/tRPC]
      - Component Architecture: [tham chiếu các components hiện có]
      - Database Schema: [tham chiếu các models hiện có]
      - Error Handling: [tham chiếu các pattern lỗi]
      - Testing Strategy: [tham chiếu các pattern test]
    </existing_patterns>
    
    <performance_requirements>
      - Response Time: [các mục tiêu cụ thể bằng mili giây]
      - Throughput: [số yêu cầu mỗi giây]
      - Concurrent Users: [tối đa dự kiến]
      - Data Volume: [kỳ vọng về kích thước và tăng trưởng]
    </performance_requirements>
    
    <security_considerations>
      - Authentication: [các cấp độ xác thực bắt buộc]
      - Authorization: [nhu cầu kiểm soát truy cập dựa trên vai trò]
      - Data Sensitivity: [xử lý dữ liệu PII/financial/health]
      - Compliance: [các yêu cầu GDPR/HIPAA/SOX]
    </security_considerations>
  </context>
  
  <constraints>
    - Phải tuân theo [loại pattern] hiện có trong [file tham chiếu/component]
    - Không được sửa đổi [các file/hệ thống/API cụ thể]
    - Phải xử lý [các trường hợp lỗi cụ thể/điều kiện biên]
    - Nên tích hợp với [các hệ thống hiện có/dịch vụ bên thứ ba]
    - Các ràng buộc ngân sách: [hạn chế về cơ sở hạ tầng/thời gian]
    - Timeline: [các deadline giao hàng và các mốc quan trọng]
  </constraints>
  
  <requirements>
    <functional>
      1. [Yêu cầu chức năng cụ thể với các tiêu chí chấp nhận]
      2. [Yêu cầu tương tác người dùng với các thông số kỹ thuật UX]
      3. [Yêu cầu Business logic với các quy tắc validation]
      4. [Yêu cầu tích hợp với các hệ thống bên ngoài]
    </functional>
    
    <non_functional>
      1. [Yêu cầu Performance với các số liệu cụ thể]
      2. [Yêu cầu Scalability với các dự báo tăng trưởng]
      3. [Yêu cầu Security với các tiêu chuẩn tuân thủ]
      4. [Yêu cầu Reliability với các mục tiêu thời gian hoạt động]
    </non_functional>
  </requirements>
  
  <deliverables>
    Vui lòng tạo một đặc tả kỹ thuật toàn diện bao gồm:
    - Sơ đồ kiến trúc hệ thống với các tương tác component
    - Các định nghĩa giao diện API với các schemas request/response
    - Các thay đổi Database schema với các chiến lược migration
    - Chi tiết thực hiện Security với mô hình hóa mối đe dọa (threat modeling)
    - Chiến lược Error handling với các cân nhắc về trải nghiệm người dùng
    - Cách tiếp cận Testing với các yêu cầu về độ bao phủ
    - Chiến lược tối ưu hóa Performance với kế hoạch giám sát
    - Các cân nhắc về Deployment với tích hợp CI/CD
  </deliverables>
  
  <approval_gate>
    CHỜ SỰ CHẤP THUẬN RÕ RÀNG CỦA TÔI TRƯỚC KHI THỰC HIỆN BẤT KỲ CODE NÀO.
    
    Tôi sẽ xem xét và phê duyệt:
    - Kiến trúc tổng thể và các quyết định thiết kế
    - Database schema và chiến lược migration
    - Các hợp đồng API và các điểm tích hợp
    - Cách tiếp cận thực hiện Security
    - Chiến lược Testing và kế hoạch bao phủ
  </approval_gate>
</planning_request>
```

## Các Ví Dụ Planning Trong Thế Giới Thực

### Template Phát Triển Feature
```xml
<feature_planning>
  <feature_definition>
    - Feature Name: Hệ thống xác thực người dùng
    - User Story: Là một người dùng, tôi muốn đăng nhập/đăng xuất an toàn để dữ liệu của tôi được bảo vệ
    - Business Value: Giảm 40% vé hỗ trợ, cho phép cá nhân hóa
    - Success Metrics: Thời gian đăng nhập <2s, thời gian hoạt động >99.9%, không có sự cố bảo mật
    - Priority: Cao (chặn các tính năng khác)
  </feature_definition>
  
  <technical_specification>
    <data_model>
      - Các thực thể mới: User, Session, RefreshToken
      - Các thực thể được sửa đổi: Phần mở rộng hồ sơ người dùng hiện có
      - Các mối quan hệ: User -> Sessions (1:nhiều), User -> RefreshTokens (1:nhiều)
      - Các quy tắc Validation: Định dạng Email, độ phức tạp của password, session timeout
      - Chiến lược Migration: Backfill người dùng hiện có với các mặc định an toàn
    </data_model>
    
    <api_design>
      - Các Endpoint mới: POST /auth/login, POST /auth/logout, POST /auth/refresh
      - Request Schemas: LoginRequest, RefreshRequest
      - Response Schemas: AuthResponse với tokens và dữ liệu người dùng
      - Security: Rate limiting, bảo vệ CSRF, secure cookies
      - Versioning: API v1 với kế hoạch tương thích ngược
    </api_design>
    
    <frontend_architecture>
      - Các Component mới: LoginForm, AuthProvider, ProtectedRoute
      - Quản lý State: Auth context với lưu trữ liên tục
      - Luồng người dùng: Login -> Dashboard với các trạng thái loading
      - Responsive: Thiết kế mobile-first với các điểm chạm
      - Accessibility: Tuân thủ WCAG 2.1 AA với trình đọc màn hình
    </frontend_architecture>
  </technical_specification>
  
  <implementation_phases>
    <phase_1 name="Foundation" duration="2 ngày">
      - Database schema và migrations
      - Các endpoint API xác thực cốt lõi
      - Xử lý JWT token cơ bản
      - Unit tests cho logic xác thực
    </phase_1>
    
    <phase_2 name="Frontend Integration" duration="2 ngày">
      - Các UI component Login/logout
      - Quản lý Auth state
      - Thực hiện Protected route
      - Integration tests
    </phase_2>
    
    <phase_3 name="Security Hardening" duration="1 ngày">
      - Thực hiện Rate limiting
      - Cấu hình Security header
      - Quét lỗ hổng bảo mật
      - Load testing
    </phase_3>
  </implementation_phases>
</feature_planning>
```

### Template Debugging
```xml
<debugging_analysis>
  <problem_scope>
    - Vấn đề: Các phản hồi API không liên tục trả về lỗi 500
    - Tần suất: 15% các yêu cầu trong giờ cao điểm (2PM-4PM EST)
    - Tác động: Sự thất vọng của người dùng, khả năng mất dữ liệu, vé hỗ trợ
    - Chi phí Business: $2K/giờ doanh thu bị mất
    - Các hệ thống bị ảnh hưởng: User dashboard, xử lý thanh toán, báo cáo
  </problem_scope>
  
  <investigation_strategy>
    <hypothesis_ranking>
      1. Cạn kiệt Database connection pool (70% khả năng)
         - Bằng chứng: Tương quan với lưu lượng truy cập cao điểm
         - Điều tra: Kiểm tra các số liệu connection pool
      
      2. Memory leak trong ứng dụng server (20% khả năng)
         - Bằng chứng: Suy giảm hiệu suất dần dần
         - Điều tra: Lập hồ sơ bộ nhớ trong khoảng thời gian 24 giờ
      
      3. Timeout dependency API bên ngoài (10% khả năng)
         - Bằng chứng: Một số lỗi đề cập đến các dịch vụ bên thứ ba
         - Điều tra: Xem xét thời gian phản hồi của API bên ngoài
    </hypothesis_ranking>
    
    <investigation_plan>
      - Ngay lập tức: Bật ghi log lỗi chi tiết với ID yêu cầu
      - Ngắn hạn: Triển khai dashboard giám sát cho các số liệu thời gian thực
      - Nguyên nhân gốc rễ: Kiểm tra có hệ thống từng giả thuyết
      - Timeline: 4 giờ để xác định, 8 giờ để sửa chữa
    </investigation_plan>
  </investigation_strategy>
  
  <solution_approach>
    <immediate_mitigation>
      - Thực hiện ngắt mạch (circuit breaker) cho các API bên ngoài
      - Thêm hàng đợi yêu cầu với xử lý tràn
      - Triển khai khả năng rollback khẩn cấp
    </immediate_mitigation>
    
    <permanent_solution>
      - Tối ưu hóa các query cơ sở dữ liệu và connection pooling
      - Thực hiện lớp caching cho các yêu cầu thường xuyên
      - Thêm giám sát và cảnh báo toàn diện
    </permanent_solution>
  </solution_approach>
</debugging_analysis>
```

## Framework Xác Thực Planning

### Checklist Trước Khi Thực Hiện
- [ ] Cách tiếp cận kỹ thuật phù hợp với các architectural patterns đã thiết lập
- [ ] Tất cả các yêu cầu business được giải quyết với các tiêu chí chấp nhận có thể đo lường được
- [ ] Các cân nhắc về Performance và scalability được lên kế hoạch rõ ràng
- [ ] Các tác động Security được phân tích kỹ lưỡng với mô hình hóa mối đe dọa
- [ ] Chiến lược Error handling bao gồm cả các trường hợp dự kiến và biên
- [ ] Chiến lược Testing bao gồm độ bao phủ unit, integration, và end-to-end
- [ ] Các giai đoạn thực hiện là hợp lý và có thể quản lý được
- [ ] Các chiến lược giảm thiểu rủi ro giải quyết các thách thức kỹ thuật đã xác định
- [ ] Yêu cầu tài nguyên là thực tế và sẵn có
- [ ] Timeline tính đến độ phức tạp, các phụ thuộc, và testing

### Các Câu Hỏi Approval Gate
1. **Architecture**: Giải pháp này có phù hợp với chiến lược kỹ thuật dài hạn của chúng ta không?
2. **Scalability**: Điều này sẽ hoạt động như thế nào dưới tải gấp 10 lần hiện tại?
3. **Security**: Các vector tấn công tiềm năng và các biện pháp giảm thiểu là gì?
4. **Maintainability**: Nhóm của chúng ta có thể hỗ trợ điều này hiệu quả trong dài hạn không?
5. **Integration**: Điều này tác động như thế nào đến các hệ thống và quy trình làm việc hiện có?
