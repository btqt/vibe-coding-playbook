# Thực Hiện Các Vòng Lặp Xác Minh (Verification Loops) Ưu Tiên Chất Lượng

### Template Prompt Xác Minh Master

Sử dụng prompt này sau mỗi lần tạo code bằng AI để thiết lập xác minh có hệ thống:

```
GIAO THỨC XÁC MINH (VERIFICATION PROTOCOL): Review code bạn vừa tạo thông qua ba lớp hệ thống

LỚP 1 - XÁC MINH KỸ THUẬT NGAY LẬP TỨC (IMMEDIATE TECHNICAL VERIFICATION):
Chạy các kiểm tra này và báo cáo kết quả:

1. KIỂM TRA SYNTAX & TYPE:
   - Có lỗi TypeScript/syntax nào không?
   - Tất cả các import có được giải quyết chính xác không?
   - Có bất kỳ type `any` nào nên được khai báo rõ ràng không?
   - Tất cả các hàm có return type thích hợp không?

2. PHÂN TÍCH CHẤT LƯỢNG CODE:
   - Code có tuân theo các pattern dự án hiện có không?
   - Có bất kỳ code smell nào không (hàm dài, code lặp lại, câu điều kiện phức tạp)?
   - Xử lý lỗi (error handling) có toàn diện và nhất quán không?
   - Tất cả các edge case có được xử lý thích hợp không?

3. VALIDATION TÍCH HỢP:
   - Điều này có tích hợp đúng cách với các component hiện có không?
   - Tất cả các dependencies có được import và sử dụng đúng cách không?
   - Liệu điều này có phá vỡ bất kỳ chức năng hiện có nào không?
   - Có bất kỳ vấn đề phụ thuộc vòng (circular dependency) nào không?

LỚP 2 - XÁC MINH CHỨC NĂNG (FUNCTIONAL VERIFICATION):
Phân tích business logic và chức năng:

1. ĐÁP ỨNG YÊU CẦU:
   - Việc thực hiện có đáp ứng tất cả các yêu cầu đã nêu không?
   - Có bất kỳ tính năng bị thiếu hoặc edge case nào không?
   - Hành vi có chính xác cho tất cả các kịch bản đầu vào không?
   - Các thông báo lỗi có thân thiện và hữu ích với người dùng không?

2. TÁC ĐỘNG PERFORMANCE:
   - Có bất kỳ nút thắt performance rõ ràng nào không?
   - Sử dụng bộ nhớ có hợp lý không?
   - Các database query có được tối ưu hóa không?
   - Caching có được thực hiện ở nơi thích hợp không?

3. VALIDATION SECURITY:
   - Tất cả các đầu vào có được validate và sanitize đúng cách không?
   - Authentication/authorization có được thực hiện chính xác không?
   - Có bất kỳ lỗ hổng bảo mật tiềm năng nào không?
   - Dữ liệu nhạy cảm có được xử lý đúng cách không?

LỚP 3 - CÁC CÂU HỎI REVIEW KIẾN TRÚC:
Gắn cờ các mục này cho review kiến trúc bởi con người:

1. SỰ CĂN CHỈNH KIẾN TRÚC:
   - Điều này có tuân theo các architectural pattern đã thiết lập của chúng ta không?
   - Có bất kỳ vi phạm nào đối với các nguyên tắc SOLID không?
   - Sự phân tách các mối quan tâm (separation of concerns) có thích hợp không?
   - Điều này có tạo ra bất kỳ vấn đề kết nối chặt chẽ (tight coupling) nào không?

2. CÁC CÂN NHẮC VỀ SCALABILITY:
   - Điều này sẽ hoạt động như thế nào dưới tải gấp 10 lần hiện tại?
   - Có bất kỳ nút thắt tiềm năng nào khi dữ liệu tăng lên không?
   - Cách tiếp cận này có bền vững trong dài hạn không?
   - Có các lựa chọn thay thế kiến trúc tốt hơn không?

3. TÁC ĐỘNG BẢO TRÌ (MAINTENANCE):
   - Code này có dễ test không?
   - Các thành viên mới trong nhóm có hiểu code này không?
   - Có những sự phức tạp ẩn nào sẽ gây ra vấn đề sau này không?
   - Điều này làm tăng hay giảm độ phức tạp tổng thể của hệ thống?

ĐỊNH DẠNG BÁO CÁO XÁC MINH:
Cung cấp một báo cáo có cấu trúc:

✅ KẾT QUẢ LỚP 1:
- Các vấn đề kỹ thuật được tìm thấy: [danh sách hoặc "không"]
- Điểm chất lượng code: [1-10 với lý do]
- Rủi ro tích hợp: [danh sách hoặc "không"]

✅ KẾT QUẢ LỚP 2:
- Độ hoàn thiện chức năng: [phần trăm với các mục còn thiếu]
- Lo ngại về Performance: [danh sách hoặc "không"]
- Các vấn đề Security: [danh sách hoặc "không"]

⚠️ LỚP 3 CẦN CON NGƯỜI REVIEW:
- Các quyết định kiến trúc yêu cầu review: [danh sách]
- Các câu hỏi về Scalability cần validate: [danh sách]
- Các lo ngại về Maintenance cần thảo luận: [danh sách]

HÀNH ĐỘNG ĐƯỢC KHUYẾN NGHỊ:
1. [Cần sửa chữa ngay lập tức]
2. [Cần xem xét tối ưu hóa Performance]
3. [Cần thảo luận về Kiến trúc]

Chỉ đánh dấu là hoàn thành sau khi tất cả các vấn đề Lớp 1 và Lớp 2 được giải quyết.
```

