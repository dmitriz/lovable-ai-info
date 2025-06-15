# Lovable AI Prompting Essentials

## Core Principles for Effective Prompting

### 1. The CLEAR Framework
- **Concise**: Be direct, avoid filler words
- **Logical**: Break complex requests into ordered steps
- **Explicit**: State exactly what you want and don't want
- **Adaptive**: Refine prompts based on results
- **Reflective**: Learn from what works and what doesn't

### 2. Foundation Setup: Knowledge Base
Before any prompting, establish your project's "brain":
- Product vision and requirements
- User personas and journeys
- Key features and functionality
- Design guidelines and constraints
- Role-specific behaviors (Admin, User, etc.)

**Pro Tip**: Auto-generate knowledge base with: *"Generate knowledge for my project based on features implemented so far"*

## Optimal Prompt Structure

### Basic Template
```
Context: [Background/role setup]
Task: [Specific goal]
Guidelines: [Preferred approach]
Constraints: [Hard limits/must-not-dos]
```

### Effective Examples

**❌ Poor Prompt:**
"Make this app better"

**✅ Good Prompt:**
"On the `/dashboard` page, add a table showing recent transactions with pagination. Include columns for date, amount, status, and customer name. Use Tailwind CSS styling consistent with existing components."

## Development Workflow

### Chat Mode vs Default Mode
- **Chat Mode**: Planning, debugging, brainstorming (no code changes)
- **Default Mode**: Direct implementation when you have a clear plan

### Iterative Development Pattern
1. **Start Small**: Single feature at a time
2. **Test Immediately**: Verify each addition works
3. **Refine**: Use feedback to improve
4. **Expand**: Add next feature only after current one is stable

## Advanced Prompting Strategies

### Context Management
- **Reference Specifics**: Mention exact pages, components, or functions
- **Provide Examples**: Show desired format or behavior
- **Set Boundaries**: "Do not modify `Layout.tsx` while implementing this"

### Error Prevention
- **Version Control**: Pin stable versions after working features
- **Incremental Changes**: One feature per prompt
- **Clear Instructions**: Repeat critical requirements in follow-ups

### Visual Guidance
- Attach screenshots for UI changes
- Upload design mockups for styling reference
- Use Visual Editor for minor tweaks instead of prompts

## Common Pitfalls to Avoid

1. **Multiple Features in One Prompt**: Leads to generic, confused output
2. **Vague Descriptions**: Results in irrelevant or incorrect code
3. **Ignoring Context**: Not using Knowledge Base effectively
4. **Fighting the AI**: Continuing same prompt instead of rephrasing
5. **Complexity Overload**: Trying to build everything at once

## Quality Assurance

### Before Publishing
- Test all user flows manually
- Verify role-specific access controls
- Check responsive design on mobile
- Run security scan for vulnerabilities
- Validate database schema consistency

### Debugging Strategy
1. Use Chat Mode for complex issues
2. Compare version history when bugs appear
3. Ask AI to explain what changed between versions
4. Restore to last known good state if needed

## Success Metrics

**You're doing it right when:**
- Each prompt produces working, testable code
- The AI understands your project context
- You can iterate quickly without breaking existing features
- Your prompts are becoming more specific and effective over time

**Red flags:**
- Stuck in bug-fixing loops
- AI ignoring specific instructions
- Burning through credits without progress
- Generated code feels generic or disconnected
