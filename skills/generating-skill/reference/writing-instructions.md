# Writing Instructions

Instructions are the core of a skill—they tell Claude what to do and how to do it.

## Core Principle: Assume Intelligence

**Default assumption**: Claude is already intelligent. Don't explain basics or provide excessive context.

### Good Example (Concise, ~50 tokens)

```markdown
## Extracting PDF Text

Use pdfplumber for text extraction:

```python
import pdfplumber

with pdfplumber.open("file.pdf") as pdf:
    text = pdf.pages[0].extract_text()
```
```

### Bad Example (Verbose, ~150 tokens)

```markdown
## Extracting PDF Text

PDF (Portable Document Format) files are a common file format that contain
text, images, and other content. To extract text from a PDF, you need to
use a library. There are many libraries available for PDF processing, but we
recommend using pdfplumber because it's easy to use and handles most cases.
First, you need to install it using pip. Then you can use the code below...
```

The concise version assumes Claude knows what PDFs are and how libraries work.

## Levels of Freedom

### High Freedom (Text-based guidance)

Use when multiple approaches work and decisions depend on context.

**Characteristics**:
- Multiple valid methods
- Context-dependent decisions
- Heuristic approaches acceptable

**Example**:
```markdown
## Code Review Process

1. Analyze code structure and organization
2. Check for potential errors or edge cases
3. Suggest readability and maintainability improvements
4. Verify adherence to project conventions
```

### Medium Freedom (Pseudocode or parameterized scripts)

Use when there's a preferred pattern but variations are acceptable.

**Characteristics**:
- Preferred pattern exists
- Some variation acceptable
- Configuration affects behavior

**Example**:
```markdown
## Generating Reports

Use this template and customize as needed:

```python
def generate_report(data, format="markdown", include_charts=True):
    # Process data
    # Generate output in specified format
    # Optionally include visualizations
```
```

### Low Freedom (Specific scripts, few/no parameters)

Use when operations are fragile and consistency is critical.

**Characteristics**:
- Operations are fragile
- Consistency is crucial
- Must follow specific sequence

**Example**:
```markdown
## Database Migration

Run this exact script:

```bash
python scripts/migrate.py --verify --backup
```

Do not modify the command or add additional flags.
```

## Structure

### Use Clear Headings

```markdown
## Main Task Name

### Sub-task 1
Instructions for sub-task 1

### Sub-task 2
Instructions for sub-task 2
```

### Include Code Examples

Always show concrete examples:

```markdown
## Processing Data

Transform input data:

```python
def transform(data):
    return {k.upper(): v for k, v in data.items()}
```
```

### Provide Context When Needed

Only include context that affects the approach:

```markdown
## Handling Errors

For network errors, retry with exponential backoff.
For validation errors, return immediately with details.
```

## Best Practices

1. **Be specific**: "Use pdfplumber" not "Use a PDF library"
2. **Show, don't tell**: Include code examples
3. **Keep it brief**: ~50 tokens per instruction section
4. **Focus on what**: What to do, not why (unless critical)
5. **Use appropriate freedom level**: Match the instruction style to the task

## Common Mistakes

1. **Over-explaining**: Don't explain what Claude already knows
2. **Under-specifying**: Don't leave critical steps ambiguous
3. **Wrong freedom level**: Don't use low freedom when flexibility is needed
4. **Missing examples**: Always include concrete examples
5. **Verbose code comments**: Let the code speak for itself
