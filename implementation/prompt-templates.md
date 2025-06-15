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

## 🛠️ Community CustomGPT Integration Templates

### Foundation-First Development (Community Best Practice)
```
PROJECT SETUP WORKFLOW:
1. "Use Lovable Base Prompt Generator to structure initial idea"
2. "Use Lovable PRD Generator to create comprehensive documentation"  
3. "Upload PRD and design docs to GitHub repo"
4. "Reference documentation in every Lovable prompt"

DOCUMENTATION REFERENCE PROMPT:
"Before making any changes, read the project documentation from GitHub and confirm your understanding of:
- Project scope and core features
- Design system and patterns
- Technical constraints and limitations
- Files that should remain unchanged

Then proceed with: [your specific request]"
```

### Community Refactoring Template (300+ Line Rule)
```
FILE SIZE MONITORING:
"Review the current project and identify any files over 300 lines that need refactoring for maintainability."

SAFE REFACTORING:
"Please refactor {filename.tsx} to break it into more manageable files but do not break any current functionality and do not make any design changes either. You are only permitted to split one main file into more smaller files. Make sure to delete any unused files/code as well, but once again DO NOT BREAK ANY FUNCTIONALITY. Make sure to tell me which files were created and their names when you are done."

POST-REFACTOR VERIFICATION:
"Confirm all functionality works exactly as before refactoring. Test key user flows and report any issues."
```

### Debugging with Community Experience (6+ Months Patterns)
```
SYSTEMATIC DEBUGGING APPROACH:
"Use the Lovable Debugging Wizard approach:
1. Identify the specific error and context
2. Review recent changes that might have caused it
3. Check for common patterns in similar issues
4. Provide templated debugging prompt
5. Verify fix doesn't break other functionality"

ANTI-ROGUE DEBUGGING:
"This is a debugging session. Focus only on the specific error:
[Error details]

Do not modify unrelated files or features. Reference project documentation for context and constraints."
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

## 🧠 Advanced Prompting Templates (2025 Update)

### Meta Prompting (AI-Assisted Improvement)
```
PROMPT ENHANCEMENT:
"Review my last prompt and identify any ambiguity or missing info. How can I rewrite it to be more concise and precise?"

PROMPT OPTIMIZATION:
"Rewrite this prompt to be more specific and detailed: '[Your original prompt]'"

ALTERNATIVE APPROACH:
"The current approach isn't working. Suggest 2-3 alternative strategies for [specific goal] and explain the trade-offs of each."
```

### Reverse Meta Prompting (Documentation)
```
SESSION DOCUMENTATION:
"Summarize the errors we encountered while setting up [feature] and how they were resolved. Create a detailed prompt I can use next time to avoid these mistakes."

SOLUTION TEMPLATE CREATION:
"Based on our successful implementation of [feature], create a reusable prompt template that captures the key decisions and constraints for future similar projects."

DEBUGGING PLAYBOOK:
"Document the debugging process we just completed as a step-by-step troubleshooting guide for [specific error type]."
```

### Stripe Integration (Official Template)
```
STRIPE SETUP:
"Initiate a Stripe connection in test mode using the configuration detailed below:

PRODUCT DETAILS:
- Product IDs: [Your Product IDs]  
- Pricing Model: [One-time or Subscription]
- Webhook Endpoint: [Your Webhook Endpoint]

FRONTEND REQUIREMENTS:
- Style the payment form as: [Describe desired payment form]
- Success Redirect: [Success URL]
- Cancel Redirect: [Cancel URL]

CONSTRAINTS:
- Use test mode only
- Include proper error handling
- Ensure mobile responsiveness

Please refrain from altering any existing code and confirm all necessary information is included."

NOTE: Use Stripe Secret Key and Webhook Signing Secret securely in Supabase Edge Function Secrets—never include them in prompts.
```

### Advanced Debugging Templates
```
INITIAL ERROR INVESTIGATION:
"The same error continues to occur. Take a moment to perform a preliminary investigation to uncover the root cause. Examine logs, workflows, and dependencies before making any changes. Provide analysis first."

