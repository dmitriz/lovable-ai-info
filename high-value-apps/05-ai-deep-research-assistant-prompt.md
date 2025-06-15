# AI Deep Research Assistant - High-Quality Lovable Prompt

**Context:** You are an expert research methodology specialist and full-stack developer with deep expertise in AI-powered research platforms, multi-platform API integration, and research workflow optimization. You understand the strengths and limitations of different AI research platforms (OpenAI, Gemini, Perplexity) and how to orchestrate them for maximum research effectiveness.

**Task:** Build an AI Deep Research Assistant that provides a unified interface for conducting complex research across multiple AI platforms, with intelligent query orchestration, cost optimization, source synthesis, and comprehensive research project management.

**Guidelines:** 
- Use React + TypeScript + Supabase + TailwindCSS + ShadCN components
- Integrate with multiple AI platforms (OpenAI, Gemini, Perplexity) with unified interface
- Implement intelligent query planning and platform selection optimization
- Create professional research interface suitable for academic and business use
- Support complex multi-step research workflows with citation management
- Mobile-friendly for research review and note-taking on-the-go

**Constraints:** 
- Must handle API rate limits and cost optimization across platforms
- Research quality must maintain academic standards with proper citations
- Should work efficiently with both free and paid AI platform tiers
- Interface must be intuitive for researchers with varying technical backgrounds
- Must preserve research integrity and maintain source traceability

---

## PROJECT REQUIREMENTS DOCUMENT (PRD)

### Introduction
The AI Deep Research Assistant is a comprehensive research orchestration platform that leverages multiple AI services to conduct sophisticated research projects. It optimizes query distribution across platforms, manages costs, synthesizes sources, and provides professional-grade research outputs with proper citations and methodology tracking.

**Target Users:** Researchers, analysts, consultants, students, journalists, policy researchers, business intelligence professionals

### Core Features

1. **Multi-Platform AI Integration**
   - Unified interface for OpenAI ChatGPT, Google Gemini, and Perplexity
   - Intelligent platform selection based on query type and requirements
   - API key management with usage tracking and budget controls
   - Platform capability mapping (technical vs. web research vs. citations)
   - Fallback systems for platform outages or rate limits

2. **Intelligent Research Orchestration**
   - Research plan generation with multi-step query strategies
   - Query optimization for each platform's strengths
   - Parallel and sequential research execution
   - Dynamic query refinement based on intermediate results
   - Research objective tracking and completion assessment

3. **Research Project Management**
   - Project organization with hierarchical research topics
   - Research timeline and milestone tracking
   - Collaborative research with team member access controls
   - Research methodology documentation and replication
   - Version control for research iterations and refinements

4. **Source Synthesis & Citation Management**
   - Automated source consolidation and deduplication
   - Citation formatting for multiple academic styles (APA, MLA, Chicago)
   - Evidence strength assessment and source credibility scoring
   - Cross-platform source verification and fact-checking
   - Bibliography generation with proper attribution

5. **Cost Optimization & Analytics**
   - Real-time cost tracking across all AI platforms
   - Budget allocation and spending alerts
   - Platform efficiency analysis and ROI metrics
   - Query cost prediction and optimization recommendations
   - Usage analytics with research productivity insights

### Tech Stack
- **Frontend:** React 18+ with TypeScript, TailwindCSS, ShadCN/UI
- **Backend:** Supabase (PostgreSQL + Auth + Real-time + Edge Functions)
- **AI Integrations:** OpenAI API, Google Gemini API, Perplexity API
- **Research Tools:** Citation parsing libraries, PDF text extraction
- **Analytics:** Recharts for usage and cost analytics
- **Export:** React-PDF for research report generation
- **Storage:** Supabase Storage for research documents and outputs

### User Flow
**Start:** User creates research project with objectives → **Planning:** AI generates research plan with query strategy → **Execution:** System orchestrates queries across platforms → **Synthesis:** Results are consolidated and cross-referenced → **Analysis:** User reviews synthesized findings and citations → **Export:** Professional research report generated → **End state:** Comprehensive research output with full methodology documentation

### Design Principles
- **Colors:** Primary #2563EB (blue-600), Secondary #64748B (slate-500), Success #059669 (emerald-600), Warning #D97706 (amber-600), Academic #1E40AF (blue-800), Background #FAFAFA (neutral-50)
- **Typography:** Inter font for interface, Georgia for research content, clear academic hierarchy
- **Layout:** Research-focused design with reading-optimized layouts, sidebar navigation, tabbed interfaces
- **Components:** Professional, academic styling with emphasis on readability and information density
- **Research Elements:** Citation styling, source highlighting, evidence strength indicators
- **Responsive:** Desktop-optimized for research workflows, tablet for review, mobile for quick access

### Database Schema (Supabase)

**research_projects table:**
- id: UUID primary key
- name: text not null
- description: text
- research_objectives: text[] (array of research questions/goals)
- methodology: text
- status: text default 'planning' check (status in ('planning', 'active', 'completed', 'paused'))
- budget_limit: numeric (total budget limit across platforms)
- spent_amount: numeric default 0
- settings: jsonb (project configuration and preferences)
- created_at: timestamptz default now()
- updated_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**ai_platform_configs table:**
- id: UUID primary key
- user_id: UUID references auth.users(id)
- platform: text not null check (platform in ('openai', 'gemini', 'perplexity'))
- api_key_encrypted: text
- usage_tier: text (free, pro, enterprise)
- monthly_limit: numeric
- current_usage: numeric default 0
- is_active: boolean default true
- last_updated: timestamptz default now()

