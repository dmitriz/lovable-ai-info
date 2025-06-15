# Prompt Quality Review System

## 🎯 Purpose
Systematic review process to ensure prompts are minimalistic, effective, and error-reducing before implementation.

## ⚡ Quick Review Checklist (30 seconds)

### Essential Elements  
- [ ] **Single Goal**: Prompt targets exactly one feature/change
- [ ] **Mobile-First**: Responsive design constraint included
- [ ] **Explicit Boundaries**: What NOT to modify clearly stated
- [ ] **Knowledge Base Reference**: Context anchoring included
- [ ] **Success Criteria**: Clear definition of completion
- [ ] **Tech Specifications**: ShadCN/Tailwind requirements stated

### Quality Indicators
- [ ] **Specificity**: No vague terms like "better" or "improve"
- [ ] **Actionability**: AI can implement without assumptions
- [ ] **Testability**: Results can be immediately verified
- [ ] **Scope Control**: Boundaries prevent unintended changes
- [ ] **Context Anchoring**: References Knowledge Base or project state
- [ ] **Error Prevention**: Includes protection constraints

---

## 📋 Detailed Review Framework

### Level 1: Structure Assessment
**Time**: 15 seconds | **Focus**: Basic prompt anatomy

```
✅ GOOD STRUCTURE:
Context: "You are a [specific role]"
Task: "Implement [single specific feature]"
Guidelines: "Use [tech]. Follow [patterns]"
Constraints: "Don't modify [files]. Must [requirements]"

❌ POOR STRUCTURE:
"Make the app better with some improvements"
```

**Review Questions:**
- Does the prompt use the 4-part structure?
- Is the task statement a single, specific goal?
- Are technologies and approaches explicitly stated?
- Are protective constraints clearly defined?

### Level 2: Scope Analysis
**Time**: 30 seconds | **Focus**: Preventing AI confusion

**Red Flags (REJECT - High Risk):**
- Multiple features in one prompt
- Vague descriptors ("better", "nicer", "improve")
- No mobile responsiveness mention
- Missing file protection constraints
- Asking for "everything" or "complete solution"
- No Knowledge Base context anchoring

**Yellow Flags (CAUTION - Medium Risk):**
- Complex UI + backend changes combined
- More than 3 specific requirements
- Missing technology specifications
- Unclear success criteria
- No testing or validation plan

**Green Flags (APPROVE - Low Risk):**
- Single, specific feature request
- Explicit file protection boundaries
- Mobile-first responsive requirement
- Knowledge Base context reference
- Clear, testable success criteria
- Technology stack clearly specified
- Missing technology specifications
- No protective constraints
- Ambiguous success criteria

**Green Flags (APPROVE):**
- Single, well-defined feature
- Specific technical requirements
- Clear boundaries and limitations
- Measurable completion criteria
- Explicit tool/framework choices

### Level 3: Risk Assessment
**Time**: 45 seconds | **Focus**: Error prevention

**High-Risk Elements:**
- Database schema modifications
- Authentication system changes
- Multi-component refactoring
- State management alterations
- Third-party integrations

**Risk Mitigation Required:**
```
FOR DATABASE CHANGES:
- Must include "Show SQL before applying"
- Specific field types and constraints
- Explicit security policy definitions

FOR COMPONENT CHANGES:
- File protection constraints mandatory
- Existing functionality preservation
- Testing verification requirements

FOR INTEGRATION WORK:
- Security key handling specifications
- Error handling requirements
- Environment variable usage rules
```

---

## 🔍 Review Templates

### Template A: New Feature Prompt Review
```
PROMPT QUALITY SCORE: ___/10

STRUCTURE (2 points):
[ ] Context role specified
[ ] Single task clearly defined

SPECIFICITY (3 points):
[ ] Technical requirements explicit
[ ] UI/UX specifications detailed
[ ] Data handling requirements clear

SAFETY (3 points):
[ ] Protected files/components listed
[ ] Existing functionality preservation noted
[ ] Breaking change prevention specified

TESTABILITY (2 points):
[ ] Success criteria measurable
[ ] Immediate verification possible

PASS/FAIL: ____
REQUIRED IMPROVEMENTS: ________________
```