## Thực Hiện Từng Bước

### Bước 1: Thiết Lập Xác Minh Lớp 1 Tự Động (5 phút)

Tạo `.vibe/verify.sh`:

```bash
#!/bin/bash
# Layer 1: Immediate Technical Verification

echo "🔍 LAYER 1: Technical Verification"

# TypeScript Check
if [ -f "tsconfig.json" ]; then
    echo "📝 TypeScript strict check..."
    npx tsc --noEmit --strict || { echo "❌ TypeScript errors found"; exit 1; }
    echo "✅ TypeScript: No errors"
fi

# ESLint Check  
if [ -f ".eslintrc.js" ] || [ -f ".eslintrc.json" ]; then
    echo "🧹 ESLint quality check..."
    npx eslint . --ext .ts,.tsx,.js,.jsx --max-warnings 0 || { echo "❌ Linting issues found"; exit 1; }
    echo "✅ ESLint: No issues"
fi

# Import Resolution Check
echo "🔗 Import resolution check..."
if command -v madge &> /dev/null; then
    madge --circular --extensions ts,tsx,js,jsx ./src || { echo "❌ Circular dependencies found"; exit 1; }
    echo "✅ Imports: No circular dependencies"
fi

# Test Execution
if grep -q "test" package.json 2>/dev/null; then
    echo "🧪 Running existing tests..."
    npm test -- --run --reporter=basic || { echo "❌ Tests failed"; exit 1; }
    echo "✅ Tests: All passing"
fi

echo "✅ LAYER 1: All technical verification passed"
```

### Bước 2: Thực Hiện Prompt Xác Minh Chức Năng Lớp 2

Sử dụng prompt này cho validation chức năng:

```
LỚP 2 XÁC MINH CHỨC NĂNG (FUNCTIONAL VERIFICATION): Test một cách có hệ thống chức năng tôi vừa thực hiện

VALIDATION BUSINESS LOGIC:
Test các kịch bản này và báo cáo kết quả:

1. TEST HAPPY PATH:
   - Use case chính hoạt động như mong đợi: [test và xác nhận]
   - Tất cả các tính năng bắt buộc hoạt động chính xác: [liệt kê những gì bạn đã test]
   - Trải nghiệm người dùng diễn ra suôn sẻ: [xác định bất kỳ điểm ma sát nào]

2. VALIDATION EDGE CASE:
   - Xử lý đầu vào rỗng/null: [test với đầu vào rỗng]
   - Các ranh giới giá trị tối đa/tối thiểu: [test các giới hạn]
   - Xử lý hoạt động đồng thời: [xác định các điều kiện race condition tiềm năng]
   - Các kịch bản lỗi mạng: [nó xử lý lỗi API như thế nào]

3. CÁC KỊCH BẢN LỖI:
   - Từ chối đầu vào không hợp lệ: [test với dữ liệu không đúng định dạng]
   - Lỗi Authorization: [test với sai quyền]
   - Tài nguyên không khả dụng: [test khi các dependency bị lỗi]
   - Thông báo lỗi nhẹ nhàng (graceful): [các lỗi có thân thiện với người dùng không]

4. VALIDATION PERFORMANCE:
   - Thời gian phản hồi dưới tải bình thường: [ước tính performance]
   - Các pattern sử dụng bộ nhớ: [xác định rò rỉ bộ nhớ tiềm năng]
   - Hiệu quả Database query: [phân tích các pattern query]
   - Hiệu quả Caching: [xác minh việc sử dụng cache]

5. XÁC MINH SECURITY:
   - Input sanitization đang hoạt động: [test với đầu vào có khả năng độc hại]
   - Authentication được thực thi đúng cách: [test mà không có auth thích hợp]
   - Ngăn chặn lộ dữ liệu: [kiểm tra rò rỉ thông tin]
   - Có ghi log kiểm toán (audit logging): [xác minh các sự kiện bảo mật được ghi log]

BÁO CÁO XÁC MINH CHỨC NĂNG:
✅ Business Logic: [đang hoạt động/các vấn đề được tìm thấy]
✅ Edge Cases: [được xử lý đúng cách/các khoảng trống được xác định]  
✅ Error Handling: [toàn diện/cần cải thiện]
✅ Performance: [chấp nhận được/các lo ngại được ghi nhận]
✅ Security: [an toàn/các lỗ hổng được tìm thấy]

CÁC VẤN ĐỀ QUAN TRỌNG CẦN SỬA CHỮA NGAY LẬP TỨC:
[Liệt kê bất kỳ vấn đề nào phải được giải quyết trước khi deployment]

CÁC CẢI TIẾN ĐƯỢC KHUYẾN NGHỊ:
[Liệt kê các nâng cấp sẽ cải thiện chất lượng]

Chỉ tiến hành sang Lớp 3 nếu tất cả các vấn đề quan trọng được giải quyết.
```

