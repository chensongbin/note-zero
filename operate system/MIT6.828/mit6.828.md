#  Background

课程官网 https://pdos.csail.mit.edu/6.828/2018/schedule.html



# 环境搭建

1. ubuntu16.04 amd64
2. 使用定制话的QEMU

```shell
# 1. 获取源代码 
git clone https://github.com/mit-pdos/6.828-qemu.git qemu

# 2. 开发环境 Debian/Ubuntu 16.04，安装依赖包
libsdl1.2-dev, libtool-bin, libglib2.0-dev, libz-dev, and libpixman-1-dev.

# 3. 配置编译参数
# 其中prefix:安装路径 target-list:支持的系统架构
./configure --disable-kvm --disable-werror [--prefix=PFX] [--target-list="i386-softmmu x86_64-softmmu"]

# 4. 编译源代码
make && make install
```



# 前置知识

- 汇编语言

> 1. 汇编->机器语言->某种[指令集架构](https://zh.wikipedia.org/zh/%E6%8C%87%E4%BB%A4%E9%9B%86%E6%9E%B6%E6%A7%8B) Instruct Set Architecture(ISA)
>
> 2. 不同的处理器“家族” - 例如Intel 的IA-32和x86-64、IBM/Freescale Power和ARM处理器家族，有不同的指令集架构。
> 3. x86汇编 就是intel发明的指令集架构所对应的机器语言的助记符
> 4. AT&T 语法、intel语法可以理解为两种不同的语法规则
> 5. intel 语法是intel自己用的，AT&T语法创建的目的是使得汇编语言的语法能够跨平台
> 6. 
>
> 





# Lab1

内核启动

1. 通电 两个寄存器 CS=0x F000, IP= 0x FFF0，这时候CPU处于实模式的状态，通过CS*16+IP 得到第一条指令的内存地址0x FFFF0，这个位置是BIOS代码所在的位置
2. BIOS
(1)CPU执行第一条指令，也就是BIOS的第一条代码，jump
(2)BIOS 设置中断表
(3)初始化各种硬件设备
(4)去加载硬盘第一个扇区的代码到内存，也就是boot load
(5)将CPU控制权交给boot looder，也就是CPU开始执行boot looder的代码
3. boot looder
(1)将CPU从实模式转换为保护模式（支持>1MB的寻址范围）
(2)将内核代码从硬盘读到内存，


环境搭建：
1. ubuntu 16.04
2. sudo apt-get install openssh-server
3. 定制





