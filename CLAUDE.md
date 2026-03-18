# Claude Code Course Transcripts (Vietnamese)

## Project Overview
Bộ transcript tiếng Việt từ khóa học Coursera "Scaling Up Software Engineering with Claude Code & Generative AI". Gồm 7 modules, mỗi module có thư mục `vi/` chứa các bài dịch dạng markdown.

## Cấu trúc thư mục
```
Module_01/ - Giới thiệu tổng quan
Module_02/ - AI Labor, Best of N pattern
Module_03/ - Chất lượng code, Chat-Craft-Scale
Module_04/ - CLAUDE.md, Commands, In-Context Learning
Module_05/ - Git, Worktrees, Parallel Development
Module_06/ - Scalability, Token Limits
Module_07/ - Multimodal Prompting, Fix Process not Code
```

## Quy tắc khi edit markdown

### Mermaid diagrams
- Giữ mermaid blocks, KHÔNG chuyển sang text/table trừ khi được yêu cầu
- KHÔNG dùng `<br/>` trong node labels — nối text thành 1 dòng
- KHÔNG dùng numbered list pattern `"1. `, `"2. ` trong node labels (gây lỗi "unsupported markdown list" trên một số renderer)
- OK: `A["Reusable Prompting - Prompt nhất quán"]`
- KHÔNG OK: `A["1. Reusable Prompting<br/>Prompt nhất quán"]`

### Nội dung
- Giữ nguyên tiếng Việt
- Giữ nguyên cấu trúc heading, table, code blocks
- Emoji trong list items (✅ ❌) là OK
