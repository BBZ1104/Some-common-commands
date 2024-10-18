---
title: linux
date: 2024-05-29 23:05:25
tags: linux
---
---
title: linux常用命令 & git常用指令
date: 2024-05-10 23:54:53
tags: linux & git
category: linux
---
# 一些linux常用命令
(1) ctrl c: 取消命令，并且换行  
(2) ctrl u: 清空本行命令  
(3) tab键：可以补全命令和文件名，如果补全不了快速按两下tab键，可以显示备选选项  
(4) ls: 列出当前目录下所有文件，蓝色的是文件夹，白色的是普通文件，绿色的是可执行文件  
(5) pwd: 显示当前路径  
(6) cd XXX: 进入XXX目录下,   
cd .. 返回上层目录   
cd /：切换到系统根目录   
cd ~：切换到用户主目录   
cd -： 切换到上一个操作所在目录  
(7) cp XXX YYY: 将XXX文件复制成YYY，XXX和YYY可以是一个路径，比如../dir_c/a.txt，表示上层目录下的dir_c文件夹下的文件a.txt  
(8) mkdir XXX: 创建目录XXX  
(9) rm XXX: 删除普通文件;  rm XXX -r: 删除文件夹  
(10) mv XXX YYY: 将XXX文件移动到YYY，和cp命令一样，XXX和YYY可以是一个路径；重命名也是用这个命令  
(11) touch XXX: 创建一个文件  
(12) cat XXX: 展示文件XXX中的内容  
(13) 复制文本 Ctrl + insert  
(14) 粘贴文本 Shift + insert 

# tmux 的使用
tmux 是终端复用工具，支持在屏幕上同时显示多个终端，允许断开Terminal连接后，继续运行进程。

常用命令  
(1)``` ctrl + b + % ``` 左右分屏  
(2)``` ctrl + b + " ``` 上下分屏  
(3)``` ctrl + b + d ``` 挂起终端  
(4) 

# vim的使用
vim是常用的文本编辑器，使用vim编辑时，不用频繁的移动鼠标。  
vim有三种模式,分别是一般模式、编辑模式和命令模式

### 切换模式命令    
（1） ```i```  进入编辑模式  
（2） ```esc```退出编辑模式  
（3） 按```?```、```/```、```?```三者中的任意一个进入命令模式  

### 一般模式下常用的操作  
（1） ```h```,```j```,```k```,```l```分别表示光标向左、下、上、右移动。  
（2） 先按下数字n，再按空格键 光标会在该行内向右移动n个字符。  
（3） 按```0```移动到本行开头，按```$```或```end```移动到本行结尾  
（4） ```G```使光标移动到最后一行，```gg```移动到光标第一行，```nG```或```:n```表示移动到第n行  
（5） 先按下数字n，再按```Enter```键，表示光标向下移动n行。  
（6）按下```/word```表示在光标以上寻找第一个值为```word```的字符串，按下```?word```表示在光标以下寻找第一个值为```word```的字符串，```n```表示重复前一个查找操作，```N```表示反向重复上一个查找操作。  
（7）可以对以上命令进行组合，比如```:n1,n2s/word1/word2/g```其中n1,n2为数字，这串指令表示在n1行和n2行之间查找```word1```并替换为```word2```，类似的```:1,$s/word1/word2/g```表示全文查找```word1```并替换为```word2```，```:1,$s/word1/word2/gc```与上面的命令相仿，不同点在于末尾的```c```表示替换时需要确认。





# git 基本知识及指令
git 是一个伟大的版本控制工具，


# shell介绍


# Makefile简介

### 简介
Makefile 用于帮助决定一个大型程序的哪些部分需要重新编译。makefile通过检测文件的依赖项是否发生更改来决定该文件是否需要重新编译。
除了make，还有一些比较流行的构建系统，如CMake等。其他编译型语言往往有自己的构建工具，例如java的Ant、Maven、Gradle，Golang的go build工具以及rust的Cargo工具，像 Python、Ruby 和 JavaScript 这样的解释型语言是不需要类似 Makefiles 的东西的。Makefiles 的目标是基于哪些文件发生了变化来编译需要被编译的一切文件。但是，当解释型语言的文件发生了变化，是不需要重新编译的，程序运行时会使用最新版的源码文件。
从一个简单的例子开始
```makefile
hello:
    echo "Hello World"
```
然后在终端中运行make，结果如下
```shell
$ make 
echo "Hello World"
Hello World
```
makefile 文件有一系列 规则（Rules） 组成。每一个规则类似
```makefile
targets: prerequisites
    command
    command
    command
```
(1)```targets```指的是这条规则指定的文件名称，多个文件名以空格隔开   

(2)```command```通常是一系列生成```targets``` 的步骤，他们需要一个```Tab```键开头    

(3)```prerequisites```也是文件名称，多个文件名以空格分隔。在运行生成目标(targets)的```commands```之前，要确保这些文件是存在的。他们也被称为依赖。  
 
### 一个简单的例子

```shell
blah: blah.o
    cc blah.o -o blah #Runs third

blah.o: blah.c
    cc -c blah.c -o blah.o # Runs second

blah.c: 
    echo "int main() { return 0;}" > blah.c # Runs first 
    # 将"int main() { return 0;}" 重定向到文件 blah.c里
```
这个```makefile```按以下步骤执行   
- 首先```blah```给```make```提供了构建目标的名称，所以他会在makefile中优先被```make```程序搜索  

- 构建系统发现```blah```依  赖```blah.o```，所以```make```开始搜索```blah.o```这个目标

- ```blah.o```又依赖```blah.c```，所以```make```又开始搜索```blah.o```这个目标  

- ```blah.c```没有依赖，直接运行```echo```命令  

- 接着运行```cc -c ```命令，因为```blah.o```的依赖的所有  ```commands```都执行完了

- 同理，接着运行顶部的```cc```命令

- 就这样，一个编译好的c程序```blah``` 就诞生了








