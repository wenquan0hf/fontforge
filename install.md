# 安装 FontForge
  
`FontForge` 是一个自由开源软件，这显然意味着你可以不受限地下载和安装。这也意味着这是一个由社区维护的应用（任何人可以贡献源代码）。  
  
FontForge 支持 Windows，Mac OS 和 GNU/Linux (“Linux”)操作系统。本节的关注在 Linux 机器上安装 FontForge。由于许多 FontForge 的开发者使用 Linux 作为日常开发环境，所以在这个平台上用源代码构建时最简单的方式。  
  
`注意：如果你使用 FontForge 时遇到了问题，或者 FontForge 缺少一个功能，你可以在软件的库打开一个问题。即使你只是刚刚入门，开发者也会去看这个问题。`    
  
## 安装预编译包  
  
在 `FontForge 网站`的主菜单上点击下载按钮将会带你到 FontForge 下载页。页面内列出了三个操作系统下的安装链接。链接页面内都提供了二进制包下载。（译者注：安装预编译包一节按照 FontForge 网站最新结构编写，原文与网站已经脱节）  
  
### 在 Windows 下安装  
  
`FontForge 的 Windows` 版本页面提供了二进制安装包下载，以管理员身份安装，并以管理员身份运行软件即可。  
  
另外，Jeremy Tan 提供了 Windows 下 FontForge 的`最近构建版本`。从 2012 年之前的稳定版安装包可以在`旧的 SourceForge 库`中找到。  

### 在 Mac OS X 下安装  
  
正在建设中的新网站上提供了`安装指南`。  
  
### 在 GNU/Linux 下安装  
  
在你的 Linux 机器上安装 FontForge 最简单的的方式是使用你的分发版的包库。  
  
#### Debian或Ubuntu  

FontForge 包从 2012 年开始就默认包含在 Ubuntu 14.04 中，因此通过 FontForge `Personal Package Archive (PPA)`可以安装最新的包。  
  
检查辅助脚本 `add-apt-repository` 已经安装：  
  
`sudo apt-get install software-properties-common`  
  
添加 FontForge PPA（同时添加认证密钥）：

`sudo add-apt-repository ppa:fontforge/fontforge`

升级软件列表，使得 PPA 包含包：  
  
`sudo apt-get update`  
  
安装 FontForge：  
  
`sudo apt-get install fontforge`

#### Fedora  
  
以 root 用户身份运行下面的 yum 命令可以在你的 Fedora Linux 桌面机上安装 FontForge。完成安装的下载量大概是 10 MiB。  
  
`yum install fontforge`  
  
如果在你的 Fedora 机器上没有编译软件，那么安装 gcc，automake，autoconf 和其他软件后你可能在执行 libtoolize 的 autogen.sh 的时候遇到错误。如果遇到这种情况你需要安装 Fedora 的 libtool-ltdl-devel 包，或者其他 Linux 分发版的类似开发包。  
  
上述 yum install 完成后你可以在你的菜单运行 FontForge，或者 从 konsole 或  gnome-terminal 直接使用 *fontforge* 命令运行。  
  
## 在 Github上编译你自己的版本  

某些情况下，可能你需要使用一个预编译版本中尚不存在的功能，你可能希望从 Github 拿到代码编译自己的版本。Github 是一个源代码托管服务，每个人都可以为软件一部分的开发做出贡献。本节的说明只针对 Ubuntu 14.04。  
  
### 安装准备软件  
  
安装一些包以准备软件的编译

`sudo apt-get install build-essential automake flex bison`  
  
安装 unifont 包使引用字形完整显示。`Unifont` 包含所有 Unicode 编码的字形，如果安装了 FontForge 将使用它。

`sudo apt-get install unifont`  
  
安装其他的必需包：  
  
`sudo apt-get install packaging-dev pkg-config python-dev libpango1.0-dev`    
`libglib2.0-dev libxml2-dev giflib-dbg libjpeg-dev libtiff-dev uthash-dev`

### 构建 libspiro  
  
FontForge 使用 `libspiro` 来简化曲线绘制。  
  
下载代码：

`git clone https://github.com/fontforge/libspiro.git`  
  
按顺序执行下面的命令（也就是说等一个执行完再执行下一个）：  
  
`cd libspiro`  
`autoreconf -i`  
`automake --foreign -Wall`  
`./configure`  
`make`  
`sudo make install`  
`cd ..`

### 构建 libuninameslist  
   
FontForge 使用 `libuninameslist` 来访问每个Unicode编码点的属性数据。

下载代码：

`git clone https://github.com/fontforge/libuninameslist.git`

按顺序执行下面的命令（也就是说等一个执行完再执行下一个）：

`cd libuninameslist`  
`autoreconf -i`  
`automake --foreign`  
`./configure`  
`make`  
`sudo make install`  
`cd ..`  

### 构建 FontForge

下载代码：

`git clone https://github.com/fontforge/fontforge.git`

按顺序执行下面的命令：

`cd fontforge`  
`./bootstrap`  
`./configure`  
`make`  
`sudo make install`  
`cd ..`  

让系统知道新的库：

`sudo ldconfig`

如果你需要单步调试 TrueType 字体提示或者其他高级功能，还需要使用`--with-freetype-source` 配置选项。  

## 调试FontForge软件  

如果在某个阶段你发现 FontForge 的可复现的稳定性问题，你可能需要安装调试信息，才能给 FontForge 团队提供回溯信息以纠正问题。  
  
如果你从 Linux 分发版的包库安装了 FontForge，安装调试信息的方法与从源代码构建时安装调试信息不同。在两种情况下，你都可以使用 *nm* 命令来检查你安装的 FontForge 中调试信息是否已经可以使用。使用“type”命令来找到你的 `Fontforge 二进制文件`。如果你看到下面显示的“no symbols”信息，你需要升级你的安装包来包含调试信息，能够给 FontForge 开发者提供良好的反馈。

`$ type -all fontforge`  
`fontforge is /usr/bin/fontforge`  
`$ nm /usr/bin/fontforge`  
`nm: /usr/bin/fontforge: no symbols`  

当你想要为来自 Fedora 库的 FontForge 添加调试信息的时候，使用下面的命令。需要注意的是如果你还没装好许多依赖的调试信息包，那么可能需要下载几百兆字节的数据。

`debuginfo-install fontforge`
  
更多信息参见`调试`一节。