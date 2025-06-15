# Lovable AI Quick Reference

## Emergency Debug Protocol
```
Error loop? → STOP "Try to Fix" → Chat Mode: "Analyze without changes"
→ Review diagnosis → If complex: Revert → Try different approach
```

## 4-Part Precision Template
```
Context: "You are [role] specializing in [domain]"
Task: "Implement [single feature]"
Guidelines: "Use [tech]. Follow [patterns]"
Constraints: "Don't modify [files]. Use [systems]"
```

## Essential Templates

### App Creation
```
"Create [app type] with MVP features:
- User auth (email/password via Supabase)
- [Primary feature with specifics]
- Mobile-responsive UI (Tailwind)
- Start with static/mock data for UI"
```

### Feature Addition
```
"Add [feature] to [component]:
Functionality: [detailed behavior]
UI: [specific styling/layout]
Data: [requirements/validation]
CRITICAL: Don't modify [existing components]"
```

### Database Schema
```
"Create Supabase table [name]:
- id: UUID primary key (uuid_generate_v4())
- [field]: [type] [constraints]
- created_at: timestamptz default now()
Security: Enable RLS, policy: auth.uid() = [field]
Show SQL before applying."
```

### Secure API
```
"Create Edge Function [name]:
Purpose: [goal] | Input: [params] | API: [service]
Security: Store [KEY] in env vars | Output: [format]
Never expose keys client-side."
```

### Auth Setup
```
"Implement auth flow:
Pages: /signup, /login, /dashboard
Flow: signup → verify → login → dashboard
Errors: clear messages | Success: redirect
Don't modify: Navigation component"
```

## Development Patterns

### Front-End First
```
Phase 1: "Create [Component] with mock data:
const mockData = [{id: 1, name: 'Example'}]"

Phase 2: "Connect to Supabase [table]:
Replace mock data with real queries + error handling"
```

### Single-Brick Development
❌ "Add search + filters + sorting + pagination"  
✅ Four separate prompts for each feature

### Context Anchoring
```
"Add [feature].

ANCHOR: [App type], [theme], [roles], [auth method]

[Feature details]"
```

## Quality Gates

### Before Each Prompt
- [ ] Single, specific goal
- [ ] Constraints identified  
- [ ] Protected components noted

### After Each Change
- [ ] Works as intended
- [ ] Zero console errors
- [ ] Mobile responsive
- [ ] Existing features intact

## Success Indicators
**✅ Expert level**: 95%+ first-try success, zero error loops, consistent quality  
**🚨 Warning signs**: Frequent fixes, ignored constraints, declining code quality

## Emergency Commands
- **Stuck**: Chat Mode → "Investigate without changes"
- **Memory loss**: "IMPORTANT: You missed [constraint]. Redo following this rule"
- **Messy code**: "Review [component] for issues. Provide improvement plan without implementing"
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
