---
name: generating-skills
description: Helps create new Claude Code skills by following the agentskills standard format. Use when creating or updating SKILL.md files with proper YAML frontmatter, clear instructions, and examples.
---

# Generating Skills

## Instructions

When creating or updating a skill, follow these steps:

1. **Create the SKILL.md file** with YAML frontmatter:
   - `name`: lowercase, alphanumeric, hyphens only (max 64 chars)
   - `description`: third-person, specific, includes key terms and use cases (max 1024 chars)
   - Avoid reserved words: "anthropic", "claude"

2. **Write concise instructions**:
   - Assume Claude is intelligent—avoid explaining basics
   - Keep instructions brief (~50 tokens per section)
   - Focus on what to do, not why

3. **Include practical examples**:
   - Show concrete usage patterns
   - Use code blocks when relevant
   - Demonstrate the skill in action

4. **Follow naming conventions**:
   - Prefer gerund form (verb-ing): `processing-pdfs`, `analyzing-data`
   - Avoid vague names: `helper`, `utils`, `tools`
   - Be specific and descriptive

5. **Structure reference files** (optional):
   - Place detailed documentation in `reference/*.md`
   - Load on-demand for complex skills
   - Keep SKILL.md focused on essentials

## Examples

### Creating a PDF Processing Skill

```markdown
---
name: processing-pdfs
description: Extracts text and metadata from PDF files using pdfplumber. Use when working with PDF documents that need text extraction or analysis.
---

# Processing PDFs

## Instructions

Use pdfplumber for text extraction:

```python
import pdfplumber

with pdfplumber.open("file.pdf") as pdf:
    text = pdf.pages[0].extract_text()
```
```

### Creating a Code Review Skill

```markdown
---
name: reviewing-code
description: Performs systematic code reviews by analyzing structure, checking for errors, and suggesting improvements. Use when reviewing pull requests or improving code quality.
---

# Reviewing Code

## Instructions

1. Analyze code structure and organization
2. Check for potential errors or edge cases
3. Suggest readability and maintainability improvements
4. Verify adherence to project conventions
```
