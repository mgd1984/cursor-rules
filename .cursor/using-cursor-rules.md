# Using Cursor Rules

Guidance on defining, managing, and applying Cursor Rules effectively for our Next.js/T3/TypeScript project.

## Core Concepts

Cursor Rules provide persistent, reusable context to the AI (Claude and other assistants), encoding preferences, workflows, and project-specific knowledge.

- **Project Rules**: Live in `.cursor/rules`, are version-controlled (`.mdc` format), and scoped to the codebase.
- **User Rules**: Global, plain text rules defined in settings, always applied.

## Project Rule Structure (.mdc Format)

Rules use MDC (Markdown with YAML frontmatter) for metadata and content.

```mdc
---
# Metadata (YAML Frontmatter)
description: "Brief explanation of the rule's purpose."
# --- Activation Type --- (Choose ONE)
alwaysApply: true # Rule Type: Always
globs: ["src/server/api/**/*.ts"] # Rule Type: Auto Attached (applied when matching files are in context)
# Rule Type: Agent Requested (no explicit keyword, relies on description for AI decision)
# Rule Type: Manual (no explicit keyword, only activated via @RuleName)
---

# Rule Content (Markdown)

Detailed instructions, guidelines, principles for the AI.

Can reference other rules using [Rule Name](mdc:.cursor/rules/category/rule-name.mdc).
```

## Our Rule Categories

Our rules are organized into categories:

1. **Architecture** - Project structure and tech stack
2. **Memory/State** - Data fetching and state management
3. **DevOps** - Deployment, CI/CD, and infrastructure
4. **Errors** - Error handling patterns
5. **Forms** - Form implementation patterns
6. **Performance** - Optimization techniques
7. **Workflow** - Development process preferences
8. **Security** - Security guidelines
9. **Project** - Component and feature implementation
10. **Accessibility** - A11y best practices
11. **Preferences** - Coding style and communication

## Choosing the Right Rule Type

- **Always (`alwaysApply: true`)**: Non-negotiable, project-wide standards (e.g., core architecture, essential security checks).
- **Auto Attached (`globs: [...]`)**: Context-specific guidance triggered by file paths (e.g., component styling rules for `src/components/**`, API validation rules for `pages/api/**`).
- **Agent Requested (Description Only)**: Situational guidance the AI *may* choose to apply based on relevance (e.g., complex refactoring patterns, performance optimization suggestions).
- **Manual (Description Only)**: Explicitly invoked rules via `@RuleName` in chat (e.g., boilerplate templates, rarely needed checklists).

## Creating and Managing Rules

### New Rules

1. Create a markdown file (.mdc) in the appropriate category directory under `.cursor/rules/`
2. Use consistent naming: `###-descriptive-name.mdc` where ### is a number (001, 002, etc.)
3. Add YAML frontmatter if using Auto Attached or Always Apply activation
4. Write clear, concise content with examples where relevant
5. Add cross-references to related rules using `[Rule Name](mdc:.cursor/rules/category/rule-name.mdc)` syntax

### Testing and Validation

1. **Chat**: Invoke rules manually (`@category/rule-name`) or trigger auto-attached rules by referencing relevant files.
2. **Observe AI Behavior**: Check if the AI follows the rule's guidance.
3. **Debug**: If a rule isn't applying, check:
   - Correct rule type/metadata (`alwaysApply`, `globs`, `description`).
   - Glob patterns match intended files.
   - File is saved in the `.cursor/rules` directory.
   - No conflicting rules.

## Best Practices

For detailed best practices on creating effective Cursor rules, see [best-practices.md](mdc:.cursor/best-practices.md). 