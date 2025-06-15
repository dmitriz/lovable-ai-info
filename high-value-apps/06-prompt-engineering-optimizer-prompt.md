# Prompt Engineering Optimizer - High-Quality Lovable Prompt

**Context:** You are a world-class AI prompt engineering expert and full-stack developer with deep expertise in LLM optimization, A/B testing methodologies, and developer productivity tools. You understand the nuances of prompt design across different AI models and have experience building tools that improve AI interaction effectiveness and cost efficiency.

**Task:** Build a comprehensive Prompt Engineering Optimizer that enables systematic testing, optimization, and management of AI prompts with A/B testing capabilities, performance analytics, version control, and cost analysis across multiple AI platforms.

**Guidelines:** 
- Use React + TypeScript + Supabase + TailwindCSS + ShadCN components
- Integrate with multiple AI platforms (OpenAI, Anthropic, Gemini) for testing
- Implement statistical A/B testing with proper significance testing
- Create professional interface suitable for both technical and non-technical users
- Support collaborative prompt development with team features
- Mobile-responsive for prompt testing and review on-the-go

**Constraints:** 
- A/B testing must be statistically rigorous with proper sample sizes
- Cost tracking must be accurate to the penny across all platforms
- Version control should preserve prompt evolution and reasoning
- Interface must handle complex prompts with thousands of characters
- Performance metrics must be actionable and clearly presented

---

## PROJECT REQUIREMENTS DOCUMENT (PRD)

### Introduction
The Prompt Engineering Optimizer is a comprehensive platform for systematic prompt development, testing, and optimization. It enables teams to improve AI interaction effectiveness through rigorous A/B testing, performance tracking, cost optimization, and collaborative prompt management across multiple AI platforms.

**Target Users:** AI engineers, prompt engineers, product teams using AI, developers building AI applications, consultants optimizing AI workflows

### Core Features

1. **Advanced Prompt Testing & A/B Comparison**
   - Statistical A/B testing with configurable sample sizes and significance levels
   - Multi-variant testing for complex prompt optimization
   - Real-time test monitoring with early stopping for clear winners
   - Test result visualization with confidence intervals and effect sizes
   - Automated test scheduling and execution across time periods

2. **Multi-Platform Performance Analytics**
   - Comprehensive metrics tracking (quality, speed, cost, consistency)
   - Response quality scoring using multiple evaluation methods
   - Latency and reliability monitoring across AI platforms
   - Cost per interaction tracking with trend analysis
   - Custom metric definition for domain-specific evaluation

3. **Collaborative Prompt Library & Versioning**
   - Centralized prompt template library with categorization
   - Git-style version control with branching and merging
   - Collaborative editing with comment and suggestion systems
   - Prompt sharing across teams with permission controls
   - Template marketplace for common use cases

4. **Intelligent Optimization Recommendations**
   - AI-powered prompt improvement suggestions
   - Performance regression detection and alerts
   - Cost optimization recommendations based on usage patterns
   - Platform migration analysis for cost/performance trade-offs
   - Automated prompt validation and quality checks

5. **Enterprise Integration & Workflow Management**
   - API integration for automated prompt testing in CI/CD pipelines
   - Webhook notifications for test completion and alerts
   - Team workspace management with role-based access
   - Audit trails and change history for compliance
   - Export capabilities for documentation and reporting

### Tech Stack
- **Frontend:** React 18+ with TypeScript, TailwindCSS, ShadCN/UI
- **Backend:** Supabase (PostgreSQL + Auth + Real-time + Edge Functions)
- **AI Integrations:** OpenAI API, Anthropic Claude API, Google Gemini API
- **Analytics:** Statistical analysis libraries, Recharts for visualization
- **Testing:** Custom A/B testing engine with statistical significance
- **Export:** React-PDF for reports, CSV export for data analysis
- **Real-time:** Supabase subscriptions for live test monitoring

### User Flow
**Start:** User creates prompt project and defines test objectives → **Setup:** User creates prompt variants and configures A/B test parameters → **Testing:** System executes tests across platforms with real data → **Monitoring:** User monitors test progress and interim results → **Analysis:** System provides statistical analysis and optimization recommendations → **Implementation:** User selects winning prompt and implements in production → **End state:** Optimized prompt with documented performance improvements

### Design Principles
- **Colors:** Primary #7C3AED (violet-600), Secondary #64748B (slate-500), Success #059669 (emerald-600), Warning #D97706 (amber-600), Error #DC2626 (red-600), Background #FAFAFA (neutral-50)
- **Typography:** JetBrains Mono for prompts/code, Inter for interface, clear hierarchy for data-heavy interfaces
- **Layout:** Data-focused design with efficient use of space, tabbed interfaces, split-view for comparisons
- **Components:** Technical, precise styling with emphasis on data visualization and prompt readability
- **Testing Elements:** Statistical confidence indicators, performance trend visualizations, clear winner highlighting
- **Responsive:** Desktop-optimized for analysis work, tablet for review, mobile for monitoring

### Database Schema (Supabase)

