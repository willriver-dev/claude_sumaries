# Bài 1: Từ phác thảo trên khăn giấy đến Production Code — Multimodal Prompting

## Nội dung chính

### Kịch bản

Bạn đang ngồi quán cà phê, brainstorm cho expense tracker app. Cảm hứng ập đến — bạn chộp lấy khăn giấy và bắt đầu phác thảo ý tưởng cho dashboard "Expense Insights". Khăn giấy có vài vết cà phê? Không sao — Claude Code có thể biến cả những phác thảo lộn xộn nhất thành code production-ready.

### Bài tập: Biến phác thảo thành code

**Bước 1**: Lưu hình ảnh phác thảo (napkin mockup) vào project folder

**Bước 2**: Prompt Claude Code:

```
I sketched an expense insights dashboard on a napkin at a coffee shop.
Please implement this as a React component called MonthlyInsights.
Looking at this sketch: /your/path/to/napkin-insights-mockup.png
Implement a new screen in the application that mirrors what you see
in the mockup.
```

(Hoặc kéo-thả hình ảnh trực tiếp vào prompt area của Claude Code)

### Khi nào hình ảnh mạnh hơn text?

```mermaid
graph TB
 A["Multimodal Prompting<br/>Khi nào dùng hình ảnh?"] --> B["UI/UX Design<br/>Layout, spatial relationships,<br/>colors, responsive behavior"]
 A --> C["Data Visualization<br/>Chart types, dashboard layouts,<br/>styling details"]
 A --> D["User Flows<br/>Multi-step processes,<br/>animations, transitions"]
 A --> E["Bug Reports<br/>Visual glitches,<br/>layout issues"]
 A --> F["Architecture<br/>System diagrams,<br/>DB schemas, network topology"]
 A --> G["Business Logic<br/>Decision trees,<br/>workflow diagrams"]

 style A fill:#ffd93d,color:#333
```

### So sánh: Text vs. Visual

| Tình huống | Text approach | Visual approach |
|---|---|---|
| **Layout** | "Search bar centered, logo 20px left, avatar 15px right, nav below with equal spacing..." | Wireframe → "Implement this layout exactly" |
| **Colors** | "Blue not too dark, not too light, professional but warmer, subtle gradient..." | Color palette → "Match these exact colors" |
| **Charts** | "Donut chart, hole 40% radius, 5 distinct colors, labels don't overlap..." | Sketch → "Create a chart like this" |
| **Bug report** | "Button text cut off, weird spacing, colors wrong, nav overlapping on mobile..." | Screenshot → "Fix what's wrong here" |
| **Architecture** | "Frontend → API gateway → 3 microservices, each with DB, message queue between..." | Diagram → "Implement this architecture" |

### Ứng dụng thực tế

- **Design handoffs**: Designer show mockup → Claude Code implement trực tiếp
- **Team whiteboard**: Chụp ảnh whiteboard sau meeting → Claude Code tạo prototypes trong lúc team nghỉ giải lao
- **Bug reports**: Screenshot + annotation >> mô tả text dài dòng
- **Stakeholder communication**: Prototype từ sketch → feedback tức thì
- **Documentation**: Visual examples hiệu quả hơn text thuần

---

# Bài 2: Bắt đầu bằng sửa Process & Context, không phải sửa Code

## Nội dung chính

### Tình huống không thể tránh

Khi bắt đầu dùng Claude Code, điều này **chắc chắn sẽ xảy ra**: Claude viết code không đúng ý bạn — sai style, sai thiết kế, không đúng mong đợi.

Bạn có vài lựa chọn:
1. Tự tay sửa code
2. Prompt Claude Code sửa trực tiếp
3. **Sửa CLAUDE.md và Commands** ← Đây là lựa chọn có giá trị nhất

### Tại sao sửa process thay vì sửa code?

```mermaid
graph TB
 subgraph " Sửa code trực tiếp"
 A1["Claude viết sai"] --> A2["Bạn sửa code bằng tay"]
 A2 --> A3["Lần sau Claude<br/>lại sai y vậy"]
 A3 --> A4["Bạn lại sửa bằng tay"]
 A4 --> A5[" Lặp lại mãi<br/>Không scalable"]
 end

 subgraph " Sửa process & context"
 B1["Claude viết sai"] --> B2["Cập nhật CLAUDE.md<br/>& Commands"]
 B2 --> B3["Lần sau Claude<br/>làm đúng tự động"]
 B3 --> B4[" Scalable<br/>Repeatable"]
 end

 style A5 fill:#ff6b6b,color:#fff
 style B4 fill:#2ecc71,color:#fff
```

> Bạn đang **lập trình AI labor** — bằng tiếng Anh (hoặc ngôn ngữ nào bạn dùng) thay vì ngôn ngữ lập trình truyền thống. CLAUDE.md và Commands là "source code" của process.

### Ẩn dụ: Sorting algorithm

Nếu bạn viết chương trình sort số, bạn có muốn nó dừng lại mỗi 10 số để hỏi bạn "đúng chưa"? Không — bạn sẽ viết chương trình sort đúng, đặt guardrails, test, và tinh chỉnh cho đến khi nó **tự chạy đúng**.

