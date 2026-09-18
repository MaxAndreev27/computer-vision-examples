# computer-vision-examples

Practical computer vision examples in Python using OpenCV, NumPy, Matplotlib, SciPy, scikit-learn, Pillow, scikit-image, and PyTorch.

## Contents

- [01 Low-level image processing](#01-low-level-image-processing)
- [02 Image segmentation](#02-image-segmentation)
- [03 High-level image processing](#03-high-level-image-processing)

## Getting Started

Each module has its own `requirements.txt` and virtual environment because the
examples use different dependency sets. Create the environment from inside the
module you want to run:

```bash
git clone https://github.com/MaxAndreev27/computer-vision-examples.git
cd computer-vision-examples/<module-directory>
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

On Windows PowerShell, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

Open the notebook in the selected module in VS Code or Jupyter and run its cells
from top to bottom.

### 01 Low-level image processing

The first module demonstrates:

- Basic image operations: cropping, resizing, rotation, drawing, and text
- Spatial filtering, denoising, sharpening, and frequency-domain methods
- Color palette extraction, HSV analysis, and Retinex enhancement
- Threshold processing, corner detection, image comparison, and difference images

```bash
cd computer-vision-examples/01_low_level_image_processing
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Open `simple-operations.ipynb` and run the cells from top to bottom.

### 02 Image segmentation

The second module uses a separate virtual environment and demonstrates:

- HSV and color-based segmentation with morphological cleanup
- Distance transform and watershed segmentation
- Canny edge and contour detection
- QuickShift region segmentation
- SLIC-based superpixel segmentation and comparisons with SLICO, SEEDS, and MSLIC
- Mask R-CNN instance segmentation with COCO class labels, bounding boxes, and masks

```bash
cd computer-vision-examples/02_image_segmentation
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

The segmentation requirements use CPU-only PyTorch wheels. The Mask R-CNN cell downloads
pretrained COCO weights on its first run, so an internet connection is required initially.
Open `segmentation.ipynb` and run the cells from top to bottom.

### 03 High-level image processing

The third module uses OpenCV and MediaPipe for:

- CamShift object tracking in video
- Hand landmark detection and English gesture labels
- Sparse optical flow with Shi-Tomasi corners and Lucas-Kanade tracking
- Face detection and blurring with a Haar cascade
- Live object detection with MobileNet SSD and Caffe
- Controlling the mouse cursor with hand gestures (index finger moves the
  cursor, pinching the index and middle fingers clicks)

The gesture, face, object-detection, and mouse-control examples use a webcam. Press `Q`
(or `Esc` for the mouse-control example) or close the OpenCV window to stop the camera;
the examples release the camera in cleanup code. Linux users may need to grant the
Python process access to the camera device.

#### X11 vs. Wayland (mouse-control example)

The mouse-control example moves the real OS cursor, which depends on the display
server:

- **X11 sessions**: the notebook uses [`autopy`](https://pypi.org/project/autopy/),
  which works out of the box.
- **Wayland sessions** (the default on recent Ubuntu releases): Wayland's security
  model blocks apps from moving the system cursor through X11 APIs, so `autopy`
  calls silently do nothing. The notebook detects `XDG_SESSION_TYPE=wayland` and
  switches to [`ydotool`](https://github.com/ouilibrary/ydotool), which drives the
  cursor through `/dev/uinput` instead. Install and configure it first:

  ```bash
  sudo apt install ydotool
  sudo usermod -aG input $USER
  # log out and back in so the group membership takes effect
  ydotoold &
  ```

- Alternatively, log in to an **"Ubuntu on Xorg"** (or "GNOME on Xorg") session at
  the login screen to keep using `autopy` unchanged.

```bash
cd computer-vision-examples/03_high_level_image_processing
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

The notebook downloads `hand_landmarker.task` and the Haar cascade when needed.
The MobileNet SSD example requires these files in the module directory:

- `MobileNetSSD_deploy.prototxt.txt`
- `MobileNetSSD_deploy.caffemodel`

The mouse-control example additionally requires `autopy` (installed from
`requirements.txt`) and, on Wayland sessions, `ydotool` (see above).

Open `hight-image-processing.ipynb` and run the cells from top to bottom. The
MobileNet SSD example requires OpenCV 4.x because OpenCV 5 removed its Caffe importer.

## Project Structure

```text
01_low_level_image_processing/
├── images/
├── requirements.txt
└── simple-operations.ipynb
02_image_segmentation/
├── images/
├── requirements.txt
└── segmentation.ipynb
03_high_level_image_processing/
├── images/
├── requirements.txt
├── MobileNetSSD_deploy.caffemodel
├── MobileNetSSD_deploy.prototxt.txt
└── hight-image-processing.ipynb
```

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## License

This project is available under the [MIT License](LICENSE).
