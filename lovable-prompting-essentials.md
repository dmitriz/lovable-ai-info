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

## The Front-End First Doctrine: Risk Mitigation Strategy

**Why**: Separates UI/layout issues from backend/database errors - the two biggest failure sources

**Process:**
1. **UI Phase**: Build complete interface with mock/static data
2. **Perfect Phase**: Refine layout, components, responsiveness with static data
3. **Connection Phase**: Connect to Supabase backend surgically, one piece at a time

**Example Mock Data Prompt:**
```
"Create UserGrid.js component displaying users in grid format. Use this hardcoded array for now:
const mockUsers = [
  {id: 1, name: 'John Doe', status: 'Active', email: 'john@example.com'},
  {id: 2, name: 'Jane Smith', status: 'Pending', email: 'jane@example.com'}
]"
```

## Advanced Prompting Techniques

### Visual Prompting: Screenshot > 1000 Words
- **Layout Cloning**: Screenshot desired layout + "Build landing page with this structure"
- **Design Implementation**: Upload Figma mockup + "Create components matching this design"
- **Visual Debugging**: Screenshot broken UI with arrows + "Fix alignment issue shown in red circle"

### Prompt Chaining for Complex Features
Break large features into 3-4 focused prompts:
1. "Create the UI components"
2. "Connect UI to backend endpoint"  
3. "Handle success and error states"
4. "Add form validation and user feedback"

### Safe Refactoring Protocol
**Critical**: Refactoring is highest-risk operation

**Safe Refactoring Prompt Template:**
```
"Refactor UserProfile.js component into smaller sub-components for avatar, details, and actions.

CRITICAL CONSTRAINTS:
- Do not change any prop names UserProfile.js accepts
- External API must remain identical
- All existing functionality must be preserved
- Component behavior must be unchanged"
```

## The "Build in Bricks" Methodology

**Never**: Multiple features in one prompt  
**Always**: One discrete functionality at a time

**Single Feature Development Flow:**
1. **Connect for Read**: Link UI component to database table (READ operation only)
2. **Test**: Verify data displays correctly
3. **Connect for Write**: Add form/logic for creating entries (CREATE)
4. **Test**: Verify new entries appear in list
5. **Add Update**: Implement edit functionality
6. **Add Delete**: Implement removal with confirmation
7. **Test All**: Complete CRUD operations work
8. **Move to Next Feature**: Only after current "brick" is solid

## Error Prevention & Recovery

### Context Decay Prevention
**Problem**: AI "forgets" early instructions as conversation grows  
**Solution**: Repeat critical constraints in every related prompt

**Example:**
"Add sorting to the user table. REMINDER: This table must remain in UserDashboard.js and use existing Tailwind classes from our design system."

### The Anti-Loop Protocol
When stuck in infinite error fixing:

1. **STOP** clicking "Try to Fix"
2. **Switch to Chat Mode**: "Analyze this error without making changes"
3. **Get diagnosis**: Let AI explain root cause
4. **If complex**: Use Version History to revert to stable state
5. **Fresh approach**: Try different implementation method

### Emergency Escape Strategies
- **Revert**: Use version history to return to last working state
- **Remix**: Clone project code into fresh instance (resets AI context)
- **Isolate & Rebuild**: Test broken component in separate blank project

## Quality Gates: Speed Without Sacrifice

### Pre-Implementation Checklist
- [ ] Knowledge Base contains current project state
- [ ] Feature broken into single-responsibility prompts  
- [ ] Constraints clearly specified
- [ ] Mock data prepared for frontend-first approach

### Post-Implementation Verification
- [ ] Feature works with test data
- [ ] No existing functionality broken
- [ ] UI responsive on mobile
- [ ] Error states handled gracefully
- [ ] Ready for next incremental addition

### Success Indicators
**✅ You're succeeding when:**
- Each prompt produces working, testable code
- AI consistently follows your project conventions
- You can add features without breaking existing ones
- Development velocity increases over time

**🚨 Warning signs:**
- Burning credits on repetitive fix attempts
- AI ignoring specific constraints
- New features breaking old ones
- Generic code that doesn't match project style
