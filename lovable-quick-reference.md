# Lovable AI Quick Reference Guide

## Prompt Templates for Common Tasks

### Initial App Creation
```
"Create a [app type] application with:
- User authentication (email/password)
- [Primary feature] with [specific requirements]
- Clean, modern UI using Tailwind CSS
- PostgreSQL database via Supabase
- Mobile-responsive design"
```

### Feature Addition
```
"Add [feature name] to the [page/component]:
- Functionality: [detailed description]
- UI elements: [specific requirements]
- Data: [what to store/retrieve]
- Permissions: [who can access/modify]
- Styling: [consistent with existing design]"
```

### Bug Fixing Strategy
```
1. Switch to Chat Mode
2. "Investigate this issue without making changes: [error/problem]"
3. Review suggested solution
4. If approved: "Implement the fix you suggested"
```

### Database Schema
```
"Create a database table for [entity] with:
- [field1]: [type] (required/optional)
- [field2]: [type] with [constraints]
- Relationships: [connections to other tables]
- Security: [row-level policies needed]"
```

### UI Refinement
```
"Update the [component] styling:
- Change [specific element] to [desired appearance]
- Maintain [existing design principles]  
- Ensure mobile responsiveness
- Keep accessibility standards"
```

## Emergency Commands

### When Things Go Wrong
- **Restore Point**: "Revert to the last working version"
- **Clean Slate**: "Remove all recent changes to [component]"
- **Fresh Start**: "Create a new [component] from scratch with [requirements]"

### Debug Mode
- **Investigation**: "Analyze why [feature] isn't working without changing code"
- **Comparison**: "Compare current version with version from [time] and highlight differences"
- **Explanation**: "Explain what this code does: [paste code]"

## Workflow Optimization

### Development Sequence
1. **Static UI First**: Build layout and components
2. **Data Layer**: Add database tables and basic CRUD
3. **Authentication**: Implement user system
4. **Business Logic**: Add specific app functionality
5. **Polish**: Styling, responsive design, error handling

### Credit Conservation
- Use Visual Editor for simple styling changes
- Plan prompts before sending
- Use Chat Mode for exploration
- Be specific to avoid iterations

### Quality Checkpoints
After every 3-5 prompts:
- Test the app manually
- Check console for errors
- Verify mobile responsiveness
- Pin current version if stable

## Troubleshooting Decision Tree

```
Issue Encountered
    ↓
Is it a simple UI tweak?
    ↓ YES → Use Visual Editor
    ↓ NO
Is it a logic/data problem?
    ↓ YES → Switch to Chat Mode
    ↓ NO
Is it breaking the app?
    ↓ YES → Restore last stable version
    ↓ NO
Try specific prompt with clear context
    ↓
Still not working after 2 attempts?
    ↓ YES → Chat Mode investigation
    ↓ NO → Continue development
```

## Best Practices Checklist

**Before Each Prompt:**
- [ ] Clear objective defined
- [ ] Specific requirements listed
- [ ] Context provided (page/component)
- [ ] Constraints mentioned
- [ ] Success criteria established

**After Each Change:**
- [ ] Test functionality works
- [ ] Check for console errors
- [ ] Verify responsive design
- [ ] Confirm it meets requirements
- [ ] Pin version if major milestone

**Regular Maintenance:**
- [ ] Update Knowledge Base with new features
- [ ] Review and clean up unused components
- [ ] Test with different user roles
- [ ] Monitor app performance
- [ ] Sync with GitHub regularly
