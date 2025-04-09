# Session 03 - Evolving Your AI Workflow

In this session, we'll explore how to continuously improve your AI collaboration process. You'll learn to create specialized prompts for different scenarios and implement a feedback loop that ensures your workflow grows more effective over time.

## Creating Specialized Prompt Templates

As your project matures, different scenarios will require specialized handling. Creating dedicated prompt templates allows you to quickly activate specific AI behaviors without lengthy explanations each time.

### Key Benefits of Specialized Prompts
- **Consistency** across multiple sessions and team members
- **Efficiency** by reducing repetitive instructions
- **Precision** in guiding the AI toward specific outcomes
- **Documentation** of your team's best practices

## Example Specialized Prompts

### `@new-feature.md`

```markdown
# New Feature Addition

When I describe a new feature, please:

1. Create a new user story in the `.project/user_stories/` directory with the next available ID
2. Break it down into specific implementation tasks (at least 3-5 tasks)
3. Update the USER-STORIES.MD and TASKS.MD index files
4. Identify any existing user stories or tasks that might be affected
5. Estimate complexity (Low/Medium/High) for each task
6. Suggest an implementation order for the tasks

Use the same templates as defined in the initialization prompt, with the following additions to the user story template:

## Complexity
[Low/Medium/High]

## Estimated Effort
[X] hours

## Dependencies
- [List any features or components this depends on]
```

### `@refactor.md`

```markdown
# Code Refactoring

When I ask for a refactoring, please:

1. Create a new task under an appropriate user story (create a maintenance user story if needed)
2. Clearly describe the current code issues including:
   - Design problems
   - Performance bottlenecks
   - Maintainability concerns
   - Technical debt
3. Outline steps for refactoring with:
   - Before/after architecture diagrams (text-based)
   - Specific patterns to apply
   - Potential risks and mitigations
4. List files that will be affected
5. Define acceptance criteria to ensure functionality is preserved
6. Suggest relevant test cases to verify the refactoring

## Refactoring Task Template

# Task: [Task-ID]

## Title
Refactor: [Brief descriptive title]

## Related User Story
[US-ID]

## Current Issues
[Detailed description of problems in the current implementation]

## Refactoring Approach
[Architectural approach and patterns to apply]

## Risk Assessment
- Risk: [Potential risk]
  - Mitigation: [How to address this risk]

## Steps
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Acceptance Criteria
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion 3]

## Files to Modify
- [Filepath 1]
- [Filepath 2]

## Testing Approach
[Specific tests to verify the refactoring]
```

### `@bug-fix.md`

```markdown
# Bug Fix Process

When I report a bug, please:

1. Create a new task with prefix "Fix:" in the appropriate user story
2. Document the bug with:
   - Observed behavior
   - Expected behavior
   - Reproduction steps
   - Potential root causes
3. Outline investigation steps
4. Suggest potential solutions
5. Define verification criteria

## Bug Fix Task Template

# Task: [Task-ID]

## Title
Fix: [Brief description of the bug]

## Related User Story
[US-ID]

## Bug Description
- Observed: [What is happening]
- Expected: [What should happen]
- Severity: [Low/Medium/High/Critical]

## Reproduction Steps
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Potential Causes
- [Possible cause 1]
- [Possible cause 2]

## Investigation Approach
1. [Investigation step 1]
2. [Investigation step 2]

## Potential Solutions
- [Solution approach 1]
- [Solution approach 2]

## Verification Steps
- [ ] [Verification step 1]
- [ ] [Verification step 2]

## Files Likely Affected
- [Filepath 1]
- [Filepath 2]
```

### `@code-review.md`

```markdown
# Code Review Request

When I ask you to review code, please:

1. Create a new task for addressing review findings
2. Analyze the code for:
   - Functional correctness
   - Performance issues
   - Security concerns
   - Style and best practices
   - Maintainability
   - Test coverage
3. Categorize findings by severity (Critical, Major, Minor, Suggestion)
4. Provide specific improvement recommendations
5. Include code examples for significant changes

## Code Review Response Structure

# Code Review: [Feature/Component Name]

## Summary
[Overall assessment and key findings]

## Critical Issues
- [Issue description]
  - Location: [File:line]
  - Recommendation: [How to fix]
  - Example: ```[language]
    [code example]
    ```

## Major Issues
[...similar structure...]

## Minor Issues
[...similar structure...]

## Improvement Suggestions
[...similar structure...]

## Follow-up Task
[Propose a task for addressing the findings]
```

