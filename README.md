# Code Captain

A structured framework for creating consistent, reusable AI prompting commands that integrate with Cursor IDE's internal tools. Code Captain transforms inconsistent AI interactions into predictable, reliable development workflows.

## 🎯 What is Code Captain?

Code Captain solves a critical problem in AI-assisted development: **inconsistent AI outputs between team members**. When different developers use the same AI assistant for similar tasks, they often get varying responses, leading to code inconsistency and reduced team efficiency.

Code Captain provides:
- **Structured Command Framework**: Reusable command definitions that follow consistent 4-phase workflows
- **Cursor Tool Integration**: Deep integration with Cursor's internal tools (`todo_write`, `codebase_search`, `run_terminal_cmd`, etc.)
- **Team Consistency**: Standardized AI interactions that produce consistent outputs across team members
- **Documentation-Driven**: Commands generate comprehensive documentation following industry best practices

## 🚀 Key Benefits

- **🎯 Consistent AI Outputs**: Get the same high-quality results regardless of who runs the command
- **⚡ Faster Development**: Pre-built workflows for common development tasks
- **📚 Built-in Best Practices**: Commands follow industry standards and proven methodologies
- **🔧 Tool Integration**: Seamlessly works with Cursor's internal capabilities
- **👥 Team Collaboration**: Share and reuse effective AI workflows across your team
- **📖 Documentation Focus**: Automatically generates comprehensive project documentation

## 📋 Available Commands

### Planning & Documentation
- **`create-prd.md`** - Create comprehensive Product Requirements Documents
- **`create-adr.md`** - Generate Architecture Decision Records with research and analysis
- **`create-user-story.md`** - Write INVEST-compliant agile user stories with GitHub integration
- **`research.md`** - Conduct systematic research with structured documentation

### Development Workflow
- **`commit.md`** - Generate conventional commit messages by analyzing staged changes
- **`review-architecture.md`** - Analyze and document software architecture patterns
- **`status-update.md`** - Generate plain text status updates from recent git activity

### Framework Management
- **`new-command.md`** - Meta-command for creating new commands in the framework

## 🛠 How It Works

Each Code Captain command follows a structured 4-phase approach:

### Phase 0: Analysis & Context
- Analyze current project state using `codebase_search` and `file_search`
- Create structured todos using `todo_write` for progress tracking
- Gather requirements through targeted questions

### Phase 1: Research & Discovery
- Use `web_search` to research best practices and current standards
- Analyze similar solutions and competitive approaches
- Validate concepts against industry practices

### Phase 2: Processing & Synthesis
- Synthesize research into actionable insights
- Structure information according to established templates
- Apply domain-specific best practices

### Phase 3: Documentation & Output
- Generate comprehensive documentation using standardized templates
- Create deliverables in appropriate project locations (`/docs/adr/`, `/docs/stories/`, etc.)
- Integrate with external tools via MCP when beneficial

## ⚡ Installation

```bash
mkdir .code-captain && curl -sL https://github.com/bradrisse/code-captain/archive/main.tar.gz | tar xz --strip-components=1 --exclude='README.md' --exclude='readme.md' --exclude='README' --exclude='.git*' -C .code-captain
```

## 🎮 Quick Start

### Using a Command

1. **Reference the command** using Cursor's @ symbol:
   ```
   @create-prd.md
   ```

2. **Follow the guided process** - the command will:
   - Analyze your current project state
   - Ask targeted questions to gather requirements
   - Research best practices for your specific needs
   - Generate comprehensive documentation

3. **Review the outputs** - each command creates:
   - Structured documentation in your `/docs/` folder
   - Integration with external tools (GitHub issues, etc.) when available
   - Progress tracking and clear deliverables

### Example: Creating a User Story

```
@create-user-story.md

// The command will:
// 1. Analyze your project context
// 2. Ask about the feature you want to create a story for
// 3. Research user story best practices
// 4. Create a GitHub issue with proper formatting
// 5. Generate local documentation in /docs/stories/
```

### Example: Generating a Commit Message

```
// Stage your changes first
git add .

// Then use the command
@commit.md

// The command will:
// 1. Analyze your staged changes
// 2. Determine appropriate commit type and scope
// 3. Generate conventional commit message
// 4. Offer to execute the commit
```

### Example: Creating a Status Update

```
@status-update.md

// The command will:
// 1. Analyze recent git commits and uncommitted changes
// 2. Group related work by feature/component
// 3. Translate technical changes into readable descriptions
// 4. Generate plain text status update ready for copy/paste
```

## 📁 Project Structure

```
code-captain/
├── commit.md                 # Generate conventional commit messages
├── create-adr.md            # Create Architecture Decision Records
├── create-prd.md            # Create Product Requirements Documents
├── create-user-story.md     # Generate agile user stories
├── new-command.md           # Create new framework commands
├── research.md              # Conduct systematic research
├── review-architecture.md   # Analyze software architecture
├── status-update.md         # Generate status updates from git activity

```

