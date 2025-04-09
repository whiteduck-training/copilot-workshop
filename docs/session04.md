# Session 04 - Implementing Tasks with AI Assistance

In this session, we'll focus on the practical aspects of implementing code with AI assistance. You'll learn how to guide the AI through code implementation, handle new sessions effectively, troubleshoot implementation failures, and maintain a productive development workflow.

## Establishing Context for Implementation

The most critical step for successful AI implementation is ensuring the AI has sufficient context. Without proper context, implementations will be generic and disconnected from your project.

### Creating a Context Prompt Template

Let's create an `@context.md` prompt that helps the AI understand your codebase at the beginning of each session:

```markdown
# Project Context Initialization

Before we start working today, please:

1. Read and analyze the following:
   - `.project/specifications/project_overview.md` to understand the project goals
   - All user stories in `.project/user_stories/` to understand features
   - All tasks in `.project/tasks/` to understand implementation details
   - Existing code in the project to understand the current state

2. Provide a brief summary of your understanding, including:
   - The project's overall purpose
   - Current implementation status
   - Pending tasks to be implemented
   - Any architectural patterns you observe

3. Let me know if you need any clarification about:
   - The project structure
   - Implementation approach
   - Specific technical questions

This will help ensure your suggestions are aligned with the project goals and current implementation.
```

### Using the Context Prompt

At the beginning of each new session, start with:

```
Please follow the instructions in @context.md
```

This ensures the AI builds a mental model of your project before attempting to implement any code.

## Implementing Specific Tasks

Once the AI understands the project context, you can direct it to implement specific tasks.

### Implementation Request Template

Create an `@implement.md` template:

```markdown
# Task Implementation

When I ask you to implement a specific task (e.g., "Please implement Task T-001-02"), please:

1. First, read and understand the task details from the corresponding task file

2. Read any related user stories and other related tasks

3. Before writing any code, outline your implementation approach:
   - Files you'll need to create or modify
   - Key algorithms or patterns you'll use
   - Any external dependencies required
   - Potential challenges and how you'll address them

4. After I approve your approach, implement the code in manageable chunks:
   - Create one file at a time
   - For large files, implement them in logical sections
   - Explain key parts of the implementation
   - Highlight any design decisions or trade-offs

5. After implementation, suggest tests that would verify the implementation

6. Update the task in the .project directory, marking completed acceptance criteria

If the implementation is complex, prefer breaking it into multiple messages rather than trying to implement everything at once.
```

### Example Implementation Workflow

**User:**
```
Please follow the instructions in @context.md
```

**AI:**
```
[Provides summary of project understanding]
```

**User:**
```
Please implement Task T-001-02
```

**AI:**
```
I'll implement Task T-001-02: "Implement Font Repository"

First, let me review the task details:
[AI restates task details]

Implementation Approach:
1. I'll need to create:
   - Models/FontDefinition.cs - to represent ASCII font data
   - Repository/IFontRepository.cs - interface for font operations
   - Repository/FontRepository.cs - concrete implementation
   - Resources/Fonts/ - directory for font definition files

2. Key Components:
   - FontDefinition will store character mappings to ASCII representations
   - Repository will load fonts from resource files
   - Will implement caching to avoid repeated file reads

3. Potential Challenges:
   - Ensuring consistent character heights within fonts
   - Handling missing characters in font definitions
   - File system access for different operating systems

Does this approach align with your expectations?
```

**User:**
```
That looks good, please proceed with the implementation.
```

**AI:**
```
[Implements the code in manageable chunks]
```

## Handling Implementation Failures

Even with good context, AI may sometimes struggle with implementations. Let's create a troubleshooting approach.

### Common Failure Scenarios and Solutions

#### 1. Misunderstood Requirements

**Problem:** The AI implements something different from what was intended.

**Solution:** Create an `@clarify.md` prompt:

