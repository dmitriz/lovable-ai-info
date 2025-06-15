# AI Code Review Assistant

**Task:** Create a comprehensive code review assistant that analyzes code quality, security, and best practices.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for review history and templates
- Clean, minimalist UI with ShadCN components
- **Minimalistic Design Focus:** Create a very light design that minimizes vertical space usage. Each content line should take up as little vertical space as possible while using horizontal space more generously. Avoid extra visual elements between content lines - use only white spaces for separation. Focus on content over decoration with a clean, minimal aesthetic.

**Constraints:**
- Start with core functionality only
- Single page application
- Client-side code analysis initially

---

## MVP Features (Build First)

1. **Code Input** - Multi-language code editor with syntax highlighting
2. **Review Analysis** - Real-time code quality assessment
3. **Issue Detection** - Identify common patterns, security flaws, and anti-patterns
4. **Best Practices** - Suggest improvements based on language-specific conventions
5. **Review Templates** - Predefined checklists for different review types

## Data Structure (Local Storage)
```javascript
// reviews: Array stored in localStorage
const reviews = [
  {
    id: "uuid",
    title: "Component Review",
    language: "javascript",
    code: "// code content",
    issues: [
      {
        type: "warning",
        line: 10,
        message: "Consider using const instead of let",
        category: "best-practice"
      }
    ],
    score: 85,
    created: "2025-01-15"
  }
]

// templates: Array stored in localStorage
const review_templates = [
  {
    id: "uuid",
    name: "React Component Review",
    checklist: [
      "Props validation",
      "Error boundaries",
      "Performance optimization",
      "Accessibility"
    ]
  }
]
```

## Design System
- **Colors:** Green theme (success/issues) with proper dark mode variants
- **Layout:** Split-pane design with code editor and review panel
- **Responsive:** Collapsible panels for mobile

---

## Development Roadmap

**Start with MVP:** Create a code analysis interface with basic pattern detection and issue highlighting.

### Phase 1: Core Analysis (MVP)
- Code input with syntax highlighting
- Basic linting and pattern detection
- Issue categorization (error, warning, info)
- Review score calculation

### Phase 2: Advanced Features
- Custom rule configuration
- Language-specific analysis
- Performance metrics
- Security vulnerability detection

### Phase 3: Collaboration
- Review sharing
- Comment system
- Team templates
- Progress tracking

---

## Technical Implementation

### Core Components
1. **CodeEditor** - Monaco editor with multi-language support
2. **ReviewPanel** - Issues list with severity indicators
3. **ScoreCard** - Overall code quality metrics
4. **TemplateManager** - Review checklist management

### Analysis Engine
- AST parsing for code structure analysis
- Pattern matching for common issues
- Configurable rule engine
- Performance and security checks

### Key Features
- Real-time code analysis
- Customizable review templates
- Historical review tracking
- Export/import functionality
