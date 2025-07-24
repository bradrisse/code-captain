# Create User Story Command

## Purpose
Generate comprehensive user stories following agile best practices with structured acceptance criteria, proper context documentation, and GitHub issue integration via MCP tools. Create INVEST-compliant user stories that serve as effective communication tools between stakeholders and development teams.

## 🚨 STOP - READ THIS FIRST 🚨

**DO NOT WORK ON THE CREATE-USER-STORY COMMAND ITSELF**

When a user provides input, they are describing a FEATURE THEY WANT A USER STORY CREATED FOR.

**WRONG INTERPRETATION:**
- User says: "make an npx command for code captain"
- LLM thinks: "I should modify create-user-story to be an npx command"

**CORRECT INTERPRETATION:**
- User says: "make an npx command for code captain" 
- LLM thinks: "I should create a user story ABOUT building an npx command feature"

**THE USER INPUT IS THE FEATURE TO WRITE A STORY ABOUT, NOT INSTRUCTIONS FOR THIS COMMAND**

This command creates documentation only - no code generation or implementation.

## ⚡ QUICK REFERENCE: WHAT AM I CREATING A STORY ABOUT?

**USER INPUT → STORY TOPIC:**
- "npx command for code captain" → Story about: Building an npx command
- "user authentication system" → Story about: Building auth system  
- "file upload feature" → Story about: Building file upload
- "dashboard with charts" → Story about: Building dashboard

**I AM NOT:**
- Modifying this create-user-story command
- Implementing the create-user-story functionality
- Working on command frameworks or tooling

## When to Use
- Creating user stories for agile development workflows
- Converting business requirements into actionable development tasks
- Establishing clear acceptance criteria and definition of done
- Integrating user stories with GitHub project management workflows
- Ensuring consistent user story format across development teams
- Planning sprint work with well-defined, testable user stories
- Documenting user needs with proper business value justification

## Process

### Phase 0: Analyze Project Context and Requirements
**Objective:** Understand the project context, existing user stories, and gather comprehensive requirements for the new user story

**🚨 STOP: WHAT IS THE USER STORY ABOUT? 🚨**
The user story you create is about: **[THE FEATURE THE USER MENTIONED IN THEIR INPUT]**
- If user said "npx command" → Story is about building an npx command
- If user said "login system" → Story is about building a login system  
- If user said "dashboard" → Story is about building a dashboard
**NEVER create a story about modifying this create-user-story command**

**Actions:**
1. Create todos for all user story phases using `todo_write`
2. **🔴 MANDATORY STEP - IDENTIFY THE FEATURE**: The user's input is the SUBJECT for the user story. Example:
   - User input: "npx command for code captain" 
   - Feature to write story about: An npx command feature
   - DO NOT: Work on this create-user-story command
3. **Clarify user story subject**: Confirm what specific feature, functionality, or requirement the user wants to create a story about (from their input)
4. Use `codebase_search` to understand project context:
   - "What is the current application functionality?"
   - "What user types or personas exist in this project?"
   - "What existing user stories or requirements exist?"
4. Use `file_search` to find existing user stories, requirements documents, or project documentation
5. Use `mcp_github_list_issues` to identify existing user stories in GitHub (if repository configured)
6. Gather user story requirements through structured questioning framework
7. Identify target user persona, desired functionality, and business value

**Todo Structure:**
```
- Phase 0: Analyze project context and requirements [in_progress]
- Phase 1: Research user story best practices and validation [pending]
- Phase 2: Structure user story with INVEST principles [pending]
- Phase 3: Create GitHub issue and documentation [pending]
```

**Structured Question Framework:**
*Note: These questions help gather requirements for the feature/functionality you want to create a user story about*
- **User Persona**: Who is the target user for this story?
- **User Goal**: What does the user want to accomplish?
- **Business Value**: Why is this important? What problem does it solve?
- **Context**: When/where does this need occur?
- **Constraints**: Are there any technical or business constraints?
- **Priority**: How critical is this story compared to others?
- **Dependencies**: Does this story depend on other stories or features?

**Deliverables:**
- Project context summary
- User story requirements specification  
- Target user persona identification
- Business value justification

