```markdown
# ralph-orchestrator Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and workflows used in the `ralph-orchestrator` Python codebase. You'll learn about file naming, import/export conventions, localization workflows (especially for Japanese documentation and HTML viewers), and how to write and organize tests. This guide will help you contribute code and documentation that matches the project's established style.

## Coding Conventions

### File Naming
- **Convention:** camelCase
- **Example:**  
  - `buildJaViewers.py`
  - `checkJaCoverage.py`
  - `jaScope.py`

### Import Style
- **Convention:** Relative imports
- **Example:**
  ```python
  from .utils import parseConfig
  from ..models import Orchestrator
  ```

### Export Style
- **Convention:** Named exports (explicitly defining what is exported)
- **Example:**
  ```python
  __all__ = ['buildJaViewers', 'checkJaCoverage']
  ```

### Commit Messages
- **Style:** Conventional commits, primarily using the `docs` prefix
- **Example:**  
  `docs: add Japanese localization for main documentation`

## Workflows

### add-japanese-localization-with-html-viewers
**Trigger:** When someone wants to localize existing documentation or examples to Japanese and provide interactive HTML viewers.  
**Command:** `/localize-ja`

1. **Create or translate `.ja.md` files**  
   For each documentation or example file, create a corresponding `.ja.md` file with the Japanese translation.
   - Example:  
     - `README.md` → `README.ja.md`
     - `exampleUsage.md` → `exampleUsage.ja.md`
2. **Generate `.ja.html` viewer files**  
   Use the build scripts to generate interactive HTML viewers for each `.ja.md` file.
   - Example command:
     ```bash
     python scripts/buildJaViewers.py
     ```
   - Output:  
     - `README.ja.html`
     - `exampleUsage.ja.html`
3. **Update or refine localization scripts**  
   If needed, update scripts that check localization coverage or build viewers.
   - Files involved:
     - `scripts/buildJaViewers.py`
     - `scripts/checkJaCoverage.py`
     - `scripts/jaScope.py`
4. **Check coverage**  
   Run the coverage checker to ensure all documentation/examples have Japanese versions.
   - Example command:
     ```bash
     python scripts/checkJaCoverage.py
     ```

## Testing Patterns

- **Test File Pattern:** Files named with `.test.` in the filename (e.g., `utils.test.py`)
- **Framework:** Not explicitly detected; use standard Python testing approaches (e.g., `unittest` or `pytest`).
- **Example:**
  ```python
  # utils.test.py
  import unittest
  from .utils import parseConfig

  class TestParseConfig(unittest.TestCase):
      def test_valid_config(self):
          self.assertEqual(parseConfig("key=val"), {"key": "val"})
  ```

## Commands

| Command       | Purpose                                                                 |
|---------------|------------------------------------------------------------------------|
| /localize-ja  | Start the Japanese localization workflow for docs and examples          |
```
