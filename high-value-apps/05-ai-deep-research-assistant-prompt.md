# AI Deep Research Assistant

**Task:** Create a simple research project manager with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no external APIs initially)
- Basic research planning and note-taking

**Constraints:**
- Start with manual research entry only
- Single page application
- No AI platform integration in MVP

---

## MVP Features (Build First)

1. **Research Projects** - Create and manage research projects
2. **Note Taking** - Add research notes and sources
3. **Source Management** - Track sources with citations
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// projects: Array stored in localStorage
const projects = [
  {
    id: "uuid",
    title: "AI Ethics Research",
    description: "Research on AI ethics frameworks",
    notes: [
      {
        id: "note-uuid",
        content: "Important finding about...",
        source: "source-uuid",
        created: "2025-01-15"
      }
    ],
    sources: [
      {
        id: "source-uuid",
        title: "AI Ethics Paper",
        url: "https://example.com",
        citation: "Author (2025). Title. Journal."
      }
    ],
    created: "2025-01-15"
  }
]
```

## Research Features
- **Project Organization** - Group related research by project
- **Note Management** - Rich text notes with source linking
- **Citation Tracking** - Automatic citation formatting
- **Search & Filter** - Find notes and sources quickly

## Design System
- **Colors:** Teal theme with professional dark mode
- **Layout:** Research-focused with project sidebar
- **Responsive:** Mobile-friendly reading and editing

---

## Future Enhancements (After MVP)
- Multi-platform AI integration (GPT, Gemini, Perplexity)
- Cost tracking and optimization
- Automatic source verification
- Research synthesis and reports
- Team collaboration features

Start with the MVP: Create a simple research project manager with note-taking and source management with dark mode.
