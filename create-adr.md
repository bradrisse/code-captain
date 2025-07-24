# Create ADR Command

## Purpose
Create comprehensive Architecture Decision Records (ADRs) that systematically document architectural decisions with clear rationale, alternatives considered, and consequences through a structured analysis and review process.

## When to Use
- Making significant architectural decisions that affect system structure or design
- Documenting technology choices with vendor lock-in or high switching costs
- Recording decisions contrary to team expectations or industry standards
- Capturing complex trade-offs between competing architectural approaches
- Establishing architectural patterns and standards for team consistency
- Onboarding new team members to architectural reasoning and context
- Creating audit trails for compliance and governance requirements

## Process

### Phase 0: Analyze Decision Context and Current State
**Objective:** Understand the current architectural state and decision context before proceeding

**Actions:**
1. Create todos for all ADR phases using `todo_write`
2. Use `codebase_search` to understand current architectural patterns:
   - "What architectural patterns are currently in use?"
   - "How are similar decisions handled in the codebase?"
   - "What dependencies and integrations exist?"
3. Use `file_search` to find existing ADRs and architectural documentation
4. Use `list_dir` to explore system structure and identify affected components
5. Identify decision stakeholders and their concerns
6. Gather the specific decision that needs to be made and its urgency

**Todo Structure:**
```
- Phase 0: Analyze decision context and current state [in_progress]
- Phase 1: Define decision scope and criteria [pending]
- Phase 2: Research alternatives and evaluate options [pending]
- Phase 3: Document ADR with decision rationale [pending]
```

**Deliverables:**
- Current architectural context summary
- Decision scope and stakeholder identification
- Existing ADR inventory and numbering

### Phase 1: Define Decision Scope and Criteria
**Objective:** Clearly define what decision needs to be made and establish evaluation criteria

**Actions:**
1. Define the specific architectural decision requiring documentation
2. Identify driving forces and constraints:
   - Business requirements and goals
   - Technical constraints and limitations
   - Performance, security, and scalability requirements
   - Team skills and organizational capabilities
   - Timeline and budget constraints
3. Establish decision criteria and priorities
4. Determine decision maker(s) and approval process
5. Set boundaries for the decision scope

**Deliverables:**
- Clear problem statement
- Decision criteria and evaluation framework
- Stakeholder roles and responsibilities
- Decision timeline and process

### Phase 2: Research Alternatives and Evaluate Options
**Objective:** Systematically research and evaluate alternative approaches to the architectural decision

**Actions:**
1. Use `web_search` to research architectural alternatives and best practices:
   - "[technology/pattern] architectural approaches", "[decision area] best practices"
   - "[technology] vs [alternative] comparison", "[pattern] pros and cons"
   - "[industry/domain] architecture patterns", "[scale] architecture examples"
2. Use `codebase_search` to understand current implementation approaches
3. Identify and document alternative options:
   - Current state/status quo option
   - Industry standard approaches
   - Innovative or emerging alternatives
   - Hybrid approaches combining multiple patterns
4. Evaluate each alternative against established criteria:
   - Technical feasibility and complexity
   - Performance and scalability implications
   - Security and compliance considerations
   - Development effort and timeline
   - Long-term maintenance and evolution
   - Risk assessment and mitigation strategies
5. Document pros and cons for each alternative
6. Gather team input and expert opinions

**Search Strategy:**
- Architecture patterns: "[domain] architecture patterns", "[scale] system design"
- Technology comparisons: "[option A] vs [option B]", "[technology] alternatives"
- Best practices: "[decision area] best practices", "[technology] production experience"
- Case studies: "[technology] case study", "[pattern] real world examples"

**Deliverables:**
- Comprehensive alternatives analysis
- Pros and cons evaluation matrix
- Risk assessment for each option
- Expert opinions and team input summary

### Phase 3: Document ADR with Decision Rationale
**Objective:** Create comprehensive ADR documentation with clear decision rationale and consequences

**Actions:**
1. Determine ADR number by checking existing ADRs in `/docs/adr/` directory
2. Synthesize research into clear decision rationale
3. Document decision consequences (both positive and negative)
4. Identify implementation steps and considerations
5. Get current date using `date +%Y-%m-%d` command for ADR metadata
6. Create ADR document in `/docs/adr/` folder using the standardized format below
7. Review ADR with stakeholders and decision makers
8. Update ADR status based on team consensus and approval

**Deliverables:**
- Comprehensive ADR document
- **ADR Document:** `/docs/adr/NNNN-decision-title.md`
- Stakeholder review and approval record

## ADR Document Template

**First, get the current date:**
```bash
date +%Y-%m-%d
```

**Then, determine the next ADR number by checking existing ADRs:**
```bash
ls -la docs/adr/ | grep -E '^[0-9]+' | tail -1
```

Create a markdown file in `/docs/adr/NNNN-decision-title.md` where `NNNN` is the next sequential number (e.g., 0001, 0002, etc.) and `decision-title` is a short kebab-case description.

**Example:** `/docs/adr/0001-use-microservices-architecture.md`

Use the following structure:

