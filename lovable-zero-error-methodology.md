# Lovable Zero-Error Methodology

*Updated Jan 2025 - Based on official prompting handbook + community insights*

## Core Problem + Solution
**Problem**: 20x speed → fragile code + infinite error loops + wasted credits  
**Solution**: Systematic constraints that preserve speed while eliminating fragility

## Three Pillars

### 1. Constrained Scope
**Rule**: One prompt = one feature = one file change
**Why**: Prevents AI confusion and reduces error cascade
**How**: Use explicit file protection in every prompt

### 2. Persistent Context  
**Rule**: Knowledge Base + context anchoring prevents AI memory loss
**Why**: LLMs forget early instructions (context decay)
**How**: Always reference Knowledge Base in prompts

### 3. Mobile-First Integration
**Rule**: Every prompt includes responsive design requirement
**Why**: 50%+ of users access via mobile, most errors are responsive failures
**How**: Add mobile-first constraint to every single prompt

## Setup: Knowledge Base Template (Copy-Paste)
```
PROJECT: [One sentence: what it does + who for]

TECH STACK: React/Vite + Tailwind CSS + ShadCN + Supabase

DESIGN SYSTEM:
- Colors: Primary #3B82F6, Secondary #64748B, Accent #10B981
- Typography: Inter font, clean hierarchy
- Components: rounded-lg, consistent spacing (p-4, gap-4)
- Mobile-first responsive all breakpoints

USER FLOW: Users start at [page] → [action] → [result] → [next step]

FEATURES (In-Scope):
1. [Feature] - [Brief description]
2. [Feature] - [Brief description] 
3. [Feature] - [Brief description]

CONSTRAINTS:
- Mobile-first responsive design
- [Critical business rule]
- [Security requirement]

OUT OF SCOPE: [List what's not included]
```

## The 4-Part Precision Prompt
```
Context: "You are a senior React developer specializing in [domain]"
Task: "Implement [single specific feature]"
Guidelines: "Use ShadCN + Tailwind. Mobile-first responsive on all breakpoints."
Constraints: "Don't modify [specific files]. Focus only on [target component]."
```

## Front-End First Doctrine
**Why**: Isolates UI bugs from backend complexity

### Phase 1: Static UI (Always First)
```
"Create [Component] with mock data:
const mockData = [{id: 1, name: 'Example', status: 'active'}]

Build complete UI with this static data. Include loading/empty states.
Mobile-first responsive design. Don't modify [other files]."
```

### Phase 2: Surgical Backend Connection  
```
"Connect [Component] to Supabase [table]:
Replace mock data with real queries. Add error handling.
Don't modify other components."
```

### Phase 3: Enhancement Only After Success
```
"Add [specific enhancement] to working [Component]:
[Detailed requirement]
Maintain existing functionality. Don't modify other files."
```

## Error Recovery Protocol (Critical)

### When Error Loops Start:
1. **STOP** clicking "Try to Fix" after 2nd failure
2. Switch to **Chat Mode**
3. Ask: **"Something's off. Walk me through what's happening"**
4. Get diagnosis **without changes first**
5. If unclear: **"What fixes have we tried?"**
6. Last resort: **Revert to stable version**

### Prevention (Use Every Time):
- Single feature per prompt
- Always include mobile responsiveness
- Explicit file protection constraints
- Reference Knowledge Base context
- Test after every change

## Success Metrics
- **95%+ first-attempt success** with reviewed prompts
- **Zero infinite loops** from constrained prompts  
- **50% fewer credits used** vs unconstrained development
- **Consistent progress** without major setbacks

---

*See `/implementation/` folder for copy-paste templates and detailed procedures.*
Replace mock data with database queries.
Add error handling and loading states."
```

## Build in Bricks: Single-Feature Development

❌ **Monolithic**: "Build user management with CRUD, roles, profiles, activity tracking"  
✅ **Brick-by-Brick**:
1. "Create read-only user list"
2. "Add user creation form"  
3. "Add edit functionality"
4. "Add delete with confirmation"
5. "Add role assignment"

**Rule**: Test each brick thoroughly before next.

## Error Prevention Strategies

### Context Anchor (Prevent AI Memory Loss)
```
"Add user profile editing.

CONTEXT ANCHOR:
- Task management app for remote teams
- Roles: admin, manager, member
- Theme: Blue (#3B82F6) with dark mode
- Auth: Supabase email/password

[Feature request details]"
```

### Anti-Loop Recovery Protocol
```
When stuck in infinite errors:
1. STOP "Try to Fix" immediately
2. Chat Mode: "Analyze error without changes"
3. Read diagnosis carefully
4. If complex: Revert to stable version
5. Try different approach entirely
```

### Emergency Escapes
- **Revert**: Version history → last working state
- **Remix**: Clone project → fresh AI context  
- **Isolate**: Build component in blank project

## Database Integration Templates

### Table Creation
```
"Create Supabase table [name] for [purpose]:

Schema:
- id: UUID primary key (uuid_generate_v4())
- [field]: [type] [constraints] -- [description]
- created_at: timestamptz default now()

Security:
- Enable RLS
- Policy: auth.uid() = [ownership_field]

Show SQL before applying."
```

### Auth Flow
```
"Implement auth flow:
- Pages: /signup, /login, /dashboard
- Flow: signup → verify → login → dashboard
- Errors: clear messages, retry options
- Logout: clear session → home

Don't modify: Navigation component"
```

## Quality Gates

### Pre-Implementation
- [ ] Feature split into 3-4 focused prompts
- [ ] Knowledge Base current
- [ ] Mock data ready
- [ ] Protected components identified

### Post-Implementation  
- [ ] Feature works as intended
- [ ] Zero console errors
- [ ] Mobile responsive
- [ ] Existing features unaffected

## Success Metrics
**Expert Level**: 95%+ first-try success, zero error loops, consistent quality  
**Warning Signs**: Frequent fixes, AI ignoring constraints, declining code quality
