# Bài 2: Viết file CLAUDE.md

## Nội dung chính

### CLAUDE.md là gì?

CLAUDE.md là **bộ nhớ persistent** của AI team member — context thiết yếu có sẵn trong mọi prompt. Giống như onboarding developer mới, bạn cần cung cấp cho Claude Code institutional knowledge để làm việc hiệu quả trong team.

### Framework CONTEXT cho thiết kế CLAUDE.md

Dùng acronym này để nhớ các nguyên tắc chính:

| Chữ cái | Nguyên tắc | Ý nghĩa |
|---|---|---|
| **C** | Clear and Concise Instructions | Chỉ dẫn rõ ràng, ngắn gọn |
| **O** | Operational Processes | Quy trình vận hành |
| **N** | Naming and Standards | Quy ước đặt tên và tiêu chuẩn |
| **T** | Testing and Quality Gates | Testing và cổng chất lượng |
| **E** | Examples and References | Ví dụ và tham chiếu |
| **X** | Xpectations and Boundaries | Kỳ vọng và ranh giới |
| **T** | Tools and Dependencies | Công cụ và dependencies |
### 3 Nguyên tắc cốt lõi

| # | Nguyên tắc | Mô tả |
|---|---|---|
| 1 | Essential Only | Chỉ thông tin toàn cục, áp dụng cho MỌI task |
| 2 | Specificity | "Follow SOLID principles" thay vì "write good code" |
| 3 | Process > Micromanagement | Định nghĩa workflow, không phải chi tiết implementation |

> 💡 Flow: **Essential Only** → **Specificity** → **Process > Micromanagement**

---

## 6 Ví dụ CLAUDE.md theo loại dự án

### Ví dụ 1: Web Application (Next.js)

```markdown
# Project: TaskFlow Web Application

## Core Principles
**IMPORTANT**: Whenever you write code, it MUST follow SOLID design
principles. Never write code that violates these principles.

## Development Workflow
1. Create and checkout feature branch: `feature-[brief-description]`
2. Write comprehensive tests for all new functionality
3. Compile code and run all tests before committing
4. Write detailed commit messages explaining changes and rationale
5. Commit all changes to the feature branch

## Architecture Overview
- Frontend: Next.js 14 with TypeScript and Tailwind CSS
- State Management: Zustand (client), React Query (server)
- Backend: Node.js with Express and Prisma ORM
- Database: PostgreSQL
- Testing: Jest (unit), Playwright (E2E)

## Code Standards
- TypeScript for all new code with strict type checking
- Follow existing component structure in `/src/components`
- API routes follow RESTful conventions in `/src/pages/api`
- Tailwind utilities preferred; custom CSS only when necessary

## Quality Gates
- All code must compile without warnings
- Test coverage must remain above 80%
- ESLint and Prettier must pass without errors

## File Organization
- Components: `/src/components/[feature]/[ComponentName].tsx`
- Pages: `/src/pages/[route].tsx`
- Utilities: `/src/lib/[category]/[utility].ts`
- Types: `/src/types/[domain].ts`
```

### Ví dụ 2: Python Data Science

```markdown
# Project: Customer Analytics Pipeline

## Development Standards
- Language: Python 3.11+
- Code Style: PEP 8, use Black for formatting
- Type Hints: Required for all function signatures
- Documentation: Docstrings required for all public functions

## Workflow Requirements
1. Create feature branch: `analysis-[description]` or `model-[description]`
2. Write unit tests for all data processing functions
3. Run `pytest`, `black .`, and `flake8` before committing
4. Update docs in `/docs` if adding new features

## Data Handling Standards
- Pandas for data manipulation, prefer vectorized operations
- Pydantic models for data validation
- Never commit raw data files to version control
- Environment variables for database connections and API keys

## ML/Analysis Guidelines
- scikit-learn for standard ML algorithms
- Notebook naming: `YYYY-MM-DD-[initials]-[description].ipynb`
- MLflow for experiment tracking
- Include model performance metrics in commit messages
```

### Ví dụ 3: Mobile App (React Native)

