# Smart Issue Labeler

**Task:** Create a simple issue management tool with automatic labeling using local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no external APIs initially)
- Simple rule-based labeling system

**Constraints:**
- Start with manual issue entry and basic labeling
- Single page application
- No GitHub API in MVP

---

## MVP Features (Build First)

1. **Issue List** - Display issues with title, labels, and status
2. **Add Issue** - Form to create new issues manually
3. **Label Rules** - Simple keyword-based auto-labeling
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// issues: Array stored in localStorage
const issues = [
  {
    id: "uuid",
    title: "Bug in login page",
    body: "Login form not submitting",
    labels: ["bug", "frontend"],
    status: "open",
    created: "2025-01-15"
  }
]

// labelRules: Auto-labeling rules
const labelRules = [
  { keywords: ["bug", "error", "broken"], label: "bug" },
  { keywords: ["feature", "enhancement"], label: "enhancement" },
  { keywords: ["question", "help"], label: "question" }
]
```

## Auto-Labeling Rules
- **Bug Detection** - Keywords: bug, error, broken, crash
- **Feature Requests** - Keywords: feature, enhancement, improve
- **Questions** - Keywords: question, help, how to
- **Priority** - Keywords: urgent, critical, minor

## Design System
- **Colors:** GitHub-inspired blue theme with dark mode
- **Layout:** Issue cards with label badges
- **Responsive:** Mobile-first design

---

## Future Enhancements (After MVP)
- GitHub API integration
- AI-powered classification
- Bulk processing capabilities
- Team productivity analytics
- Webhook automation

Start with the MVP: Create a simple issue tracker with basic keyword-based auto-labeling and dark mode.
