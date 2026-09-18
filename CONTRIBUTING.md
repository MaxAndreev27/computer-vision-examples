# Contributing

Thank you for contributing to `computer-vision-examples`.

## Before You Start

- Search existing issues and pull requests before opening a new one.
- For larger changes, open an issue first to discuss the approach.
- Do not include private images, credentials, generated virtual environments, or unrelated files.

## Development Setup

```bash
cd <module-directory>
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Available module directories are `01_low_level_image_processing`, `02_image_segmentation`,
and `03_high_level_image_processing`. Use the notebook in the selected module and keep
image and model paths relative to that module.
The segmentation module uses CPU-only PyTorch dependencies; do not add CUDA or NVIDIA
packages to its requirements file.
The high-level processing module uses a webcam for several examples, MediaPipe for hand
landmarks, and OpenCV 4.x for the Caffe-based MobileNet SSD example. Keep camera cleanup
in `finally` blocks when changing webcam cells, including both window-close and `Q` exit.

## Notebook Changes

- Keep cells focused and runnable from top to bottom.
- Use clear English headings and output labels.
- Check that referenced images exist in the module's `images/` directory.
- Check that referenced model files and download URLs are documented for the module.
- Prefer reproducible examples and fixed random seeds when randomness is used.
- Avoid committing large generated outputs unless they are required for the example.
- For Mask R-CNN changes, document whether pretrained COCO weights and CPU inference were tested.
- For webcam changes, verify that the camera and OpenCV windows are released after every exit path.

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
