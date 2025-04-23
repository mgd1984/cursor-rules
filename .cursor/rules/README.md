# Cursor Rules Library

A comprehensive collection of Cursor Rules organized by category, designed to provide guidance for working with a Next.js/T3/TypeScript application.

## Ruleset Overview

For a comprehensive overview of all standards and patterns, see:
- [001-ruleset-overview.mdc](mdc:.cursor/rules/global/001-ruleset-overview.mdc) - Complete Next.js application coding standards

## Rule Categories

- **Architecture**
  - [001-project-overview.mdc](mdc:.cursor/rules/architecture/001-project-overview.mdc) - Project structure, tech stack, and file organization

- **Memory Management & State**
  - [001-data-state.mdc](mdc:.cursor/rules/memory/001-data-state.mdc) - Data fetching and state management patterns
  - [002-advanced-patterns.mdc](mdc:.cursor/rules/memory/002-advanced-patterns.mdc) - Advanced React patterns (compound components, render props, hooks composition)
  - [003-graphiti-mcp.mdc](mdc:.cursor/rules/memory/003-graphiti-mcp.mdc) - Model Context Protocol pattern for complex state

- **DevOps & Deployment**
  - [001-vercel-deployment-optimization.mdc](mdc:.cursor/rules/devops/001-vercel-deployment-optimization.mdc) - Vercel deployment, optimization and cost management
  - [003-git-workflow.mdc](mdc:.cursor/rules/devops/003-git-workflow.mdc) - Git workflow and commit message guidelines

- **Error Handling**
  - [001-errors.mdc](mdc:.cursor/rules/errors/001-errors.mdc) - Error handling strategies for client and server

- **Forms**
  - [001-forms.mdc](mdc:.cursor/rules/forms/001-forms.mdc) - Form implementation with React Hook Form and Zod

- **Performance**
  - [001-performance.mdc](mdc:.cursor/rules/performance/001-performance.mdc) - Performance optimization techniques

- **Workflow**
  - [001-workflow-preferences.mdc](mdc:.cursor/rules/workflow/001-workflow-preferences.mdc) - Development workflow preferences

- **Security**
  - [001-agent-security.mdc](mdc:.cursor/rules/security/001-agent-security.mdc) - AI agent security guidelines
  - [002-owasp-llm-top-10.mdc](mdc:.cursor/rules/security/002-owasp-llm-top-10.mdc) - OWASP Top 10 for LLM applications
  - [003-owasp-agents-guidelines.mdc](mdc:.cursor/rules/security/003-owasp-agents-guidelines.mdc) - OWASP guidelines for agent systems

- **Project Components**
  - [002-react-component.mdc](mdc:.cursor/rules/project/002-react-component.mdc) - React component implementation standards

- **Accessibility**
  - [001-a11y.mdc](mdc:.cursor/rules/accessibility/001-a11y.mdc) - Accessibility best practices

- **Preferences**
  - [001-coding-preferences.mdc](mdc:.cursor/rules/preferences/001-coding-preferences.mdc) - General coding preferences
  - [002-code-style.mdc](mdc:.cursor/rules/preferences/002-code-style.mdc) - Code style guidelines
  - [003-naming-tailwind.mdc](mdc:.cursor/rules/preferences/003-naming-tailwind.mdc) - Naming conventions and Tailwind usage
  - [004-communication.mdc](mdc:.cursor/rules/preferences/004-communication.mdc) - AI communication protocol

## Usage

To activate a rule in chat:
1. Reference it directly: `@architecture/001-project-overview`
2. Or use the rule picker by typing `@` and selecting from the list

Some rules are automatically attached based on the files being edited.

## Rule Management

- Rules are stored in `.cursor/rules/` directory, categorized by subdirectories
- Each rule uses the `.mdc` extension (Markdown for Cursor)
- Rules should be concise, focused, and cross-linked where appropriate
- All rules should be version-controlled with the project

For more detailed guidance on creating and using Cursor rules, see:
- [using-cursor-rules.md](mdc:.cursor/using-cursor-rules.md)
- [best-practices.md](mdc:.cursor/best-practices.md) 