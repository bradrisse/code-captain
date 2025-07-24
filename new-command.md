# New Command Meta-Command

## Purpose
Create new code-captain framework commands by analyzing requirements, discovering relevant tools, and generating structured command documentation with appropriate Cursor tool and MCP integrations.

## When to Use
- Creating new commands for the code-captain framework
- Standardizing command structure and tool usage across the framework
- Discovering and integrating relevant MCP tools for specific command purposes
- Ensuring new commands follow established patterns and best practices
- Building domain-specific commands (e.g., GitHub, database, API-focused commands)
- Extending the framework with team or project-specific workflows

## Process

### Phase 0: Analyze Command Requirements and Context
**Objective:** Understand the new command requirements and existing framework patterns

**Actions:**
1. Create todos for all command creation phases using `todo_write`
2. Use `codebase_search` to understand existing command patterns:
   - "How are existing commands structured?"
   - "What common patterns exist across commands?"
   - "What tool integrations are currently used?"
3. Use `file_search` to catalog existing commands and their purposes
4. Gather command requirements from user:
   - Command name and purpose
   - Target domain or workflow
   - Expected inputs and outputs
   - Integration requirements
5. Analyze similar existing commands for pattern reference

**Todo Structure:**
```
- Phase 0: Analyze command requirements and context [in_progress]
- Phase 1: Discover and catalog available tools [pending]
- Phase 2: Design command structure and integrations [pending]
- Phase 3: Generate command documentation [pending]
```

**Deliverables:**
- Command requirements specification
- Existing pattern analysis
- Similar command references

### Phase 1: Discover and Catalog Available Tools
**Objective:** Identify all available Cursor tools and relevant MCP integrations for the new command

**Actions:**
1. Catalog all available Cursor internal tools with their capabilities
2. Identify available MCP function tools in the current LLM environment by examining available functions
3. Inventory which MCP tools are accessible (GitHub, Slack, databases, etc.)
4. Match command requirements with appropriate tool capabilities (both Cursor and MCP)
5. Identify potential tool combinations and workflows
6. Plan integration patterns for available MCPs with fallback strategies

**Cursor Internal Tools Catalog:**

#### Core Development Tools
- **`codebase_search`** - Semantic search across codebase for understanding context and patterns
- **`grep_search`** - Fast regex-based text search for exact matches and patterns  
- **`file_search`** - Fuzzy filename search for finding specific files
- **`read_file`** - Read file contents with line range support
- **`edit_file`** - Create or modify files with structured edits
- **`search_replace`** - Find and replace text in files with context
- **`delete_file`** - Remove files from the project
- **`list_dir`** - Explore directory contents and structure

#### Command Execution Tools
- **`run_terminal_cmd`** - Execute shell commands and scripts
- **`web_search`** - Search the internet for information and research

#### Workflow Management Tools  
- **`todo_write`** - Create and manage structured todo lists for progress tracking
- **`update_memory`** - Store and retrieve persistent information across sessions

#### Version Control Tools
- **`fetch_pull_request`** - Retrieve pull request and commit information from repositories

#### Documentation Tools
- **`create_diagram`** - Generate Mermaid diagrams for documentation
- **`edit_notebook`** - Edit Jupyter notebook cells for data science workflows

#### MCP Tools (Available)
- **Dynamic Discovery**: Query available MCP tools during command creation
- **Domain-Specific Integration**: Utilize relevant MCPs based on command domain
- **Fallback Planning**: Design commands to work with or without specific MCPs

**MCP Tool Discovery Process:**
1. Examine available function tools to identify MCP integrations (functions starting with `mcp_`)
2. Catalog discovered MCP tools by category (GitHub, communication, databases, etc.)
3. Identify which available MCPs are relevant to command domain
4. Map available MCP capabilities to command requirements
5. Plan integration strategies for relevant MCPs
6. Design fallback workflows for when MCPs are unavailable

**Deliverables:**
- Complete Cursor tools catalog with use cases
- Available MCP tools inventory and relevance assessment
- Tool capability mapping to command requirements
- Integration feasibility and fallback planning

### Phase 2: Design Command Structure and Integrations
**Objective:** Design the new command following framework patterns with appropriate tool integrations

**Actions:**
1. Design command phases following the established 4-phase pattern:
   - Phase 0: Analysis and context gathering
   - Phase 1: Research and discovery
   - Phase 2: Processing and synthesis  
   - Phase 3: Documentation and output
2. Select appropriate Cursor tools for each phase
3. Design MCP tool integration points
4. Plan todo structure and progress tracking
5. Define input requirements and output formats
6. Create workflow diagrams if needed using `create_diagram`

