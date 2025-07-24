# Review Architecture Command

## Purpose
Systematically understand and document the current architectural state of a codebase exactly as it exists, without evaluation or improvement suggestions.

## When to Use
- Onboarding to an existing codebase or system
- Creating comprehensive documentation of current system state
- Building a factual knowledge base about existing system architecture
- Understanding current system structure and implementation
- Documenting existing patterns and conventions
- Creating reference documentation for the current codebase state

## Process

### Phase 1: Define Exploration Scope
**Objective:** Establish what parts of the architecture to understand and document

**Actions:**
1. Create todos for the exploration phases using `todo_write`
2. Define what you want to understand about the system
3. Identify key areas of interest (frontend, backend, data, integrations)
4. Determine exploration boundaries and depth
5. Set timeline for the architectural exploration

**Todo Structure:**
```
- Phase 1: Define exploration scope [in_progress]
- Phase 2: Discover system structure and components [pending]
- Phase 3: Map relationships and data flows [pending]
- Phase 4: Document architectural patterns and context [pending]
```

**Deliverables:**
- Exploration scope and focus areas
- Understanding goals and questions to answer

### Phase 2: Discover System Structure and Components
**Objective:** Understand how the system is organized and what components exist

**Actions:**
1. Use `codebase_search` to explore system structure and organization
2. Search for key architectural patterns:
   - "How is the application structured?"
   - "What are the main components and modules?"
   - "Where are the configuration files and entry points?"
3. Identify technology stack and frameworks in use
4. Map out directory structure and code organization
5. Find and document existing architectural documentation
6. Discover key configuration files and entry points

**Search Strategies:**
- "main application entry point"
- "configuration files and settings"
- "database models and schemas"
- "API routes and endpoints"
- "component structure and organization"
- "dependency management and imports"

**Deliverables:**
- System component map
- Technology stack documentation
- Code organization overview
- Key entry points and configurations

### Phase 3: Map Relationships and Data Flows
**Objective:** Understand how components interact and data moves through the system

**Actions:**
1. Use `codebase_search` to trace data flows and component relationships:
   - "How do components communicate with each other?"
   - "What are the data models and database schemas?"
   - "Where are API calls and service integrations?"
   - "How is state managed and shared?"
2. Identify integration patterns and external dependencies
3. Map authentication and authorization flows
4. Understand deployment and runtime architecture
5. Document key workflows and business processes

**Search Strategies:**
- "database connections and queries"
- "API calls and HTTP requests"
- "message queues and event handling"
- "authentication and session management"
- "external service integrations"
- "data validation and processing flows"

**Deliverables:**
- Component interaction diagrams
- Data flow documentation
- Integration and dependency map
- Key workflow descriptions

### Phase 4: Document Architectural Patterns and Context
**Objective:** Synthesize understanding into comprehensive documentation of the current architectural state

**Actions:**
1. Identify and document key architectural patterns currently in use
2. Summarize current system capabilities and existing constraints
3. Document observable design decisions and their implementation (where discoverable)
4. Create comprehensive overview of existing system architecture
5. Get current date using `date +%Y-%m-%d` command for documentation
6. Create architectural context document in `/docs/architecture/` folder
7. Organize findings as factual reference documentation of current state

**Pattern Documentation:**
- Common design patterns in use (MVC, Repository, Factory, etc.)
- Architectural styles (layered, microservices, monolithic, etc.)
- Data access patterns and ORM usage
- Authentication and authorization patterns
- Error handling and logging approaches
- Testing patterns and strategies

**Deliverables:**
- Comprehensive architectural overview
- Design patterns and conventions documentation
- System capabilities and constraints summary
- **Architecture Context Document:** `/docs/architecture/architecture-context-[DATE].md`
- LLM-ready context summaries for development tasks

## Architecture Context Document Template

**First, get the current date:**
```bash
date +%Y-%m-%d
```

Create a markdown file in `/docs/architecture/architecture-context-[DATE].md` where `[DATE]` is the output from the date command above.

**Example:** `/docs/architecture/architecture-context-2024-01-15.md`

Use the following structure:

