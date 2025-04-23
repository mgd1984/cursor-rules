# Best Practices for Cursor Rules

Guidelines for crafting effective, maintainable Cursor Rules for our project.

## Rule Content Best Practices

### Be Specific and Actionable

✅ **DO**:
- Provide concrete examples from our codebase
- Include specific TypeScript patterns we use
- Reference our component structure and patterns
- Link to implementation examples

❌ **DON'T**:
- Write overly general guidelines
- Include obvious programming practices
- Create rules that are too restrictive or prescriptive
- Duplicate TypeScript compiler checks

### Focus on Value-Add Guidance

✅ **DO**:
- Document hard-won lessons specific to our stack
- Encode architectural decisions and their rationales
- Capture team consensus on code organization
- Document complex interactions between components

❌ **DON'T**:
- Rehash common programming practices
- Create rules with vague suggestions
- Add rule content that will quickly become outdated

### Optimize Rule Organization

✅ **DO**:
- Use consistent prefix numbering (001-, 002-, etc.)
- Group related concepts into single rules
- Cross-reference related rules

❌ **DON'T**:
- Create many small, fragmented rules
- Duplicate content across rules
- Mix unrelated concepts in a single rule

## YAML Frontmatter Usage

### Always Add Description

✅ **DO**:
```yaml
---
description: "Guidelines for data fetching using React Query and API integration"
---
```

❌ **DON'T**:
```yaml
---
description: "Data rules"
---
```

### Use Glob Patterns Effectively

✅ **DO**:
```yaml
---
globs: ["src/components/**/*.tsx", "src/components/**/*.ts"] 
---
```

❌ **DON'T**:
```yaml
---
globs: ["**/*.ts"] # Too broad
---
```

### When to Use Always Apply

✅ **DO** use `alwaysApply: true` for:
- Core architectural patterns
- Cross-cutting concerns
- Non-negotiable standards

❌ **DON'T** use `alwaysApply: true` for:
- Domain-specific guidance
- Suggestions rather than requirements
- Rules that apply to specific file types

## Real-World Examples

### Well-Structured Rule Example

```mdc
---
description: "Standards for implementing form validation using react-hook-form and zod"
globs: ["src/components/**/Form*.tsx", "src/components/**/*Form.tsx", "src/pages/**/form*.tsx"]
---

# Form Implementation Standards

Forms in our application follow these patterns:

## Schema Definition
Define zod schemas separately from component:

```tsx
// formSchema.ts
import { z } from "zod";

export const userFormSchema = z.object({
  name: z.string().min(2).max(50),
  email: z.string().email(),
});

export type UserFormValues = z.infer<typeof userFormSchema>;
```

## Form Implementation
Use react-hook-form with zod resolver:

```tsx
import { useForm } from "react-hook-form";
import { zodResolver } from "@hookform/resolvers/zod";
import { userFormSchema, type UserFormValues } from "./formSchema";

export function UserForm() {
  const form = useForm<UserFormValues>({
    resolver: zodResolver(userFormSchema),
    defaultValues: {
      name: "",
      email: "",
    },
  });
  
  // Rest of implementation...
}
```

See [Error Handling Standards](mdc:.cursor/rules/errors/001-errors.mdc) for error display guidance.
```

## Common Pitfalls to Avoid

### Too Vague

❌ **Ineffective Rule**:
```
Always write clean, maintainable code with good documentation.
```

✅ **Better Alternative**:
```
Component documentation must include:
1. A JSDoc comment explaining its purpose
2. Prop type documentation with example values
3. Usage examples for complex components

Example:
```tsx
/**
 * Displays a paginated data table with sorting and filtering
 *
 * @example
 * <DataTable 
 *   data={users} 
 *   columns={userColumns} 
 *   initialSort="name" 
 * />
 */
```

### Too Restrictive

❌ **Ineffective Rule**:
```
All components must use the exact same error handling pattern with no variations.
```

✅ **Better Alternative**:
```
Error handling should follow these principles:
1. User-facing errors use ErrorBoundary or toast notifications
2. API errors should be logged and provide useful feedback
3. Form validation errors appear inline next to fields

Adapt the pattern based on the specific component needs while maintaining these principles.
```

### Documentation Heavy

❌ **Ineffective Rule**:
```
[10 pages of documentation without clear actionable guidance]
```

✅ **Better Alternative**:
Short, focused rules with clear sections:
- Principles (why we do this)
- Patterns (how we implement)
- Examples (real code from our project)
- References (links to related rules or resources)

## Maintenance Process

1. **Quarterly Review**: Review rules as a team every quarter.
2. **Deprecate Outdated Rules**: Mark obsolete rules with "DEPRECATED" and plan removal.
3. **Update with Lessons Learned**: Add new rules based on recurring issues or solutions.
4. **Get Team Feedback**: Share rule changes with the whole team for input.

---

*By tailoring your Cursor Rules this way—focused on T3-stack conventions, AI-driven iteration, and precision-first coding—you provide crisp, actionable guardrails that evolve seamlessly with your development flow.* 