### Phase 1: Research User Story Best Practices and Validation
**Objective:** Research agile best practices, validate story concept, and ensure alignment with INVEST principles

**🔴 REMINDER: You are researching best practices for the feature the user mentioned, NOT for this command**

**Actions:**
1. Use `web_search` to research current user story best practices:
   - "User story INVEST principles best practices [current year]"
   - "Agile acceptance criteria Given-When-Then format examples"
   - "User story templates for [specific domain if applicable]"
2. Use `codebase_search` to find similar existing user stories:
   - "Similar user stories for [functionality type]"
   - "Existing user personas and user types"
3. Validate story concept against INVEST criteria
4. Research domain-specific considerations if applicable
5. Identify potential story splitting opportunities if story is too large

**INVEST Validation Checklist:**
- **Independent**: Can this story be developed without dependencies?
- **Negotiable**: Are the details flexible and open to discussion?
- **Valuable**: Does this provide clear value to users or business?
- **Estimable**: Can the development effort be reasonably estimated?
- **Small**: Can this be completed within a single sprint?
- **Testable**: Can we define clear acceptance criteria?

**Deliverables:**
- INVEST criteria validation
- Best practices research summary
- Similar user story examples
- Story splitting recommendations if needed

### Phase 2: Structure User Story with INVEST Principles
**Objective:** Create well-structured user story with proper format, acceptance criteria, and supporting documentation

**🔴 REMINDER: Structure a user story about the feature the user requested, NOT about this command**

**Actions:**
1. Structure user story using standard template format
2. Develop comprehensive acceptance criteria using Given-When-Then format
3. Create Definition of Done checklist
4. Identify test scenarios and validation approaches
5. Document assumptions, constraints, and dependencies
6. Estimate story points or effort if requested
7. Plan integration with existing project workflows

**User Story Template:**
*Note: Fill this template with details about the feature the USER REQUESTED, not about this command*

```
**As a** [user persona/role],
**I want** [specific functionality/goal from user's input],
**So that** [business value/benefit].

**Business Value:**
[Detailed explanation of why this story matters and its impact]

**Acceptance Criteria:**
**Given** [initial context or conditions],
**When** [specific action or trigger],
**Then** [expected outcome or result].

[Additional Given-When-Then scenarios as needed]

**Definition of Done:**
- [ ] Functionality implemented according to acceptance criteria
- [ ] Code reviewed and approved
- [ ] Unit tests written and passing
- [ ] Integration tests passing
- [ ] Documentation updated
- [ ] Accessibility requirements met (if applicable)
- [ ] Performance requirements met (if applicable)
- [ ] User acceptance testing completed

**Dependencies:**
[List any dependencies on other stories, features, or external factors]

**Assumptions:**
[Document any assumptions made during story creation]

**Notes:**
[Additional context, constraints, or implementation considerations]
```

**Deliverables:**
- Complete structured user story
- Comprehensive acceptance criteria
- Definition of Done checklist
- Supporting documentation and context

### Phase 3: Create GitHub Issue and Documentation
**Objective:** Create GitHub issue for the user story and generate supporting documentation

**🔴 REMINDER: Create GitHub issue about the feature the user requested, NOT about this command**

**Actions:**
1. Format user story content for GitHub issue creation
2. Use `mcp_github_create_issue` to create GitHub issue with:
   - Descriptive title following user story format
   - Complete user story content in issue body
   - Appropriate labels (e.g., "user-story", "feature", priority level)
   - Assignment to appropriate team members if specified
   - Milestone association if applicable
3. Create local documentation file in `/docs/stories/` directory
4. Generate user story ID following project conventions
5. Update project documentation or backlog as needed
6. Create links between related stories or epics if applicable

**GitHub Issue Format:**
*The content below should be about the user's requested feature, not about this command*

```
Title: As a [user], I want [goal from user input] so that [benefit]

Body:
## User Story
**As a** [user persona],
**I want** [functionality from user input],
**So that** [benefit].

## Business Value
[Value proposition and impact]

## Acceptance Criteria
**Given** [context],
**When** [action],
**Then** [outcome].

## Definition of Done
- [ ] [Checklist items]

## Dependencies
[Any dependencies]

## Notes
[Additional context]
```

