# Windows Dynamic-link Library Injector

![C++](docs/badges/C++-20.svg)
[![Windows](docs/badges/Microsoft-Windows.svg)](https://www.microsoft.com/en-ie/windows)
[![License](docs/badges/License-GPL-3.0.svg)](https://www.gnu.org/licenses/gpl-3.0.html)
[![DOI](https://zenodo.org/badge/302512489.svg)](https://zenodo.org/badge/latestdoi/302512489)

## 翻译

- [English](https://github.com/Zhuagenborn/Dll-Injector/blob/main/README.md)
- [简体中文](https://github.com/Zhuagenborn/Dll-Injector/blob/main/README-CN.md)

## 简介

***Dll-Injector***是一款使用*C++20*编写的**Windows动态链接库**注入工具。它可以通过搜索窗口标题将`.dll`文件注入至运行中的进程，或在创建新进程时进行注入。

## 开始

**警告**

> 项目不包含工程配置文件，源代码可以使用*Visual Studio 2022*手动构建。

### 前置条件

该项目需要编译为**Windows 32位**版本。

## 使用

```console
Dll-Injector [-f <proc-path> | <win-title>] <dll-path>
```

**将Dll注入至运行中的进程**

对运行中的进程进行注入时，需要指定目标进程的*窗口标题*和`.dll`文件的*路径*。如果`dll-path`参数是一个相对路径，则其必须相对于`Dll-Injector.exe`文件。

```console
Dll-Injector <win-title> <dll-path>
```

例如，将`dllmain_msg.dll`（假定其位于*Dll-Injector*目录）注入*Windows Calculator*进程：

```console
Dll-Injector Calculator dllmain_msg.dll
```

**创建新进程时进行注入**

若需要在创建新进程时进行注入，必须先设置`-f`选项，然后再指定目标进程和`.dll`文件的*路径*。如果`dll-path`参数是一个相对路径，则其必须相对于进程文件。

```console
Dll-Injector -f <proc-path> <dll-path>
```

## 文档

代码注释采用[*Doxygen*](https://www.doxygen.nl)规范。

类图由[*PlantUML*](https://plantuml.com)创建，详见`docs/class-diagram.plantuml`文件。

![class-diagram](docs/class-diagram.png)

## 许可证

使用*GNU General Public*协议，请参考`LICENSE`文件。

## 引用

```tex
@software{chenzs108_2021_4698332,
  author       = {Chen Zhenshuo and Liu Guowen},
  title        = {Zhuagenborn/Dll-Injector: v1.0.0},
  month        = apr,
  year         = 2021,
  publisher    = {Zenodo},
  version      = {v1.0.0},
  doi          = {10.5281/zenodo.4698332},
  url          = {https://doi.org/10.5281/zenodo.4698332}
}
```

## 作者

- ***Chen Zhenshuo***

  > ***GitHub***: https://github.com/czs108
  >
  > ***E-Mail***: chenzs108@outlook.com
  >
  > ***微信***: chenzs108

- ***Liu Guowen***

  > ***GitHub***: https://github.com/lgw1995
  >
  > ***E-Mail***: liu.guowen@outlook.com