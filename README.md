# OpenHarmony
https://repo.huaweicloud.com/harmonyos/os/2.0/

OpenHarmony介绍

OpenHarmony是HarmonyOS的开源版

由华为捐赠给开放原子开源基金会（OpenAtom Foundation）开源。

第一个开源版本支持在128KB~128MB的设备上运行

OpenHarmony源代码仅支持在Linux环境下编译，所以通过以下方式获取到源码后都需要上传到Linux服务器进行编译。

HarmonyOS技术架构：

 

HarmonyOS的代码以组件的形式开放，开发者可以通过如下其中一种方式获取：

获取方式1：从镜像站点获取

获取方式2：从HPM网站组件式获取

获取方式3：用包管理器命令行获取

获取方式4：从代码仓库获取

 

从镜像站点获取

下载内容

版本信息

下载站点

SHA256校验码

全量代码

1.0

站点

SHA256 校验码

Hi3861解决方案（二进制）

1.0

站点

SHA256 校验码

Hi3518解决方案（二进制）

1.0

站点

SHA256 校验码

Hi3516解决方案（二进制）

1.0

站点

SHA256 校验码

RELEASE-NOTES

1.0

站点

-

点击全量代码解决方案 一栏中的 站点 进行下载：

点击Hi3861解决方案 一栏中的 站点 进行下载：

【在Linux服务器上直接下载：

wget https://repo.huaweicloud.com/harmonyos/os/1.0/code-1.0.tar.gz】

 

上传到服务器：

 

 

解压代码【此处解压全量代码】

$ tar -xvf code-1.0.tar.gz

 

 

从HPM网站组件式获取

获取到的组件上传Linux服务器解压后，通过hpm命令行工具的安装指令 hpm install 进行安装

 

对于刚接触HarmonyOS的新用户，可以在HPM获取推荐的解决方案，以此为基础，增加或裁剪部分组件，快速定制系统

 

获取步骤：

step1、查找合适的解决方案组件包

打开包管理页面HPM，设定搜索的对象为“解决方案”，如下图所示。
自搜索框输入关键字搜索，如"BearPi"。
结果中显示匹配的解决方案，可以进一步根据组件类别等过滤条件(如：适配的开发板，内核）精确筛选。
查找合适的解决方案，点击查看解决方案详情介绍
 

step2、定制解决方案组件包。

仔细阅读解决方案的说明，以了解该解决方案的使用场景、特性、使用方法以及如何进行定制化，如下图所示。
点击「直接下载」，将解决方案下载到本地。
点击「定制组件」，将对解决方案包含的组件进行定制。
 

点击「直接下载」，将解决方案下载到本地

 

将源码上传服务器

 

Linux服务器上需要先安装Node.js和hpm命令行工具，安装步骤如下：

软件环境要求Linux服务器安装12.13.0+ 的Node.js

获取Node.js安装包：https://nodejs.org/dist/v14.15.1/node-v14.15.1-linux-x64.tar.xz

方式一、Windows浏览器获取安装包：

 

上传服务器：

 

 

方式二、

Linux命令行下通过wget获取：

wget https://nodejs.org/dist/v14.15.1/node-v14.15.1-linux-x64.tar.xz

 

解压安装：

$ tar -xvf node-v14.15.1-linux-x64.tar.xz -C ~/

 

使用ln命令设置软链接【软链接若已经存在但版本不对则执行$ sudo rm -r /usr/bin/node】

$ sudo ln -s ~/node-v14.15.1-linux-x64/bin/npm /usr/bin/

$ sudo ln -s ~/node-v14.15.1-linux-x64/bin/node /usr/bin/

 

 

安装hpm命令行工具【华为包管理的命令行工具】：

$ npm install -g @ohos/hpm-cli

 

使用ln命令设置软链接【软链接若已经存在但版本不对则执行$ sudo rm -r /usr/bin/hpm】

$ sudo ln -s ~/node-v14.15.1-linux-x64/bin/hpm /usr/bin/

 

 

通过hpm install命令安装组件：

进入源码目录并解压源码：

$ unzip demo.zip

 

进行组件安装：

进入解压后的demo目录执行 ：

$ hpm install

 

下载安装完成：

 

从HPM网站下载的代码：

 

 

用包管理器命令行获取

适用场景

用户已通过组件式获取的方式获取源码，需要对源码中的某个或某几个组件进行独立升级。

用户已经比较熟悉HarmonyOS系统的开发并且熟练掌握命令行工具的使用。

Linux服务器上需要先安装Node.js和hpm命令行工具，通过hpm install 命令安装组件；

工具安装步骤同上，不再进行安装。

 

示例：

接下来将组件添加到开发项目中，假定要获取的组件名为@ohos/demo，具体操作如下：

 

1.进入开发目录，执行如下命令，采用默认模板创建一个开发项目。

hpm init -t default

 

2.执行如下命令，安装组件@bearpi/bearpi_hm_nano

hpm install @bearpi/bearpi_hm_nano

 

下载后的代码如下，同 【从HPM网站组件式获取】 一样：

 

 

从代码仓库获取

 

适用场景

基于HarmonyOS的稳定分支建立自己的基线，分发下游客户。
已经完成自身软件与HarmonyOS的对接，需要进行HarmonyOS官方认证。
芯片/模组/app通过HarmonyOS官方认证后，贡献代码到HarmonyOS生态。
修复HarmonyOS的问题。
学习HarmonyOS的源码。
 

注册码云gitee账号。

注册码云SSH公钥，请参考码云帮助中心的公钥管理：https://gitee.com/help/articles/4181

安装git客户端并配置用户信息。

git config --global user.name "yourname"

git config --global user.email "your-email-address"

git config --global credential.helper store

安装码云repo工具，可以执行如下命令。

curl https://gitee.com/oschina/repo/raw/fork_flow/repo-py3 > /usr/local/bin/repo

chmod a+x /usr/local/bin/repo

pip install -i https://pypi.tuna.tsinghua.edu.cn/simple requests

操作

方式一（推荐）：通过repo下载

repo init -u https://gitee.com/openharmony/manifest.git -b master --no-repo-verify

repo sync -c

方式二：通过git clone单个代码仓库

进入代码仓库主页，选择需要克隆的代码仓库，执行命令，如：

git clone https://gitee.com/openharmony/manifest.git -b master

【$ git clone https://gitee.com/bearpi/bearpi-hm_nano.git -b master】

 

 

 

HarmonyOS源码的目录及简单说明：

目录名

描述

applications

应用程序样例，包括wifi-iot，camera等

base

基础软件服务子系统集&硬件服务子系统集

build

组件化编译、构建和配置脚本

docs

说明文档

domains

增强软件服务子系统集

drivers

驱动子系统

foundation

系统基础能力子系统集

kernel

内核子系统

prebuilts

编译器及工具链子系统

test

测试子系统

third_party

开源第三方组件

utils

常用的工具集

vendor

厂商提供的软件

build.py

编译脚本文件

 

 

 

参考：HarmonyOS社区、小熊派开源社区

https://device.harmonyos.com/cn/docs/start/get-code/oem_sourcecode_guide-0000001050769927

 

