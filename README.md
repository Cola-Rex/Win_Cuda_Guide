# Win_Cuda_Guide
This project offers a concise, step-by-step guide to simplify the process of installing CUDA on Windows.

现在it最火的话题就是ai了，是否想在自己的电脑上尝试一下呢，ai训练一定离不开cuda，所以第一步就是要先配置好本地环境，本项目将一步步带您配置好windows的cuda

1.先查看本机是否已经安装cuda
直接快捷键 win+R，输入cmd打开终端，输入 nvcc -V，如果显示版本信息则说明已经安装cuda，请记住'ralease'后面的版本号，直接到第3步；
如果显示:'nvcc' 不是内部或外部命令，也不是可运行的程序，则说明没有安装cuda，进行第2步

2. 安装cuda
2.1 打开cuda下载地址：https://developer.nvidia.com/cuda-downloads，因为我是全新的系统，所以我选择了 CUDA Toolkit 12.2.1,
然后以此点击 Windows -> x86_64 -> 11 -> exe(local),接着下面会弹出下载按钮，点击 Download按钮，等待下载完成
2.2 打开安装包，开始进入安装流程，选择'精简'，安装所有组件，并安装最新版本显卡驱动覆盖当前的驱动，然后进入安装阶段，可能会出现短暂的黑屏

2.3 接着我们验证一下是否安装成功，使用第1步的方法 快捷键 win+R，输出cmd打开终端，输入 nvcc -V，显示版本信息则说明cuda安装成功

3. 安装cuDNN
3.1只有cuda还不够，还需要安装 cuDnn，cuDnn 官方地址：https://developer.nvidia.com/rdp/cudnn-download，但是下载cuDNN需要NVIDIA account，所以没有账号的话请先注册再登入，
进到下载页面，请选择cuda版本对应的下载，刚才安装的cuda版本是12.2，所以这里我选择 12.x版本，在弹出的列表中选择:Local Installer for Windows (Zip)
下载得到一个压缩包，解压后打开会可以看一个同名的文件夹，修改这个文件夹名称为 'cudnn'，将这个文件夹复制到cuda的安装目录下(默认是C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2)

3.2 接着，还需要配置环境变量，打开Path，把下面2行添加：
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\extras\CUPTI\lib64
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\cudnn\bin

4.到这里
