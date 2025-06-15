# API Testing & Validation Suite

**Task:** Create a comprehensive API testing platform that validates endpoints, monitors performance, and generates test reports.

**Guidelines:**
- Mobile-responsive design with dark mode support
- Use local storage for test suites and results
- Clean, minimalist UI with ShadCN components
- **Minimalistic Design Focus:** Create a very light design that minimizes vertical space usage. Each content line should take up as little vertical space as possible while using horizontal space more generously. Avoid extra visual elements between content lines - use only white spaces for separation. Focus on content over decoration with a clean, minimal aesthetic.

**Constraints:**
- Start with core functionality only
- Single page application
- Client-side HTTP requests with CORS considerations

---

## MVP Features (Build First)

1. **Request Builder** - Visual interface for creating HTTP requests
2. **Test Suites** - Organize and group related API tests
3. **Response Validation** - Automatic validation of response structure and data
4. **Performance Testing** - Response time and load testing capabilities
5. **Test Reports** - Comprehensive test result reporting and history

## Data Structure (Local Storage)
```javascript
// test_suites: Array stored in localStorage
const test_suites = [
  {
    id: "uuid",
    name: "User API Tests",
    description: "Tests for user management endpoints",
    base_url: "https://api.example.com",
    tests: ["test-uuid-1", "test-uuid-2"],
    created: "2025-01-15"
  }
]

// tests: Array stored in localStorage
const api_tests = [
  {
    id: "uuid",
    suite_id: "suite-uuid",
    name: "Get User Profile",
    method: "GET",
    endpoint: "/users/{id}",
    headers: {
      "Authorization": "Bearer {token}",
      "Content-Type": "application/json"
    },
    body: null,
    validations: [
      {
        type: "status_code",
        expected: 200
      },
      {
        type: "response_schema",
        schema: {
          type: "object",
          required: ["id", "name", "email"]
        }
      }
    ],
    created: "2025-01-15"
  }
]

// test_results: Array stored in localStorage
const test_results = [
  {
    id: "uuid",
    test_id: "test-uuid",
    suite_id: "suite-uuid",
    status: "passed",
    response_time: 245,
    response_code: 200,
    response_body: "...",
    validations: [
      {
        type: "status_code",
        passed: true,
        message: "Status code matches expected"
      }
    ],
    executed_at: "2025-01-15T10:00:00Z"
  }
]
```

## Design System
- **Colors:** Teal theme (testing/validation) with proper dark mode variants
- **Layout:** Multi-panel design (test tree, request builder, results)
- **Responsive:** Collapsible panels for mobile

---

## Development Roadmap

**Start with MVP:** Create a basic API testing interface with request building and response validation.

### Phase 1: Core Testing (MVP)
- HTTP request builder
- Basic response validation
- Test suite organization
- Simple reporting

### Phase 2: Advanced Validation
- JSON schema validation
- Custom assertion rules
- Performance benchmarking
- Automated test execution

### Phase 3: Integration & Automation
- CI/CD integration
- Scheduled test runs
- Team collaboration
- Advanced reporting and analytics

---

## Technical Implementation

### Core Components
1. **RequestBuilder** - Visual HTTP request construction
2. **TestSuiteManager** - Organize and manage test collections
3. **ValidationEngine** - Response validation and assertion checking
4. **ReportGenerator** - Test result analysis and reporting

### Testing Engine
- HTTP client for API requests
- JSON schema validation
- Performance metrics collection
- Result aggregation and analysis

### Key Features
- Visual request building
- Automated response validation
- Performance monitoring
- Test result history
- Export/import test suites
