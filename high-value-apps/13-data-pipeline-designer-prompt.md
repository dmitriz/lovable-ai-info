# Data Pipeline Designer

**Task:** Create a visual data pipeline builder that allows users to design, test, and monitor data transformation workflows.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for pipeline configurations and execution history
- Clean, minimalist UI with ShadCN components
- **Minimalistic Design Focus:** Create a very light design that minimizes vertical space usage. Each content line should take up as little vertical space as possible while using horizontal space more generously. Avoid extra visual elements between content lines - use only white spaces for separation. Focus on content over decoration with a clean, minimal aesthetic.

**Constraints:**
- Start with core functionality only
- Single page application
- Client-side data processing initially

---

## MVP Features (Build First)

1. **Visual Pipeline Builder** - Drag-and-drop interface for creating data flows
2. **Transform Nodes** - Pre-built transformation components (filter, map, aggregate)
3. **Data Preview** - Real-time preview of data at each pipeline stage
4. **Pipeline Execution** - Run pipelines with sample data
5. **Export Options** - Generate code or configuration files

## Data Structure (Local Storage)
```javascript
// pipelines: Array stored in localStorage
const pipelines = [
  {
    id: "uuid",
    name: "User Data Processing",
    description: "Process and clean user data",
    nodes: [
      {
        id: "node-1",
        type: "source",
        config: {
          type: "csv",
          data: "sample data..."
        },
        position: { x: 100, y: 100 }
      },
      {
        id: "node-2",
        type: "transform",
        config: {
          operation: "filter",
          condition: "age > 18"
        },
        position: { x: 300, y: 100 }
      }
    ],
    connections: [
      {
        source: "node-1",
        target: "node-2"
      }
    ],
    created: "2025-01-15"
  }
]

// executions: Array stored in localStorage
const pipeline_executions = [
  {
    id: "uuid",
    pipeline_id: "pipeline-uuid",
    status: "completed",
    input_records: 1000,
    output_records: 850,
    execution_time: 1200,
    errors: [],
    executed_at: "2025-01-15T10:00:00Z"
  }
]
```

## Design System
- **Colors:** Indigo theme (data/flow) with proper dark mode variants
- **Layout:** Canvas-based design with toolbar and property panels
- **Responsive:** Adaptive canvas with touch support for mobile

---

## Development Roadmap

**Start with MVP:** Create a basic visual pipeline editor with simple data transformations.

### Phase 1: Core Builder (MVP)
- Visual canvas with drag-and-drop
- Basic transformation nodes
- Connection system
- Data preview

### Phase 2: Advanced Transformations
- Custom transformation functions
- Data validation nodes
- Conditional branching
- Error handling

### Phase 3: Integration & Deployment
- External data source connectors
- Pipeline scheduling
- Performance monitoring
- Code generation for deployment

---

## Technical Implementation

### Core Components
1. **PipelineCanvas** - Visual drag-and-drop interface
2. **NodeLibrary** - Collection of transformation components
3. **DataPreview** - Real-time data visualization
4. **ExecutionEngine** - Pipeline execution and monitoring

### Transform Engine
- Functional data transformation library
- Stream processing capabilities
- Error handling and validation
- Performance optimization

### Key Features
- Visual pipeline design
- Real-time data preview
- Custom transformation nodes
- Pipeline version control
- Execution monitoring and logging
