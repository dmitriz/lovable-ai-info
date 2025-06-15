# Smart Documentation Generator

**Task:** Create an intelligent documentation generator that analyzes codebases and generates comprehensive documentation.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for projects and templates
- Clean, minimalist UI with ShadCN components
- **Minimalistic Design Focus:** Create a very light design that minimizes vertical space usage. Each content line should take up as little vertical space as possible while using horizontal space more generously. Avoid extra visual elements between content lines - use only white spaces for separation. Focus on content over decoration with a clean, minimal aesthetic.

**Constraints:**
- Start with core functionality only
- Single page application
- Client-side analysis initially

---

## MVP Features (Build First)

1. **Project Scanner** - Analyze file structure and identify key components
2. **Auto Documentation** - Generate README, API docs, and inline comments
3. **Template Engine** - Customizable documentation templates
4. **Preview Mode** - Live preview of generated documentation
5. **Export Options** - Markdown, HTML, and PDF export

## Data Structure (Local Storage)
```javascript
// projects: Array stored in localStorage
const projects = [
  {
    id: "uuid",
    name: "Project Name",
    description: "Project description",
    files: [
      {
        path: "src/component.js",
        type: "javascript",
        functions: ["function1", "function2"],
        classes: ["Class1"],
        exports: ["export1"]
      }
    ],
    documentation: {
      readme: "# Generated README content",
      api_docs: "API documentation",
      changelog: "Version history"
    },
    created: "2025-01-15"
  }
]

// templates: Array stored in localStorage
const doc_templates = [
  {
    id: "uuid",
    name: "React Project Template",
    sections: [
      "Installation",
      "Usage",
      "API Reference",
      "Examples",
      "Contributing"
    ],
    format: "markdown"
  }
]
```

## Design System
- **Colors:** Purple theme with proper dark mode variants
- **Layout:** Three-panel design (file tree, editor, preview)
- **Responsive:** Collapsible panels for mobile

---

## Development Roadmap

**Start with MVP:** Create a file analyzer that generates basic project documentation.

### Phase 1: Core Generation (MVP)
- File structure analysis
- Basic README generation
- Template system
- Live preview

### Phase 2: Advanced Analysis
- Code parsing and API extraction
- Inline comment generation
- Dependency analysis
- Architecture diagrams

### Phase 3: Export & Integration
- Multiple export formats
- Git integration
- Continuous documentation updates
- Team collaboration features

---

## Technical Implementation

### Core Components
1. **FileExplorer** - Project file tree navigation
2. **CodeAnalyzer** - AST parsing and metadata extraction
3. **TemplateEngine** - Customizable documentation templates
4. **PreviewPane** - Real-time documentation preview

### Analysis Engine
- Multi-language code parsing
- Function/class/export detection
- Dependency mapping
- Documentation coverage analysis

### Key Features
- Automatic README generation
- API documentation extraction
- Code comment suggestions
- Template customization
- Bulk documentation updates
