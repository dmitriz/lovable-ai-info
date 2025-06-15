# MCP Server Manager

**Task:** Create a simple server configuration manager with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no external connections initially)
- Basic configuration templates and management

**Constraints:**
- Start with configuration storage only
- Single page application
- No actual server connections in MVP

---

## MVP Features (Build First)

1. **Server List** - Display configured servers with status
2. **Configuration Form** - Add/edit server configurations
3. **Template Library** - Pre-built configuration templates
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// servers: Array stored in localStorage
const servers = [
  {
    id: "uuid",
    name: "Development Server",
    type: "mcp-server",
    config: {
      host: "localhost",
      port: 3000,
      protocol: "http",
      endpoints: ["/api/chat", "/api/tools"]
    },
    template: "basic-mcp",
    status: "configured",
    created: "2025-01-15"
  }
]

// templates: Pre-built configurations
const templates = [
  {
    id: "basic-mcp",
    name: "Basic MCP Server",
    description: "Standard MCP server configuration",
    config: { /* template config */ }
  }
]
```

## Configuration Templates
- **Basic MCP** - Standard server setup
- **Development** - Local development configuration
- **Production** - Production-ready settings
- **Custom** - User-defined configurations

## Design System
- **Colors:** Green theme with professional dark mode
- **Layout:** Server cards with configuration panels
- **Responsive:** Mobile-friendly management interface

---

## Future Enhancements (After MVP)
- Real server health monitoring
- Automated deployment features
- Team configuration sharing
- Performance metrics dashboard
- Integration with container platforms

Start with the MVP: Create a simple server configuration manager with templates and dark mode support.