**Command Design Framework:**

**Essential Elements for Every Command:**
- **Purpose**: Clear statement of what the command does
- **When to Use**: Specific scenarios and triggers
- **Process**: 4-phase structured workflow
- **Tool Integration**: Appropriate Cursor and MCP tools
- **Deliverables**: Clear outputs and artifacts
- **Best Practices**: Guidelines for effective usage
- **Common Pitfalls**: What to avoid

**Tool Selection Guidelines:**
- **Analysis Phase**: `codebase_search`, `file_search`, `list_dir`
- **Research Phase**: `web_search`, MCP tools
- **Processing Phase**: `read_file`, `edit_file`, domain-specific MCPs
- **Documentation Phase**: `edit_file`, `create_diagram`, `todo_write`

**Deliverables:**
- Command structure design
- Tool integration plan
- Phase-by-phase workflow
- Output format specification

### Phase 3: Generate Command Documentation
**Objective:** Create comprehensive command documentation following framework standards

**Actions:**
1. Generate command documentation using the established template
2. Include all required sections with appropriate detail
3. Document MCP integration approach (MCP-First vs MCP-Enhanced):
   - **MCP-First**: Primary workflow uses MCP tools, fallback informs user of limitations
   - **MCP-Enhanced**: Core workflow + optional MCP integration sections
4. Add domain-specific examples and use cases
5. Document tool integration patterns with clear MCP priority level
6. Create usage examples and best practices
7. Add the new command to the commands overview
8. Update framework documentation as needed

**Command Documentation Template:**

```markdown
# [Command Name] Command

## Purpose
[Clear statement of command purpose and capabilities]

## When to Use
- [Specific use case 1]
- [Specific use case 2]
- [Integration scenario]
- [Workflow trigger]

## Process

### Phase 0: [Analysis Phase Name]
**Objective:** [What this phase accomplishes]

**Actions:**
1. Create todos for all phases using `todo_write`
2. Use `[appropriate_tool]` to [specific action]:
   - [Search query or action 1]
   - [Search query or action 2]
3. [Additional actions with tools]

**Todo Structure:**
```
- Phase 0: [Phase description] [in_progress]
- Phase 1: [Phase description] [pending]
- Phase 2: [Phase description] [pending]
- Phase 3: [Phase description] [pending]
```

**Deliverables:**
- [Deliverable 1]
- [Deliverable 2]

### [Phases 1-3 follow same pattern]

## [Domain-Specific Sections]
[Add sections specific to the command domain]

## Tool Integration

### Cursor Tools Used
- **`tool_name`**: [Purpose and usage]
- **`another_tool`**: [Purpose and usage]

### MCP Integrations
**Priority Level**: [MCP-First | MCP-Enhanced]

**For MCP-First Commands:**
- **Primary MCP**: [Name] - [Core functionality and usage]
- **Alternative MCPs**: [Other options] - [When to use alternatives]
- **Fallback Strategy**: [What happens when MCP unavailable]

**For MCP-Enhanced Commands:**
- **Optional MCP**: [Name] - [Enhancement purpose and usage]
- **Core Workflow**: [How command works without MCP]
- **Enhanced Workflow**: [Additional capabilities with MCP]

## Best Practices
[Guidelines for effective command usage]

## Common Pitfalls to Avoid
[What to avoid when using this command]
```

**Deliverables:**
- Complete command documentation
- Updated commands overview
- Integration examples
- Usage guidelines

## Available Cursor Internal Tools Reference

### File and Code Operations
| Tool | Purpose | Best Used For |
|------|---------|---------------|
| `codebase_search` | Semantic search across codebase | Understanding context, finding patterns, analyzing code relationships |
| `grep_search` | Fast regex text search | Finding exact matches, symbol searches, pattern matching |
| `file_search` | Fuzzy filename search | Locating specific files when you know partial names |
| `read_file` | Read file contents | Analyzing code, understanding implementations, gathering context |
| `edit_file` | Create/modify files | Writing new code, updating documentation, making structured changes |
| `search_replace` | Find and replace text | Making precise text modifications with context |
| `delete_file` | Remove files | Cleaning up, removing obsolete files |
| `list_dir` | Directory exploration | Understanding project structure, finding related files |

### Execution and Research
| Tool | Purpose | Best Used For |
|------|---------|---------------|
| `run_terminal_cmd` | Execute shell commands | Git operations, build scripts, system commands, testing |
| `web_search` | Internet research | Market research, technology investigation, best practices |

