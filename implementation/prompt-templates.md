# Prompt Templates: Copy-Paste Ready

*Based on latest Lovable prompting handbook (Jan 2025) and community-proven patterns*

## 🚀 Foundation Templates

### Project Initialization (Copy-Paste)
```
I need a [type] application with:

TECH STACK:
- Frontend: React/Vite with Tailwind CSS
- Backend: Supabase (auth, database, storage)
- Styling: ShadCN components + Tailwind utilities

CORE FEATURES:
1. [Primary feature with user action]
2. [Secondary feature with user action]  
3. [Third feature with user action]

DESIGN REQUIREMENTS:
- Mobile-first responsive design
- Modern UI/UX following current best practices
- Clean, minimal interface focusing on usability

Start with the main page containing:
[Detailed page requirements - be specific about layout, components, and interactions]

Always make things responsive on all breakpoints, with focus on mobile first. Use ShadCN and Tailwind built-in breakpoints instead of anything custom.
```

### Knowledge Base Setup (Essential)
```
PROJECT: [One sentence: what it does + who for]

TECH STACK: React/Vite + Tailwind CSS + ShadCN + Supabase

DESIGN SYSTEM:
- Colors: Primary #3B82F6, Secondary #64748B, Accent #10B981
- Typography: Inter font family, clean hierarchy
- Components: Rounded corners (rounded-lg), consistent spacing (p-4, gap-4)
- Buttons: Primary style with hover states, disabled states

USER FLOW:
[Start] → [Action] → [Result] → [Next Step]
Users begin on [page], can [action], which leads to [outcome]

FEATURES (In-Scope):
1. [Feature] - [Brief description]
2. [Feature] - [Brief description]
3. [Feature] - [Brief description]

CONSTRAINTS:
- Mobile-first responsive (all breakpoints)
- [Business rule]
- [Security requirement]
- [Performance requirement]

OUT OF SCOPE:
- [Feature not included]  
- [Integration not needed]
```

---

## 💡 Development Templates

### New Feature Development (3-Step Process)
```
STEP 1 - Static UI:
"Create [FeatureName] component with mock data:
const mockData = [{id: 1, name: 'Example', status: 'active'}]

Build complete UI functionality with this static data. Include:
- [Specific UI requirement 1]
- [Specific UI requirement 2]
- Loading and empty states

Focus only on this component. Don't modify [list other files]."

STEP 2 - Backend Connection:
"Connect [FeatureName] to Supabase [table_name]:
- Replace mock data with real database queries
- Add proper error handling
- Include loading states
- Don't modify other components or files"

STEP 3 - Enhancement:
"Add [specific enhancement] to [FeatureName]:
[Detailed requirements]
Maintain existing functionality. Don't modify other components."
```

### Mobile-First Responsive (Required for Every Prompt)
```
"Always make things responsive on all breakpoints, with focus on mobile first. 
Use modern UI/UX best practices for determining how breakpoints should change components. 
Use ShadCN and Tailwind built-in breakpoints instead of anything custom, 
unless user prompts for custom breakpoints directly.

Optimize for mobile without changing design or functionality. 
Analyze layout and responsiveness to identify necessary adjustments 
for smaller screens and touch interactions."
```

---

## 🛡️ Protection Templates

### File Protection (Copy to Every Prompt)
```
"Focus changes only on [specific file/component]. 
Please refrain from altering [list all files to protect] 
and focus changes solely on [target]."
```

### Delicate Update Protocol
```
"This update is quite delicate and requires utmost precision. 
Carefully examine all dependencies and potential impacts 
before implementing any changes, and test systematically 
to guarantee nothing is disrupted. Steer clear of shortcuts 
or assumptions—take a moment to seek clarification if unsure. 
Precision is crucial."
```

### UI-Only Changes
```
"Make solely visual enhancements—ensure functionality and logic 
remain unaffected. Gain comprehensive understanding of how 
existing UI interacts with the app, ensuring logic, state 
management, and APIs stay intact. Conduct extensive testing 
to verify the app operates precisely as it did before."
```

---

## 🔧 Debugging Templates

