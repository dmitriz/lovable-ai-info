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

## Advanced Prompting & Debugging (2025)

### Meta Prompting
```
"Review my last prompt and suggest improvements for clarity and completeness."
"Rewrite this prompt to be more specific and detailed: '[Your original prompt]'"
```

### Reverse Meta Prompting
```
"Summarize the errors we encountered and how we resolved them. Create a reusable prompt template for future use."
```

### Debugging Escalation Protocol
```
1. STOP "Try to Fix" after 2nd failure
2. Chat Mode: "Walk me through what's happening"
3. Initial Investigation: "Preliminary analysis of logs, workflows, dependencies"
4. Deep Analysis: "Thorough review, halt changes until root cause is certain"
5. System Review: "Map entire flow, document discrepancies, no code edits until clear"
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

---

### Community CustomGPTs Workflow
```
STRUCTURED DEVELOPMENT PROCESS:
1. Base Prompt Generator: "Brain dump your idea, get structured Lovable prompt"
2. PRD Generator: "Create comprehensive project documentation"
3. Design Assistant: "Generate detailed design guidelines"
4. Upload docs to GitHub repo
5. Reference docs in every Lovable prompt
6. Use Debugging Wizard for systematic error resolution
```

### Refactoring Protocol (Community Standard)
```
TRIGGER: Files over 300 lines

REFACTORING PROMPT:
"Please refactor {filename.tsx} to break it into more manageable files but do not break any current functionality and do not make any design changes either. You are only permitted to split one main file into more smaller files. Make sure to delete any unused files/code as well, but once again DO NOT BREAK ANY FUNCTIONALITY. Make sure to tell me which files were created and their names when you are done."
```

### Preventing "Rogue" Behavior
```
FOUNDATION PROMPT:
"Read the project documentation and confirm your understanding of:
- Core project scope and limitations  
- Established design patterns
- Technical constraints
- Files that should not be modified
Then proceed with the requested change."
```

### Credit Conservation & Multi-Model Strategy
```
EXTERNAL AI ANALYSIS (ChatGPT, Claude):
"List all past build errors and conflicts in this project"
"Generate README with architecture, dependencies, tech stack"
"Review project roadmap and suggest optimizations"

DOCUMENTATION WORKFLOW:
1. Save analysis in Google Docs
2. Create "safe steps" summaries  
3. Document error patterns and solutions
4. Reference docs in Lovable prompts

EFFICIENT LOVABLE USAGE:
Chat Mode: "Create implementation plan for [feature]"
→ Click "Implement plan" button
→ Use Developer Mode for simple edits
```

### Prompt Length Optimization
```
SHORT PROMPT STRATEGY (Community Preference):
- Start minimal and focused
- Add context only when needed
- Monitor hallucination risk
- Single goal per prompt

EXAMPLE PROGRESSION:
1. "Add user authentication"
2. If unclear: "Add email/password authentication using Supabase"
3. If still issues: "Add Supabase auth with signup/login pages, redirect to dashboard"
```
