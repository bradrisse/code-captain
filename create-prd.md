# Create PRD Command

## Purpose
Create comprehensive Product Requirements Documents (PRDs) that clearly define product features, user needs, business objectives, and success metrics through a structured discovery and documentation process.

## When to Use
- Defining new product features or major functionality
- Planning significant product changes or enhancements
- Aligning stakeholders on product direction and scope
- Establishing clear requirements before development begins
- Creating shared understanding between product, engineering, and business teams
- Documenting product decisions and rationale for future reference

## Process

### Phase 0: Analyze Current Application State
**Objective:** Understand the existing codebase, documentation, and application state before proceeding

**Actions:**
1. Create todos for all PRD phases using `todo_write`
2. Use `list_dir` to explore the project structure and understand the codebase
3. Use `file_search` and `codebase_search` to find existing documentation:
   - Search for README files, documentation folders, existing PRDs
   - Look for API documentation, user guides, or technical specs
   - Check for package.json, requirements.txt, or similar dependency files
4. Use `codebase_search` to understand the application's purpose and current functionality:
   - "What does this application do?", "Main features and functionality"
   - "User authentication", "Core business logic", "Data models"
   - "API endpoints", "User interface components"
5. Read key files to understand the application architecture and current state
6. Ask the user a series of structured questions to gather PRD requirements (see Question Framework below)

**Todo Structure:**
```
- Phase 0: Analyze current application state and gather requirements [in_progress]
- Phase 1: Define product context and scope [pending]
- Phase 2: Research user needs and market context [pending]
- Phase 3: Define requirements and specifications [pending]
- Phase 4: Document PRD with constraints [pending]
```

**Question Framework:**
After analyzing the current state, ask the user these questions to gather PRD requirements:

**Application Context:**
1. "Based on my analysis, this appears to be [description of current app]. Is this correct, and can you provide more context about what the application currently does?"
2. "What specific new feature or enhancement are you looking to add to this application?"
3. "Is this a completely new feature, an enhancement to existing functionality, or a redesign of current features?"

**Business Context:**
4. "What business problem are you trying to solve with this new feature/enhancement?"
5. "Who are the primary users who will benefit from this change?"
6. "What's driving the need for this feature now? (user feedback, business growth, competitive pressure, etc.)"
7. "How does this feature align with your overall business objectives?"

**Scope and Constraints:**
8. "What's your timeline for this feature? Any hard deadlines?"
9. "What's your budget or resource constraints for this project?"
10. "Are there any technical constraints I should be aware of? (platform limitations, integration requirements, etc.)"
11. "What constitutes success for this feature? How will you measure it?"

**User and Market Context:**
12. "Can you describe your typical users and their current workflow?"
13. "What specific pain points are users experiencing that this feature would address?"
14. "Are there any competitive products or features you'd like to reference or differentiate from?"
15. "Do you have any existing user research or data that informs this feature?"

**Requirements Gathering:**
16. "What are the core functionalities this feature must have? (Must-haves vs Nice-to-haves)"
17. "How should users interact with this feature? Any specific UX requirements?"
18. "Are there any integration requirements with existing systems or third-party services?"
19. "What are your security, privacy, or compliance requirements?"
20. "Are there any accessibility or internationalization requirements?"

**Deliverables:**
- Current application analysis summary
- User responses to requirement questions
- Initial feature scope definition

### Phase 1: Define Product Context and Scope
**Objective:** Establish clear product boundaries, stakeholders, and high-level objectives based on current application analysis and user inputs

**Actions:**
1. Synthesize application analysis and user responses into clear product context
2. Identify primary stakeholders and their roles
3. Define the specific product area or feature being specified within the existing application
4. Establish business context and strategic alignment
5. Set PRD scope and boundaries based on existing architecture and constraints

**Deliverables:**
- Product scope statement incorporating existing application context
- Stakeholder identification
- Success criteria framework
- Integration points with existing application

### Phase 2: Research User Needs and Market Context
**Objective:** Understand the problem space, user needs, and competitive landscape

