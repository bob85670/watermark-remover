# WatermarkRemover-AI Installation Guide for Windows

This guide will help you install and configure WatermarkRemover-AI on your Windows system.

## Prerequisites

1. **Python and Conda**: You must have Miniconda or Anaconda installed on your system. If not, download and install Miniconda from the official website (https://docs.conda.io/en/latest/miniconda.html).

2. **Git**: If you want to clone the repository directly, you will need Git. Download it from git-scm.com (https://git-scm.com/downloads).

## Method 1: Using the automatic installation script

1. Open a command prompt (CMD) in the project folder.

2. Run the installation script:
```
install_windows.bat
```

3. Follow the on-screen instructions.

## Method 2: Manual Installation

If the automatic script doesn't work, follow these manual steps:

1. Open a Command Prompt (CMD) or PowerShell with administrator rights.

2. Navigate to the project folder:
```
cd path\to\WatermarkRemover-AI
```

3. Create the conda environment:
```
conda env create -f environment.yml
```

4. Activate the environment:
```
conda activate py312aiwatermark
```

5. Install additional dependencies:
```
pip install PyQt6 transformers iopaint opencv-python-headless
```

6. Download the LaMA model:
```
iopaint download --model lama
```

## Running the application

After installation, you can run the application:

1. Activate the environment (if it isn't already):
```
conda activate py312aiwatermark
```

2. Launch the GUI application:
```
python remwmgui.py
```

## Usage

Once the application is launched:

1. Select the processing mode:
- Process a single image
- Process an entire folder

2. Select the input and output paths.

3. Configure the options:
- Enable overwriting of existing files if necessary
- Set whether watermark areas should be made transparent
- Adjust the maximum bounding box size for detection
- Select the output format (PNG, WEBP, JPG, or original format)

4. Click "Start" to begin processing.

## Common Problems and Solutions

### Problem: "Conda is not recognized as an internal or external command"
**Solution**: Ensure that Conda is properly installed and that its path is added to the PATH environment variable.

### Problem: Failure to install dependencies
**Solution**: Try running the installation commands individually and check for specific error messages.

### Problem: The application fails to start
**Solution**: Ensure that the Python environment is properly activated with `conda activate py312aiwatermark`.

### Problem: The LaMA model fails to download
**Solution**: Ensure you have a stable internet connection and try again with the `iopaint download --model lama` command.

## Support

If you encounter any problems, you can:
- Open an issue on the [GitHub repository](https://github.com/D-Ogi/WatermarkRemover-AI)
- Check existing discussions to see if anyone has already encountered the same problem

---

Enjoy your new AI-powered watermark removal tool!