# 大气层1.12.0整合包V1带特斯拉和极限超频（2026.9.28更新）

大气层1.12.0最高支持23.0.0系统，向下兼容支持21.x、20.x、19.x等低版本系统。

【下载地址】

https://github.com/zghenhen/Atmosphere-AIO/releases

https://codeberg.org/zghenhen/Atmosphere-AIO/releases

2026.9.28更新大气层1.12.0整合包V1，官方大气层atmosphere-1.12.0-master-28d6a2e11，hekate_ctcaer_6.5.4_Nyx_1.9.4中文，增加Warmboot_Extractor.bin（续航lite和oled等mariko型号的提取防止熔断休眠死机补丁wb_xx.bin，自动提取，非续航的erista型号无用）。极限超频的hoc.kip没更新无法支持23.0.0，可以降级22.5.0或者删除或重命名atmosphere/kips文件夹名消除黑屏问题，当普通超频插件使用。

【使用说明】

首先感谢莱莱大佬的大气层整合包的制作教程，和大佬的沟通交流，已经熟练掌握方法，以后更新也会自己动手弄了。如果一直使用我发的大气层整合包，没有另外加插件的，以后更新日志里没有特别说明，就可以一直覆盖升级，我的整合包里只有极限超频插件可自选添加，如果更新以后也多覆盖一次极限超频插件。删除TF卡上的atmosphere/kips/loader.kip，极限超频插件变成普通超频插件。

https://github.com/laila509/hekate_ipl/releases/tag/v6.0.3

我是根据莱莱的大气层整合包作为底包，调整hekate启动大气层的引导顺序，精简些NRO插件，默认开机启动Tesla，极限超频和syspatch，相册改sphaira。大气层真实系统可正常联机，因syspatch所以升级正版系统要切换到机身正版系统，大气层虚拟系统做了序列号和host双防。

ATM-EMU：大气层-虚拟系统（Hekate的Fss0引导，强制只能进虚拟系统，可以用插件软件）

ATM-SYS：大气层-真实系统（Hekate的Fss0引导，强制只能进真实系统，可以用插件软件）

OFW-SYS：机身正版系统（Hekate的Fss0引导，强制只能进真实系统，无破解，又名正版系统）

【更新大气层文件】

1.每次更新TF卡上的大气层文件，不能dbi.nro或者haze.nro来更新TF卡上的大气层破解包文件，建议选择1、重启hekate，在usb工具-SD卡这里usb数据线连win电脑。2、也可以选择关机取出TF卡，插入读卡器接win电脑。

2.从别人的整合包换成我发布的大气层整合包，推荐批处理脚本del-atmosphere-syspatch.bat一键清理TF卡上旧的大气层破解包。或者TF卡保留nintendo，emummc，jksv和switch/checkpoint/saves四个文件夹，删除其余的之后再将压缩包中的文件全选复制到TF卡覆盖。

【进虚拟系统】

1.大气层虚拟系统首先进相册，sphaira那里按X安装桌面的万能前端。以后使用Checkpoint，jksv，dbi，CyberFoil都能稳定不崩溃。

2.特斯拉插件修改为L+Ddown开启菜单，启动在相册Hekate/Deepsea工具箱里找Background services，设ON完毕，然后按B退出，再按Home保存后重启机器。切记：每次调Hekate工具箱后台插件管理务必确保sys-patch要设置ON。

3.虚拟系统玩破解游戏只需要建一个头像账号，可以用linkalho.nro离线绑定任天堂账号。

4.极限超频插件Switch-OC-Suite和普通超频区别是多了loader.kip这个文件（每次系统更新，loader.kip也要适配）和在hekate_ipl.ini中加一条指令kip1=atmosphere/kips/loader.kip。覆盖这2个文件就可变成极限超频，再加上boot2.flag零文件就变成系统自动启动极限超频插件。

非续航型号不必超频，其它型号可以玩玩普通超频，玩极限超频去专门提供教程的网站学习，极限超频弄坏系统或硬件一律归于个人行为。

![Banner](img/banner.png?raw=true)
=====

![License](https://img.shields.io/badge/License-GPLv2-blue.svg)
[![Chat on Discord](https://img.shields.io/badge/Discord-5865f2?logo=discord&logoColor=white)](https://discordapp.com/invite/ZdqEhed)
![Made with Notepad++](img/np++.png?raw=true)

Atmosphère is a work-in-progress customized firmware for the Nintendo Switch.

Components
=====

Atmosphère consists of multiple components, each of which replaces/modifies a different component of the system:

* Fusée: First-stage Loader, responsible for loading and validating stage 2 (custom TrustZone) plus package2 (Kernel/FIRM sysmodules), and patching them as needed. This replaces all functionality normally in Package1loader/NX Bootloader.
* Exosphère: Customized TrustZone, to run a customized Secure Monitor
* Thermosphère: EL2 EmuNAND support, i.e. backing up and using virtualized/redirected NAND images
* Stratosphère: Custom Sysmodule(s), both Rosalina style to extend the kernel/provide new features, and of the loader reimplementation style to hook important system actions
* Troposphère: Application-level Horizon OS patches, used to implement desirable CFW features

Licensing
=====

This software is licensed under the terms of the GPLv2, with exemptions for specific projects noted below.

You can find a copy of the license in the [LICENSE file](LICENSE).

Exemptions:
* [Nintendo](https://github.com/Nintendo) is exempt from GPLv2 licensing and may (at its option) instead license any source code authored for the Atmosphère project under the Zero-Clause BSD license.

Credits
=====

Atmosphère is currently being developed and maintained by __SciresM__, __TuxSH__, __hexkyz__, and __fincs__.<br>
In no particular order, we credit the following for their invaluable contributions:

* __switchbrew__ for the [libnx](https://github.com/switchbrew/libnx) project and the extensive [documentation, research and tool development](http://switchbrew.org) pertaining to the Nintendo Switch.
* __devkitPro__ for the [devkitA64](https://devkitpro.org/) toolchain and libnx support.
* __ReSwitched Team__ for additional [documentation, research and tool development](https://reswitched.github.io/) pertaining to the Nintendo Switch.
* __ChaN__ for the [FatFs](http://elm-chan.org/fsw/ff/00index_e.html) module.
* __Marcus Geelnard__ for the [bcl-1.2.0](https://sourceforge.net/projects/bcl/files/bcl/bcl-1.2.0) library.
* __naehrwert__ and __st4rk__ for the original [hekate](https://github.com/nwert/hekate) project and its hwinit code base.
* __CTCaer__ for the continued [hekate](https://github.com/CTCaer/hekate) project's fork and the [minerva_tc](https://github.com/CTCaer/minerva_tc) project.
* __m4xw__ for development of the [emuMMC](https://github.com/m4xw/emummc) project.
* __Riley__ for suggesting "Atmosphere" as a Horizon OS reimplementation+customization project name.
* __hedgeberg__ for research and hardware testing.
* __lioncash__ for code cleanup and general improvements.
* __jaames__ for designing and providing Atmosphère's graphical resources.
* Everyone who submitted entries for Atmosphère's [splash design contest](https://github.com/Atmosphere-NX/Atmosphere-splashes).
* _All those who actively contribute to the Atmosphère repository._