```markdown
# NNNN. [Decision Title]

**Date:** [Use output from date +%Y-%m-%d command]  
**Status:** [Proposed/Accepted/Deprecated/Superseded]  
**Deciders:** [Names or roles of decision makers]  
**Technical Story:** [Brief reference to related issue, epic, or requirement]

## Context and Problem Statement

[Describe the architectural problem or decision that needs to be made. Include the business context, technical context, and driving forces that led to this decision being necessary.]

### Driving Forces

- **Business Driver 1:** [e.g., Need to support 10x user growth]
- **Technical Driver 2:** [e.g., Current monolith becoming unmaintainable]
- **Organizational Driver 3:** [e.g., Team scaling requires better separation of concerns]

### Assumptions

- [Any assumptions made during the decision process]
- [External dependencies or constraints assumed to remain stable]

## Decision Drivers

[List the key factors that influenced this architectural decision, in order of importance]

- **Driver 1:** [e.g., Scalability requirements]
- **Driver 2:** [e.g., Team autonomy and development velocity]
- **Driver 3:** [e.g., Technology stack modernization]
- **Driver 4:** [e.g., Operational complexity management]

## Considered Options

### Option 1: [Name of option, e.g., "Maintain Current Monolithic Architecture"]

**Description:** [Brief description of this approach]

**Pros:**
- [Positive aspect 1]
- [Positive aspect 2]

**Cons:**
- [Negative aspect 1]
- [Negative aspect 2]

**Effort:** [Implementation effort assessment]
**Risk:** [Risk level and key risks]

### Option 2: [Name of option, e.g., "Migrate to Microservices Architecture"]

**Description:** [Brief description of this approach]

**Pros:**
- [Positive aspect 1]
- [Positive aspect 2]

**Cons:**
- [Negative aspect 1]
- [Negative aspect 2]

**Effort:** [Implementation effort assessment]
**Risk:** [Risk level and key risks]

### Option 3: [Name of option, e.g., "Hybrid Modular Monolith Approach"]

**Description:** [Brief description of this approach]

**Pros:**
- [Positive aspect 1]
- [Positive aspect 2]

**Cons:**
- [Negative aspect 1]
- [Negative aspect 2]

**Effort:** [Implementation effort assessment]
**Risk:** [Risk level and key risks]

## Decision Outcome

**Chosen Option:** [Selected option with brief rationale]

### Rationale

[Detailed explanation of why this option was selected over the alternatives. Reference the decision drivers and how this option best addresses them.]

### Confirmation

[How will we know this decision is working? What metrics or indicators will we monitor?]

## Consequences

### Positive Consequences

- [Positive outcome 1 - what improvements this decision enables]
- [Positive outcome 2 - what capabilities this decision provides]
- [Positive outcome 3 - what risks this decision mitigates]

### Negative Consequences

- [Negative outcome 1 - what complexities this decision introduces]
- [Negative outcome 2 - what trade-offs this decision requires]
- [Negative outcome 3 - what new risks this decision creates]

### Mitigation Strategies

- [Strategy 1 for addressing negative consequences]
- [Strategy 2 for managing introduced complexities]

## Implementation Notes

### Prerequisites

- [What needs to be in place before implementing this decision]
- [Dependencies that must be resolved first]

### Implementation Steps

1. [Step 1 - immediate actions required]
2. [Step 2 - follow-up activities]
3. [Step 3 - validation and monitoring setup]

### Success Criteria

- [Measurable criteria for successful implementation]
- [Timeline for achieving implementation milestones]

## Follow-up Actions

- [Action item 1 with owner and timeline]
- [Action item 2 with owner and timeline]
- [Review date for evaluating decision effectiveness]

## References

- [Link to related ADRs]
- [External documentation, articles, or research]
- [Code repositories or examples]
- [Meeting notes or discussion records]

## Related Decisions

- [ADR-XXXX: Related decision that influences this one]
- [ADR-YYYY: Decision that this one supersedes or is superseded by]
```

## Best Practices

### Decision Scope and Focus
- Focus on one significant architectural decision per ADR
- Clearly separate the problem from potential solutions
- Include sufficient context for future readers to understand the decision
- Document the decision even if it seems obvious at the time
- Consider both technical and business implications

### Alternatives Analysis
- Always include the "do nothing" or "status quo" option
- Research industry standards and best practices
- Consider both short-term and long-term implications
- Include effort and risk assessments for each option
- Seek diverse perspectives and expert opinions

### Decision Documentation
- Use clear, jargon-free language that new team members can understand
- Include relevant diagrams, code examples, or architectural sketches
- Reference external sources and supporting documentation
- Document both positive and negative consequences honestly
- Plan for decision review and potential revision

### Stakeholder Engagement
- Involve all teams affected by the architectural decision
- Allow time for thoughtful review and feedback
- Document dissenting opinions and how they were addressed
- Ensure decision makers have sufficient context and time
- Follow up on implementation and measure success

### ADR Management
- Maintain sequential numbering for easy reference
- Store ADRs in version control alongside code
- Link related ADRs to show decision evolution
- Update status when decisions are superseded or deprecated
- Regular review of ADR effectiveness and team satisfaction

## Common Pitfalls to Avoid

### Decision Process Issues
- Rushing to document a decision without proper analysis
- Making decisions in isolation without stakeholder input
- Failing to research alternative approaches thoroughly
- Not considering long-term consequences and evolution
- Avoiding difficult trade-off discussions

### Documentation Problems
- Writing ADRs that are too technical for business stakeholders
- Failing to include sufficient context for future understanding
- Not updating ADR status when decisions change
- Creating ADRs for trivial decisions that don't warrant documentation
- Writing overly long ADRs that obscure the key decision

### Team and Process Challenges
- Not establishing clear decision-making authority
- Failing to follow up on implementation and monitoring
- Creating ADRs after decisions are already implemented
- Not linking ADRs to related architectural documentation
- Ignoring dissenting opinions without proper consideration

### Maintenance and Evolution
- Letting ADRs become stale or outdated
- Not reviewing and learning from past decisions
- Failing to update related ADRs when superseding decisions
- Not considering the cumulative effect of multiple ADRs
- Avoiding difficult conversations about failed decisions 