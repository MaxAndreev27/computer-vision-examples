# computer-vision-examples

Practical computer vision examples in Python using OpenCV, NumPy, Matplotlib, SciPy, scikit-learn, and Pillow.

## Contents

- Basic image operations: cropping, resizing, rotation, drawing, and text
- Spatial filtering and image denoising
- Geometric mean, Laplacian, Gaussian, bilateral, and sharpening filters
- Butterworth and Wiener frequency-domain methods
- Color palette extraction and HSV color analysis
- Retinex enhancement and Haar-transform denoising
- Threshold processing and corner detection
- Image comparison and difference-image generation

## Getting Started

```bash
git clone https://github.com/MaxAndreev27/computer-vision-examples.git
cd computer-vision-examples/01_low_level_image_processing
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

On Windows PowerShell, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

Open `simple-operations.ipynb` in VS Code or Jupyter and run the cells from top to bottom.

## Project Structure

```text
01_low_level_image_processing/
├── images/
├── requirements.txt
└── simple-operations.ipynb
```

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## License

This project is available under the [MIT License](LICENSE).
