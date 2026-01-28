# YAML Frontmatter Reference

Every skill must start with YAML frontmatter containing required metadata.

## Required Fields

### `name`
- **Type**: String
- **Max length**: 64 characters
- **Format**: lowercase letters, numbers, and hyphens only
- **Restrictions**: 
  - No XML tags
  - Cannot contain reserved words: "anthropic", "claude"
- **Best practice**: Use gerund form (verb-ing) like `processing-pdfs`, `analyzing-data`

### `description`
- **Type**: String
- **Max length**: 1024 characters
- **Format**: Plain text, no XML tags
- **Style**: Write in third person
- **Content**: Should include:
  - What the skill does
  - When to use it (triggers/context)
  - Key terms for discoverability

## Optional Fields

### `license`
- **Type**: String
- **Purpose**: Specify license for the skill
- **Example**: `MIT`, `Apache-2.0`

## Example

```yaml
---
name: processing-pdfs
description: Extracts text and metadata from PDF files using pdfplumber. Use when working with PDF documents that need text extraction or analysis.
license: MIT
---
```

## Common Mistakes

1. **Using first/second person in description**: 
   - ❌ "Helps you extract text from PDFs"
   - ✅ "Extracts text from PDF files using pdfplumber"

2. **Vague descriptions**:
   - ❌ "Handles PDFs"
   - ✅ "Extracts text and metadata from PDF files using pdfplumber. Use when working with PDF documents that need text extraction or analysis."

3. **Invalid name formats**:
   - ❌ `PDF_Processor` (uppercase, underscore)
   - ❌ `pdf processor` (space)
   - ✅ `processing-pdfs` (lowercase, hyphen)
