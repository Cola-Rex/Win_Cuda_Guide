# Win_Cuda_Guide

[English](README.md) | 简体中文

现在 IT 最火的话题就是 AI 了，是否想在自己的电脑上尝试一下呢？AI 训练一定离不开 CUDA，所以第一步就是要先配置好本地环境，本项目将一步步带您配置好 Windows 的 CUDA。

## 步骤

### 1. 先查看本机是否已经安装 CUDA
- 直接快捷键 `win+R`，输入 `cmd` 打开终端，输入 `nvcc -V`。
- 如果显示版本信息则说明已经安装 CUDA，请记住 'release' 后面的版本号，直接到第 3 步。
- 如果显示：`'nvcc' 不是内部或外部命令，也不是可运行的程序`，则说明没有安装 CUDA，进行第 2 步。

### 2. 安装 CUDA

#### 2.1 下载 CUDA
- 打开 CUDA 下载地址：[NVIDIA CUDA Downloads](https://developer.nvidia.com/cuda-downloads)。
- 选择 CUDA Toolkit 12.2.1，然后依次点击 `Windows` -> `x86_64` -> `11` -> `exe(local)`。
- 点击 Download 按钮，等待下载完成。

#### 2.2 安装 CUDA
- 打开安装包，选择 '精简'，安装所有组件，并安装最新版本显卡驱动覆盖当前的驱动。
- 注意：可能会出现短暂的黑屏。

#### 2.3 验证安装
- 使用第 1 步的方法快捷键 `win+R`，输入 `cmd` 打开终端，输入 `nvcc -V`，显示版本信息则说明 CUDA 安装成功。

### 3. 安装 cuDNN

#### 3.1 下载 cuDNN
- 访问 cuDNN 官方地址：[NVIDIA cuDNN Downloads](https://developer.nvidia.com/rdp/cudnn-download)。
- 下载对应的 CUDA 版本，例如 CUDA 版本是 12.2，请选择 12.x 版本。
- 解压下载的文件并重命名为 'cudnn'，将文件夹复制到 CUDA 的安装目录下。

#### 3.2 配置环境变量
- 打开 Path，添加以下两行：
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\extras\CUPTI\lib64`
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\cudnn\bin`

### 4. 安装 PyTorch
- 打开 PyTorch 官网：[PyTorch](https://pytorch.org/get-started/locally/)。
- 找到对应的版本号并选择 conda 或 pip。
- 运行显示的命令，例如：`conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia`。
- 请耐心等待安装完成。

### 5. 验证
- 打开终端运行 python。
- 输入 `import torch`，再次输入 `print(torch.cuda.is_available())`。
- 如果输出 `True`，则代表安装成功了，恭喜！
