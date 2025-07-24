# Status Update Command

## Purpose
Generate concise, plain text status updates based on recent git activity including uncommitted work and commits from the previous day. Transform technical git information into digestible progress summaries that follow status update best practices.

## When to Use
- Creating daily standup updates
- Generating weekly status reports
- Summarizing recent development progress
- Documenting work completed for project retrospectives
- Preparing personal progress summaries
- Creating consistent status report format
- Preparing for agile ceremonies and team meetings

## Process

### Phase 0: Analyze Git State and Project Context
**Objective:** Understand current git repository state, uncommitted changes, and recent commit history

**Actions:**
1. Create todos for all status update phases using `todo_write`
2. Use `run_terminal_cmd` to analyze git repository state:
   - Check current git status and uncommitted changes
   - Analyze commits from the previous working day
   - Identify modified files and affected project areas
   - Check current branch and any pending merge/rebase operations
3. Use `codebase_search` to understand project context:
   - "What is the purpose of the recently modified files?"
   - "What components or features are being worked on?"
   - "Are there any related ongoing initiatives?"
4. Use `grep_search` to find patterns in recent changes if needed

**Todo Structure:**
```
- Phase 0: Analyze git state and project context [in_progress]
- Phase 1: Research effective status update formats [pending]
- Phase 2: Generate structured status content [pending]
- Phase 3: Format and deliver status update [pending]
```

**Deliverables:**
- Git activity summary (commits + uncommitted work)
- Affected files and project areas analysis
- Project context understanding

### Phase 1: Research Effective Status Update Formats
**Objective:** Apply status update best practices and determine optimal format for the specific context

**Actions:**
1. Apply research-backed status update best practices:
   - Use the "What I did / What I'm doing / Blockers" format
   - Keep content concise and scannable (under 3 sentences per section)
   - Focus on outcomes and impact, not just activities
   - Include any notable technical decisions or challenges overcome
2. Determine appropriate tone and detail level based on audience:
   - Daily standup: Brief, focused on immediate work
   - Weekly update: Broader scope, include metrics and outcomes
   - Stakeholder report: Business impact and milestone progress
3. Identify visual elements or progress indicators to include
4. Plan for consistent formatting that works across communication platforms

**Deliverables:**
- Status update format selection
- Tone and detail level guidelines
- Visual element planning

### Phase 2: Generate Structured Status Content
**Objective:** Transform git activity analysis into structured, readable status update content

**Actions:**
1. Process commit messages and file changes into meaningful work descriptions:
   - Group related commits by feature or component
   - Extract key functionality changes and improvements
   - Identify bug fixes, new features, and refactoring work
   - Translate technical changes into business-understandable language
2. Structure content into standard status update sections:
   - **Yesterday/Recently Completed**: Major accomplishments and completed tasks
   - **Today/Next**: Planned work and immediate priorities
   - **Blockers/Challenges**: Any impediments or assistance needed
   - **Notes**: Additional context, upcoming time off, or team coordination needs
3. Apply status update best practices:
   - Use action-oriented language ("Implemented", "Fixed", "Deployed")
   - Include impact or outcome when possible
   - Keep technical details appropriate for audience
   - Highlight collaboration or dependencies

**Deliverables:**
- Structured status update content
- Business-friendly descriptions of technical work
- Clear action items and next steps

### Phase 3: Format and Deliver Status Update
**Objective:** Create final status update in plain text format

**Actions:**
1. Format status update as clean plain text:
   - Clear section headers
   - Bullet points for readability
   - Concise, scannable structure
2. Add simple text formatting:
   - Section headers (Yesterday, Today, Blockers)
   - Bullet points for each item
   - Clear organization without special characters
3. Generate final plain text output ready for copy/paste
4. Save formatted status update to local documentation if needed
5. Provide usage instructions and next steps

**Deliverables:**
- Final plain text status update
- Clean, readable formatting
- Documentation and follow-up guidance

## Git Activity Analysis

### Working Day Logic
The command intelligently handles working days to provide relevant activity:

**Monday Analysis:**
- Shows commits from Friday (last working day)
- Includes any weekend commits if present
- Notes any work done outside normal hours

**Tuesday-Friday Analysis:**
- Shows commits from previous day
- Includes any commits from current day if working late

**Custom Date Range:**
- Supports `-d` flag for custom days back (e.g., `-d 3` for last 3 days)
- Useful for weekly updates or returning from time off

### Commit Processing
**Smart Commit Grouping:**
- Groups related commits by file/component
- Identifies feature work vs bug fixes vs refactoring
- Consolidates minor commits (formatting, typos) into single mentions

**Technical Translation:**
- Converts technical file paths to user-friendly component names
- Translates commit messages into business outcomes
- Identifies breaking changes or significant architectural decisions

### Uncommitted Work Analysis
**Staged Changes:**
- Analyzes `git diff --cached` for staged but uncommitted work
- Describes work in progress and completion status

