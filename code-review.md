# Code Review Command

## Purpose
Implement structured self-review methodology for uncommitted local changes using research-backed hybrid AI+human approach. Analyze staged and unstaged changes with context-specific review prompts to identify issues before committing code.

## When to Use
- Reviewing uncommitted changes before staging or committing
- Self-auditing code quality, security, and maintainability of local changes
- Applying context-specific review checklists for different code types (security, performance, API, frontend)
- Identifying potential issues in local development before sharing with team
- Learning effective review techniques through systematic self-analysis
- Conducting pre-commit analysis to ensure code quality standards

## Process

### Phase 0: Analyze Local Changes and Context
**Objective:** Understand uncommitted changes, project context, and appropriate review approach

**Actions:**
1. Create todos for all phases using `todo_write`
2. Use `run_terminal_cmd` to analyze current git status:
   - `git status --porcelain` to identify modified, added, and deleted files
   - `git diff --name-only` to get list of changed files
   - `git diff --stat` to understand scope of changes
3. Use `codebase_search` to understand project context:
   - "What are the main architectural patterns in this codebase?"
   - "What security considerations are important for this project?"
   - "What coding standards and conventions are used?"
4. Use `file_search` to identify relevant dependencies for changed files
5. Determine review scope and complexity:
   - Single file changes vs. multi-component changes
   - New feature development vs. bug fixes vs. refactoring
   - Security-sensitive areas vs. general functionality
6. Select appropriate review framework based on code type and scope

**Todo Structure:**
```
- Phase 0: Analyze review context and scope [in_progress]
- Phase 1: Research domain-specific best practices [pending]
- Phase 2: Conduct systematic code analysis [pending]
- Phase 3: Generate review documentation and GitHub integration [pending]
```

**Deliverables:**
- Git status and change scope analysis
- Project context summary
- Review framework selection
- Self-review checklist preparation

### Phase 1: Research Domain-Specific Best Practices
**Objective:** Gather relevant best practices and standards for the specific type of code being reviewed

**Actions:**
1. Use `web_search` to research current best practices for identified code domain:
   - "Security best practices for [language/framework] code review"
   - "Performance optimization patterns for [specific domain]"
   - "API design best practices and review criteria"
   - "Frontend code review checklist [framework-specific]"
2. Use `codebase_search` to identify existing patterns and conventions:
   - "How is error handling implemented in this codebase?"
   - "What authentication patterns are used?"
   - "How are database operations structured?"
3. Research domain-specific security considerations and common vulnerabilities
4. Identify relevant automated tools and linting rules for the technology stack

**Deliverables:**
- Domain-specific best practices documentation
- Security checklist relevant to code type
- Performance optimization guidelines
- Technology-specific review criteria

### Phase 2: Conduct Systematic Code Analysis
**Objective:** Perform comprehensive analysis following staged hybrid review approach

**Actions:**
1. **Stage 1: Automated Analysis** (AI-focused review areas)
   - Use `run_terminal_cmd` with `git diff` to examine specific changes
   - Use `read_file` to analyze modified files in context
   - Check coding standards and style consistency
   - Identify basic security patterns (input validation, error handling)
   - Analyze code complexity and maintainability indicators
   - Review naming conventions and documentation quality

2. **Stage 2: Human-Focused Analysis** (Context requiring human judgment)
   - Business logic correctness and completeness
   - Architectural alignment and design pattern adherence
   - Complex security implications and threat modeling
   - Performance implications and scalability considerations
   - User experience and accessibility considerations (for frontend)

3. **Stage 3: Integration and Dependency Analysis**
   - Impact on existing functionality and backwards compatibility
   - Database schema changes and migration considerations
   - API contract changes and versioning implications
   - Testing coverage and quality assessment

4. Use `codebase_search` to check for consistency with existing implementations:
   - "How are similar features implemented elsewhere?"
   - "What testing patterns are used for this type of functionality?"

**Deliverables:**
- Automated analysis report with specific findings
- Human review checklist with context-specific items
- Integration impact assessment
- Testing and validation recommendations

### Phase 3: Generate Review Documentation and Action Items
**Objective:** Create comprehensive self-review documentation with clear improvement recommendations

**Actions:**
1. Generate structured review documentation using `edit_file`:
   - Executive summary of changes and impact
   - Detailed findings organized by category (quality, security, performance)
   - Specific action items with priority levels
   - Recommendations for improvement before committing
   - Self-assessment checklist completion

2. Create local review documentation:
   - Generate `/docs/code-reviews/[short-name]-review-[YYYY-MM-DD].md` with comprehensive findings
     - Short-name: Descriptive name based on main changes (e.g., "auth-security", "api-refactor", "ui-components")
     - Date format: `YYYY-MM-DD` consistent with other docs files
   - Document patterns and lessons learned for future reference
   - Create actionable checklist for immediate code improvements

3. Provide immediate next steps:
   - High-priority issues that must be fixed before commit
   - Medium-priority improvements to consider
   - Low-priority enhancements for future consideration
   - Code patterns to apply consistently

**Deliverables:**
- Comprehensive self-review documentation in `/docs/code-reviews/`
- Prioritized action items for code improvement
- Local knowledge base updates
- Ready-to-commit assessment

## Review Framework Matrix

### By Code Type

#### Security-Sensitive Code
**Focus Areas:**
- Input validation and sanitization
- Authentication and authorization mechanisms
- Data encryption and secure storage
- SQL injection and XSS prevention
- Secure API design and rate limiting