## 🔧 Advanced Features

### Tool Integration
Code Captain leverages Cursor's internal tools for enhanced functionality:

- **`todo_write`**: Progress tracking and phase management
- **`codebase_search`**: Semantic code analysis and context understanding
- **`file_search`**: Intelligent file discovery and exploration
- **`run_terminal_cmd`**: Automated git operations and system commands
- **`web_search`**: Real-time research and best practice discovery
- **`edit_file`**: Structured code and documentation generation

### MCP Integration
Commands integrate with external services through Model Context Protocol:

- **GitHub**: Automatic issue creation, PR analysis, project management
- **Project Management**: Integration with Jira, Linear, Asana (when available)
- **Communication**: Slack, Discord, Teams notifications (when available)

### Parallel Execution
Commands are designed for maximum efficiency with parallel tool execution, significantly reducing response times.

## 📖 Documentation Standards

Code Captain follows established industry standards:

- **ADRs**: Based on Michael Nygard's Architecture Decision Records format
- **User Stories**: INVEST principles with Given-When-Then acceptance criteria
- **Commit Messages**: Conventional Commits specification
- **PRDs**: Industry-standard product requirements documentation
- **Research**: Systematic research methodology with proper source citation

## 🔄 Creating Custom Commands

Use the meta-command to create new commands for your specific workflows:

```
@new-command.md

// Specify your command requirements:
// - Command name and purpose
// - Target domain (GitHub, database, API, etc.)
// - Expected inputs and outputs
// - Integration requirements
```

The framework will:
1. Analyze your requirements
2. Discover relevant tools and integrations
3. Design the command structure
4. Generate complete command documentation following framework patterns

## 🤝 Team Adoption

### For Individual Developers
- Start with `commit.md` for consistent commit messages
- Use `research.md` for investigating new technologies
- Try `create-user-story.md` for agile development workflows

### For Development Teams
- Standardize on Code Captain commands for consistency
- Share custom commands across team members
- Integrate with existing GitHub/project management workflows
- Use ADRs for architectural decision documentation

### For Organizations
- Create organization-specific command libraries
- Integrate with existing development toolchains
- Measure consistency improvements across teams
- Build upon the framework for domain-specific workflows

## 🔍 Example Outputs

### Architecture Decision Record
```markdown
# 0001. Use Day.js for Date Manipulation

**Date:** 2024-01-15
**Status:** Accepted
**Deciders:** Development Team

## Context and Problem Statement
Need a lightweight, reliable date manipulation library...

## Decision Outcome
**Chosen Option:** Day.js for its small bundle size and Moment.js compatibility...
```

### User Story
```markdown
As a customer,
I want to save items to a wishlist,
So that I can purchase them later.

**Acceptance Criteria:**
Given a logged-in customer,
When they click the "Add to Wishlist" button,
Then the item should be saved to their wishlist...
```

### Conventional Commit
```bash
feat(auth): add OAuth2 integration with Google provider

Implement OAuth2 authentication flow using Google Identity Platform.
Includes user profile synchronization and token refresh handling.

Fixes: #234
```

### Status Update
```
Status Update - January 15, 2024

Yesterday:
- Completed OAuth2 integration with Google and GitHub providers
- Fixed critical session timeout bug affecting mobile users
- Code review for payment processing refactor

Today:
- Writing unit tests for authentication module
- Starting user dashboard wireframe review
- Team architecture discussion at 3pm

Blockers:
- API documentation review needed for dashboard endpoints
- Staging environment access required for payment testing
```

## 🤔 Why Code Captain?

**vs. Manual AI Prompting:**
- Consistent outputs across team members
- Built-in best practices and industry standards
- Systematic workflows with progress tracking
- Automatic tool integration and context awareness

**vs. Other AI Frameworks:**
- Purpose-built for Cursor IDE integration
- Documentation-focused approach
- Team collaboration emphasis
- Structured 4-phase methodology

**vs. Generic Templates:**
- Dynamic context analysis
- Real-time research integration
- Tool automation capabilities
- Adaptive workflows based on project state

## 📝 Contributing

Code Captain is designed to be extensible. To add new commands:

1. Use `@new-command.md` to create the command structure
2. Follow the established 4-phase pattern
3. Integrate appropriate Cursor tools
4. Include comprehensive documentation and examples
5. Test with multiple project types and team scenarios

## 📄 License

This project is part of the broader effort to improve AI-assisted development workflows. See individual command files for specific guidance and best practices.

---

**Get Started:** Try `@commit.md` for your next commit, `@status-update.md` for your daily standup, or `@create-user-story.md` for your next agile story. Experience the difference of consistent, tool-integrated AI workflows. 