**Working Directory:**
- Reviews `git status` for modified files and new work
- Identifies experimental branches or feature work

## Plain Text Format

### Daily Standup Format
```
Status Update - January 15, 2024

Yesterday:
- Implemented user authentication flow (login/signup components)
- Fixed critical bug in payment processing (issue #234)
- Code review for API documentation

Today:
- Completing unit tests for auth module
- Starting work on user dashboard UI
- Team architecture discussion at 3pm

Blockers:
- Waiting for API key from payments team for testing
- Need staging environment access for integration tests
```

### Weekly Update Format
```
Weekly Status Update - Week of January 15, 2024

Completed This Week:
- User authentication system (MVP ready)
- Payment integration testing and bug fixes
- Code review and documentation updates
- Performance optimization for login flow

In Progress:
- User dashboard development (60% complete)
- Mobile responsive design improvements

Next Week:
- Dashboard completion and testing
- Performance optimization review
- Sprint planning for reporting features

Notes:
- Will be out Friday for team retreat
- Collaborated with Sarah on payment flow design
```

## Tool Integration

### Cursor Tools Used
- **`run_terminal_cmd`**: Git operations for status, log, and diff analysis
- **`codebase_search`**: Project context understanding and component identification
- **`grep_search`**: Pattern matching in code changes and commit messages
- **`edit_file`**: Status update content generation and formatting
- **`todo_write`**: Progress tracking and phase management

### Workflow
Generate comprehensive status update content from git analysis with clean plain text formatting ready for copy/paste into any communication platform.

## Advanced Features

### Custom Timeframes
```bash
# Last 3 days (useful after weekends or time off)
@status-update.md -d 3

# Specific date range
@status-update.md --since "2024-01-15" --until "2024-01-19"

# This week's work (for weekly reports)
@status-update.md --week
```

## Best Practices

### Effective Status Updates
- **Focus on Outcomes**: Describe what was accomplished, not just what was worked on
- **Business Value**: Connect technical work to user or business benefits when possible
- **Be Specific**: "Fixed login bug" vs "Resolved authentication timeout issue affecting 15% of users"
- **Include Context**: Mention collaboration, learning, or notable technical decisions
- **Plan Forward**: Clear next steps help team coordination

### Git Hygiene for Better Updates
- **Meaningful Commit Messages**: Use conventional commits for better automatic processing
- **Atomic Commits**: One logical change per commit makes analysis easier
- **Regular Commits**: Daily commits provide better activity tracking
- **Branch Naming**: Clear branch names help identify feature work

### Communication Guidelines
- **Know Your Audience**: Adjust technical detail level appropriately
- **Be Honest**: Include blockers and challenges, not just successes
- **Stay Concise**: Keep updates focused and scannable
- **Clear Structure**: Use consistent formatting for readability
- **Consistency**: Regular format helps with quick information scanning

## Common Pitfalls to Avoid

### Content Issues
- **Too Technical**: Avoiding jargon and implementation details in team updates
- **Too Vague**: "Worked on stuff" doesn't help team coordination
- **List Every Commit**: Focus on meaningful progress, not every minor change
- **Missing Context**: Include why work was done, not just what was done
- **Ignoring Blockers**: Status updates are for coordination - share challenges

### Format Problems
- **Inconsistent Structure**: Use the same format consistently
- **Too Long**: Keep daily updates under 30 seconds reading time
- **Poor Organization**: Use clear headers and bullet points for scannability
- **No Clear Actions**: Include what help is needed or what's coming next

### Process Mistakes
- **Irregular Updates**: Consistency is key for team coordination
- **Last-Minute Writing**: Status updates written in rush lose quality
- **No Follow-up**: Connect status updates to actual work planning
- **Ignoring Feedback**: Adjust format based on team needs and preferences
- **Over-Engineering**: Start simple and add complexity only if needed

## Integration Examples

### Basic Usage
```bash
# In any git repository
@status-update.md

# Output: Plain text status update ready for copy/paste
```

### Custom Timeframes
```bash
# Last 3 days of work
@status-update.md -d 3

# Weekly summary
@status-update.md --week
```

## Output Examples

### Daily Standup Output
```
Status Update - January 15, 2024

Yesterday:
- Completed OAuth2 integration with Google and GitHub providers
- Fixed critical session timeout bug affecting mobile users (PR #156)
- Code review for payment processing refactor

Today:
- Writing unit tests for authentication module (target: 90% coverage)
- Starting user dashboard wireframe review with design team
- Team architecture discussion at 3pm

Blockers:
- API documentation review needed for dashboard endpoints
- Staging environment access required for payment testing

Notes:
- Great pair programming session with Sarah on error handling
- Will be 30min late tomorrow due to dentist appointment
```

This status update is now ready to copy into any communication channel or document! 