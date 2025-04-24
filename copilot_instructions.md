# Copilot Instructions

These guidelines instruct GitHub Copilot (the AI code assistant) on how to contribute effectively to this Python project.

## Project Structure

Use the following structure as a reference when adding or modifying files:

```
demo-repo/
├── .github/
│   └── workflows/
│       └── ci.yml           # Continuous Integration configuration
├── docs/                    # Project documentation (Sphinx, MkDocs, or similar)
├── src/
│   └── <package_name>/      # Main Python package
│       ├── __init__.py
│       └── ...              # Modules and subpackages
├── tests/                   # Unit and integration tests
│   └── test_*.py
├── .gitignore               # Files and directories to ignore in Git
├── README.md                # Project overview and setup instructions
├── requirements.txt         # List of runtime dependencies
├── setup.py                 # Packaging and installation script (or use pyproject.toml)
└── pyproject.toml           # Build system and tool configuration
```

> **Note:** Replace `<package_name>` with the actual name of the Python package in `src/`.

## Coding Guidelines

- **Style & Formatting**
  - Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) conventions.
  - Use `black` for auto-formatting. Configure with the project’s `pyproject.toml` or `setup.cfg`.
  - Use `isort` for import sorting.
- **Naming Conventions**
  - Modules and variables: lowercase with underscores (e.g., `my_module.py`, `my_function`).
  - Classes: `CamelCase` (e.g., `MyClass`).
  - Constants: UPPER_SNAKE_CASE (e.g., `MAX_RETRIES`).
- **Docstrings**
  - Use [Google-style](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html) or [NumPy-style](https://numpydoc.readthedocs.io/en/latest/format.html).

## Dependency Management

- Add new dependencies to `requirements.txt` (or `pyproject.toml` under `[tool.poetry.dependencies]`).
- After adding, run `pip install -r requirements.txt` and verify imports.

## Testing

- Use `pytest` for all tests.
- Place test files in `tests/`, mirroring the structure under `src/`.
- Aim for at least 90% code coverage.
- Write tests for both expected behavior and edge cases.

## Continuous Integration (CI)

- CI is configured in `.github/workflows/ci.yml`.
- Every pull request must pass:
  - Formatting (`black --check`).
  - Linting (e.g., `flake8`).
  - Tests (`pytest`).
  - (Optional) Type checking (`mypy`).

## Documentation

- Document new public APIs in `docs/` and update `README.md` as needed.
- Ensure doc builds and examples render correctly.

## Git & Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
feat: add new feature
fix: resolve bug
docs: update documentation
style: code formatting changes (no logic)
refactor: code restructuring
test: add or update tests
chore: maintenance tasks
```

- Prefix commit messages with the appropriate type.
- Use imperative mood (e.g., “Add feature” not “Added feature”).

## Branching & Pull Requests

- Create topic branches named by convention: `<type>/<short-description>` (e.g., `feat/add-auth`).
- Open a pull request against the `main` branch.
- Include:
  - A clear title and description.
  - Motivation and context.
  - List of changes with bullet points.
  - Reference to related issues (e.g., `Closes #123`).
- Request at least one reviewer before merging.

## Copilot Interactions

- **Context Awareness:** Review existing code patterns before generating new code.
- **Clarifications:** If requirements are unclear, ask for more details.
- **Security & Best Practices:** Avoid hardcoding secrets; use environment variables and secure storage.
- **Error Handling:** Follow project’s error-handling conventions (`exceptions.py`, custom error classes).
- **Testing:** Always provide or update corresponding tests when generating business logic.
- **Performance:** Keep performance in mind; use efficient algorithms and native data structures.

---

By following these guidelines, Copilot will generate consistent, maintainable, and high-quality code aligned with the project’s standards.

