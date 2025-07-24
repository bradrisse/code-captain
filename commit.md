# Commit Command

## Purpose
Generate conventional commit messages by analyzing staged changes and automatically determining appropriate commit types, scopes, and descriptions following the Conventional Commits specification.

## When to Use
- Creating consistent, meaningful commit messages across team members
- Ensuring commits follow Conventional Commits specification for automated tooling
- Analyzing staged changes to determine appropriate commit type and scope
- Generating semantic commit messages that support automated changelog generation
- Maintaining commit history quality for better project navigation and understanding
- Supporting semantic versioning through structured commit messages

## Process

### Phase 0: Analyze Staged Changes and Repository Context
**Objective:** Understand the current repository state, staged changes, and codebase context

**Actions:**
1. Create todos for all commit phases using `todo_write`
2. Use `run_terminal_cmd` to analyze git repository state:
   - Check git status and staged changes
   - Analyze file modifications, additions, and deletions
   - Identify affected directories and file types
3. Use `codebase_search` to understand affected code areas:
   - "What is the purpose of the modified files?"
   - "What components or modules are affected?"
   - "Are there any breaking changes in the modifications?"
4. Use `file_search` to find related configuration files and documentation
5. Determine if this is a feature, fix, documentation, or other type of change

**Todo Structure:**
```
- Phase 0: Analyze staged changes and repository context [in_progress]
- Phase 1: Determine commit type and scope [pending]
- Phase 2: Generate commit message components [pending]
- Phase 3: Create conventional commit message [pending]
```

**Deliverables:**
- Staged changes analysis
- Affected file and directory summary
- Codebase context understanding

### Phase 1: Determine Commit Type and Scope
**Objective:** Classify the changes according to Conventional Commits types and identify appropriate scope

**Actions:**
1. Analyze file changes to determine primary commit type:
   - **feat**: New features, functionality additions
   - **fix**: Bug fixes, error corrections
   - **docs**: Documentation-only changes
   - **style**: Code style, formatting (no functional changes)
   - **refactor**: Code restructuring without changing external behavior
   - **perf**: Performance improvements
   - **test**: Test additions or modifications
   - **build**: Build system, dependencies, tooling
   - **ci**: Continuous integration configuration
   - **chore**: Maintenance tasks, routine updates
2. Identify appropriate scope based on affected areas:
   - Component names (e.g., parser, api, auth)
   - Module or package names
   - Functional areas (e.g., database, ui, config)
3. Detect potential breaking changes:
   - API signature changes
   - Configuration format changes
   - Behavior modifications that could affect consumers
4. Prioritize commit type if multiple types are present

**Deliverables:**
- Primary commit type determination
- Scope identification
- Breaking change detection
- Secondary change types for body content

### Phase 2: Generate Commit Message Components
**Objective:** Create meaningful commit message title, body, and footers based on analysis

**Actions:**
1. Generate concise, descriptive commit title:
   - Use imperative mood (e.g., "add", "fix", "update")
   - Focus on the primary change or benefit
   - Keep under 50 characters when possible
   - Be specific about what changed
2. Create detailed commit body (if needed):
   - Explain the motivation for the change
   - Describe what was changed at a high level
   - Reference any related issues or tickets
   - Include context that would help future developers
3. Add appropriate footers:
   - Breaking changes: `BREAKING CHANGE: description`
   - Issue references: `Fixes: #123` or `Refs: #456`
   - Co-authors: `Co-authored-by: Name <email>`
   - Other relevant metadata

**Deliverables:**
- Commit title with type and scope
- Detailed commit body (if applicable)
- Appropriate footers and metadata

### Phase 3: Create Conventional Commit Message
**Objective:** Assemble and present the complete conventional commit message for review and execution

**Actions:**
1. Assemble final commit message following Conventional Commits format:
   - `<type>[optional scope]: <description>`
   - Optional body paragraphs
   - Optional footers
2. Validate commit message against Conventional Commits specification
3. Present commit message for review and approval
4. Optionally execute the commit using `run_terminal_cmd`
5. Update any related documentation or changelogs if needed

**Deliverables:**
- Complete conventional commit message
- Commit execution (if approved)
- Updated project documentation

## Commit Type Detection Rules

### Automatic Type Detection
Based on file analysis and change patterns:

**feat (Feature)**
- New files in source directories
- New public methods or classes
- New configuration options
- New user-facing functionality

**fix (Bug Fix)**
- Changes to existing functionality
- Error handling improvements
- Bug-related modifications
- Patches to existing features

**docs (Documentation)**
- README, CHANGELOG, or documentation files
- Code comments additions/updates
- Documentation-only repositories
- API documentation changes

**style (Code Style)**
- Formatting changes (indentation, whitespace)
- Code style fixes (linting, prettier)
- No functional changes detected

**refactor (Code Refactoring)**
- Code restructuring without behavior change
- Variable/function renaming
- Code organization improvements
- Performance optimizations without API changes

