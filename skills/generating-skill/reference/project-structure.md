# Project Structure

Skills follow the [agentskills](https://github.com/agentskills/agentskills) standard format.

## Directory Layout

```
skills/
  <skill-name>/
    SKILL.md              # Entry point with YAML frontmatter
    reference/            # Optional: detailed documentation
      *.md                # Reference files loaded on-demand
```

## Required Files

### `SKILL.md`

The main entry point for the skill. Must include:

1. **YAML frontmatter** with required fields:
   - `name`: Skill identifier
   - `description`: Discovery metadata

2. **Main content**:
   - Skill title
   - Instructions section
   - Examples section

**Example structure**:
```markdown
---
name: processing-pdfs
description: Extracts text and metadata from PDF files using pdfplumber.
---

# Processing PDFs

## Instructions
[Clear, step-by-step guidance]

## Examples
[Concrete usage examples]
```

## Optional Files

### `reference/*.md`

Reference files provide detailed documentation that can be loaded on-demand. Use them for:

- **Extended documentation**: Detailed guides, best practices
- **Advanced topics**: Complex use cases, edge cases
- **Reference material**: API details, configuration options
- **Examples**: Additional examples beyond the main SKILL.md

**Naming convention**: Use descriptive, kebab-case names:
- `yaml-frontmatter.md`
- `naming-conventions.md`
- `writing-instructions.md`
- `description-field.md`

## File Organization

### When to Use Reference Files

**Use reference files when**:
- Content exceeds ~200 lines
- Multiple related topics need separate documentation
- Advanced topics need detailed explanation
- You want to keep SKILL.md concise

**Keep in SKILL.md when**:
- Content is concise (~50-100 lines total)
- All information is essential for basic usage
- Examples are simple and self-contained

## Best Practices

1. **Keep SKILL.md focused**: Essential information only
2. **Organize references logically**: Group related topics
3. **Use clear file names**: Descriptive, kebab-case
4. **Cross-reference when needed**: Link between files if helpful
5. **Maintain consistency**: Follow the same structure across skills

## Example Structure

### Simple Skill (No References Needed)

```
skills/processing-pdfs/
  SKILL.md
```

### Complex Skill (With References)

```
skills/generating-skills/
  SKILL.md
  reference/
    yaml-frontmatter.md
    naming-conventions.md
    writing-instructions.md
    description-field.md
    project-structure.md
```

## Integration with Marketplace

Skills are registered in `.claude-plugin/marketplace.json`:

```json
{
  "skills": [
    {
      "name": "processing-pdfs",
      "path": "skills/processing-pdfs/SKILL.md"
    }
  ]
}
```

The marketplace manifest references the `SKILL.md` file, which serves as the entry point. Reference files are loaded automatically when the skill is used.
