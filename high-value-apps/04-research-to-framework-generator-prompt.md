# Research-to-Framework Generator

**Task:** Create a simple research analysis tool with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no file uploads initially)
- Basic text analysis and framework generation

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

## Future Enhancements (After MVP)
- File upload support (PDF, DOCX, MD)
- AI-powered analysis and synthesis
- Collaborative editing features
- Export to multiple formats
- Template library system

Start with the MVP: Create a simple research analyzer that takes text input and generates basic frameworks with dark mode.
