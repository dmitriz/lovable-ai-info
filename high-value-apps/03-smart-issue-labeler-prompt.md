# Smart Issue Labeler - High-Quality Lovable Prompt

**Context:** You are an expert developer productivity engineer and full-stack developer with deep expertise in GitHub automation, AI-powered classification systems, and developer workflow optimization. You understand the pain points of issue management and have experience building tools that integrate seamlessly with developer workflows.

**Task:** Build a Smart Issue Labeler that automatically categorizes and labels GitHub issues using AI analysis, with custom rule support, team productivity metrics, and seamless GitHub integration to eliminate manual issue management overhead.

**Guidelines:** 
- Use React + TypeScript + Supabase + TailwindCSS + ShadCN components
- Integrate with GitHub API for issue management and webhook processing
- Implement AI classification using OpenAI/Anthropic APIs
- Create intuitive interface for non-technical team members
- Mobile-first responsive design for on-the-go issue management
- Focus on developer productivity and time savings

**Constraints:** 
- Must handle GitHub rate limits gracefully with proper queuing
- AI classification must be fast (<5 seconds per issue)
- Should work with private and public repositories
- Must preserve manual labels when adding automated ones
- Interface should be simple enough for product managers to use

---

## PROJECT REQUIREMENTS DOCUMENT (PRD)

### Introduction
The Smart Issue Labeler is an AI-powered GitHub issue management tool that automatically categorizes, labels, and prioritizes issues to eliminate manual overhead and improve team productivity. It reduces issue triage time by 80% while maintaining accuracy and providing valuable insights into project health.

**Target Users:** Development teams, DevOps engineers, product managers, open-source maintainers, GitHub repository owners

### Core Features

1. **AI-Powered Issue Classification**
   - Automatic categorization (bug, feature, documentation, question, etc.)
   - Priority assignment based on content analysis and keywords
   - Sentiment analysis for urgency detection
   - Technology stack detection for appropriate team routing
   - Duplicate issue detection with similarity scoring

2. **Custom Labeling Rules & Templates**
   - Visual rule builder for custom classification logic
   - Template library for common project types (web app, mobile, API, etc.)
   - Conditional labeling based on title patterns, body content, and metadata
   - Team-specific labeling schemes and conventions
   - Import/export functionality for sharing rules across projects

3. **GitHub Integration & Automation**
   - Real-time webhook processing for new issues
   - Batch processing for existing unlabeled issues
   - Preserve existing manual labels while adding automated ones
   - Integration with GitHub Projects and milestones
   - Comment generation with classification reasoning

4. **Team Productivity Analytics**
   - Issue resolution time tracking by label and category
   - Team workload distribution analysis
   - Label accuracy monitoring and feedback loops
   - Productivity metrics dashboard with trending
   - Export capabilities for reporting to stakeholders

5. **Bulk Operations & Management**
   - Bulk reprocessing of historical issues
   - Mass label updates with preview functionality
   - Conflict resolution for overlapping manual/auto labels
   - Archive and restore functionality for label schemes
   - API access for custom integrations

### Tech Stack
- **Frontend:** React 18+ with TypeScript, TailwindCSS, ShadCN/UI
- **Backend:** Supabase (PostgreSQL + Auth + Real-time + Edge Functions)
- **Integrations:** GitHub API v4 (GraphQL), GitHub Webhooks
- **AI Processing:** OpenAI GPT-4 or Anthropic Claude for classification
- **Analytics:** Recharts for productivity dashboards
- **Queue Management:** Supabase Edge Functions with job queuing
- **Authentication:** GitHub OAuth integration

### User Flow
**Start:** User connects GitHub repository via OAuth → **Setup:** User configures labeling rules and AI preferences → **Processing:** System processes existing issues in background → **Monitoring:** User monitors real-time labeling of new issues → **Analytics:** User reviews productivity metrics and accuracy → **Optimization:** User refines rules based on feedback → **End state:** Fully automated issue management with continuous optimization