DEEP ERROR ANALYSIS:
"This issue persists without resolution. Perform a thorough analysis of the flow and dependencies. Stop all modifications until the root cause is identified with complete certainty. Document failures, reasons, and patterns observed."

SYSTEM-WIDE REVIEW:
"This requires a comprehensive re-evaluation of the entire system. Map the flow systematically—covering authentication, database interactions, integrations, state management, and redirects. Evaluate each component to pinpoint failures."

ROOT CAUSE DOCUMENTATION:
"Create a detailed report outlining expected vs actual behavior, identifying specific discrepancies. Avoid code suggestions until you have evidence-based insights with clear reasoning."
```

### Mobile-First Responsive (Enhanced)
```
COMPREHENSIVE RESPONSIVE UPDATE:
"Always make things responsive on all breakpoints, with a focus on mobile first. Use modern UI/UX best practices for determining how breakpoints should change the components. Use ShadCN and Tailwind built-in breakpoints instead of anything custom, unless the user prompts for custom breakpoints directly.

MOBILE OPTIMIZATION PROCESS:
1. Analyze current layout and responsiveness
2. Identify necessary adjustments for smaller screens and touch interactions
3. Outline detailed plan before editing any code
4. Test thoroughly across devices
5. Ensure app behaves exactly as it does on desktop

If unsure about any aspect, pause and propose solutions before proceeding."
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

## 🎯 Credit Optimization Templates (Community-Proven)

### Multi-Model Analysis Workflow
```
EXTERNAL AI ANALYSIS PROMPTS (Use ChatGPT, Claude, etc.):

PROJECT REVIEW:
"Analyze this Lovable project code and list all past build errors and conflicts. 
[Paste project files or descriptions]"

ARCHITECTURE ASSESSMENT:
"Generate a comprehensive README for this project including:
- Architecture overview and design patterns
- Complete dependency list and versions  
- Tech stack breakdown and rationale
- Database schema and relationships
- API endpoints and integration points
- Deployment requirements"

ROADMAP OPTIMIZATION:
"Based on this project roadmap: [paste roadmap]
Suggest architecture optimizations for the next development phase.
Identify potential bottlenecks and recommend solutions."

COMPARATIVE ANALYSIS:
"Compare the outputs from different AI models for this feature request and identify:
- Consistency across recommendations
- Conflicting approaches and their trade-offs
- Best practices alignment
- Implementation complexity assessment"
```

### Credit Conservation Implementation
```
EFFICIENT LOVABLE WORKFLOW:

PLANNING PHASE (Chat Mode):
"Create a detailed implementation plan for [specific feature]:
1. Break down into smallest possible steps
2. Identify dependencies and prerequisites  
3. Suggest order of implementation
4. Highlight potential risks or complications"

EXECUTION PHASE:
→ Review plan in Chat Mode
→ Click "Implement plan" button for automated execution
→ Use Developer Mode for manual tweaks (styles, text, simple logic)

MANUAL OPTIMIZATION:
- Handle translations manually in Developer Mode
- Adjust CSS/styling without prompts
- Update static content directly
- Save prompts for complex logic only
```

### Smart Prompt Length Strategy
```
PROGRESSIVE PROMPT BUILDING:

LEVEL 1 - MINIMAL:
"Add user authentication"

LEVEL 2 - CLARIFIED (if Level 1 unclear):
"Add email/password authentication using Supabase with signup and login pages"

LEVEL 3 - DETAILED (if Level 2 has issues):
"Implement Supabase authentication system:
- Signup page with email/password validation
- Login page with error handling  
- Protected dashboard route
- Logout functionality
- Redirect logic after successful auth"

LEVEL 4 - COMPREHENSIVE (complex features only):
"Build complete authentication flow with Supabase:
[Include full context, constraints, and detailed requirements]"

HALLUCINATION MONITORING:
- Watch for unexpected changes in Level 3+ prompts
- Revert to shorter prompts if AI adds unwanted features
- Document successful prompt length for each feature type
```