### Bước 3: Checklist Review Kiến Trúc Của Con Người

Tạo checklist này cho review Lớp 3 của con người:

```
LỚP 3: CHECKLIST REVIEW KIẾN TRÚC

SỰ CĂN CHỈNH KIẾN TRÚC:
□ Tuân theo các design pattern đã thiết lập trong codebase của chúng ta
□ Tôn trọng các ranh giới module và các giao diện (interface) hiện có  
□ Duy trì các mức độ trừu tượng nhất quán
□ Không giới thiệu sự phức tạp không cần thiết

ĐÁNH GIÁ SCALABILITY:
□ Sẽ hoạt động ở mức chấp nhận được tại quy mô gấp 10 lần hiện tại
□ Các Database query sẽ mở rộng (scale) cùng với sự tăng trưởng dữ liệu
□ Không có nút thắt rõ ràng dưới tải tăng lên
□ Các pattern sử dụng tài nguyên là bền vững

ĐÁNH GIÁ MAINTAINABILITY:
□ Code tự tài liệu hóa (self-documenting) và rõ ràng
□ Dễ dàng sửa đổi mà không phá vỡ các component khác
□ Test coverage cho phép refactoring tự tin
□ Các thành viên mới trong nhóm có thể hiểu và mở rộng cái này

KIẾN TRÚC SECURITY:
□ Các kiểm soát Security được phân lớp đúng cách
□ Không có quyết định bảo mật nào bị đẩy sang lớp trình bày (presentation layer)
□ Các hoạt động nhạy cảm có authorization thích hợp
□ Bề mặt tấn công được giảm thiểu

TÁC ĐỘNG TECHNICAL DEBT:
□ Không làm tăng độ phức tạp tổng thể của hệ thống
□ Tuân theo các quy ước và tiêu chuẩn hiện có
□ Không tạo ra các thách thức migration trong tương lai
□ Cân bằng tốc độ với khả năng bảo trì dài hạn

CÁC CỜ ĐỎ CẦN THẢO LUẬN:
□ Tạo ra các architectural pattern mới mà không có lý do chính đáng
□ Giới thiệu các dependency ảnh hưởng đến các nhóm khác
□ Đưa ra các giả định về các yêu cầu trong tương lai
□ Tối ưu hóa cho các nhu cầu hiện tại với chi phí là sự linh hoạt

QUYẾT ĐỊNH PHÊ DUYỆT:
□ PHÊ DUYỆT (APPROVE): Đáp ứng tất cả các tiêu chuẩn kiến trúc
□ PHÊ DUYỆT CÓ ĐIỀU KIỆN (APPROVE WITH CONDITIONS): [liệt kê các thay đổi bắt buộc]
□ CẦN LÀM LẠI (NEEDS REWORK): [giải thích các lo ngại về kiến trúc]
```

## Workflow Tích Hợp

### Tích Hợp Tự Động

Thêm vào `package.json` của bạn:

```json
{
  "scripts": {
    "ai-verify": "./.vibe/verify.sh",
    "ai-verify-full": "./.vibe/verify.sh && echo 'Run Layer 2 functional verification prompt'",
    "pre-commit": "./.vibe/verify.sh"
  }
}
```

### Tích Hợp IDE

Đối với VS Code/Cursor, thêm vào `.vscode/tasks.json`:

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "AI Verification",
      "type": "shell", 
      "command": "./.vibe/verify.sh",
      "group": "build",
      "problemMatcher": "$tsc"
    }
  ]
}
```

## Mẫu Sử Dụng

Sau mỗi lần tạo code bằng AI:

1. **Ngay lập tức**: Chạy `.vibe/verify.sh` (Lớp 1 - tự động)
2. **Chức năng**: Sử dụng prompt xác minh Lớp 2 với AI
3. **Kiến trúc**: Con người review sử dụng checklist Lớp 3
4. **Sửa Vấn Đề**: Giải quyết các vấn đề trước khi tiếp tục
5. **Tài liệu**: Ghi chú bất kỳ quyết định kiến trúc nào được đưa ra

Điều này tạo ra vòng lặp phản hồi ngay lập tức ngăn chặn các lỗi phức hợp trong khi duy trì các tiêu chuẩn chất lượng production trong suốt quá trình phát triển.

Chìa khóa là làm cho việc xác minh trở nên có hệ thống và tự động thay vì tùy chọn, đảm bảo chất lượng được xây dựng vào mọi tương tác AI thay vì được gắn vào sau đó.
