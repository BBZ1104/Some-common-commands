## 这些好像现在不怎么用了
### 1. 显示已安装的系统
```bash
wsl --list -v
```

### 2. 启动
```bash
wsl -d Ubuntu
```

### 3. 退出
```bash
exit
```

## Julia相关内容，说起来好像有几个星期没写Julia了

## Julia并行与线程

### 设置线程数量,这里的=左右好像不能加空格
```bash
export JULIA_NUM_THREADS=4
```
### 开启julia
```julia
julia
```
### 显示线程数量
```julia
Threads.nthreads()
```