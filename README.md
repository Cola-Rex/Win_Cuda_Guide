# Win_Cuda_Guide

This project offers a concise, step-by-step guide to simplify the process of installing CUDA on Windows.

As AI is currently one of the hottest topics in IT, you might want to try it on your own computer. AI training relies heavily on CUDA, so the first step is to set up the local environment. This project will guide you through configuring CUDA on Windows step by step.

## Steps

### 1. Check if CUDA is Already Installed
- Press `win+R`, type `cmd` to open the terminal, and enter `nvcc -V`.
- If the version information is displayed, CUDA is already installed. Please note the version number after 'release' and proceed to step 3.
- If it displays: `'nvcc' is not recognized as an internal or external command, operable program or batch file`, then CUDA is not installed, and you should proceed to step 2.

### 2. Install CUDA

#### 2.1 Download CUDA
- Visit the CUDA download page: [NVIDIA CUDA Downloads](https://developer.nvidia.com/cuda-downloads).
- Select `CUDA Toolkit 12.2.1`, then click Windows -> x86_64 -> 11 -> exe(local).
- Click the Download button and wait for it to complete.

#### 2.2 Install CUDA
- Open the installer, choose 'Custom', install all components, and overwrite the current driver with the latest version.
- Note: A brief blackout might occur.

#### 2.3 Verify Installation
- Use the method from step 1, press `win+R`, type `cmd`, and enter `nvcc -V`. If the version information is displayed, CUDA was installed successfully.

### 3. Install cuDNN

#### 3.1 Download cuDNN
- Visit cuDNN's official page: [NVIDIA cuDNN Downloads](https://developer.nvidia.com/rdp/cudnn-download).
- Download the corresponding CUDA version, e.g., if your CUDA version is 12.2, choose the 12.x version.
- Unzip the downloaded file, rename the folder to 'cudnn', and copy it to the CUDA installation directory.

#### 3.2 Configure Environment Variables
- Open Path and add the following two lines:
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\extras\CUPTI\lib64`
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\cudnn\bin`

### 4. Install PyTorch
- Visit PyTorch's official website: [PyTorch](https://pytorch.org/get-started/locally/).
- Find the corresponding version and choose conda or pip.
- Run the displayed command, e.g., `conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia`.
- Please wait patiently for the installation to complete.

### 5. Verification
- Open a terminal and run python.
- Type `import torch`, then type `print(torch.cuda.is_available())`.
- If it outputs 'True', the installation was successful. Congratulations!