**Review Checklist:**
- [ ] All user inputs properly validated and sanitized
- [ ] Authentication mechanisms correctly implemented
- [ ] Authorization checks in place for all operations
- [ ] Sensitive data properly encrypted/hashed
- [ ] No hardcoded secrets or credentials
- [ ] Error messages don't leak sensitive information
- [ ] Security headers and CORS properly configured

#### Performance-Critical Code
**Focus Areas:**
- Algorithm efficiency and complexity analysis
- Database query optimization
- Caching strategies and implementation
- Memory usage and garbage collection
- Concurrent processing and thread safety

**Review Checklist:**
- [ ] Algorithm complexity appropriate for expected data size
- [ ] Database queries optimized with proper indexing
- [ ] Caching implemented where beneficial
- [ ] Memory allocation and cleanup handled correctly
- [ ] Thread safety considered for concurrent operations
- [ ] Performance testing strategy defined

#### API and Integration Code
**Focus Areas:**
- RESTful design principles
- Error response consistency
- Versioning strategy
- Documentation completeness
- Backwards compatibility

**Review Checklist:**
- [ ] RESTful conventions followed consistently
- [ ] Error responses follow standardized format
- [ ] API versioning strategy implemented
- [ ] Comprehensive documentation provided
- [ ] Backwards compatibility maintained
- [ ] Rate limiting and throttling considered

#### Frontend and UI Code
**Focus Areas:**
- User experience and accessibility
- Performance and responsiveness
- Cross-browser compatibility
- State management patterns
- Component reusability

**Review Checklist:**
- [ ] Accessibility standards (WCAG) followed
- [ ] Responsive design implemented correctly
- [ ] Cross-browser compatibility tested
- [ ] State management follows established patterns
- [ ] Components designed for reusability
- [ ] Performance optimizations applied

### By Change Size and Complexity

#### Small Changes (< 50 lines)
- Lightweight review focusing on immediate impact
- Automated checks for style and basic security
- Single reviewer sufficient
- Fast turnaround expected (< 4 hours)

#### Medium Changes (50-400 lines)
- Standard review process with domain expert
- Both automated and human review stages
- Focus on business logic and integration points
- Target completion within 24 hours

#### Large Changes (> 400 lines)
- Comprehensive review with multiple perspectives
- Architectural review for significant changes
- Break down into smaller reviewable chunks when possible
- Extended timeline with staged review process

## Cursor Tools Used
- **`run_terminal_cmd`**: Git status analysis and diff examination
- **`codebase_search`**: Project context analysis and pattern discovery
- **`file_search`**: Locate relevant files and dependencies
- **`read_file`**: Detailed code analysis and examination of modified files
- **`web_search`**: Research domain-specific best practices and security guidelines
- **`todo_write`**: Progress tracking and phase management
- **`edit_file`**: Generate review documentation and reports

## Review Quality Framework

### Effectiveness Metrics
Based on research showing 76% effectiveness of well-designed review prompts:

**Code Quality & Maintainability (26% focus):**
- Code clarity and readability assessment
- DRY principle adherence verification
- SOLID principles compliance check
- Error handling consistency review

**Code Performance (22% focus):**
- Algorithm efficiency analysis
- Resource management evaluation
- Scalability consideration review
- Concurrency handling assessment

**Security (Critical focus):**
- Input validation verification
- Authentication/authorization check
- Secure coding practices review
- Data protection implementation

**Additional Areas:**
- Testing coverage and quality
- Documentation completeness
- Integration and compatibility
- Maintainability and technical debt



## Best Practices

### For Self-Review
- **Focus on High-Impact Issues**: Prioritize business logic, security, and architecture over style
- **Use Staged Approach**: Let automated analysis handle routine checks, focus on complex decisions
- **Be Critical but Constructive**: Identify issues objectively and plan specific improvements
- **Consider Impact**: Evaluate changes in context of overall system architecture
- **Document Learning**: Keep notes on patterns and issues for future reference



## Common Pitfalls to Avoid

### Review Process Issues
- **Over-focusing on Style**: Spending too much time on formatting instead of logic
- **Generic Checklists**: Using one-size-fits-all approaches instead of context-specific reviews
- **Delayed Reviews**: Allowing reviews to sit for days, blocking development progress
- **Inconsistent Standards**: Applying different criteria across team members or projects
- **Missing Context**: Reviewing code without understanding business requirements or constraints

### Technical Review Mistakes
- **Surface-Level Analysis**: Only checking syntax without understanding business logic
- **Security Blind Spots**: Missing security implications in seemingly innocuous changes
- **Performance Assumptions**: Not considering scalability and performance implications
- **Integration Overlooked**: Failing to consider impact on other system components
- **Testing Gaps**: Not evaluating test coverage and quality adequately

### Communication Problems
- **Unclear Feedback**: Providing vague or non-actionable review comments
- **Defensive Responses**: Taking review feedback personally instead of professionally
- **Knowledge Hoarding**: Not sharing context or reasoning behind review decisions
- **Perfectionism**: Blocking progress with excessive nitpicking on minor issues
- **Inadequate Documentation**: Not documenting decisions or patterns for future reference

### Process Anti-Patterns
- **Review Bottlenecks**: Creating dependencies on single reviewers or experts
- **Rubber Stamping**: Approving changes without thorough analysis
- **Tool Over-Reliance**: Depending entirely on automated tools without human insight
- **Context Switching**: Interrupting deep work for immediate review responses
- **Inadequate Follow-up**: Not tracking completion of review action items 