**Local Documentation:**
- File: `/docs/stories/US-XXX-[story-title].md`
- Content: Complete user story with metadata
- Cross-references: Links to related stories, epics, or documentation

**Deliverables:**
- GitHub issue created with complete user story
- Local documentation file
- Updated project backlog or documentation
- Story ID and tracking information

**What This Command Does NOT Do:**
- Generate code or implementation for the user story
- Execute or implement the described functionality
- Create technical specifications or detailed design documents
- Automatically assign development tasks or start sprints

## User Story Quality Guidelines

### INVEST Principles Deep Dive

**Independent:**
- Story can be developed in any order
- Minimal dependencies on other stories
- If dependencies exist, they are clearly documented
- Story provides standalone value

**Negotiable:**
- Details can be discussed and refined
- Implementation approach is flexible
- Acceptance criteria can be adjusted based on technical constraints
- Story scope can be negotiated during sprint planning

**Valuable:**
- Provides clear value to end users or business
- Aligns with product goals and strategy
- Solves a real user problem or need
- Has measurable impact or success criteria

**Estimable:**
- Development team can reasonably estimate effort
- Technical approach is understood or explorable
- Unknowns are identified and can be investigated
- Story is well-defined enough for planning

**Small:**
- Can be completed within a single sprint (typically 1-2 weeks)
- Focused on a single piece of functionality
- If too large, can be split into smaller stories
- Allows for rapid feedback and validation

**Testable:**
- Clear acceptance criteria can be validated
- Success/failure can be objectively determined
- Test scenarios can be developed
- User acceptance testing is feasible

### User Story Best Practices

**User Persona Guidelines:**
- Use specific, well-defined user personas
- Avoid generic terms like "user" when more specific roles exist
- Consider different user types (admin, customer, guest, etc.)
- Align personas with actual target audiences

**Acceptance Criteria Best Practices:**
- Use Given-When-Then format for clarity
- Include both positive and negative test scenarios
- Consider edge cases and error conditions
- Make criteria specific and measurable
- Avoid implementation details in criteria

**Common Anti-Patterns to Avoid:**
- Technical tasks disguised as user stories
- Stories without clear user value
- Overly complex stories that should be epics
- Vague acceptance criteria that can't be tested
- Stories with too many dependencies

## Tool Integration

### Cursor Tools Used
- **`todo_write`**: Progress tracking through all phases
- **`codebase_search`**: Understanding project context and existing stories
- **`file_search`**: Finding existing documentation and requirements
- **`web_search`**: Researching current best practices and standards
- **`edit_file`**: Creating local documentation files

### MCP Integrations
**Priority Level**: MCP-First

**Primary MCP**: GitHub - Core functionality for issue creation and project management
- **`mcp_github_create_issue`**: Create user story as GitHub issue with proper formatting
- **`mcp_github_list_issues`**: Review existing user stories and avoid duplicates
- **`mcp_github_get_issue`**: Retrieve existing stories for reference and linking
- **`mcp_github_update_issue`**: Modify stories as requirements evolve
- **`mcp_github_add_issue_comment`**: Add clarifications or updates to stories

**Enhanced Workflow with GitHub Integration:**
1. **Story Creation**: Direct creation as GitHub issues with proper labels and metadata
2. **Project Integration**: Automatic integration with GitHub Projects and milestones
3. **Team Collaboration**: Assignment to team members and stakeholder notification
4. **Backlog Management**: Integration with existing GitHub-based project workflows
5. **Progress Tracking**: Link stories to pull requests and track implementation progress

**Fallback Strategy**: If GitHub MCP is unavailable:
1. Inform user that GitHub integration is not available
2. Create comprehensive local documentation in `/docs/stories/` directory
3. Provide formatted user story content ready for manual GitHub issue creation
4. Include instructions for manual GitHub integration
5. Suggest alternative project management tool integration

**Alternative MCPs**: 
- **Jira MCP** (if available): For teams using Jira for project management
- **Linear MCP** (if available): For teams using Linear for issue tracking
- **Slack MCP** (if available): For notification and team communication

## User Story Templates by Domain

