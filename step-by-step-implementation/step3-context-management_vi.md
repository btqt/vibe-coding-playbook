# Hệ Thống Quản Lý Ngữ Cảnh Nâng Cao

## The Context Engineering Pipeline

Quản lý ngữ cảnh biến đổi AI từ một công cụ tạo code gây ảo giác (hallucinating code generator) thành một đối tác phát triển đáng tin cậy. Dưới đây là lý do tại sao mỗi thành phần lại quan trọng:

### Context Selection Framework

**High Priority Context (Luôn Bao Gồm)**:
```bash
# Cấu hình cốt lõi và types
- package.json (dependencies và scripts)
- tsconfig.json (cấu hình TypeScript)
- các file schema (database/API schemas)
- types/*.d.ts (type definitions)
- .env.example (các biến môi trường)

# Các quy ước dự án
- .cursor-rules (các tiêu chuẩn coding)
- README.md (tổng quan dự án)
- CONTRIBUTING.md (các hướng dẫn phát triển)
```

**Pattern Context (Bao Gồm Khi Liên Quan)**:
```bash
# Các triển khai tương tự
- components/auth/* (cho các tính năng liên quan đến auth)
- lib/utils/* (cho các hàm tiện ích)
- hooks/* (cho các custom React hooks)
- api/routes/* (cho phát triển API)

# Các pattern tích hợp
- middleware/* (cho xử lý request)
- services/* (cho business logic)
- tests/* (cho testing patterns)
```

**Integration Context (Khi Cần Thiết)**:
```bash
# Các hệ thống liên quan
- tài liệu external API
- các file database migration
- các cấu hình deployment
- các thiết lập monitoring
```

### Chiến Lược Tải Context Lũy Tiến (Progressive Context Loading Strategy)

```xml
<context_loading>
  <session_start>
    <!-- Foundation Context -->
    - Các file cấu hình cốt lõi
    - Type definitions và schemas  
    - Các quy tắc và quy ước dự án
    - Tài liệu Architecture
  </session_start>
  
  <feature_development>
    <!-- Pattern Context -->
    - Các triển khai component tương tự
    - Các API endpoint liên quan
    - Các Database model và query
    - Các ví dụ Test
  </feature_development>
  
  <complex_integration>
    <!-- Full Context -->
    - Cây dependency hoàn chỉnh
    - Tài liệu Integration
    - Performance benchmarks
    - Các hướng dẫn Security
  </complex_integration>
</context_loading>
```

## Các Context Template Cho Các Kịch Bản Khác Nhau

### Frontend Development Context
```xml
<frontend_context>
  <required_files>
    - components/ui/* (các component hệ thống thiết kế)
    - lib/utils.ts (các hàm tiện ích)
    - hooks/* (các custom React hooks)
    - types/index.ts (TypeScript definitions)
    - tailwind.config.js (cấu hình styling)
  </required_files>
  
  <patterns_to_follow>
    - Các pattern component composition từ các component hiện có
    - Các pattern quản lý State (Context API/Zustand/Redux)
    - Các pattern xử lý Form (React Hook Form + Zod)
    - Các triển khai Error boundary
    - Quản lý trạng thái Loading
  </patterns_to_follow>
  
  <constraints>
    - Sử dụng các component hệ thống thiết kế hiện có
    - Tuân theo các quy ước đặt tên đã thiết lập
    - Thực hiện các TypeScript type thích hợp
    - Bao gồm các thuộc tính accessibility
    - Đảm bảo thiết kế responsive
  </constraints>
</frontend_context>
```

### API Development Context
```xml
<backend_context>
  <required_files>
    - api/routes/* (các pattern route hiện có)
    - lib/db.ts (các pattern kết nối database)
    - middleware/* (các pattern authentication/validation)
    - types/api.ts (API type definitions)
    - schema/* (validation schemas)
  </required_files>
  
  <patterns_to_follow>
    - Các quy ước RESTful API hoặc tRPC patterns
    - Error handling và định dạng response
    - Các pattern Authentication và authorization
    - Input validation với Zod schemas
    - Các pattern tối ưu hóa Database query
  </patterns_to_follow>
  
  <constraints>
    - Tuân theo các pattern authentication hiện có
    - Thực hiện input validation thích hợp
    - Sử dụng error handling đã thiết lập
    - Bao gồm logging toàn diện
    - Duy trì tính nhất quán của API versioning
  </constraints>
</backend_context>
```

### Database Schema Context
```xml
<database_context>
  <required_files>
    - prisma/schema.prisma (schema hiện tại)
    - migrations/* (lịch sử migration)
    - lib/db.ts (các tiện ích database)
    - types/database.ts (database types)
  </required_files>
  
  <patterns_to_follow>
    - Các quy ước đặt tên cho bảng và cột
    - Các pattern quan hệ và khóa ngoại (foreign keys)
    - Các chiến lược Index cho performance
    - Các pattern an toàn Migration
    - Data validation ở cấp độ database
  </patterns_to_follow>
  
  <constraints>
    - Duy trì tính toàn vẹn tham chiếu (referential integrity)
    - Tuân theo các quy ước đặt tên đã thiết lập
    - Tạo các migration có thể đảo ngược
    - Xem xét các tác động về performance
    - Bao gồm các constraint và validation thích hợp
  </constraints>
</database_context>
```

## Các Metrics Chất Lượng Context

