---
title: IDEA
date: 2023-07-16 19:29:09
categories:
 - 核心基础
---

# 卸载与安装

## 卸载过程
{% tabs 卸载过程 %}
<!-- tab 步骤一 -->
这里以卸载2022.1.2版本为例说明。在【控制面板】找到【卸载程序】
{% asset_img 04_01.png %}
<!-- endtab -->
<!-- tab 步骤二 -->
右键点击或左键双击IntelliJ IDEA 2022.1.2进行卸载：
{% asset_img 04_02.png %}
<!-- endtab -->
<!-- tab 步骤三 -->
如果需要保留下述数据，就不要打√。如果想彻底删除IDEA所有数据，那就打上√。
{% asset_img 04_03.png %}
<!-- endtab -->
<!-- tab 步骤四 -->
软件卸载完以后，还需要删除其它几个位置的残留：
{% asset_img 04_04.png %}
{% asset_img 04_05.png %}
<!-- endtab -->
{% endtabs %}


---

## 安装过程

{% tabs 安装过程 %}
<!-- tab 步骤一 -->
下载完安装包，双击直接安装
{% asset_img 04_06.png %}
<!-- endtab -->
<!-- tab 步骤二 -->
欢迎安装
{% asset_img 04_07.png %}
<!-- endtab -->
<!-- tab 步骤三 -->
是否删除电脑上低版本的IDEA（如果有，可以选择忽略）
{% asset_img 04_08.png %}
- 如果电脑上有低版本的IDEA，可以选择删除或保留。
- 这里没有卸载旧版本，如果需要卸载，记得勾选下面的保留旧的设置和配置。
<!-- endtab -->
<!-- tab 步骤四 -->
选择安装目录，目录中要避免中文和空格。
{% asset_img 04_09.png %}
<!-- endtab -->
<!-- tab 步骤五 -->
创建桌面快捷图标等
{% asset_img 04_10.png %}
确认是否与.java、.groovy、.kt 格式文件进行关联。这里建议不关联。
<!-- endtab -->
<!-- tab 步骤六 -->
在【开始】菜单新建一个文件夹（这里需要确认文件夹的名称），来管理IDEA的相关内容。
{% asset_img 04_11.png %}
<!-- endtab -->
<!-- tab 步骤七 -->
完成安装
{% asset_img 04_12.png %}
<!-- endtab -->
{% endtabs %}

## 注册
自己百度叭

## 闪退问题
先不写了

# 配置

## jdk相关配置
{% tabs jdk相关配置 %}
<!-- tab 项目的jdk配置 -->
`File-->Project Structure...-->Platform Settings -->SDKs`
{% gallery %}
![](04_13.png)
![](04_14.png)
{% endgallery %}
- 注1：SDKs全称是Software Development Kit ，这里一定是选择JDK的安装根目录，不是JRE的目录。
- 注2：这里还可以从本地添加多个JDK。使用“+”即可实现。
<!-- endtab -->
<!-- tab out目录和编译版本 -->
`File-->Project Structure...-->Project Settings -->Project`
{% gallery %}
![](04_15.png)
{% endgallery %}
<!-- endtab -->
{% endtabs %}

## 详细配置

{% tabs 详细配置 %}
<!-- tab 打开详细配置 -->
**1. 显示工具栏**
{% gallery %}
![](04_16.png)
{% endgallery %}

**2. 选择详细配置菜单或按钮**
{% gallery %}
![](04_17.png)
![](04_18.png)
{% endgallery %}
<!-- endtab -->
<!-- tab 系统设置 -->
**1. 默认启动项目配置**
> 启动IDEA时，默认自动打开上次开发的项目？还是自己选择？
> {% gallery %}
> ![](04_19.png)
> {% endgallery %}
> 如果去掉Reopen projects on startup前面的对勾，每次启动IDEA就会出现如下界面：
> {% gallery %}
> ![](04_20.png)
> {% endgallery %}

**2. 取消自动更新**
> Settings-->Appearance & Behavior->System Settings -> Updates
> 默认都打√了，建议检查IDE更新的√去掉，检查插件更新的√选上。
> {% gallery %}
> ![](04_21.png)
> {% endgallery %}
<!-- endtab -->

<!-- tab 整体主题 -->
**1. 选择主题**

> {% gallery %}
> ![](04_22.png)
> {% endgallery %}

**2. 设置菜单和窗口字体和大小**
> {% gallery %}
> ![](04_23.png)
> {% endgallery %}

**3. 设置IDEA背景图**
> {% gallery %}
> ![](04_24.png)
> {% endgallery %}
> 
> 选择一张合适的图片作为背景，即可。
> 
> {% gallery %}
> ![](04_25.png)
> {% endgallery %}

<!-- endtab -->
<!-- tab 编辑器主题-->
<!-- endtab -->
<!-- tab 显示行号与方法分隔符 -->
<!-- endtab -->
<!-- tab 代码智能提示 -->
<!-- endtab -->
<!-- tab 自动导包 -->
<!-- endtab -->
<!-- tab 项目文件编码 -->
<!-- endtab -->
<!-- tab 控制台字符编码 -->
<!-- endtab -->
<!-- tab 类头的文档注释信息 -->
<!-- endtab -->
<!-- tab 自动编译 -->
<!-- endtab -->
<!-- tab 省电模式(忽略) -->
<!-- endtab -->
<!-- tab 取消双击shift搜索 -->
<!-- endtab -->

{% endtabs %}