**Actions:**
1. Use `web_search` to research market context and competitive landscape:
   - "[product area] user needs", "[feature type] best practices"
   - "[product category] market trends", "[competitor] features"
   - "[industry] user research", "[use case] pain points"
2. Research existing solutions and competitive offerings
3. Understand user workflows and pain points
4. Gather quantitative data on market opportunity and user behavior
5. Document technical constraints and platform considerations

**Search Strategy:**
- Market research: "[product category] market size", "[feature] adoption rates"
- User research: "[use case] user journey", "[use case] pain points"
- Competitive analysis: "[competitor] features", "[product type] comparison"
- Technical context: "[platform] capabilities", "[technology] limitations"

**Deliverables:**
- Market and competitive analysis
- User journey and pain point documentation
- Technical constraint identification

### Phase 3: Define Requirements and Specifications
**Objective:** Transform research into specific, actionable product requirements

**Actions:**
1. Define core user stories and acceptance criteria
2. Prioritize features using impact vs effort analysis
3. Specify functional requirements and user interactions
4. Define non-functional requirements (performance, security, accessibility)
5. Create user experience flows and interface considerations
6. Identify dependencies and integration requirements
7. Establish success metrics and measurement criteria

**Requirements Categories:**
- **Functional Requirements:** What the product must do
- **Non-Functional Requirements:** How the product must perform
- **User Experience Requirements:** How users will interact with the product
- **Technical Requirements:** Platform, performance, and integration needs
- **Business Requirements:** Metrics, timeline, and resource constraints

**Deliverables:**
- Prioritized feature list
- Detailed user stories with acceptance criteria
- Success metrics and KPIs
- Technical and business constraints

### Phase 4: Document PRD with Constraints
**Objective:** Create comprehensive PRD documentation that serves as the single source of truth

**Actions:**
1. Synthesize research and requirements into structured PRD document
2. Document assumptions, risks, and mitigation strategies
3. Create implementation timeline and milestone framework
4. Create PRD document in `/docs/prd.md` using the standardized format below
5. Review PRD with stakeholders and incorporate feedback

**Deliverables:**
- Comprehensive PRD document
- **PRD Document:** `/docs/prd.md`

## PRD Document Template

Create a markdown file in `/docs/prd.md`

Use the following structure:

