# AI Agent Orchestrator Dashboard - High-Quality Lovable Prompt

**Context:** You are a world-class full-stack developer specializing in AI agent orchestration systems, with expertise in React, TypeScript, Supabase, and modern UI/UX design. You have deep understanding of multi-agent AI workflows, LangGraph patterns, and enterprise-grade system monitoring.

**Task:** Build a comprehensive AI Agent Orchestrator Dashboard that enables teams to register, monitor, coordinate, and optimize multiple AI agents working together in complex workflows.

**Guidelines:** 
- Use React + TypeScript + Supabase + TailwindCSS + ShadCN components
- Follow mobile-first responsive design principles across all breakpoints
- Implement real-time updates using Supabase real-time subscriptions
- Create clean, professional enterprise-grade UI with intuitive navigation
- Use TypeScript for all components with proper type safety
- Integrate chart libraries (Recharts) for analytics and monitoring
- Follow atomic design principles with reusable components

**Constraints:** 
- Don't modify any configuration files unless absolutely necessary
- Focus on the core dashboard functionality first before adding advanced features
- Ensure all database operations use proper RLS (Row Level Security) policies
- Must work seamlessly across desktop, tablet, and mobile devices
- Use environment variables for all API keys and sensitive configuration

---

## PROJECT REQUIREMENTS DOCUMENT (PRD)

### Introduction
The AI Agent Orchestrator Dashboard is a comprehensive web application that enables teams to manage, monitor, and coordinate multiple AI agents working together in complex workflows. It addresses the critical need for centralized oversight and optimization of multi-agent AI systems.

**Target Users:** AI engineers, DevOps teams, product managers overseeing AI agent deployments

### Core Features

1. **Agent Registry & Management**
   - Register new agents with capabilities, models, and configurations
   - Agent status monitoring (online/offline/busy/error states)
   - Capability-based agent discovery and matching
   - Agent versioning and deployment history
   - Bulk operations for agent management

2. **Real-Time Workflow Monitoring**
   - Live workflow execution tracking with visual progress indicators
   - Agent-to-agent communication logs and message tracing
   - Performance metrics dashboard (response times, success rates, costs)
   - Error tracking and alerting with detailed error context
   - Resource utilization monitoring (CPU, memory, API calls)

3. **Workflow Coordination Interface**
   - Visual workflow builder using drag-and-drop components
   - Agent assignment based on capabilities and availability
   - Conditional logic and branching for complex workflows
   - Manual intervention points for human-in-the-loop workflows
   - Workflow templates and reusable patterns

4. **Analytics & Optimization**
   - Historical performance analytics with trending
   - Cost analysis and optimization recommendations
   - Agent utilization reports and capacity planning
   - Workflow success/failure analysis
   - Custom dashboard widgets and reports

5. **System Administration**
   - User management with role-based access control
   - System health monitoring and diagnostics
   - Configuration management for agents and workflows
   - Audit trails and compliance reporting
   - Integration management for external systems

### Tech Stack
- **Frontend:** React 18+ with TypeScript, TailwindCSS, ShadCN/UI
- **Backend:** Supabase (PostgreSQL + Auth + Real-time + Edge Functions)
- **State Management:** React Query (TanStack Query) for server state
- **Charts/Visualization:** Recharts, React Flow for workflow visualization
- **Icons:** Lucide React icons
- **Real-time:** Supabase real-time subscriptions

### User Flow
**Start:** User logs in and sees overview dashboard → **Navigation:** User selects agents, workflows, or analytics sections → **Management:** User registers new agents or creates workflows → **Monitoring:** User monitors live workflow execution → **Analysis:** User reviews performance analytics → **Optimization:** User adjusts configurations based on insights → **End state:** Optimized multi-agent system with improved performance

### Design Principles
- **Colors:** Primary #3B82F6 (blue-500), Secondary #64748B (slate-500), Success #10B981 (emerald-500), Warning #F59E0B (amber-500), Error #EF4444 (red-500), Background #F8FAFC (slate-50)
- **Typography:** Inter font family, consistent text sizing (text-sm, text-base, text-lg for hierarchy)
- **Layout:** Grid-based layout with consistent spacing (p-4, gap-4, m-6), card-based design for sections
- **Components:** Rounded corners (rounded-lg), subtle shadows (shadow-sm), consistent button styles
- **Responsive:** Mobile-first with breakpoints at sm:640px, md:768px, lg:1024px, xl:1280px

### Database Schema (Supabase)