```markdown
# Requirement Clarification

I notice the implementation doesn't match what I expected. Let's clarify:

## Current Understanding
[AI describes its current understanding]

## Clarification
[User provides clarification]

## Updated Approach
[AI proposes updated approach]

After we agree on the updated approach, please re-implement according to the new understanding.
```

#### 2. Implementation Errors

**Problem:** The AI's code contains errors or doesn't work as expected.

**Solution:** Create an `@debug.md` prompt:

```markdown
# Implementation Debugging

The current implementation has issues. Let's debug:

## Current Issue
[Describe the specific error or unexpected behavior]

## Error Analysis
[AI analyzes possible causes]

## Potential Solutions
[AI proposes solutions]

Let's systematically fix these issues and then verify the solution.
```

#### 3. Complexity Overload

**Problem:** The task is too complex for a single implementation attempt.

**Solution:** Create a `@decompose.md` prompt:

```markdown
# Task Decomposition

This task seems more complex than initially thought. Let's break it down:

1. Analyze the task complexity
2. Divide into smaller, manageable sub-tasks
3. Implement each sub-task sequentially
4. Integrate the sub-tasks into a complete solution

Please propose a breakdown of this task into smaller steps.
```

## Maintaining Implementation Momentum

To keep your development process moving smoothly, consider these strategies:

### 1. Progressive Implementation

Instead of trying to implement an entire feature at once, use a step-by-step approach:

```
Please implement just the basic structure for Task T-001-02, without the full functionality yet.
```

Then:

```
Now, let's add the functionality to load font definitions from files.
```

### 2. Implementation Checkpoints

Regularly verify your progress:

```
Let's test what we have so far. Can you write a simple program that uses the FontRepository to list available fonts?
```

### 3. Documentation While Implementing

Have the AI document its work as it goes:

```
As you implement, please also update the task file with implementation notes and any design decisions you're making.
```

## Workshop Exercise: Implementation Practice

Let's apply these techniques to our project:

### Exercise 1: Creating Implementation Prompts
1. Create the following prompt templates:
   - `@context.md` - For establishing project context
   - `@implement.md` - For implementing specific tasks
   - `@debug.md` - For troubleshooting issues

2. Test the context prompt with your project

### Exercise 2: Implementing a Task
1. Choose a simple task from your project
2. Ask the AI to implement it using your implementation prompt
3. Review the implementation approach before proceeding
4. Guide the AI through implementation

### Exercise 3: Handling Implementation Failures
1. Intentionally give the AI an ambiguous task or requirement
2. When it struggles, use your troubleshooting prompts
3. Guide it to a successful implementation

## Advanced Implementation Techniques

### Creating an Implementation Review Prompt

For more critical code, create an `@review.md` prompt:

```markdown
# Implementation Review

Before finalizing this implementation, let's review it:

## Code Review
- Check for edge cases
- Verify error handling
- Ensure adherence to project patterns
- Look for performance issues

## Testing Strategy
- Unit test cases
- Integration test considerations
- Edge cases to test

Let's ensure this implementation is robust before proceeding.
```

### Implementation Refactoring Prompt

As implementation progresses, create an `@improve.md` prompt:

```markdown
# Implementation Improvement

Now that we have a working implementation, let's improve it:

## Current Limitations
[Identify current limitations]

## Improvement Opportunities
- Performance optimizations
- Readability improvements
- Better error handling
- More flexible design

Let's systematically enhance this implementation while maintaining its functionality.
```

## Key Takeaways

- **Context is crucial** - Always ensure the AI understands your project before implementing
- **Start each session with context** - Use `@context.md` to establish understanding
- **Approach before code** - Validate implementation approaches before writing code
- **Divide and conquer** - Break complex implementations into manageable chunks
- **Expect and handle failures** - Have strategies ready for when implementations don't work
- **Progressive improvement** - Build basic functionality first, then enhance
- **Review and refine** - Systematically review and improve implementations

## Next Steps

In the next session, we'll explore how to leverage AI for testing, refactoring existing code, and documenting your implementations.