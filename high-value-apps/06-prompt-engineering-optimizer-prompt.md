# Prompt Engineering Optimizer

**Task:** Create a simple prompt testing and management tool with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no external APIs initially)
- Basic prompt template management

**Constraints:**
- Start with manual prompt testing only
- Single page application
- No AI platform integration in MVP

---

## MVP Features (Build First)

1. **Prompt Library** - Create and save prompt templates
2. **Test Results** - Track prompt performance manually
3. **Version Control** - Keep prompt revision history
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// prompts: Array stored in localStorage
const prompts = [
  {
    id: "uuid",
    name: "Code Review Prompt",
    template: "Review this code for...",
    category: "development",
    versions: [
      {
        version: "1.0",
        content: "Review this code...",
        notes: "Initial version",
        created: "2025-01-15"
      }
    ],
    tests: [
      {
        id: "test-uuid",
        input: "Test input",
        output: "Test output",
        rating: 4,
        notes: "Good but could be better"
      }
    ]
  }
]
```

## Prompt Features
- **Template Management** - Organize prompts by category
- **Version Control** - Track changes and improvements
- **Manual Testing** - Record test results and ratings
- **Search & Filter** - Find prompts by name or category

## Design System
- **Colors:** Purple theme with professional dark mode
- **Layout:** Split view with template list and editor
- **Responsive:** Mobile-friendly editing interface

---

## Future Enhancements (After MVP)
- Multi-platform AI testing (OpenAI, Anthropic, Google)
- A/B testing with statistical analysis
- Automated performance metrics
- Cost analysis and optimization
- Team collaboration features

Start with the MVP: Create a simple prompt library with version control and manual testing capabilities with dark mode.
