## 解决wsl下使用新的base之后找不到julia路径问题
### 打开cmd或者PowerShell，进入wsl
```bash
wsl
```
### 进入用户主目录
```bash
cd ~
```

### 使用ls -a命令查看.bashrc
```bash
ls -a
```
### 使用vim 打开bashrc
```bash
vim .bashrc
```
### 找到下面的代码，这个是我电脑的路径，你需要找到你的
```bash
case ":$PATH:" in
    *:/home/lbc/.juliaup/bin:*)
        ;;

    *)
        export PATH=/home/lbc/.juliaup/bin${PATH:+:${PATH}}
        ;;
esac
```
### 将其复制到.zshrc中
### 一定要注意以下几步！！！
### 激活
```bash
source .zshrc
```
### 如果你使用的是vscode，目前我认为是这个原因，你需要进入Windows命令行关闭wsl
```bash
wsl --shutdown
```
### 重新进入wsl后就可以了
