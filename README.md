# AutoSetup_Ubuntu

> Auto setup basic develop enviconment and utilities on ubuntu>=12.04
>
> 本项目服务于 CLI 环境且只在 CLI 环境下做过测试，在 GUI 中使用可能存在未知问题，欢迎写 issue~

### 项目概况

当你手头有了 5 台以上服务器的时候，你就不得不考虑自动化配置某些环境了。本项目的创作背景就是作者于某互联网公司实习期间，手头一下子有了自己的、学校的、公司的好多台服务器，被环境配置和各种突发问题搞得头要炸了，总算下定决心要把这事妥善解决。

本项目的主旨即实现一个**能在任何裸机上全自动配置好基础设施**的自动化 shell 脚本。

### 功能特性

- 硬 / 软件要求：**有网 / Ubuntu>=12.04**（更多系统支持正在路上）

- 自动配置内容

  - **apt**：切换为对应 Ubuntu 发行版的[清华源](https://mirror.tuna.tsinghua.edu.cn/help/ubuntu/)，自动更新现有包，并安装基础工具。
  - **oh-my-zsh**：自动安装 zsh、[oh-my-zsh](https://ohmyz.sh/)及常用插件、[powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh)主题，并修改配置文件。全部走 gitee 资源下载，减少 github 网络不畅导致的下载安装问题。
  - **python**：在用户目录下安装 anaconda，并切换[anaconda](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/)与[pip](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/)为对应的清华源。如果系统中已经安装了 Anaconda，则第一步安装会跳过，仅进行换源。
  - **nvidia-driver**：安装 PPA 源的系统推荐英伟达显卡驱动（版本可能并非最新，如果想要使用最新驱动请自行修改 install.sh 以跳过这部分，并手动前往[官网](https://www.nvidia.cn/Download/index.aspx?lang=cn)下载安装）

  - 其他
    - 安装可爱的`cowsay`工具，作为提示信息输出
    - 安装`sl`命令，缓解`ls`命令输反之后的尴尬
    - 安装`cmatrix`命令，黑客帝国一键体验

### 使用方式

- 克隆本项目到本地

  ```shell
  git clone https://github.com/Nickydusk/AutoSetup_Ubuntu.git
  cd AutoSetup_Ubuntu
  ```

- 如果国内网速较慢的话可以将上方 github 链接换成 gitee 链接：https://gitee.com/Nickydusk/AutoSetup_Ubuntu.git
- 一键配置所有环境，如果您的用户没有设为免密可能需要输入一次密码

  ```shell
  ./install.sh
  ```

- 仅需要配置部分环境: 根据需要`cd`到相应目录，并执行对应的安装脚本。
