# Win_Cuda_Guide

 English | [简体中文](README_CN.md)

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
![cuda_tool](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/79c0b4fa-a71c-4368-9b78-b9236db8434f)
- Select `CUDA Toolkit 12.2.1`, then click `Windows` -> `x86_64` -> `11` -> `exe(local)`.
![2](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/840bd49a-dda0-4d2c-a3d0-ea677c322d07)
- Click the Download button and wait for it to complete.

#### 2.2 Install CUDA
- Open the installer, choose 'Express', install all components, and overwrite the current driver with the latest version.
![3](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/f1a3a36e-c47d-49a3-847d-b151db250aad)
- Note: A brief blackout might occur.

#### 2.3 Verify Installation
- Use the method from step 1, press `win+R`, type `cmd`, and enter `nvcc -V`. If the version information is displayed, CUDA was installed successfully.

### 3. Install cuDNN

#### 3.1 Download cuDNN
- Visit cuDNN's official page: [NVIDIA cuDNN Downloads](https://developer.nvidia.com/rdp/cudnn-download).
- Download the corresponding CUDA version, e.g., if your CUDA version is 12.2, choose the 12.x version.
 ![4](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/251ebcd9-9f3b-4590-9069-6bc9ff02792c)
- Unzip the downloaded file, rename the folder to 'cudnn', and copy it to the CUDA installation directory.

#### 3.2 Configure Environment Variables
- Open Path and add the following two lines:
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\extras\CUPTI\lib64`
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\cudnn\bin`
![5](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/3e63f4fe-2a7f-40e9-9677-c6c0666f333a)

### 4. Install PyTorch

#### 4.1 Official Website Installation
- Visit PyTorch's official website: [PyTorch](https://pytorch.org/get-started/locally/).
- Find the corresponding version and choose conda or pip.
![PyTorch Installation Guide](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/b723e808-f744-4f5c-b20c-699988d16795)
- Run the displayed command, e.g., `conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia`.
- Please wait patiently for the installation to complete.

#### 4.2 Direct Installation via .whl Files
If the official website installation fails due to network issues, you can directly download the .whl files from [PyTorch Stable](https://download.pytorch.org/whl/torch_stable.html).

- Find the three packages corresponding to your local environment: torch, torchvision, torchaudio.
- Use `ctrl+F` and search for your CUDA version number (e.g., for version 11.8, enter `cu118`) to quickly jump to the corresponding download links. The numbers in `cpxx` represent your Python version, e.g., if your Python version is 3.11, choose the links containing `cp311`.
![PyTorch .whl Files](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/8546ae79-e8af-4190-a20b-d8937e091aac)
- After downloading the three files, use the terminal's pip command to install:
  ```bash
  pip install torch-2.0.0+cu118-cp311-cp311-win_amd64.whl
  pip install cu118/torchaudio-2.0.2+cu118-cp311-cp311-win_amd64.whl
  pip install cu118/torchvision-0.15.2+cu118-cp311-cp311-win_amd64.whl


### 5. Verification
- Open a terminal and run python.
- Type `import torch`, then type `print(torch.cuda.is_available())`.
- If it outputs `True`, the installation was successful. Congratulations!
![7](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/6d531ca8-5b96-41cc-bece-ad43280419e6)

