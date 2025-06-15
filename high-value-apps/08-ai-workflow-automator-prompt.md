# AI Workflow Automator

**Task:** Create a simple workflow builder with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no external automation initially)
- Basic workflow creation and management

**Constraints:**
- Start with workflow design only
- Single page application
- No actual automation execution in MVP

---

## MVP Features (Build First)

1. **Workflow List** - Display created workflows with status
2. **Workflow Builder** - Simple step-by-step workflow creation
3. **Template Library** - Pre-built workflow templates
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// workflows: Array stored in localStorage
const workflows = [
  {
    id: "uuid",
    name: "Data Processing Workflow",
    description: "Process and analyze data files",
    steps: [
      {
        id: "step-1",
        type: "input",
        name: "Upload File",
        config: { fileTypes: ["csv", "json"] }
      },
      {
        id: "step-2", 
        type: "process",
        name: "Analyze Data",
        config: { tool: "data-analyzer" }
      }
    ],
    template: "data-processing",
    status: "draft",
    created: "2025-01-15"
  }
]

// templates: Pre-built workflows
const templates = [
  {
    id: "data-processing",
    name: "Data Processing",
    description: "Basic data analysis workflow",
    steps: [ /* template steps */ ]
  }
]
```

## Workflow Templates
- **Data Processing** - File upload, analysis, report
- **Content Creation** - Input, AI processing, output
- **Research Pipeline** - Query, search, synthesize
- **Custom** - Build from scratch

## Design System
- **Colors:** Blue theme with professional dark mode
- **Layout:** Canvas-style workflow builder
- **Responsive:** Mobile-friendly workflow viewing

---

## Future Enhancements (After MVP)
- Visual drag-and-drop builder
- Real automation execution
- AI agent integration
- Performance monitoring
- Team workflow sharing

Start with the MVP: Create a simple workflow management interface with templates and step-by-step builder with dark mode.
