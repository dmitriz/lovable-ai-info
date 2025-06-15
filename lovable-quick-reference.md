# Lovable AI Quick Reference: Fast, Precise, Error-Free

## Emergency Debug Protocol
```
When stuck in error loops:
1. STOP clicking "Try to Fix"
2. Chat Mode: "Analyze this error without making changes"
3. Review AI diagnosis
4. If complex: Revert to last stable version
5. Try different approach
```

## Power Prompt Templates

### The 4-Part Precision Template
```
Context: "You are a [specific expertise] developer"
Task: "Implement [single specific feature]"
Guidelines: "Use [tech stack]. Follow [patterns]"
Constraints: "Don't modify [files]. Must use [existing systems]"
```

### Initial App Creation
```
"Create a [app type] with essential features only:

Core MVP:
- User auth (email/password via Supabase)
- [Primary feature with specific requirements]
- Clean, mobile-responsive UI (Tailwind CSS)
- PostgreSQL database with basic schema

Constraints:
- Start with static/mock data for UI
- No third-party integrations yet
- Focus on single user flow"
```

### Safe Feature Addition
```
"Add [feature name] to [specific page/component]:

Functionality:
- [Detailed behavior description]
- [Data requirements and validation]
- [User permission rules]

UI Requirements:
- [Specific styling needs]
- [Mobile responsive behavior]
- [Accessibility considerations]

CRITICAL: Don't modify [existing components]. Use existing [design system/styles]."
```

### Database Schema Creation
```
"Create Supabase table [table_name] for [purpose]:

Fields:
- id: UUID primary key (uuid_generate_v4())
- [field]: [postgres_type] [constraints] - [description]
- created_at: timestamptz default now()
- [foreign_key]: UUID references [other_table](id)

Security:
- Enable Row Level Security
- Policy: [specific access rule]
- Example: auth.uid() = user_id for user-owned data

Show me the SQL before applying changes."
```

### Secure API Integration
```
"Create Supabase Edge Function [function-name]:

Purpose: [specific goal - be explicit]
Input: JSON payload with [parameters]
External API: [service name and endpoint]
Security: Store [API_KEY_NAME] in environment variables
Output: Return structured JSON with [fields]

CRITICAL: Never expose API keys client-side."
```

### Visual Debugging Template
```
"Fix the UI issue shown in attached screenshot:

Problem: [specific visual issue]
Expected: [how it should look/behave]
Location: [page/component affected]
Constraints: [what not to change]

Screenshot: [attach image with arrows/circles highlighting issue]"
```

### Authentication Setup
```
"Implement secure user authentication:

Flow: Email/password signup → verification → login → dashboard
Pages: /signup, /login, /dashboard
Components: AuthForm, ProtectedRoute, UserProvider
Database: profiles table linked to auth.users
Redirects: Success → /dashboard, Logout → /

Don't modify: existing [Navigation] component"
```

## Lightning-Fast Development Patterns

### The 90-Second Feature Pattern
1. **15s Planning**: Know exactly what you want
2. **45s Prompting**: Use 4-part template with specifics
3. **30s Testing**: Verify it works immediately

### Front-End First Strategy
```
Phase 1: Static UI
"Create [component] with mock data:
const mockData = [hardcoded examples]
Show complete UI working with this data."

Phase 2: Backend Connection
"Connect [component] to Supabase [table].
Replace mock data with real database queries."
```

### Single-Brick Development
**Never**: "Add search, filters, sorting, and pagination"  
**Always**: One feature per prompt
1. "Add search functionality to user list"
2. "Add filter dropdown for user status"  
3. "Add sorting by name and date"
4. "Add pagination with 10 items per page"

## Critical Error Prevention

### Context Anchor Strategy
Repeat key constraints in every related prompt:
```
"Add [feature]. 

PROJECT CONTEXT:
- Task management app for teams
- Users: admin, manager, member roles
- Theme: Blue (#3B82F6) with dark mode
- Auth: Supabase email/password only

[Your specific feature request]"
```

### Safe Refactoring Protocol
```
"Refactor [component] to improve [specific aspect]:

CRITICAL CONSTRAINTS:
- External API must remain unchanged
- All prop names must stay the same
- Existing functionality must work identically
- Component behavior cannot change

Goal: [internal improvement without breaking anything]"
```

## Emergency Recovery Commands

### When Stuck in Error Loops
```
STOP → Chat Mode → "Investigate this without changes"
```

### When AI Ignores Instructions
```
"IMPORTANT: You missed the constraint about [specific requirement]. 
Please redo the last change while following this rule: [repeat constraint]"
```

### When Code Gets Messy
```
"Review [component] and identify issues with:
- Code organization
- Performance problems  
- Potential bugs
- Style inconsistencies

Provide improvement plan without implementing changes."
```

## Quality Gates Checklist

### Before Each Prompt
- [ ] Single, specific goal defined
- [ ] Key constraints identified
- [ ] Success criteria clear
- [ ] Related components protected

### After Each Change
- [ ] Feature works as intended
- [ ] No console errors
- [ ] Mobile responsive
- [ ] Existing features still work

### Before Moving On
- [ ] Thoroughly tested
- [ ] Version pinned
- [ ] Knowledge Base updated
- [ ] Ready for next increment

## Success Indicators

**✅ You're expert-level when:**
- 90%+ prompts work on first try
- Zero infinite error loops
- AI consistently follows your style
- Development feels rapid but controlled

**🚨 Warning signs:**
- Burning credits on fixes
- AI ignoring specific instructions  
- Code quality declining
- More debugging than building
Is it a logic/data problem?
    ↓ YES → Switch to Chat Mode
    ↓ NO
Is it breaking the app?
    ↓ YES → Restore last stable version
    ↓ NO
Try specific prompt with clear context
    ↓
Still not working after 2 attempts?
    ↓ YES → Chat Mode investigation
    ↓ NO → Continue development
```

## Best Practices Checklist

**Before Each Prompt:**
- [ ] Clear objective defined
- [ ] Specific requirements listed
- [ ] Context provided (page/component)
- [ ] Constraints mentioned
- [ ] Success criteria established

**After Each Change:**
- [ ] Test functionality works
- [ ] Check for console errors
- [ ] Verify responsive design
- [ ] Confirm it meets requirements
- [ ] Pin version if major milestone

**Regular Maintenance:**
- [ ] Update Knowledge Base with new features
- [ ] Review and clean up unused components
- [ ] Test with different user roles
- [ ] Monitor app performance
- [ ] Sync with GitHub regularly
