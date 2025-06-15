# Lovable AI Success Patterns

## The 90-10 Rule
**90% of success**: External planning + Knowledge Base + Front-end first + Single-brick development  
**10%**: Advanced debugging + complex integrations

## Core Development Patterns

### Pattern 1: Strategic Foundation
```
Pre-Lovable: Natural language concept → ChatGPT PRD → MVP feature list
Lovable: Knowledge Base → Static UI → Backend piece-by-piece
```

### Pattern 2: Surgical Integration
```
Per backend connection:
1. Verify Supabase setup manually
2. Create single table with explicit schema  
3. Connect ONE component to READ data
4. Test thoroughly → ADD CREATE → Test → ADD UPDATE/DELETE
```

### Pattern 3: Error Recovery
```
When stuck: STOP fixes → Chat Mode analysis → 
Clear diagnosis OR revert to stable → Different approach
```

## Precision Prompt Templates

### 4-Part Power Prompt
```
Context: "You are [role] specializing in [domain]"
Task: "Implement [single feature]"  
Guidelines: "Use [tech]. Follow [patterns]"
Constraints: "Don't modify [files]. Must use [systems]"
```

### Database Creation
```
"In Supabase, create table [name] with:
- id: UUID primary key (uuid_generate_v4())
- [field]: [type] [constraints]
- created_at: timestamptz default now()

Security: Enable RLS, policy: auth.uid() = [ownership_field]
Show SQL before applying."
```

### Secure Integration
```
"Create Edge Function [name]:
Purpose: [goal] | Input: [params] | External API: [service]
Security: Use env var [KEY_NAME] | Output: [format]
Never expose keys client-side."
```

## Error Prevention

### Context Anchor
```
"Add [feature].

ANCHOR: [App type], [theme], [user roles], [auth method]

[Feature details]"
```

### Meta-Prompting
"Refine this prompt for safety: '[draft prompt]'"

## Quality Assurance

### Pre-Implementation
- [ ] Feature split into 3-4 prompts
- [ ] Knowledge Base current  
- [ ] Mock data ready
- [ ] Protected components identified

### Post-Implementation
- [ ] Works as intended
- [ ] Zero console errors
- [ ] Mobile responsive  
- [ ] Existing features intact

## Success Metrics
**Expert Level**: 95%+ first-try success, zero loops, consistent quality  
**Warning Signs**: Frequent fixes, ignored constraints, declining quality
4. **Batch Changes**: Group related modifications in single prompts

### Development Speed
1. **Knowledge Base**: Keep it updated and comprehensive
2. **Templates**: Use proven prompt formulas
3. **Incremental**: Build and test small pieces
4. **Version Control**: Pin frequently, restore when needed

### Code Quality
1. **Review Output**: Always check generated code makes sense
2. **Test Thoroughly**: Manual testing catches AI blind spots
3. **Refactor Regularly**: Keep codebase clean and organized
4. **Export Early**: Use GitHub integration for complex projects
