# WatermarkRemover-AI - Quick Start Guide

## Quick Installation on Windows

1. **Prerequisites**: Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) if you haven't already.

2. **Install the application**:
- Open PowerShell as an administrator
- Navigate to the project folder
- Run the command:
```
powershell -ExecutionPolicy Bypass -File install_windows.ps1
```

3. **Alternative**: Manual installation
```powershell
# Create the conda environment
conda env create -f environment.yml

# Activate the environment
conda activate py312aiwatermark

# Install additional dependencies
pip install PyQt6 transformers iopaint opencv-python-headless

# Download the LaMA model
iopaint download --model lama
```

## Launching the application

1. Open PowerShell
2. Activate the environment: `conda activate py312aiwatermark`
3. Launch the application: `python remwmgui.py`

## Basic Usage

1. **Mode**: Choose between processing a single image or an entire folder.
2. **Paths**: Set the input and output paths.
3. **Options**:
- **Overwrite Existing Files**: Overwrite existing files.
- **Make Watermark Transparent**: Make watermark areas transparent.
- **Max BBox Percent**: Maximum size of the watermark area (as a percentage of the image).
- **Output Format**: PNG, WEBP, JPG, or keep the original format.
4. **Start**: Start processing.

## Usage Tips

- For best results, use the PNG format, which supports transparency.
- If processing large images, use a lower value for Max BBox Percent. - The transparency option is particularly useful for preserving image details.

## Troubleshooting

- Check that all prerequisites are installed correctly.
- Ensure the conda environment is enabled.
- See the `INSTALLATION_EN.md` file for more detailed instructions.