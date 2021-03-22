# 鸿蒙OS学习

## 用到链接

~~[安装带有开发工具的虚拟机](https://blog.csdn.net/Touxon/article/details/111465883)：~~不好用，还是参照B站视频的做法比较方便

[烧录代码](https://blog.csdn.net/qq_42754570/article/details/112144100)

[学习顺序](https://huaweicloud.blog.csdn.net/article/details/102520428)

[Gitee仓库](https://gitee.com/bearpi/bearpi-hm_nano)

## 视频教程

<div style="position: relative; padding: 30% 45%;">
<iframe style="position: absolute; width: 100%; height: 100%; left: 0; top: 0;" src="////player.bilibili.com/player.html?aid=245535732&bvid=BV1tv411b7SA&cid=270679606&page=1&as_wide=1&high_quality=1&danmaku=0" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
</div>

# 2021.03.10

上午继续参照B站视频进行了安装，发现这个驱动安装失败了，可能是因为没有板子吧。

![image-20210310090327848](https://gitee.com/yuyang201907/Imags/raw/master/img/image-20210310090327848.png)

发现卡在虚拟机和宿主机之间建立联系上，虚拟机能ping通宿主机，但宿主机ping不通虚拟机。

试了一下，防火墙也是关闭的，应该还是不在同一网段的问题。

这个解答是正解，因为主机如果连接在校园网上的话，IP应该是172开头，怎么可能会和虚拟机在一个网段？

所以只要能讲VMnet8改成和虚拟机同网段即可。[链接](https://blog.csdn.net/qqxyy99/article/details/80864862)

**感觉在虚拟机内改IP地址应该也可以。**

- 源码两种方式获取，一种是gitclone，另一种是华为HPM获取。
- 在本地通过VScode进行代码编译，**直接打开Z盘的文件夹进行代码修改即可，**通过Hiburn烧录到开发板中。
- 使用MobaXterm中的串口工具在虚拟机中进行串口调试。
- 编译命令 python build.py BearPi-HM_Nano

通过RaiDrive进行权限设置，去掉只读选项之后，可以同时进行进行读写。