**research_queries table:**
- id: UUID primary key
- project_id: UUID references research_projects(id)
- query_text: text not null
- platform: text not null
- query_type: text not null (background, technical, current_events, citation_heavy)
- status: text default 'pending' check (status in ('pending', 'processing', 'completed', 'failed'))
- cost_estimate: numeric
- actual_cost: numeric
- execution_time: interval
- executed_at: timestamptz
- completed_at: timestamptz

**research_results table:**
- id: UUID primary key
- query_id: UUID references research_queries(id)
- content: text not null
- sources: jsonb (array of source objects with URLs, titles, credibility scores)
- citations: jsonb (extracted citations with formatting)
- quality_score: numeric check (quality_score >= 0 AND quality_score <= 10)
- word_count: integer
- confidence_level: text check (confidence_level in ('high', 'medium', 'low'))
- created_at: timestamptz default now()

**synthesis_reports table:**
- id: UUID primary key
- project_id: UUID references research_projects(id)
- title: text not null
- synthesized_content: text not null
- key_findings: text[]
- consolidated_sources: jsonb
- methodology_notes: text
- confidence_assessment: text
- export_formats: text[] (pdf, markdown, word)
- generated_at: timestamptz default now()
- generated_by: UUID references auth.users(id)

**cost_tracking table:**
- id: UUID primary key
- user_id: UUID references auth.users(id)
- project_id: UUID references research_projects(id)
- platform: text not null
- query_id: UUID references research_queries(id)
- cost_amount: numeric not null
- query_tokens: integer
- response_tokens: integer
- timestamp: timestamptz default now()

### Security (RLS Policies)
- User-based access control (users see only their research projects)
- API key encryption with secure storage in Edge Functions
- Project sharing with role-based permissions (owner, collaborator, viewer)
- Budget and usage limits to prevent cost overruns
- Research data encryption for sensitive topics

### In-Scope vs Out-of-Scope

**In-Scope:**
- Core multi-platform AI research orchestration
- Intelligent query planning and platform optimization
- Research project management with collaboration features
- Professional citation management and source synthesis
- Cost tracking and budget optimization tools
- Export capabilities for academic and business reports

**Out-of-Scope:**
- Custom AI model training or fine-tuning
- Advanced statistical analysis or data visualization
- Integration with external research databases beyond AI platforms
- Advanced enterprise features (SAML SSO, advanced audit logs)
- Real-time collaborative editing (basic sharing and comments only)

---

## IMPLEMENTATION INSTRUCTIONS

### Phase 1: Platform Integration Foundation
1. Set up Supabase database with secure API key management
2. Implement authentication and user management system
3. Create AI platform integration layer with unified API wrapper
4. Build platform selection and query routing algorithms

### Phase 2: Research Project Management
1. Create research project creation and management interface
2. Implement research objective setting and methodology tracking
3. Build project collaboration features with access controls
4. Add research timeline and milestone tracking

### Phase 3: Query Orchestration Engine
1. Implement intelligent research planning and query generation
2. Create query execution engine with platform optimization
3. Build real-time monitoring for research progress
4. Add cost tracking and budget management systems

### Phase 4: Synthesis & Citation Management
1. Create source consolidation and deduplication algorithms
2. Implement citation extraction and formatting systems
3. Build evidence assessment and credibility scoring
4. Add cross-platform source verification capabilities

### Phase 5: Analytics & Export
1. Create comprehensive usage and cost analytics dashboard
2. Implement professional report generation with multiple formats
3. Build research methodology documentation and replication
4. Add advanced search and filtering for research history

---

## SUCCESS CRITERIA

**Research Quality Requirements:**
- Research outputs maintain academic standards with proper citations
- Source synthesis accuracy of 90%+ based on expert evaluation
- Citation formatting meets academic style requirements
- Platform selection optimization improves research efficiency by 40%
- Cross-platform source verification reduces misinformation

**Performance Requirements:**
- Query execution across platforms completes within 5 minutes for complex research
- Cost optimization reduces research expenses by 30% compared to manual platform use
- Platform failover and rate limit handling maintains 99% research completion rate
- Real-time progress tracking updates within 10 seconds
- Export generation completes within 60 seconds for 50-page reports

**User Experience Requirements:**
- Research project setup takes under 5 minutes for new users
- Platform integration requires minimal technical knowledge
- Cost tracking provides clear, actionable budget insights
- Collaboration features support 10+ team members efficiently
- Mobile interface supports research review and basic project management

**Integration Requirements:**
- Supports all major AI platform tiers (free, pro, enterprise)
- Handles API rate limits gracefully across all platforms
- Maintains research integrity during platform outages
- Scales to support 100+ concurrent research projects
- API usage optimization respects platform terms of service

---

Begin implementation by setting up the secure multi-platform API integration foundation and basic research project management. Focus on creating a reliable query orchestration system that can handle the complexities of multiple AI platforms before adding advanced synthesis features.
