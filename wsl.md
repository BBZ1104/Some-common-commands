## 1. 显示已安装的系统
```bash
wsl --list -v
```
2. 启动
'''
wsl -d Ubuntu
'''
3. 退出
exit


Julia并行与线程

设置线程数量
export JULIA_NUM_THREADS=4

开启julia
Julia

显示线程数量
Threads.nthreads()