### Workflow and Documentation
| Tool | Purpose | Best Used For |
|------|---------|---------------|
| `todo_write` | Manage structured todos | Progress tracking, phase management, task organization |
| `update_memory` | Persistent information storage | Saving context between sessions, storing configuration |
| `create_diagram` | Generate Mermaid diagrams | Architecture visualization, process documentation |
| `edit_notebook` | Jupyter notebook editing | Data science workflows, analysis documentation |

### Version Control
| Tool | Purpose | Best Used For |
|------|---------|---------------|
| `fetch_pull_request` | Retrieve PR/commit info | Understanding changes, analyzing git history |

## MCP Integration Patterns

### Common MCP Categories
1. **Version Control**: GitHub, GitLab, Bitbucket
2. **Communication**: Slack, Discord, Teams
3. **Project Management**: Jira, Linear, Asana
4. **Databases**: PostgreSQL, MongoDB, Redis
5. **Cloud Services**: AWS, Azure, GCP
6. **Development Tools**: Docker, Kubernetes, Jenkins

### MCP Discovery Process
```bash
# Use todo_write to track MCP evaluation
- Identify available MCP function tools in LLM environment [pending]
- Catalog discovered MCP tools by category and capabilities [pending]
- Evaluate relevant MCPs for command domain [pending] 
- Plan MCP integration patterns and fallbacks [pending]
- Document MCP usage and configuration requirements [pending]
```

### Integration Guidelines
- Identify available MCP function tools by examining the LLM's available functions (look for `mcp_` prefixes)
- **Determine MCP Priority Level**: Assess if MCP integration is core value or enhancement
  - **MCP-First**: When MCP integration IS the primary value proposition (e.g., GitHub issues for user stories)
  - **MCP-Enhanced**: When MCP adds value but command works well without it (e.g., optional Slack notifications)
- Plan for MCP authentication and setup requirements when using discovered tools
- Design appropriate workflows based on MCP priority:
  - **MCP-First Commands**: Primary workflow uses MCP, with graceful degradation if unavailable
  - **MCP-Enhanced Commands**: Core workflow + optional MCP integration
- Document MCP-specific configuration needs and usage patterns
- Consider rate limiting and API constraints for external MCP services

## MCP Priority Level Determination

### When to Use MCP-First Approach
Commands should prioritize MCP integration as the primary workflow when:

- **MCP Integration IS the Core Value**: The command's main purpose is to interact with external systems
  - Examples: Creating GitHub issues, sending Slack notifications, database queries
- **Users Expect External System Integration**: Users naturally expect the command to work with external tools
  - Examples: User story creation → GitHub issues, deployment commands → cloud services
- **Manual Alternative is Cumbersome**: Without MCP, users would need complex manual steps
  - Examples: Creating detailed GitHub issues manually vs automated creation with labels/assignments

### When to Use MCP-Enhanced Approach  
Commands should treat MCP as optional enhancement when:

- **Core Functionality is Self-Contained**: Command provides complete value without external integration
  - Examples: Code analysis, documentation generation, local file operations
- **MCP Adds Convenience, Not Core Value**: External integration is nice-to-have
  - Examples: Optional notifications, backup documentation in external systems
- **Multiple MCP Options Available**: Users might prefer different external tools
  - Examples: Notifications could go to Slack, Teams, or Discord

### MCP Priority Assessment Questions
When designing a command, ask:
1. **Primary Value**: Is the external system integration the main reason users would use this command?
2. **User Expectations**: Do users naturally expect this command to work with external tools?
3. **Manual Effort**: How difficult is it for users to accomplish the external integration manually?
4. **Command Completeness**: Does the command provide complete value without MCP integration?

## Command Categories and Tool Recommendations

### Planning and Documentation Commands
**Typical Tools**: `web_search`, `codebase_search`, `edit_file`, `create_diagram`
**MCP Approach**: Usually MCP-Enhanced (core value is documentation, MCP adds distribution)
**MCP Suggestions**: GitHub (for issues), Project management tools
**Examples**: create-prd, create-adr, document-project

### Development Process Commands  
**Typical Tools**: `codebase_search`, `run_terminal_cmd`, `edit_file`, `grep_search`
**MCP Approach**: Mixed - depends on specific command purpose
**MCP Suggestions**: GitHub, CI/CD tools, testing frameworks
**Examples**: commit (MCP-Enhanced), deploy (MCP-First), review-code (MCP-Enhanced)

### Analysis and Discovery Commands
**Typical Tools**: `codebase_search`, `file_search`, `read_file`, `list_dir`
**MCP Approach**: Usually MCP-Enhanced (analysis is primary, external reporting secondary)
**MCP Suggestions**: Code analysis tools, dependency scanners
**Examples**: review-architecture, debug-issue