**agents table:**
- id: UUID primary key
- name: text not null
- description: text
- capabilities: jsonb (array of capability objects)
- model_config: jsonb (AI model configuration)
- status: text default 'inactive' check (status in ('active', 'inactive', 'error', 'busy'))
- endpoint_url: text
- api_key_encrypted: text
- created_at: timestamptz default now()
- updated_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**workflows table:**
- id: UUID primary key
- name: text not null
- description: text
- workflow_config: jsonb (workflow definition and steps)
- status: text default 'draft' check (status in ('draft', 'active', 'paused', 'archived'))
- created_at: timestamptz default now()
- updated_at: timestamptz default now()
- created_by: UUID references auth.users(id)

**workflow_executions table:**
- id: UUID primary key
- workflow_id: UUID references workflows(id)
- status: text default 'running' check (status in ('running', 'completed', 'failed', 'cancelled'))
- input_data: jsonb
- output_data: jsonb
- execution_log: jsonb (detailed execution steps and agent interactions)
- started_at: timestamptz default now()
- completed_at: timestamptz
- created_by: UUID references auth.users(id)

**agent_metrics table:**
- id: UUID primary key
- agent_id: UUID references agents(id)
- execution_id: UUID references workflow_executions(id)
- metric_type: text not null (response_time, cost, success_rate, etc.)
- metric_value: numeric not null
- timestamp: timestamptz default now()

### Security (RLS Policies)
- Users can only see agents and workflows they created or have been granted access to
- Agents table: `auth.uid() = created_by OR auth.uid() IN (SELECT user_id FROM agent_permissions WHERE agent_id = agents.id)`
- Workflows table: `auth.uid() = created_by OR auth.uid() IN (SELECT user_id FROM workflow_permissions WHERE workflow_id = workflows.id)`
- Real-time subscriptions filtered by user permissions
- Encrypted storage for sensitive agent API keys

### In-Scope vs Out-of-Scope

**In-Scope:**
- Core agent registration and management
- Real-time workflow monitoring and coordination
- Basic analytics and performance tracking
- User authentication and basic permissions
- Mobile-responsive dashboard interface
- Integration with common AI APIs (OpenAI, Anthropic, etc.)

**Out-of-Scope:**
- Advanced machine learning for workflow optimization
- Custom AI model training or fine-tuning
- Complex enterprise integrations (LDAP, SSO)
- Advanced audit and compliance features
- Multi-tenant architecture for this initial version

---

## IMPLEMENTATION INSTRUCTIONS

### Phase 1: Foundation Setup
1. Create the core Supabase database schema with proper RLS policies
2. Set up authentication with user management
3. Build the main dashboard layout with navigation and routing
4. Implement responsive design system with TailwindCSS and ShadCN

### Phase 2: Agent Management
1. Create agent registration forms with capability selection
2. Build agent list/grid views with status indicators
3. Implement agent detail pages with configuration options
4. Add real-time status updates using Supabase subscriptions

### Phase 3: Workflow System
1. Design workflow creation interface with visual builder
2. Implement workflow execution engine (basic version)
3. Create real-time monitoring dashboard for running workflows
4. Add workflow history and execution logs

### Phase 4: Analytics & Optimization
1. Build performance metrics collection system
2. Create analytics dashboard with charts and trending
3. Implement cost tracking and optimization recommendations
4. Add custom dashboard widgets and reporting

### Phase 5: Polish & Enhancement
1. Add comprehensive error handling and user feedback
2. Implement advanced search and filtering capabilities
3. Create system health monitoring and diagnostics
4. Add export functionality for reports and data

---

## SUCCESS CRITERIA

**Functional Requirements:**
- Users can register and manage AI agents with full CRUD operations
- Real-time workflow monitoring works smoothly without lag
- Analytics dashboard provides meaningful insights into agent performance
- Mobile interface is fully functional and user-friendly
- All database operations are secure and follow RLS policies

**Performance Requirements:**
- Page load times under 2 seconds on 3G connections
- Real-time updates have less than 500ms latency
- Dashboard can handle 100+ agents and 1000+ workflow executions
- Database queries are optimized with proper indexing

**User Experience Requirements:**
- Intuitive navigation that requires no training
- Consistent design system across all components
- Responsive design works perfectly on all device sizes
- Clear error messages and loading states throughout
- Professional, modern aesthetic suitable for enterprise use

---

Begin implementation by setting up the Supabase database schema and main dashboard layout. Focus on creating a solid foundation that can support the advanced features in later phases.