```markdown
# Project: FitnessTracker Mobile App

## Platform Requirements
- Framework: React Native 0.72+ with TypeScript
- State: Redux Toolkit with RTK Query
- Navigation: React Navigation v6
- Platform Support: iOS 14+ and Android API 24+

## Mobile-Specific Standards
- Use React Native built-in components before third-party
- Implement proper error boundaries for crash prevention
- Follow platform-specific design guidelines
- Use FlatList for large datasets, never ScrollView
- Implement memoization with React.memo and useMemo
```
claude --resume bdaeb62b-deec-44a8-8060-8f1e86845e29
### Ví dụ 4: Enterprise Backend (Spring Boot)

```markdown
# Project: Payment Processing Microservice

## Service Architecture
- Framework: Spring Boot 3.1 with Java 17
- Database: PostgreSQL with JPA/Hibernate
- Security: OAuth 2.0 with JWT tokens
- Documentation: OpenAPI 3.0

## Security Requirements
- All endpoints require authentication except health checks
- Validate all inputs with Bean Validation annotations
- Use parameterized queries to prevent SQL injection
- Never expose internal entity models in API responses
```

### Ví dụ 5: DevOps Infrastructure

```markdown
# Project: Multi-Cloud Infrastructure Platform

## Infrastructure as Code Standards
- Primary Tool: Terraform with HCL
- Configuration Management: Ansible playbooks
- Container Orchestration: Kubernetes with Helm charts

## Security and Compliance
- All secrets must use external secret management
- Enable encryption at rest and in transit
- Implement least-privilege access policies
- Use service accounts, never personal credentials
```

### Ví dụ 6: Open Source Library (Python)

```markdown
# Project: DataValidator - Python Data Validation Library

## Library Design Principles
- API Design: Simple, intuitive, and Pythonic
- Dependencies: Minimal external dependencies
- Compatibility: Python 3.8+ support
- Performance: Optimize for speed and memory efficiency

## Development Workflow
1. Write tests first (TDD approach)
2. Ensure 100% test coverage for new code
3. Run full test suite across Python versions: `tox`
4. Update CHANGELOG.md with user-facing description
```

---

## Cấu trúc chung của CLAUDE.md hiệu quả

| CLAUDE.md | Mô tả |
|---|---|
| Core Principles | Design principles, bắt buộc |
| Development Workflow | Quy trình từng bước |
| Architecture Overview | Tech stack, cấu trúc |
| Code Standards | Conventions, style |
| Quality Gates | Testing, linting, coverage |
| File Organization | Cấu trúc thư mục |

---

## Best Practices Summary

### Nên làm (Do's)

- ✅ Dùng ngôn ngữ rõ ràng, actionable
- ✅ Chỉ định cụ thể tools và frameworks
- ✅ Định nghĩa quality gates và testing requirements
- ✅ Bao gồm workflow processes
- ✅ Chỉ định naming conventions
- ✅ Tham chiếu design principles đã biết (SOLID, DRY...)

### Không nên làm (Don'ts)

- ❌ Đưa chi tiết chỉ áp dụng cho task cụ thể
- ❌ Viết tài liệu dài hàng nghìn trang
- ❌ Dùng chỉ dẫn mơ hồ như "write good code"
- ❌ Quên chỉ định version control workflow
- ❌ Micromanage chi tiết implementation
- ❌ Đưa thông tin tạm thời hoặc thay đổi thường xuyên

---

## Summary — Đúc rút kinh nghiệm

> **CLAUDE.md là institutional knowledge cô đọng thành persistent context.** Dùng framework CONTEXT (Clear, Operational, Naming, Testing, Examples, Xpectations, Tools) để thiết kế. Mỗi loại dự án cần CLAUDE.md khác nhau — web app cần component structure, data science cần data handling standards, mobile cần platform-specific rules, enterprise cần security requirements. Nguyên tắc vàng: đủ cụ thể để Claude Code đi đúng hướng, nhưng không quá ràng buộc để nó vẫn có thể sáng tạo trong ranh giới bạn đặt ra. Essential only — chỉ thông tin toàn cục áp dụng cho MỌI task.
