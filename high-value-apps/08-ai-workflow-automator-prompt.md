# AI Workflow Automator - High-Quality Lovable Prompt

**Context:** You are a world-class AI workflow specialist and full-stack developer with deep expertise in visual workflow design, agent orchestration, and process automation. You understand the complexities of multi-agent AI systems, conditional logic in workflows, and the need for visual tools that enable non-technical users to create sophisticated AI automation sequences.

**Task:** Build a comprehensive AI Workflow Automator that provides a visual drag-and-drop interface for designing, executing, and monitoring complex AI agent workflows with conditional logic, real-time execution tracking, and reusable workflow templates.

**Guidelines:** 
- Use React + TypeScript + Supabase + TailwindCSS + ShadCN components
- Implement intuitive visual workflow designer similar to Zapier/n8n but for AI agents
- Create real-time workflow execution monitoring with step-by-step visibility
- Support conditional logic, loops, and branching for complex automation
- Design for both technical and non-technical users
- Mobile-responsive for workflow monitoring and basic editing

**Constraints:** 
- Visual workflow designer must handle complex logic without overwhelming users
- Workflow execution must be reliable with proper error handling and recovery
- Should support integration with multiple AI platforms and external services
- Performance must scale to handle 100+ concurrent workflow executions
- Interface must be intuitive enough for product managers to create workflows

---

## PROJECT REQUIREMENTS DOCUMENT (PRD)

### Introduction
The AI Workflow Automator is a comprehensive visual workflow platform that enables teams to design, deploy, and monitor sophisticated AI agent automation sequences. It combines the ease of visual workflow design with the power of multi-agent AI orchestration to create complex automation that adapts based on data, conditions, and AI agent outputs.

**Target Users:** Business process owners, AI engineers, product managers, operations teams, consultants, no-code automation specialists

### Core Features

1. **Visual Workflow Designer**
   - Drag-and-drop interface with pre-built nodes for common AI operations
   - Conditional logic builder with visual branching and decision points
   - Loop and iteration support for batch processing workflows
   - Real-time workflow validation with error highlighting
   - Collaborative editing with version control and change tracking

2. **AI Agent Integration & Orchestration**
   - Pre-built integrations for major AI platforms (OpenAI, Anthropic, Gemini)
   - Agent capability matching and automatic task routing
   - Dynamic agent selection based on workload and specialization
   - Multi-agent coordination with dependency management
   - Custom agent integration via API connectors

3. **Real-Time Execution Engine**
   - Scalable workflow execution with queue management
   - Real-time progress tracking with step-by-step visibility
   - Error handling with automatic retry and fallback mechanisms
   - Parallel execution support for independent workflow branches
   - Resource management and cost optimization during execution

4. **Monitoring & Analytics Dashboard**
   - Live workflow execution monitoring with detailed logs
   - Performance analytics with execution time and success rate trends
   - Cost analysis across AI platforms and workflow operations
   - Alert system for workflow failures and performance issues
   - Historical execution data with searchable audit trails

5. **Template Library & Sharing**
   - Curated library of workflow templates for common business processes
   - Community template sharing with rating and review system
   - Workflow marketplace for specialized automation patterns
   - Template parameterization for easy customization
   - Export/import functionality for workflow sharing between teams

### Tech Stack
- **Frontend:** React 18+ with TypeScript, TailwindCSS, ShadCN/UI
- **Backend:** Supabase (PostgreSQL + Auth + Real-time + Edge Functions)
- **Workflow Engine:** Custom workflow execution engine with job queuing
- **Visual Designer:** React Flow for drag-and-drop workflow design
- **AI Integrations:** OpenAI, Anthropic, Google Gemini APIs
- **Monitoring:** Real-time execution tracking with Supabase subscriptions
- **External Integrations:** Webhook support, REST API connectors

### User Flow
**Start:** User creates new workflow project → **Design:** User builds workflow using visual designer with AI agent nodes → **Configuration:** User configures AI agents, conditions, and data flows → **Testing:** User tests workflow with sample data → **Deployment:** User activates workflow for production execution → **Monitoring:** User monitors real-time execution and performance → **End state:** Automated AI workflow running with ongoing optimization

### Design Principles
- **Colors:** Primary #6366F1 (indigo-500), Secondary #64748B (slate-500), Success #059669 (emerald-600), Warning #D97706 (amber-600), Error #DC2626 (red-600), Background #F8FAFC (slate-50)
- **Typography:** Inter font for interface, JetBrains Mono for code/configurations, clear hierarchy
- **Layout:** Workflow-focused design with canvas-style main area, property panels, node libraries
- **Components:** Node-based design system with clear visual connections, status indicators
- **Workflow Elements:** Color-coded node types, flow connections, execution progress indicators
- **Responsive:** Desktop-optimized for workflow design, tablet for monitoring, mobile for alerts

### Database Schema (Supabase)

**workflow_projects table:**
- id: UUID primary key
- name: text not null
- description: text
- category: text (data_processing, content_generation, analysis, customer_service)
- workflow_definition: jsonb not null (complete workflow structure)
- status: text default 'draft' check (status in ('draft', 'testing', 'active', 'paused', 'archived'))
- version: integer default 1
- settings: jsonb (project configuration and preferences)
- created_at: timestamptz default now()
- updated_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**workflow_nodes table:**
- id: UUID primary key
- workflow_id: UUID references workflow_projects(id)
- node_id: text not null (unique within workflow)
- node_type: text not null check (node_type in ('ai_agent', 'condition', 'loop', 'webhook', 'data_transform', 'delay'))
- node_config: jsonb not null (node-specific configuration)
- position: jsonb not null (x, y coordinates for visual layout)
- connections: jsonb (outbound connections to other nodes)
- created_at: timestamptz default now()

