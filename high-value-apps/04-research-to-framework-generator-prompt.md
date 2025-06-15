# Research-to-Framework Generator

**Task:** Create a simple research analysis tool with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no file uploads initially)
- Basic text analysis and framework generation
- **Minimalistic Design Focus:** Create a very light design that minimizes vertical space usage. Each content line should take up as little vertical space as possible while using horizontal space more generously. Avoid extra visual elements between content lines - use only white spaces for separation. Focus on content over decoration with a clean, minimal aesthetic.

**Constraints:**
- Start with manual text input only
- Single page application
- No external APIs in MVP

---

## MVP Features (Build First)

1. **Research Input** - Text area for pasting research content
2. **Analysis Results** - Display key insights and patterns
3. **Framework Output** - Generated implementation framework
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// research: Array stored in localStorage
const research = [
  {
    id: "uuid",
    title: "AI Safety Research",
    content: "Research content text...",
    insights: ["Key insight 1", "Key insight 2"],
    framework: {
      title: "AI Safety Framework",
      steps: ["Step 1", "Step 2"],
      recommendations: ["Rec 1", "Rec 2"]
    },
    created: "2025-01-15"
  }
]
```

## Analysis Features
- **Keyword Extraction** - Identify important terms and concepts
- **Pattern Recognition** - Find recurring themes and ideas
- **Insight Generation** - Extract key takeaways
- **Framework Creation** - Structure findings into actionable steps

## Design System
- **Colors:** Purple theme with professional dark mode
- **Layout:** Document-style with clear sections
- **Responsive:** Mobile-friendly reading and editing

---

## Development Roadmap

**Start with MVP:** Create a simple research analyzer that takes text input and generates basic frameworks with dark mode.

### Phase 1: Basic Text Analysis (MVP)
✅ Build foundation with text input, keyword extraction, and basic framework generation

### Phase 2: File Upload Support
🔄 Add support for PDF, DOCX, and Markdown file uploads with text extraction

### Phase 3: AI-Powered Analysis
🔄 Integrate AI models for advanced pattern recognition and insight generation

### Phase 4: Framework Templates
🔄 Create library of framework templates for different research domains

### Phase 5: Collaborative Features
🔄 Enable real-time collaboration with shared research projects and comments

### Phase 6: Advanced Export Options
🔄 Add export to multiple formats (PDF, Word, PowerPoint, Notion)

### Phase 7: Research Database
🔄 Implement searchable research database with tagging and categorization

### Phase 8: Integration Ecosystem
🔄 Connect with reference managers, note-taking apps, and research platforms

**Next Step After MVP:** Implement Phase 2 - File Upload Support
