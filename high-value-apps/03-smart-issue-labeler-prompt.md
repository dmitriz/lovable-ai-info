# Smart Issue Labeler

**Task:** Create a simple issue management tool with automatic labeling using local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no external APIs initially)
- Simple rule-based labeling system
- **Minimalistic Design Focus:** Create a very light design that minimizes vertical space usage. Each content line should take up as little vertical space as possible while using horizontal space more generously. Avoid extra visual elements between content lines - use only white spaces for separation. Focus on content over decoration with a clean, minimal aesthetic.

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

## Development Roadmap

**Start with MVP:** Create a simple issue tracker with basic keyword-based auto-labeling and dark mode.

### Phase 1: Basic Issue Management (MVP)
✅ Build foundation with manual issue entry, keyword labeling, and dark mode

### Phase 2: Advanced Labeling Rules
🔄 Add complex rule conditions, priority detection, and custom label categories

### Phase 3: GitHub API Integration
🔄 Connect to GitHub for automatic issue import and real-time synchronization

### Phase 4: AI-Powered Classification
🔄 Implement machine learning models for intelligent issue categorization

### Phase 5: Bulk Processing
🔄 Add batch operations for processing multiple issues simultaneously

### Phase 6: Analytics Dashboard
🔄 Create team productivity metrics and issue pattern analysis

### Phase 7: Automation & Webhooks
🔄 Enable automated workflows with webhook triggers and actions

### Phase 8: Multi-Repository Support
🔄 Expand to handle multiple repositories with centralized management

**Next Step After MVP:** Implement Phase 2 - Advanced Labeling Rules