### Error Recovery Protocol
```
"Something's off. Can you walk me through what's happening 
and what you've tried? Don't make any changes yet - 
just analyze and explain the situation."
```

### Context Recovery
```
"Before you write any code, please review the Knowledge Base 
and share your understanding of my project. Confirm the 
current state and what we're trying to achieve."
```

### Infinite Loop Breaker
```
"Take a step back. Analyze this error and suggest a different 
approach. What fixes have we already tried? Let's try a 
completely different strategy."
```

---

## 📱 Specialized Templates

### Landing Page Creation
```
"Create a modern landing page with:

SECTIONS:
- Hero: Compelling headline + CTA button
- Features: 3-column grid of key benefits
- Social proof: Testimonials or logos
- Footer: Simple navigation links

DESIGN:
- Mobile-first responsive
- ShadCN components
- Modern gradients and animations
- Accessible color contrast

CONSTRAINTS:
- No backend integration yet
- Static content only
- Single page application"
```

### Dashboard Creation
```
"Create a dashboard page with:

LAYOUT:
- Sidebar navigation (collapsible on mobile)
- Top header with user info
- Main content area with cards/widgets
- Responsive grid system

COMPONENTS:
- Stats cards showing [specific metrics]
- Data table with [specific columns]
- Quick action buttons for [specific actions]

CONSTRAINTS:
- Use mock data initially
- Mobile-responsive design
- Don't implement authentication yet"
```

### Authentication Setup
```
"Implement user authentication using Supabase:

FEATURES:
- Sign up with email/password
- Login with email/password
- Password reset functionality
- Protected routes

REQUIREMENTS:
- Use Supabase Auth (not custom implementation)
- Redirect to dashboard after successful login
- Handle loading and error states
- Mobile-friendly forms

CONSTRAINTS:
- Don't modify existing pages
- Focus only on auth components"
```

---

## 📋 Quality Assurance Templates

### Pre-Implementation Check
```
"Before implementing, please:
1. Review the Knowledge Base to understand project context
2. Identify which files will be modified
3. Confirm the approach aligns with existing architecture
4. Outline the step-by-step implementation plan

Share this analysis before making any code changes."
```

### Testing Strategy
```
"Suggest a testing strategy for [component/feature] including:
- What to test and how
- Unit tests for business logic
- Integration tests for data flow  
- UI tests for critical user flows
- Best practices for mocking dependencies"
```

### Performance Optimization
```
"Optimize [component/feature] for performance without changing functionality:
- Identify potential bottlenecks
- Implement React best practices (useMemo, useCallback where appropriate)
- Optimize database queries if applicable
- Ensure mobile performance
- Test before and after to confirm improvements"
```

---

## 🎯 Success Patterns

### The 4-Part Precision Prompt
```
Context: "You are a [specific role] specializing in [domain]"
Task: "Implement [single specific feature]"
Guidelines: "Use [tech]. Follow [patterns]" 
Constraints: "Don't modify [files]. Must use [systems]"
```

### Meta Prompting (Prompt Improvement)
```
"Rewrite this prompt to be more concise and detailed: 
'[Your original prompt]'

Make it follow best practices for:
- Clarity and specificity
- Proper constraints
- Mobile-first approach
- Single-task focus"
```

### Reverse Meta Prompting (Learn from Debugging)
```
"Summarize the errors we encountered while [task] and 
how they were resolved. Create a detailed prompt I can 
use next time to avoid these issues."
```

---

## ⚠️ Common Mistakes to Avoid

### DON'T Do This:
```
❌ "Make the app better"
❌ "Fix all the bugs"  
❌ "Add some improvements"
❌ "Create a dashboard with everything"
❌ "Build the entire backend"
```

### DO This Instead:
```
✅ "Add a search filter to the ProductList component"
✅ "Fix the mobile navigation hamburger menu"
✅ "Implement email validation in the signup form"
✅ "Create user dashboard with profile section only"
✅ "Connect UserProfile component to Supabase profiles table"
```

---

*Last Updated: Based on Lovable Prompting Handbook (Jan 2025) + Community Reports*
