# AI Guardrails Policy Dashboard

**Task:** Create a simple policy management dashboard with local storage.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for all data (no database initially)
- Clean policy template interface

**Constraints:**
- Start with basic policy CRUD operations only
- Single page application
- No external APIs in MVP

---

## MVP Features (Build First)

1. **Policy List** - Display policies with name, type, and status
2. **Add Policy** - Form to create new policies with templates
3. **Policy Templates** - Pre-built templates (GDPR, Security, etc.)
4. **Dark Mode** - Toggle between light and dark themes

## Data Structure (Local Storage)
```javascript
// policies: Array stored in localStorage
const policies = [
  {
    id: "uuid",
    name: "GDPR Compliance",
    type: "data-privacy",
    rules: ["No personal data logging", "User consent required"],
    status: "active",
    created: "2025-01-15"
  }
]
```

## Policy Templates
- **Data Privacy** - GDPR, CCPA guidelines
- **Security** - Access control, API security
- **Content Safety** - Content moderation rules
- **Custom** - User-defined policies

## Design System
- **Colors:** Professional blue theme with dark mode
- **Layout:** Card-based with clear policy status indicators
- **Responsive:** Mobile-first design

---

## Future Enhancements (After MVP)
- Real-time violation monitoring
- AI system integration and alerts
- Compliance reporting and exports
- Risk assessment scoring
- Team collaboration features

Start with the MVP: Create a simple policy management interface with templates and dark mode support.
