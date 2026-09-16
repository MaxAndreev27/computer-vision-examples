# Contributing

Thank you for contributing to `computer-vision-examples`.

## Before You Start

- Search existing issues and pull requests before opening a new one.
- For larger changes, open an issue first to discuss the approach.
- Do not include private images, credentials, generated virtual environments, or unrelated files.

## Development Setup

```bash
cd 01_low_level_image_processing
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Use the project notebook and keep image paths relative to `01_low_level_image_processing`.

## Notebook Changes

- Keep cells focused and runnable from top to bottom.
- Use clear English headings and output labels.
- Check that referenced images exist in `images/`.
- Prefer reproducible examples and fixed random seeds when randomness is used.
- Avoid committing large generated outputs unless they are required for the example.

## Pull Requests

1. Create a focused branch from the default branch.
2. Make the smallest complete change that solves the problem.
3. Run the affected notebook cells from a clean kernel.
4. Update documentation or dependencies when needed.
5. Describe what changed and how it was tested.

Pull requests should pass the relevant checks and should not contain unrelated formatting or file changes.

## Commit Messages

Use a short, descriptive imperative subject, for example:

```text
Add image difference example
```

## Questions

For usage questions, see [SUPPORT.md](SUPPORT.md). For security issues, follow [SECURITY.md](SECURITY.md).
