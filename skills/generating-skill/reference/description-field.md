# Description Field Guide

The `description` field is critical for skill discovery. Claude uses it to select the right skill from potentially 100+ available skills.

## Purpose

The description enables skill discovery by:
- Telling Claude what the skill does
- Indicating when to use it (triggers/context)
- Providing key terms for matching

## Writing Style

### Use Third Person

> [!Warning]
> Always write in third person. The description is injected into system prompts, and inconsistent perspective can cause discovery issues.

**Correct**:
- "Extracts text from PDF files using pdfplumber"
- "Performs systematic code reviews by analyzing structure"
- "Generates API documentation from code comments"

**Incorrect**:
- "Helps you extract text from PDFs" (second person)
- "I extract text from PDFs" (first person)
- "Extract text from PDFs" (imperative)

## Content Requirements

### Be Specific

Include:
- **What** the skill does (functionality)
- **When** to use it (triggers/context)
- **Key terms** for discoverability

### Good Examples

```
Extracts text and metadata from PDF files using pdfplumber. Use when working with PDF documents that need text extraction or analysis.
```

```
Performs systematic code reviews by analyzing structure, checking for errors, and suggesting improvements. Use when reviewing pull requests or improving code quality.
```

```
Generates API documentation from code comments and type hints. Use when creating or updating API documentation for Python projects.
```

### Bad Examples

```
Handles PDFs.
```
Too vague—doesn't specify what it does or when to use it.

```
This skill helps you work with PDF files by extracting text and other information. It's useful when you need to get text from PDF documents.
```
Too verbose, uses second person, and doesn't include key technical terms.

```
PDF text extraction.
```
Too brief, missing context about when to use it.

## Key Terms

Include relevant technical terms that Claude might search for:

- **Technologies**: "pdfplumber", "pandas", "React"
- **Actions**: "extract", "analyze", "generate", "validate"
- **Context**: "pull requests", "API documentation", "data analysis"
- **Formats**: "PDF", "CSV", "JSON", "Markdown"

## Length Guidelines

- **Minimum**: Enough to be specific and include key terms
- **Maximum**: 1024 characters
- **Optimal**: 100-200 characters (concise but complete)

## Structure

A well-structured description follows this pattern:

```
[What it does] using [how/technology]. Use when [trigger/context].
```

**Example**:
```
Extracts text and metadata from PDF files using pdfplumber. Use when working with PDF documents that need text extraction or analysis.
```

## Testing Your Description

Ask yourself:
1. Would Claude know what this skill does?
2. Would Claude know when to use it?
3. Does it include key terms someone might search for?
4. Is it written in third person?
5. Is it specific enough to distinguish from similar skills?

## Common Mistakes

1. **First/second person**: "Helps you..." → "Extracts..."
2. **Too vague**: "Handles files" → "Extracts text from PDF files"
3. **Missing context**: "Extracts text" → "Extracts text from PDF files. Use when..."
4. **Missing key terms**: "Works with documents" → "Extracts text from PDF files using pdfplumber"
5. **Too verbose**: Keep it concise while being complete
