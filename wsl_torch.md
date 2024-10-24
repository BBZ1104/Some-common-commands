## 使用wsl进入Linux，进行torch学习

### 进入wsl
```bash
wsl
```

### 进入用户主目录
```bash
cd ~
```

### 创建 文件夹 
```bash
mkdir foldername
```

### 进入文件夹
```bash
cd foldername
```

### 创建虚拟环境 
```bash
python3 -m venv .venv
```

### 进入 vscode
```bash
code .
```

### 安装包
```bash
pip install torch torchvision numpy scipy matplotlib h5py
```

### 检查是否成功
```bash
import torch

# 检查 PyTorch 版本
print(f"PyTorch version: {torch.__version__}")

# 检查 GPU 是否可用
gpu_available = torch.cuda.is_available()
print(f"Is GPU available: {gpu_available}")
```