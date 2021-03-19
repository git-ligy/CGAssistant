# CGAssistant

![](img/logo.png)

[英文README](README.md)

CGAssistant 是一个用于游戏CrossGate（中译：魔力宝贝）的工具，可以让你拥有自动化的游戏体验。

目前只支持cg_item_6000（道具服6.0.0）
  
QQ群: 300303705

最新版本的完整包可以从国内镜像 https://gitee.com/hzqst/CGAssistantJS/repository/archive/master.zip 下载（可能需要注册）

Wiki（国内镜像）： https://gitee.com/hzqst/CGAssistantJS/wikis

## 编译前置需求

Visual Studio 2017 with C++

QT 5.12 for msvc2017, win32 (x86)

NodeJS 8.9 windows x86 (可从 https://nodejs.org/dist/v8.9.0/ 或者其他镜像处下载)

node-gyp (建议跟随 https://www.npmjs.com/package/node-gyp 的指示来安装 node-gyp)

## 编译

假设你已经成功安装了所有的前置需求

1. 把 "Qt5.xxx\Tools\QtCreator\bin\" 和 "Qt5.xxx\5.xxx\msvc2017\bin\" 添加到你的系统环境变量 "PATH" 中，就如下图所示的那样。如果不知道如何添加环境变量请自行百度。

![](img/1.png)

2. 如果你的MSVC2017没有安装到默认路径，请修改每一个 "build-*.bat" 批处理文件, 把其中的 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars32.bat" 改成你的 "vcvars32.bat" 所在的位置，就如下图所示的那样。不知道vcvars32.bat在哪建议直接全盘搜索或者重新以默认路径安装MSVC2017。

![](img/2.png)

3. 运行 "init-dependencies.bat", 等待所有子模块下载完成。 (这一步可能需要花费几分钟时间, 具体取决于你的网速，如果速度很慢或者下载出错建议尝试使用proxy)

4. 运行 "build-boost.bat", 等待boost的所有静态库编译完成。 (这一步可能需要花费十几分钟时间，具体取决于你的CPU性能)

5. 运行 "build-CGAHook.bat", 等待 "CGAHook.dll" 生成成功后会自动复制到 "build" 目录下。

5. 运行 "build-nodegyp.bat", 等待 "node_cga.node" 生成成功后会自动复制到 "build/Release" 目录下。

6. 运行 "build-qhttp.bat", 等待 "qhttp.dll" 生成成功后会自动复制到 "build" 目录下。

7. 运行 "build-CGAssiatant.bat", 等待 "CGAssistant.exe" 生成成功后会自动复制到 "build" 目录下。

8. 运行 "windeploy.bat"

如果没有错误发生，那么所有编译好的二进制文件应该都会在 "build" 目录下。