**test (Testing)**
- Test file additions/modifications
- Test configuration changes
- Testing utility updates

**build (Build System)**
- Package.json, requirements.txt, build files
- Dependency updates
- Build configuration changes
- CI/CD pipeline modifications

**ci (Continuous Integration)**
- GitHub Actions, Travis CI, etc.
- Deployment configuration
- CI/CD workflow changes

**chore (Maintenance)**
- Routine maintenance tasks
- Tool configuration updates
- Version bumps
- Miscellaneous updates

### Breaking Change Detection
Automatically detect potential breaking changes:

- **API Changes**: Public method signature modifications
- **Configuration**: Required config format changes
- **Dependencies**: Major version dependency updates
- **Behavior**: Functional behavior modifications
- **Environment**: Runtime requirement changes

## Commit Message Template

Based on the [Conventional Commits v1.0.0 specification](https://www.conventionalcommits.org/en/v1.0.0/):

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Example Outputs

**Feature Addition:**
```
feat(auth): add OAuth2 integration with Google provider

Implement OAuth2 authentication flow using Google Identity Platform.
Includes user profile synchronization and token refresh handling.

Fixes: #234
```

**Bug Fix:**
```
fix(parser): handle edge case with empty input arrays

Previously, empty arrays would cause a null pointer exception.
Added input validation and appropriate error handling.

Fixes: #456
```

**Breaking Change:**
```
feat(api)!: restructure user authentication endpoints

BREAKING CHANGE: Auth endpoints moved from /auth/* to /api/v2/auth/*.
Update your API calls to use the new endpoint structure.
```

**Documentation Update:**
```
docs: update API documentation with authentication examples

Add comprehensive examples for OAuth2 and API key authentication.
Include common error scenarios and troubleshooting guide.
```

**Refactoring:**
```
refactor(database): extract query builder into separate module

Improve code organization and testability by separating
query construction logic from database connection handling.
```

## Best Practices

### Commit Message Quality
- Use imperative mood in the description ("add", not "added" or "adds")
- Keep the description under 50 characters when possible
- Use present tense for the action being performed
- Be specific about what changed, not just where
- Focus on the "what" and "why", not the "how"

### Type Selection
- Choose the most significant type if multiple apply
- Use `feat` for any new user-facing functionality
- Use `fix` for any correction to existing functionality
- Prefer specific types (docs, test, style) over generic (chore)
- Use scope to provide additional context

### Breaking Changes
- Always document breaking changes in the footer
- Use `!` after type/scope for breaking changes
- Provide migration guidance in breaking change descriptions
- Consider the impact on consumers and dependent projects

### Scope Guidelines
- Use consistent scope naming across the project
- Prefer component or module names as scopes
- Keep scopes short and meaningful
- Use kebab-case for multi-word scopes
- Consider the project's architecture when defining scopes

### Body and Footer Usage
- Use body for complex changes requiring explanation
- Include motivation, impact, and implementation details
- Reference related issues, pull requests, or tickets
- Add co-author information when collaborating
- Include any relevant metadata or context

## Integration Examples

### Basic Commit Flow
```bash
# Stage your changes
git add .

# Use the commit command to analyze and generate commit message
@commit.md

# Review the generated commit message
# Execute the commit if approved
```

### With Additional Context
```bash
# For complex changes, provide additional context
@commit.md
# Command will analyze:
# - Staged file changes
# - Affected code areas
# - Breaking change potential
# - Related documentation needs
```

## Tool Integration

### Cursor Integration
- Uses `run_terminal_cmd` for git operations
- Uses `codebase_search` for context understanding
- Uses `file_search` for related file discovery
- Uses `todo_write` for progress tracking
- Integrates with Cursor's @ symbol file reference system

### Git Hooks Integration
- Can be integrated with pre-commit hooks
- Supports commit-msg hooks for validation
- Compatible with conventional commit linters
- Works with automated changelog generation tools

### CI/CD Integration
- Supports semantic release automation
- Enables automated version bumping
- Compatible with conventional changelog tools
- Facilitates release note generation

## Common Pitfalls to Avoid

### Message Quality Issues
- Writing vague descriptions like "fix stuff" or "update code"
- Using past tense instead of imperative mood
- Including implementation details in the description
- Making descriptions too long or too technical
- Forgetting to specify scope for multi-component changes

### Type Selection Errors
- Using `feat` for internal refactoring without user impact
- Using `fix` for new functionality additions
- Choosing `chore` for changes that affect functionality
- Misclassifying breaking changes as non-breaking
- Using inconsistent type naming across commits

### Scope and Context Problems
- Using inconsistent scope naming conventions
- Making scopes too broad or too narrow
- Forgetting to update scope names when refactoring
- Not providing enough context for complex changes
- Ignoring the impact on dependent projects

### Process and Workflow Issues
- Committing too many unrelated changes together
- Not reviewing generated commit messages before executing
- Skipping commit message generation for "small" changes
- Not updating related documentation with significant changes
- Forgetting to reference related issues or tickets 