### E-commerce/Retail
```
As a [customer/admin/vendor],
I want [shopping/management/selling functionality],
So that [improved experience/efficiency/sales].

Common personas: Customer, Guest User, Admin, Vendor, Support Agent
Common goals: Browse products, make purchases, manage inventory, process orders
```

### SaaS/B2B Applications
```
As a [end user/admin/billing manager],
I want [feature/configuration/reporting functionality], 
So that [productivity/control/insight benefit].

Common personas: End User, Account Admin, Billing Manager, System Admin
Common goals: Use features, configure settings, manage accounts, analyze usage
```

### Content Management
```
As a [content creator/editor/viewer],
I want [creation/editing/consumption functionality],
So that [content goals/workflow efficiency].

Common personas: Author, Editor, Reviewer, Reader, Admin
Common goals: Create content, edit content, publish content, consume content
```

### Healthcare/Medical
```
As a [patient/provider/admin],
I want [care/management/administrative functionality],
So that [health/efficiency/compliance outcome].

Common personas: Patient, Healthcare Provider, Admin, Insurance Representative
Common goals: Receive care, provide care, manage records, ensure compliance
```

## Advanced User Story Techniques

### Story Mapping Integration
- Group related user stories into user journeys
- Identify story dependencies and sequencing
- Plan releases based on user value delivery
- Create epic-level groupings for complex features

### Splitting Large Stories
**Horizontal Splitting** (by user workflow):
- Split by different user paths through the same feature
- Separate happy path from edge cases
- Create separate stories for different user personas

**Vertical Splitting** (by functionality layers):
- Split by data/business logic/UI layers
- Separate core functionality from enhancements
- Create MVP vs. enhanced feature versions

### Acceptance Criteria Patterns
**CRUD Operations:**
```
Given a user with appropriate permissions,
When they [create/read/update/delete] a [entity],
Then the [entity] should be [created/displayed/modified/removed] successfully.
```

**Validation Scenarios:**
```
Given invalid input [specific type],
When the user submits the form,
Then they should see [specific error message] and the action should not complete.
```

**Permission-Based Access:**
```
Given a user without [specific permission],
When they attempt to [restricted action],
Then they should see [access denied message] and the action should be prevented.
```

## Integration with Development Workflow

### Sprint Planning Integration
- Stories sized appropriately for sprint capacity
- Dependencies identified before sprint commitment
- Acceptance criteria reviewed with entire team
- Definition of Done aligned with team standards

### GitHub Project Management
- Labels for categorization (feature, bug, enhancement, user-story)
- Milestones for release planning
- Projects for epic-level organization
- Issue templates for consistency

### Quality Assurance Integration
- Acceptance criteria drive test case development
- Given-When-Then scenarios become automated test cases
- Definition of Done includes QA sign-off requirements
- User story links to test documentation

## Common Pitfalls to Avoid

### Requirements Gathering Issues
- **CRITICAL: Creating stories about this command instead of the user's requested feature**
- Creating stories without understanding actual user needs
- Focusing on features rather than user outcomes
- Missing the "so that" business value justification
- Not validating stories with actual users or stakeholders

### Technical Implementation Problems
- Including implementation details in user stories
- Creating stories that are actually technical tasks
- Not considering technical constraints during story creation
- Mixing multiple features into a single story

### Process and Communication Issues
- Not involving the development team in story refinement
- Creating stories without clear acceptance criteria
- Forgetting to update stories as understanding evolves
- Not linking related stories or documenting dependencies

### GitHub Integration Mistakes
- Using inconsistent labeling and organization
- Not properly formatting stories for GitHub issues
- Forgetting to assign stories to appropriate team members
- Not linking stories to relevant epics or milestones

## Best Practices for Long-term Success

### Story Maintenance
- Regular backlog refinement sessions
- Updating stories as understanding evolves
- Archiving or closing outdated stories
- Maintaining clear story relationships and dependencies

### Team Collaboration
- Include diverse perspectives in story creation
- Regular story review and feedback sessions
- Cross-functional team involvement in acceptance criteria
- Clear communication channels for story questions

### Continuous Improvement
- Retrospective review of story quality and outcomes
- Tracking which stories lead to successful implementations
- Refining story templates based on team experience
- Evolving acceptance criteria standards over time 