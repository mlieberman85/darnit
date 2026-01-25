# Claude Code Instructions for darnit

## Before Committing Code

**IMPORTANT**: Always run the full test suite before committing or pushing code changes:

```bash
uv run pytest tests/ -v
```

All tests must pass before pushing. If tests fail, fix the issues before committing.

## Lint Enforcement

This project enforces lint rules via tests. The following are checked:
- F401: Unused imports
- F841: Unused variables
- F821: Undefined names
- F811: Redefined while unused

To check and auto-fix lint issues:
```bash
uv run ruff check --select F401,F841 packages/ --fix
```

## Project Structure

- `packages/darnit/` - Core framework
- `packages/darnit-baseline/` - OpenSSF Baseline implementation
- `packages/darnit-plugins/` - Plugin adapters
- `packages/darnit-testchecks/` - Test framework implementation
- `main.py` - MCP server entry point
- `tests/` - Test suite

## Development Workflow

1. Make changes
2. Run lint checks: `uv run ruff check packages/`
3. Run tests: `uv run pytest tests/ -v`
4. Commit only after tests pass
