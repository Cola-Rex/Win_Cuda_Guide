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
![cuda_tool](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/79c0b4fa-a71c-4368-9b78-b9236db8434f)
- 选择 CUDA Toolkit 12.2.1，然后依次点击 `Windows` -> `x86_64` -> `11` -> `exe(local)`。
![2](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/840bd49a-dda0-4d2c-a3d0-ea677c322d07)
- 点击 Download 按钮，等待下载完成。

#### 2.2 安装 CUDA
- 打开安装包，选择 '精简'，安装所有组件，并安装最新版本显卡驱动覆盖当前的驱动。
![3](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/f1a3a36e-c47d-49a3-847d-b151db250aad)
- 注意：可能会出现短暂的黑屏。

#### 2.3 验证安装
- 使用第 1 步的方法快捷键 `win+R`，输入 `cmd` 打开终端，输入 `nvcc -V`，显示版本信息则说明 CUDA 安装成功。

### 3. 安装 cuDNN

#### 3.1 下载 cuDNN
- 访问 cuDNN 官方地址：[NVIDIA cuDNN Downloads](https://developer.nvidia.com/rdp/cudnn-download)。
- 下载对应的 CUDA 版本，例如 CUDA 版本是 12.2，请选择 12.x 版本。
 ![4](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/251ebcd9-9f3b-4590-9069-6bc9ff02792c)
- 解压下载的文件并重命名为 'cudnn'，将文件夹复制到 CUDA 的安装目录下。

#### 3.2 配置环境变量
- 打开 Path，添加以下两行：
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\extras\CUPTI\lib64`
  - `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\cudnn\bin`
  ![5](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/3e63f4fe-2a7f-40e9-9677-c6c0666f333a)

### 4. 安装 PyTorch

#### 4.1 官网安装
- 打开 PyTorch 官网：[PyTorch](https://pytorch.org/get-started/locally/)。
- 找到对应的版本号并选择 conda 或 pip。
  ![PyTorch 安装指导](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/b723e808-f744-4f5c-b20c-699988d16795)
- 运行显示的命令，例如：`conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia`。
- 请耐心等待安装完成。

#### 4.2 直接下载whl文件安装
如果因为网络问题导致官网安装失败，则可直接下载whl，地址为：[PyTorch Stable](https://download.pytorch.org/whl/torch_stable.html)。
- 找到你本地环境对应的3个包：torch, torchvision, torchaudio。
- 使用 ctrl+F，根据你的cuda版本号（比如我要找11.8版本），则输入：cu118,会快速跳到对应的下载地址，cpxx的数字代表你的python版本号，比如我的python是3.11，则选择名字带 cp311的链接。
  ![PyTorch .whl 文件](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/8546ae79-e8af-4190-a20b-d8937e091aac)
...
- 3个文件下载完后，使用终端的pip命令安装：
  ```bash
  pip install torch-2.0.0+cu118-cp311-cp311-win_amd64.whl
  pip install cu118/torchaudio-2.0.2+cu118-cp311-cp311-win_amd64.whl
  pip install cu118/torchvision-0.15.2+cu118-cp311-cp311-win_amd64.whl


### 5. 验证
- 打开终端运行 python。
- 输入 `import torch`，再次输入 `print(torch.cuda.is_available())`。
- 如果输出 `True`，则代表安装成功了，恭喜！
![7](https://github.com/Cola-Rex/Win_Cuda_Guide/assets/16102355/6d531ca8-5b96-41cc-bece-ad43280419e6)
