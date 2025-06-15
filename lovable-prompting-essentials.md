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

## Four Levels of Prompting Mastery (2025 Update)

### Level 1: Training Wheels Prompting
```
Context: You are a world-class Lovable AI coding assistant
Task: Create a secure login page in React using Supabase
Guidelines: Minimalistic UI, Tailwind CSS, clear code comments
Constraints: Only modify LoginPage component, ensure working output
```

### Level 2: Conversational Prompting
Natural but complete instructions without rigid structure:
"Build a profile picture upload feature with image file input, submit button, Supabase storage integration, and graceful error handling for oversized files."

### Level 3: Meta Prompting
Use AI to improve your prompts:
"Rewrite this prompt to be more concise and detailed: 'Create a secure login page in React using Supabase, ensuring role-based authentication.'"

### Level 4: Reverse Meta Prompting
Document successful solutions for reuse:
"Summarize the JWT authentication errors we resolved and create a reusable prompt template to avoid these issues in future auth implementations."

## Knowledge Base Setup
```
PROJECT: [Purpose + audience in one sentence]

PROJECT REQUIREMENTS DOCUMENT (PRD):
- Introduction: App purpose and target users
- Core Features: 3-5 numbered primary features  
- Tech Stack: Frontend, Backend, Integrations, Libraries
- User Flow: Start → Action → Result → End state
- Design Principles: Color palette, typography, layout patterns
- In-Scope vs Out-of-Scope: Clear boundaries

DESIGN SYSTEM:
- Colors: Primary #3B82F6, Secondary #64748B, Error #EF4444
- Typography: Font families, sizes, weights, line heights
- Components: Button styles, card patterns, form elements
- Spacing: Consistent padding/margin system (4px grid)
- Breakpoints: mobile-first responsive strategy

BACKEND STRUCTURE (if using Supabase):
- Authentication: User roles, permissions, signup flow
- Database: Table relationships, constraints, indexes
- Storage: File upload patterns, bucket organization
- Security: RLS policies, API endpoints, data validation

FRONTEND GUIDELINES:
- Component Structure: Atomic design principles
- State Management: Context patterns, data flow
- Navigation: Route structure, protected routes
- Error Handling: User feedback, fallback states
```

### Enhanced Knowledge Base Prompt
```
Before writing any code, please review the Knowledge Base and confirm your understanding of:
1. The app's core purpose and user flow
2. Design system constraints and patterns  
3. Tech stack requirements and integrations
4. Feature scope and explicit limitations

Then proceed with implementation following these established guidelines.
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

### Advanced Anti-Loop Protocol (2025 Update)
```
PHASE 1: Initial Investigation
"The same error continues to occur. Take a moment to perform a preliminary investigation to uncover the root cause. Examine logs, workflows, and dependencies to gain insight into the problem. Avoid making any changes until you fully grasp the situation."

PHASE 2: Deep Analysis (if still failing)
"The issue persists without resolution. Perform a thorough analysis of the flow and dependencies, halting all modifications until the root cause is identified with complete certainty. Record the failures, reasons, and observed patterns."

PHASE 3: System Review (if critical)
"This is a pressing issue that necessitates a thorough re-evaluation of the entire system. Map the flow systematically—authentication, database interactions, integrations, state management, and redirects. Evaluate each component individually to pinpoint failures."

PHASE 4: Comprehensive Audit
"Generate a clear and detailed report outlining expected behaviors, current realities, and discrepancies. Refrain from suggesting code changes until you have accurate, evidence-based insights."
```

### Chat Mode vs Default Mode Strategy
**Chat Mode Usage:**
- Error analysis and debugging discussion
- Feature planning and architectural decisions  
- Code review and optimization strategies
- Meta prompting and prompt improvement

**Default Mode Usage:**
- Direct code implementation after planning
- Applying specific fixes identified in Chat Mode
- Building features with clear specifications
- Making targeted changes to existing code

### Quality Gates
**Pre-prompt**: Single goal, constraints identified  
**Post-change**: Works as intended, zero console errors, mobile responsive
**Verification**: Test core functionality, check related components
