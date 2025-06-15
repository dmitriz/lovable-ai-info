# AI Deep Research Assistant

**Task:** Create a simple research project manager with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no external APIs initially)
- Basic research planning and note-taking
- **Minimalistic Design Focus:** Create a very light design that minimizes vertical space usage. Each content line should take up as little vertical space as possible while using horizontal space more generously. Avoid extra visual elements between content lines - use only white spaces for separation. Focus on content over decoration with a clean, minimal aesthetic.

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

## Development Roadmap

**Start with MVP:** Create a simple research project manager with note-taking and source management with dark mode.

### Phase 1: Basic Research Management (MVP)
✅ Build foundation with project creation, note-taking, source management, and dark mode

### Phase 2: Enhanced Note System
🔄 Add rich text editing, tagging, cross-referencing, and advanced search

### Phase 3: AI Platform Integration
🔄 Connect to multiple AI services (GPT, Gemini, Perplexity) for automated research

### Phase 4: Cost Tracking & Optimization
🔄 Implement usage monitoring, cost analysis, and budget management tools

### Phase 5: Source Verification
🔄 Add automatic source credibility checking and fact verification

### Phase 6: Research Synthesis
🔄 Create AI-powered research summaries and comprehensive reports

### Phase 7: Team Collaboration
🔄 Enable shared projects, real-time collaboration, and peer review

### Phase 8: Advanced Analytics
🔄 Implement research trend analysis, citation networks, and impact metrics

**Next Step After MVP:** Implement Phase 2 - Enhanced Note System