### Điểm Hoàn Thiện (Completeness Score)
```javascript
// Tính toán độ hoàn thiện context
const contextScore = {
  requiredFiles: openFiles.filter(f => requiredFiles.includes(f)).length / requiredFiles.length,
  typeDefinitions: openFiles.filter(f => f.endsWith('.d.ts')).length > 0,
  configFiles: openFiles.filter(f => ['package.json', 'tsconfig.json'].includes(f)).length / 2,
  patternExamples: openFiles.filter(f => similarPatterns.includes(f)).length / Math.min(similarPatterns.length, 3)
};

const overall = Object.values(contextScore).reduce((a, b) => a + b, 0) / Object.keys(contextScore).length;
// Mục tiêu: 90%+ hoàn thiện
```

### Các Lệnh Quản Lý Context

**Các Lệnh Cụ Thể Cho Cursor**:
```bash
# Tìm kiếm và thêm các file liên quan
@codebase search for authentication patterns
@files add all TypeScript definition files
@docs reference API documentation
@git show recent changes to auth system
```

**Tải Context Tự Động**:
```bash
#!/bin/bash
# .vibe/scripts/context.sh

case $1 in
  "frontend")
    echo "Loading frontend context..."
    cursor --add-to-context components/ui/*
    cursor --add-to-context hooks/*
    cursor --add-to-context types/*
    cursor --add-to-context lib/utils.ts
    ;;
  "backend") 
    echo "Loading backend context..."
    cursor --add-to-context api/routes/*
    cursor --add-to-context middleware/*
    cursor --add-to-context lib/db.ts
    cursor --add-to-context schema/*
    ;;
  "database")
    echo "Loading database context..."
    cursor --add-to-context prisma/schema.prisma
    cursor --add-to-context migrations/*
    cursor --add-to-context lib/db.ts
    ;;
esac
```

## XML-Based Context Injection

### Structured Context Prompting
```xml
<context_injection>
  <project_metadata>
    - Framework: Next.js 14 với TypeScript
    - Database: PostgreSQL với Prisma ORM
    - Authentication: NextAuth.js với JWT
    - Styling: Tailwind CSS với shadcn/ui
    - State Management: Zustand cho global state
  </project_metadata>
  
  <current_patterns>
    <authentication>
      - Pattern: JWT tokens với refresh token rotation
      - Implementation: /lib/auth.ts, /api/auth/[...nextauth].ts
      - Error Handling: Lớp AuthError tùy chỉnh với thông báo thân thiện người dùng
      - Testing: Mock authentication trong môi trường test
    </authentication>
    
    <api_structure>
      - Pattern: Các thủ tục tRPC với Zod validation
      - Implementation: /server/api/routers/*.ts
      - Error Handling: TRPCError với các mã trạng thái HTTP thích hợp
      - Testing: Integration tests với test database
    </api_structure>
    
    <component_architecture>
      - Pattern: Compound components với forwarded refs
      - Implementation: /components/ui/*.tsx
      - State: Server state với TanStack Query, local state với useState
      - Testing: React Testing Library với mô phỏng sự kiện người dùng
    </component_architecture>
  </current_patterns>
  
  <architectural_constraints>
    - Tất cả các component phải tương thích server (Next.js App Router)
    - Các query Database phải sử dụng Prisma với error handling thích hợp
    - Các API route phải thực hiện rate limiting và CORS
    - Frontend phải hoàn toàn responsive và accessible
    - Tất cả các form phải sử dụng React Hook Form với Zod validation
  </architectural_constraints>
</context_injection>
```

## Các Chiến Lược Tối Ưu Hóa Context

### Quản Lý Context Window
```typescript
// Thuật toán ưu tiên Context
interface ContextFile {
  path: string;
  relevanceScore: number;
  size: number;
  lastModified: Date;
}

function optimizeContext(files: ContextFile[], maxTokens: number): ContextFile[] {
  // Ưu tiên theo mức độ liên quan, tính mới, và hiệu quả kích thước
  return files
    .sort((a, b) => {
      const relevanceWeight = 0.5;
      const recencyWeight = 0.3;
      const sizeWeight = 0.2;
      
      const aScore = a.relevanceScore * relevanceWeight + 
                    (Date.now() - a.lastModified.getTime()) * recencyWeight +
                    (1 / a.size) * sizeWeight;
                    
      const bScore = b.relevanceScore * relevanceWeight + 
                    (Date.now() - b.lastModified.getTime()) * recencyWeight +
                    (1 / b.size) * sizeWeight;
                    
      return bScore - aScore;
    })
    .reduce((selected, file) => {
      const currentTokens = selected.reduce((sum, f) => sum + f.size, 0);
      if (currentTokens + file.size <= maxTokens) {
        selected.push(file);
      }
      return selected;
    }, [] as ContextFile[]);
}
```

### Xác Thực Context
```bash
#!/bin/bash
# .vibe/scripts/validate-context.sh

echo "🔍 Validating context quality..."

# Kiểm tra các file bắt buộc
required_files=("package.json" "tsconfig.json" ".cursor-rules")
missing_files=()

for file in "${required_files[@]}"; do
  if [ ! -f "$file" ]; then
    missing_files+=("$file")
  fi
done

if [ ${#missing_files[@]} -gt 0 ]; then
  echo "❌ Missing required files: ${missing_files[*]}"
  exit 1
fi

# Kiểm tra type definitions
if [ -z "$(find . -name "*.d.ts" | head -1)" ]; then
  echo "⚠️  No TypeScript definition files found"
fi

# Kiểm tra các ví dụ pattern
if [ -z "$(find components -name "*.tsx" | head -1)" ]; then
  echo "⚠️  No component examples found"
fi

echo "✅ Context validation complete"
```

Cách tiếp cận có hệ thống này đối với quản lý ngữ cảnh đảm bảo AI tạo ra code tích hợp liền mạch với các pattern và quyết định kiến trúc hiện có của bạn.
