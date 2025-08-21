## Warning!!! This repository is an experimental fork for learning purpose, not for commercial use. Use at your own risk!!!

# WatermarkRemover-AI

**AI-powered watermark removal tool using Florence-2 and LaMA models**

## Overview

`WatermarkRemover-AI` is a cutting-edge application that uses AI models to accurately detect and remove watermarks. It uses Microsoft's Florence-2 to identify watermarks and LaMA to naturally fill in the removed regions. The software offers both a command-line interface (CLI) and a graphical user interface (GUI) based on PyQt6, making it accessible to both novice and advanced users.

## Features

* Multiple Modes: Process individual files or entire folders of images and videos.
* Advanced Watermark Detection: Uses Florence-2's open-vocabulary detection for accurate watermark identification.
* Seamless Inpainting: Uses LaMA for high-quality, context-aware watermark filling.
* Video Support: Process video files frame by frame to remove watermarks.
* Customizable Output:
* Configure the maximum bounding box size for watermark detection.
* Set transparency for watermark regions (images only).
* Force specific output formats (PNG, WEBP, JPG for images; MP4, AVI for videos).
* Progress Tracking: Real-time progress updates in GUI and CLI modes.
* **Dark Mode Support**: The GUI automatically adapts to the system's dark mode settings.
* **Efficient Resource Management**: Optimized for GPU acceleration using CUDA (optional).

## Quick Install

See the [QUICK_START.md](./QUICK_START.md) file for quick installation and setup.

For detailed installation, refer to the [INSTALLATION_EN.md](./INSTALLATION_EN.md) file.

### Prerequisites

* Conda/Miniconda installed.
* CUDA (optional for GPU acceleration; the application also runs well on CPUs).

### One-click installation

Run the PowerShell installation script:

```powershell
powershell -ExecutionPolicy Bypass -File install_windows.ps1
```

This script automatically installs all dependencies and downloads the necessary LaMA template.

## Usage

### Using the Graphical User Interface (GUI)

0. **Build**
```
conda create -n py312aiwatermark
conda activate py312aiwatermark
pip install PyQt6 transformers iopaint opencv-python-headless
iopaint download --model lama
```

1. **Launch the application** with:
```
python remwmgui.py
```

2. **Configure the settings**:
* **Mode**: Select "Process Single File" or "Process Directory"
* **Paths**: Browse and set the input/output directories
* **Options**:
* Enable overwriting of existing files
* Enable transparency for watermark regions (images only)
* Adjust the maximum bounding box size
* **Output format**: Choose between PNG, WEBP, JPG for images, MP4, AVI for videos, or keep the original format

3. **Begin processing**:
* Click "Start" to begin
* Monitor progress and logs in the interface

### Command Line (CLI) Usage

1. Basic Command:
```
python remwm.py input_path output_path
```

2. Options:
* `--overwrite`: Overwrites existing files
* `--transparent`: Makes watermark regions transparent (images only)
* `--max-bbox-percent`: Sets the maximum bounding box size (default: 10%)
* `--force-format`: Forces the output format (PNG, WEBP, JPG for images; MP4, AVI for videos)

3. Examples:
```
python remwm.py ./input_images ./output_images --overwrite --max-bbox-percent=15 --force-format=PNG
```

```
python remwm.py ./video_input.mp4 ./video_output.mp4 --max-bbox-percent=15 --force-format=MP4
```

## Upgrade Notes

If you have previously used a previous version of the repository, follow these steps to upgrade:

1. **Update the repository**:
```
git pull
```

2. **Remove the old environment**:
```
conda deactivate
conda env remove -n py312
```

3. **Run the installation script**:
```
powershell -ExecutionPolicy Bypass -File install_windows.ps1
```

## Common Issues

See the [INSTALLATION_FR.md](./INSTALLATION_FR.md) file for solutions to common issues.

## License

This project is licensed under the MIT License. See the LICENSE file for details.