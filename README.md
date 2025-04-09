# Optimizing the use of AI productivity tools

## Introduction and Planning Approach

---

## The Schrödinger's AI Paradox

The biggest mistake developers make is falling into the **Schrödinger's AI Paradox**: simultaneously believing AI is too limited for serious development work, yet expecting it to implement impossibly complex systems.

### Common Ineffective Approaches

❌ *"Implement a new award-winning game!"*

❌ *"Implement a new feature even I don't understand. Please read these 200 pages of documentation to figure it out."*

Even if you get lucky with good results, you'll immediately face these problems:

- 🥺 The AI loses context in the next session
- 🥺 The work isn't easily shareable with colleagues

**Ask yourself:** Would you give the same task to a new intern? Probably not!

---

## The Intern Analogy

Think of AI tools like GitHub Copilot or Cursor as skilled interns who need proper guidance:

### Effective Intern Onboarding

1. **Code familiarization** - Intern taking notes
2. **Project management introduction**
3. **Creating well-specified user stories and tasks**

### Why Human Best Practices Work with AI

- **Onboarding** forces you to develop a comprehensive overview
- **Project management** helps track progress effectively
- **Well-specified items** lead to consistently better results

---

## Communication Medium

The right communication approach with AI tools makes all the difference:

- ✅ Keep specifications as part of your repository - trackable and shareable
- ✅ AI understanding improves with better context
- ✅ Different workflows can be adapted for different use cases and team members

---

## The Solution: Minimalistic Text-Based Project Management

> **Important Note:** AI capabilities are improving rapidly, so best practices are evolving week by week!

### Basic Framework

#### 1. Generate Project Specifications / High-Level Requirements

- Define current state and/or goal state
- High level view of the project

#### 2. Generate User Stories

- Features to implement
- Will change the state of specifications
- Focus on clear outcomes

#### 3. Generate Tasks

- Concrete plan on how to implement each user story
- Self-tracking capabilities
- Will update the state of user stories

**Project Flexibility:** Depending on the project size and complexity, you may need more or fewer levels in your hierarchy.

> Does this mean **I** have to write plenty of text and stuff?

No, you of course use the very AI to create those for you!

---

## Benefits of This Approach

- 🚀 Maintains context across multiple sessions
- 🤝 Facilitates collaboration with both AI and human team members
- 📈 Produces higher quality, more maintainable code
- 📚 Gradually builds useful documentation
- 🔄 Adapts to rapidly evolving AI capabilities

---

## Challenges to Consider

- 🚀 Every team has to "find" itself - very dependent on internal requirements, constraints, philosophy
- 🤝 AI is improving week by week
- 📈 Tools are improving week by week
- 📚 Organizational overhead
- 🔄 You don't write much code anymore

→ No pre-cut best practice "That's how you HAVE TO do it" possible  
→ Learning by doing is essential

---

## Workshop Goals

In the upcoming practical session, you'll apply this framework to experience how structured prompting dramatically improves AI tool performance.


What we'll create:

- A .NET C# CLI app for managing project management with GitHub Copilot and Cursor

What does this app do?

- By letting the user go through specialized wizards the cli app should create prompt templates as described in the Sessions inside docs/