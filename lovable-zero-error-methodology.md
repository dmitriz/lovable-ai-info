# Lovable Zero-Error Methodology

## Core Problem + Solution
**Problem**: 20x speed → fragile code + infinite error loops + wasted credits  
**Solution**: Systematic constraints that preserve speed while eliminating fragility

## Three Pillars
1. **Constrained Scope**: One prompt = one feature
2. **Persistent Context**: Knowledge Base prevents AI memory loss  
3. **Surgical Integration**: Frontend first, then piece-by-piece backend

## Setup: Knowledge Base Template
```
PROJECT: [One clear sentence: purpose + audience]

TECH STACK: React/Vite + Tailwind + Supabase

DESIGN SYSTEM:
- Primary: #3B82F6 | Buttons: rounded-lg py-2 px-4
- Cards: border border-gray-200 rounded-lg p-4

FEATURES: [Numbered list of 3-5 core features]

CONSTRAINTS:
- Mobile-first responsive
- [Critical business rules]
- [User permission structure]
```

## The 4-Part Precision Prompt
```
Context: "You are a [specific role] specializing in [domain]"
Task: "Implement [single specific feature]"
Guidelines: "Use [tech]. Follow [patterns]"
Constraints: "Don't modify [files]. Must use [systems]"
```

## Front-End First Doctrine
**Why**: Isolates UI bugs from backend complexity

**Phase 1**: Static UI with mock data
```
"Create [Component] with hardcoded data:
const mockData = [{id: 1, name: 'Example'}]
Build complete UI functionality with this data."
```

**Phase 2**: Surgical backend connection
```
"Connect [Component] to Supabase [table]:
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