```markdown
# Product Requirements Document

**Product Manager:** [Name]  
**Status:** [Draft/In Review/Approved/Implemented]  

## Executive Summary
[2-3 paragraph overview of the product feature, its purpose, and expected impact]

## Problem Statement

### Background
[Context about why this feature is needed, current pain points, and business drivers]

### User Pain Points
- **Pain Point 1:** [Description and impact]
- **Pain Point 2:** [Description and impact]
- **Pain Point 3:** [Description and impact]

### Opportunity
[Market opportunity, user demand, or business value this feature will address]

## Goals and Success Metrics

### Business Objectives
- **Primary Goal:** [Main business objective with measurable outcome]
- **Secondary Goals:** [Supporting business objectives]

### Success Metrics
- **Primary KPI:** [Key metric with target value and timeline]
- **Secondary KPIs:** [Supporting metrics with targets]
- **Leading Indicators:** [Early signals of success]

### Success Criteria
[Specific, measurable criteria that define feature success]

## Use Cases
1. **Use Case 1:** [Primary usage scenario]
   - **Actor:** [Who performs this action]
   - **Goal:** [What they want to accomplish]
   - **Steps:** [High-level workflow]

2. **Use Case 2:** [Secondary usage scenario]
   - **Actor:** [Who performs this action]
   - **Goal:** [What they want to accomplish]
   - **Steps:** [High-level workflow]

## Requirements

### Functional Requirements

#### Core Features
1. **Feature 1: [Name]**
   - **Description:** [What it does]
   - **User Story:** As a [user], I want [functionality] so that [benefit]
   - **Acceptance Criteria:**
     - [Specific, testable criteria]
     - [Additional criteria]
   - **Priority:** [High/Medium/Low]

2. **Feature 2: [Name]**
   - **Description:** [What it does]
   - **User Story:** As a [user], I want [functionality] so that [benefit]
   - **Acceptance Criteria:**
     - [Specific, testable criteria]
     - [Additional criteria]
   - **Priority:** [High/Medium/Low]

#### Supporting Features
[Less critical features that enhance the core experience]

### Non-Functional Requirements

#### Performance
- **Response Time:** [Target load times]
- **Throughput:** [Expected traffic volume]
- **Scalability:** [Growth expectations]

#### Security
- **Authentication:** [Security requirements]
- **Data Protection:** [Privacy and security measures]
- **Compliance:** [Regulatory requirements]

#### Accessibility
- **Standards:** [WCAG compliance level]
- **Device Support:** [Mobile, tablet, desktop requirements]
- **Browser Support:** [Supported browsers and versions]

#### Usability
- **Learning Curve:** [Ease of use expectations]
- **Error Handling:** [User-friendly error management]
- **Help and Documentation:** [Support requirements]

## User Experience Design

### User Journey
[Step-by-step flow of how users will interact with the feature]

### Key Interactions
- **Interaction 1:** [User action and system response]
- **Interaction 2:** [User action and system response]

### Interface Considerations
- **Layout:** [General interface approach]
- **Navigation:** [How users move through the feature]
- **Feedback:** [How system communicates with users]



## Technical Considerations

### System Integration
- **APIs:** [Required integrations with existing systems]
- **Data Sources:** [Where data comes from and goes to]
- **Dependencies:** [External services or internal components]

### Technical Constraints
- **Platform Limitations:** [Technology or platform restrictions]
- **Performance Requirements:** [Technical performance needs]
- **Security Requirements:** [Technical security implementation]

### Data Requirements
- **Data Models:** [New data structures needed]
- **Data Migration:** [Existing data handling]
- **Analytics:** [Data collection for metrics]

## Implementation Plan

### Dependencies
- **Internal Dependencies:** [Other teams or projects]
- **External Dependencies:** [Third-party services or vendors]
- **Technical Dependencies:** [Infrastructure or platform requirements]



## Risks and Mitigation

### High-Risk Items
- **Risk 1:** [Description] 
  - **Impact:** [What happens if this occurs]
  - **Mitigation:** [How to prevent or address]
- **Risk 2:** [Description]
  - **Impact:** [What happens if this occurs]
  - **Mitigation:** [How to prevent or address]

### Medium-Risk Items
[Less critical but notable risks]

### Assumptions
- **Assumption 1:** [What we're assuming to be true]
- **Assumption 2:** [What we're assuming to be true]


```

## Best Practices

### Requirements Definition
- Use specific, measurable acceptance criteria
- Focus on user outcomes, not just features
- Include both positive and negative test cases
- Consider edge cases and error scenarios
- Prioritize requirements based on user impact and business value

### Stakeholder Alignment
- Involve key stakeholders in requirements definition
- Use consistent terminology throughout the document
- Make assumptions explicit and validate them
- Create shared understanding of success metrics
- Document decisions and their rationale

### User-Centered Approach
- Start with user problems, not solutions
- Use real user research and data when possible
- Think about the complete user journey
- Validate assumptions with user testing



## Common Pitfalls to Avoid

### Requirements Issues
- Writing features instead of problems to solve
- Making requirements too vague or unmeasurable
- Focusing on edge cases before core functionality
- Not considering non-functional requirements
- Assuming technical implementation details

### Stakeholder Management
- Not involving key stakeholders early enough
- Failing to get explicit sign-off on requirements
- Not updating the PRD as requirements evolve
- Creating requirements in isolation from engineering
- Not considering business constraints and timelines

### User Experience
- Not considering the complete user workflow
- Focusing on features instead of user outcomes
- Not planning for onboarding and help
- Ignoring accessibility and inclusion requirements





 