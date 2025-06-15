# AI Agent Orchestrator Dashboard

**Task:** Create a simple dashboard for managing AI agents with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no database initially)
- Clean, minimalist UI with ShadCN components

**Constraints:**
- Start with core functionality only
- Single page application
- No external APIs in MVP

---

## MVP Features (Build First)

1. **Agent List** - Display agents with name, status, and capabilities
2. **Add Agent** - Simple form to register new agents 
3. **Agent Status** - Toggle between active/inactive states
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// agents: Array stored in localStorage
const agents = [
  {
    id: "uuid",
    name: "Agent Name",
    status: "active" | "inactive", 
    capabilities: ["text", "image", "code"],
    created: "2025-01-15"
  }
]
```

## Design System
- **Colors:** Blue theme with proper dark mode variants
- **Layout:** Card-based design with consistent spacing
- **Responsive:** Mobile-first, works on all screen sizes

---

## Future Enhancements (After MVP)
- Real-time monitoring dashboard
- Workflow builder with drag-and-drop
- Performance analytics and charts
- Database integration with Supabase
- Multi-agent coordination features

Start with the MVP: Create a simple agent management interface with add/edit/delete functionality and dark mode toggle.
