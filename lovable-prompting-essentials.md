# Lovable AI Prompting Essentials

## CLEAR Framework 2.0

**C**oncise: Surgical precision, no filler  
❌ "Make login better" → ✅ "Set login button padding py-3 px-6, background #3B82F6, text white"

**L**ogical: Single-step focus  
❌ "Build signup + stats + blue buttons" → ✅ Three separate prompts

**E**xplicit: Zero assumptions  
❌ "Add profiles" → ✅ "Create UserProfile.js with avatar, name, email. Props: userId (string), showEdit (boolean)"

**A**daptive: Specific feedback vs "Try to Fix"  
"Email validation missing. Add regex check before form submission"

**R**eflective: Track successful patterns

## Knowledge Base Setup
```
PROJECT: [Purpose + audience in one sentence]

DESIGN SYSTEM:
- Colors: Primary #3B82F6, Secondary #64748B
- Buttons: rounded-lg py-2 px-4
- Cards: border border-gray-200 rounded-lg p-4

FEATURES: [3-5 numbered core features]
CONSTRAINTS: [Critical rules that never change]
```

## Front-End First: Risk Mitigation

**Process**: Static UI → Perfect with mock data → Connect backend surgically

```
Static Phase:
"Create UserGrid.js with hardcoded array:
const mockUsers = [{id: 1, name: 'John', status: 'active'}]
Build complete grid functionality."

Connection Phase:
"Replace mock data with Supabase query.
Add error handling and loading states."
```

## Advanced Techniques

### Visual Prompting
- Screenshots + "Build with this layout"
- Design mockups + "Create components matching this"
- Broken UI image + arrows + "Fix alignment shown in red"

### Context Anchoring (Prevent Memory Loss)
```
"Add search feature.

ANCHOR: Task management app, blue theme #3B82F6, 
admin/member roles, Supabase auth.

[Feature details]"
```

### Safe Refactoring
```
"Refactor UserProfile.js into sub-components.

CRITICAL: External API unchanged, all props identical, 
functionality preserved. Internal improvement only."
```

## Error Prevention & Recovery

### Anti-Loop Protocol
1. STOP "Try to Fix"
2. Chat Mode: "Analyze without changes"  
3. Review diagnosis
4. If complex: Revert to stable version

### Quality Gates
**Pre-prompt**: Single goal, constraints identified  
**Post-change**: Works as intended, zero console errors, mobile responsive
