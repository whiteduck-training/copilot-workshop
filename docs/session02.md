# Session 02 - Setting Up AI-Driven Project Management

In this session, we'll learn how to create initialization prompts that teach AI tools to establish and maintain a project management structure. Once set up, you'll be able to describe high-level project goals and have the AI generate detailed project documentation automatically.

## Creating an Initialization Prompt

The first step is to create an initialization prompt that teaches the AI how to set up your project management structure.

### Example: `@init.md`

Create a file named `@init.md` in your project root with the following content:

```markdown
# Initialization of a new project

Create following folder structure with a placeholder story/task/overview for the time being.


.project/
├── specifications/
│   └── project_overview.md
├── user_stories/
│   ├── us_001.md
│   └── ...
└── tasks/
    ├── us_001_task_001.md
    ├── ...
    └── ...


and two index files in the `.project` root

USER-STORIES.MD
TASKS.MD

for quick overview about all items.

This is how the items should look like

## Project Overview


# Project: [Project Name]

## Overview
[Brief description of the project]

## Current State
[Description of existing functionality or starting point]

## Goal State
[Description of desired end state]

## Technical Context
- Programming language: [Language]
- Framework: [Framework]
- Key libraries: [Libraries]
- Patterns to follow: [Patterns]

## Constraints
[Any limitations or requirements to follow]


### User Stories

**Purpose:** Describes features from a user perspective

**Recommended Structure:**

# User Story: [US-ID]

## Title
[Brief descriptive title]

## Description
As a [type of user], I want [goal] so that [benefit].

## Acceptance Criteria
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion 3]

## Technical Notes
[Any implementation details or considerations]

## Related Stories
- [Related-US-ID-1]
- [Related-US-ID-2]



### Tasks

**Purpose:** Provides specific implementation details

**Recommended Structure:**

# Task: [Task-ID]

## Title
[Brief descriptive title]

## Related User Story
[US-ID]

## Description
[Detailed description of what needs to be implemented]

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
[How this task should be tested]

```

## Initializing the Project Structure

After creating the initialization prompt, you'll use it to set up the basic project management structure.

### Steps to Initialize

1. Open your AI tool (GitHub Copilot, Cursor, etc.)
2. Reference the initialization prompt:
   ```
   Please follow the instructions in @init.md
   ```
3. The AI will create the folder structure and placeholder files
4. Verify that the structure has been created correctly

## Generating Project Documentation

Once the project structure is in place, you can use natural language to have the AI generate detailed project documentation.

### Example Prompt

```
I want to create a .NET C# app for scaffolding prompts like @init.md. The app should guide the user through some questions, and based on the answers, different kinds of prompt templates get merged into a single prompt. And it should not stop with just the init prompt. For example, another prompt could be built this way defining the rules for creating the new project, which framework, which libraries, etc.

Please generate the necessary items in .project to plan this project.
```

### What to Expect

After providing a high-level description like the example above, the AI should:

1. Update `project_overview.md` with relevant details
2. Create meaningful user stories in the `user_stories/` directory
3. Break down user stories into specific tasks
4. Update the index files for quick reference

## Workshop Exercise: Setting Up a Project

Let's apply what we've learned:

1. Create an `@init.md` file based on the template provided
2. Use your AI tool to initialize the project structure
3. Provide a high-level description for one of the following projects:
   - ASCII font renderer CLI application
   - Project management CLI application
   - A project of your choice

4. Review the generated documentation:
   - Is it complete and well-structured?
   - Do the user stories cover all aspects of your project?
   - Are the tasks specific and actionable?
   - What refinements would you make?

## Best Practices for Project Initialization

1. **Be explicit in your initialization prompt** - Clearly define the structure and templates you want the AI to use

2. **Provide sufficient context in your project description** - Include key features, technologies, and constraints

3. **Review and refine generated content** - AI-generated documentation is a starting point that often needs human refinement

4. **Iterate on unclear items** - If a user story or task is vague, ask the AI to elaborate or provide more specific details

5. **Keep your documentation up-to-date** - As your project evolves, ensure your documentation reflects the current state


## Next Steps

In the next session, we'll explore ways to fine-tune our process and to improve it.

In the next session, we'll explore how to use the generated project documentation to guide AI in implementing specific tasks, focusing on effective prompting techniques for code generation.