Đó chính xác là mindset bạn cần: tinh chỉnh CLAUDE.md và Commands cho đến khi process **tự chạy đúng** mà không cần bạn can thiệp.

### Quy trình khi Claude Code mắc lỗi

```mermaid
graph TD
 A["Claude Code làm sai<br/>hoặc khác mong đợi"] --> B["1. Hỏi: Thiếu gì trong<br/>CLAUDE.md hoặc Commands?"]
 B --> C["2. Thêm specificity,<br/>instructions, examples,<br/>context vào files đó"]
 C --> D["3. Prompt Claude Code<br/>sửa code lần này"]
 D --> E["4. Lần sau: Claude Code<br/>tự làm đúng nhờ<br/>process đã cải thiện"]

 style B fill:#ffd93d,color:#333
 style C fill:#4d96ff,color:#fff
 style E fill:#2ecc71,color:#fff
```

### Câu hỏi tự vấn mỗi khi sửa code

> "Tôi có thể thay đổi gì trong CLAUDE.md hoặc Commands để lần sau không phải sửa lỗi này nữa?"

Mỗi phút bạn dành để cải thiện CLAUDE.md và Commands = **đầu tư vào scalability**:
- Process lặp lại tốt hơn
- Code chất lượng cao hơn
- Bạn hands-off nhiều hơn
- AI labor scale xa hơn

### Vẫn nên prompt sửa code (không tự sửa tay)

Khi cần sửa code ngay, hãy **prompt Claude Code sửa** thay vì tự sửa tay. Vì:
- Prompt sửa giúp bạn hiểu **Claude cần context/instruction gì** để thấy lỗi
- Từ đó biết cần thêm gì vào CLAUDE.md/Commands
- Tự sửa tay = không học được gì cho process

---

## Kiến thức bổ sung: Vòng lặp cải tiến liên tục

```mermaid
graph LR
 A["Giao task cho<br/>Claude Code"] --> B["Review kết quả"]
 B --> C{"Đúng mong đợi?"}
 C -->|"Có"| D[" Tiếp tục"]
 C -->|"Không"| E["Phân tích:<br/>Thiếu context gì?<br/>Thiếu instruction gì?"]
 E --> F["Cập nhật<br/>CLAUDE.md / Commands"]
 F --> G["Prompt Claude<br/>sửa code lần này"]
 G --> A

 style F fill:#4d96ff,color:#fff
 style D fill:#2ecc71,color:#fff
```

Theo thời gian, CLAUDE.md và Commands của bạn sẽ trở thành **bộ institutional knowledge hoàn chỉnh** — và Claude Code sẽ ngày càng ít mắc lỗi hơn.

---

## Summary — Đúc rút kinh nghiệm Module 07 & Toàn khóa học

> **Module 07 đóng lại khóa học với 2 bài học quan trọng.** (1) Multimodal prompting: hình ảnh mạnh hơn text cho UI, charts, architecture, bug reports — chụp ảnh phác thảo/whiteboard và để Claude Code implement. (2) Bài học quan trọng nhất: khi Claude Code sai, sửa CLAUDE.md và Commands TRƯỚC, sửa code SAU. Bạn đang lập trình AI labor — CLAUDE.md và Commands là source code của process. Mỗi lần cải thiện chúng = đầu tư vào scalability, repeatability, và chất lượng dài hạn.

---

## Tổng kết toàn khóa học

```mermaid
graph TB
 subgraph "Module 2: Tư duy"
 M2["AI = Labor<br/>Big Prompts<br/>Best of N"]
 end

 subgraph "Module 3: Chất lượng"
 M3["AI đánh giá code<br/>Chat, Craft, Scale<br/>Design Principles"]
 end

 subgraph "Module 4: Context"
 M4["CLAUDE.md<br/>Commands<br/>In-Context Learning"]
 end

 subgraph "Module 5: Song song"
 M5["Git Branches<br/>Worktrees<br/>Subagents"]
 end

 subgraph "Module 6: Scale"
 M6["Feedback loops<br/>Token limits<br/>Think first<br/>Project structure"]
 end

 subgraph "Module 7: Tinh chỉnh"
 M7["Multimodal<br/>Fix process,<br/>not code"]
 end

 M2 --> M3 --> M4 --> M5 --> M6 --> M7

 style M2 fill:#ffd93d,color:#333
 style M3 fill:#4d96ff,color:#fff
 style M4 fill:#6bcb77,color:#fff
 style M5 fill:#9b59b6,color:#fff
 style M6 fill:#e67e22,color:#fff
 style M7 fill:#2ecc71,color:#fff
```

> **Từ developer viết code → CEO điều phối AI labor.** Tư duy lớn (Big Prompts, Best of N) → Đảm bảo chất lượng (Chat, Craft, Scale) → Xây dựng context (CLAUDE.md, Commands, Examples) → Phát triển song song (Branches, Worktrees, Subagents) → Tối ưu scalability (Token limits, Think first, Project structure) → Cải tiến liên tục (Fix process, not code). Đó là hành trình từ 1x đến 1000x.
