- **注意，作者[WallBreaker2](https://github.com/WallBreaker2)已经删除op源仓库，解散op的群，gitee的也一起删除了，目前github上的源码已经退回到3年前的版本了，原因未知，且行且珍惜吧**
- 如果还有人继续开发，欢迎PR



Overview
===========

operator & open是一个开源插件(类似大漠插件).主要功能有:Windows消息模拟,后台截图，找图,字符识别(OCR)等。使用c++编写，源代码可编译为32/64位dll.op插件提供了两类接口:1. 原生c++接口，可以让c/c++开发者方便调用；2. com接口，支持大多数编译型语言，比如：c#,vb,delphi以及脚本语言python,lua等的调用



![ava](doc/class_struct.svg)



## 功能特色

1. Windows消息模拟，常见的键盘消息和鼠标消息模拟。
2. 支持常见的截图方式，gdi,dx（包括d3d9,d3d10,d3d11),opengl截图，支持常见模拟器（雷电，夜神）的最小化截图
3. 找色找图,支持偏色，支持模糊识别
4. 字符识别(OCR),最大支持255 X 255 超大点阵，支持偏色，支持模糊识别，支持系统字库，兼容大漠字库
5. 插件有32位和64位版本，支持32/64位绑定
6. 项目完全开源,无后门无病毒，可放心使用



#### 已知问题

- **d3d12是不支持的，这种类型的游戏就别问了，除非你帮忙改一下底层的支持**
- 部分鼠键操作，内部是一个合成命令，可能中间延迟过短导致某些游戏无法正常识别，建议分成多个元操作来做。
- 截图-某些游戏可能存在几列像素错位的情况（最后几列像素复制到了前几列）



## Download

包含32位和64位插件，tool工具以及必要的第三方库等文件

这不是基于最新版的，是个稍微老一点的，但是差距不大

[Release](https://github.com/elmagnificogi/op/releases/download/0.4.0.1/op0.4.0.rar)



## 教程

教程请看doc内的chm，类似于大漠的说明（照抄）



## 编译

### 编译环境
* 操作系统: windows 10 64位
* 编译器: vs2019 MSVC2017 32/64
* 工具： cmake 3.0以上
* Windows SDK: 10.0.18362.0 (如果不同，可以在vs项目属性-->常规-->Windows SDk版本手动改一下)
* DirectX SDK: 最新的即可



### 第三方库

* [blackbone](https://github.com/DarthTon/Blackbone.git)(静态编译，链接方式MT)
* [kiero](https://github.com/Rebzzel/kiero.git)(已在源码内，无需安装)
* [minhook](https://github.com/TsudaKageyu/minhook.git)(推荐使用[Vcpkg](https://github.com/Microsoft/vcpkg.git)安装)
* [boost-stacktrace]()(可选，安装使用vcpkg.如果不想安装，注释掉helpfunc.cpp中的宏定义USE_BOOST_STACK_TRACE即可)



## 交流

* 提交issue



## 参考

> [1] [TSPLUG源码,TC company](https://github.com/gaojunxin/TSPlug) 
> [2] [Kiero](https://github.com/Rebzzel/kiero.git)  
