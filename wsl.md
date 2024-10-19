## 这些好像现在不怎么用了
### 1. 显示已安装的系统
```bash
wsl --list -v
```
### 2. 启动
'''
### wsl -d Ubuntu
'''
#### 3. 退出
'''
exit
'''
## Julia相关内容，说起来好像有几个星期没写Julia了

## Julia并行与线程

### 设置线程数量
'''
export JULIA_NUM_THREADS=4
'''
### 开启julia
'''
julia
'''
### 显示线程数量
'''
Threads.nthreads()
'''