**ai_agents table:**
- id: UUID primary key
- name: text not null
- description: text
- platform: text not null check (platform in ('openai', 'anthropic', 'gemini', 'custom'))
- capabilities: text[] (array of agent capabilities)
- configuration: jsonb not null (platform-specific config)
- status: text default 'active' check (status in ('active', 'inactive', 'error'))
- cost_per_operation: numeric
- average_response_time: interval
- created_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**workflow_executions table:**
- id: UUID primary key
- workflow_id: UUID references workflow_projects(id)
- trigger_type: text not null check (trigger_type in ('manual', 'scheduled', 'webhook', 'api'))
- trigger_data: jsonb (data that initiated the execution)
- status: text default 'running' check (status in ('queued', 'running', 'completed', 'failed', 'cancelled'))
- current_node: text (currently executing node_id)
- execution_log: jsonb (detailed step-by-step execution history)
- total_cost: numeric default 0
- started_at: timestamptz default now()
- completed_at: timestamptz
- triggered_by: UUID references auth.users(id)

**node_executions table:**
- id: UUID primary key
- workflow_execution_id: UUID references workflow_executions(id)
- node_id: text not null
- status: text not null check (status in ('pending', 'running', 'completed', 'failed', 'skipped'))
- input_data: jsonb
- output_data: jsonb
- error_details: text
- execution_time: interval
- cost: numeric default 0
- started_at: timestamptz
- completed_at: timestamptz

**workflow_templates table:**
- id: UUID primary key
- name: text not null
- description: text
- category: text not null
- template_definition: jsonb not null (workflow structure template)
- parameters: jsonb (configurable parameters)
- usage_count: integer default 0
- rating: numeric check (rating >= 0 AND rating <= 5)
- is_public: boolean default false
- created_at: timestamptz default now()
- created_by: UUID references auth.users(id)

### Security (RLS Policies)
- Project-based access control with team sharing capabilities
- Workflow execution isolation between users and organizations
- Secure API key management for AI platform integrations
- Role-based permissions (owner, editor, operator, viewer)
- Audit logging for all workflow executions and configuration changes

### In-Scope vs Out-of-Scope

**In-Scope:**
- Visual workflow designer with comprehensive node library
- Real-time workflow execution with monitoring and logging
- AI agent integration with major platforms
- Template library with community sharing capabilities
- Performance analytics and cost tracking
- Basic scheduling and webhook triggers for workflow automation

**Out-of-Scope:**
- Custom AI model training or hosting
- Advanced enterprise orchestration (Kubernetes integration)
- Complex data transformation beyond basic operations
- Advanced security features (SAML SSO, enterprise audit)
- Integration with external workflow platforms (Zapier, n8n)

---

## IMPLEMENTATION INSTRUCTIONS

### Phase 1: Visual Workflow Designer
1. Set up Supabase database with workflow management schema
2. Implement React Flow-based visual workflow designer
3. Create node library with basic AI agent and logic nodes
4. Build workflow validation and error checking system

### Phase 2: AI Agent Integration
1. Implement AI platform integrations (OpenAI, Anthropic, Gemini)
2. Create agent configuration and capability management
3. Build agent selection and routing algorithms
4. Add cost tracking and performance monitoring for agents

### Phase 3: Execution Engine
1. Create workflow execution engine with queue management
2. Implement real-time execution monitoring and logging
3. Build error handling with retry and fallback mechanisms
4. Add parallel execution support for workflow branches

### Phase 4: Monitoring & Analytics
1. Create comprehensive execution monitoring dashboard
2. Implement performance analytics with trend analysis
3. Build cost analysis and optimization recommendations
4. Add alert system for failures and performance issues

### Phase 5: Templates & Collaboration
1. Create workflow template system with parameterization
2. Implement community template sharing and marketplace
3. Build collaborative editing with version control
4. Add export/import functionality for workflow sharing

---

## SUCCESS CRITERIA

**Workflow Design Requirements:**
- Visual designer supports complex workflows with 50+ nodes without performance issues
- Workflow validation catches 95%+ of configuration errors before execution
- Designer is intuitive enough for non-technical users to create basic workflows
- Collaborative editing supports 10+ concurrent users without conflicts
- Version control preserves all workflow changes with rollback capability

**Execution Requirements:**
- Workflow execution success rate exceeds 95% for properly configured workflows
- Real-time monitoring updates within 3 seconds of status changes
- Error handling and retry mechanisms prevent 80%+ of temporary failures
- Parallel execution improves workflow completion time by 50%+ for suitable workflows
- Resource management prevents workflow executions from impacting system performance

**Integration Requirements:**
- AI agent integrations maintain 99%+ uptime and reliability
- Cost tracking accuracy is within 2% of actual platform billing
- Agent selection algorithms optimize for performance and cost
- External integrations (webhooks, APIs) handle failures gracefully
- Workflow templates cover 80% of common business automation use cases

**User Experience Requirements:**
- Workflow creation from template takes under 10 minutes for new users
- Execution monitoring provides clear visibility into workflow progress
- Error messages are actionable and guide users to resolution
- Mobile interface supports workflow monitoring and basic management
- Performance analytics provide insights for workflow optimization

---

Begin implementation by setting up the visual workflow designer foundation and basic AI agent integration. Focus on creating an intuitive design experience that can handle complex logic before adding advanced execution and monitoring features.