### Design Principles
- **Colors:** Primary #0066CC (GitHub blue), Secondary #586069 (GitHub gray), Success #28A745 (green), Warning #FFC107 (amber), Error #DC3545 (red), Background #FAFBFC (GitHub light)
- **Typography:** System font stack (-apple-system, BlinkMacSystemFont, Segoe UI), consistent with GitHub design
- **Layout:** Clean, developer-focused interface with efficient use of space, card-based design
- **Components:** GitHub-inspired design elements, consistent with developer expectations
- **Icons:** Octicons (GitHub's icon set) for familiarity, Lucide React for additional icons
- **Responsive:** Desktop-optimized for development workflows, mobile-friendly for quick reviews

### Database Schema (Supabase)

**repositories table:**
- id: UUID primary key
- github_id: bigint unique not null
- name: text not null
- full_name: text not null
- owner: text not null
- is_private: boolean default false
- webhook_url: text
- webhook_secret: text
- last_sync: timestamptz
- settings: jsonb (repository-specific configuration)
- created_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**labeling_rules table:**
- id: UUID primary key
- repository_id: UUID references repositories(id)
- name: text not null
- description: text
- rule_type: text not null check (rule_type in ('ai_classification', 'keyword_match', 'pattern_match', 'conditional'))
- rule_config: jsonb not null (rule definition and parameters)
- priority: integer default 0
- is_active: boolean default true
- created_at: timestamptz default now()
- updated_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**issues table:**
- id: UUID primary key
- repository_id: UUID references repositories(id)
- github_issue_id: bigint not null
- issue_number: integer not null
- title: text not null
- body: text
- state: text not null
- labels: jsonb (current labels array)
- auto_labels: jsonb (labels added by our system)
- classification: jsonb (AI classification results)
- processed_at: timestamptz
- last_updated: timestamptz
- UNIQUE(repository_id, github_issue_id)

**processing_jobs table:**
- id: UUID primary key
- repository_id: UUID references repositories(id)
- job_type: text not null check (job_type in ('initial_sync', 'single_issue', 'bulk_reprocess'))
- status: text default 'pending' check (status in ('pending', 'processing', 'completed', 'failed'))
- total_items: integer
- processed_items: integer default 0
- error_details: jsonb
- started_at: timestamptz
- completed_at: timestamptz
- created_by: UUID references auth.users(id)

**analytics_events table:**
- id: UUID primary key
- repository_id: UUID references repositories(id)
- event_type: text not null (label_applied, issue_resolved, accuracy_feedback)
- event_data: jsonb not null
- timestamp: timestamptz default now()

### Security (RLS Policies)
- Users can only access repositories they have connected via GitHub OAuth
- Repository data filtered by GitHub permissions (read access required)
- Webhook secrets encrypted and repository-specific
- API keys stored securely in Supabase Edge Function environment
- Rate limiting to prevent abuse of GitHub API quotas

### In-Scope vs Out-of-Scope

**In-Scope:**
- Core AI-powered issue classification and labeling
- GitHub API integration with webhook support
- Custom rule creation and management interface
- Basic productivity analytics and reporting
- Bulk processing for existing issues
- Mobile-responsive interface for basic monitoring

**Out-of-Scope:**
- Advanced machine learning model training
- Integration with other issue tracking systems (Jira, Linear)
- Advanced enterprise features (SAML SSO, audit logs)
- Custom AI model hosting or fine-tuning
- Advanced workflow automation beyond labeling

---

## IMPLEMENTATION INSTRUCTIONS

### Phase 1: GitHub Integration Foundation
1. Set up Supabase database with proper schema and RLS policies
2. Implement GitHub OAuth authentication and repository connection
3. Create GitHub API integration with rate limiting and error handling
4. Build basic repository management interface

### Phase 2: AI Classification Engine
1. Implement AI classification service using OpenAI/Anthropic APIs
2. Create issue processing pipeline with queue management
3. Build classification rules engine for custom logic
4. Add webhook handling for real-time issue processing

### Phase 3: User Interface & Management
1. Create repository dashboard with issue overview
2. Build rule creation and management interface
3. Implement bulk processing controls with progress tracking
4. Add issue detail views with classification explanations

### Phase 4: Analytics & Optimization
1. Create productivity analytics dashboard
2. Implement accuracy tracking and feedback systems
3. Build export functionality for reports
4. Add rule optimization suggestions based on usage

### Phase 5: Polish & Advanced Features
1. Add comprehensive error handling and user feedback
2. Implement advanced search and filtering capabilities
3. Create template library for common project types
4. Add API endpoints for custom integrations

---

## SUCCESS CRITERIA

**Automation Requirements:**
- Successfully processes 95%+ of issues without manual intervention
- Classification accuracy of 85%+ based on user feedback
- Processing time under 5 seconds per issue
- Handles GitHub rate limits without dropping requests
- Preserves all existing manual labels correctly

**User Experience Requirements:**
- Repository connection process takes under 60 seconds
- Rule creation interface is intuitive for non-technical users
- Dashboard loads issue data within 3 seconds
- Mobile interface supports basic monitoring and manual corrections
- Error messages are clear and actionable

**Integration Requirements:**
- Works with both public and private GitHub repositories
- Supports organizations with 100+ repositories
- Webhook processing has 99.5% reliability
- Batch processing can handle 1000+ issues without timeout
- API rate limits are respected with graceful degradation

**Business Value Requirements:**
- Reduces manual issue triage time by 80%
- Improves issue resolution speed through better categorization
- Provides actionable insights into team productivity
- Scales to support growing development teams
- Integrates seamlessly into existing GitHub workflows

---

Begin implementation by setting up the GitHub OAuth integration and basic repository management interface. Focus on creating a reliable foundation that can handle the GitHub API complexities before adding advanced AI features.