**prompt_projects table:**
- id: UUID primary key
- name: text not null
- description: text
- use_case: text (chatbot, content_generation, analysis, classification)
- evaluation_criteria: jsonb (custom metrics and weights)
- status: text default 'active' check (status in ('active', 'paused', 'archived'))
- settings: jsonb (project configuration)
- created_at: timestamptz default now()
- updated_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**prompts table:**
- id: UUID primary key
- project_id: UUID references prompt_projects(id)
- name: text not null
- content: text not null
- system_prompt: text
- parameters: jsonb (temperature, max_tokens, etc.)
- version: text not null
- parent_prompt_id: UUID references prompts(id)
- change_description: text
- tags: text[]
- created_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**ab_tests table:**
- id: UUID primary key
- project_id: UUID references prompt_projects(id)
- name: text not null
- hypothesis: text
- prompt_a_id: UUID references prompts(id)
- prompt_b_id: UUID references prompts(id)
- test_config: jsonb (sample_size, significance_level, platforms)
- status: text default 'setup' check (status in ('setup', 'running', 'completed', 'paused', 'cancelled'))
- target_sample_size: integer not null
- current_sample_size: integer default 0
- confidence_level: numeric default 0.95
- started_at: timestamptz
- completed_at: timestamptz
- created_by: UUID references auth.users(id)

**test_executions table:**
- id: UUID primary key
- ab_test_id: UUID references ab_tests(id)
- prompt_id: UUID references prompts(id)
- platform: text not null check (platform in ('openai', 'anthropic', 'gemini'))
- input_data: jsonb not null
- response_data: jsonb not null
- quality_score: numeric check (quality_score >= 0 AND quality_score <= 10)
- response_time: interval not null
- cost: numeric not null
- tokens_used: integer
- executed_at: timestamptz default now()

**performance_metrics table:**
- id: UUID primary key
- prompt_id: UUID references prompts(id)
- metric_name: text not null
- metric_value: numeric not null
- measurement_date: date not null
- platform: text
- sample_size: integer
- confidence_interval_lower: numeric
- confidence_interval_upper: numeric
- created_at: timestamptz default now()

**cost_analysis table:**
- id: UUID primary key
- prompt_id: UUID references prompts(id)
- platform: text not null
- daily_cost: numeric not null
- daily_volume: integer not null
- cost_per_interaction: numeric not null
- date: date not null
- projected_monthly_cost: numeric

### Security (RLS Policies)
- Project-based access control with team sharing capabilities
- Prompt versioning with secure change tracking
- API key encryption for all platform integrations
- Test data anonymization for sensitive use cases
- Role-based permissions (owner, editor, analyst, viewer)

### In-Scope vs Out-of-Scope

**In-Scope:**
- Core A/B testing with statistical rigor for prompt optimization
- Multi-platform performance tracking and cost analysis
- Collaborative prompt management with version control
- Professional analytics dashboard with exportable reports
- Integration APIs for automated testing workflows
- Template library with common prompt patterns

**Out-of-Scope:**
- Custom AI model training or fine-tuning
- Advanced machine learning for automated prompt generation
- Integration with external analytics platforms
- Enterprise SSO and advanced security features
- Real-time collaborative editing (version-based collaboration only)

---

## IMPLEMENTATION INSTRUCTIONS

### Phase 1: Core Testing Infrastructure
1. Set up Supabase database with statistical testing schema
2. Implement multi-platform AI API integration with cost tracking
3. Create A/B testing engine with proper statistical analysis
4. Build prompt management system with version control

### Phase 2: Testing Interface & Analytics
1. Create A/B test setup wizard with statistical guidance
2. Implement real-time test monitoring dashboard
3. Build comprehensive analytics with performance visualization
4. Add statistical significance testing and confidence intervals

### Phase 3: Prompt Management & Collaboration
1. Create prompt library with search and categorization
2. Implement version control system with change tracking
3. Build collaborative features with comments and reviews
4. Add template sharing and team workspace management

### Phase 4: Optimization & Intelligence
1. Implement performance regression detection and alerts
2. Create cost optimization analysis and recommendations
3. Build automated prompt validation and quality checks
4. Add intelligent suggestions for prompt improvements

### Phase 5: Integration & Enterprise Features
1. Create API endpoints for CI/CD pipeline integration
2. Implement webhook system for notifications and alerts
3. Build comprehensive reporting and export capabilities
4. Add audit trails and compliance documentation

---

## SUCCESS CRITERIA

**Statistical Rigor Requirements:**
- A/B tests maintain proper statistical significance with configurable confidence levels
- Sample size calculations are accurate and prevent underpowered tests
- Test results include confidence intervals and effect sizes
- Early stopping algorithms prevent false positives from peeking
- Multiple testing corrections are applied when running multiple comparisons

**Performance Requirements:**
- Test execution latency is under 10 seconds for individual prompt runs
- Concurrent testing supports 100+ simultaneous executions
- Real-time monitoring updates within 5 seconds of test completion
- Cost tracking accuracy is within 1% of actual platform billing
- Analytics dashboard loads test data within 3 seconds

**User Experience Requirements:**
- Test setup wizard guides users through proper experimental design
- Statistical results are presented in clear, non-technical language
- Prompt editing interface supports complex, multi-part prompts
- Version control allows easy comparison between prompt iterations
- Mobile interface supports test monitoring and basic prompt review

**Business Value Requirements:**
- A/B testing demonstrates statistically significant prompt improvements
- Cost optimization features reduce AI spending by 20% on average
- Version control prevents prompt regression and maintains improvements
- Collaboration features accelerate team prompt development by 50%
- Integration APIs enable automated prompt testing in development workflows

---

Begin implementation by setting up the statistical A/B testing foundation and multi-platform AI integration. Focus on creating a rigorous testing framework that provides reliable, actionable insights for prompt optimization.