## The Improvement Process: Meta-Prompting

The most critical element of this workshop is establishing an **improvement feedback loop** with AI. This process is what we call "meta-prompting" - having the AI improve its own prompts.

### The Meta-Prompting Cycle

1. **Observe** - Notice limitations in the AI's current responses
2. **Request** - Ask the AI to improve its approach
3. **Capture** - Have the AI document the improvement
4. **Institutionalize** - Update your prompt templates

This creates a continuous improvement cycle that evolves with your project and the AI's capabilities.

### Example Improvement Dialogue

**User:**
```
I notice the task descriptions are too minimalistic. They don't include enough detail about the implementation approach. Could you improve how tasks are structured?
```

**AI Response:**
```
You're right, the current task structure is quite basic. I can enhance it with more implementation details. Here's an improved task template:

# Task: [Task-ID]

## Title
[Brief descriptive title]

## Related User Story
[US-ID]

## Description
[Detailed description of what needs to be implemented]

## Technical Approach
[Specific technical details about how to implement this task, including:
- Design patterns to use
- Algorithms to employ
- Data structures needed
- Performance considerations]

## Implementation Steps
1. [Detailed step 1]
2. [Detailed step 2]
3. [Detailed step 3]

## Acceptance Criteria
- [ ] [Specific criterion 1]
- [ ] [Specific criterion 2]
- [ ] [Specific criterion 3]

## Files to Modify
- [Filepath 1]: [Purpose of modification]
- [Filepath 2]: [Purpose of modification]

## Testing Approach
- Unit tests: [Specific test cases]
- Integration tests: [Specific scenarios]
- Edge cases to verify: [List of edge cases]

## Dependencies
- [Any other tasks that must be completed first]

## Estimated Effort
[X] hours
```

**User:**
```
That's much better! Please update the @init.md file to include this improved task template.
```

**AI:**
```
I'll update the @init.md file to include the improved task template. Here's the updated section:

[AI provides the updated template to be added to @init.md]
```

### The Power of Incremental Improvement

Each time you go through this cycle, your AI collaboration becomes more effective. This applies to:

- Templates structure and level of detail
- AI coding practices
- Project organization approaches
- Documentation standards
- Testing strategies

## Advanced Meta-Prompting: Creating System Prompts

You can take meta-prompting to the next level by having the AI create specialized system prompts that define how it should behave throughout a project.

### Example: `@project-behavior.md`

```markdown
# Project Behavior Settings

Throughout this project, please apply these guidelines to all our interactions:

## Code Style
- Follow .NET coding conventions
- Use camelCase for local variables and parameters
- Use PascalCase for type names and method names
- Use XML documentation comments for public APIs

## Architecture Preferences
- Favor composition over inheritance
- Use dependency injection for service dependencies
- Implement interfaces for testability
- Follow SOLID principles

## Documentation Standards
- Include purpose and usage examples in all documentation
- Document any non-obvious design decisions
- Keep documentation up-to-date with code changes

## Error Handling
- Use specific exception types
- Include context information in exception messages
- Log appropriate information for troubleshooting

Please apply these guidelines automatically in all suggestions and implementations.
```

## Workshop Exercise: Evolving Your Process

Let's put these concepts into practice:

### Exercise 1: Create Specialized Prompts
1. Create at least two specialized prompts for your project:
   - `@new-feature.md`
   - Either `@refactor.md`, `@bug-fix.md`, or a custom prompt

2. Test each prompt with a simple request:
   - "I need a feature to export ASCII art as PNG files"
   - "We should refactor the font loading logic to support more formats"

### Exercise 2: Implement the Improvement Process
1. Identify an aspect of your current workflow that could be improved
2. Ask the AI to enhance that aspect
3. Have the AI update your `@init.md` with the improvement
4. Test the improved process on a new feature or task

### Exercise 3: Create a Project Behavior Prompt
1. Create a `@project-behavior.md` file with guidelines specific to your project
2. Test whether the AI follows these guidelines in subsequent interactions
3. Refine the guidelines based on the results

## Key Takeaways

- **Evolve, don't settle** - Your process should continuously improve
- **Documentation as code** - Treat your prompts as valuable project assets
- **Feedback loop** - Always capture improvements in your templates
- **Specialized guidance** - Create dedicated prompts for recurring scenarios
- **System behaviors** - Define consistent patterns across your entire project

## Next Steps

In the next session, we'll explore how to apply these techniques to solve common development challenges, including translating projects between programming languages and refactoring legacy code.