```markdown
# Architecture Context Documentation

**Date:** [Use output from date +%Y-%m-%d command]  
**Documented by:** [Name(s)]  
**System/Project:** [System name]  
**Status:** [In Progress/Complete]  

## System Overview
[2-3 paragraph high-level description of what the system does and its main purpose]

## Exploration Scope
[What parts of the system were explored and documented]

## System Architecture

### Core Components
[Description of main system components and their responsibilities]

### Technology Stack
- **Frontend:** [Technologies, frameworks, and libraries in use]
- **Backend:** [Languages, frameworks, databases, and services]
- **Infrastructure:** [Deployment platforms, containers, orchestration]
- **Dependencies:** [Key external services and integrations]

### Directory Structure
[Overview of how the codebase is organized]

### Entry Points
[Main application entry points, configuration files, and startup processes]

## Data Architecture

### Data Models
[Key data structures, entities, and their relationships]

### Database Schema
[Database structure, tables, and key relationships]

### Data Flow
[How data moves through the system from input to storage to output]

### External Data Sources
[APIs, services, and data sources the system depends on]

## Component Interactions

### Communication Patterns
[How components communicate - REST APIs, events, direct calls, etc.]

### Authentication & Authorization
[How user authentication and permissions are handled]

### State Management
[How application state is managed and shared between components]

### Error Handling
[Common error handling patterns and logging approaches]

## Architectural Patterns

### Design Patterns
[Common design patterns identified in the codebase]

### Architectural Style
[Overall architectural approach - monolithic, microservices, layered, etc.]

### Code Organization Patterns
[How code is structured and organized across the system]

### Testing Patterns
[Testing approaches and patterns used in the codebase]

## System Capabilities

### Current Features
[Main features and capabilities the system currently provides]

### Performance Characteristics
[What we know about system performance - response times, throughput, etc.]

### Scalability Characteristics
[How the system currently handles load and growth]

### Security Implementation
[Current security measures and authentication approaches]

## System Constraints

### Technical Constraints
[Known technical limitations or constraints]

### Dependencies
[Critical dependencies that affect system behavior]

### Configuration Requirements
[Key configuration needs and environment setup]

### Operational Constraints
[Deployment, monitoring, or operational limitations]

## Development Context

### Code Quality Patterns
[Observed code quality patterns and conventions]

### Testing Approach
[Current testing strategies and coverage]

### Documentation State
[Available documentation and knowledge gaps]

### Development Workflow
[How development, building, and deployment currently works]

## Integration Points

### External Services
[Services and APIs the system integrates with]

### Data Sources
[External data sources and how they're consumed]

### Third-party Dependencies
[Key libraries, frameworks, and external dependencies]

### API Interfaces
[APIs the system exposes and their characteristics]

## Appendix

### Code Examples
[Key code snippets that illustrate architectural patterns]

### Configuration Examples
[Important configuration files and settings]

### Architecture Diagrams
[System diagrams and visual representations]

### References and Sources
[Links to existing documentation and resources discovered]
```

## Best Practices

### Exploration Strategy
- Start with high-level structure before diving into details
- Use semantic search to understand concepts before looking at specific code
- Focus purely on understanding "what" and "how" the current system works
- Document patterns and conventions exactly as they currently exist

### Documentation Approach
- Use clear, objective language to describe what currently exists
- Focus strictly on facts and observations of the current implementation
- Include specific examples and code snippets that show current state
- Organize information as factual reference material

### Current State Documentation
- Connect related components and show existing relationships
- Document observable design decisions and their current implementation
- Record both explicit and implicit conventions currently in use
- Note areas where current understanding is incomplete or uncertain

### Reference Documentation
- Structure information as clear reference material about current state
- Use consistent terminology that reflects actual system implementation
- Provide sufficient detail about current architecture and patterns
- Organize information logically for reference and understanding

## Common Exploration Areas

### System Structure
- Application entry points and main modules
- Directory organization and code structure
- Component relationships and dependencies
- Configuration files and environment setup
- Build and deployment processes

### Data Handling
- Data models and database schemas
- Data validation and processing flows
- API endpoints and data interfaces
- Caching and data storage patterns
- External data source integrations

### Communication Patterns
- Inter-component communication methods
- API design and usage patterns
- Message queues and event handling
- Authentication and session management
- Error handling and logging approaches

### Development Patterns
- Code organization and naming conventions
- Testing strategies and patterns
- Documentation and comments
- Dependency management and imports
- Version control and branching patterns