### Communication and Reporting Commands
**Typical Tools**: `edit_file`, `create_diagram`, `todo_write`
**MCP Approach**: Usually MCP-First (external communication is primary purpose)
**MCP Suggestions**: Slack, email, project management tools
**Examples**: write-status-update (MCP-First), create-proposal (MCP-Enhanced)

### Project Management Commands
**Typical Tools**: `codebase_search`, `web_search`, `edit_file`
**MCP Approach**: Usually MCP-First (external system integration is expected)
**MCP Suggestions**: GitHub, Jira, Linear, Asana
**Examples**: create-user-story (MCP-First), create-epic (MCP-First), assign-tasks (MCP-First)

## Best Practices for Command Creation

### Command Design Principles
- **Single Responsibility**: Each command should have a clear, focused purpose
- **Consistent Structure**: Follow the 4-phase pattern established in the framework
- **Tool Integration**: Leverage appropriate Cursor tools and MCP integrations
- **Progress Tracking**: Always use `todo_write` for phase management
- **Documentation**: Include comprehensive examples and best practices

### Tool Selection Guidelines
- **Start with Context**: Use `codebase_search` and `file_search` to understand current state
- **Research Thoroughly**: Use `web_search` for best practices and alternatives
- **Track Progress**: Use `todo_write` for systematic progress management
- **Execute Safely**: Use `run_terminal_cmd` for necessary system operations
- **Document Clearly**: Use `edit_file` and `create_diagram` for documentation

### MCP Integration Best Practices
- **Evaluate Necessity**: Only integrate MCPs that add significant value
- **Determine Priority Level**: Choose appropriate integration strategy
  - **MCP-First**: For commands where MCP integration is the main value (GitHub issues, Slack notifications, database operations)
  - **MCP-Enhanced**: For commands that work well standalone but benefit from MCP integration
- **Plan for Failures**: Design appropriate graceful degradation based on priority level
- **Document Setup**: Include clear MCP configuration instructions and requirements
- **Provide Appropriate Fallbacks**: 
  - MCP-First: Inform user if MCP unavailable, offer alternative workflow
  - MCP-Enhanced: Continue with core workflow, note missing enhancements

## Example: Creating a "create-user-story" Command

### Phase 0: Requirements Analysis
```bash
Command Purpose: Generate user stories following agile best practices
Domain: Project management, agile development
Potential MCPs: GitHub (for issues), Jira, Linear
Output: Structured user story with acceptance criteria
```

### Phase 1: Tool Discovery
```bash
Cursor Tools Needed:
- codebase_search: Understand project context
- web_search: Research user story best practices  
- edit_file: Create user story documentation

Available MCP Assessment:
- Examine function tools to identify available MCP integrations
- Look for project management MCPs (mcp_github_*, mcp_jira_*, mcp_linear_*, etc.)
- Plan integration if relevant MCPs are available
- Design fallback to file-based workflow if no relevant MCPs exist
```

### Phase 2: Command Design (MCP-First Approach)
```bash
Phase 0: Analyze project context and existing user stories
Phase 1: Research user story formats and gather requirements
Phase 2: Generate user story components and acceptance criteria
Phase 3: Create GitHub issue as primary output, with local documentation as supporting artifact
```

### Phase 3: Documentation Generation (MCP-First)
```bash
Primary Output: GitHub issue with formatted user story content
Supporting Output: /docs/stories/[story-id]-[story-title].md for local reference
Integration: Direct creation in project management tools (GitHub, Jira, Linear)
Fallback: If MCP unavailable, inform user and suggest manual issue creation
```

## Common Pitfalls to Avoid

### Command Design Issues
- Creating commands that are too broad or trying to do too much
- Not following the established 4-phase pattern
- Forgetting to include progress tracking with `todo_write`
- Not researching existing similar commands before creating new ones
- Creating commands without clear use cases or triggers

### Tool Integration Problems
- Using inappropriate tools for specific tasks
- Not leveraging semantic search capabilities of `codebase_search`
- Overusing `run_terminal_cmd` when file operations would be better
- Not considering tool execution order and dependencies
- Ignoring error handling and edge cases

### MCP Integration Mistakes
- Assuming MCPs are always available without fallback plans
- Not documenting MCP setup and authentication requirements
- Creating hard dependencies on specific MCPs
- Not considering rate limits and API constraints
- Forgetting to update documentation when MCP integrations change

### Documentation and Maintenance Issues
- Insufficient examples and use cases in command documentation
- Not updating the commands overview when adding new commands
- Creating commands without clear success criteria
- Not considering how commands integrate with existing workflows
- Forgetting to include troubleshooting and common pitfalls sections 