### Template B: Debugging Prompt Review
```
DEBUGGING PROMPT ASSESSMENT: ___/10

PROBLEM DESCRIPTION (3 points):
[ ] Specific error messages included
[ ] Context of occurrence provided
[ ] Expected vs actual behavior clear

INVESTIGATION APPROACH (4 points):
[ ] Chat Mode specified for analysis
[ ] No immediate code changes requested
[ ] Step-by-step diagnosis requested
[ ] Multiple solution options requested

SAFETY MEASURES (3 points):
[ ] "No changes" instruction clear
[ ] Revert option considered
[ ] Impact assessment requested

APPROVAL STATUS: ____
NOTES: ________________________
```

### Template C: Database Prompt Review
```
DATABASE PROMPT SAFETY CHECK: ___/10

SCHEMA SPECIFICATION (4 points):
[ ] Exact field types specified
[ ] Constraints clearly defined
[ ] Relationships explicitly stated
[ ] Security policies detailed

SAFETY PROTOCOLS (4 points):
[ ] SQL review requirement included
[ ] RLS policy specifications clear
[ ] Foreign key relationships safe
[ ] Data migration considerations noted

VERIFICATION (2 points):
[ ] Manual Supabase dashboard check required
[ ] Testing plan for new schema included

CRITICAL SAFETY APPROVAL: ____
REQUIRED MODIFICATIONS: _______________
```

---

## 🎭 Prompt Examples: Good vs Bad

### Feature Addition: Good Example
```
Context: "You are a React developer specializing in data visualization"
Task: "Add user activity chart to dashboard page"
Guidelines: "Use Chart.js library. Display last 30 days of user login data. Responsive design with Tailwind classes"
Constraints: "Don't modify Header.js or Sidebar.js components. Use existing API endpoint /api/user-activity. Chart container max-height: 400px"

REVIEW SCORE: 9/10 ✅
- Single, specific feature
- Technical requirements clear
- Protected components specified
- Measurable completion criteria
```

### Feature Addition: Bad Example
```
"Make the dashboard more engaging with better visuals and some charts maybe"

REVIEW SCORE: 2/10 ❌
- Multiple vague improvements
- No technical specifications
- Missing protective constraints
- Unmeasurable success criteria
```

### Debugging: Good Example
```
Context: "Investigating authentication issue without making changes"
Task: "Analyze why users can't log in after password reset"
Guidelines: "Check Supabase Auth logs, review RLS policies, examine client-side error handling"
Constraints: "Don't modify any authentication code. Don't change database policies. Provide diagnosis only with 2-3 ranked solution options"

REVIEW SCORE: 10/10 ✅
- Clear investigation focus
- No modification risk
- Specific analysis areas
- Multiple solution requirement
```

### Debugging: Bad Example
```
"Fix the login thing it's broken"

REVIEW SCORE: 1/10 ❌
- No problem description
- No investigation approach
- Risk of random changes
- No solution structure
```

---

## 🚀 Review Workflow

### Pre-Implementation Review (Required)
1. **Self-Review**: Use appropriate template (30 seconds)
2. **Score Assessment**: Must score 7/10 or higher to proceed
3. **Risk Evaluation**: High-risk prompts require additional safety measures
4. **Approval**: Document review decision and reasoning

### Post-Implementation Analysis
1. **Success Rate Tracking**: Did prompt work on first attempt?
2. **Error Pattern Analysis**: What types of issues occurred?
3. **Template Refinement**: Update templates based on learnings
4. **Quality Improvement**: Adjust review criteria as needed

### Continuous Improvement
- Weekly review of prompt success rates
- Monthly template updates based on community reports
- Quarterly comprehensive review process evaluation
- Annual best practices documentation update

---

## 📊 Success Metrics

### Target Quality Standards
- **Prompt Success Rate**: 95%+ first-attempt success
- **Error Prevention**: Zero infinite loops from reviewed prompts
- **Credit Efficiency**: Maximum value per credit spent
- **Development Velocity**: Consistent progress without setbacks

### Quality Indicators
- **Review Time**: Under 60 seconds per prompt
- **Approval Rate**: 80%+ prompts pass review on first assessment
- **Revision Efficiency**: Failed prompts require minimal changes
- **Learning Velocity**: Review accuracy improves over time

---

*This review system ensures every prompt is optimized for success before implementation, reducing errors and maximizing development efficiency.*
