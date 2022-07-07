<h1 style="color:skyblue;text-align:center">---Linux学习笔记---</h1>



----



# Linux特点



* 免费
* 开源
* Linux 与 Unix 系统兼容，该系统的构建采用了一些与 UNIX 操作系统相同的技术，具备 Unix 几乎所有的优秀特性
* 和其他操作系统相比，Linux 更容易安装，且不会收到任何商业化版本的制约
* Linux 让开展各种实际有用且具有创造性的事情成为可能
* Linux 提供了复杂的软件包管理系统，可以放心地安装和维护每一个在线资源库中的软件应用





# UNIX与Linux的关系和区别

关系：

UNIX 是 Linux 的“父亲”



区别：

* UNIX 系统大多是与硬件配套的，也就是说，大多数 UNIX 系统如 AIX、HP-UX 等是无法安装在 x86 服务器和个人计算机上的，而 Linux 则可以运行在多种硬件平台上
* UNIX 是商业软件，而 Linux 是开源软件，是免费、公开源代码的





# UNIX/Linux系统结构

UNIX/Linux 系统可以粗糙地抽象为 3 个层次：

底层是 UNIX/Linux 操作系统，即系统内核（Kernel）；中间层是 Shell 层，即命令解释层；高层则是应用层。



**内核层：**

内核层是 UNIX/Linux 系统的核心和基础，它直接附着在硬件平台之上，控制和管理系统内各种资源（硬件资源和软件资源），有效地组织进程的运行，从而扩展硬件的功能，提高资源的利用效率，为用户提供方便、高效、安全、可靠的应用环境。

**Shell层：**

Shell 层是与用户直接交互的界面。用户可以在提示符下输入命令行，由 Shell 解释执行并输出相应结果或者有关信息，所以我们也把 Shell 称作命令解释器，利用系统提供的丰富命令可以快捷而简便地完成许多工作

**应用层：**

应用层提供基于 X Window 协议的图形环境。X Window 协议定义了一个系统所必须具备的功能（就如同 TCP/IP 是一个协议，定义软件所应具备的功能），可系统能满足此协议及符合 X 协会其他的规范，便可称为 X Window



X Window 与微软的 Windows 图形环境有很大的区别：

- UNIX/Linux 系统与 X Window 没有必然捆绑的关系，也就是说，UNIX/Linux 可以安装 X Window，也可以不安装；而微软的 Windows 图形环境与内核捆绑密切。
- UNIX/Linux 系统不依赖图形环境，依然可以通过命令行完成 100% 的功能，而且因为不使用图形环境还会节省大量的系统资源。



# 类UNIX系统



类Unix系统（英文：Unix-like）是指继承UNIX的设计风格演变出来的系统（比如GNU/Linux、FreeBSD、OpenBSD、SUN公司的Solaris、Minix、QNX等），这些操作系统虽然有的是自由软件，有的是商业软件，但都相当程度地继承了原始UNIX的特性，有许多相似处，并且都在一定程度上遵守POSIX规范，但是它们却并不含有UNIX的源代码。UNIX的源代码为SCO公司所有，属于商业软件，UNIX的商标权和UNIX标准认定属于OPENGROUP所有。由于UNIX标准认定价格昂贵，所以唯一获得UNIX标准认定的为苹果的MACOS系统。





# Linux系统的优点

## 大量的可用软件及免费软件

Linux 系统上有着大量的可用软件，且绝大多数是免费的，比如声名赫赫的 Apache、Samba、[PHP](http://m.biancheng.net/php/)、[MySQL](http://m.biancheng.net/mysql/) 等，构建成本低廉，是 Linux 被众多企业青睐的原因之一。当然，这和 Linux 出色的性能是分不开的，否则，节约成本就没有任何意义。



## 良好的可移植性及灵活性

Linux 系统有良好的可移植性，它几乎支持所有的 CPU 平台，这使得它便于裁剪和定制。我们可以把 Linux 放在 U 盘、光盘等存储介质中，也可以在嵌入式领域广泛应用。



## 优良的稳定性和安全性

Linux 开放源代码，将所有代码放在网上，全世界的程序员都看得到，有什么缺陷和漏洞，很快就会被发现，从而成就了它的稳定性和安全注。



## 支持几乎所有的网络协议及开发语言

UNIX 系统是与 C 语言、TCP/IP 协议一同发展起来的，而 Linux 是 UNIX 的一种，C 语言又衍生出了现今主流的语言 PHP、Java、C++ 等。所以，Linux 对网络协议和开发语言的支持很好





# 应用领域

* 网站服务器
* 嵌入式应用





# 远程管理协议



- RDP（remote desktop protocol）协议：远程桌面协议，大部分 Windows 系统都默认支持此协议，Windows 系统中的远程桌面管理就基于该协议。
- RFB（Remote FrameBuffer）协议：图形化远程管理协议，VNC 远程管理工具就基于此协议。
- Telnet：命令行界面远程管理协议，几乎所有的操作系统都默认支持此协议。此协议的特点是，在进行数据传送时使用明文传输的方式，也就是不对数据进行加密。
- SSH（Secure Shell）协议：命令行界面远程管理协议，几乎所有操作系统都默认支持此协议。和 Telnet 不同，该协议在数据传输时会对数据进行加密并压缩，因此使用此协议传输数据既安全速度又快。



RDP 协议和 RFB 协议都允许用户通过图形用户界面访问远程系统，但 RFB 协议倾向于传输图像，RDP 协议倾向于传输指令：

- RFB 协议会在服务器端将窗口在显存中画好，然后将图像传给客户端，客户端只需要将得到的图像解码显示即可；
- RDP 会将画图的工作交给客户端，服务器端需要根据客户端的显示能力做适当的调整。

完成相同的操作，使用 RFB 协议传输的数据量会比 RDP 大，而 RDP 对客户端的要求比 RFB 更苛刻，RFB 适用于瘦客户端，而 RDP 适用于低速网络



## 瘦客户端

瘦客户端指的是最大可能减轻客户端的负担，多数工作由服务器端完成；胖客户端则相反。





# 注意事项

* **Linux 严格区分大小写**
* **Windows 下的程序不能直接在 Linux 中使用**
* **Linux 不靠扩展名区分文件类型**
  * Linux 系统通过权限位标识来确定文件类型
* **Linux 中所有内容（包括硬件设备）以文件形式保存，Linux一切皆文件**
* **Linux中所有存储设备都必须在挂载之后才能使用**





# 目录结构



使用 Linux 时，通过命令行输入 `ls -l /` 可以看到，在 Linux 根目录（/）下包含很多的子目录（称为一级目录），例如 bin、boot、dev 等。同时，各一级目录下还含有很多子目录（称为二级目录），比如 /bin/bash、/bin/ed 等。Linux 文件系统目录总体呈现树形结构，/ 根目录就相当于树根



FHS（Filesystem Hierarchy Standard），文件系统层次化标准，该标准规定了 Linux 系统中所有一级目录以及部分二级目录（/usr 和 /var）的用途。发布此标准的主要目的就是为了让用户清楚地了解每个目录应该存放什么类型的文件。



## Linux 根目录

位置：/

* 所有目录都是由根目录衍生出来的
* 根目录与系统的开机、修复、还原密切相关



| 一级目录 |                         功能（作用）                         |
| :------: | :----------------------------------------------------------: |
|  /bin/   | 存放系统命令，普通用户和 root 都可以执行。放在 /bin 下的命令在单用户模式下也可以执行 |
|  /boot/  | 系统启动目录，保存与系统启动相关的文件，如内核文件和启动引导程序（grub）文件等 |
|  /dev/   |                       设备文件保存位置                       |
|  /etc/   | 配置文件保存位置。系统内所有采用默认安装方式（rpm 安装）的服务配置文件全部保存在此目录中，如用户信息、服务的启动脚本、常用服务的配置文件等 |
|  /home/  | 普通用户的主目录（也称为家目录）。在创建用户时，每个用户要有一个默认登录和保存自己数据的位置，就是用户的主目录，所有普通用户的主目录是在 /home/ 下建立一个和用户名相同的目录。如用户 liming 的主目录就是 /home/liming |
|  /lib/   |                   系统调用的函数库保存位置                   |
| /media/  |       挂载目录。系统建议用来挂载媒体设备，如软盘和光盘       |
|  /mnt/   | 挂载目录。早期 Linux 中只有这一个挂载目录，并没有细分。系统建议这个目录用来挂载额外的设备，如 U 盘、移动硬盘和其他操作系统的分区 |
|  /misc/  | 挂载目录。系统建议用来挂载 NFS 服务的共享目录。虽然系统准备了三个默认挂载目录 /media/、/mnt/、/misc/，但是到底在哪个目录中挂载什么设备可以由管理员自己决定。例如，笔者在接触 Linux 的时候，默认挂载目录只有 /mnt/，所以养成了在 /mnt/ 下建立不同目录挂载不同设备的习惯，如 /mnt/cdrom/ 挂载光盘、/mnt/usb/ 挂载 U 盘，都是可以的 |
|  /opt/   | 第三方安装的软件保存位置。这个目录是放置和安装其他软件的位置，手工安装的源码包软件都可以安装到这个目录中。 |
|  /root/  | root 的主目录。普通用户主目录在 /home/ 下，root 主目录直接在“/”下 |
|  /sbin/  | 保存与系统环境设置相关的命令，只有 root 可以使用这些命令进行系统环境设置，但也有些命令可以允许普通用户查看 |
|  /srv/   | 服务数据目录。一些系统服务启动之后，可以在这个目录中保存所需要的数据 |
|  /tmp/   | 临时目录。系统存放临时文件的目录，在该目录下，所有用户都可以访问和写入。建议此目录中不能保存重要数据，最好每次开机都把该目录清空 |



|   一级目录   |                         功能（作用）                         |
| :----------: | :----------------------------------------------------------: |
| /lost+found/ | 当系统意外崩溃或意外关机时，产生的一些文件碎片会存放在这里。在系统启动的过程中，fsck 工具会检查这里，并修复已经损坏的文件系统。这个目录只在每个分区中出现，例如，/lost+found 就是根分区的备份恢复目录，/boot/lost+found 就是 /boot 分区的备份恢复目录 |
|    /proc/    | 虚拟文件系统。该目录中的数据并不保存在硬盘上，而是保存到内存中。主要保存系统的内核、进程、外部设备状态和网络状态等。如 /proc/cpuinfo 是保存 CPU 信息的，/proc/devices 是保存设备驱动的列表的，/proc/filesystems 是保存文件系统列表的，/proc/net 是保存网络协议信息的 |
|    /sys/     | 虚拟文件系统。和 /proc/ 目录相似，该目录中的数据都保存在内存中，主要保存与内核相关的信息 |



```sh
PS C:\Users\mao\Desktop> docker images
REPOSITORY            TAG       IMAGE ID       CREATED        SIZE
docker_compose_boot   1.0       aaef57816a3b   12 days ago    588MB
java17                1.0       282982c69086   13 days ago    489MB
grafana/grafana       latest    c4b778290339   2 weeks ago    292MB
tomcat                latest    c795915cb678   4 weeks ago    680MB
redis                 latest    53aa81e8adfa   4 weeks ago    117MB
mysql                 latest    65b636d5542b   4 weeks ago    524MB
ubuntu                latest    d2e4e1f51132   2 months ago   77.8MB
google/cadvisor       latest    eb1210707573   3 years ago    69.6MB
tutum/influxdb        0.9       7aa2a38f2ef6   6 years ago    275MB
PS C:\Users\mao\Desktop> docker run  --name ubuntu -it ubuntu
root@e331c5c18f3f:/# pwd
/
root@e331c5c18f3f:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@e331c5c18f3f:/#
```



```sh
root@e331c5c18f3f:/# ls -l
total 48
lrwxrwxrwx   1 root root    7 Apr 28 12:01 bin -> usr/bin
drwxr-xr-x   2 root root 4096 Apr 18 10:28 boot
drwxr-xr-x   5 root root  360 Jul  1 11:39 dev
drwxr-xr-x   1 root root 4096 Jul  1 11:39 etc
drwxr-xr-x   2 root root 4096 Apr 18 10:28 home
lrwxrwxrwx   1 root root    7 Apr 28 12:01 lib -> usr/lib
lrwxrwxrwx   1 root root    9 Apr 28 12:01 lib32 -> usr/lib32
lrwxrwxrwx   1 root root    9 Apr 28 12:01 lib64 -> usr/lib64
lrwxrwxrwx   1 root root   10 Apr 28 12:01 libx32 -> usr/libx32
drwxr-xr-x   2 root root 4096 Apr 28 12:01 media
drwxr-xr-x   2 root root 4096 Apr 28 12:01 mnt
drwxr-xr-x   2 root root 4096 Apr 28 12:01 opt
dr-xr-xr-x 310 root root    0 Jul  1 11:39 proc
drwx------   2 root root 4096 Apr 28 12:04 root
drwxr-xr-x   5 root root 4096 Apr 28 12:04 run
lrwxrwxrwx   1 root root    8 Apr 28 12:01 sbin -> usr/sbin
drwxr-xr-x   2 root root 4096 Apr 28 12:01 srv
dr-xr-xr-x  11 root root    0 Jul  1 11:39 sys
drwxrwxrwt   2 root root 4096 Apr 28 12:04 tmp
drwxr-xr-x  14 root root 4096 Apr 28 12:01 usr
drwxr-xr-x  11 root root 4096 Apr 28 12:04 var
root@e331c5c18f3f:/#
```





## /usr目录

usr（注意不是 user），全称为 Unix Software Resource，此目录用于存储系统软件资源。FHS 建议所有开发者，应把软件产品的数据合理的放置在 /usr 目录下的各子目录中，而不是为他们的产品创建单独的目录。

Linux 系统中，所有系统默认的软件都存储在 /usr 目录下，/usr 目录类似 Windows 系统中 C:\Windows\ + C:\Program files\ 两个目录的综合体。



|    子目录    |                         功能（作用）                         |
| :----------: | :----------------------------------------------------------: |
|  /usr/bin/   | 存放系统命令，普通用户和超级用户都可以执行。这些命令和系统启动无关，在单用户模式下不能执行 |
|  /usr/sbin/  | 存放根文件系统不必要的系统管理命令，如多数服务程序，只有 root 可以使用。 |
|  /usr/lib/   |                 应用程序调用的函数库保存位置                 |
| /usr/XllR6/  |                     图形界面系统保存位置                     |
| /usr/local/  | 手工安装的软件保存位置。我们一般建议源码包软件安装在这个位置 |
| /usr/share/  |  应用程序的资源文件保存位置，如帮助文档、说明文档和字体目录  |
|  /usr/src/   | 源码包保存位置。我们手工下载的源码包和内核源码包都可以保存到这里。 |
| /usr/include |               C/C++等编程语言头文件的放置目录                |



```sh
root@e331c5c18f3f:/# cd usr
root@e331c5c18f3f:/usr# pwd
/usr
root@e331c5c18f3f:/usr# ls
bin  games  include  lib  lib32  lib64  libexec  libx32  local  sbin  share  src
root@e331c5c18f3f:/usr# ls -l
total 56
drwxr-xr-x  2 root root 12288 Apr 28 12:04 bin
drwxr-xr-x  2 root root  4096 Apr 18 10:28 games
drwxr-xr-x  2 root root  4096 Apr 18 10:28 include
drwxr-xr-x 15 root root  4096 Apr 28 12:04 lib
drwxr-xr-x  2 root root  4096 Apr 28 12:01 lib32
drwxr-xr-x  2 root root  4096 Apr 28 12:02 lib64
drwxr-xr-x  4 root root  4096 Apr 28 12:01 libexec
drwxr-xr-x  2 root root  4096 Apr 28 12:01 libx32
drwxr-xr-x 10 root root  4096 Apr 28 12:01 local
drwxr-xr-x  2 root root  4096 Apr 28 12:04 sbin
drwxr-xr-x 33 root root  4096 Apr 28 12:01 share
drwxr-xr-x  2 root root  4096 Apr 18 10:28 src
root@e331c5c18f3f:/usr#
```





## /var 目录

/var 目录用于存储动态数据，例如缓存、日志文件、软件运行过程中产生的文件等



|    /var子目录     |                         功能（作用）                         |
| :---------------: | :----------------------------------------------------------: |
|     /var/lib/     | 程序运行中需要调用或改变的数据保存位置。如MySql的数据库保存在 /var/lib/mysql/ 目录中 |
|     /var/log/     | 登陆文件放置的目录，其中所包含比较重要的文件如 /var/log/messages, /var/log/wtmp 等。 |
|     /var/run/     |     一些服务和程序运行后，它们的 PID（进程 ID）保存位置      |
|    /var/spool/    | 里面主要都是一些临时存放，随时会被用户所调用的数据，例如 /var/spool/mail/ 存放新收到的邮件，/var/spool/cron/ 存放系统定时任务。 |
|     /var/www/     |               RPM 包安装的 Apache 的网页主目录               |
| /var/nis和/var/yp | NIS 服务机制所使用的目录，nis 主要记录所有网络中每一个 client 的连接信息；yp 是 linux 的 nis 服务的日志文件存放的目录 |
|     /var/tmp      | 一些应用程序在安装或执行时，需要在重启后使用的某些文件，此目录能将该类文件暂时存放起来，完成后再行删除 |



```sh
root@e331c5c18f3f:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@e331c5c18f3f:/# cd var
root@e331c5c18f3f:/var# ls
backups  cache  lib  local  lock  log  mail  opt  run  spool  tmp
root@e331c5c18f3f:/var# ls -l
total 36
drwxr-xr-x 2 root root  4096 Apr 18 10:28 backups
drwxr-xr-x 5 root root  4096 Apr 28 12:04 cache
drwxr-xr-x 7 root root  4096 Apr 28 12:02 lib
drwxrwsr-x 2 root staff 4096 Apr 18 10:28 local
lrwxrwxrwx 1 root root     9 Apr 28 12:01 lock -> /run/lock
drwxr-xr-x 3 root root  4096 Apr 28 12:01 log
drwxrwsr-x 2 root mail  4096 Apr 28 12:01 mail
drwxr-xr-x 2 root root  4096 Apr 28 12:01 opt
lrwxrwxrwx 1 root root     4 Apr 28 12:01 run -> /run
drwxr-xr-x 2 root root  4096 Apr 28 12:01 spool
drwxrwxrwt 2 root root  4096 Apr 28 12:04 tmp
root@e331c5c18f3f:/var#
```





# 一切皆文件

Linux 中所有内容都是以文件的形式保存和管理的，即一切皆文件，普通文件是文件，目录（Windows 下称为文件夹）是文件，硬件设备（键盘、监视器、硬盘、打印机）是文件，就连套接字（socket）、网络通信等资源也都是文件。



## 普通文件

类似 mp4、pdf、html 这样，可直接拿来使用的文件都属于普通文件，Linux 用户根据访问权限的不同可以对这些文件进行查看、删除以及更改操作



## 目录文件

Linux 系统中，目录文件包含了此目录中各个文件的文件名以及指向这些文件的指针，打开目录等同于打开目录文件，只要你有权限，可以随意访问目录中的任何文件



## 字符设备文件和块设备文件

这些文件通常隐藏在 /dev/ 目录下，当进行设备读取或外设交互时才会被使用。

例如，磁盘光驱属于块设备文件，串口设备则属于字符设备文件。

Linux 系统中的所有设备，要么是块设备文件，要么是字符设备文件。



## 套接字文件

套接字文件一般隐藏在 /var/run/ 目录下，用于进程间的网络通信



## 符号链接文件（symbolic link）

类似与 Windows 中的快捷方式，是指向另一文件的简介指针（也就是软链接）



## 管道文件（pipe）

主要用于进程间通信。例如，使用 mkfifo 命令创建一个 FIFO 文件，与此同时，启用进程 A 从 FIFO文件读数据，启用进程 B 从 FIFO文件中写数据，随写随读。



## 一切皆文件的利弊

Linux 系统没有 C 盘、D 盘、E 盘那么多的盘符，只有一个根目录（/），所有的文件（资源）都存储在以根目录（/）为树根的树形目录结构中。

**利：**

开发者仅需要使用一套 API 和开发工具即可调取 Linux 系统中绝大部分的资源

几乎所有读（读文件，读系统状态，读 socket，读 PIPE）的操作都可以用 read 函数来进行；几乎所有更改（更改文件，更改系统参数，写 socket，写 PIPE）的操作都可以用 write 函数来进行

**弊：**

使用任何硬件设备都必须与根目录下某一目录执行挂载操作，否则无法使用

Linux 具有一个以根目录为树根的文件目录结构，每个设备也同样如此，它们是相互独立的。如果我们想通过 Linux 上的根目录找到设备文件的目录结构，就必须将这两个文件系统目录合二为一，这就是挂载的真正含义。





# 挂载

当在 Linux 系统中使用这些硬件设备时，只有将Linux本身的文件目录与硬件设备的文件目录合二为一，硬件设备才能为我们所用。合二为一的过程称为“挂载”

如果不挂载，通过Linux系统中的图形界面系统可以查看找到硬件设备，但命令行方式无法找到。

**挂载，指的就是将设备文件中的顶级目录连接到 Linux 根目录下的某一目录（最好是空目录），访问此目录就等同于访问设备文件。**

并不是根目录下任何一个目录都可以作为挂载点，由于挂载操作会使得原有目录中文件被隐藏，因此根目录以及系统原有目录都不要作为挂载点，会造成系统异常甚至崩溃，挂载点最好是新建的空目录



在根目录下新建一个目录 /sdb-u，通过挂载命令将 U 盘文件系统挂载到此目录。U 盘文件系统已经成为 Linux 文件系统目录的一部分，此时访问 /sdb-u/ 就等同于访问 U 盘



# 文件和目录管理



## 绝对路径和相对路径

根目录“/”开始的路径为绝对路径

以"./"开始的路径为相对路径



* 一个点(.)：表示相对路径
* 两个点(..)：表示相对路径的父目录



```sh
root@e331c5c18f3f:/var# pwd
/var
root@e331c5c18f3f:/var# cd .
root@e331c5c18f3f:/var# pwd
/var
root@e331c5c18f3f:/var# cd ..
root@e331c5c18f3f:/# pwd
/
root@e331c5c18f3f:/#
```





## 文件（目录）命名规则

命名规则如下：

* 除了字符“/”之外，所有的字符都可以使用，但是要注意，在目录名或文件名中，使用某些特殊字符并不是明智之举。例如，在命名时应避免使用 <、>、？、* 和非打印字符等。如果一个文件名中包含了特殊字符，例如空格，那么在访问这个文件时就需要使用引号将文件名括起来。

* 目录名或文件名的长度不能超过 255 个字符。

* 目录名或文件名是区分大小写的。是互不相同的目录名或文件名，但使用字符大小写来区分不同的文件或目录，也是不明智的。

* 与 Windows 操作系统不同，文件的扩展名对 Linux 操作系统没有特殊的含义，换句话说，Linux 系统并不以文件的扩展名开分区文件类型。例如，dog.exe 只是一个文件，其扩展名 .exe 并不代表此文件就一定是可执行文件。



|   硬件设备    |                           文件名称                           |
| :-----------: | :----------------------------------------------------------: |
|    IDE设备    |                         /dev/hd[a-d]                         |
| SCSI/SATA/U盘 | /dev/sd[a-p]，一台主机可以有多块硬盘，因此系统采用 a~p 代表 16 块不同的硬盘。 |
|     软驱      |                         /dev/fd[0-1]                         |
|    打印机     |                        /dev/lp[0-15]                         |
|     光驱      |                          /dev/cdrom                          |
|     鼠标      |                          /dev/mouse                          |
|    磁带机     |                     /dev/st0 或 /dev/ht0                     |





## 识别文件类型



通过 ls -l 命令，我们就可以查看当前目录下所有文件和目录各自的属性

显示的执行结构中，每行代表一个文件或目录，其中第一个字符表示的就是文件的类型

| 第一个字符 |                           文件类型                           |
| :--------: | :----------------------------------------------------------: |
|     -      |    普通文件，包括纯文本文件、二进制文件、各种压缩文件等。    |
|     d      |             目录，类似 Windows 系统中的文件夹。              |
|     b      |    块设备文件，就是保存大块数据的设备，比如最常见的硬盘。    |
|     c      |               字符设备文件，例如键盘、鼠标等。               |
|     s      | 套接字文件，通常用在网络数据连接，可以启动一个程序开监听用户的要求，用户可以通过套接字进行数据通信。 |
|     p      | 管道文件，其主要作用是解决多个程序同时存取一个文件所造成的错误。 |
|     l      |          链接文件，类似 Windows 系统中的快捷方式。           |





```sh
root@e331c5c18f3f:/# ls -l
total 48
lrwxrwxrwx   1 root root    7 Apr 28 12:01 bin -> usr/bin
drwxr-xr-x   2 root root 4096 Apr 18 10:28 boot
drwxr-xr-x   5 root root  360 Jul  1 11:39 dev
drwxr-xr-x   1 root root 4096 Jul  1 11:39 etc
drwxr-xr-x   2 root root 4096 Apr 18 10:28 home
lrwxrwxrwx   1 root root    7 Apr 28 12:01 lib -> usr/lib
lrwxrwxrwx   1 root root    9 Apr 28 12:01 lib32 -> usr/lib32
lrwxrwxrwx   1 root root    9 Apr 28 12:01 lib64 -> usr/lib64
lrwxrwxrwx   1 root root   10 Apr 28 12:01 libx32 -> usr/libx32
drwxr-xr-x   2 root root 4096 Apr 28 12:01 media
drwxr-xr-x   2 root root 4096 Apr 28 12:01 mnt
drwxr-xr-x   2 root root 4096 Apr 28 12:01 opt
dr-xr-xr-x 281 root root    0 Jul  1 11:39 proc
drwx------   2 root root 4096 Apr 28 12:04 root
drwxr-xr-x   5 root root 4096 Apr 28 12:04 run
lrwxrwxrwx   1 root root    8 Apr 28 12:01 sbin -> usr/sbin
drwxr-xr-x   2 root root 4096 Apr 28 12:01 srv
dr-xr-xr-x  11 root root    0 Jul  1 11:39 sys
drwxrwxrwt   2 root root 4096 Apr 28 12:04 tmp
drwxr-xr-x  14 root root 4096 Apr 28 12:01 usr
drwxr-xr-x  11 root root 4096 Apr 28 12:04 var
root@e331c5c18f3f:/#
```

```sh
root@e331c5c18f3f:/var# ls -l
total 36
drwxr-xr-x 2 root root  4096 Apr 18 10:28 backups
drwxr-xr-x 5 root root  4096 Apr 28 12:04 cache
drwxr-xr-x 7 root root  4096 Apr 28 12:02 lib
drwxrwsr-x 2 root staff 4096 Apr 18 10:28 local
lrwxrwxrwx 1 root root     9 Apr 28 12:01 lock -> /run/lock
drwxr-xr-x 3 root root  4096 Apr 28 12:01 log
drwxrwsr-x 2 root mail  4096 Apr 28 12:01 mail
drwxr-xr-x 2 root root  4096 Apr 28 12:01 opt
lrwxrwxrwx 1 root root     4 Apr 28 12:01 run -> /run
drwxr-xr-x 2 root root  4096 Apr 28 12:01 spool
drwxrwxrwt 2 root root  4096 Apr 28 12:04 tmp
```

```sh
root@e331c5c18f3f:/usr# ls -l
total 56
drwxr-xr-x  2 root root 12288 Apr 28 12:04 bin
drwxr-xr-x  2 root root  4096 Apr 18 10:28 games
drwxr-xr-x  2 root root  4096 Apr 18 10:28 include
drwxr-xr-x 15 root root  4096 Apr 28 12:04 lib
drwxr-xr-x  2 root root  4096 Apr 28 12:01 lib32
drwxr-xr-x  2 root root  4096 Apr 28 12:02 lib64
drwxr-xr-x  4 root root  4096 Apr 28 12:01 libexec
drwxr-xr-x  2 root root  4096 Apr 28 12:01 libx32
drwxr-xr-x 10 root root  4096 Apr 28 12:01 local
drwxr-xr-x  2 root root  4096 Apr 28 12:04 sbin
drwxr-xr-x 33 root root  4096 Apr 28 12:01 share
drwxr-xr-x  2 root root  4096 Apr 18 10:28 src
```

```sh
root@e331c5c18f3f:/etc# ls -l
total 268
-rw-r--r-- 1 root root    3028 Apr 28 12:01 adduser.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 alternatives
drwxr-xr-x 8 root root    4096 Apr 28 12:01 apt
-rw-r--r-- 1 root root    2319 Jan  6 16:23 bash.bashrc
-rw-r--r-- 1 root root     367 Dec 16  2020 bindresvport.blacklist
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.d
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.daily
-rw-r--r-- 1 root root    2969 Feb 20 14:42 debconf.conf
-rw-r--r-- 1 root root      13 Aug 22  2021 debian_version
drwxr-xr-x 2 root root    4096 Apr 28 12:04 default
-rw-r--r-- 1 root root     604 Sep 15  2018 deluser.conf
drwxr-xr-x 4 root root    4096 Apr 28 12:02 dpkg
-rw-r--r-- 1 root root     685 Jan  8 20:02 e2scrub.conf
-rw-r--r-- 1 root root     106 Apr 28 12:01 environment
-rw-r--r-- 1 root root      37 Apr 28 12:01 fstab
-rw-r--r-- 1 root root    2584 Feb  3 05:27 gai.conf
-rw-r--r-- 1 root root     446 Apr 28 12:01 group
-rw-r----- 1 root shadow   374 Apr 28 12:01 gshadow
drwxr-xr-x 3 root root    4096 Feb 21 20:05 gss
-rw-r--r-- 1 root root      92 Oct 15  2021 host.conf
-rw-r--r-- 1 root root      13 Jul  1 11:39 hostname
-rw-r--r-- 1 root root     174 Jul  1 11:39 hosts
drwxr-xr-x 2 root root    4096 Apr 28 12:04 init.d
-rw-r--r-- 1 root root      24 Apr 18 10:28 issue
-rw-r--r-- 1 root root      17 Apr 18 10:28 issue.net
drwxr-xr-x 3 root root    4096 Apr 28 12:01 kernel
-rw-r--r-- 1 root root    5561 Apr 28 12:04 ld.so.cache
-rw-r--r-- 1 root root      34 Dec 16  2020 ld.so.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:02 ld.so.conf.d
-rw-r--r-- 1 root root     267 Oct 15  2021 legal
-rw-r--r-- 1 root root     191 Mar 17 17:50 libaudit.conf
-rw-r--r-- 1 root root   10734 Nov 11  2021 login.defs
drwxr-xr-x 2 root root    4096 Apr 28 12:02 logrotate.d
-rw-r--r-- 1 root root     102 Apr 18 10:28 lsb-release
-rw-r--r-- 1 root root       0 Apr 28 12:04 machine-id
-rw-r--r-- 1 root root     744 Jan  8 20:02 mke2fs.conf
lrwxrwxrwx 1 root root      12 Jul  1 11:39 mtab -> /proc/mounts
-rw-r--r-- 1 root root     767 Mar 24 16:13 netconfig
-rw-r--r-- 1 root root      91 Oct 15  2021 networks
-rw-r--r-- 1 root root     494 Dec 16  2020 nsswitch.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:01 opt
lrwxrwxrwx 1 root root      21 Apr 22 14:34 os-release -> ../usr/lib/os-release
-rw-r--r-- 1 root root     552 Aug 12  2020 pam.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 pam.d
-rw-r--r-- 1 root root     922 Apr 28 12:01 passwd
-rw-r--r-- 1 root root     582 Oct 15  2021 profile
drwxr-xr-x 2 root root    4096 Apr 28 12:04 profile.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc0.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc1.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc2.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc3.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc4.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc5.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc6.d
drwxr-xr-x 2 root root    4096 Apr 28 12:01 rcS.d
-rw-r--r-- 1 root root      97 Jul  1 11:39 resolv.conf
lrwxrwxrwx 1 root root      13 Mar 25 09:52 rmt -> /usr/sbin/rmt
drwxr-xr-x 4 root root    4096 Apr 28 12:03 security
drwxr-xr-x 2 root root    4096 Apr 28 12:03 selinux
-rw-r----- 1 root shadow   501 Apr 28 12:01 shadow
-rw-r--r-- 1 root root     128 Apr 28 12:02 shells
drwxr-xr-x 2 root root    4096 Apr 28 12:01 skel
-rw-r--r-- 1 root root       0 Apr 28 12:01 subgid
-rw-r--r-- 1 root root       0 Apr 28 12:01 subuid
-rw-r--r-- 1 root root    2355 Feb 25 11:32 sysctl.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 sysctl.d
drwxr-xr-x 4 root root    4096 Feb 15 22:32 systemd
drwxr-xr-x 2 root root    4096 Apr 28 12:04 terminfo
drwxr-xr-x 2 root root    4096 Apr 28 12:04 update-motd.d
-rw-r--r-- 1 root root     681 Mar 23 09:41 xattr.conf
root@e331c5c18f3f:/etc#

```





## 命令提示符

```sh
[root@localhost ~]#
```



- []：这是提示符的分隔符号，没有特殊含义。
- root：显示的是当前的登录用户，笔者现在使用的是 root 用户登录。
- @：分隔符号，没有特殊含义。
- localhost：当前系统的简写主机名（完整主机名是 localhost.localdomain）。
- ~：代表用户当前所在的目录，此例中用户当前所在的目录是家目录。
- \#：命令提示符，Linux 用这个符号标识登录的用户权限等级。如果是超级用户，提示符就是 #；如果是普通用户，提示符就是 $。



## 命令基本格式



```sh
[root@localhost ~]# 命令 [选项] [参数]
```

命令的选项用于调整命令功能，而命令的参数是这个命令的操作对象。



```sh
root@e331c5c18f3f:/# ls -l
total 48
lrwxrwxrwx   1 root root    7 Apr 28 12:01 bin -> usr/bin
drwxr-xr-x   2 root root 4096 Apr 18 10:28 boot
drwxr-xr-x   5 root root  360 Jul  1 11:39 dev
drwxr-xr-x   1 root root 4096 Jul  1 11:39 etc
drwxr-xr-x   2 root root 4096 Apr 18 10:28 home
lrwxrwxrwx   1 root root    7 Apr 28 12:01 lib -> usr/lib
lrwxrwxrwx   1 root root    9 Apr 28 12:01 lib32 -> usr/lib32
lrwxrwxrwx   1 root root    9 Apr 28 12:01 lib64 -> usr/lib64
lrwxrwxrwx   1 root root   10 Apr 28 12:01 libx32 -> usr/libx32
drwxr-xr-x   2 root root 4096 Apr 28 12:01 media
drwxr-xr-x   2 root root 4096 Apr 28 12:01 mnt
drwxr-xr-x   2 root root 4096 Apr 28 12:01 opt
dr-xr-xr-x 281 root root    0 Jul  1 11:39 proc
drwx------   2 root root 4096 Apr 28 12:04 root
drwxr-xr-x   5 root root 4096 Apr 28 12:04 run
lrwxrwxrwx   1 root root    8 Apr 28 12:01 sbin -> usr/sbin
drwxr-xr-x   2 root root 4096 Apr 28 12:01 srv
dr-xr-xr-x  11 root root    0 Jul  1 11:39 sys
drwxrwxrwt   2 root root 4096 Apr 28 12:04 tmp
drwxr-xr-x  14 root root 4096 Apr 28 12:01 usr
drwxr-xr-x  11 root root 4096 Apr 28 12:04 var
root@e331c5c18f3f:/#
```

```sh
root@e331c5c18f3f:/# cd boot
root@e331c5c18f3f:/boot# ls
root@e331c5c18f3f:/boot#
```





## cd命令

cd 命令，是 Change Directory 的缩写，**用来切换工作目录。**



Linux 命令按照来源方式，可分为两种，分别是 Shell 内置命令和外部命令。所谓 Shell 内置命令，就是 Shell 自带的命令，这些命令是没有执行文件的；而外部命令就是由程序员单独开发的，所以会有命令的执行文件。Linux 中的绝大多数命令是外部命令，而 cd 命令是一个典型的 Shell 内置命令，所以 cd 命令没有执行文件所在路径。

cd 命令的基本格式如下：

```sh
[root@localhost ~]# cd [相对路径或绝对路径]
```



| 特殊符号 |           作 用            |
| :------: | :------------------------: |
|    ~     |  代表当前登录用户的主目录  |
| ~用户名  | 表示切换至指定用户的主目录 |
|    -     |      代表上次所在目录      |
|    .     |        代表当前目录        |
|    ..    |        代表上级目录        |



```sh
root@e331c5c18f3f:/boot# pwd
/boot
root@e331c5c18f3f:/boot# cd ~
root@e331c5c18f3f:~#
root@e331c5c18f3f:~# pwd
/root
root@e331c5c18f3f:~# cd -
/boot
root@e331c5c18f3f:/boot# cd .
root@e331c5c18f3f:/boot# pwd
/boot
root@e331c5c18f3f:/boot# cd ..
root@e331c5c18f3f:/# pwd
/
root@e331c5c18f3f:/#
```





## pwd命令

**显示当前目录的绝对路径**



命令的基本格式为：

```sh
[root@localhost ~]# pwd
```



```sh
root@e331c5c18f3f:/# pwd
/
root@e331c5c18f3f:/# cd etc
root@e331c5c18f3f:/etc# pwd
/etc
root@e331c5c18f3f:/etc# ls
adduser.conf            debconf.conf    fstab      hosts        ld.so.conf.d   mke2fs.conf    pam.conf   rc2.d        rmt       subuid
alternatives            debian_version  gai.conf   init.d       legal          mtab           pam.d      rc3.d        security  sysctl.conf
apt                     default         group      issue        libaudit.conf  netconfig      passwd     rc4.d        selinux   sysctl.d
bash.bashrc             deluser.conf    gshadow    issue.net    login.defs     networks       profile    rc5.d        shadow    systemd
bindresvport.blacklist  dpkg            gss        kernel       logrotate.d    nsswitch.conf  profile.d  rc6.d        shells    terminfo
cron.d                  e2scrub.conf    host.conf  ld.so.cache  lsb-release    opt            rc0.d      rcS.d        skel      update-motd.d
cron.daily              environment     hostname   ld.so.conf   machine-id     os-release     rc1.d      resolv.conf  subgid    xattr.conf
root@e331c5c18f3f:/etc#
```





## ls命令

**显示当前目录下的内容**

基本格式：

```sh
[root@localhost ~]# ls [选项] 目录名称
```



|                   选项                    |                             功能                             |
| :---------------------------------------: | :----------------------------------------------------------: |
|                    -a                     | 显示全部的文件，包括隐藏文件（开头为 . 的文件）也一起罗列出来，这是最常用的选项之一。 |
|                    -A                     | 显示全部的文件，连同隐藏文件，但不包括 . 与 .. 这两个目录。  |
|                    -d                     |         仅列出目录本身，而不是列出目录内的文件数据。         |
|                    -f                     | ls 默认会以文件名排序，使用 -f 选项会直接列出结果，而不进行排序。 |
|                    -F                     | 在文件或目录名后加上文件类型的指示符号，例如，* 代表可运行文件，/ 代表目录，= 代表 socket文件，\| 代表 FIFO 文件。 |
|                    -h                     | 以人们易读的方式显示文件或目录大小，如 1KB、234MB、2GB 等。  |
|                    -i                     |                    显示 inode 节点信息。                     |
|                    -l                     |                使用长格式列出文件和目录信息。                |
|                    -n                     |      以 UID 和 GID 分别代替文件用户名和群组名显示出来。      |
|                    -r                     | 将排序结果反向输出，比如，若原本文件名由小到大，反向则为由大到小。 |
|                    -R                     | 连同子目录内容一起列出来，等於将该目录下的所有文件都显示出来。 |
|                    -S                     |           以文件容量大小排序，而不是以文件名排序。           |
|                    -t                     |               以时间排序，而不是以文件名排序。               |
| --color=never --color=always --color=auto | never 表示不依据文件特性给予颜色显示。 always 表示显示颜色，ls 默认采用这种方式。 auto 表示让系统自行依据配置来判断是否给予颜色。 |
|                --full-time                |        以完整时间模式 （包含年、月、日、时、分）输出         |
|           --time={atime,ctime}            | 输出 access 时间或改变权限属性时间（ctime），而不是内容变更时间。 |



ls -l 命令各列的含义：

1. 第一列：规定了不同的用户对文件所拥有的权限
2. 第二列：引用计数，文件的引用计数代表该文件的硬链接个数，而目录的引用计数代表该目录有多少个一级子目录。
3. 第三列：所有者，也就是这个文件属于哪个用户。默认所有者是文件的建立用户。
4. 第四列：所属组，默认所属组是文件建立用户的有效组，一般情况下就是建立用户的所在组。
5. 第五列：大小，默认单位是字节。
6. 第六列：文件修改时间，文件状态修改时间或文件数据修改时间都会更改这个时间，注意这个时间不是文件的创建时间。
7. 第七列：文件名或目录名。

```sh
drwxr-xr-x 2 root root    4096 Apr 28 12:04 update-motd.d
-rw-r--r-- 1 root root     681 Mar 23 09:41 xattr.conf
```



使用：

```sh
root@e331c5c18f3f:/etc# ls -a
.             bindresvport.blacklist  dpkg          gss        kernel         logrotate.d  nsswitch.conf  profile.d  rc6.d        shells       terminfo
..            cron.d                  e2scrub.conf  host.conf  ld.so.cache    lsb-release  opt            rc0.d      rcS.d        skel         update-motd.d
.pwd.lock     cron.daily              environment   hostname   ld.so.conf     machine-id   os-release     rc1.d      resolv.conf  subgid       xattr.conf
adduser.conf  debconf.conf            fstab         hosts      ld.so.conf.d   mke2fs.conf  pam.conf       rc2.d      rmt          subuid
alternatives  debian_version          gai.conf      init.d     legal          mtab         pam.d          rc3.d      security     sysctl.conf
apt           default                 group         issue      libaudit.conf  netconfig    passwd         rc4.d      selinux      sysctl.d
bash.bashrc   deluser.conf            gshadow       issue.net  login.defs     networks     profile        rc5.d      shadow       systemd
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -A
.pwd.lock               cron.daily      environment  hostname     ld.so.conf     machine-id     os-release  rc1.d  resolv.conf  subgid         xattr.conf
adduser.conf            debconf.conf    fstab        hosts        ld.so.conf.d   mke2fs.conf    pam.conf    rc2.d  rmt          subuid
alternatives            debian_version  gai.conf     init.d       legal          mtab           pam.d       rc3.d  security     sysctl.conf
apt                     default         group        issue        libaudit.conf  netconfig      passwd      rc4.d  selinux      sysctl.d
bash.bashrc             deluser.conf    gshadow      issue.net    login.defs     networks       profile     rc5.d  shadow       systemd
bindresvport.blacklist  dpkg            gss          kernel       logrotate.d    nsswitch.conf  profile.d   rc6.d  shells       terminfo
cron.d                  e2scrub.conf    host.conf    ld.so.cache  lsb-release    opt            rc0.d       rcS.d  skel         update-motd.d
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -d
.
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -f
lsb-release  rc4.d         rmt            terminfo                pam.d         security   environment   mke2fs.conf    debian_version  mtab
systemd      machine-id    apt            passwd                  e2scrub.conf  host.conf  pam.conf      issue.net      profile.d
gai.conf     netconfig     opt            bash.bashrc             selinux       hostname   gshadow       group          debconf.conf
dpkg         rc6.d         resolv.conf    deluser.conf            ld.so.cache   fstab      ld.so.conf.d  .pwd.lock      ..
xattr.conf   ld.so.conf    os-release     init.d                  profile       rc3.d      gss           networks       alternatives
legal        adduser.conf  hosts          sysctl.d                skel          cron.d     sysctl.conf   update-motd.d  logrotate.d
rcS.d        subuid        nsswitch.conf  bindresvport.blacklist  issue         default    subgid        rc2.d          cron.daily
rc5.d        rc0.d         libaudit.conf  login.defs              shadow        rc1.d      shells        kernel         .
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -F
adduser.conf            debconf.conf    fstab      hosts        ld.so.conf.d/  mke2fs.conf    pam.conf    rc2.d/       rmt@       subuid
alternatives/           debian_version  gai.conf   init.d/      legal          mtab@          pam.d/      rc3.d/       security/  sysctl.conf
apt/                    default/        group      issue        libaudit.conf  netconfig      passwd      rc4.d/       selinux/   sysctl.d/
bash.bashrc             deluser.conf    gshadow    issue.net    login.defs     networks       profile     rc5.d/       shadow     systemd/
bindresvport.blacklist  dpkg/           gss/       kernel/      logrotate.d/   nsswitch.conf  profile.d/  rc6.d/       shells     terminfo/
cron.d/                 e2scrub.conf    host.conf  ld.so.cache  lsb-release    opt/           rc0.d/      rcS.d/       skel/      update-motd.d/
cron.daily/             environment     hostname   ld.so.conf   machine-id     os-release@    rc1.d/      resolv.conf  subgid     xattr.conf
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -h
adduser.conf            debconf.conf    fstab      hosts        ld.so.conf.d   mke2fs.conf    pam.conf   rc2.d        rmt       subuid
alternatives            debian_version  gai.conf   init.d       legal          mtab           pam.d      rc3.d        security  sysctl.conf
apt                     default         group      issue        libaudit.conf  netconfig      passwd     rc4.d        selinux   sysctl.d
bash.bashrc             deluser.conf    gshadow    issue.net    login.defs     networks       profile    rc5.d        shadow    systemd
bindresvport.blacklist  dpkg            gss        kernel       logrotate.d    nsswitch.conf  profile.d  rc6.d        shells    terminfo
cron.d                  e2scrub.conf    host.conf  ld.so.cache  lsb-release    opt            rc0.d      rcS.d        skel      update-motd.d
cron.daily              environment     hostname   ld.so.conf   machine-id     os-release     rc1.d      resolv.conf  subgid    xattr.conf
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -i
 5392 adduser.conf             5429 deluser.conf  63388 hostname       5463 libaudit.conf   5475 opt          5502 rc3.d         5526 shells
 5393 alternatives             5430 dpkg          63387 hosts          5464 login.defs      5476 os-release   5503 rc4.d         5527 skel
 5400 apt                      5439 e2scrub.conf   5450 init.d         5465 logrotate.d     5477 pam.conf     5504 rc5.d         5531 subgid
 5418 bash.bashrc              5440 environment    5453 issue          5469 lsb-release     5478 pam.d        5505 rc6.d         5532 subuid
 5419 bindresvport.blacklist   5441 fstab          5454 issue.net      5470 machine-id      5495 passwd       5506 rcS.d         5533 sysctl.conf
 5420 cron.d                   5442 gai.conf       5455 kernel         5471 mke2fs.conf     5496 profile     63389 resolv.conf   5534 sysctl.d
 5422 cron.daily               5443 group          5457 ld.so.cache   63366 mtab            5497 profile.d    5509 rmt           5543 systemd
 5425 debconf.conf             5444 gshadow        5458 ld.so.conf     5472 netconfig       5499 rc0.d        5510 security      5555 terminfo
 5426 debian_version           5445 gss            5459 ld.so.conf.d   5473 networks        5500 rc1.d        5523 selinux       5557 update-motd.d
 5427 default                  5447 host.conf      5462 legal          5474 nsswitch.conf   5501 rc2.d        5525 shadow        5562 xattr.conf
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -l
total 268
-rw-r--r-- 1 root root    3028 Apr 28 12:01 adduser.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 alternatives
drwxr-xr-x 8 root root    4096 Apr 28 12:01 apt
-rw-r--r-- 1 root root    2319 Jan  6 16:23 bash.bashrc
-rw-r--r-- 1 root root     367 Dec 16  2020 bindresvport.blacklist
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.d
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.daily
-rw-r--r-- 1 root root    2969 Feb 20 14:42 debconf.conf
-rw-r--r-- 1 root root      13 Aug 22  2021 debian_version
drwxr-xr-x 2 root root    4096 Apr 28 12:04 default
-rw-r--r-- 1 root root     604 Sep 15  2018 deluser.conf
drwxr-xr-x 4 root root    4096 Apr 28 12:02 dpkg
-rw-r--r-- 1 root root     685 Jan  8 20:02 e2scrub.conf
-rw-r--r-- 1 root root     106 Apr 28 12:01 environment
-rw-r--r-- 1 root root      37 Apr 28 12:01 fstab
-rw-r--r-- 1 root root    2584 Feb  3 05:27 gai.conf
-rw-r--r-- 1 root root     446 Apr 28 12:01 group
-rw-r----- 1 root shadow   374 Apr 28 12:01 gshadow
drwxr-xr-x 3 root root    4096 Feb 21 20:05 gss
-rw-r--r-- 1 root root      92 Oct 15  2021 host.conf
-rw-r--r-- 1 root root      13 Jul  1 11:39 hostname
-rw-r--r-- 1 root root     174 Jul  1 11:39 hosts
drwxr-xr-x 2 root root    4096 Apr 28 12:04 init.d
-rw-r--r-- 1 root root      24 Apr 18 10:28 issue
-rw-r--r-- 1 root root      17 Apr 18 10:28 issue.net
drwxr-xr-x 3 root root    4096 Apr 28 12:01 kernel
-rw-r--r-- 1 root root    5561 Apr 28 12:04 ld.so.cache
-rw-r--r-- 1 root root      34 Dec 16  2020 ld.so.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:02 ld.so.conf.d
-rw-r--r-- 1 root root     267 Oct 15  2021 legal
-rw-r--r-- 1 root root     191 Mar 17 17:50 libaudit.conf
-rw-r--r-- 1 root root   10734 Nov 11  2021 login.defs
drwxr-xr-x 2 root root    4096 Apr 28 12:02 logrotate.d
-rw-r--r-- 1 root root     102 Apr 18 10:28 lsb-release
-rw-r--r-- 1 root root       0 Apr 28 12:04 machine-id
-rw-r--r-- 1 root root     744 Jan  8 20:02 mke2fs.conf
lrwxrwxrwx 1 root root      12 Jul  1 11:39 mtab -> /proc/mounts
-rw-r--r-- 1 root root     767 Mar 24 16:13 netconfig
-rw-r--r-- 1 root root      91 Oct 15  2021 networks
-rw-r--r-- 1 root root     494 Dec 16  2020 nsswitch.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:01 opt
lrwxrwxrwx 1 root root      21 Apr 22 14:34 os-release -> ../usr/lib/os-release
-rw-r--r-- 1 root root     552 Aug 12  2020 pam.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 pam.d
-rw-r--r-- 1 root root     922 Apr 28 12:01 passwd
-rw-r--r-- 1 root root     582 Oct 15  2021 profile
drwxr-xr-x 2 root root    4096 Apr 28 12:04 profile.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc0.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc1.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc2.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc3.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc4.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc5.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc6.d
drwxr-xr-x 2 root root    4096 Apr 28 12:01 rcS.d
-rw-r--r-- 1 root root      97 Jul  1 11:39 resolv.conf
lrwxrwxrwx 1 root root      13 Mar 25 09:52 rmt -> /usr/sbin/rmt
drwxr-xr-x 4 root root    4096 Apr 28 12:03 security
drwxr-xr-x 2 root root    4096 Apr 28 12:03 selinux
-rw-r----- 1 root shadow   501 Apr 28 12:01 shadow
-rw-r--r-- 1 root root     128 Apr 28 12:02 shells
drwxr-xr-x 2 root root    4096 Apr 28 12:01 skel
-rw-r--r-- 1 root root       0 Apr 28 12:01 subgid
-rw-r--r-- 1 root root       0 Apr 28 12:01 subuid
-rw-r--r-- 1 root root    2355 Feb 25 11:32 sysctl.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 sysctl.d
drwxr-xr-x 4 root root    4096 Feb 15 22:32 systemd
drwxr-xr-x 2 root root    4096 Apr 28 12:04 terminfo
drwxr-xr-x 2 root root    4096 Apr 28 12:04 update-motd.d
-rw-r--r-- 1 root root     681 Mar 23 09:41 xattr.conf
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -n
total 268
-rw-r--r-- 1 0  0  3028 Apr 28 12:01 adduser.conf
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 alternatives
drwxr-xr-x 8 0  0  4096 Apr 28 12:01 apt
-rw-r--r-- 1 0  0  2319 Jan  6 16:23 bash.bashrc
-rw-r--r-- 1 0  0   367 Dec 16  2020 bindresvport.blacklist
drwxr-xr-x 2 0  0  4096 Apr 28 12:02 cron.d
drwxr-xr-x 2 0  0  4096 Apr 28 12:02 cron.daily
-rw-r--r-- 1 0  0  2969 Feb 20 14:42 debconf.conf
-rw-r--r-- 1 0  0    13 Aug 22  2021 debian_version
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 default
-rw-r--r-- 1 0  0   604 Sep 15  2018 deluser.conf
drwxr-xr-x 4 0  0  4096 Apr 28 12:02 dpkg
-rw-r--r-- 1 0  0   685 Jan  8 20:02 e2scrub.conf
-rw-r--r-- 1 0  0   106 Apr 28 12:01 environment
-rw-r--r-- 1 0  0    37 Apr 28 12:01 fstab
-rw-r--r-- 1 0  0  2584 Feb  3 05:27 gai.conf
-rw-r--r-- 1 0  0   446 Apr 28 12:01 group
-rw-r----- 1 0 42   374 Apr 28 12:01 gshadow
drwxr-xr-x 3 0  0  4096 Feb 21 20:05 gss
-rw-r--r-- 1 0  0    92 Oct 15  2021 host.conf
-rw-r--r-- 1 0  0    13 Jul  1 11:39 hostname
-rw-r--r-- 1 0  0   174 Jul  1 11:39 hosts
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 init.d
-rw-r--r-- 1 0  0    24 Apr 18 10:28 issue
-rw-r--r-- 1 0  0    17 Apr 18 10:28 issue.net
drwxr-xr-x 3 0  0  4096 Apr 28 12:01 kernel
-rw-r--r-- 1 0  0  5561 Apr 28 12:04 ld.so.cache
-rw-r--r-- 1 0  0    34 Dec 16  2020 ld.so.conf
drwxr-xr-x 2 0  0  4096 Apr 28 12:02 ld.so.conf.d
-rw-r--r-- 1 0  0   267 Oct 15  2021 legal
-rw-r--r-- 1 0  0   191 Mar 17 17:50 libaudit.conf
-rw-r--r-- 1 0  0 10734 Nov 11  2021 login.defs
drwxr-xr-x 2 0  0  4096 Apr 28 12:02 logrotate.d
-rw-r--r-- 1 0  0   102 Apr 18 10:28 lsb-release
-rw-r--r-- 1 0  0     0 Apr 28 12:04 machine-id
-rw-r--r-- 1 0  0   744 Jan  8 20:02 mke2fs.conf
lrwxrwxrwx 1 0  0    12 Jul  1 11:39 mtab -> /proc/mounts
-rw-r--r-- 1 0  0   767 Mar 24 16:13 netconfig
-rw-r--r-- 1 0  0    91 Oct 15  2021 networks
-rw-r--r-- 1 0  0   494 Dec 16  2020 nsswitch.conf
drwxr-xr-x 2 0  0  4096 Apr 28 12:01 opt
lrwxrwxrwx 1 0  0    21 Apr 22 14:34 os-release -> ../usr/lib/os-release
-rw-r--r-- 1 0  0   552 Aug 12  2020 pam.conf
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 pam.d
-rw-r--r-- 1 0  0   922 Apr 28 12:01 passwd
-rw-r--r-- 1 0  0   582 Oct 15  2021 profile
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 profile.d
drwxr-xr-x 2 0  0  4096 Feb 15 22:32 rc0.d
drwxr-xr-x 2 0  0  4096 Feb 15 22:32 rc1.d
drwxr-xr-x 2 0  0  4096 Feb 15 22:32 rc2.d
drwxr-xr-x 2 0  0  4096 Feb 15 22:32 rc3.d
drwxr-xr-x 2 0  0  4096 Feb 15 22:32 rc4.d
drwxr-xr-x 2 0  0  4096 Feb 15 22:32 rc5.d
drwxr-xr-x 2 0  0  4096 Feb 15 22:32 rc6.d
drwxr-xr-x 2 0  0  4096 Apr 28 12:01 rcS.d
-rw-r--r-- 1 0  0    97 Jul  1 11:39 resolv.conf
lrwxrwxrwx 1 0  0    13 Mar 25 09:52 rmt -> /usr/sbin/rmt
drwxr-xr-x 4 0  0  4096 Apr 28 12:03 security
drwxr-xr-x 2 0  0  4096 Apr 28 12:03 selinux
-rw-r----- 1 0 42   501 Apr 28 12:01 shadow
-rw-r--r-- 1 0  0   128 Apr 28 12:02 shells
drwxr-xr-x 2 0  0  4096 Apr 28 12:01 skel
-rw-r--r-- 1 0  0     0 Apr 28 12:01 subgid
-rw-r--r-- 1 0  0     0 Apr 28 12:01 subuid
-rw-r--r-- 1 0  0  2355 Feb 25 11:32 sysctl.conf
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 sysctl.d
drwxr-xr-x 4 0  0  4096 Feb 15 22:32 systemd
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 terminfo
drwxr-xr-x 2 0  0  4096 Apr 28 12:04 update-motd.d
-rw-r--r-- 1 0  0   681 Mar 23 09:41 xattr.conf
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -l -r
total 268
-rw-r--r-- 1 root root     681 Mar 23 09:41 xattr.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 update-motd.d
drwxr-xr-x 2 root root    4096 Apr 28 12:04 terminfo
drwxr-xr-x 4 root root    4096 Feb 15 22:32 systemd
drwxr-xr-x 2 root root    4096 Apr 28 12:04 sysctl.d
-rw-r--r-- 1 root root    2355 Feb 25 11:32 sysctl.conf
-rw-r--r-- 1 root root       0 Apr 28 12:01 subuid
-rw-r--r-- 1 root root       0 Apr 28 12:01 subgid
drwxr-xr-x 2 root root    4096 Apr 28 12:01 skel
-rw-r--r-- 1 root root     128 Apr 28 12:02 shells
-rw-r----- 1 root shadow   501 Apr 28 12:01 shadow
drwxr-xr-x 2 root root    4096 Apr 28 12:03 selinux
drwxr-xr-x 4 root root    4096 Apr 28 12:03 security
lrwxrwxrwx 1 root root      13 Mar 25 09:52 rmt -> /usr/sbin/rmt
-rw-r--r-- 1 root root      97 Jul  1 11:39 resolv.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:01 rcS.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc6.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc5.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc4.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc3.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc2.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc1.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc0.d
drwxr-xr-x 2 root root    4096 Apr 28 12:04 profile.d
-rw-r--r-- 1 root root     582 Oct 15  2021 profile
-rw-r--r-- 1 root root     922 Apr 28 12:01 passwd
drwxr-xr-x 2 root root    4096 Apr 28 12:04 pam.d
-rw-r--r-- 1 root root     552 Aug 12  2020 pam.conf
lrwxrwxrwx 1 root root      21 Apr 22 14:34 os-release -> ../usr/lib/os-release
drwxr-xr-x 2 root root    4096 Apr 28 12:01 opt
-rw-r--r-- 1 root root     494 Dec 16  2020 nsswitch.conf
-rw-r--r-- 1 root root      91 Oct 15  2021 networks
-rw-r--r-- 1 root root     767 Mar 24 16:13 netconfig
lrwxrwxrwx 1 root root      12 Jul  1 11:39 mtab -> /proc/mounts
-rw-r--r-- 1 root root     744 Jan  8 20:02 mke2fs.conf
-rw-r--r-- 1 root root       0 Apr 28 12:04 machine-id
-rw-r--r-- 1 root root     102 Apr 18 10:28 lsb-release
drwxr-xr-x 2 root root    4096 Apr 28 12:02 logrotate.d
-rw-r--r-- 1 root root   10734 Nov 11  2021 login.defs
-rw-r--r-- 1 root root     191 Mar 17 17:50 libaudit.conf
-rw-r--r-- 1 root root     267 Oct 15  2021 legal
drwxr-xr-x 2 root root    4096 Apr 28 12:02 ld.so.conf.d
-rw-r--r-- 1 root root      34 Dec 16  2020 ld.so.conf
-rw-r--r-- 1 root root    5561 Apr 28 12:04 ld.so.cache
drwxr-xr-x 3 root root    4096 Apr 28 12:01 kernel
-rw-r--r-- 1 root root      17 Apr 18 10:28 issue.net
-rw-r--r-- 1 root root      24 Apr 18 10:28 issue
drwxr-xr-x 2 root root    4096 Apr 28 12:04 init.d
-rw-r--r-- 1 root root     174 Jul  1 11:39 hosts
-rw-r--r-- 1 root root      13 Jul  1 11:39 hostname
-rw-r--r-- 1 root root      92 Oct 15  2021 host.conf
drwxr-xr-x 3 root root    4096 Feb 21 20:05 gss
-rw-r----- 1 root shadow   374 Apr 28 12:01 gshadow
-rw-r--r-- 1 root root     446 Apr 28 12:01 group
-rw-r--r-- 1 root root    2584 Feb  3 05:27 gai.conf
-rw-r--r-- 1 root root      37 Apr 28 12:01 fstab
-rw-r--r-- 1 root root     106 Apr 28 12:01 environment
-rw-r--r-- 1 root root     685 Jan  8 20:02 e2scrub.conf
drwxr-xr-x 4 root root    4096 Apr 28 12:02 dpkg
-rw-r--r-- 1 root root     604 Sep 15  2018 deluser.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 default
-rw-r--r-- 1 root root      13 Aug 22  2021 debian_version
-rw-r--r-- 1 root root    2969 Feb 20 14:42 debconf.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.daily
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.d
-rw-r--r-- 1 root root     367 Dec 16  2020 bindresvport.blacklist
-rw-r--r-- 1 root root    2319 Jan  6 16:23 bash.bashrc
drwxr-xr-x 8 root root    4096 Apr 28 12:01 apt
drwxr-xr-x 2 root root    4096 Apr 28 12:04 alternatives
-rw-r--r-- 1 root root    3028 Apr 28 12:01 adduser.conf
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -l -R
.:
total 268
-rw-r--r-- 1 root root    3028 Apr 28 12:01 adduser.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 alternatives
drwxr-xr-x 8 root root    4096 Apr 28 12:01 apt
-rw-r--r-- 1 root root    2319 Jan  6 16:23 bash.bashrc
-rw-r--r-- 1 root root     367 Dec 16  2020 bindresvport.blacklist
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.d
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.daily
-rw-r--r-- 1 root root    2969 Feb 20 14:42 debconf.conf
-rw-r--r-- 1 root root      13 Aug 22  2021 debian_version
drwxr-xr-x 2 root root    4096 Apr 28 12:04 default
-rw-r--r-- 1 root root     604 Sep 15  2018 deluser.conf
drwxr-xr-x 4 root root    4096 Apr 28 12:02 dpkg
-rw-r--r-- 1 root root     685 Jan  8 20:02 e2scrub.conf
-rw-r--r-- 1 root root     106 Apr 28 12:01 environment
-rw-r--r-- 1 root root      37 Apr 28 12:01 fstab
-rw-r--r-- 1 root root    2584 Feb  3 05:27 gai.conf
-rw-r--r-- 1 root root     446 Apr 28 12:01 group
-rw-r----- 1 root shadow   374 Apr 28 12:01 gshadow
drwxr-xr-x 3 root root    4096 Feb 21 20:05 gss
-rw-r--r-- 1 root root      92 Oct 15  2021 host.conf
-rw-r--r-- 1 root root      13 Jul  1 11:39 hostname
-rw-r--r-- 1 root root     174 Jul  1 11:39 hosts
drwxr-xr-x 2 root root    4096 Apr 28 12:04 init.d
-rw-r--r-- 1 root root      24 Apr 18 10:28 issue
-rw-r--r-- 1 root root      17 Apr 18 10:28 issue.net
drwxr-xr-x 3 root root    4096 Apr 28 12:01 kernel
-rw-r--r-- 1 root root    5561 Apr 28 12:04 ld.so.cache
-rw-r--r-- 1 root root      34 Dec 16  2020 ld.so.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:02 ld.so.conf.d
-rw-r--r-- 1 root root     267 Oct 15  2021 legal
-rw-r--r-- 1 root root     191 Mar 17 17:50 libaudit.conf
-rw-r--r-- 1 root root   10734 Nov 11  2021 login.defs
drwxr-xr-x 2 root root    4096 Apr 28 12:02 logrotate.d
-rw-r--r-- 1 root root     102 Apr 18 10:28 lsb-release
-rw-r--r-- 1 root root       0 Apr 28 12:04 machine-id
-rw-r--r-- 1 root root     744 Jan  8 20:02 mke2fs.conf
lrwxrwxrwx 1 root root      12 Jul  1 11:39 mtab -> /proc/mounts
-rw-r--r-- 1 root root     767 Mar 24 16:13 netconfig
-rw-r--r-- 1 root root      91 Oct 15  2021 networks
-rw-r--r-- 1 root root     494 Dec 16  2020 nsswitch.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:01 opt
lrwxrwxrwx 1 root root      21 Apr 22 14:34 os-release -> ../usr/lib/os-release
-rw-r--r-- 1 root root     552 Aug 12  2020 pam.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 pam.d
-rw-r--r-- 1 root root     922 Apr 28 12:01 passwd
-rw-r--r-- 1 root root     582 Oct 15  2021 profile
drwxr-xr-x 2 root root    4096 Apr 28 12:04 profile.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc0.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc1.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc2.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc3.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc4.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc5.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc6.d
drwxr-xr-x 2 root root    4096 Apr 28 12:01 rcS.d
-rw-r--r-- 1 root root      97 Jul  1 11:39 resolv.conf
lrwxrwxrwx 1 root root      13 Mar 25 09:52 rmt -> /usr/sbin/rmt
drwxr-xr-x 4 root root    4096 Apr 28 12:03 security
drwxr-xr-x 2 root root    4096 Apr 28 12:03 selinux
-rw-r----- 1 root shadow   501 Apr 28 12:01 shadow
-rw-r--r-- 1 root root     128 Apr 28 12:02 shells
drwxr-xr-x 2 root root    4096 Apr 28 12:01 skel
-rw-r--r-- 1 root root       0 Apr 28 12:01 subgid
-rw-r--r-- 1 root root       0 Apr 28 12:01 subuid
-rw-r--r-- 1 root root    2355 Feb 25 11:32 sysctl.conf
drwxr-xr-x 2 root root    4096 Apr 28 12:04 sysctl.d
drwxr-xr-x 4 root root    4096 Feb 15 22:32 systemd
drwxr-xr-x 2 root root    4096 Apr 28 12:04 terminfo
drwxr-xr-x 2 root root    4096 Apr 28 12:04 update-motd.d
-rw-r--r-- 1 root root     681 Mar 23 09:41 xattr.conf

./alternatives:
total 4
-rw-r--r-- 1 root root 100 Apr  6 09:40 README
lrwxrwxrwx 1 root root  13 Apr 28 12:04 awk -> /usr/bin/mawk
lrwxrwxrwx 1 root root  13 Apr 28 12:04 nawk -> /usr/bin/mawk
lrwxrwxrwx 1 root root   9 Apr 28 12:04 pager -> /bin/more
lrwxrwxrwx 1 root root  17 Apr 28 12:04 rmt -> /usr/sbin/rmt-tar
lrwxrwxrwx 1 root root  26 Apr 28 12:02 which -> /usr/bin/which.debianutils

./apt:
total 28
drwxr-xr-x 2 root root 4096 Apr 28 12:04 apt.conf.d
drwxr-xr-x 2 root root 4096 Apr  8 10:22 auth.conf.d
drwxr-xr-x 2 root root 4096 Apr  8 10:22 keyrings
drwxr-xr-x 2 root root 4096 Apr  8 10:22 preferences.d
-rw-r--r-- 1 root root 2403 Apr 28 12:04 sources.list
drwxr-xr-x 2 root root 4096 Apr  8 10:22 sources.list.d
drwxr-xr-x 2 root root 4096 Apr 28 12:04 trusted.gpg.d

./apt/apt.conf.d:
total 32
-rw-r--r-- 1 root root  92 Apr  8 10:22 01-vendor-ubuntu
-rw-r--r-- 1 root root 630 Apr  8 10:22 01autoremove
-rw-r--r-- 1 root root 182 Feb 20 14:42 70debconf
-rw-r--r-- 1 root root  44 Apr 28 12:04 docker-autoremove-suggests
-rw-r--r-- 1 root root 318 Apr 28 12:04 docker-clean
-rw-r--r-- 1 root root  27 Apr 28 12:04 docker-disable-periodic-update
-rw-r--r-- 1 root root  70 Apr 28 12:04 docker-gzip-indexes
-rw-r--r-- 1 root root  27 Apr 28 12:04 docker-no-languages

./apt/auth.conf.d:
total 0

./apt/keyrings:
total 0

./apt/preferences.d:
total 0

./apt/sources.list.d:
total 0

./apt/trusted.gpg.d:
total 8
-rw-r--r-- 1 root root 2794 Mar 26  2021 ubuntu-keyring-2012-cdimage.gpg
-rw-r--r-- 1 root root 1733 Mar 26  2021 ubuntu-keyring-2018-archive.gpg

./cron.d:
total 4
-rw-r--r-- 1 root root 201 Jan  8 20:02 e2scrub_all

./cron.daily:
total 8
-rwxr-xr-x 1 root root 1478 Apr  8 10:22 apt-compat
-rwxr-xr-x 1 root root  123 Dec  5  2021 dpkg

./default:
total 4
-rw-r--r-- 1 root root 1118 Nov 11  2021 useradd

./dpkg:
total 12
-rw-r--r-- 1 root root  446 Jan 30  2021 dpkg.cfg
drwxr-xr-x 2 root root 4096 Apr 28 12:04 dpkg.cfg.d
drwxr-xr-x 2 root root 4096 Apr 28 12:04 origins

./dpkg/dpkg.cfg.d:
total 8
-rw-r--r-- 1 root root  16 Apr 28 12:04 docker-apt-speedup
-rw-r--r-- 1 root root 364 Apr 28 12:01 excludes

./dpkg/origins:
total 8
-rw-r--r-- 1 root root  83 Apr 10  2021 debian
lrwxrwxrwx 1 root root   6 Apr 28 12:01 default -> ubuntu
-rw-r--r-- 1 root root 114 Oct 15  2021 ubuntu

./gss:
total 4
drwxr-xr-x 2 root root 4096 Feb 21 20:05 mech.d

./gss/mech.d:
total 0

./init.d:
total 8
-rwxr-xr-x 1 root root 1748 Feb 20 23:13 hwclock.sh
-rwxr-xr-x 1 root root  959 Feb 25 11:32 procps

./kernel:
total 4
drwxr-xr-x 2 root root 4096 Apr  8 10:22 postinst.d

./kernel/postinst.d:
total 0

./ld.so.conf.d:
total 8
-rw-r--r-- 1 root root  44 Dec 16  2020 libc.conf
-rw-r--r-- 1 root root 100 Mar  4 02:54 x86_64-linux-gnu.conf

./logrotate.d:
total 12
-rw-r--r-- 1 root root 120 Sep 11  2021 alternatives
-rw-r--r-- 1 root root 173 Apr  8 10:22 apt
-rw-r--r-- 1 root root 112 Sep 11  2021 dpkg

./opt:
total 0

./pam.d:
total 68
-rw-r--r-- 1 root root  384 Nov 11  2021 chfn
-rw-r--r-- 1 root root   92 Nov 11  2021 chpasswd
-rw-r--r-- 1 root root  581 Nov 11  2021 chsh
-rw-r--r-- 1 root root 1208 Apr 28 12:03 common-account
-rw-r--r-- 1 root root 1214 Apr 28 12:03 common-auth
-rw-r--r-- 1 root root 1620 Apr 28 12:03 common-password
-rw-r--r-- 1 root root 1394 Apr 28 12:03 common-session
-rw-r--r-- 1 root root 1435 Apr 28 12:03 common-session-noninteractive
-rw-r--r-- 1 root root 4126 Mar 14 08:59 login
-rw-r--r-- 1 root root   92 Nov 11  2021 newusers
-rw-r--r-- 1 root root  520 Aug 12  2020 other
-rw-r--r-- 1 root root   92 Nov 11  2021 passwd
-rw-r--r-- 1 root root  143 Feb 20 23:13 runuser
-rw-r--r-- 1 root root  138 Feb 20 23:13 runuser-l
-rw-r--r-- 1 root root 2259 Feb 20 23:13 su
-rw-r--r-- 1 root root  137 Feb 20 23:13 su-l

./profile.d:
total 4
-rw-r--r-- 1 root root 96 Oct 15  2021 01-locale-fix.sh

./rc0.d:
total 0

./rc1.d:
total 0

./rc2.d:
total 0

./rc3.d:
total 0

./rc4.d:
total 0

./rc5.d:
total 0

./rc6.d:
total 0

./rcS.d:
total 0
lrwxrwxrwx 1 root root 16 Apr 28 12:01 S01procps -> ../init.d/procps

./security:
total 48
-rw-r--r-- 1 root root 4564 Mar 24 01:43 access.conf
-rw-r--r-- 1 root root 2234 Mar 24 01:43 faillock.conf
-rw-r--r-- 1 root root 3635 Mar 24 01:43 group.conf
-rw-r--r-- 1 root root 2161 Mar 24 01:43 limits.conf
drwxr-xr-x 2 root root 4096 Mar 24 01:43 limits.d
-rw-r--r-- 1 root root 1637 Mar 24 01:43 namespace.conf
drwxr-xr-x 2 root root 4096 Mar 24 01:43 namespace.d
-rwxr-xr-x 1 root root 1016 Mar 24 01:43 namespace.init
-rw------- 1 root root    0 Apr 28 12:01 opasswd
-rw-r--r-- 1 root root 2971 Mar 24 01:43 pam_env.conf
-rw-r--r-- 1 root root  419 Mar 24 01:43 sepermit.conf
-rw-r--r-- 1 root root 2179 Mar 24 01:43 time.conf

./security/limits.d:
total 0

./security/namespace.d:
total 0

./selinux:
total 4
-rw-r--r-- 1 root root 2041 Mar 17 14:06 semanage.conf

./skel:
total 0

./sysctl.d:
total 32
-rw-r--r-- 1 root root   77 Feb 25 11:57 10-console-messages.conf
-rw-r--r-- 1 root root  490 Feb 25 11:57 10-ipv6-privacy.conf
-rw-r--r-- 1 root root 1229 Feb 25 11:57 10-kernel-hardening.conf
-rw-r--r-- 1 root root 1184 Feb 25 11:57 10-magic-sysrq.conf
-rw-r--r-- 1 root root  158 Feb 25 11:57 10-network-security.conf
-rw-r--r-- 1 root root 1292 Feb 25 11:57 10-ptrace.conf
-rw-r--r-- 1 root root  506 Feb 25 11:57 10-zeropage.conf
-rw-r--r-- 1 root root  798 Feb 25 11:32 README.sysctl

./systemd:
total 8
drwxr-xr-x 4 root root 4096 Apr 28 12:01 system
drwxr-xr-x 2 root root 4096 Feb 15 22:32 user

./systemd/system:
total 8
drwxr-xr-x 2 root root 4096 Apr 28 12:01 multi-user.target.wants
drwxr-xr-x 2 root root 4096 Apr 28 12:01 timers.target.wants

./systemd/system/multi-user.target.wants:
total 0
lrwxrwxrwx 1 root root 40 Apr 28 12:01 e2scrub_reap.service -> /lib/systemd/system/e2scrub_reap.service

./systemd/system/timers.target.wants:
total 0
lrwxrwxrwx 1 root root 43 Apr 28 12:01 apt-daily-upgrade.timer -> /lib/systemd/system/apt-daily-upgrade.timer
lrwxrwxrwx 1 root root 35 Apr 28 12:01 apt-daily.timer -> /lib/systemd/system/apt-daily.timer
lrwxrwxrwx 1 root root 40 Apr 28 12:01 dpkg-db-backup.timer -> /lib/systemd/system/dpkg-db-backup.timer
lrwxrwxrwx 1 root root 37 Apr 28 12:01 e2scrub_all.timer -> /lib/systemd/system/e2scrub_all.timer
lrwxrwxrwx 1 root root 32 Apr 28 12:01 fstrim.timer -> /lib/systemd/system/fstrim.timer
lrwxrwxrwx 1 root root 35 Apr 28 12:01 motd-news.timer -> /lib/systemd/system/motd-news.timer

./systemd/user:
total 0

./terminfo:
total 4
-rw-r--r-- 1 root root 212 Jan 17 17:02 README

./update-motd.d:
total 20
-rwxr-xr-x 1 root root 1220 Oct 15  2021 00-header
-rwxr-xr-x 1 root root 1157 Oct 15  2021 10-help-text
-rwxr-xr-x 1 root root 5023 Oct 15  2021 50-motd-news
-rwxr-xr-x 1 root root  356 Apr 28 12:04 60-unminimize
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -l -S
total 268
-rw-r--r-- 1 root root   10734 Nov 11  2021 login.defs
-rw-r--r-- 1 root root    5561 Apr 28 12:04 ld.so.cache
drwxr-xr-x 2 root root    4096 Apr 28 12:04 alternatives
drwxr-xr-x 8 root root    4096 Apr 28 12:01 apt
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.d
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.daily
drwxr-xr-x 2 root root    4096 Apr 28 12:04 default
drwxr-xr-x 4 root root    4096 Apr 28 12:02 dpkg
drwxr-xr-x 3 root root    4096 Feb 21 20:05 gss
drwxr-xr-x 2 root root    4096 Apr 28 12:04 init.d
drwxr-xr-x 3 root root    4096 Apr 28 12:01 kernel
drwxr-xr-x 2 root root    4096 Apr 28 12:02 ld.so.conf.d
drwxr-xr-x 2 root root    4096 Apr 28 12:02 logrotate.d
drwxr-xr-x 2 root root    4096 Apr 28 12:01 opt
drwxr-xr-x 2 root root    4096 Apr 28 12:04 pam.d
drwxr-xr-x 2 root root    4096 Apr 28 12:04 profile.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc0.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc1.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc2.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc3.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc4.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc5.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc6.d
drwxr-xr-x 2 root root    4096 Apr 28 12:01 rcS.d
drwxr-xr-x 4 root root    4096 Apr 28 12:03 security
drwxr-xr-x 2 root root    4096 Apr 28 12:03 selinux
drwxr-xr-x 2 root root    4096 Apr 28 12:01 skel
drwxr-xr-x 2 root root    4096 Apr 28 12:04 sysctl.d
drwxr-xr-x 4 root root    4096 Feb 15 22:32 systemd
drwxr-xr-x 2 root root    4096 Apr 28 12:04 terminfo
drwxr-xr-x 2 root root    4096 Apr 28 12:04 update-motd.d
-rw-r--r-- 1 root root    3028 Apr 28 12:01 adduser.conf
-rw-r--r-- 1 root root    2969 Feb 20 14:42 debconf.conf
-rw-r--r-- 1 root root    2584 Feb  3 05:27 gai.conf
-rw-r--r-- 1 root root    2355 Feb 25 11:32 sysctl.conf
-rw-r--r-- 1 root root    2319 Jan  6 16:23 bash.bashrc
-rw-r--r-- 1 root root     922 Apr 28 12:01 passwd
-rw-r--r-- 1 root root     767 Mar 24 16:13 netconfig
-rw-r--r-- 1 root root     744 Jan  8 20:02 mke2fs.conf
-rw-r--r-- 1 root root     685 Jan  8 20:02 e2scrub.conf
-rw-r--r-- 1 root root     681 Mar 23 09:41 xattr.conf
-rw-r--r-- 1 root root     604 Sep 15  2018 deluser.conf
-rw-r--r-- 1 root root     582 Oct 15  2021 profile
-rw-r--r-- 1 root root     552 Aug 12  2020 pam.conf
-rw-r----- 1 root shadow   501 Apr 28 12:01 shadow
-rw-r--r-- 1 root root     494 Dec 16  2020 nsswitch.conf
-rw-r--r-- 1 root root     446 Apr 28 12:01 group
-rw-r----- 1 root shadow   374 Apr 28 12:01 gshadow
-rw-r--r-- 1 root root     367 Dec 16  2020 bindresvport.blacklist
-rw-r--r-- 1 root root     267 Oct 15  2021 legal
-rw-r--r-- 1 root root     191 Mar 17 17:50 libaudit.conf
-rw-r--r-- 1 root root     174 Jul  1 11:39 hosts
-rw-r--r-- 1 root root     128 Apr 28 12:02 shells
-rw-r--r-- 1 root root     106 Apr 28 12:01 environment
-rw-r--r-- 1 root root     102 Apr 18 10:28 lsb-release
-rw-r--r-- 1 root root      97 Jul  1 11:39 resolv.conf
-rw-r--r-- 1 root root      92 Oct 15  2021 host.conf
-rw-r--r-- 1 root root      91 Oct 15  2021 networks
-rw-r--r-- 1 root root      37 Apr 28 12:01 fstab
-rw-r--r-- 1 root root      34 Dec 16  2020 ld.so.conf
-rw-r--r-- 1 root root      24 Apr 18 10:28 issue
lrwxrwxrwx 1 root root      21 Apr 22 14:34 os-release -> ../usr/lib/os-release
-rw-r--r-- 1 root root      17 Apr 18 10:28 issue.net
-rw-r--r-- 1 root root      13 Aug 22  2021 debian_version
-rw-r--r-- 1 root root      13 Jul  1 11:39 hostname
lrwxrwxrwx 1 root root      13 Mar 25 09:52 rmt -> /usr/sbin/rmt
lrwxrwxrwx 1 root root      12 Jul  1 11:39 mtab -> /proc/mounts
-rw-r--r-- 1 root root       0 Apr 28 12:04 machine-id
-rw-r--r-- 1 root root       0 Apr 28 12:01 subgid
-rw-r--r-- 1 root root       0 Apr 28 12:01 subuid
root@e331c5c18f3f:/etc#
```

```sh
root@e331c5c18f3f:/etc# ls -l -t
total 268
-rw-r--r-- 1 root root      13 Jul  1 11:39 hostname
-rw-r--r-- 1 root root     174 Jul  1 11:39 hosts
-rw-r--r-- 1 root root      97 Jul  1 11:39 resolv.conf
lrwxrwxrwx 1 root root      12 Jul  1 11:39 mtab -> /proc/mounts
-rw-r--r-- 1 root root       0 Apr 28 12:04 machine-id
drwxr-xr-x 2 root root    4096 Apr 28 12:04 profile.d
drwxr-xr-x 2 root root    4096 Apr 28 12:04 update-motd.d
-rw-r--r-- 1 root root    5561 Apr 28 12:04 ld.so.cache
drwxr-xr-x 2 root root    4096 Apr 28 12:04 alternatives
drwxr-xr-x 2 root root    4096 Apr 28 12:04 init.d
drwxr-xr-x 2 root root    4096 Apr 28 12:04 pam.d
drwxr-xr-x 2 root root    4096 Apr 28 12:04 sysctl.d
drwxr-xr-x 2 root root    4096 Apr 28 12:04 default
drwxr-xr-x 2 root root    4096 Apr 28 12:04 terminfo
drwxr-xr-x 2 root root    4096 Apr 28 12:03 selinux
drwxr-xr-x 4 root root    4096 Apr 28 12:03 security
drwxr-xr-x 2 root root    4096 Apr 28 12:02 ld.so.conf.d
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.d
drwxr-xr-x 2 root root    4096 Apr 28 12:02 cron.daily
drwxr-xr-x 4 root root    4096 Apr 28 12:02 dpkg
drwxr-xr-x 2 root root    4096 Apr 28 12:02 logrotate.d
-rw-r--r-- 1 root root     128 Apr 28 12:02 shells
drwxr-xr-x 2 root root    4096 Apr 28 12:01 skel
-rw-r--r-- 1 root root     922 Apr 28 12:01 passwd
-rw-r----- 1 root shadow   501 Apr 28 12:01 shadow
-rw-r--r-- 1 root root    3028 Apr 28 12:01 adduser.conf
drwxr-xr-x 8 root root    4096 Apr 28 12:01 apt
-rw-r--r-- 1 root root     106 Apr 28 12:01 environment
-rw-r--r-- 1 root root     446 Apr 28 12:01 group
-rw-r----- 1 root shadow   374 Apr 28 12:01 gshadow
drwxr-xr-x 3 root root    4096 Apr 28 12:01 kernel
-rw-r--r-- 1 root root       0 Apr 28 12:01 subgid
-rw-r--r-- 1 root root       0 Apr 28 12:01 subuid
drwxr-xr-x 2 root root    4096 Apr 28 12:01 rcS.d
-rw-r--r-- 1 root root      37 Apr 28 12:01 fstab
drwxr-xr-x 2 root root    4096 Apr 28 12:01 opt
lrwxrwxrwx 1 root root      21 Apr 22 14:34 os-release -> ../usr/lib/os-release
-rw-r--r-- 1 root root      24 Apr 18 10:28 issue
-rw-r--r-- 1 root root      17 Apr 18 10:28 issue.net
-rw-r--r-- 1 root root     102 Apr 18 10:28 lsb-release
lrwxrwxrwx 1 root root      13 Mar 25 09:52 rmt -> /usr/sbin/rmt
-rw-r--r-- 1 root root     767 Mar 24 16:13 netconfig
-rw-r--r-- 1 root root     681 Mar 23 09:41 xattr.conf
-rw-r--r-- 1 root root     191 Mar 17 17:50 libaudit.conf
-rw-r--r-- 1 root root    2355 Feb 25 11:32 sysctl.conf
drwxr-xr-x 3 root root    4096 Feb 21 20:05 gss
-rw-r--r-- 1 root root    2969 Feb 20 14:42 debconf.conf
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc0.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc1.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc2.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc3.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc4.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc5.d
drwxr-xr-x 2 root root    4096 Feb 15 22:32 rc6.d
drwxr-xr-x 4 root root    4096 Feb 15 22:32 systemd
-rw-r--r-- 1 root root    2584 Feb  3 05:27 gai.conf
-rw-r--r-- 1 root root     685 Jan  8 20:02 e2scrub.conf
-rw-r--r-- 1 root root     744 Jan  8 20:02 mke2fs.conf
-rw-r--r-- 1 root root    2319 Jan  6 16:23 bash.bashrc
-rw-r--r-- 1 root root   10734 Nov 11  2021 login.defs
-rw-r--r-- 1 root root      92 Oct 15  2021 host.conf
-rw-r--r-- 1 root root     267 Oct 15  2021 legal
-rw-r--r-- 1 root root      91 Oct 15  2021 networks
-rw-r--r-- 1 root root     582 Oct 15  2021 profile
-rw-r--r-- 1 root root      13 Aug 22  2021 debian_version
-rw-r--r-- 1 root root     367 Dec 16  2020 bindresvport.blacklist
-rw-r--r-- 1 root root      34 Dec 16  2020 ld.so.conf
-rw-r--r-- 1 root root     494 Dec 16  2020 nsswitch.conf
-rw-r--r-- 1 root root     552 Aug 12  2020 pam.conf
-rw-r--r-- 1 root root     604 Sep 15  2018 deluser.conf
root@e331c5c18f3f:/etc#
```







## mkdir命令

mkdir 命令，是 make directories 的缩写，**用于创建新目录**



```sh
[root@localhost ~]# mkdir [-mp] 目录名
```

- -m 选项用于手动配置所创建目录的权限，而不再使用默认权限。
- -p 选项递归创建所有目录，以创建 /home/test/demo 为例，在默认情况下，你需要一层一层的创建各个目录，而使用 -p 选项，则系统会自动帮你创建 /home、/home/test 以及 /home/test/demo。



```sh
root@e331c5c18f3f:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@e331c5c18f3f:/# cd tmp
root@e331c5c18f3f:/tmp# ls
root@e331c5c18f3f:/tmp# mkdir test
root@e331c5c18f3f:/tmp# ls -l
total 4
drwxr-xr-x 2 root root 4096 Jul  2 04:37 test
root@e331c5c18f3f:/tmp# mkdir t1/t2/t3
mkdir: cannot create directory 't1/t2/t3': No such file or directory
root@e331c5c18f3f:/tmp# mkdir -p t1/t2/t3
root@e331c5c18f3f:/tmp# ls -l
total 8
drwxr-xr-x 3 root root 4096 Jul  2 04:40 t1
drwxr-xr-x 2 root root 4096 Jul  2 04:37 test
root@e331c5c18f3f:/tmp# cd t1
root@e331c5c18f3f:/tmp/t1# ls -l
total 4
drwxr-xr-x 3 root root 4096 Jul  2 04:40 t2
root@e331c5c18f3f:/tmp/t1# cd t2
root@e331c5c18f3f:/tmp/t1/t2# ls -l
total 4
drwxr-xr-x 2 root root 4096 Jul  2 04:40 t3
root@e331c5c18f3f:/tmp/t1/t2#
```





## rmdir命令

rmdir（remove empty directories 的缩写）命令**用于删除空目录**



```sh
[root@localhost ~]# rmdir [-p] 目录名
```

* -p 选项用于递归删除空目录



```sh
root@e331c5c18f3f:/tmp# ls -l
total 8
drwxr-xr-x 3 root root 4096 Jul  2 04:40 t1
drwxr-xr-x 2 root root 4096 Jul  2 04:37 test
root@e331c5c18f3f:/tmp# rmdir test
root@e331c5c18f3f:/tmp# ls -l
total 4
drwxr-xr-x 3 root root 4096 Jul  2 04:40 t1
root@e331c5c18f3f:/tmp# rmdir -p t1
rmdir: failed to remove 't1': Directory not empty
root@e331c5c18f3f:/tmp# rmdir -p t1/t2/t3
root@e331c5c18f3f:/tmp# ls
root@e331c5c18f3f:/tmp#
```





## touch命令

**创建文件及修改文件时间戳**

touch 命令不光可以用来创建文件（当指定操作文件不存在时，该命令会在当前位置建立一个空文件），此命令更重要的功能是修改文件的时间参数（但当文件存在时，会修改此文件的时间参数）



Linux 系统中，每个文件主要拥有 3 个时间参数（通过 stat 命令进行查看），分别是文件的访问时间、数据修改时间以及状态修改时间：

- 访问时间（Access Time，简称 atime）：只要文件的内容被读取，访问时间就会更新。例如，使用 cat 命令可以查看文件的内容，此时文件的访问时间就会发生改变。
- 数据修改时间（Modify Time，简称 mtime）：当文件的内容数据发生改变，此文件的数据修改时间就会跟着相应改变。
- 状态修改时间（Change Time，简称 ctime）：当文件的状态发生变化，就会相应改变这个时间。比如说，如果文件的权限或者属性发生改变，此时间就会相应改变。



```sh
root@e331c5c18f3f:/tmp# stat hello.txt
  File: hello.txt
  Size: 0               Blocks: 0          IO Block: 4096   regular empty file
Device: c6h/198d        Inode: 63251       Links: 1
Access: (0644/-rw-r--r--)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2022-07-02 04:46:05.298133084 +0000
Modify: 2022-07-02 04:46:05.298133084 +0000
Change: 2022-07-02 04:46:05.298133084 +0000
 Birth: 2022-07-02 04:46:05.298133084 +0000
root@e331c5c18f3f:/tmp#
```



```sh
[root@localhost ~]# touch [选项] 文件名
```



```sh
root@e331c5c18f3f:/tmp# ls -l
total 0
-rw-r--r-- 1 root root 0 Jul  2 04:46 hello.txt
root@e331c5c18f3f:/tmp# touch test.txt
root@e331c5c18f3f:/tmp# ls -l
total 0
-rw-r--r-- 1 root root 0 Jul  2 04:46 hello.txt
-rw-r--r-- 1 root root 0 Jul  2 04:49 test.txt
root@e331c5c18f3f:/tmp#
```





## ln命令

**建立链接（硬链接和软链接）**



ext4 文件系统会把分区主要分为两大部分：小部分用于保存文件的 inode (i 节点）信息；剩余的大部分用于保存 block 信息。

inode 的默认大小为 128 Byte，用来记录文件的权限（r、w、x）、文件的所有者和属组、文件的大小、文件的状态改变时间（ctime）、文件的最近一次读取时间（atime）、文件的最近一次修改时间（mtime）、文件的数据真正保存的 block 编号。每个文件需要占用一个 inode。 inode 中是不记录文件名的，那是因为文件名记录在文件所在目录的 block 中。

block 的大小可以是 1KB、2KB、4KB，默认为 4KB。block 用于实际的数据存储，如果一个 block 放不下数据，则可以占用多个 block。例如，有一个 10KB 的文件需要存储，则会占用 3 个 block，虽然最后一个 block 不能占满，但也不能再放入其他文件的数据。这 3 个 block 有可能是连续的，也有可能是分散的。



* 每个文件都独自占用一个 inode，文件内容由 inode 的记录来指向；

* 如果想要读取文件内容，就必须借助目录中记录的文件名找到该文件的 inode，才能成功找到文件内容所在的 block 块；



ln 命令用于给文件创建链接，根据 Linux 系统存储文件的特点，链接的方式分为以下 2 种：

- **软链接：**类似于 Windows 系统中给文件创建快捷方式，即产生一个特殊的文件，该文件用来指向另一个文件，此链接方式同样适用于目录。
- **硬链接：**我们知道，文件的基本信息都存储在 inode 中，而硬链接指的就是给一个文件的 inode 分配多个文件名，通过任何一个文件名，都可以找到此文件的 inode，从而读取该文件的数据信息。



命令：

```sh
[root@localhost ~]# ln [选项] 源文件 目标文件
```

选项：

- -s：建立软链接文件。如果不加 "-s" 选项，则建立硬链接文件；
- -f：强制。如果目标文件已经存在，则删除目标文件后再建立链接文件；



软链接文件的源文件必须写成绝对路径，而不能写成相对路径（硬链接没有这样的要求）；否则软链接文件会报错。



### 硬链接



当我们查找一个文件，比如 /root/test 时，要经过以下步骤：

1. 首先找到根目录的 inode（根目录的 inode 是系统已知的，inode 号是 2），然后判断用户是否有权限访问根目录的 block。
2. 如果有权限，则可以在根目录的 block 中访问到 /root 的文件名及对应的 inode 号。
3. 通过 /root/ 目录的 inode 号，可以查找到 /root/ 目录的 inode 信息，接着判断用户是否有权限访问 /root/ 目录的 block。
4. 如果有权限，则可以从 /root/ 目录的 block 中读取到 test 文件的文件名及对应的 inode 号。
5. 通过 test 文件的 inode 号，就可以找到 test 文件的 inode 信息，接着判断用户是否有权限访问 test 文件的 block。
6. 如果有权限，则可以读取 block 中的数据，这样就完成了 /root/test 文件的读取与访问。



这就是硬链接的原理。硬链接的特点如下：

- 不论是修改源文件（test 文件），还是修改硬链接文件（test-hard 文件），另一个文件中的数据都会发生改变。
- 不论是删除源文件，还是删除硬链接文件，只要还有一个文件存在，这个文件（inode 号是 262147 的文件）都可以被访问。
- 硬链接不会建立新的 inode 信息，也不会更改 inode 的总数。
- 硬链接不能跨文件系统（分区）建立，因为在不同的文件系统中，inode 号是重新计算的。
- 硬链接不能链接目录，因为如果给目录建立硬链接，那么不仅目录本身需要重新建立，目录下所有的子文件，包括子目录中的所有子文件都需要建立硬链接，这对当前的 Linux 来讲过于复杂。



### 软链接

软链接也称作符号链接

软链接的特点和 Windows 中的快捷方式完全一致



步骤：

1. 首先找到根目录的 inode 索引信息，然后判断用户是否有权限访问根目录的 block。
2. 如果有权限访问根目录的 block，就会在 block 中查找到 /tmp/ 目录的 inode 号。
3. 接着访问 /tmp/ 目录的 inode 信息，判断用户是否有权限访问 /tmp/ 目录的 block。
4. 如果有权限，就会在 block 中读取到软链接文件 check-soft 的 inode 号。因为软链接文件会真正建立自己的 inode 索引和 block，所以软链接文件和源文件的 inode 号是不一样的。
5. 通过软链接文件的 inode 号，找到了 check-soft 文件 inode 信息，判断用户是否有权限访问 block。
6. 如果有权限，就会发现 check-soft 文件的 block 中没有实际数据，仅有源文件 check 的 inode 号。
7. 接着通过源文件的 inode 号，访问到源文件 check 的 inode 信息，判断用户是否有权限访问 block。
8. 如果有权限，就会在 check 文件的 block 中读取到真正的数据，从而完成数据访问。



特点：

- 不论是修改源文件（check），还是修改硬链接文件（check-soft)，另一个文件中的数据都会发生改变。
- 删除软链接文件，源文件不受影响。而删除原文件，软链接文件将找不到实际的数据，从而显示文件不存在。
- 软链接会新建自己的 inode 信息和 block，只是在 block 中不存储实际文件数据，而存储的是源文件的文件名及 inode 号。
- 软链接可以链接目录。
- 软链接可以跨分区。





## cp命令

cp 命令，**主要用来复制文件和目录**，同时借助某些选项，还可以实现复制整个目录



```sh
[root@localhost ~]# cp [选项] 源文件 目标文件
```



选项：

- -a：相当于 -d、-p、-r 选项的集合；
- -d：如果源文件为软链接（对硬链接无效），则复制出的目标文件也为软链接；
- -i：询问，如果目标文件已经存在，则会询问是否覆盖；
- -l：把目标文件建立为源文件的硬链接文件，而不是复制源文件；
- -s：把目标文件建立为源文件的软链接文件，而不是复制源文件；
- -p：复制后目标文件保留源文件的属性（包括所有者、所属组、权限和时间）；
- -r：递归复制，用于复制目录；
- -u：若目标文件比源文件有差异，则使用该选项可以更新目标文件，此选项可用于对文件的升级和备用。



```sh
root@e331c5c18f3f:/tmp# ls -l
total 0
-rw-r--r-- 1 root root 0 Jul  2 04:46 hello.txt
-rw-r--r-- 1 root root 0 Jul  2 04:49 test.txt
root@e331c5c18f3f:/tmp# mkdir test
root@e331c5c18f3f:/tmp# ls -l
total 4
-rw-r--r-- 1 root root    0 Jul  2 04:46 hello.txt
drwxr-xr-x 2 root root 4096 Jul  2 05:04 test
-rw-r--r-- 1 root root    0 Jul  2 04:49 test.txt
root@e331c5c18f3f:/tmp# cp hello.txt ./test
root@e331c5c18f3f:/tmp# ls -l
total 4
-rw-r--r-- 1 root root    0 Jul  2 04:46 hello.txt
drwxr-xr-x 2 root root 4096 Jul  2 05:05 test
-rw-r--r-- 1 root root    0 Jul  2 04:49 test.txt
root@e331c5c18f3f:/tmp# cd test
root@e331c5c18f3f:/tmp/test# ls -l
total 0
-rw-r--r-- 1 root root 0 Jul  2 05:05 hello.txt
root@e331c5c18f3f:/tmp/test#
```

```sh
root@e331c5c18f3f:/tmp# cp -i hello.txt ./test
cp: overwrite './test/hello.txt'? yes
```





## rm命令

**永久性地删除文件系统中指定的文件或目录**。在使用 rm 命令删除文件或目录时，系统不会产生任何提示信息



命令：

```sh
[root@localhost ~]# rm [选项] 文件或目录
```

- -f：强制删除（force），和 -i 选项相反，使用 -f，系统将不再询问，而是直接删除目标文件或目录。
- -i：和 -f 正好相反，在删除文件或目录之前，系统会给出提示信息，使用 -i 可以有效防止不小心删除有用的文件或目录。
- -r：递归删除，主要用于删除目录，可删除指定目录及包含的所有内容，包括所有的子目录和文件。



```sh
root@e331c5c18f3f:/tmp# ls
hello.txt  test  test.txt
root@e331c5c18f3f:/tmp# rm test.txt
root@e331c5c18f3f:/tmp# ls
hello.txt  test
root@e331c5c18f3f:/tmp# rm -i hello.txt
rm: remove regular empty file 'hello.txt'? no
root@e331c5c18f3f:/tmp# ls
hello.txt  test
root@e331c5c18f3f:/tmp# rm -i hello.txt
rm: remove regular empty file 'hello.txt'? yes
root@e331c5c18f3f:/tmp# ls
test
root@e331c5c18f3f:/tmp# rm test
rm: cannot remove 'test': Is a directory
root@e331c5c18f3f:/tmp# rm -rf test
root@e331c5c18f3f:/tmp# ls
root@e331c5c18f3f:/tmp#
```





## mv命令

mv 命令（move 的缩写），**既可以在不同的目录之间移动文件或目录，也可以对文件和目录进行重命名**



```sh
[root@localhost ~]# mv [选项] 源文件 目标文件
```



选项：

- -f：强制覆盖，如果目标文件已经存在，则不询问，直接强制覆盖；
- -i：交互移动，如果目标文件已经存在，则询问用户是否覆盖（默认选项）；
- -n：如果目标文件已经存在，则不会覆盖移动，而且不询问用户；
- -v：显示文件或目录的移动过程；
- -u：若目标文件已经存在，但两者相比，源文件更新，则会对目标文件进行升级；



```sh
root@e331c5c18f3f:/tmp# ls
root@e331c5c18f3f:/tmp# touch 1.txt
root@e331c5c18f3f:/tmp# touch 2.txt
root@e331c5c18f3f:/tmp# mkdir test
root@e331c5c18f3f:/tmp# mv 1.txt ./test
root@e331c5c18f3f:/tmp# ls -l
total 4
-rw-r--r-- 1 root root    0 Jul  2 05:21 2.txt
drwxr-xr-x 2 root root 4096 Jul  2 05:22 test
root@e331c5c18f3f:/tmp# cd test
root@e331c5c18f3f:/tmp/test# ls -l
total 0
-rw-r--r-- 1 root root 0 Jul  2 05:21 1.txt
root@e331c5c18f3f:/tmp/test#
```





## 命令自动补全

按 Tab 键，Shell 就可以自动将文件名补全

连续按两次 Tab 键，显示目录



```sh
root@e331c5c18f3f:/tmp# mk
mkdir             mkfifo            mkfs.bfs          mkfs.ext2         mkfs.ext4         mkhomedir_helper  mknod             mktemp
mke2fs            mkfs              mkfs.cramfs       mkfs.ext3         mkfs.minix        mklost+found      mkswap
root@e331c5c18f3f:/tmp# mk
```





## 命令执行过程

* 判断路径
* 检查别名
* 判断是内部命令还是外部命令
* 查找外部命令对应的可执行文件



### 判断路径

断用户是否以绝对路径或相对路径的方式输入命令（如 /bin/ls），如果是的话直接执行。



### 检查别名

inux 系统会检查用户输入的命令是否为“别名命令”。要知道，通过 alias 命令是可以给现有命令自定义别名的，即用一个自定义的命令名称来替换原本的命令名称。



### 判断是内部命令还是外部命令

Linux命令行解释器（又称为 Shell）会判断用户输入的命令是内部命令还是外部命令。其中，内部命令指的是解释器内部的命令，会被直接执行；而用户通常输入的命令都是外部命令，这些命令交给步骤四继续处理。

内部命令由 Shell 自带，会随着系统启动，可以直接从内存中读取；而外部命令仅是在系统中有对应的可执行文件，执行时需要读取该文件。

判断一个命令属于内部命令还是外部命令，可以使用 type 命令实现



```sh
root@e331c5c18f3f:/tmp# type pwd
pwd is a shell builtin
root@e331c5c18f3f:/tmp# type cp
cp is hashed (/usr/bin/cp)
root@e331c5c18f3f:/tmp# type ls
ls is aliased to `ls --color=auto'
root@e331c5c18f3f:/tmp# type gcc
bash: type: gcc: not found
root@e331c5c18f3f:/tmp#

```





### 查找外部命令对应的可执行文件

当用户执行的是外部命令时，系统会在指定的多个路径中查找该命令的可执行文件，而定义这些路径的变量，就称为 PATH 环境变量，其作用就是告诉 Shell 待执行命令的可执行文件可能存放的位置，也就是说，Shell 会在 PATH 变量包含的多个路径中逐个查找，直到找到为止。如果找不到，Shell 会提供用户“找不到此命令”。



```sh
root@e331c5c18f3f:/tmp# gcc
bash: gcc: command not found
root@e331c5c18f3f:/tmp# redis-clli
bash: redis-clli: command not found
root@e331c5c18f3f:/tmp#
```







## 环境变量

变量是计算机系统用于保存可变值的数据类型，我们可以直接通过变量名称来提取到对应的变量值。在 Linux 系统中，环境变量是用来定义系统运行环境的一些参数，比如每个用户不同的家目录（HOME）、邮件存放位置（MAIL）等。

Linux 系统中环境变量的名称一般都是大写的



查看Linux 系统中所有的环境变量：

```sh
env
```



```sh
root@e331c5c18f3f:/tmp# env
HOSTNAME=e331c5c18f3f
PWD=/tmp
HOME=/root
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
TERM=xterm
SHLVL=1
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/usr/bin/env
OLDPWD=/tmp/test
root@e331c5c18f3f:/tmp#
```



| 环境变量名称 |                  作用                  |
| :----------: | :------------------------------------: |
|     HOME     |       用户的主目录（也称家目录）       |
|    SHELL     |      用户使用的 Shell 解释器名称       |
|     PATH     | 定义命令行解释器搜索用户执行命令的路径 |
|    EDITOR    |          用户默认的文本解释器          |
|    RANDOM    |            生成一个随机数字            |
|     LANG     |           系统语言、语系名称           |
|   HISTSIZE   |         输出的历史命令记录条数         |
| HISTFILESIZE |         保存的历史命令记录条数         |
|     PS1      |           Bash解释器的提示符           |
|     MAIL     |              邮件保存路径              |











# 打包（归档）和压缩

归档：也称为打包，指的是一个文件或目录的集合，而这个集合被存储在一个文件中。归档文件没有经过压缩，因此，它占用的空间是其中所有文件和目录的总和。

压缩是指利用算法将文件进行处理，已达到保留最大文件信息，而让文件体积变小的目的。其基本原理为，通过查找文件内的重复字节，建立一个相同字节的词典文件，并用一个代码表示。

采用压缩工具对文件进行压缩，生成的文件称为压缩包

使用前需要利用压缩工具将文件数据还原，此过程又称解压缩





## tar命令

### 打包

命令：

```sh
[root@localhost ~]#tar [选项] 源文件或目录
```



|  选项   |                             含义                             |
| :-----: | :----------------------------------------------------------: |
|   -c    |                  将多个文件或目录进行打包。                  |
|   -A    |                  追加 tar 文件到归档文件。                   |
| -f 包名 | 指定包的文件名。包的扩展名是用来给管理员识别格式的，所以一定要正确指定扩展名 |
|   -v    |                       显示打包文件过程                       |



```sh
mao@ubuntu:~/桌面$ tar -cvf a.tar a.c
a.c
mao@ubuntu:~/桌面$ ls
1.txt  a.out                                    filea.c  linux_file.c
2.txt  a.tar                                    func1.c  main.c
a.c    English_early_education_machine_input.c  func2.c  main.h
mao@ubuntu:~/桌面$ 
```



### 解压



```sh
[root@localhost ~]#tar [选项] 压缩包
```



|  选项   |                            含义                            |
| :-----: | :--------------------------------------------------------: |
|   -x    |                  对 tar 包做解打包操作。                   |
|   -f    |                指定要解压的 tar 包的包名。                 |
|   -t    | 只查看 tar 包中有哪些文件或目录，不对 tar 包做解打包操作。 |
| -C 目录 |                      指定解打包位置。                      |
|   -v    |                   显示解打包的具体过程。                   |



```sh
mao@ubuntu:~/桌面$ tar -tvf a.tar
-rw------- mao/mao        8859 2021-12-30 04:31 a.c
mao@ubuntu:~/桌面$ tar -xvf a.tar
a.c
mao@ubuntu:~/桌面$ ls -l
总用量 96
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ 

```





## zip命令



命令：

```sh
[root@localhost ~]#zip [选项] 压缩包名 源文件或源目录列表
```



|   选项    |                             含义                             |
| :-------: | :----------------------------------------------------------: |
|    -r     |  递归压缩目录，及将制定目录下的所有文件以及子目录全部压缩。  |
|    -m     |  将文件压缩之后，删除原始文件，相当于把文件移到压缩文件中。  |
|    -v     |                   显示详细的压缩过程信息。                   |
|    -q     |              在压缩的时候不显示命令的执行过程。              |
| -压缩级别 | 压缩级别是从 1~9 的数字，-1 代表压缩速度更快，-9 代表压缩效果更好。 |
|    -u     |            更新压缩文件，即往压缩文件中添加新文件            |



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 96
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ zip -v a.zip a.c
  adding: a.c	(in=8859) (out=2742) (deflated 69%)
total bytes=8859, compressed=2742 -> 69% savings
mao@ubuntu:~/桌面$ ls -l
总用量 100
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ 
```







## unzip命令

unzip 命令可以**查看和解压缩 zip 文件**



命令：

```sh
[root@localhost ~]# unzip [选项] 压缩包名
```



|    选项     |                             含义                             |
| :---------: | :----------------------------------------------------------: |
|  -d 目录名  |                 将压缩文件解压到指定目录下。                 |
|     -n      |                解压时并不覆盖已经存在的文件。                |
|     -o      |         解压时覆盖已经存在的文件，并且无需用户确认。         |
|     -v      | 查看压缩文件的详细信息，包括压缩文件中包含的文件大小、文件名以及压缩比等，但并不做解压操作。 |
|     -t      |              测试压缩文件有无损坏，但并不解压。              |
| -x 文件列表 |           解压文件，但不包含文件列表中指定的文件。           |



```sh
mao@ubuntu:~/桌面$ unzip -t a.zip
Archive:  a.zip
    testing: a.c                      OK
No errors detected in compressed data of a.zip.
mao@ubuntu:~/桌面$ unzip a.zip
Archive:  a.zip
replace a.c? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
  inflating: a.c                     
mao@ubuntu:~/桌面$ 
```





## gzip命令

gzip 是 Linux 系统中经常用来对文件进行压缩和解压缩的命令，通过此命令压缩得到的新文件，其扩展名通常标记为“.gz”

gzip 命令只能用来压缩文件，不能压缩目录，即便指定了目录，也只能压缩目录内的所有文件



命令：

```sh
[root@localhost ~]# gzip [选项] 源文件
```



| 选项  |                             含义                             |
| :---: | :----------------------------------------------------------: |
|  -c   |          将压缩数据输出到标准输出中，并保留源文件。          |
|  -d   |                    对压缩文件进行解压缩。                    |
|  -r   |          递归压缩指定目录下以及子目录下的所有文件。          |
|  -v   |    对于每个压缩和解压缩的文件，显示相应的文件名和压缩比。    |
|  -l   | 对每一个压缩文件，显示以下字段：1.压缩文件的大小；2.未压缩文件的大小；3.压缩比；4.未压缩文件的名称。 |
| -数字 | 用于指定压缩等级，-1 压缩等级最低，压缩比最差；-9 压缩比最高。默认压缩比是 -6。 |



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 100
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ gzip a.c
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  2764 12月 30  2021 a.c.gz
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ 

```





## gunzip命令

gunzip 是一个使用广泛的解压缩命令，它**用于解压被 gzip 压缩过的文件**



命令：

```sh
[root@localhost ~]# gunzip [选项] 文件
```



| 选项 |                        含义                        |
| :--: | :------------------------------------------------: |
|  -r  | 递归处理，解压缩指定目录下以及子目录下的所有文件。 |
|  -c  |        把解压缩后的文件输出到标准输出设备。        |
|  -f  |    强制解压缩文件，不理会文件是否已存在等情况。    |
|  -l  |                 列出压缩文件内容。                 |
|  -v  |                 显示命令执行过程。                 |
|  -t  |    测试压缩文件是否正常，但不对其做解压缩操作。    |



```sh
mao@ubuntu:~/桌面$ gunzip -l a.c.gz 
         compressed        uncompressed  ratio uncompressed_name
               2764                8859  69.0% a.c
mao@ubuntu:~/桌面$ gunzip a.c.gz 
mao@ubuntu:~/桌面$ ls -l
总用量 100
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ 

```





## bzip2命令

bzip2 命令同 gzip 命令类似，只能对文件进行压缩（或解压缩），对于目录只能压缩（或解压缩）该目录及子目录下的所有文件。当执行压缩任务完成后，会生成一个以“.bz2”为后缀的压缩包。

.bz2"格式的算法更先进、压缩比更好



命令：

```sh
[root@localhost ~]# bzip2 [选项] 源文件
```



| 选项  |                             含义                             |
| :---: | :----------------------------------------------------------: |
|  -d   | 执行解压缩，此时该选项后的源文件应为标记有 .bz2 后缀的压缩包文件。 |
|  -k   | bzip2 在压缩或解压缩任务完成后，会删除原始文件，若要保留原始文件，可使用此选项。 |
|  -f   | bzip2 在压缩或解压缩时，若输出文件与现有文件同名，默认不会覆盖现有文件，若使用此选项，则会强制覆盖现有文件。 |
|  -t   |                   测试压缩包文件的完整性。                   |
|  -v   |              压缩或解压缩文件时，显示详细信息。              |
| -数字 | 这个参数和 gzip 命令的作用一样，用于指定压缩等级，-1 压缩等级最低，压缩比最差；-9 压缩比最高 |



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 100
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ bzip2 a.c
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  2831 12月 30  2021 a.c.bz2
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ 

```





## bunzip2命令

**bz2格式的解压缩命令**



命令：

```sh
[root@localhost ~]# bunzip2 [选项] 源文件
```



| 选项 |                             含义                             |
| :--: | :----------------------------------------------------------: |
|  -k  | 解压缩后，默认会删除原来的压缩文件。若要保留压缩文件，需使用此参数。 |
|  -f  | 解压缩时，若输出的文件与现有文件同名时，默认不会覆盖现有的文件。若要覆盖，可使用此选项。 |
|  -v  |                      显示命令执行过程。                      |
|  -L  |                      列出压缩文件内容。                      |



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  2831 12月 30  2021 a.c.bz2
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ bunzip2 a.c.bz2
mao@ubuntu:~/桌面$ ls -l
总用量 100
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
mao@ubuntu:~/桌面$ 

```









# Vim文本编辑器



## 三种工作模式

3 种工作模式，分别是**命令模式、输入模式和编辑模式**



### 命令模式

使用 Vim 编辑文件时，默认处于命令模式。此模式下，可使用方向键（上、下、左、右键）或 k、j、h、i 移动光标的位置，还可以对文件内容进行复制、粘贴、替换、删除等操作

* 进入vim默认就是命令模式
* 从输入模式到命令模式：esc键
* 从编辑模式到命令模式：回车键
* 退出：输入ZZ



### 输入模式

在输入模式下，Vim 可以对文件执行写操作，类似于在 Windows 系统的文档中输入内容。

使 Vim 进行输入模式的方式是在**命令模式状态下输入 i、I、a、A、o、O** 等插入命令

当编辑文件完成后**按 Esc 键即可返回命令模式**



| 快捷键 |                           功能描述                           |
| :----: | :----------------------------------------------------------: |
|   i    | 在当前光标所在位置插入随后输入的文本，光标后的文本相应向右移动 |
|   I    | 在光标所在行的行首插入随后输入的文本，行首是该行的第一个非空白字符，相当于光标移动到行首执行 i 命令 |
|   o    | 在光标所在行的下面插入新的一行。光标停在空行首，等待输入文本 |
|   O    | 在光标所在行的上面插入新的一行。光标停在空行的行首，等待输入文本 |
|   a    |           在当前光标所在位置之后插入随后输入的文本           |
|   A    | 在光标所在行的行尾插入随后输入的文本，相当于光标移动到行尾再执行a命令 |





### 编辑模式

编辑模式用于对文件中的指定内容执行保存、查找或替换等操作

* 命令模式切换到编辑模式：按“：”键
* 返回命令模式，按 Esc 







## 基本操作



### 打开文件



命令：

```sh
[root@itxdl ~]# vim 文件名
```



|     Vi 使用的选项      |                       说 明                       |
| :--------------------: | :-----------------------------------------------: |
|      vim filename      |   打开或新建一个文件，并将光标置于第一行的首部    |
|    vim -r filename     |           恢复上次 vim 打开时崩溃的文件           |
|    vim -R filename     |      把指定的文件以只读方式放入 Vim 编辑器中      |
|     vim + filename     |       打开文件，并将光标置于最后一行的首部        |
|     vi +n filename     |        打开文件，并将光标置于第 n 行的首部        |
| vi +/pattern filename  | 打幵文件，并将光标置于第一个与 pattern 匹配的位置 |
| vi -c command filename |       在对文件进行编辑前，先执行指定的命令        |



```sh
mao@ubuntu:~/桌面$ vi a.c
```

```sh
               {
                        printf("debug: Slide left\n");
                        bmp_location_increase();
                }
                else if (location == 4)
                {
                        printf("debug: Slide right\n");
                        bmp_location_reduce();
                }
                else
                {
                        printf("debug: Slide error!\n");
                }

        }
        //¹Ø±ÕÆÁÄ»
        Lcd_close();
        return 0;
}




"a.c" [已转换][dos] 411L, 10627C                              400,1-8      底端
```





### 编辑

####  插入文本

从命令模式进入输入模式进行编辑，可以按下 I、i、O、o、A、a 等键来完成，使用不同的键，光标所处的位置不同



|  快捷键   |                           功能描述                           |
| :-------: | :----------------------------------------------------------: |
|     i     | 在当前光标所在位置插入随后输入的文本，光标后的文本相应向右移动 |
|     I     | 在光标所在行的行首插入随后输入的文本，行首是该行的第一个非空白字符，相当于光标移动到行首执行 i 命令 |
|     o     | 在光标所在行的下面插入新的一行。光标停在空行首，等待输入文本 |
| O（大写） | 在光标所在行的上面插入新的一行。光标停在空行的行首，等待输入文本 |
|     a     |           在当前光标所在位置之后插入随后输入的文本           |
|     A     | 在光标所在行的行尾插入随后输入的文本，相当于光标移动到行尾再执行 a 命令 |



```sh
int main()
{
        //³õÊ¼»¯ÆÁÄ»
        Lcd_init();
        Lcd_clear(0x00ffffff);
        while (1)
        {
                int location = Get_Fingler_Direction();
                if (location == 1)
                {
                        printf("debug: Slide up\n");
                }
                else if (location == 2)
                {
                        printf("debug: Slide down\n");
                }
                else if (location == 3)
                {
                        printf("debug: Slide left\n");
                        bmp_location_increase();
                }
                else if (location == 4)
-- 插入 --                                                    387,1         95%
```



#### 查找文本

| 快捷键 |             功能描述             |
| :----: | :------------------------------: |
|  /abc  | 从光标所在位置向前查找字符串 abc |
| /^abc  |      查找以 abc 为行首的行       |
| /abc$  |      查找以 abc 为行尾的行       |
|  ?abc  | 从光标所在为主向后查找字符串 abc |
|   n    |   向同一方向重复上次的查找指令   |
|   N    |   向相反方向重复上次的查找指定   |



```sh
       {
                Lcd_draw_bmp("10.bmp", 800, 480, 0, 0);
                bmp_location = 10;
        }
        else
        {
                printf("reduce error! \a \n");
        }
}


int main()
{
        //³õÊ¼»¯ÆÁÄ»
        Lcd_init();
        Lcd_clear(0x00ffffff);
        while (1)
        {
                int location = Get_Fingler_Direction();
                if (location == 1)
                {
                        printf("debug: Slide up\n");
                }
/main
```



* 如果想忽略大小写，则输入命令 ":set ic"；调整回来输入":set noic"

* 如果在字符串中出现特殊符号，则需要加上转义字符 "\"。常见的特殊符号有 \、*、?、$ 等。如果出现这些字符，例如，要查找字符串 "10$"，则需要在命令模式中输入 "/10\$"





####  替换文本



|     快捷键      |                           功能描述                           |
| :-------------: | :----------------------------------------------------------: |
|        r        |                    替换光标所在位置的字符                    |
|        R        | 从光标所在位置开始替换字符，其输入内容会覆盖掉后面等长的文本内容，按“Esc”可以结束 |
|   :s/a1/a2/g    |            将当前光标所在行中的所有 a1 用 a2 替换            |
| :n1,n2s/a1/a2/g |          将文件中 n1 到 n2 行中所有 a1 都用 a2 替换          |
|   :g/a1/a2/g    |                将文件中所有的 a1 都用 a2 替换                |





#### 删除文本



| 快捷键  |                功能描述                |
| :-----: | :------------------------------------: |
|    x    |         删除光标所在位置的字符         |
|   dd    |             删除光标所在行             |
|   ndd   |   删除当前行（包括此行）后 n 行文本    |
|   dG    | 删除光标所在行一直到文件末尾的所有内容 |
|    D    |        删除光标位置到行尾的内容        |
| :a1,a2d |     函数从 a1 行到 a2 行的文本内容     |



被删除的内容并没有真正删除，都放在了剪贴板中。将光标移动到指定位置处，按下 "p" 键，就可以将刚才删除的内容又粘贴到此处



#### 复制和粘贴文本



|  快捷键   |                          功能描述                          |
| :-------: | :--------------------------------------------------------: |
|     p     |                将剪贴板中的内容粘贴到光标后                |
| P（大写） |                将剪贴板中的内容粘贴到光标前                |
|     y     |                  复制已选中的文本到剪贴板                  |
|    yy     | 将光标所在行复制到剪贴板，此命令前可以加数字 n，可复制多行 |
|    yw     |                将光标位置的单词复制到剪贴板                |





#### 其他常用快捷键



| 快捷键 |       功能描述       |
| :----: | :------------------: |
|   J    |    把两行进行连接    |
|   u    | 撤销上一次执行的命令 |



```sh
               {
                        printf("debug: Slide left\n");
                        bmp_location_increase();
                }
                else if (location == 4)
                {
                        printf("debug: Slide right\n");
                        bmp_location_reduce();
                }
                else
                {
                        printf("debug: Slide error!\n");
                }

        }
        //¹Ø±ÕÆÁÄ»
        Lcd_close();
        return 0;
}




                                                              396,1-8      底端
```

```sh
                {
                        printf("debug: Slide left\n");
                        bmp_location_increase();
                }
                else if (location == 4)
                {
                        printf("debug: Slide right\n");
                        bmp_location_reduce();
                }
                else
                { printf("debug: Slide error!\n");
                }

        }
        //¹Ø±ÕÆÁÄ»
        Lcd_close();
        return 0;
}




~                                                                               
                                                              399,4-18     底端
```

```sh
               {
                        printf("debug: Slide left\n");
                        bmp_location_increase();
                }
                else if (location == 4)
                {
                        printf("debug: Slide right\n");
                        bmp_location_reduce();
                }
                else
                { 
                        printf("debug: Slide error!\n");
                }

        }
        //¹Ø±ÕÆÁÄ»
        Lcd_close();
        return 0;
}




1 行被加入；before #1  30 seconds ago                         399,3-17     底端
```







### 保存退出文本



|    命令     |                      功能描述                      |
| :---------: | :------------------------------------------------: |
|     :wq     |               保存并退出 Vim 编辑器                |
|    :wq!     |             保存并强制退出 Vim 编辑器              |
|     :q      |              不保存就退出 Vim 编辑器               |
|     :q!     |           不保存，且强制退出 Vim 编辑器            |
|     :w      |             保存但是不退出 Vim 编辑器              |
|     :w!     |                    强制保存文本                    |
| :w filename |                另存到 filename 文件                |
|     x！     | 保存文本，并退出 Vim 编辑器，更通用的一个 vim 命令 |
|     ZZ      |                直接退出 Vim 编辑器                 |



```sh
               {
                        printf("debug: Slide left\n");
                        bmp_location_increase();
                }
                else if (location == 4)
                {
                        printf("debug: Slide right\n");
                        bmp_location_reduce();
                }
                else
                { 
                        printf("debug: Slide error!\n");
                }

        }
        //¹Ø±ÕÆÁÄ»
        Lcd_close();
        return 0;
}




:q
```

```sh
mao@ubuntu:~/桌面$ vi a.c
mao@ubuntu:~/桌面$ 
```







## 移动光标



### 快捷方向键



| 快捷键 |                        功能描述                        |
| :----: | :----------------------------------------------------: |
|   h    |                    光标向左移动一位                    |
|   j    | 光标向下移动一行（以回车为换行符），也就是光标向下移动 |
|   k    |           光标向上移动一行（也就是向上移动）           |
|   l    |                    光标向右移动一位                    |





### 光标以单词为单位移动



|  快捷键  |              功能描述               |
| :------: | :---------------------------------: |
|  w 或 W  |    光标移动至下一个单词的单词首     |
|  b 或 B  |    光标移动至上一个单词的单词首     |
|  e 或 E  |    光标移动至下一个单词的单词尾     |
| nw 或 nW | n 为数字，表示光标向右移动 n 个单词 |
| nb 或 nB | n 为数字，表示光标向左移动 n 个单词 |



### 光标移动至行首或行尾



| 快捷键 |                 功能描述                 |
| :----: | :--------------------------------------: |
| 0 或 ^ |          光标移动至当前行的行首          |
|   $    |          光标移动至当前行的行尾          |
|   n$   | 光标移动至当前行只有 n 行的行尾，n为数字 |



### 光标移动至指定字符



| 快捷键 |             功能描述              |
| :----: | :-------------------------------: |
|   fx   | 光标移动至当前行中下一个 x 字符处 |
|   Fx   | 光标移动至当前行中下一个 x 字符处 |



### 光标移动到指定行



| 快捷键 |                         功能描述                         |
| :----: | :------------------------------------------------------: |
|   gg   |                    光标移动到文件开头                    |
|   G    |                    光标移动至文件末尾                    |
|   nG   |               光标移动到第 n 行，n 为数字                |
|   :n   | 编辑模式下使用的快捷键，可以将光标快速定义到指定行的行首 |



### 光标移动到匹配的括号处



使用命令：%



```sh
       ²ÎÊý: ÎÞ
        ·µ»ØÖµ: ·µ»Ø·½Ïò
                enum Mov_Dir
*/
enum Mov_Dir  Get_Fingler_Direction(void)
{
        int x1 = -1, y1 = -1;
        int x2, y2;

        //1.´ò¿ª´¥ÃþÆÁÎÄ¼þ
        int fd_input;
        fd_input = open("/dev/input/event0", O_RDWR);
        if (fd_input == -1)
        {

        }

        //2.²»¶ÏµØ»ñÈ¡ÊäÈëÊÂ¼þµÄÊý¾ÝÐÅÏ¢£¬
        //      ²¢ÇÒ½«Æä±£´æÖÁ struct input_event 
                                                          30,1           6%
```

```sh
                                else
                                {
                                        //ÏòÏÂ£¬·µ»Ø1
                                        return MOVE_UP;
                                }
                        }
                }
        }
        //3.¹Ø±ÕÎÄ¼þ
}

/*
Lcd_init:³õÊ¼»¯LCDÆÁÄ»
*/
void Lcd_init()
{
        //´ò¿ªÆÁÄ»ÎÄ¼þ(open)
        fd = open("/dev/fb0", O_RDWR);
        if (fd == -1)
                                                          112,1         26%
```





## 撤销和恢复撤销



|  快捷键   |                             功能                             |
| :-------: | :----------------------------------------------------------: |
| u（小写） |  undo 的第 1 个字母，功能是撤销最近一次对文本做的修改操作。  |
|  Ctrl+R   |    Redo 的第 1 个字母，功能是恢复最近一次所做的撤销操作。    |
| U（大写） | 第一次会撤销对一行文本（光标所在行）做过的全部操作，第二次使用该命令会恢复对该行文本做过的所有操作。 |





## 可视化模式



|       命令       |                             功能                             |
| :--------------: | :----------------------------------------------------------: |
|    v（小写）     | 又称字符可视化模式，此模式下目标文本的选择是以字符为单位的，也就是说，该模式下要一个字符一个字符的选中要操作的文本。 |
|    V（大写）     | 又称行可视化模式，此模式化目标文本的选择是以行为单位的，也就是说，该模式化可以一行一行的选中要操作的文本。 |
| Ctrl+v（组合键） | 又称块可视化模式，该模式下可以选中文本中的一个矩形区域作为目标文本，以按下 Ctrl+v 位置作为矩形的一角，光标移动的终点位置作为它的对角。 |



|   命令    |                             功能                             |
| :-------: | :----------------------------------------------------------: |
|     d     |                     删除选中的部分文本。                     |
|     D     | 删除选中部分所在的行，和 d 不同之处在于，即使选中文本中有些字符所在的行没有都选中，删除时也会一并删除。 |
|     y     |                  将选中部分复制到剪贴板中。                  |
| p（小写） |               将剪贴板中的内容粘贴到光标之后。               |
| P（大写） |               将剪贴板中的内容粘贴到光标之前。               |
| u（小写） |           将选中部分中的大写字符全部改为小写字符。           |
| U（大写） |           将选中部分中的小写字符全部改为大写字符。           |
|     >     | 将选中部分右移（缩进）一个 tab 键规定的长度（CentOS 6.x 中，一个tab键默认相当于 8 个空白字符的长度）。 |
|     <     | 将选中部分左移一个 tab 键规定的长度（CentOS 6.x 中，一个tab键默认相当于 8 个空白字符的长度）。 |



```sh
                {
                        if (y1 == -1)
                        {
                                y1 = ev.value;
                        }
                        y2 = ev.value; 
                } 
 
                //»¬¶¯½áÊø£¬±æ±ð·½Ïò 
                if (ev.type == EV_KEY && ev.code == BTN_TOUCH && ev.value == 0) 
                { 
                        int deltx = abs(x2 - x1); 
                        int delty = abs(y2 - y1); 
 
                        close(fd_input); 
 
                        if (deltx > delty) 
                        { 
-- 可视 --                                      35        70,4-25       16%
```

```sh
               }
                //absolute ¾ø¶ÔÊÂ¼þ(´¥ÃþÆÁÊÂ¼þ)  ´¥ÃþÆÁ°´¼ü x
                if (ev.type == EV_ABS && ev.code == ABS_X)
                {
                        if (x1 == -1)
                        {
                                //value ±íÊ¾°´ÏÂµÄ×´Ì¬ ,1 °´ÏÂ×´Ì¬,0 µ¯Æð×´Ì¬ 
                                x1 = ev.value; 
                        } 
                        x2 = ev.value; 
                } 
                //absolute ¾ø¶ÔÊÂ¼þ(´¥ÃþÆÁÊÂ¼þ)  ´¥ÃþÆÁ°´¼ü y 
                if (ev.type == EV_ABS && ev.code == ABS_Y) 
                { 
                        if (y1 == -1) 
                        { 
                                y1 = ev.value; 
                        }
-- 可视 行 --                                   12        57,5-26       12%
```

```sh
                                //value ±íÊ¾°´ÏÂµÄ×´Ì¬ ,1 °´ÏÂ×´Ì¬,0 µ¯Æð×´Ì¬
                                x1 = ev.value;
                        }
                        x2 = ev.value;
                }
                //absolute ¾ø¶ÔÊÂ¼þ(´¥ÃþÆÁÊÂ¼þ)  ´¥ÃþÆÁ°´¼ü y
                if (ev.type == EV_ABS && ev.code == ABS_Y)
                {
                        if (y1 == -1)
                        {
                                y1 = ev.value;
                        }
                        y2 = ev.value;
                }

                //»¬¶¯½áÊø£¬±æ±ð·½Ïò
                if (ev.type == EV_KEY && ev.code == BTN_TOUCH && ev.value == 0)
-- 可视 块 --                                   12x15     68,11-39      14%
```





## 显示行号



|          设置参数           |                            含 义                             |
| :-------------------------: | :----------------------------------------------------------: |
|      :set nu :set nonu      |                       设置与取消行号。                       |
|      :syn on :syn off       | 是否依据语法显示相关的颜色帮助。在Vim中修改相关的配置文件或Shell脚本文件 时（如前面示例的脚本/etc/init.d/sshd)，默认会显示相应的颜色，用来帮助排错。如果觉得颜色产生了干扰，则可以取消此设置 |
| set hlsearch set nohlsearch |    设置是否将査找的字符串高亮显示。默认是hlsearch高亮显示    |
|   set nobackup set backup   | 是否保存自动备份文件。默认是nobackup不自动备份。如果设定了:set backup，则会产生“文件名〜”作为备份文件 |
|    set ruler set noruler    |         设置是否显示右下角的状态栏。默认是ruler显示          |
| set showmode set noshowmode | 设置是否在左下角显示如“一INSERT--”之类的状态栏。默认是showmode显示 |



```sh
{
        int i, j;
        for (j = y; j < y + h; j++) //Ã¿Ò»ÐÐ
        {
                for (i = x; i < x + w; i++) //Ã¿Ò»ÐÐµÄÃ¿Ò»¸öµã
                {
                        Lcd_draw_point(i, j, color);
                }
        }
}

int Lcd_draw_bmp(char* name, int w, int h, int x, int y)
{
        int fd_bmp = open(name, O_RDWR);
        if (fd_bmp == -1)
        {
                printf("open bmp error\n");
                return -1;
        }
                                                          212,1-8       52%
```

```sh
{
        int i, j;
        for (j = y; j < y + h; j++) //Ã¿Ò»ÐÐ
        {
                for (i = x; i < x + w; i++) //Ã¿Ò»ÐÐµÄÃ¿Ò»¸öµã
                {
                        Lcd_draw_point(i, j, color);
                }
        }
}

int Lcd_draw_bmp(char* name, int w, int h, int x, int y)
{
        int fd_bmp = open(name, O_RDWR);
        if (fd_bmp == -1)
        {
                printf("open bmp error\n");
                return -1;
        }
:set nu
```

```sh
207 {
208         int i, j;
209         for (j = y; j < y + h; j++) //Ã¿Ò»ÐÐ
210         {
211                 for (i = x; i < x + w; i++) //Ã¿Ò»ÐÐµÄÃ¿Ò»¸öµã
212                 {
213                         Lcd_draw_point(i, j, color);
214                 }
215         }
216 }
217 
218 int Lcd_draw_bmp(char* name, int w, int h, int x, int y)
219 {
220         int fd_bmp = open(name, O_RDWR);
221         if (fd_bmp == -1)
222         {
223                 printf("open bmp error\n");
224                 return -1;
225         }
:set nu                                                   212,1-8       52%
```





## 配置文件.vimrc

Vim 启动时，会根据配置文件（.vimrc）来设置 Vim，因此我们可以通过此文件来定制适合自己的 Vim



Vim 配置文件分为系统配置文件和用户配置文件：

- 系统配置文件位于 Vim 的安装目录（默认路径为 /etc/.vimrc）；
- 用户配置文件位于主目录 ~/.vimrc，即通过执行 `vim ~/.vimrc` 命令即可对此配置文件进行合理修改。通常情况下，Vim 用户配置文件需要自己手动创建。



Vim 用户配置文件比系统配置文件的优先级高



在 Vim 编辑模式中，通过 “:set nu” 命令也可以让 Vim 显示行号，但只是临时有效，下次使用 Vim 编辑文件还是不显示行号。

永久自定义配置，需要对配置文件（.vimrc）进行编辑





## 执行Linux命令



|    格式     |                             功能                             |
| :---------: | :----------------------------------------------------------: |
|   :!命令    |  直接运行一个 Linux 命令，运行完毕之后，即可返回到 Vim 中。  |
|   :w!命令   | 将 Vim 中所有的文本内容作为指定命令的输入。但命令的执行结果不会写入到当前文件中。 |
|   :r!命令   | 将命令执行的结果写入到当前 Vim 中，例如 :!ls 表示将 ls 的执行结果输入到 Vim 中。 |
|  :nr!命令   | 其中 n 为数字，表示将命令的执行结果写入到 Vim 第 n 行的位置。例如，:3r!date 表示将 date 命令的执行结果写入到第 3 行文本处。 |
|  :n,m!命令  | 其中 n 表示起始行号，m为结束行号，功能是将 Vim 中指定的部分文本作为某个命令的输入，同时将命令的输出也插入到当前指定的位置。 |
| :n,m w!命令 | 其中 n 表示起始行号，m为结束行号，其功能是 Vim 中指定的部分文本作为某个命令的输入，但命令的执行结果不会写入到文件中。 |
|   !!date    |                   向 Vim 中插入当前时间。                    |



```sh
393                 else if (location == 4)
394                 {
395                         printf("debug: Slide right\n");
396                         bmp_location_reduce();
397                 }
398                 else
399                 {
400                         printf("debug: Slide error!\n");
401                 }
402 
403         }
404         //¹Ø±ÕÆÁÄ»
405         Lcd_close();
406         return 0;
407 }
408 
409 
410 
411 
                                                          411,0-1      底端
```

```sh
393                 else if (location == 4)
394                 {
395                         printf("debug: Slide right\n");
396                         bmp_location_reduce();
397                 }
398                 else
399                 {
400                         printf("debug: Slide error!\n");
401                 }
402 
403         }
404         //¹Ø±ÕÆÁÄ»
405         Lcd_close();
406         return 0;
407 }
408 
409 
410 
411 2022年 07月 02日 星期六 07:04:17 PDT
:.!date                                                   411,1        底端
```









# 文本处理



## cat命令

cat 命令可以**用来显示文本文件的内容**

也可以**把几个文件内容附加到另一个文件中**，即连接合并文件



命令：

```sh
[root@localhost ~]# cat [选项] 文件名
或者
[root@localhost ~]# cat 文件1 文件2 > 文件3
```



| 选项 |                           含义                           |
| :--: | :------------------------------------------------------: |
|  -A  |      相当于 -vET 选项的整合，用于列出所有隐藏符号；      |
|  -E  |                 列出每行结尾的回车符 $；                 |
|  -n  |                 对输出的所有行进行编号；                 |
|  -b  |        同 -n 不同，此选项表示只对非空行进行编号。        |
|  -T  |                 把 Tab 键 ^I 显示出来；                  |
|  -V  |                      列出特殊字符；                      |
|  -s  | 当遇到有连续 2 行以上的空白行时，就替换为 1 行的空白行。 |



```sh
mao@ubuntu:~/桌面$ touch in.txt
mao@ubuntu:~/桌面$ touch in2.txt
mao@ubuntu:~/桌面$ vi in.txt
mao@ubuntu:~/桌面$ vi in2.txt
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ cat in.txt
12345

mao@ubuntu:~/桌面$ cat in2.txt
67890
mao@ubuntu:~/桌面$ cat -n in.txt
     1	12345
     2	
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ cat in.txt in2.txt >out.txt
mao@ubuntu:~/桌面$ ls -l
总用量 112
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao mao     6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao mao     7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao    13 7月   2 21:52 out.txt
mao@ubuntu:~/桌面$ cat -n out.txt
     1	12345
     2	
     3	67890
mao@ubuntu:~/桌面$ 
```





## more命令

more 命令可以**分页显示文本文件的内容**



命令：

```sh
[root@localhost ~]# more [选项] 文件名
```



| 选项 |                           含义                           |
| :--: | :------------------------------------------------------: |
|  -f  |   计算行数时，以实际的行数，而不是自动换行过后的行数。   |
|  -p  |  不以卷动的方式显示每一页，而是先清除屏幕后再显示内容。  |
|  -c  |   跟 -p 选项相似，不同的是先显示内容再清除其他旧资料。   |
|  -s  |  当遇到有连续两行以上的空白行时，就替换为一行的空白行。  |
|  -u  | 不显示下引号（根据环境变量 TERM 指定的终端而有所不同）。 |
|  +n  |         从第 n 行开始显示文件内容，n 代表数字。          |
|  -n  |               一次显示的行数，n 代表数字。               |



more 命令的执行会打开一个交互界面



|      交互指令       |             功能             |
| :-----------------: | :--------------------------: |
|       h 或 ？       | 显示 more 命令交互命令帮助。 |
|       q 或 Q        |         退出 more。          |
|          v          |   在当前行启动一个编辑器。   |
|         :f          | 显示当前文件的文件名和行号。 |
| !<命令> 或 :!<命令> |  在子Shell中执行指定命令。   |
|       回车键        |        向下移动一行。        |
|       空格键        |        向下移动一页。        |
|       Ctrl+l        |          刷新屏幕。          |
|          =          |      显示当前行的行号。      |
|          '          |  转到上一次搜索开始的地方。  |
|       Ctrf+f        |        向下滚动一页。        |
|          .          |     重复上次输入的命令。     |
|      / 字符串       |      搜索指定的字符串。      |
|          d          |        向下移动半页。        |
|          b          |        向上移动一页。        |



```sh
mao@ubuntu:~/桌面$ more a.c
#include <stdio.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
#include <unistd.h>
#include <sys/mman.h>

//ȫ�ֱ���
int fd;  //��ʾ��Ļ���ļ�������
int* plcd = NULL; //��Ļӳ�����ڴ��׵�ַ
int bmp_location = 1;                      //��ǰλ�ڵڼ���ͼƬ��1��ʾ��ǰλ�ڵ�1��ͼƬ

enum Mov_Dir
{
	MOVE_UP = 1,
	MOVE_DOWN,
	MOVE_LEFT,
	MOVE_RIGHT
};

#define BTN_TOUCH 0x14a //���������� 

/*
--更多--(4%)
```





## head命令

head 命令可以**显示指定文件前若干行的文件内容**



```sh
[root@localhost ~]# head [选项] 文件名
```



| 选项 |                             含义                             |
| :--: | :----------------------------------------------------------: |
| -n K | 这里的 K 表示行数，该选项用来显示文件前 K 行的内容；如果使用 "-K" 作为参数，则表示除了文件最后 K 行外，显示剩余的全部内容。 |
| -c K | 这里的 K 表示字节数，该选项用来显示文件前 K 个字节的内容；如果使用 "-K"，则表示除了文件最后 K 字节的内容，显示剩余全部内容。 |
|  -v  |                         显示文件名；                         |



```sh
mao@ubuntu:~/桌面$ head -n 10 a.c
#include <stdio.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
#include <unistd.h>
#include <sys/mman.h>

//ȫ�ֱ���
int fd;  //��ʾ��Ļ���ļ�������
int* plcd = NULL; //��Ļӳ�����ڴ��׵�ַ
mao@ubuntu:~/桌面$ head -10 a.c
#include <stdio.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
#include <unistd.h>
#include <sys/mman.h>

//ȫ�ֱ���
int fd;  //��ʾ��Ļ���ļ�������
int* plcd = NULL; //��Ļӳ�����ڴ��׵�ַ
mao@ubuntu:~/桌面$ head -c 10 a.c
#include <mao@ubuntu:~/桌面$ head -20 a.c
#include <stdio.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
#include <unistd.h>
#include <sys/mman.h>

//ȫ�ֱ���
int fd;  //��ʾ��Ļ���ļ�������
int* plcd = NULL; //��Ļӳ�����ڴ��׵�ַ
int bmp_location = 1;                      //��ǰλ�ڵڼ���ͼƬ��1��ʾ��ǰλ�ڵ�1��ͼƬ

enum Mov_Dir
{
	MOVE_UP = 1,
	MOVE_DOWN,
	MOVE_LEFT,
	MOVE_RIGHT
};

mao@ubuntu:~/桌面$ 
```





## less命令

less 命令的作用和 more 十分类似，都用来浏览文本文件中的内容，不同之处在于，使用 more 命令浏览文件内容时，只能不断向后翻看，而使用 less 命令浏览，既可以向后翻看，也可以向前翻看。



less 命令还提供了以下几个功能：

- 使用光标键可以在文本文件中前后（左后）滚屏；
- 用行号或百分比作为书签浏览文件；
- 提供更加友好的检索、高亮显示等操作；
- 兼容常用的字处理程序（如 Vim、Emacs）的键盘操作；
- 阅读到文件结束时，less 命令不会退出；
- 屏幕底部的信息提示更容易控制使用，而且提供了更多的信息。



命令：

```sh
[root@localhost ~]# less [选项] 文件名
```



|      选项       |                        选项含义                        |
| :-------------: | :----------------------------------------------------: |
|       -N        |                    显示每行的行号。                    |
|       -S        |                行过长时将超出部分舍弃。                |
|       -e        |              当文件显示结束后，自动离开。              |
|       -g        |               只标志最后搜索到的关键同。               |
|       -Q        |                     不使用警告音。                     |
|       -i        |                  忽略搜索时的大小写。                  |
|       -m        |              显示类似 more 命令的百分比。              |
|       -f        | 强迫打开特殊文件，比如外围设备代号、目录和二进制文件。 |
|       -s        |                  显示连续空行为一行。                  |
| -b <缓冲区大小> |                   设置缓冲区的大小。                   |
|   -o <文件名>   |          将 less 输出的内容保存到指定文件中。          |
|    -x <数字>    |            将 Tab 键显示为规定的数字空格。             |







在使用 less 命令查看文件内容的过程中，和 more 命令一样，也会进入交互界面



|  交互指令  |                  功能                  |
| :--------: | :------------------------------------: |
|  /字符串   |        向下搜索“字符串”的功能。        |
|  ?字符串   |        向上搜索“字符串”的功能。        |
|     n      |  重复*前一个搜索（与 / 成 ? 有关）。   |
|     N      | 反向重复前一个搜索（与 / 或 ? 有关）。 |
|     b      |             向上移动一页。             |
|     d      |             向下移动半页。             |
|   h 或 H   |             显示帮助界面。             |
|   q 或 Q   |            退出 less 命令。            |
|     y      |             向上移动一行。             |
|   空格键   |             向下移动一页。             |
|   回车键   |             向下移动一行。             |
| 【PgDn】键 |             向下移动一页。             |
| 【PgUp】键 |             向上移动一页。             |
|   Ctrl+f   |             向下移动一页。             |
|   Ctrl+b   |             向上移动一页。             |
|   Ctrl+d   |             向下移动一页。             |
|   Ctrl+u   |             向上移动半页。             |
|     j      |             向下移动一行。             |
|     k      |             向上移动一行。             |
|     G      |            移动至最后一行。            |
|     g      |             移动到第一行。             |
|     ZZ     |            退出 less 命令。            |
|     v      |     使用配置的编辑器编辑当前文件。     |
|     [      |       移动到本文档的上一个节点。       |
|     ]      |       移动到本文档的下一个节点。       |
|     p      |        移动到同级的上一个节点。        |
|     u      |             向上移动半页。             |



```sh
mao@ubuntu:~/桌面$ ^C
mao@ubuntu:~/桌面$ less -N a.c
"a.c" may be a binary file.  See it anyway? 
```

```sh
      8 //ȫ<BE>ֱ<E4><C1><BF>
      9 int fd;  //<B1><ED>ʾ<C6><C1>Ļ<B5><C4><CE>ļ<FE><C3><E8><CA><F6><B7><FB>
     10 int* plcd = NULL; //<C6><C1>Ļӳ<C9><E4><BA><F3><B5><C4><C4>ڴ<E6><CA>׵<D8>ַ
     11 int bmp_location = 1;                      //<B5><B1>ǰλ<D3>ڵڼ<B8><D5>
     11 <C5>ͼƬ<A3><AC>1<B1><ED>ʾ<B5><B1>ǰλ<D3>ڵ<DA>1<D5><C5>ͼƬ
     12 
     13 enum Mov_Dir
     14 {
     15         MOVE_UP = 1,
     16         MOVE_DOWN,
     17         MOVE_LEFT,
     18         MOVE_RIGHT
     19 };
     20 
     21 #define BTN_TOUCH 0x14a //<B4><A5><C3><FE><C6><C1><B0><B4><BC><FC> 
     22 
     23 /*
     24         Get_Fingler_Direction : <BB><F1>ȡ<D3>û<A7><CA><D6>ָ<BB><AC><B6>
     24 <AF><B5>ķ<BD><CF><F2>
     25         <B2><CE><CA><FD>: <CE><DE>
     26         <B7><B5><BB><D8>ֵ: <B7><B5><BB>ط<BD><CF><F2>
     27                 enum Mov_Dir
     28 */
:
```







## tail命令

tail 命令和 head 命令正好相反，它用来**查看文件末尾的数据**



命令：

```sh
[root@localhost ~]# tail [选项] 文件名
```



| 选项 |                             含义                             |
| :--: | :----------------------------------------------------------: |
| -n K | 这里的 K 指的是行数，该选项表示输出最后 K 行，在此基础上，如果使用 -n +K，则表示从文件的第 K 行开始输出。 |
| -c K | 这里的 K 指的是字节数，该选项表示输出文件最后 K 个字节的内容，在此基础上，使用 -c +K 则表示从文件第 K 个字节开始输出。 |
|  -f  |                 输出文件变化后新增加的数据。                 |



```sh
mao@ubuntu:~/桌面$ tail -n 15 a.c
		}
		else
		{
			printf("debug: Slide error!\n");
		}

	}
	//�ر���Ļ
	Lcd_close();
	return 0;
}




mao@ubuntu:~/桌面$ tail -20 a.c
		}
		else if (location == 4)
		{
			printf("debug: Slide right\n");
			bmp_location_reduce();
		}
		else
		{
			printf("debug: Slide error!\n");
		}

	}
	//�ر���Ļ
	Lcd_close();
	return 0;
}




mao@ubuntu:~/桌面$ tail -c -30 a.c
se();
	return 0;
}




mao@ubuntu:~/桌面$ 
```





## 重定向

Linux 中标准的输入设备默认指的是键盘，标准的输出设备默认指的是显示器

- 输入重定向：指的是重新指定设备来代替键盘作为新的输入设备；
- 输出重定向：指的是重新指定设备来代替显示器作为新的输出设备。



通常是用文件或命令的执行结果来代替键盘作为新的输入设备，而新的输出设备通常指的就是文件。



### 输入重定向



|      命令符号格式      |                             作用                             |
| :--------------------: | :----------------------------------------------------------: |
|      命令 < 文件       |                 将指定文件作为命令的输入设备                 |
|     命令 << 分界符     | 表示从标准输入设备（键盘）中读入，直到遇到分界符才停止（读入的数据不包括分界符），这里的分界符其实就是自定义的字符串 |
| 命令 < 文件 1 > 文件 2 | 将文件 1 作为命令的输入设备，该命令的执行结果输出到文件 2 中。 |



```sh
mao@ubuntu:~/桌面$ cat in.txt
12345

mao@ubuntu:~/桌面$ cat < in.txt
12345

mao@ubuntu:~/桌面$ 
```



虽然执行结果相同，但第一行代表是以键盘作为输入设备，而第二行代码是以文件作为输入设备。



```sh
mao@ubuntu:~/桌面$ cat << /
> we
> w
> q
> t
> u
> 7
> 6
> 5
> 566554gy
> /
we
w
q
t
u
7
6
5
566554gy
mao@ubuntu:~/桌面$ 
```



当指定了 / 作为分界符之后，只要不输入 /，就可以一直输入数据



```sh
mao@ubuntu:~/桌面$ ls -l < in.txt > out.txt
mao@ubuntu:~/桌面$ cat out.txt
总用量 108
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao mao     6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao mao     7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao     0 7月   2 22:19 out.txt
mao@ubuntu:~/桌面$ 
```





### 输出重定向

输出重定向还可以细分为标准输出重定向和错误输出重定向两种技术



|             命令符号格式             |                             作用                             |
| :----------------------------------: | :----------------------------------------------------------: |
|             命令 > 文件              | 将命令执行的标准输出结果重定向输出到指定的文件中，如果该文件已包含数据，会清空原有数据，再写入新数据。 |
|             命令 2> 文件             | 将命令执行的错误输出结果重定向到指定的文件中，如果该文件中已包含数据，会清空原有数据，再写入新数据。 |
|             命令 >> 文件             | 将命令执行的标准输出结果重定向输出到指定的文件中，如果该文件已包含数据，新数据将写入到原有内容的后面。 |
|            命令 2>> 文件             | 将命令执行的错误输出结果重定向到指定的文件中，如果该文件中已包含数据，新数据将写入到原有内容的后面。 |
| 命令 >> 文件 2>&1 或者 命令 &>> 文件 | 将标准输出或者错误输出写入到指定文件，如果该文件中已包含数据，新数据将写入到原有内容的后面。注意，第一种格式中，最后的 2>&1 是一体的，可以认为是固定写法。 |





```sh
mao@ubuntu:~/桌面$ cat out.txt 
mao@ubuntu:~/桌面$ ls -l
总用量 108
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao mao     6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao mao     7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao     0 7月   2 22:22 out.txt
mao@ubuntu:~/桌面$ ls -l > out.txt
mao@ubuntu:~/桌面$ cat out.txt 
总用量 108
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao mao     6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao mao     7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao     0 7月   2 22:23 out.txt
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ ls -l >> out.txt 
mao@ubuntu:~/桌面$ cat out.txt 
总用量 108
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao mao     6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao mao     7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao     0 7月   2 22:23 out.txt
总用量 112
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao 20480 7月   2 04:37 a.tar
-rw-rw-r-- 1 mao mao  2898 7月   2 04:51 a.zip
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao mao     6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao mao     7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao   834 7月   2 22:23 out.txt
mao@ubuntu:~/桌面$ 
```







## grep命令

**查找文件内容**

很多时候，我们并不需要列出文件的全部内容，而是从文件中找到包含指定信息的那些行

grep 命令的由来可以追溯到 UNIX 诞生的早期，在 UNIX 系统中，搜索的模式（patterns）被称为正则表达式（regular expressions），为了要彻底搜索一个文件，有的用户在要搜索的字符串前加上前缀 global（全面的），一旦找到相匹配的内容，用户就像将其输出（print）到屏幕上，而将这一系列的操作整合到一起就是 global regular expressions print，而这也就是 grep 命令的全称。



| 通配符 |                        功能                         |
| :----: | :-------------------------------------------------: |
|   c*   | 将匹配 0 个（即空白）或多个字符 c（c 为任一字符）。 |
|   .    |       将匹配任何一个字符，且只能是一个字符。        |
| [xyz]  |            匹配方括号中的任意一个字符。             |
| [^xyz] |          匹配除方括号中字符外的所有字符。           |
|   ^    |                   锁定行的开头。                    |
|   $    |                   锁定行的结尾。                    |



在基本正则表达式中，如通配符 *、+、{、|、( 和 )等，已经失去了它们原本的含义，而若要恢复它们原本的含义，则要在之前添加反斜杠 \，如：

```sh
 \*、\+、\{、\|、\( 和 \)
```



grep 命令是用来在每一个文件或中（或特定输出上）搜索特定的模式，当使用 grep 时，包含指定字符模式的每一行内容，都会被打印（显示）到屏幕上，但是使用 grep 命令并不改变文件中的内容。



命令：

```sh
[root@localhost ~]# grep [选项] 模式 文件名
```



| 选项 |                            含义                            |
| :--: | :--------------------------------------------------------: |
|  -c  |                仅列出文件中包含模式的行数。                |
|  -i  |                  忽略模式中的字母大小写。                  |
|  -l  |                  列出带有匹配行的文件名。                  |
|  -n  |                 在每一行的最前面列出行号。                 |
|  -v  |                   列出没有匹配模式的行。                   |
|  -w  | 把表达式当做一个完整的单字符来搜寻，忽略那些部分匹配的行。 |



```sh
mao@ubuntu:~/桌面$ grep -n main a.c
372:int main()
mao@ubuntu:~/桌面$ grep -n printf a.c
123:		printf("open lcd failed\n");
152:		printf("mmap failed\n");
184:		printf("bro,your point out of the LCD\n");
223:		printf("open bmp error\n");
309:		printf("increase error! \a \n");
367:		printf("reduce error! \a \n");
382:			printf("debug: Slide up\n");
386:			printf("debug: Slide down\n");
390:			printf("debug: Slide left\n");
395:			printf("debug: Slide right\n");
400:			printf("debug: Slide error!\n");
匹配到二进制文件 a.c
mao@ubuntu:~/桌面$ 
```





## sed命令

sed采用的是流编辑模式，最明显的特点是，在 sed 处理数据之前，需要预先提供一组规则，sed 会按照此规则来编辑数据。



sed 会根据脚本命令来处理文本文件中的数据，这些命令要么从命令行中输入，要么存储在一个文本文件中，此命令执行数据的顺序如下：

1. 每次仅读取一行内容；
2. 根据提供的规则命令匹配并修改数据。注意，sed 默认不会直接修改源文件数据，而是会将数据复制到缓冲区中，修改也仅限于缓冲区中的数据；
3. 将执行结果输出。

当一行数据匹配完成后，它会继续读取下一行数据，并重复这个过程，直到将文件中所有数据处理完毕。



命令：

```sh
[root@localhost ~]# sed [选项] [脚本命令] 文件名
```



|      选项       |                             含义                             |
| :-------------: | :----------------------------------------------------------: |
|   -e 脚本命令   |        该选项会将其后跟的脚本命令添加到已有的命令中。        |
| -f 脚本命令文件 |      该选项会将其后文件中的脚本命令添加到已有的命令中。      |
|       -n        | 默认情况下，sed 会在所有的脚本指定执行完毕后，会自动输出处理后的内容，而该选项会屏蔽启动输出，需使用 print 命令来完成输出。 |
|       -i        |               此选项会直接修改源文件，要慎用。               |





### sed s 替换脚本命令



命令：

```sh
[address]s/pattern/replacement/flags
```



| flags 标记 |                             功能                             |
| :--------: | :----------------------------------------------------------: |
|     n      | 1~512 之间的数字，表示指定要替换的字符串出现第几次时才进行替换，例如，一行中有 3 个 A，但用户只想替换第二个 A，这是就用到这个标记； |
|     g      | 对数据中所有匹配到的内容进行替换，如果没有 g，则只会在第一次匹配成功时做替换操作。例如，一行数据中有 3 个 A，则只会替换第一个 A； |
|     p      | 会打印与替换命令中指定的模式匹配的行。此标记通常与 -n 选项一起使用。 |
|   w file   |           将缓冲区中的内容写到指定的 file 文件中；           |
|     &      |               用正则表达式匹配的内容进行替换；               |
|     \n     |    匹配第 n 个子串，该子串之前在 pattern 中用 \(\) 指定。    |
|     \      |             转义（转义替换部分包含：&、\ 等）。              |



### sed d 替换脚本命令



命令：

```sh
[address]d
```



比如删除 data6.txt 文件内容中的第 3 行：

sed '3d' data6.txt



比如删除 data6.txt 文件内容中的第 2、3行：

sed '2,3d' data6.txt



删除 data6.txt 文件内容中第 3 行开始的所有的内容：

sed '3,$d' data6.txt





### sed a 和 i 脚本命令

a 命令表示在指定行的后面附加一行，i 命令表示在指定行的前面插入一行



命令：

```sh
[address]a（或 i）\新文本内容
```



将一个新行插入到数据流第三行前：

sed '3i\



将一个新行附加到数据流中第三行后：

sed '3a\



### sed c 替换脚本命令

c 命令表示将指定行中的所有内容，替换成该选项后面的字符串



命令：

```sh
[address]c\用于替换的新文本
```





### sed y 转换脚本命令

y 转换命令是唯一可以处理单个字符的 sed 脚本命令



命令：

```sh
[address]y/inchars/outchars/
```



转换命令会对 inchars 和 outchars 值进行一对一的映射，即 inchars 中的第一个字符会被转换为 outchars 中的第一个字符，第二个字符会被转换成 outchars 中的第二个字符...这个映射过程会一直持续到处理完指定字符。如果 inchars 和 outchars 的长度不同，则 sed 会产生一条错误消息。





### sed p 打印脚本命令

p 命令表示搜索符号条件的行，并输出该行的内容



命令：

```sh
[address]p
```





### sed w 脚本命令

w 命令用来将文本中指定行的内容写入文件中



命令：

```sh
[address]w filename
```



### sed r 脚本命令

r 命令用于将一个独立文件的数据插入到当前数据流的指定位置



命令：

```sh
[address]r filename
```





### sed q 退出脚本命令

q 命令的作用是使 sed 命令在第一次匹配任务结束后，退出 sed 程序，不再进行对后续数据的处理。





### 脚本命令的寻址方式

address 用来表明该脚本命令作用到文本中的具体行

默认情况下，sed 命令会作用于文本数据的所有行。如果只想将命令作用于特定行或某些行，则必须写明 address 部分，表示的方法有以下 2 种：

1. 以数字形式指定行区间；
2. 用文本模式指定具体行区间。



```sh
[address]脚本命令

或者

address {
    多个脚本命令
}
```







## awk命令

awk命令和 sed 命令类似，awk 命令也是逐行扫描文件（从第 1 行到最后一行），寻找含有目标文本的行，如果匹配成功，则会在该行上执行用户想要的操作；反之，则不对行做任何处理。



命令：

```sh
[root@localhost ~]# awk [选项] '脚本命令' 文件名
```



|    选项    |                             含义                             |
| :--------: | :----------------------------------------------------------: |
|   -F fs    | 指定以 fs 作为输入行的分隔符，awk 命令默认分隔符为空格或制表符。 |
|  -f file   | 从脚本文件中读取 awk 脚本指令，以取代直接在命令行中输入指令。 |
| -v var=val | 在执行处理过程之前，设置一个变量 var，并给其设备初始值为 val。 |



awk 的强大之处在于脚本命令，它由 2 部分组成，分别为匹配规则和执行命令

```sh
'匹配规则{执行命令}'
```



这里的匹配规则，和 sed 命令中的 address 部分作用相同，用来指定脚本命令可以作用到文本内容中的具体行，可以使用字符串（比如 /demo/，表示查看含有 demo 字符串的行）或者正则表达式指定。另外需要注意的是，整个脚本命令是用单引号（''）括起，而其中的执行命令部分需要用大括号（{}）括起来。

在 awk 程序执行时，如果没有指定执行命令，则默认会把匹配的行输出；如果不指定匹配规则，则默认匹配文本中所有的行。









# 软件安装

## 软件包

GPL，全称 General Public License，中文名称“通用性公开许可证”，简单理解 GPL 就是一个保护软件自由的一个协议

Linux下的软件包可细分为两种，分别是源码包和二进制包。



### 源码包

源码包就是一大堆源代码程序，是由程序员按照特定的格式和语法编写出来的



### 二进制包

二进制包，也就是源码包经过成功编译之后产生的包。

由于二进制包在发布之前就已经完成了编译的工作，因此用户安装软件的速度较快，且安装过程报错几率大大减小。



因此二进制包又被称为默认安装软件包。目前主要有以下 2 大主流的二进制包管理系统：

- RPM 包管理系统：功能强大，安装、升级、査询和卸载非常简单方便，因此很多 Linux 发行版都默认使用此机制作为软件安装的管理方式，例如 Fedora、CentOS、SuSE 等。
- DPKG 包管理系统：由 Debian Linux 所开发的包管理机制，通过 DPKG 包，Debian Linux 就可以进行软件包管理，主要应用在 Debian 和 Ubuntu 中。



### 比较

源码包需要我们自己去软件官方网站进行下载，包中通常包含以下内容：

- 源代码文件。
- 配置和检测程序（如 configure 或 config 等）。
- 软件安装说明和软件说明（如 INSTALL 或 README）。


使用源码包安装软件具有以下几点好处：

- 开源。如果你有足够的能力，则可以修改源代码。
- 可以自由选择所需的功能。
- 因为软件是编译安装的，所以更加适合自己的系统，更加稳定，效率也更高。
- 卸载方便。


但同时，使用源码包安装软件也有几点不足：

- 安装过程步骤较多，尤其是在安装较大的软件集合时（如 LAMP 环境搭建），容易出现拼写错误。
- 编译时间较长，所以安装时间比二进制安装要长。
- 因为软件是编译安装的，所以在安装过程中一旦报错，新手很难解决。



使用 RMP 包安装软件具有以下 2 点好处：

1. 包管理系统简单，只通过几个命令就可以实现包的安装、升级、査询和卸载。
2. 安装速度比源码包安装快得多。


与此同时，使用 RMP 包安装软件有如下不足：

- 经过编译，不能在看到源代码。
- 功能选择不如源码包灵活。
- 依赖性。有时我们会发现，在安装软件包 a 时需要先安装 b 和 c，而在安装 b 时需要先安装 d 和 e。这就需要先安装 d 和 e，再安装 b 和 c，最后才能安装 。需要有一定的顺序，但是有时依赖性会非常强。





## RPM包统一命名规则

规则：

```sh
包名-版本号-发布次数-发行商-Linux平台-适合的硬件平台-包扩展名
```





## Docker安装centOS



搜索：

```sh
docker search centos
```



```sh
PS C:\Users\mao\Desktop> docker search centos
NAME                                         DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
centos                                       The official build of CentOS.                   7216      [OK]
kasmweb/centos-7-desktop                     CentOS 7 desktop for Kasm Workspaces            21
continuumio/centos5_gcc5_base                                                                3
dokken/centos-7                              CentOS 7 image for kitchen-dokken               2
dokken/centos-stream-9                                                                       1
couchbase/centos7-systemd                    centos7-systemd images with additional debug…   1                    [OK]
spack/centos7                                CentOS 7 with Spack preinstalled                1
datadog/centos-i386                                                                          0
dokken/centos-8                              CentOS 8 image for kitchen-dokken               0
dokken/centos-6                              CentOS 6 image for kitchen-dokken               0
spack/centos6                                CentOS 6 with Spack preinstalled                0
dokken/centos-stream-8                                                                       0
bitnami/centos-extras-base                                                                   0
corpusops/centos                             centos corpusops baseimage                      0
couchbase/centos-72-java-sdk                                                                 0
couchbase/centos-72-jenkins-core                                                             0
fnndsc/centos-python3                        Source for a slim Centos-based Python3 image…   0                    [OK]
couchbase/centos-69-sdk-build                                                                0
bitnami/centos-base-buildpack                Centos base compilation image                   0                    [OK]
couchbase/centos-69-sdk-nodevtoolset-build                                                   0
couchbase/centos-70-sdk-build                                                                0
spack/centos-stream                                                                          0
galaxy/centos-wheel                                                                          0
galaxy/centos32                                                                              0
galaxy/centos32-wheel                                                                        0
PS C:\Users\mao\Desktop>
```



拉取：

```sh
docker pull centos
```



```sh
PS C:\Users\mao\Desktop> docker pull centos
Using default tag: latest
latest: Pulling from library/centos
a1d0c7532777: Pull complete
Digest: sha256:a27fd8080b517143cbbbab9dfb7c8571c40d67d534bbdee55bd6c473f432b177
Status: Downloaded newer image for centos:latest
docker.io/library/centos:latest
PS C:\Users\mao\Desktop>
```



查看镜像：

```sh
docker images
```



```sh
PS C:\Users\mao\Desktop> docker images
REPOSITORY            TAG       IMAGE ID       CREATED        SIZE
docker_compose_boot   1.0       aaef57816a3b   2 weeks ago    588MB
java17                1.0       282982c69086   2 weeks ago    489MB
grafana/grafana       latest    c4b778290339   2 weeks ago    292MB
tomcat                latest    c795915cb678   5 weeks ago    680MB
redis                 latest    53aa81e8adfa   5 weeks ago    117MB
mysql                 latest    65b636d5542b   5 weeks ago    524MB
ubuntu                latest    d2e4e1f51132   2 months ago   77.8MB
centos                latest    5d0da3dc9764   9 months ago   231MB
google/cadvisor       latest    eb1210707573   3 years ago    69.6MB
tutum/influxdb        0.9       7aa2a38f2ef6   6 years ago    275MB
PS C:\Users\mao\Desktop>
```



运行实例：

```sh
docker run -it --name centos centos
```

可以使用容器数据卷



```sh
PS C:\Users\mao\Desktop> docker run -it --name centos centos
[root@889e0484bdd2 /]#
```



退出：

```sh
exit
```



```sh
[root@889e0484bdd2 /]# exit
exit
PS C:\Users\mao\Desktop>
```



查看状态：

```sh
docker ps -a
```



```sh
PS C:\Users\mao\Desktop> docker ps -a
CONTAINER ID   IMAGE                     COMMAND                  CREATED              STATUS                        PORTS                    NAMES
889e0484bdd2   centos                    "/bin/bash"              About a minute ago   Exited (0) 43 seconds ago                              centos
e331c5c18f3f   ubuntu                    "bash"                   2 days ago           Exited (255) 10 minutes ago                            ubuntu
bc3a894f3f5a   mysql                     "docker-entrypoint.s…"   10 days ago          Exited (0) 10 days ago                                 mysql3
acc4ae47d7fe   mysql                     "docker-entrypoint.s…"   10 days ago          Exited (0) 10 days ago                                 mysql2
1219851e3bc5   grafana/grafana           "/run.sh"                2 weeks ago          Exited (0) 10 minutes ago                              desktop_grafana_1
059cf60a61b1   google/cadvisor           "/usr/bin/cadvisor -…"   2 weeks ago          Exited (0) 10 minutes ago                              desktop_cadvisor_1
71da6b2b40a2   tutum/influxdb:0.9        "/run.sh"                2 weeks ago          Exited (0) 10 minutes ago                              desktop_influxdb_1
e955fb5f7a77   docker_compose_boot:1.0   "java -jar Docker_co…"   2 weeks ago          Exited (143) 2 weeks ago                               docker_compose_boot1
72a29340a31e   redis                     "docker-entrypoint.s…"   2 weeks ago          Exited (0) 2 weeks ago                                 compose_redis
ce530f498cc4   mysql                     "docker-entrypoint.s…"   2 weeks ago          Exited (0) 2 weeks ago                                 compose_mysql
8a8076944128   redis                     "docker-entrypoint.s…"   2 weeks ago          Exited (255) 2 weeks ago      0.0.0.0:6380->6379/tcp   redis1
2d379d342bb6   mysql                     "docker-entrypoint.s…"   2 weeks ago          Exited (0) 2 weeks ago                                 mysql1
3ca156e4541d   tomcat                    "catalina.sh run"        2 weeks ago          Exited (143) 10 days ago                               tomcat1
PS C:\Users\mao\Desktop>
```





启动：

```sh
docker start -i centos
```



```sh
PS C:\Users\mao\Desktop> docker start -i centos
[root@889e0484bdd2 /]#
```



```sh
[root@889e0484bdd2 /]# ls
bin  dev  etc  home  lib  lib64  lost+found  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
[root@889e0484bdd2 /]# ls  -l
total 48
lrwxrwxrwx   1 root root    7 Nov  3  2020 bin -> usr/bin
drwxr-xr-x   5 root root  360 Jul  3 12:33 dev
drwxr-xr-x   1 root root 4096 Jul  3 12:30 etc
drwxr-xr-x   2 root root 4096 Nov  3  2020 home
lrwxrwxrwx   1 root root    7 Nov  3  2020 lib -> usr/lib
lrwxrwxrwx   1 root root    9 Nov  3  2020 lib64 -> usr/lib64
drwx------   2 root root 4096 Sep 15  2021 lost+found
drwxr-xr-x   2 root root 4096 Nov  3  2020 media
drwxr-xr-x   2 root root 4096 Nov  3  2020 mnt
drwxr-xr-x   2 root root 4096 Nov  3  2020 opt
dr-xr-xr-x 283 root root    0 Jul  3 12:33 proc
dr-xr-x---   1 root root 4096 Jul  3 12:31 root
drwxr-xr-x  11 root root 4096 Sep 15  2021 run
lrwxrwxrwx   1 root root    8 Nov  3  2020 sbin -> usr/sbin
drwxr-xr-x   2 root root 4096 Nov  3  2020 srv
dr-xr-xr-x  11 root root    0 Jul  3 12:33 sys
drwxrwxrwt   7 root root 4096 Sep 15  2021 tmp
drwxr-xr-x  12 root root 4096 Sep 15  2021 usr
drwxr-xr-x  20 root root 4096 Sep 15  2021 var
[root@889e0484bdd2 /]#
```



RPM

```sh
[root@889e0484bdd2 /]# rpm
RPM version 4.14.3
Copyright (C) 1998-2002 - Red Hat, Inc.
This program may be freely redistributed under the terms of the GNU GPL

Usage: rpm [-afgpcdLAlsiv?] [-a|--all] [-f|--file] [-g|--group] [-p|--package] [--pkgid] [--hdrid] [--triggeredby] [--whatconflicts] [--whatrequires]
        [--whatobsoletes] [--whatprovides] [--whatrecommends] [--whatsuggests] [--whatsupplements] [--whatenhances] [--nomanifest] [-c|--configfiles]
        [-d|--docfiles] [-L|--licensefiles] [-A|--artifactfiles] [--dump] [-l|--list] [--queryformat=QUERYFORMAT] [-s|--state] [--nofiledigest]
        [--nofiles] [--nodeps] [--noscript] [--allfiles] [--allmatches] [--badreloc] [-e|--erase=<package>+] [--excludedocs] [--excludepath=<path>]
        [--force] [-F|--freshen=<packagefile>+] [-h|--hash] [--ignorearch] [--ignoreos] [--ignoresize] [--noverify] [-i|--install] [--justdb]
        [--nodeps] [--nofiledigest] [--nocontexts] [--nocaps] [--noorder] [--noscripts] [--notriggers] [--oldpackage] [--percent] [--prefix=<dir>]
        [--relocate=<old>=<new>] [--replacefiles] [--replacepkgs] [--test] [-U|--upgrade=<packagefile>+] [--reinstall=<packagefile>+]
        [-D|--define='MACRO EXPR'] [--undefine=MACRO] [-E|--eval='EXPR'] [--target=CPU-VENDOR-OS] [--macros=<FILE:...>] [--noplugins] [--nodigest]
        [--nosignature] [--rcfile=<FILE:...>] [-r|--root=ROOT] [--dbpath=DIRECTORY] [--querytags] [--showrc] [--quiet] [-v|--verbose] [--version]
        [-?|--help] [--usage] [--scripts] [--setperms] [--setugids] [--setcaps] [--restore] [--conflicts] [--obsoletes] [--provides] [--requires]
        [--recommends] [--suggests] [--supplements] [--enhances] [--info] [--changelog] [--changes] [--xml] [--triggers] [--filetriggers] [--last]
        [--dupes] [--filesbypkg] [--fileclass] [--filecolor] [--fileprovide] [--filerequire] [--filecaps]
[root@889e0484bdd2 /]#
```



yum：

```sh
[root@889e0484bdd2 /]# yum
Failed to set locale, defaulting to C.UTF-8
usage: yum [options] COMMAND

List of Main Commands:

alias                     List or create command aliases
autoremove                remove all unneeded packages that were originally installed as dependencies
check                     check for problems in the packagedb
check-update              check for available package upgrades
clean                     remove cached data
deplist                   List package's dependencies and what packages provide them
distro-sync               synchronize installed packages to the latest available versions
downgrade                 Downgrade a package
group                     display, or use, the groups information
help                      display a helpful usage message
history                   display, or use, the transaction history
info                      display details about a package or group of packages
install                   install a package or packages on your system
list                      list a package or groups of packages
makecache                 generate the metadata cache
mark                      mark or unmark installed packages as installed by user.
module                    Interact with Modules.
provides                  find what package provides the given value
reinstall                 reinstall a package
remove                    remove a package or packages from your system
repolist                  display the configured software repositories
repoquery                 search for packages matching keyword
repository-packages       run commands on top of all packages in given repository
search                    search package details for the given string
shell                     run an interactive YUM shell
swap                      run an interactive YUM mod for remove and install one spec
updateinfo                display advisories about packages
upgrade                   upgrade a package or packages on your system
upgrade-minimal           upgrade, but only 'newest' package match which fixes a problem that affects your system

General YUM options:
  -c [config file], --config [config file]
                        config file location
  -q, --quiet           quiet operation
  -v, --verbose         verbose operation
  --version             show YUM version and exit
  --installroot [path]  set install root
  --nodocs              do not install documentations
  --noplugins           disable all plugins
  --enableplugin [plugin]
                        enable plugins by name
  --disableplugin [plugin]
                        disable plugins by name
  --releasever RELEASEVER
                        override the value of $releasever in config and repo
                        files
  --setopt SETOPTS      set arbitrary config and repo options
  --skip-broken         resolve depsolve problems by skipping packages
  -h, --help, --help-cmd
                        show command help
  --allowerasing        allow erasing of installed packages to resolve
                        dependencies
  -b, --best            try the best available package versions in
                        transactions.
  --nobest              do not limit the transaction to the best candidate
  -C, --cacheonly       run entirely from system cache, don't update cache
  -R [minutes], --randomwait [minutes]
                        maximum command wait time
  -d [debug level], --debuglevel [debug level]
                        debugging output level
  --debugsolver         dumps detailed solving results into files
  --showduplicates      show duplicates, in repos, in list/search commands
  -e ERRORLEVEL, --errorlevel ERRORLEVEL
                        error output level
  --obsoletes           enables yum's obsoletes processing logic for upgrade
                        or display capabilities that the package obsoletes for
                        info, list and repoquery
  --rpmverbosity [debug level name]
                        debugging output level for rpm
  -y, --assumeyes       automatically answer yes for all questions
  --assumeno            automatically answer no for all questions
  --enablerepo [repo]   Enable additional repositories. List option. Supports
                        globs, can be specified multiple times.
  --disablerepo [repo]  Disable repositories. List option. Supports globs, can
                        be specified multiple times.
  --repo [repo], --repoid [repo]
                        enable just specific repositories by an id or a glob,
                        can be specified multiple times
  --enable              enable repos with config-manager command
                        (automatically saves)
  --disable             disable repos with config-manager command
                        (automatically saves)
  -x [package], --exclude [package], --excludepkgs [package]
                        exclude packages by name or glob
  --disableexcludes [repo], --disableexcludepkgs [repo]
                        disable excludepkgs
  --repofrompath [repo,path]
                        label and path to an additional repository to use
                        (same path as in a baseurl), can be specified multiple
                        times.
  --noautoremove        disable removal of dependencies that are no longer
                        used
  --nogpgcheck          disable gpg signature checking (if RPM policy allows)
  --color COLOR         control whether color is used
  --refresh             set metadata as expired before running the command
  -4                    resolve to IPv4 addresses only
  -6                    resolve to IPv6 addresses only
  --destdir DESTDIR, --downloaddir DESTDIR
                        set directory to copy packages to
  --downloadonly        only download packages
  --comment COMMENT     add a comment to transaction
  --bugfix              Include bugfix relevant packages, in updates
  --enhancement         Include enhancement relevant packages, in updates
  --newpackage          Include newpackage relevant packages, in updates
  --security            Include security relevant packages, in updates
  --advisory ADVISORY, --advisories ADVISORY
                        Include packages needed to fix the given advisory, in
                        updates
  --bz BUGZILLA, --bzs BUGZILLA
                        Include packages needed to fix the given BZ, in
                        updates
  --cve CVES, --cves CVES
                        Include packages needed to fix the given CVE, in
                        updates
  --sec-severity {Critical,Important,Moderate,Low}, --secseverity {Critical,Important,Moderate,Low}
                        Include security relevant packages matching the
                        severity, in updates
  --forcearch ARCH      Force the use of an architecture
[root@889e0484bdd2 /]#
```



```sh
[root@889e0484bdd2 /]# type yum
yum is hashed (/usr/bin/yum)
[root@889e0484bdd2 /]# type rpm
rpm is hashed (/usr/bin/rpm)
[root@889e0484bdd2 /]#
```





## RPM包

通常情况下，RPM 包采用系统默认的安装路径



|    安装路径     |           含 义            |
| :-------------: | :------------------------: |
|      /etc/      |      配置文件安装目录      |
|    /usr/bin/    |    可执行的命令安装目录    |
|    /usr/lib/    | 程序所使用的函数库保存位置 |
| /usr/share/doc/ | 基本的软件使用手册保存位置 |
| /usr/share/man/ |      帮助文件保存位置      |





### RPM 包的安装



安装 RPM 的命令格式为：

```sh
[root@localhost ~]# rpm -ivh 包全名
```

注意一定是包全名。涉及到包全名的命令，一定要注意路径，可能软件包在光盘中，因此需提前做好设备的挂载工作。



- -i：安装（install）;
- -v：显示更详细的信息（verbose）;
- -h：打印 #，显示安装进度（hash）;



此命令还可以一次性安装多个软件包，仅需将包全名用空格分开即可

```sh
[root@localhost ~]# rpm -ivh a.rpm b.rpm c.rpm
```



如果还有其他安装要求（比如强制安装某软件而不管它是否有依赖性），可以通过以下选项进行调整：

- -nodeps：不检测依赖性安装。软件安装时会检测依赖性，确定所需的底层软件是否安装，如果没有安装则会报错。如果不管依赖性，想强制安装，则可以使用这个选项。注意，这样不检测依赖性安装的软件基本上是不能使用的，所以不建议这样做。
- -replacefiles：替换文件安装。如果要安装软件包，但是包中的部分文件已经存在，那么在正常安装时会报"某个文件已经存在"的错误，从而导致软件无法安装。使用这个选项可以忽略这个报错而覆盖安装。
- -replacepkgs：替换软件包安装。如果软件包已经安装，那么此选项可以把软件包重复安装一遍。
- -force：强制安装。不管是否已经安装，都重新安装。也就是 -replacefiles 和 -replacepkgs 的综合。
- -test：测试安装。不会实际安装，只是检测一下依赖性。
- -prefix：指定安装路径。为安装软件指定安装路径，而不使用默认安装路径。





### RPM包的升级



命令：

```sh
[root@localhost ~]# rpm -Uvh 包全名
```



-U（大写）选项的含义是：如果该软件没安装过则直接安装；若没安装则升级至最新版本。



或者：

```sh
[root@localhost ~]# rpm -Fvh 包全名
```

-F（大写）选项的含义是：如果该软件没有安装，则不会安装，必须安装有较低版本才能升级。



### RPM包的卸载

RPM 软件包的卸载要考虑包之间的依赖性



命令：

```sh
[root@localhost ~]# rpm -e 包名
```

-e 选项表示卸载，也就是 erase 的首字母。





## rpm命令查询软件包



使用 rpm 做查询命令的格式如下：

```sh
[root@localhost ~]# rpm 选项 查询对象
```



### rpm -q

**查询软件包是否安装**



命令：

```sh
[root@localhost ~]# rpm -q 包名
```



-q 表示查询，是 query 的首字母



### rpm -qa

**查询系统中所有安装的软件包**



命令：

```sh
rpm -qa
```



```sh
[root@889e0484bdd2 /]# rpm -qa
crypto-policies-20210209-1.gitbfb6bed.el8_3.noarch
python3-pip-wheel-9.0.3-19.el8.noarch
ncurses-base-6.1-7.20180224.el8.noarch
dnf-data-4.4.2-11.el8.noarch
dhcp-common-4.3.6-44.0.1.el8.noarch
centos-gpg-keys-8-2.el8.noarch
centos-linux-repos-8-2.el8.noarch
filesystem-3.8-3.el8.x86_64
pcre2-10.32-2.el8.x86_64
ncurses-libs-6.1-7.20180224.el8.x86_64
glibc-common-2.28-151.el8.x86_64
bash-4.4.19-14.el8.x86_64
zlib-1.2.11-17.el8.x86_64
bzip2-libs-1.0.6-26.el8.x86_64
libgpg-error-1.31-1.el8.x86_64
elfutils-libelf-0.182-3.el8.x86_64
libcom_err-1.45.6-1.el8.x86_64
libxml2-2.9.7-9.el8.x86_64
expat-2.2.5-4.el8.x86_64
libuuid-2.32.1-27.el8.x86_64
chkconfig-1.13-2.el8.x86_64
gmp-6.1.2-10.el8.x86_64
libattr-2.4.48-3.el8.x86_64
coreutils-single-8.30-8.el8.x86_64
sed-4.5-2.el8.x86_64
libcap-ng-0.7.9-5.el8.x86_64
libsmartcols-2.32.1-27.el8.x86_64
lz4-libs-1.8.3-2.el8.x86_64
file-libs-5.33-16.el8_3.1.x86_64
p11-kit-0.23.22-1.el8.x86_64
cracklib-2.9.6-15.el8.x86_64
libunistring-0.9.9-3.el8.x86_64
libassuan-2.5.1-3.el8.x86_64
keyutils-libs-1.5.10-6.el8.x86_64
libnl3-3.5.0-1.el8.x86_64
p11-kit-trust-0.23.22-1.el8.x86_64
pcre-8.42-4.el8.x86_64
systemd-libs-239-45.el8.x86_64
dbus-tools-1.12.8-12.el8.x86_64
libusbx-1.0.23-4.el8.x86_64
ca-certificates-2020.2.41-80.0.el8_2.noarch
libdb-5.3.28-40.el8.x86_64
iproute-5.9.0-4.el8.x86_64
libdb-utils-5.3.28-40.el8.x86_64
tpm2-tss-2.3.2-3.el8.x86_64
xz-5.2.4-3.el8.x86_64
ethtool-5.8-5.el8.x86_64
libsemanage-2.9-6.el8.x86_64
dbus-daemon-1.12.8-12.el8.x86_64
libfdisk-2.32.1-27.el8.x86_64
mpfr-3.1.6-1.el8.x86_64
gnutls-3.6.14-7.el8_3.x86_64
snappy-1.1.8-3.el8.x86_64
libmetalink-0.1.3-7.el8.x86_64
libksba-1.3.5-7.el8.x86_64
ipcalc-0.2.4-4.el8.x86_64
libseccomp-2.5.1-1.el8.x86_64
gawk-4.2.1-2.el8.x86_64
krb5-libs-1.18.2-8.el8.x86_64
libnsl2-1.2.0-2.20180605git4a062cf.el8.x86_64
platform-python-3.6.8-37.el8.x86_64
libpwquality-1.4.4-3.el8.x86_64
util-linux-2.32.1-27.el8.x86_64
curl-7.61.1-18.el8.x86_64
rpm-libs-4.14.3-13.el8.x86_64
python3-libcomps-0.1.11-5.el8.x86_64
cyrus-sasl-lib-2.1.27-5.el8.x86_64
libyaml-0.1.7-5.el8.x86_64
npth-1.5-4.el8.x86_64
gpgme-1.13.1-7.el8.x86_64
libdnf-0.55.0-7.el8.x86_64
python3-hawkey-0.55.0-7.el8.x86_64
pciutils-libs-3.7.0-1.el8.x86_64
rdma-core-32.0-4.el8.x86_64
libpcap-1.9.1-5.el8.x86_64
device-mapper-1.02.175-5.el8.x86_64
cryptsetup-libs-2.3.3-4.el8.x86_64
elfutils-libs-0.182-3.el8.x86_64
systemd-239-45.el8.x86_64
iputils-20180629-7.el8.x86_64
libkcapi-1.2.0-2.el8.x86_64
systemd-udev-239-45.el8.x86_64
dracut-network-049-135.git20210121.el8.x86_64
rpm-build-libs-4.14.3-13.el8.x86_64
python3-dnf-4.4.2-11.el8.noarch
yum-4.4.2-11.el8.noarch
binutils-2.30-93.el8.x86_64
vim-minimal-8.0.1763-15.el8.x86_64
less-530-1.el8.x86_64
rootfiles-8.1-22.el8.noarch
libgcc-8.4.1-1.el8.x86_64
python3-setuptools-wheel-39.2.0-6.el8.noarch
tzdata-2021a-1.el8.noarch
libreport-filesystem-2.9.5-15.el8.x86_64
hwdata-0.314-8.8.el8.noarch
dbus-common-1.12.8-12.el8.noarch
centos-linux-release-8.4-1.2105.el8.noarch
setup-2.12.2-6.el8.noarch
basesystem-11-5.el8.noarch
libselinux-2.9-5.el8.x86_64
glibc-minimal-langpack-2.28-151.el8.x86_64
glibc-2.28-151.el8.x86_64
libsepol-2.9-2.el8.x86_64
xz-libs-5.2.4-3.el8.x86_64
libcap-2.26-4.el8.x86_64
info-6.5-6.el8.x86_64
libzstd-1.4.4-1.el8.x86_64
libxcrypt-4.1.1-4.el8.x86_64
sqlite-libs-3.26.0-13.el8.x86_64
libstdc++-8.4.1-1.el8.x86_64
popt-1.18-1.el8.x86_64
readline-7.0-10.el8.x86_64
json-c-0.13.1-0.4.el8.x86_64
libacl-2.2.53-1.el8.x86_64
libblkid-2.32.1-27.el8.x86_64
libmount-2.32.1-27.el8.x86_64
audit-libs-3.0-0.17.20191104git1c2f876.el8.x86_64
lua-libs-5.3.4-11.el8.x86_64
libgcrypt-1.8.5-4.el8.x86_64
libffi-3.1-22.el8.x86_64
gzip-1.9-12.el8.x86_64
cracklib-dicts-2.9.6-15.el8.x86_64
libidn2-2.2.0-1.el8.x86_64
gdbm-libs-1.18-1.el8.x86_64
libmnl-1.0.4-6.el8.x86_64
libtasn1-4.13-3.el8.x86_64
lzo-2.08-14.el8.x86_64
grep-3.1-6.el8.x86_64
dbus-libs-1.12.8-12.el8.x86_64
dhcp-libs-4.3.6-44.0.1.el8.x86_64
procps-ng-3.3.15-6.el8.x86_64
openssl-libs-1.1.1g-15.el8_3.x86_64
kmod-libs-25-17.el8.x86_64
kmod-25-17.el8.x86_64
libarchive-3.3.3-1.el8.x86_64
ima-evm-utils-1.3.2-12.el8.x86_64
squashfs-tools-4.3-20.el8.x86_64
gdbm-1.18-1.el8.x86_64
shadow-utils-4.6-12.el8.x86_64
libutempter-1.1.6-14.el8.x86_64
acl-2.2.53-1.el8.x86_64
nettle-3.4.1-2.el8.x86_64
glib2-2.56.4-9.el8.x86_64
libcomps-0.1.11-5.el8.x86_64
findutils-4.6.0-20.el8.x86_64
cpio-2.12-10.el8.x86_64
libnghttp2-1.33.0-3.el8_2.1.x86_64
libsigsegv-2.11-5.el8.x86_64
libverto-0.3.0-5.el8.x86_64
libtirpc-1.1.4-4.el8.x86_64
platform-python-setuptools-39.2.0-6.el8.noarch
python3-libs-3.6.8-37.el8.x86_64
pam-1.3.1-14.el8.x86_64
libcurl-minimal-7.61.1-18.el8.x86_64
rpm-4.14.3-13.el8.x86_64
libsolv-0.7.16-2.el8.x86_64
bind-export-libs-9.11.26-3.el8.x86_64
openldap-2.4.46-16.el8.x86_64
libmodulemd-2.9.4-2.el8.x86_64
gnupg2-2.2.20-2.el8.x86_64
librepo-1.12.0-3.el8.x86_64
python3-libdnf-0.55.0-7.el8.x86_64
python3-gpg-1.13.1-7.el8.x86_64
pciutils-3.7.0-1.el8.x86_64
libibverbs-32.0-4.el8.x86_64
iptables-libs-1.8.4-17.el8.x86_64
device-mapper-libs-1.02.175-5.el8.x86_64
elfutils-default-yama-scope-0.182-3.el8.noarch
systemd-pam-239-45.el8.x86_64
dbus-1.12.8-12.el8.x86_64
dhcp-client-4.3.6-44.0.1.el8.x86_64
libkcapi-hmaccalc-1.2.0-2.el8.x86_64
dracut-049-135.git20210121.el8.x86_64
dracut-squash-049-135.git20210121.el8.x86_64
python3-rpm-4.14.3-13.el8.x86_64
dnf-4.4.2-11.el8.noarch
kexec-tools-2.0.20-46.el8.x86_64
tar-1.30-5.el8.x86_64
hostname-3.20-6.el8.x86_64
langpacks-en-1.0-12.el8.noarch
[root@889e0484bdd2 /]#
```



还可以使用管道符查找出需要的内容





### rpm -qi

**查询软件包的详细信息**



```sh
[root@localhost ~]# rpm -qi 包名
```



-i 选项表示查询软件信息，是 information 的首字母。



查询gzip-1.9-12.el8.x86_64

```sh
[root@889e0484bdd2 /]# rpm -qi gzip-1.9-12.el8.x86_64
Name        : gzip
Version     : 1.9
Release     : 12.el8
Architecture: x86_64
Install Date: Wed Sep 15 14:17:30 2021
Group       : Applications/File
Size        : 353139
License     : GPLv3+ and GFDL
Signature   : RSA/SHA256, Wed Jan 13 20:53:46 2021, Key ID 05b555b38483c65d
Source RPM  : gzip-1.9-12.el8.src.rpm
Build Date  : Wed Jan 13 15:02:05 2021
Build Host  : x86-01.mbox.centos.org
Relocations : (not relocatable)
Packager    : CentOS Buildsys <bugs@centos.org>
Vendor      : CentOS
URL         : http://www.gzip.org/
Summary     : The GNU data compression program
Description :
The gzip package contains the popular GNU gzip data compression
program. Gzipped files have a .gz extension.

Gzip should be installed on your system, because it is a
very commonly used data compression program.
[root@889e0484bdd2 /]#
```



还可以查询未安装软件包的详细信息：

```sh
[root@localhost ~]# rpm -qip 包全名
```



-p 选项表示查询未安装的软件包，是 package 的首字母。

这里用的是包全名，且未安装的软件包需使用“绝对路径+包全名”的方式才能确定包。





### rpm -ql

**查询软件包的文件列表**

各安装文件会分门别类安放在适当的目录文件下。使用 rpm 命令可以查询到已安装软件包中包含的所有文件及各自安装路径



命令：

```sh
[root@localhost ~]# rpm -ql 包名
```



-l 选项表示列出软件包所有文件的安装目录。



查询gzip-1.9-12.el8.x86_64文件列表：

```sh
[root@889e0484bdd2 /]# rpm -ql gzip-1.9-12.el8.x86_64
/etc/profile.d/colorzgrep.csh
/etc/profile.d/colorzgrep.sh
/usr/bin/gunzip
/usr/bin/gzexe
/usr/bin/gzip
/usr/bin/zcat
/usr/bin/zcmp
/usr/bin/zdiff
/usr/bin/zegrep
/usr/bin/zfgrep
/usr/bin/zforce
/usr/bin/zgrep
/usr/bin/zless
/usr/bin/zmore
/usr/bin/znew
/usr/lib/.build-id
/usr/lib/.build-id/69
/usr/lib/.build-id/69/f880422e6ff80dbb4b461f1ffa03e8e943299e
/usr/share/doc/gzip
/usr/share/doc/gzip/AUTHORS
/usr/share/doc/gzip/ChangeLog
/usr/share/doc/gzip/NEWS
/usr/share/doc/gzip/README
/usr/share/doc/gzip/THANKS
/usr/share/doc/gzip/TODO
/usr/share/info/gzip.info.gz
/usr/share/licenses/gzip
/usr/share/licenses/gzip/COPYING
/usr/share/licenses/gzip/fdl-1.3.txt
/usr/share/man/man1/gunzip.1.gz
/usr/share/man/man1/gzexe.1.gz
/usr/share/man/man1/gzip.1.gz
/usr/share/man/man1/zcat.1.gz
/usr/share/man/man1/zcmp.1.gz
/usr/share/man/man1/zdiff.1.gz
/usr/share/man/man1/zforce.1.gz
/usr/share/man/man1/zgrep.1.gz
/usr/share/man/man1/zless.1.gz
/usr/share/man/man1/zmore.1.gz
/usr/share/man/man1/znew.1.gz
[root@889e0484bdd2 /]#
```



rpm 命令还可以查询未安装软件包中包含的所有文件以及打算安装的路径



```sh
[root@localhost ~]# rpm -qlp 包全名
```



需要使用“绝对路径+包全名”的方式才能确定包





### rpm -qf

**查询系统文件属于哪个RPM包**

rpm -ql 命令是通过软件包查询所含文件的安装路径，rpm 还支持反向查询，即查询某系统文件所属哪个 RPM 软件包



命令：

```sh
[root@localhost ~]# rpm -qf 系统文件名
```



-f 选项的含义是查询系统文件所属哪个软件包，是 file 的首字母。



```sh
[root@889e0484bdd2 /]# rpm -qf /bin/ls
coreutils-single-8.30-8.el8.x86_64
[root@889e0484bdd2 /]#
```

```sh
[root@889e0484bdd2 /]# rpm -qf /usr/bin/gzip
gzip-1.9-12.el8.x86_64
[root@889e0484bdd2 /]#
```



### rpm -qR

**查询软件包的依赖关系**

使用 rpm 命令安装 RPM 包，需考虑与其他 RPM 包的依赖关系。rpm -qR 命令就用来查询某已安装软件包依赖的其他包



命令：

```sh
[root@localhost ~]# rpm -qR 包名
```

-R（大写）选项的含义是查询软件包的依赖性，是 requires 的首字母。





```sh
[root@889e0484bdd2 /]# rpm -qR gzip-1.9-12.el8.x86_64
/bin/sh
/bin/sh
/bin/sh
/sbin/install-info
coreutils
libc.so.6()(64bit)
libc.so.6(GLIBC_2.14)(64bit)
libc.so.6(GLIBC_2.17)(64bit)
libc.so.6(GLIBC_2.2.5)(64bit)
libc.so.6(GLIBC_2.3)(64bit)
libc.so.6(GLIBC_2.3.4)(64bit)
libc.so.6(GLIBC_2.4)(64bit)
libc.so.6(GLIBC_2.6)(64bit)
rpmlib(CompressedFileNames) <= 3.0.4-1
rpmlib(FileDigests) <= 4.6.0-1
rpmlib(PayloadFilesHavePrefix) <= 4.0-1
rpmlib(PayloadIsXz) <= 5.2-1
rtld(GNU_HASH)
[root@889e0484bdd2 /]#
```

```sh
[root@889e0484bdd2 /]# rpm -qR yum-4.4.2-11.el8.noarch
config(yum) = 4.4.2-11.el8
dnf = 4.4.2-11.el8
rpmlib(CompressedFileNames) <= 3.0.4-1
rpmlib(FileDigests) <= 4.6.0-1
rpmlib(PayloadFilesHavePrefix) <= 4.0-1
rpmlib(PayloadIsXz) <= 5.2-1
[root@889e0484bdd2 /]#
```



在此命令的基础上增加 -p 选项，即可实现查找未安装软件包的依赖性







## RPM包验证

RPM 包校验可用来判断已安装的软件包（或文件）是否被修改



```sh
[root@localhost ~]# rpm -Va
```

-Va 选项表示校验系统中已安装的所有软件包



```sh
[root@localhost ~]# rpm -V 已安装的包名
```

-V 选项表示校验指定 RPM 包中的文件，是 verity 的首字母



```sh
[root@localhost ~]# rpm -Vf 系统文件名
```

-Vf 选项表示校验某个系统文件是否被修改



```sh
[root@889e0484bdd2 /]# rpm -Va
S.5....T.  c /etc/dnf/vars/infra
.M.......    /
missing     /boot
missing     /usr/lib/udev/hwdb.d
missing     /usr/lib/udev/hwdb.d/20-OUI.hwdb
missing     /usr/lib/udev/hwdb.d/20-acpi-vendor.hwdb
missing     /usr/lib/udev/hwdb.d/20-bluetooth-vendor-product.hwdb
missing     /usr/lib/udev/hwdb.d/20-net-ifname.hwdb
missing     /usr/lib/udev/hwdb.d/20-pci-classes.hwdb
missing     /usr/lib/udev/hwdb.d/20-pci-vendor-model.hwdb
missing     /usr/lib/udev/hwdb.d/20-sdio-classes.hwdb
missing     /usr/lib/udev/hwdb.d/20-sdio-vendor-model.hwdb
missing     /usr/lib/udev/hwdb.d/20-usb-classes.hwdb
missing     /usr/lib/udev/hwdb.d/20-usb-vendor-model.hwdb
missing     /usr/lib/udev/hwdb.d/20-vmbus-class.hwdb
missing     /usr/lib/udev/hwdb.d/60-evdev.hwdb
missing     /usr/lib/udev/hwdb.d/60-keyboard.hwdb
missing     /usr/lib/udev/hwdb.d/60-sensor.hwdb
missing     /usr/lib/udev/hwdb.d/70-joystick.hwdb
missing     /usr/lib/udev/hwdb.d/70-mouse.hwdb
missing     /usr/lib/udev/hwdb.d/70-pointingstick.hwdb
missing     /usr/lib/udev/hwdb.d/70-touchpad.hwdb
.M....G..  g /var/log/lastlog
[root@889e0484bdd2 /]#
```

```sh
[root@889e0484bdd2 /]# rpm -V centos-gpg-keys-8-2.el8.noarch
[root@889e0484bdd2 /]#
```







## cpio命令

cpio 命令用于**从归档包中存入和读取文件**，换句话说，cpio 命令可以从归档包中提取文件（或目录），也可以将文件（或目录）复制到归档包中。



归档包，也可称为文件库，其实就是 cpio 或 tar 格式的文件，该文件中包含其他文件以及一些相关信息（文件名、访问权限等）。归档包既可以是磁盘中的文件，也可以是磁带或管道。



- 使用 cpio 备份数据时如果使用的是绝对路径，那么还原数据时会自动恢复到绝对路径下；同理，如果备份数据使用的是相对路径，那么数据会还原到相对路径下。
- cpio 命令无法自行指定备份（或还原）的文件，需要目标文件（或目录）的完整路径才能成功读取，因此此命令常与 find 命令配合使用。
- cpio 命令恢复数据时不会自动覆盖同名文件，也不会创建目录（直接解压到当前文件夹）。



把数据备份到文件库中：

```sh
[root@localhost ~]# cpio -o[vcB] > [文件丨设备]
```

- -o：copy-out模式，备份；
- -v：显示备份过程；
- -c：使用较新的portable format存储方式；
- -B：设定输入/输出块为 5120Bytes，而不是模式的 512Bytes；



把数据从文件库中恢复：

```sh
[root@localhost ~]# cpio -i[vcdu] < [文件|设备]
```

- -i：copy-in 模式，还原；
- -v：显示还原过程；
- -c：较新的 portable format 存储方式；
- -d：还原时自动新建目录；
- -u：自动使用较新的文件覆盖较旧的文件；





## yum

yum，全称“Yellow dog Updater, Modified”，是一个专门为了解决包的依赖关系而存在的软件包管理器。

yum 是改进型的 RPM 软件管理器，它很好的解决了 RPM 所面临的软件包依赖问题。yum 在服务器端存有所有的 RPM 包，并将各个包之间的依赖关系记录在文件中，当管理员使用 yum 安装 RPM 包时，yum 会先从服务器端下载包的依赖性文件，通过分析此文件从服务器端一次性下载所有相关的 RPM 包并进行安装





## 解决Docker centOS 无法使用yum问题



错误描述：

```sh
Error: Failed to download metadata for repo 'appstream': Cannot prepare internal mirrorlist: No URLs in mirrorlist
```

从仓库 ‘appstream’ 下载元数据失败：由于镜像列表中没有 URL，不能准备内部镜像列表



ping百度，查看是否为网络问题：

```sh
ping baidu.com
```



```sh
[root@889e0484bdd2 rpm-gpg]# ping baidu.com
PING baidu.com (220.181.38.251) 56(84) bytes of data.
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=1 ttl=37 time=48.7 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=2 ttl=37 time=50.2 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=3 ttl=37 time=48.3 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=4 ttl=37 time=48.9 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=5 ttl=37 time=50.1 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=6 ttl=37 time=48.9 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=7 ttl=37 time=48.8 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=8 ttl=37 time=48.3 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=9 ttl=37 time=48.0 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=10 ttl=37 time=50.4 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=11 ttl=37 time=48.9 ms
64 bytes from 220.181.38.251 (220.181.38.251): icmp_seq=12 ttl=37 time=47.10 ms
^C
--- baidu.com ping statistics ---
12 packets transmitted, 12 received, 0% packet loss, time 20074ms
rtt min/avg/max/mdev = 47.990/48.976/50.441/0.818 ms
[root@889e0484bdd2 rpm-gpg]#
```

网络正常



如果网络正常，便是 CentOS 已经停止维护的问题。2020 年 12 月 8 号，CentOS 官方宣布了停止维护 CentOS Linux 的计划，并推出了 CentOS Stream 项目，CentOS Linux 8 作为 RHEL 8 的复刻版本，生命周期缩短，于 2021 年 12 月 31 日停止更新并停止维护（EOL），更多的信息可以查看 CentOS 官方公告。如果需要更新 CentOS，需要将镜像从 mirror.centos.org 更改为 vault.centos.org



进入到 yum 的 repos 目录：

```sh
cd /etc/yum.repos.d/
```



修改 centos 文件内容：

```sh
sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
```



生成缓存更新：

```sh
yum makecache
```



最后使用yum list验证



```sh
[root@889e0484bdd2 rpm-gpg]# cd /etc/yum.repos.d/
[root@889e0484bdd2 yum.repos.d]# ls
CentOS-Linux-AppStream.repo          CentOS-Linux-Debuginfo.repo  CentOS-Linux-FastTrack.repo         CentOS-Linux-Plus.repo
CentOS-Linux-BaseOS.repo             CentOS-Linux-Devel.repo      CentOS-Linux-HighAvailability.repo  CentOS-Linux-PowerTools.repo
CentOS-Linux-ContinuousRelease.repo  CentOS-Linux-Extras.repo     CentOS-Linux-Media.repo             CentOS-Linux-Sources.repo
[root@889e0484bdd2 yum.repos.d]# sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
[root@889e0484bdd2 yum.repos.d]# sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
[root@889e0484bdd2 yum.repos.d]# yum makecache
Failed to set locale, defaulting to C.UTF-8
CentOS Linux 8 - AppStream                                                                                                      1.1 MB/s | 8.4 MB     00:07
CentOS Linux 8 - BaseOS                                                                                                         1.0 MB/s | 4.6 MB     00:04
CentOS Linux 8 - Extras                                                                                                         4.6 kB/s |  10 kB     00:02
Metadata cache created.
[root@889e0484bdd2 yum.repos.d]#
```







## yum命令

### yum查询命令



查询所有已安装和可安装的软件包

```sh
yum list
```



```sh
xz-devel.x86_64                                                            5.2.4-3.el8                                                                 baseos
xz-libs.i686                                                               5.2.4-3.el8                                                                 baseos
yajl.i686                                                                  2.1.0-10.el8                                                                appstream
yajl.x86_64                                                                2.1.0-10.el8                                                                appstream
yelp.x86_64                                                                2:3.28.1-3.el8                                                              appstream
yelp-libs.i686                                                             2:3.28.1-3.el8                                                              appstream
yelp-libs.x86_64                                                           2:3.28.1-3.el8                                                              appstream
yelp-tools.noarch                                                          3.28.0-3.el8                                                                appstream
yelp-xsl.noarch                                                            3.28.0-2.el8                                                                appstream
yp-tools.x86_64                                                            4.2.3-1.el8                                                                 appstream
ypbind.x86_64                                                              3:2.5-2.el8                                                                 appstream
ypserv.x86_64                                                              4.0-6.20170331git5bfba76.el8                                                appstream
yum.noarch                                                                 4.7.0-4.el8                                                                 baseos
yum-utils.noarch                                                           4.0.21-3.el8                                                                baseos
zenity.x86_64                                                              3.28.1-1.el8                                                                appstream
zip.x86_64                                                                 3.0-23.el8                                                                  baseos
zlib.i686                                                                  1.2.11-17.el8                                                               baseos
zlib-devel.i686                                                            1.2.11-17.el8                                                               baseos
zlib-devel.x86_64                                                          1.2.11-17.el8                                                               baseos
zsh.x86_64                                                                 5.5.1-6.el8_1.2                                                             baseos
zsh-html.noarch                                                            5.5.1-6.el8_1.2                                                             appstream
zstd.x86_64                                                                1.4.4-1.el8                                                                 appstream
zziplib.i686                                                               0.13.68-9.el8                                                               appstream
zziplib.x86_64                                                             0.13.68-9.el8                                                               appstream
zziplib-utils.x86_64                                                       0.13.68-9.el8                                                               appstream
[root@889e0484bdd2 yum.repos.d]#
```

只列举一部分





查询执行软件包的安装情况

```sh
yum list 包名
```



```sh
[root@889e0484bdd2 yum.repos.d]# yum list zip.x86_64
Failed to set locale, defaulting to C.UTF-8
Last metadata expiration check: 0:05:06 ago on Mon Jul  4 06:25:24 2022.
Available Packages
zip.x86_64                                                                   3.0-23.el8                                                                   baseos
[root@889e0484bdd2 yum.repos.d]#
```





从 yum 源服务器上查找与关键字相关的所有软件包

```sh
yum search 关键字
```



```sh
[root@889e0484bdd2 yum.repos.d]# yum search mysql
Failed to set locale, defaulting to C.UTF-8
Last metadata expiration check: 0:06:02 ago on Mon Jul  4 06:25:24 2022.
================================================================ Name & Summary Matched: mysql =================================================================
mysql.x86_64 : MySQL client programs and shared libraries
apr-util-mysql.x86_64 : APR utility library MySQL DBD driver
dovecot-mysql.x86_64 : MySQL back end for dovecot
freeradius-mysql.x86_64 : MySQL support for freeradius
mysql-common.x86_64 : The shared files required for MySQL server and client
mysql-devel.x86_64 : Files for development of MySQL applications
mysql-errmsg.x86_64 : The error messages files required by MySQL server
mysql-libs.x86_64 : The shared libraries required for MySQL clients
mysql-selinux.noarch : SELinux policy modules for MySQL and MariaDB packages
mysql-server.x86_64 : The MySQL server and related files
mysql-test.x86_64 : The test suite distributed with MySQL
pcp-pmda-mysql.x86_64 : Performance Co-Pilot (PCP) metrics for MySQL
perl-DBD-MySQL.x86_64 : A MySQL interface for Perl
php-mysqlnd.x86_64 : A module for PHP applications that use MySQL databases
postfix-mysql.x86_64 : Postfix MySQL map support
python2-PyMySQL.noarch : Pure-Python MySQL client library
python3-PyMySQL.noarch : Pure-Python MySQL client library
python38-PyMySQL.noarch : Pure-Python MySQL client library
python39-PyMySQL.noarch : Pure-Python MySQL client library
qt5-qtbase-mysql.i686 : MySQL driver for Qt5's SQL classes
qt5-qtbase-mysql.x86_64 : MySQL driver for Qt5's SQL classes
rsyslog-mysql.x86_64 : MySQL support for rsyslog
rubygem-mysql2.x86_64 : A simple, fast Mysql library for Ruby, binding to libmysql
rubygem-mysql2-doc.noarch : Documentation for rubygem-mysql2
==================================================================== Summary Matched: mysql ====================================================================
mariadb-devel.x86_64 : Files for development of MariaDB/MySQL applications
mariadb-java-client.noarch : Connects applications developed in Java to MariaDB and MySQL databases
mariadb-server-utils.x86_64 : Non-essential server utilities for MariaDB/MySQL applications
[root@889e0484bdd2 yum.repos.d]#
```

```sh
[root@889e0484bdd2 yum.repos.d]# yum search jdk
Failed to set locale, defaulting to C.UTF-8
Last metadata expiration check: 0:06:30 ago on Mon Jul  4 06:25:24 2022.
================================================================= Name & Summary Matched: jdk ==================================================================
copy-jdk-configs.noarch : JDKs configuration files copier
java-1.8.0-openjdk.x86_64 : OpenJDK 8 Runtime Environment
java-1.8.0-openjdk-accessibility.x86_64 : OpenJDK 8 accessibility connector
java-1.8.0-openjdk-demo.x86_64 : OpenJDK 8 Demos
java-1.8.0-openjdk-devel.x86_64 : OpenJDK 8 Development Environment
java-1.8.0-openjdk-headless.x86_64 : OpenJDK 8 Headless Runtime Environment
java-1.8.0-openjdk-headless-slowdebug.x86_64 : OpenJDK 8 Runtime Environment unoptimised with full debugging on
java-1.8.0-openjdk-javadoc.noarch : OpenJDK 8 API documentation
java-1.8.0-openjdk-javadoc-zip.noarch : OpenJDK 8 API documentation compressed in a single archive
java-1.8.0-openjdk-slowdebug.x86_64 : OpenJDK 8 Runtime Environment unoptimised with full debugging on
java-1.8.0-openjdk-src.x86_64 : OpenJDK 8 Source Bundle
java-11-openjdk.x86_64 : OpenJDK 11 Runtime Environment
java-11-openjdk-demo.x86_64 : OpenJDK 11 Demos
java-11-openjdk-devel.x86_64 : OpenJDK 11 Development Environment
java-11-openjdk-headless.x86_64 : OpenJDK 11 Headless Runtime Environment
java-11-openjdk-javadoc.x86_64 : OpenJDK 11 API documentation
java-11-openjdk-javadoc-zip.x86_64 : OpenJDK 11 API documentation compressed in a single archive
java-11-openjdk-jmods.x86_64 : JMods for OpenJDK 11
java-11-openjdk-src.x86_64 : OpenJDK 11 Source Bundle
java-11-openjdk-static-libs.x86_64 : OpenJDK 11 libraries for static linking
java-17-openjdk.x86_64 : OpenJDK 17 Runtime Environment
java-17-openjdk-demo.x86_64 : OpenJDK 17 Demos
java-17-openjdk-devel.x86_64 : OpenJDK 17 Development Environment
java-17-openjdk-headless.x86_64 : OpenJDK 17 Headless Runtime Environment
java-17-openjdk-javadoc.x86_64 : OpenJDK 17 API documentation
java-17-openjdk-javadoc-zip.x86_64 : OpenJDK 17 API documentation compressed in a single archive
java-17-openjdk-jmods.x86_64 : JMods for OpenJDK 17
java-17-openjdk-src.x86_64 : OpenJDK 17 Source Bundle
java-17-openjdk-static-libs.x86_64 : OpenJDK 17 libraries for static linking
===================================================================== Summary Matched: jdk =====================================================================
icedtea-web.x86_64 : Additional Java components for OpenJDK - Java browser plug-in and Web Start implementation
jmc.x86_64 : JDK Mission Control is a profiling and diagnostics tool
jmc-core.noarch : Core API for JDK Mission Control
[root@889e0484bdd2 yum.repos.d]#
```





查询执行软件包的详细信息：

```sh
yum info 包名
```





```sh
[root@889e0484bdd2 yum.repos.d]# yum info zip.x86_64
Failed to set locale, defaulting to C.UTF-8
Last metadata expiration check: 0:10:01 ago on Mon Jul  4 06:25:24 2022.
Available Packages
Name         : zip
Version      : 3.0
Release      : 23.el8
Architecture : x86_64
Size         : 270 k
Source       : zip-3.0-23.el8.src.rpm
Repository   : baseos
Summary      : A file compression and packaging utility compatible with PKZIP
URL          : http://www.info-zip.org/Zip.html
License      : BSD
Description  : The zip program is a compression and file packaging utility.  Zip is
             : analogous to a combination of the UNIX tar and compress commands and
             : is compatible with PKZIP (a compression and file packaging utility for
             : MS-DOS systems).
             :
             : Install the zip package if you need to compress files using the zip
             : program.

[root@889e0484bdd2 yum.repos.d]#
```





### yum安装命令



命令：

```sh
yum -y install 包名
```



- install：表示安装软件包。
- -y：自动回答 yes。如果不加 -y，那么每个安装的软件都需要手工回答 yes；



安装jdk17：

```sh
yum -y install java-17-openjdk.x86_64
```



```sh
[root@889e0484bdd2 /]# yum -y install java-17-openjdk.x86_64
Failed to set locale, defaulting to C.UTF-8
Last metadata expiration check: 0:16:09 ago on Mon Jul  4 06:25:24 2022.
Dependencies resolved.
================================================================================================================================================================ Package                                     Architecture             Version                                                 Repository                   Size
================================================================================================================================================================Installing:
 java-17-openjdk                             x86_64                   1:17.0.1.0.12-2.el8_5                                   appstream                   244 k
Upgrading:
 crypto-policies                             noarch                   20210617-1.gitc776d3e.el8                               baseos                       63 k
 lua-libs                                    x86_64                   5.3.4-12.el8                                            baseos                      118 k
Installing dependencies:
 adwaita-cursor-theme                        noarch                   3.28.0-2.el8                                            appstream                   647 k
 adwaita-icon-theme                          noarch                   3.28.0-2.el8                                            appstream                    11 M
 alsa-lib                                    x86_64                   1.2.5-4.el8                                             appstream                   489 k
 at-spi2-atk                                 x86_64                   2.26.2-1.el8                                            appstream                    89 k
 at-spi2-core                                x86_64                   2.28.0-1.el8                                            appstream                   169 k
 atk                                         x86_64                   2.28.1-1.el8                                            appstream                   272 k
 avahi-libs                                  x86_64                   0.7-20.el8                                              baseos                       62 k
 cairo                                       x86_64                   1.15.12-3.el8                                           appstream                   721 k
 cairo-gobject                               x86_64                   1.15.12-3.el8                                           appstream                    33 k
 colord-libs                                 x86_64                   1.4.2-1.el8                                             appstream                   236 k
 copy-jdk-configs                            noarch                   4.0-2.el8                                               appstream                    31 k
 crypto-policies-scripts                     noarch                   20210617-1.gitc776d3e.el8                               baseos                       83 k
 cups-libs                                   x86_64                   1:2.2.6-40.el8                                          baseos                      433 k
 dejavu-fonts-common                         noarch                   2.35-7.el8                                              baseos                       74 k
 dejavu-sans-mono-fonts                      noarch                   2.35-7.el8                                              baseos                      447 k
 fontconfig                                  x86_64                   2.13.1-4.el8                                            baseos                      274 k
 fontpackages-filesystem                     noarch                   1.44-22.el8                                             baseos                       16 k
 freetype                                    x86_64                   2.9.1-4.el8_3.1                                         baseos                      394 k
 fribidi                                     x86_64                   1.0.4-8.el8                                             appstream                    89 k
 gdk-pixbuf2                                 x86_64                   2.36.12-5.el8                                           baseos                      467 k
 gdk-pixbuf2-modules                         x86_64                   2.36.12-5.el8                                           appstream                   109 k
 giflib                                      x86_64                   5.1.4-3.el8                                             appstream                    51 k
 glib-networking                             x86_64                   2.56.1-1.1.el8                                          baseos                      155 k
 graphite2                                   x86_64                   1.3.10-10.el8                                           appstream                   122 k
 gsettings-desktop-schemas                   x86_64                   3.32.0-6.el8                                            baseos                      633 k
 gtk-update-icon-cache                       x86_64                   3.22.30-8.el8                                           appstream                    32 k
 harfbuzz                                    x86_64                   1.7.5-3.el8                                             appstream                   295 k
 hicolor-icon-theme                          noarch                   0.17-2.el8                                              appstream                    49 k
 jasper-libs                                 x86_64                   2.0.14-5.el8                                            appstream                   167 k
 java-17-openjdk-headless                    x86_64                   1:17.0.1.0.12-2.el8_5                                   appstream                    41 M
 javapackages-filesystem                     noarch                   5.3.0-1.module_el8.0.0+11+5b8c10bd                      appstream                    30 k
 jbigkit-libs                                x86_64                   2.1-14.el8                                              appstream                    55 k
 json-glib                                   x86_64                   1.4.4-1.el8                                             baseos                      144 k
 lcms2                                       x86_64                   2.9-2.el8                                               appstream                   165 k
 libX11                                      x86_64                   1.6.8-5.el8                                             appstream                   611 k
 libX11-common                               noarch                   1.6.8-5.el8                                             appstream                   158 k
 libXau                                      x86_64                   1.0.9-3.el8                                             appstream                    37 k
 libXcomposite                               x86_64                   0.4.4-14.el8                                            appstream                    28 k
 libXcursor                                  x86_64                   1.1.15-3.el8                                            appstream                    36 k
 libXdamage                                  x86_64                   1.1.4-14.el8                                            appstream                    27 k
 libXext                                     x86_64                   1.3.4-1.el8                                             appstream                    45 k
 libXfixes                                   x86_64                   5.0.3-7.el8                                             appstream                    25 k
 libXft                                      x86_64                   2.3.3-1.el8                                             appstream                    67 k
 libXi                                       x86_64                   1.7.10-1.el8                                            appstream                    49 k
 libXinerama                                 x86_64                   1.1.4-1.el8                                             appstream                    16 k
 libXrandr                                   x86_64                   1.5.2-1.el8                                             appstream                    34 k
 libXrender                                  x86_64                   0.9.10-7.el8                                            appstream                    33 k
 libXtst                                     x86_64                   1.2.3-7.el8                                             appstream                    22 k
 libdatrie                                   x86_64                   0.2.9-7.el8                                             appstream                    33 k
 libepoxy                                    x86_64                   1.5.8-1.el8                                             appstream                   225 k
 libfontenc                                  x86_64                   1.1.3-8.el8                                             appstream                    37 k
 libgusb                                     x86_64                   0.3.0-1.el8                                             baseos                       49 k
 libjpeg-turbo                               x86_64                   1.5.3-12.el8                                            appstream                   157 k
 libmodman                                   x86_64                   2.0.1-17.el8                                            baseos                       36 k
 libpkgconf                                  x86_64                   1.4.2-1.el8                                             baseos                       35 k
 libpng                                      x86_64                   2:1.6.34-5.el8                                          baseos                      126 k
 libproxy                                    x86_64                   0.4.15-5.2.el8                                          baseos                       75 k
 libsoup                                     x86_64                   2.62.3-2.el8                                            baseos                      424 k
 libthai                                     x86_64                   0.1.27-2.el8                                            appstream                   203 k
 libtiff                                     x86_64                   4.0.9-20.el8                                            appstream                   188 k
 libwayland-client                           x86_64                   1.19.0-1.el8                                            appstream                    39 k
 libwayland-cursor                           x86_64                   1.19.0-1.el8                                            appstream                    26 k
 libwayland-egl                              x86_64                   1.19.0-1.el8                                            appstream                    19 k
 libxcb                                      x86_64                   1.13.1-1.el8                                            appstream                   229 k
 libxkbcommon                                x86_64                   0.9.1-1.el8                                             appstream                   116 k
 lksctp-tools                                x86_64                   1.0.18-3.el8                                            baseos                      100 k
 lua                                         x86_64                   5.3.4-12.el8                                            appstream                   192 k
 nspr                                        x86_64                   4.32.0-1.el8_4                                          appstream                   142 k
 nss                                         x86_64                   3.67.0-7.el8_5                                          appstream                   741 k
 nss-softokn                                 x86_64                   3.67.0-7.el8_5                                          appstream                   487 k
 nss-softokn-freebl                          x86_64                   3.67.0-7.el8_5                                          appstream                   395 k
 nss-sysinit                                 x86_64                   3.67.0-7.el8_5                                          appstream                    73 k
 nss-util                                    x86_64                   3.67.0-7.el8_5                                          appstream                   137 k
 pango                                       x86_64                   1.42.4-8.el8                                            appstream                   297 k
 pixman                                      x86_64                   0.38.4-1.el8                                            appstream                   257 k
 pkgconf                                     x86_64                   1.4.2-1.el8                                             baseos                       38 k
 pkgconf-m4                                  noarch                   1.4.2-1.el8                                             baseos                       17 k
 pkgconf-pkg-config                          x86_64                   1.4.2-1.el8                                             baseos                       15 k
 rest                                        x86_64                   0.8.1-2.el8                                             appstream                    70 k
 shared-mime-info                            x86_64                   1.9-3.el8                                               baseos                      329 k
 ttmkfdir                                    x86_64                   3.0.9-54.el8                                            appstream                    62 k
 tzdata-java                                 noarch                   2021e-1.el8                                             appstream                   191 k
 xkeyboard-config                            noarch                   2.28-1.el8                                              appstream                   782 k
 xorg-x11-font-utils                         x86_64                   1:7.5-41.el8                                            appstream                   104 k
 xorg-x11-fonts-Type1                        noarch                   7.5-19.el8                                              appstream                   522 k
Installing weak dependencies:
 abattis-cantarell-fonts                     noarch                   0.0.25-6.el8                                            appstream                   156 k
 dconf                                       x86_64                   0.28.0-4.el8                                            appstream                   108 k
 gtk3                                        x86_64                   3.22.30-8.el8                                           appstream                   4.5 M
Enabling module streams:
 javapackages-runtime                                                 201801

Transaction Summary
================================================================================================================================================================Install  89 Packages
Upgrade   2 Packages

Total download size: 72 M
Downloading Packages:
(1/91): abattis-cantarell-fonts-0.0.25-6.el8.noarch.rpm                                                                          38 kB/s | 156 kB     00:04
(2/91): adwaita-cursor-theme-3.28.0-2.el8.noarch.rpm                                                                            146 kB/s | 647 kB     00:04
(3/91): at-spi2-atk-2.26.2-1.el8.x86_64.rpm                                                                                     186 kB/s |  89 kB     00:00
(4/91): at-spi2-core-2.28.0-1.el8.x86_64.rpm                                                                                    221 kB/s | 169 kB     00:00
(5/91): adwaita-icon-theme-3.28.0-2.el8.noarch.rpm                                                                              1.8 MB/s |  11 MB     00:06
(6/91): alsa-lib-1.2.5-4.el8.x86_64.rpm                                                                                         209 kB/s | 489 kB     00:02
(7/91): atk-2.28.1-1.el8.x86_64.rpm                                                                                             310 kB/s | 272 kB     00:00
(8/91): colord-libs-1.4.2-1.el8.x86_64.rpm                                                                                      351 kB/s | 236 kB     00:00
(9/91): cairo-gobject-1.15.12-3.el8.x86_64.rpm                                                                                   36 kB/s |  33 kB     00:00
(10/91): copy-jdk-configs-4.0-2.el8.noarch.rpm                                                                                   73 kB/s |  31 kB     00:00
(11/91): dconf-0.28.0-4.el8.x86_64.rpm                                                                                          157 kB/s | 108 kB     00:00
(12/91): gdk-pixbuf2-modules-2.36.12-5.el8.x86_64.rpm                                                                           164 kB/s | 109 kB     00:00
(13/91): cairo-1.15.12-3.el8.x86_64.rpm                                                                                         305 kB/s | 721 kB     00:02
(14/91): fribidi-1.0.4-8.el8.x86_64.rpm                                                                                          76 kB/s |  89 kB     00:01
(15/91): gtk-update-icon-cache-3.22.30-8.el8.x86_64.rpm                                                                          82 kB/s |  32 kB     00:00
(16/91): graphite2-1.3.10-10.el8.x86_64.rpm                                                                                     192 kB/s | 122 kB     00:00
(17/91): giflib-5.1.4-3.el8.x86_64.rpm                                                                                           69 kB/s |  51 kB     00:00
(18/91): hicolor-icon-theme-0.17-2.el8.noarch.rpm                                                                               120 kB/s |  49 kB     00:00
(19/91): jasper-libs-2.0.14-5.el8.x86_64.rpm                                                                                    251 kB/s | 167 kB     00:00
(20/91): harfbuzz-1.7.5-3.el8.x86_64.rpm                                                                                        177 kB/s | 295 kB     00:01
(21/91): java-17-openjdk-17.0.1.0.12-2.el8_5.x86_64.rpm                                                                         348 kB/s | 244 kB     00:00
(22/91): javapackages-filesystem-5.3.0-1.module_el8.0.0+11+5b8c10bd.noarch.rpm                                                   75 kB/s |  30 kB     00:00
(23/91): jbigkit-libs-2.1-14.el8.x86_64.rpm                                                                                     135 kB/s |  55 kB     00:00
(24/91): lcms2-2.9-2.el8.x86_64.rpm                                                                                             245 kB/s | 165 kB     00:00
(25/91): gtk3-3.22.30-8.el8.x86_64.rpm                                                                                          1.1 MB/s | 4.5 MB     00:04
(26/91): libX11-common-1.6.8-5.el8.noarch.rpm                                                                                   245 kB/s | 158 kB     00:00
(27/91): libXau-1.0.9-3.el8.x86_64.rpm                                                                                           95 kB/s |  37 kB     00:00
(28/91): libXcomposite-0.4.4-14.el8.x86_64.rpm                                                                                   57 kB/s |  28 kB     00:00
(29/91): libXcursor-1.1.15-3.el8.x86_64.rpm                                                                                      56 kB/s |  36 kB     00:00
(30/91): libXdamage-1.1.4-14.el8.x86_64.rpm                                                                                      70 kB/s |  27 kB     00:00
(31/91): libXext-1.3.4-1.el8.x86_64.rpm                                                                                         116 kB/s |  45 kB     00:00
(32/91): libXfixes-5.0.3-7.el8.x86_64.rpm                                                                                        59 kB/s |  25 kB     00:00
(33/91): libXft-2.3.3-1.el8.x86_64.rpm                                                                                          163 kB/s |  67 kB     00:00
(34/91): libXi-1.7.10-1.el8.x86_64.rpm                                                                                          123 kB/s |  49 kB     00:00
(35/91): libXinerama-1.1.4-1.el8.x86_64.rpm                                                                                      41 kB/s |  16 kB     00:00
(36/91): libX11-1.6.8-5.el8.x86_64.rpm                                                                                          108 kB/s | 611 kB     00:05
(37/91): libXrandr-1.5.2-1.el8.x86_64.rpm                                                                                        52 kB/s |  34 kB     00:00
(38/91): libXrender-0.9.10-7.el8.x86_64.rpm                                                                                      27 kB/s |  33 kB     00:01
(39/91): libXtst-1.2.3-7.el8.x86_64.rpm                                                                                          16 kB/s |  22 kB     00:01
(40/91): libdatrie-0.2.9-7.el8.x86_64.rpm                                                                                        31 kB/s |  33 kB     00:01
(41/91): libepoxy-1.5.8-1.el8.x86_64.rpm                                                                                        127 kB/s | 225 kB     00:01
(42/91): libfontenc-1.1.3-8.el8.x86_64.rpm                                                                                       37 kB/s |  37 kB     00:01
(43/91): libthai-0.1.27-2.el8.x86_64.rpm                                                                                        155 kB/s | 203 kB     00:01
(44/91): libjpeg-turbo-1.5.3-12.el8.x86_64.rpm                                                                                   75 kB/s | 157 kB     00:02
(45/91): libtiff-4.0.9-20.el8.x86_64.rpm                                                                                        154 kB/s | 188 kB     00:01
(46/91): libwayland-client-1.19.0-1.el8.x86_64.rpm                                                                               56 kB/s |  39 kB     00:00
(47/91): libwayland-egl-1.19.0-1.el8.x86_64.rpm                                                                                  33 kB/s |  19 kB     00:00
(48/91): libwayland-cursor-1.19.0-1.el8.x86_64.rpm                                                                               30 kB/s |  26 kB     00:00
(49/91): libxkbcommon-0.9.1-1.el8.x86_64.rpm                                                                                    133 kB/s | 116 kB     00:00
(50/91): lua-5.3.4-12.el8.x86_64.rpm                                                                                            160 kB/s | 192 kB     00:01
(51/91): libxcb-1.13.1-1.el8.x86_64.rpm                                                                                         104 kB/s | 229 kB     00:02
(52/91): nspr-4.32.0-1.el8_4.x86_64.rpm                                                                                          87 kB/s | 142 kB     00:01
(53/91): nss-3.67.0-7.el8_5.x86_64.rpm                                                                                          218 kB/s | 741 kB     00:03
(54/91): nss-softokn-freebl-3.67.0-7.el8_5.x86_64.rpm                                                                           265 kB/s | 395 kB     00:01
(55/91): nss-softokn-3.67.0-7.el8_5.x86_64.rpm                                                                                  140 kB/s | 487 kB     00:03
(56/91): nss-sysinit-3.67.0-7.el8_5.x86_64.rpm                                                                                  100 kB/s |  73 kB     00:00
(57/91): nss-util-3.67.0-7.el8_5.x86_64.rpm                                                                                     171 kB/s | 137 kB     00:00
(58/91): pixman-0.38.4-1.el8.x86_64.rpm                                                                                         198 kB/s | 257 kB     00:01
(59/91): pango-1.42.4-8.el8.x86_64.rpm                                                                                          137 kB/s | 297 kB     00:02
(60/91): rest-0.8.1-2.el8.x86_64.rpm                                                                                             88 kB/s |  70 kB     00:00
(61/91): ttmkfdir-3.0.9-54.el8.x86_64.rpm                                                                                        73 kB/s |  62 kB     00:00
(62/91): tzdata-java-2021e-1.el8.noarch.rpm                                                                                     200 kB/s | 191 kB     00:00
(63/91): xorg-x11-font-utils-7.5-41.el8.x86_64.rpm                                                                              130 kB/s | 104 kB     00:00
(64/91): xkeyboard-config-2.28-1.el8.noarch.rpm                                                                                 243 kB/s | 782 kB     00:03
(65/91): xorg-x11-fonts-Type1-7.5-19.el8.noarch.rpm                                                                             233 kB/s | 522 kB     00:02
(66/91): avahi-libs-0.7-20.el8.x86_64.rpm                                                                                       111 kB/s |  62 kB     00:00
(67/91): crypto-policies-scripts-20210617-1.gitc776d3e.el8.noarch.rpm                                                            99 kB/s |  83 kB     00:00
(68/91): dejavu-fonts-common-2.35-7.el8.noarch.rpm                                                                               88 kB/s |  74 kB     00:00
(69/91): cups-libs-2.2.6-40.el8.x86_64.rpm                                                                                      239 kB/s | 433 kB     00:01
(70/91): fontconfig-2.13.1-4.el8.x86_64.rpm                                                                                     287 kB/s | 274 kB     00:00
(71/91): dejavu-sans-mono-fonts-2.35-7.el8.noarch.rpm                                                                           277 kB/s | 447 kB     00:01
(72/91): fontpackages-filesystem-1.44-22.el8.noarch.rpm                                                                          40 kB/s |  16 kB     00:00
(73/91): freetype-2.9.1-4.el8_3.1.x86_64.rpm                                                                                    252 kB/s | 394 kB     00:01
(74/91): gdk-pixbuf2-2.36.12-5.el8.x86_64.rpm                                                                                   369 kB/s | 467 kB     00:01
(75/91): glib-networking-2.56.1-1.1.el8.x86_64.rpm                                                                              230 kB/s | 155 kB     00:00
(76/91): json-glib-1.4.4-1.el8.x86_64.rpm                                                                                       227 kB/s | 144 kB     00:00
(77/91): gsettings-desktop-schemas-3.32.0-6.el8.x86_64.rpm                                                                      356 kB/s | 633 kB     00:01
(78/91): libgusb-0.3.0-1.el8.x86_64.rpm                                                                                          57 kB/s |  49 kB     00:00
(79/91): libmodman-2.0.1-17.el8.x86_64.rpm                                                                                       50 kB/s |  36 kB     00:00
(80/91): libpkgconf-1.4.2-1.el8.x86_64.rpm                                                                                       41 kB/s |  35 kB     00:00
(81/91): libpng-1.6.34-5.el8.x86_64.rpm                                                                                         162 kB/s | 126 kB     00:00
(82/91): libproxy-0.4.15-5.2.el8.x86_64.rpm                                                                                     101 kB/s |  75 kB     00:00
(83/91): lksctp-tools-1.0.18-3.el8.x86_64.rpm                                                                                   129 kB/s | 100 kB     00:00
(84/91): libsoup-2.62.3-2.el8.x86_64.rpm                                                                                        287 kB/s | 424 kB     00:01
(85/91): pkgconf-1.4.2-1.el8.x86_64.rpm                                                                                          54 kB/s |  38 kB     00:00
(86/91): pkgconf-m4-1.4.2-1.el8.noarch.rpm                                                                                       26 kB/s |  17 kB     00:00
(87/91): pkgconf-pkg-config-1.4.2-1.el8.x86_64.rpm                                                                               37 kB/s |  15 kB     00:00
(88/91): crypto-policies-20210617-1.gitc776d3e.el8.noarch.rpm                                                                    84 kB/s |  63 kB     00:00
(89/91): shared-mime-info-1.9-3.el8.x86_64.rpm                                                                                  232 kB/s | 329 kB     00:01
(90/91): lua-libs-5.3.4-12.el8.x86_64.rpm                                                                                       127 kB/s | 118 kB     00:00
(91/91): java-17-openjdk-headless-17.0.1.0.12-2.el8_5.x86_64.rpm                                                                163 kB/s |  41 MB     04:17
----------------------------------------------------------------------------------------------------------------------------------------------------------------Total                                                                                                                           276 kB/s |  72 MB     04:28
warning: /var/cache/dnf/appstream-d7987f026ef99c82/packages/abattis-cantarell-fonts-0.0.25-6.el8.noarch.rpm: Header V3 RSA/SHA256 Signature, key ID 8483c65d: NOKEY
CentOS Linux 8 - AppStream                                                                                                      1.6 MB/s | 1.6 kB     00:00
Importing GPG key 0x8483C65D:
 Userid     : "CentOS (CentOS Official Signing Key) <security@centos.org>"
 Fingerprint: 99DB 70FA E1D7 CE22 7FB6 4882 05B5 55B3 8483 C65D
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-centosofficial
Key imported successfully
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Running scriptlet: copy-jdk-configs-4.0-2.el8.noarch                                                                                                      1/1
  Running scriptlet: java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                                                                                  1/1
  Preparing        :                                                                                                                                        1/1
  Installing       : libpng-2:1.6.34-5.el8.x86_64                                                                                                          1/93
  Installing       : freetype-2.9.1-4.el8_3.1.x86_64                                                                                                       2/93
  Installing       : nspr-4.32.0-1.el8_4.x86_64                                                                                                            3/93
  Running scriptlet: nspr-4.32.0-1.el8_4.x86_64                                                                                                            3/93
  Installing       : nss-util-3.67.0-7.el8_5.x86_64                                                                                                        4/93
  Installing       : libjpeg-turbo-1.5.3-12.el8.x86_64                                                                                                     5/93
  Installing       : fontpackages-filesystem-1.44-22.el8.noarch                                                                                            6/93
  Installing       : abattis-cantarell-fonts-0.0.25-6.el8.noarch                                                                                           7/93
  Installing       : fontconfig-2.13.1-4.el8.x86_64                                                                                                        8/93
  Running scriptlet: fontconfig-2.13.1-4.el8.x86_64                                                                                                        8/93
  Upgrading        : crypto-policies-20210617-1.gitc776d3e.el8.noarch                                                                                      9/93
  Running scriptlet: crypto-policies-20210617-1.gitc776d3e.el8.noarch                                                                                      9/93
  Installing       : crypto-policies-scripts-20210617-1.gitc776d3e.el8.noarch                                                                             10/93
  Installing       : pixman-0.38.4-1.el8.x86_64                                                                                                           11/93
  Installing       : libwayland-client-1.19.0-1.el8.x86_64                                                                                                12/93
  Installing       : lcms2-2.9-2.el8.x86_64                                                                                                               13/93
  Running scriptlet: lcms2-2.9-2.el8.x86_64                                                                                                               13/93
  Installing       : atk-2.28.1-1.el8.x86_64                                                                                                              14/93
  Installing       : libwayland-cursor-1.19.0-1.el8.x86_64                                                                                                15/93
  Installing       : dejavu-fonts-common-2.35-7.el8.noarch                                                                                                16/93
  Installing       : dejavu-sans-mono-fonts-2.35-7.el8.noarch                                                                                             17/93
  Installing       : gsettings-desktop-schemas-3.32.0-6.el8.x86_64                                                                                        18/93
  Installing       : jasper-libs-2.0.14-5.el8.x86_64                                                                                                      19/93
  Installing       : nss-softokn-freebl-3.67.0-7.el8_5.x86_64                                                                                             20/93
  Installing       : nss-softokn-3.67.0-7.el8_5.x86_64                                                                                                    21/93
  Installing       : nss-3.67.0-7.el8_5.x86_64                                                                                                            22/93
  Installing       : nss-sysinit-3.67.0-7.el8_5.x86_64                                                                                                    23/93
  Installing       : ttmkfdir-3.0.9-54.el8.x86_64                                                                                                         24/93
  Upgrading        : lua-libs-5.3.4-12.el8.x86_64                                                                                                         25/93
  Installing       : lua-5.3.4-12.el8.x86_64                                                                                                              26/93
  Installing       : copy-jdk-configs-4.0-2.el8.noarch                                                                                                    27/93
  Installing       : shared-mime-info-1.9-3.el8.x86_64                                                                                                    28/93
  Running scriptlet: shared-mime-info-1.9-3.el8.x86_64                                                                                                    28/93
  Installing       : gdk-pixbuf2-2.36.12-5.el8.x86_64                                                                                                     29/93
  Running scriptlet: gdk-pixbuf2-2.36.12-5.el8.x86_64                                                                                                     29/93
  Installing       : gtk-update-icon-cache-3.22.30-8.el8.x86_64                                                                                           30/93
  Installing       : pkgconf-m4-1.4.2-1.el8.noarch                                                                                                        31/93
  Installing       : lksctp-tools-1.0.18-3.el8.x86_64                                                                                                     32/93
  Running scriptlet: lksctp-tools-1.0.18-3.el8.x86_64                                                                                                     32/93
  Installing       : libpkgconf-1.4.2-1.el8.x86_64                                                                                                        33/93
  Installing       : pkgconf-1.4.2-1.el8.x86_64                                                                                                           34/93
  Installing       : pkgconf-pkg-config-1.4.2-1.el8.x86_64                                                                                                35/93
  Installing       : libmodman-2.0.1-17.el8.x86_64                                                                                                        36/93
  Running scriptlet: libmodman-2.0.1-17.el8.x86_64                                                                                                        36/93
  Installing       : libproxy-0.4.15-5.2.el8.x86_64                                                                                                       37/93
  Running scriptlet: libproxy-0.4.15-5.2.el8.x86_64                                                                                                       37/93
  Installing       : glib-networking-2.56.1-1.1.el8.x86_64                                                                                                38/93
  Installing       : libsoup-2.62.3-2.el8.x86_64                                                                                                          39/93
  Installing       : rest-0.8.1-2.el8.x86_64                                                                                                              40/93
  Running scriptlet: rest-0.8.1-2.el8.x86_64                                                                                                              40/93
  Installing       : libgusb-0.3.0-1.el8.x86_64                                                                                                           41/93
  Installing       : colord-libs-1.4.2-1.el8.x86_64                                                                                                       42/93
  Installing       : json-glib-1.4.4-1.el8.x86_64                                                                                                         43/93
  Installing       : avahi-libs-0.7-20.el8.x86_64                                                                                                         44/93
  Installing       : cups-libs-1:2.2.6-40.el8.x86_64                                                                                                      45/93
  Installing       : xkeyboard-config-2.28-1.el8.noarch                                                                                                   46/93
  Installing       : libxkbcommon-0.9.1-1.el8.x86_64                                                                                                      47/93
  Installing       : tzdata-java-2021e-1.el8.noarch                                                                                                       48/93
  Installing       : libwayland-egl-1.19.0-1.el8.x86_64                                                                                                   49/93
  Installing       : libfontenc-1.1.3-8.el8.x86_64                                                                                                        50/93
  Installing       : xorg-x11-font-utils-1:7.5-41.el8.x86_64                                                                                              51/93
  Installing       : xorg-x11-fonts-Type1-7.5-19.el8.noarch                                                                                               52/93
  Running scriptlet: xorg-x11-fonts-Type1-7.5-19.el8.noarch                                                                                               52/93
  Installing       : libepoxy-1.5.8-1.el8.x86_64                                                                                                          53/93
  Installing       : libdatrie-0.2.9-7.el8.x86_64                                                                                                         54/93
  Running scriptlet: libdatrie-0.2.9-7.el8.x86_64                                                                                                         54/93
  Installing       : libthai-0.1.27-2.el8.x86_64                                                                                                          55/93
  Running scriptlet: libthai-0.1.27-2.el8.x86_64                                                                                                          55/93
  Installing       : libXau-1.0.9-3.el8.x86_64                                                                                                            56/93
  Installing       : libxcb-1.13.1-1.el8.x86_64                                                                                                           57/93
  Installing       : libX11-common-1.6.8-5.el8.noarch                                                                                                     58/93
  Installing       : libX11-1.6.8-5.el8.x86_64                                                                                                            59/93
  Installing       : libXext-1.3.4-1.el8.x86_64                                                                                                           60/93
  Installing       : libXrender-0.9.10-7.el8.x86_64                                                                                                       61/93
  Installing       : cairo-1.15.12-3.el8.x86_64                                                                                                           62/93
  Installing       : libXi-1.7.10-1.el8.x86_64                                                                                                            63/93
  Installing       : libXfixes-5.0.3-7.el8.x86_64                                                                                                         64/93
  Installing       : libXtst-1.2.3-7.el8.x86_64                                                                                                           65/93
  Installing       : libXcomposite-0.4.4-14.el8.x86_64                                                                                                    66/93
  Installing       : at-spi2-core-2.28.0-1.el8.x86_64                                                                                                     67/93
  Running scriptlet: at-spi2-core-2.28.0-1.el8.x86_64                                                                                                     67/93
  Installing       : at-spi2-atk-2.26.2-1.el8.x86_64                                                                                                      68/93
  Running scriptlet: at-spi2-atk-2.26.2-1.el8.x86_64                                                                                                      68/93
  Installing       : libXcursor-1.1.15-3.el8.x86_64                                                                                                       69/93
  Installing       : libXdamage-1.1.4-14.el8.x86_64                                                                                                       70/93
  Installing       : cairo-gobject-1.15.12-3.el8.x86_64                                                                                                   71/93
  Installing       : libXft-2.3.3-1.el8.x86_64                                                                                                            72/93
  Installing       : libXrandr-1.5.2-1.el8.x86_64                                                                                                         73/93
  Installing       : libXinerama-1.1.4-1.el8.x86_64                                                                                                       74/93
  Installing       : jbigkit-libs-2.1-14.el8.x86_64                                                                                                       75/93
  Running scriptlet: jbigkit-libs-2.1-14.el8.x86_64                                                                                                       75/93
  Installing       : libtiff-4.0.9-20.el8.x86_64                                                                                                          76/93
  Installing       : gdk-pixbuf2-modules-2.36.12-5.el8.x86_64                                                                                             77/93
  Installing       : javapackages-filesystem-5.3.0-1.module_el8.0.0+11+5b8c10bd.noarch                                                                    78/93
  Installing       : hicolor-icon-theme-0.17-2.el8.noarch                                                                                                 79/93
  Installing       : graphite2-1.3.10-10.el8.x86_64                                                                                                       80/93
  Installing       : harfbuzz-1.7.5-3.el8.x86_64                                                                                                          81/93
  Running scriptlet: harfbuzz-1.7.5-3.el8.x86_64                                                                                                          81/93
  Installing       : giflib-5.1.4-3.el8.x86_64                                                                                                            82/93
  Installing       : fribidi-1.0.4-8.el8.x86_64                                                                                                           83/93
  Installing       : pango-1.42.4-8.el8.x86_64                                                                                                            84/93
  Running scriptlet: pango-1.42.4-8.el8.x86_64                                                                                                            84/93
  Installing       : dconf-0.28.0-4.el8.x86_64                                                                                                            85/93
  Installing       : alsa-lib-1.2.5-4.el8.x86_64                                                                                                          86/93
  Running scriptlet: alsa-lib-1.2.5-4.el8.x86_64                                                                                                          86/93
  Installing       : java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                                                                                87/93
  Running scriptlet: java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                                                                                87/93
  Installing       : adwaita-cursor-theme-3.28.0-2.el8.noarch                                                                                             88/93
  Installing       : adwaita-icon-theme-3.28.0-2.el8.noarch                                                                                               89/93
  Installing       : gtk3-3.22.30-8.el8.x86_64                                                                                                            90/93
  Installing       : java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                                                                         91/93
  Running scriptlet: java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                                                                         91/93
  Cleanup          : crypto-policies-20210209-1.gitbfb6bed.el8_3.noarch                                                                                   92/93
  Cleanup          : lua-libs-5.3.4-11.el8.x86_64                                                                                                         93/93
  Running scriptlet: crypto-policies-scripts-20210617-1.gitc776d3e.el8.noarch                                                                             93/93
  Running scriptlet: nss-3.67.0-7.el8_5.x86_64                                                                                                            93/93
  Running scriptlet: copy-jdk-configs-4.0-2.el8.noarch                                                                                                    93/93
  Running scriptlet: dconf-0.28.0-4.el8.x86_64                                                                                                            93/93
  Running scriptlet: java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                                                                         93/93
  Running scriptlet: lua-libs-5.3.4-11.el8.x86_64                                                                                                         93/93
  Running scriptlet: fontconfig-2.13.1-4.el8.x86_64                                                                                                       93/93
  Running scriptlet: shared-mime-info-1.9-3.el8.x86_64                                                                                                    93/93
  Running scriptlet: gdk-pixbuf2-2.36.12-5.el8.x86_64                                                                                                     93/93
  Running scriptlet: hicolor-icon-theme-0.17-2.el8.noarch                                                                                                 93/93
  Running scriptlet: adwaita-icon-theme-3.28.0-2.el8.noarch                                                                                               93/93
  Verifying        : abattis-cantarell-fonts-0.0.25-6.el8.noarch                                                                                           1/93
  Verifying        : adwaita-cursor-theme-3.28.0-2.el8.noarch                                                                                              2/93
  Verifying        : adwaita-icon-theme-3.28.0-2.el8.noarch                                                                                                3/93
  Verifying        : alsa-lib-1.2.5-4.el8.x86_64                                                                                                           4/93
  Verifying        : at-spi2-atk-2.26.2-1.el8.x86_64                                                                                                       5/93
  Verifying        : at-spi2-core-2.28.0-1.el8.x86_64                                                                                                      6/93
  Verifying        : atk-2.28.1-1.el8.x86_64                                                                                                               7/93
  Verifying        : cairo-1.15.12-3.el8.x86_64                                                                                                            8/93
  Verifying        : cairo-gobject-1.15.12-3.el8.x86_64                                                                                                    9/93
  Verifying        : colord-libs-1.4.2-1.el8.x86_64                                                                                                       10/93
  Verifying        : copy-jdk-configs-4.0-2.el8.noarch                                                                                                    11/93
  Verifying        : dconf-0.28.0-4.el8.x86_64                                                                                                            12/93
  Verifying        : fribidi-1.0.4-8.el8.x86_64                                                                                                           13/93
  Verifying        : gdk-pixbuf2-modules-2.36.12-5.el8.x86_64                                                                                             14/93
  Verifying        : giflib-5.1.4-3.el8.x86_64                                                                                                            15/93
  Verifying        : graphite2-1.3.10-10.el8.x86_64                                                                                                       16/93
  Verifying        : gtk-update-icon-cache-3.22.30-8.el8.x86_64                                                                                           17/93
  Verifying        : gtk3-3.22.30-8.el8.x86_64                                                                                                            18/93
  Verifying        : harfbuzz-1.7.5-3.el8.x86_64                                                                                                          19/93
  Verifying        : hicolor-icon-theme-0.17-2.el8.noarch                                                                                                 20/93
  Verifying        : jasper-libs-2.0.14-5.el8.x86_64                                                                                                      21/93
  Verifying        : java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                                                                         22/93
  Verifying        : java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                                                                                23/93
  Verifying        : javapackages-filesystem-5.3.0-1.module_el8.0.0+11+5b8c10bd.noarch                                                                    24/93
  Verifying        : jbigkit-libs-2.1-14.el8.x86_64                                                                                                       25/93
  Verifying        : lcms2-2.9-2.el8.x86_64                                                                                                               26/93
  Verifying        : libX11-1.6.8-5.el8.x86_64                                                                                                            27/93
  Verifying        : libX11-common-1.6.8-5.el8.noarch                                                                                                     28/93
  Verifying        : libXau-1.0.9-3.el8.x86_64                                                                                                            29/93
  Verifying        : libXcomposite-0.4.4-14.el8.x86_64                                                                                                    30/93
  Verifying        : libXcursor-1.1.15-3.el8.x86_64                                                                                                       31/93
  Verifying        : libXdamage-1.1.4-14.el8.x86_64                                                                                                       32/93
  Verifying        : libXext-1.3.4-1.el8.x86_64                                                                                                           33/93
  Verifying        : libXfixes-5.0.3-7.el8.x86_64                                                                                                         34/93
  Verifying        : libXft-2.3.3-1.el8.x86_64                                                                                                            35/93
  Verifying        : libXi-1.7.10-1.el8.x86_64                                                                                                            36/93
  Verifying        : libXinerama-1.1.4-1.el8.x86_64                                                                                                       37/93
  Verifying        : libXrandr-1.5.2-1.el8.x86_64                                                                                                         38/93
  Verifying        : libXrender-0.9.10-7.el8.x86_64                                                                                                       39/93
  Verifying        : libXtst-1.2.3-7.el8.x86_64                                                                                                           40/93
  Verifying        : libdatrie-0.2.9-7.el8.x86_64                                                                                                         41/93
  Verifying        : libepoxy-1.5.8-1.el8.x86_64                                                                                                          42/93
  Verifying        : libfontenc-1.1.3-8.el8.x86_64                                                                                                        43/93
  Verifying        : libjpeg-turbo-1.5.3-12.el8.x86_64                                                                                                    44/93
  Verifying        : libthai-0.1.27-2.el8.x86_64                                                                                                          45/93
  Verifying        : libtiff-4.0.9-20.el8.x86_64                                                                                                          46/93
  Verifying        : libwayland-client-1.19.0-1.el8.x86_64                                                                                                47/93
  Verifying        : libwayland-cursor-1.19.0-1.el8.x86_64                                                                                                48/93
  Verifying        : libwayland-egl-1.19.0-1.el8.x86_64                                                                                                   49/93
  Verifying        : libxcb-1.13.1-1.el8.x86_64                                                                                                           50/93
  Verifying        : libxkbcommon-0.9.1-1.el8.x86_64                                                                                                      51/93
  Verifying        : lua-5.3.4-12.el8.x86_64                                                                                                              52/93
  Verifying        : nspr-4.32.0-1.el8_4.x86_64                                                                                                           53/93
  Verifying        : nss-3.67.0-7.el8_5.x86_64                                                                                                            54/93
  Verifying        : nss-softokn-3.67.0-7.el8_5.x86_64                                                                                                    55/93
  Verifying        : nss-softokn-freebl-3.67.0-7.el8_5.x86_64                                                                                             56/93
  Verifying        : nss-sysinit-3.67.0-7.el8_5.x86_64                                                                                                    57/93
  Verifying        : nss-util-3.67.0-7.el8_5.x86_64                                                                                                       58/93
  Verifying        : pango-1.42.4-8.el8.x86_64                                                                                                            59/93
  Verifying        : pixman-0.38.4-1.el8.x86_64                                                                                                           60/93
  Verifying        : rest-0.8.1-2.el8.x86_64                                                                                                              61/93
  Verifying        : ttmkfdir-3.0.9-54.el8.x86_64                                                                                                         62/93
  Verifying        : tzdata-java-2021e-1.el8.noarch                                                                                                       63/93
  Verifying        : xkeyboard-config-2.28-1.el8.noarch                                                                                                   64/93
  Verifying        : xorg-x11-font-utils-1:7.5-41.el8.x86_64                                                                                              65/93
  Verifying        : xorg-x11-fonts-Type1-7.5-19.el8.noarch                                                                                               66/93
  Verifying        : avahi-libs-0.7-20.el8.x86_64                                                                                                         67/93
  Verifying        : crypto-policies-scripts-20210617-1.gitc776d3e.el8.noarch                                                                             68/93
  Verifying        : cups-libs-1:2.2.6-40.el8.x86_64                                                                                                      69/93
  Verifying        : dejavu-fonts-common-2.35-7.el8.noarch                                                                                                70/93
  Verifying        : dejavu-sans-mono-fonts-2.35-7.el8.noarch                                                                                             71/93
  Verifying        : fontconfig-2.13.1-4.el8.x86_64                                                                                                       72/93
  Verifying        : fontpackages-filesystem-1.44-22.el8.noarch                                                                                           73/93
  Verifying        : freetype-2.9.1-4.el8_3.1.x86_64                                                                                                      74/93
  Verifying        : gdk-pixbuf2-2.36.12-5.el8.x86_64                                                                                                     75/93
  Verifying        : glib-networking-2.56.1-1.1.el8.x86_64                                                                                                76/93
  Verifying        : gsettings-desktop-schemas-3.32.0-6.el8.x86_64                                                                                        77/93
  Verifying        : json-glib-1.4.4-1.el8.x86_64                                                                                                         78/93
  Verifying        : libgusb-0.3.0-1.el8.x86_64                                                                                                           79/93
  Verifying        : libmodman-2.0.1-17.el8.x86_64                                                                                                        80/93
  Verifying        : libpkgconf-1.4.2-1.el8.x86_64                                                                                                        81/93
  Verifying        : libpng-2:1.6.34-5.el8.x86_64                                                                                                         82/93
  Verifying        : libproxy-0.4.15-5.2.el8.x86_64                                                                                                       83/93
  Verifying        : libsoup-2.62.3-2.el8.x86_64                                                                                                          84/93
  Verifying        : lksctp-tools-1.0.18-3.el8.x86_64                                                                                                     85/93
  Verifying        : pkgconf-1.4.2-1.el8.x86_64                                                                                                           86/93
  Verifying        : pkgconf-m4-1.4.2-1.el8.noarch                                                                                                        87/93
  Verifying        : pkgconf-pkg-config-1.4.2-1.el8.x86_64                                                                                                88/93
  Verifying        : shared-mime-info-1.9-3.el8.x86_64                                                                                                    89/93
  Verifying        : crypto-policies-20210617-1.gitc776d3e.el8.noarch                                                                                     90/93
  Verifying        : crypto-policies-20210209-1.gitbfb6bed.el8_3.noarch                                                                                   91/93
  Verifying        : lua-libs-5.3.4-12.el8.x86_64                                                                                                         92/93
  Verifying        : lua-libs-5.3.4-11.el8.x86_64                                                                                                         93/93

Upgraded:
  crypto-policies-20210617-1.gitc776d3e.el8.noarch                                         lua-libs-5.3.4-12.el8.x86_64
Installed:
  abattis-cantarell-fonts-0.0.25-6.el8.noarch                                          adwaita-cursor-theme-3.28.0-2.el8.noarch
  adwaita-icon-theme-3.28.0-2.el8.noarch                                               alsa-lib-1.2.5-4.el8.x86_64
  at-spi2-atk-2.26.2-1.el8.x86_64                                                      at-spi2-core-2.28.0-1.el8.x86_64
  atk-2.28.1-1.el8.x86_64                                                              avahi-libs-0.7-20.el8.x86_64
  cairo-1.15.12-3.el8.x86_64                                                           cairo-gobject-1.15.12-3.el8.x86_64
  colord-libs-1.4.2-1.el8.x86_64                                                       copy-jdk-configs-4.0-2.el8.noarch
  crypto-policies-scripts-20210617-1.gitc776d3e.el8.noarch                             cups-libs-1:2.2.6-40.el8.x86_64
  dconf-0.28.0-4.el8.x86_64                                                            dejavu-fonts-common-2.35-7.el8.noarch
  dejavu-sans-mono-fonts-2.35-7.el8.noarch                                             fontconfig-2.13.1-4.el8.x86_64
  fontpackages-filesystem-1.44-22.el8.noarch                                           freetype-2.9.1-4.el8_3.1.x86_64
  fribidi-1.0.4-8.el8.x86_64                                                           gdk-pixbuf2-2.36.12-5.el8.x86_64
  gdk-pixbuf2-modules-2.36.12-5.el8.x86_64                                             giflib-5.1.4-3.el8.x86_64
  glib-networking-2.56.1-1.1.el8.x86_64                                                graphite2-1.3.10-10.el8.x86_64
  gsettings-desktop-schemas-3.32.0-6.el8.x86_64                                        gtk-update-icon-cache-3.22.30-8.el8.x86_64
  gtk3-3.22.30-8.el8.x86_64                                                            harfbuzz-1.7.5-3.el8.x86_64
  hicolor-icon-theme-0.17-2.el8.noarch                                                 jasper-libs-2.0.14-5.el8.x86_64
  java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                         java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64
  javapackages-filesystem-5.3.0-1.module_el8.0.0+11+5b8c10bd.noarch                    jbigkit-libs-2.1-14.el8.x86_64
  json-glib-1.4.4-1.el8.x86_64                                                         lcms2-2.9-2.el8.x86_64
  libX11-1.6.8-5.el8.x86_64                                                            libX11-common-1.6.8-5.el8.noarch
  libXau-1.0.9-3.el8.x86_64                                                            libXcomposite-0.4.4-14.el8.x86_64
  libXcursor-1.1.15-3.el8.x86_64                                                       libXdamage-1.1.4-14.el8.x86_64
  libXext-1.3.4-1.el8.x86_64                                                           libXfixes-5.0.3-7.el8.x86_64
  libXft-2.3.3-1.el8.x86_64                                                            libXi-1.7.10-1.el8.x86_64
  libXinerama-1.1.4-1.el8.x86_64                                                       libXrandr-1.5.2-1.el8.x86_64
  libXrender-0.9.10-7.el8.x86_64                                                       libXtst-1.2.3-7.el8.x86_64
  libdatrie-0.2.9-7.el8.x86_64                                                         libepoxy-1.5.8-1.el8.x86_64
  libfontenc-1.1.3-8.el8.x86_64                                                        libgusb-0.3.0-1.el8.x86_64
  libjpeg-turbo-1.5.3-12.el8.x86_64                                                    libmodman-2.0.1-17.el8.x86_64
  libpkgconf-1.4.2-1.el8.x86_64                                                        libpng-2:1.6.34-5.el8.x86_64
  libproxy-0.4.15-5.2.el8.x86_64                                                       libsoup-2.62.3-2.el8.x86_64
  libthai-0.1.27-2.el8.x86_64                                                          libtiff-4.0.9-20.el8.x86_64
  libwayland-client-1.19.0-1.el8.x86_64                                                libwayland-cursor-1.19.0-1.el8.x86_64
  libwayland-egl-1.19.0-1.el8.x86_64                                                   libxcb-1.13.1-1.el8.x86_64
  libxkbcommon-0.9.1-1.el8.x86_64                                                      lksctp-tools-1.0.18-3.el8.x86_64
  lua-5.3.4-12.el8.x86_64                                                              nspr-4.32.0-1.el8_4.x86_64
  nss-3.67.0-7.el8_5.x86_64                                                            nss-softokn-3.67.0-7.el8_5.x86_64
  nss-softokn-freebl-3.67.0-7.el8_5.x86_64                                             nss-sysinit-3.67.0-7.el8_5.x86_64
  nss-util-3.67.0-7.el8_5.x86_64                                                       pango-1.42.4-8.el8.x86_64
  pixman-0.38.4-1.el8.x86_64                                                           pkgconf-1.4.2-1.el8.x86_64
  pkgconf-m4-1.4.2-1.el8.noarch                                                        pkgconf-pkg-config-1.4.2-1.el8.x86_64
  rest-0.8.1-2.el8.x86_64                                                              shared-mime-info-1.9-3.el8.x86_64
  ttmkfdir-3.0.9-54.el8.x86_64                                                         tzdata-java-2021e-1.el8.noarch
  xkeyboard-config-2.28-1.el8.noarch                                                   xorg-x11-font-utils-1:7.5-41.el8.x86_64
  xorg-x11-fonts-Type1-7.5-19.el8.noarch

Complete!
[root@889e0484bdd2 /]#
```



验证是否安装成功：

```sh
java -version
```



```sh
[root@889e0484bdd2 /]# java -version
openjdk version "17.0.1" 2021-10-19 LTS
OpenJDK Runtime Environment 21.9 (build 17.0.1+12-LTS)
OpenJDK 64-Bit Server VM 21.9 (build 17.0.1+12-LTS, mixed mode, sharing)
[root@889e0484bdd2 /]#
```



安装成功





### yum 升级命令

使用 yum 升级软件包，需确保 yum 源服务器中软件包的版本比本机安装的软件包版本高。



升级所有软件包：

```sh
yum -y update
```



升级特定的软件包：

```sh
yum -y update 包名
```



升级jdk17：

```sh
yum -y update java-17-openjdk.x86_64
```



```sh
[root@889e0484bdd2 /]# yum -y update java-17-openjdk.x86_64
Failed to set locale, defaulting to C.UTF-8
Last metadata expiration check: 0:27:15 ago on Mon Jul  4 06:25:24 2022.
Dependencies resolved.
Nothing to do.
Complete!
[root@889e0484bdd2 /]#
```

已经是最新版，无法更新







### yum 卸载命令

**使用 yum 卸载软件包时，会同时卸载所有与该包有依赖关系的其他软件包，即便有依赖包属于系统运行必备文件，也会被 yum 无情卸载**，带来的直接后果就是使系统崩溃

**除非你能确定卸载此包以及它的所有依赖包不会对系统产生影响，否则不要使用 yum 卸载软件包**



卸载指定的软件包：

```sh
yum remove 包名
```



卸载jdk17：

```sh
yum remove java-17-openjdk.x86_64
```





```sh
[root@889e0484bdd2 /]# yum remove java-17-openjdk.x86_64
Failed to set locale, defaulting to C.UTF-8
Dependencies resolved.
================================================================================================================================================================
 Package                                     Architecture             Version                                                Repository                    Size
================================================================================================================================================================
Removing:
 java-17-openjdk                             x86_64                   1:17.0.1.0.12-2.el8_5                                  @appstream                   702 k
Removing unused dependencies:
 abattis-cantarell-fonts                     noarch                   0.0.25-6.el8                                           @appstream                   295 k
 adwaita-cursor-theme                        noarch                   3.28.0-2.el8                                           @appstream                    11 M
 adwaita-icon-theme                          noarch                   3.28.0-2.el8                                           @appstream                    13 M
 alsa-lib                                    x86_64                   1.2.5-4.el8                                            @appstream                   1.4 M
 at-spi2-atk                                 x86_64                   2.26.2-1.el8                                           @appstream                   247 k
 at-spi2-core                                x86_64                   2.28.0-1.el8                                           @appstream                   502 k
 atk                                         x86_64                   2.28.1-1.el8                                           @appstream                   1.2 M
 avahi-libs                                  x86_64                   0.7-20.el8                                             @baseos                      152 k
 cairo                                       x86_64                   1.15.12-3.el8                                          @appstream                   1.8 M
 cairo-gobject                               x86_64                   1.15.12-3.el8                                          @appstream                    36 k
 colord-libs                                 x86_64                   1.4.2-1.el8                                            @appstream                   824 k
 copy-jdk-configs                            noarch                   4.0-2.el8                                              @appstream                    19 k
 cups-libs                                   x86_64                   1:2.2.6-40.el8                                         @baseos                      926 k
 dconf                                       x86_64                   0.28.0-4.el8                                           @appstream                   304 k
 dejavu-fonts-common                         noarch                   2.35-7.el8                                             @baseos                      143 k
 dejavu-sans-mono-fonts                      noarch                   2.35-7.el8                                             @baseos                      1.1 M
 fontconfig                                  x86_64                   2.13.1-4.el8                                           @baseos                      694 k
 fontpackages-filesystem                     noarch                   1.44-22.el8                                            @baseos                        0
 freetype                                    x86_64                   2.9.1-4.el8_3.1                                        @baseos                      793 k
 fribidi                                     x86_64                   1.0.4-8.el8                                            @appstream                   312 k
 gdk-pixbuf2                                 x86_64                   2.36.12-5.el8                                          @baseos                      2.5 M
 gdk-pixbuf2-modules                         x86_64                   2.36.12-5.el8                                          @appstream                   308 k
 giflib                                      x86_64                   5.1.4-3.el8                                            @appstream                   103 k
 glib-networking                             x86_64                   2.56.1-1.1.el8                                         @baseos                      519 k
 graphite2                                   x86_64                   1.3.10-10.el8                                          @appstream                   264 k
 gsettings-desktop-schemas                   x86_64                   3.32.0-6.el8                                           @baseos                      4.0 M
 gtk-update-icon-cache                       x86_64                   3.22.30-8.el8                                          @appstream                    59 k
 gtk3                                        x86_64                   3.22.30-8.el8                                          @appstream                    17 M
 harfbuzz                                    x86_64                   1.7.5-3.el8                                            @appstream                   784 k
 hicolor-icon-theme                          noarch                   0.17-2.el8                                             @appstream                    72 k
 jasper-libs                                 x86_64                   2.0.14-5.el8                                           @appstream                   363 k
 java-17-openjdk-headless                    x86_64                   1:17.0.1.0.12-2.el8_5                                  @appstream                   189 M
 javapackages-filesystem                     noarch                   5.3.0-1.module_el8.0.0+11+5b8c10bd                     @appstream                   1.9 k
 jbigkit-libs                                x86_64                   2.1-14.el8                                             @appstream                   107 k
 json-glib                                   x86_64                   1.4.4-1.el8                                            @baseos                      518 k
 lcms2                                       x86_64                   2.9-2.el8                                              @appstream                   390 k
 libX11                                      x86_64                   1.6.8-5.el8                                            @appstream                   1.3 M
 libX11-common                               noarch                   1.6.8-5.el8                                            @appstream                   1.3 M
 libXau                                      x86_64                   1.0.9-3.el8                                            @appstream                    60 k
 libXcomposite                               x86_64                   0.4.4-14.el8                                           @appstream                    35 k
 libXcursor                                  x86_64                   1.1.15-3.el8                                           @appstream                    48 k
 libXdamage                                  x86_64                   1.1.4-14.el8                                           @appstream                    30 k
 libXext                                     x86_64                   1.3.4-1.el8                                            @appstream                    90 k
 libXfixes                                   x86_64                   5.0.3-7.el8                                            @appstream                    29 k
 libXft                                      x86_64                   2.3.3-1.el8                                            @appstream                   129 k
 libXi                                       x86_64                   1.7.10-1.el8                                           @appstream                    73 k
 libXinerama                                 x86_64                   1.1.4-1.el8                                            @appstream                    15 k
 libXrandr                                   x86_64                   1.5.2-1.el8                                            @appstream                    48 k
 libXrender                                  x86_64                   0.9.10-7.el8                                           @appstream                    51 k
 libXtst                                     x86_64                   1.2.3-7.el8                                            @appstream                    34 k
 libdatrie                                   x86_64                   0.2.9-7.el8                                            @appstream                    61 k
 libepoxy                                    x86_64                   1.5.8-1.el8                                            @appstream                   1.2 M
 libfontenc                                  x86_64                   1.1.3-8.el8                                            @appstream                    56 k
 libgusb                                     x86_64                   0.3.0-1.el8                                            @baseos                      115 k
 libjpeg-turbo                               x86_64                   1.5.3-12.el8                                           @appstream                   513 k
 libmodman                                   x86_64                   2.0.1-17.el8                                           @baseos                       68 k
 libpkgconf                                  x86_64                   1.4.2-1.el8                                            @baseos                       66 k
 libpng                                      x86_64                   2:1.6.34-5.el8                                         @baseos                      230 k
 libproxy                                    x86_64                   0.4.15-5.2.el8                                         @baseos                      197 k
 libsoup                                     x86_64                   2.62.3-2.el8                                           @baseos                      1.5 M
 libthai                                     x86_64                   0.1.27-2.el8                                           @appstream                   757 k
 libtiff                                     x86_64                   4.0.9-20.el8                                           @appstream                   506 k
 libwayland-client                           x86_64                   1.19.0-1.el8                                           @appstream                    67 k
 libwayland-cursor                           x86_64                   1.19.0-1.el8                                           @appstream                    34 k
 libwayland-egl                              x86_64                   1.19.0-1.el8                                           @appstream                   8.7 k
 libxcb                                      x86_64                   1.13.1-1.el8                                           @appstream                   1.0 M
 lksctp-tools                                x86_64                   1.0.18-3.el8                                           @baseos                      252 k
 lua                                         x86_64                   5.3.4-12.el8                                           @appstream                   553 k
 nspr                                        x86_64                   4.32.0-1.el8_4                                         @appstream                   310 k
 nss                                         x86_64                   3.67.0-7.el8_5                                         @appstream                   2.0 M
 nss-softokn                                 x86_64                   3.67.0-7.el8_5                                         @appstream                   1.9 M
 nss-softokn-freebl                          x86_64                   3.67.0-7.el8_5                                         @appstream                   792 k
 nss-sysinit                                 x86_64                   3.67.0-7.el8_5                                         @appstream                    14 k
 nss-util                                    x86_64                   3.67.0-7.el8_5                                         @appstream                   220 k
 pango                                       x86_64                   1.42.4-8.el8                                           @appstream                   771 k
 pixman                                      x86_64                   0.38.4-1.el8                                           @appstream                   677 k
 pkgconf                                     x86_64                   1.4.2-1.el8                                            @baseos                       62 k
 pkgconf-m4                                  noarch                   1.4.2-1.el8                                            @baseos                       14 k
 pkgconf-pkg-config                          x86_64                   1.4.2-1.el8                                            @baseos                      3.0 k
 rest                                        x86_64                   0.8.1-2.el8                                            @appstream                   190 k
 ttmkfdir                                    x86_64                   3.0.9-54.el8                                           @appstream                   140 k
 tzdata-java                                 noarch                   2021e-1.el8                                            @appstream                   362 k
 xorg-x11-font-utils                         x86_64                   1:7.5-41.el8                                           @appstream                   362 k
 xorg-x11-fonts-Type1                        noarch                   7.5-19.el8                                             @appstream                   863 k

Transaction Summary
================================================================================================================================================================
Remove  85 Packages

Freed space: 271 M
Is this ok [y/N]: y
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                                                                                                        1/1
  Erasing          : java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                                                                          1/85
  Running scriptlet: java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                                                                          1/85
  Erasing          : gtk3-3.22.30-8.el8.x86_64                                                                                                             2/85
  Erasing          : xorg-x11-fonts-Type1-7.5-19.el8.noarch                                                                                                3/85
  Running scriptlet: xorg-x11-fonts-Type1-7.5-19.el8.noarch                                                                                                3/85
  Erasing          : java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                                                                                 4/85
  Running scriptlet: java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                                                                                 4/85
  Erasing          : nss-3.67.0-7.el8_5.x86_64                                                                                                             5/85
  Erasing          : pango-1.42.4-8.el8.x86_64                                                                                                             6/85
  Running scriptlet: pango-1.42.4-8.el8.x86_64                                                                                                             6/85
  Erasing          : nss-softokn-3.67.0-7.el8_5.x86_64                                                                                                     7/85
  Erasing          : cairo-gobject-1.15.12-3.el8.x86_64                                                                                                    8/85
  Erasing          : cairo-1.15.12-3.el8.x86_64                                                                                                            9/85
  Erasing          : gdk-pixbuf2-modules-2.36.12-5.el8.x86_64                                                                                             10/85
  Erasing          : nss-sysinit-3.67.0-7.el8_5.x86_64                                                                                                    11/85
  Erasing          : libXft-2.3.3-1.el8.x86_64                                                                                                            12/85
  Erasing          : fontconfig-2.13.1-4.el8.x86_64                                                                                                       13/85
  Erasing          : libXcursor-1.1.15-3.el8.x86_64                                                                                                       14/85
  Erasing          : libXrandr-1.5.2-1.el8.x86_64                                                                                                         15/85
  Erasing          : at-spi2-atk-2.26.2-1.el8.x86_64                                                                                                      16/85
  Running scriptlet: at-spi2-atk-2.26.2-1.el8.x86_64                                                                                                      16/85
  Erasing          : colord-libs-1.4.2-1.el8.x86_64                                                                                                       17/85
  Erasing          : libtiff-4.0.9-20.el8.x86_64                                                                                                          18/85
  Erasing          : xorg-x11-font-utils-1:7.5-41.el8.x86_64                                                                                              19/85
  Erasing          : libXinerama-1.1.4-1.el8.x86_64                                                                                                       20/85
  Erasing          : pkgconf-pkg-config-1.4.2-1.el8.x86_64                                                                                                21/85
  Erasing          : pkgconf-1.4.2-1.el8.x86_64                                                                                                           22/85
  Erasing          : at-spi2-core-2.28.0-1.el8.x86_64                                                                                                     23/85
  Running scriptlet: at-spi2-core-2.28.0-1.el8.x86_64                                                                                                     23/85
  Erasing          : libXtst-1.2.3-7.el8.x86_64                                                                                                           24/85
  Erasing          : libXi-1.7.10-1.el8.x86_64                                                                                                            25/85
  Erasing          : libXext-1.3.4-1.el8.x86_64                                                                                                           26/85
  Erasing          : libXrender-0.9.10-7.el8.x86_64                                                                                                       27/85
  Erasing          : jasper-libs-2.0.14-5.el8.x86_64                                                                                                      28/85
  Erasing          : nss-softokn-freebl-3.67.0-7.el8_5.x86_64                                                                                             29/85
  Erasing          : nss-util-3.67.0-7.el8_5.x86_64                                                                                                       30/85
  Erasing          : harfbuzz-1.7.5-3.el8.x86_64                                                                                                          31/85
  Running scriptlet: harfbuzz-1.7.5-3.el8.x86_64                                                                                                          31/85
  Erasing          : libthai-0.1.27-2.el8.x86_64                                                                                                          32/85
  Running scriptlet: libthai-0.1.27-2.el8.x86_64                                                                                                          32/85
  Erasing          : cups-libs-1:2.2.6-40.el8.x86_64                                                                                                      33/85
  Erasing          : libXdamage-1.1.4-14.el8.x86_64                                                                                                       34/85
  Erasing          : libXfixes-5.0.3-7.el8.x86_64                                                                                                         35/85
  Erasing          : rest-0.8.1-2.el8.x86_64                                                                                                              36/85
  Running scriptlet: rest-0.8.1-2.el8.x86_64                                                                                                              36/85
  Erasing          : copy-jdk-configs-4.0-2.el8.noarch                                                                                                    37/85
  Erasing          : adwaita-icon-theme-3.28.0-2.el8.noarch                                                                                               38/85
  Erasing          : libsoup-2.62.3-2.el8.x86_64                                                                                                          39/85
  Erasing          : glib-networking-2.56.1-1.1.el8.x86_64                                                                                                40/85
  Erasing          : gsettings-desktop-schemas-3.32.0-6.el8.x86_64                                                                                        41/85
  Erasing          : abattis-cantarell-fonts-0.0.25-6.el8.noarch                                                                                          42/85
  Erasing          : dejavu-sans-mono-fonts-2.35-7.el8.noarch                                                                                             43/85
  Erasing          : dejavu-fonts-common-2.35-7.el8.noarch                                                                                                44/85
  Erasing          : libproxy-0.4.15-5.2.el8.x86_64                                                                                                       45/85
  Running scriptlet: libproxy-0.4.15-5.2.el8.x86_64                                                                                                       45/85
  Erasing          : ttmkfdir-3.0.9-54.el8.x86_64                                                                                                         46/85
  Erasing          : freetype-2.9.1-4.el8_3.1.x86_64                                                                                                      47/85
  Erasing          : gtk-update-icon-cache-3.22.30-8.el8.x86_64                                                                                           48/85
  Erasing          : gdk-pixbuf2-2.36.12-5.el8.x86_64                                                                                                     49/85
  Running scriptlet: gdk-pixbuf2-2.36.12-5.el8.x86_64                                                                                                     49/85
  Erasing          : libXcomposite-0.4.4-14.el8.x86_64                                                                                                    50/85
  Erasing          : libX11-1.6.8-5.el8.x86_64                                                                                                            51/85
  Erasing          : libxcb-1.13.1-1.el8.x86_64                                                                                                           52/85
  Erasing          : libwayland-cursor-1.19.0-1.el8.x86_64                                                                                                53/85
  Erasing          : libX11-common-1.6.8-5.el8.noarch                                                                                                     54/85
  Erasing          : fontpackages-filesystem-1.44-22.el8.noarch                                                                                           55/85
  Erasing          : adwaita-cursor-theme-3.28.0-2.el8.noarch                                                                                             56/85
  Erasing          : pkgconf-m4-1.4.2-1.el8.noarch                                                                                                        57/85
  Erasing          : javapackages-filesystem-5.3.0-1.module_el8.0.0+11+5b8c10bd.noarch                                                                    58/85
  Erasing          : tzdata-java-2021e-1.el8.noarch                                                                                                       59/85
  Erasing          : hicolor-icon-theme-0.17-2.el8.noarch                                                                                                 60/85
  Erasing          : libwayland-client-1.19.0-1.el8.x86_64                                                                                                61/85
  Erasing          : libXau-1.0.9-3.el8.x86_64                                                                                                            62/85
  Erasing          : libpng-2:1.6.34-5.el8.x86_64                                                                                                         63/85
  Erasing          : libmodman-2.0.1-17.el8.x86_64                                                                                                        64/85
  Running scriptlet: libmodman-2.0.1-17.el8.x86_64                                                                                                        64/85
  Erasing          : lua-5.3.4-12.el8.x86_64                                                                                                              65/85
  Erasing          : avahi-libs-0.7-20.el8.x86_64                                                                                                         66/85
  Erasing          : libdatrie-0.2.9-7.el8.x86_64                                                                                                         67/85
  Running scriptlet: libdatrie-0.2.9-7.el8.x86_64                                                                                                         67/85
  Erasing          : graphite2-1.3.10-10.el8.x86_64                                                                                                       68/85
  Erasing          : nspr-4.32.0-1.el8_4.x86_64                                                                                                           69/85
  Running scriptlet: nspr-4.32.0-1.el8_4.x86_64                                                                                                           69/85
  Erasing          : libjpeg-turbo-1.5.3-12.el8.x86_64                                                                                                    70/85
  Erasing          : libpkgconf-1.4.2-1.el8.x86_64                                                                                                        71/85
  Erasing          : libfontenc-1.1.3-8.el8.x86_64                                                                                                        72/85
  Erasing          : jbigkit-libs-2.1-14.el8.x86_64                                                                                                       73/85
  Running scriptlet: jbigkit-libs-2.1-14.el8.x86_64                                                                                                       73/85
  Erasing          : libgusb-0.3.0-1.el8.x86_64                                                                                                           74/85
  Erasing          : lcms2-2.9-2.el8.x86_64                                                                                                               75/85
  Running scriptlet: lcms2-2.9-2.el8.x86_64                                                                                                               75/85
  Erasing          : atk-2.28.1-1.el8.x86_64                                                                                                              76/85
  Erasing          : pixman-0.38.4-1.el8.x86_64                                                                                                           77/85
  Erasing          : fribidi-1.0.4-8.el8.x86_64                                                                                                           78/85
  Erasing          : alsa-lib-1.2.5-4.el8.x86_64                                                                                                          79/85
  Running scriptlet: alsa-lib-1.2.5-4.el8.x86_64                                                                                                          79/85
  Erasing          : lksctp-tools-1.0.18-3.el8.x86_64                                                                                                     80/85
  Running scriptlet: lksctp-tools-1.0.18-3.el8.x86_64                                                                                                     80/85
  Erasing          : libepoxy-1.5.8-1.el8.x86_64                                                                                                          81/85
  Erasing          : json-glib-1.4.4-1.el8.x86_64                                                                                                         82/85
  Erasing          : libwayland-egl-1.19.0-1.el8.x86_64                                                                                                   83/85
  Erasing          : dconf-0.28.0-4.el8.x86_64                                                                                                            84/85
  Erasing          : giflib-5.1.4-3.el8.x86_64                                                                                                            85/85
  Running scriptlet: giflib-5.1.4-3.el8.x86_64                                                                                                            85/85
  Verifying        : abattis-cantarell-fonts-0.0.25-6.el8.noarch                                                                                           1/85
  Verifying        : adwaita-cursor-theme-3.28.0-2.el8.noarch                                                                                              2/85
  Verifying        : adwaita-icon-theme-3.28.0-2.el8.noarch                                                                                                3/85
  Verifying        : alsa-lib-1.2.5-4.el8.x86_64                                                                                                           4/85
  Verifying        : at-spi2-atk-2.26.2-1.el8.x86_64                                                                                                       5/85
  Verifying        : at-spi2-core-2.28.0-1.el8.x86_64                                                                                                      6/85
  Verifying        : atk-2.28.1-1.el8.x86_64                                                                                                               7/85
  Verifying        : avahi-libs-0.7-20.el8.x86_64                                                                                                          8/85
  Verifying        : cairo-1.15.12-3.el8.x86_64                                                                                                            9/85
  Verifying        : cairo-gobject-1.15.12-3.el8.x86_64                                                                                                   10/85
  Verifying        : colord-libs-1.4.2-1.el8.x86_64                                                                                                       11/85
  Verifying        : copy-jdk-configs-4.0-2.el8.noarch                                                                                                    12/85
  Verifying        : cups-libs-1:2.2.6-40.el8.x86_64                                                                                                      13/85
  Verifying        : dconf-0.28.0-4.el8.x86_64                                                                                                            14/85
  Verifying        : dejavu-fonts-common-2.35-7.el8.noarch                                                                                                15/85
  Verifying        : dejavu-sans-mono-fonts-2.35-7.el8.noarch                                                                                             16/85
  Verifying        : fontconfig-2.13.1-4.el8.x86_64                                                                                                       17/85
  Verifying        : fontpackages-filesystem-1.44-22.el8.noarch                                                                                           18/85
  Verifying        : freetype-2.9.1-4.el8_3.1.x86_64                                                                                                      19/85
  Verifying        : fribidi-1.0.4-8.el8.x86_64                                                                                                           20/85
  Verifying        : gdk-pixbuf2-2.36.12-5.el8.x86_64                                                                                                     21/85
  Verifying        : gdk-pixbuf2-modules-2.36.12-5.el8.x86_64                                                                                             22/85
  Verifying        : giflib-5.1.4-3.el8.x86_64                                                                                                            23/85
  Verifying        : glib-networking-2.56.1-1.1.el8.x86_64                                                                                                24/85
  Verifying        : graphite2-1.3.10-10.el8.x86_64                                                                                                       25/85
  Verifying        : gsettings-desktop-schemas-3.32.0-6.el8.x86_64                                                                                        26/85
  Verifying        : gtk-update-icon-cache-3.22.30-8.el8.x86_64                                                                                           27/85
  Verifying        : gtk3-3.22.30-8.el8.x86_64                                                                                                            28/85
  Verifying        : harfbuzz-1.7.5-3.el8.x86_64                                                                                                          29/85
  Verifying        : hicolor-icon-theme-0.17-2.el8.noarch                                                                                                 30/85
  Verifying        : jasper-libs-2.0.14-5.el8.x86_64                                                                                                      31/85
  Verifying        : java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64                                                                                         32/85
  Verifying        : java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                                                                                33/85
  Verifying        : javapackages-filesystem-5.3.0-1.module_el8.0.0+11+5b8c10bd.noarch                                                                    34/85
  Verifying        : jbigkit-libs-2.1-14.el8.x86_64                                                                                                       35/85
  Verifying        : json-glib-1.4.4-1.el8.x86_64                                                                                                         36/85
  Verifying        : lcms2-2.9-2.el8.x86_64                                                                                                               37/85
  Verifying        : libX11-1.6.8-5.el8.x86_64                                                                                                            38/85
  Verifying        : libX11-common-1.6.8-5.el8.noarch                                                                                                     39/85
  Verifying        : libXau-1.0.9-3.el8.x86_64                                                                                                            40/85
  Verifying        : libXcomposite-0.4.4-14.el8.x86_64                                                                                                    41/85
  Verifying        : libXcursor-1.1.15-3.el8.x86_64                                                                                                       42/85
  Verifying        : libXdamage-1.1.4-14.el8.x86_64                                                                                                       43/85
  Verifying        : libXext-1.3.4-1.el8.x86_64                                                                                                           44/85
  Verifying        : libXfixes-5.0.3-7.el8.x86_64                                                                                                         45/85
  Verifying        : libXft-2.3.3-1.el8.x86_64                                                                                                            46/85
  Verifying        : libXi-1.7.10-1.el8.x86_64                                                                                                            47/85
  Verifying        : libXinerama-1.1.4-1.el8.x86_64                                                                                                       48/85
  Verifying        : libXrandr-1.5.2-1.el8.x86_64                                                                                                         49/85
  Verifying        : libXrender-0.9.10-7.el8.x86_64                                                                                                       50/85
  Verifying        : libXtst-1.2.3-7.el8.x86_64                                                                                                           51/85
  Verifying        : libdatrie-0.2.9-7.el8.x86_64                                                                                                         52/85
  Verifying        : libepoxy-1.5.8-1.el8.x86_64                                                                                                          53/85
  Verifying        : libfontenc-1.1.3-8.el8.x86_64                                                                                                        54/85
  Verifying        : libgusb-0.3.0-1.el8.x86_64                                                                                                           55/85
  Verifying        : libjpeg-turbo-1.5.3-12.el8.x86_64                                                                                                    56/85
  Verifying        : libmodman-2.0.1-17.el8.x86_64                                                                                                        57/85
  Verifying        : libpkgconf-1.4.2-1.el8.x86_64                                                                                                        58/85
  Verifying        : libpng-2:1.6.34-5.el8.x86_64                                                                                                         59/85
  Verifying        : libproxy-0.4.15-5.2.el8.x86_64                                                                                                       60/85
  Verifying        : libsoup-2.62.3-2.el8.x86_64                                                                                                          61/85
  Verifying        : libthai-0.1.27-2.el8.x86_64                                                                                                          62/85
  Verifying        : libtiff-4.0.9-20.el8.x86_64                                                                                                          63/85
  Verifying        : libwayland-client-1.19.0-1.el8.x86_64                                                                                                64/85
  Verifying        : libwayland-cursor-1.19.0-1.el8.x86_64                                                                                                65/85
  Verifying        : libwayland-egl-1.19.0-1.el8.x86_64                                                                                                   66/85
  Verifying        : libxcb-1.13.1-1.el8.x86_64                                                                                                           67/85
  Verifying        : lksctp-tools-1.0.18-3.el8.x86_64                                                                                                     68/85
  Verifying        : lua-5.3.4-12.el8.x86_64                                                                                                              69/85
  Verifying        : nspr-4.32.0-1.el8_4.x86_64                                                                                                           70/85
  Verifying        : nss-3.67.0-7.el8_5.x86_64                                                                                                            71/85
  Verifying        : nss-softokn-3.67.0-7.el8_5.x86_64                                                                                                    72/85
  Verifying        : nss-softokn-freebl-3.67.0-7.el8_5.x86_64                                                                                             73/85
  Verifying        : nss-sysinit-3.67.0-7.el8_5.x86_64                                                                                                    74/85
  Verifying        : nss-util-3.67.0-7.el8_5.x86_64                                                                                                       75/85
  Verifying        : pango-1.42.4-8.el8.x86_64                                                                                                            76/85
  Verifying        : pixman-0.38.4-1.el8.x86_64                                                                                                           77/85
  Verifying        : pkgconf-1.4.2-1.el8.x86_64                                                                                                           78/85
  Verifying        : pkgconf-m4-1.4.2-1.el8.noarch                                                                                                        79/85
  Verifying        : pkgconf-pkg-config-1.4.2-1.el8.x86_64                                                                                                80/85
  Verifying        : rest-0.8.1-2.el8.x86_64                                                                                                              81/85
  Verifying        : ttmkfdir-3.0.9-54.el8.x86_64                                                                                                         82/85
  Verifying        : tzdata-java-2021e-1.el8.noarch                                                                                                       83/85
  Verifying        : xorg-x11-font-utils-1:7.5-41.el8.x86_64                                                                                              84/85
  Verifying        : xorg-x11-fonts-Type1-7.5-19.el8.noarch                                                                                               85/85

Removed:
  abattis-cantarell-fonts-0.0.25-6.el8.noarch                              adwaita-cursor-theme-3.28.0-2.el8.noarch
  adwaita-icon-theme-3.28.0-2.el8.noarch                                   alsa-lib-1.2.5-4.el8.x86_64
  at-spi2-atk-2.26.2-1.el8.x86_64                                          at-spi2-core-2.28.0-1.el8.x86_64
  atk-2.28.1-1.el8.x86_64                                                  avahi-libs-0.7-20.el8.x86_64
  cairo-1.15.12-3.el8.x86_64                                               cairo-gobject-1.15.12-3.el8.x86_64
  colord-libs-1.4.2-1.el8.x86_64                                           copy-jdk-configs-4.0-2.el8.noarch
  cups-libs-1:2.2.6-40.el8.x86_64                                          dconf-0.28.0-4.el8.x86_64
  dejavu-fonts-common-2.35-7.el8.noarch                                    dejavu-sans-mono-fonts-2.35-7.el8.noarch
  fontconfig-2.13.1-4.el8.x86_64                                           fontpackages-filesystem-1.44-22.el8.noarch
  freetype-2.9.1-4.el8_3.1.x86_64                                          fribidi-1.0.4-8.el8.x86_64
  gdk-pixbuf2-2.36.12-5.el8.x86_64                                         gdk-pixbuf2-modules-2.36.12-5.el8.x86_64
  giflib-5.1.4-3.el8.x86_64                                                glib-networking-2.56.1-1.1.el8.x86_64
  graphite2-1.3.10-10.el8.x86_64                                           gsettings-desktop-schemas-3.32.0-6.el8.x86_64
  gtk-update-icon-cache-3.22.30-8.el8.x86_64                               gtk3-3.22.30-8.el8.x86_64
  harfbuzz-1.7.5-3.el8.x86_64                                              hicolor-icon-theme-0.17-2.el8.noarch
  jasper-libs-2.0.14-5.el8.x86_64                                          java-17-openjdk-1:17.0.1.0.12-2.el8_5.x86_64
  java-17-openjdk-headless-1:17.0.1.0.12-2.el8_5.x86_64                    javapackages-filesystem-5.3.0-1.module_el8.0.0+11+5b8c10bd.noarch
  jbigkit-libs-2.1-14.el8.x86_64                                           json-glib-1.4.4-1.el8.x86_64
  lcms2-2.9-2.el8.x86_64                                                   libX11-1.6.8-5.el8.x86_64
  libX11-common-1.6.8-5.el8.noarch                                         libXau-1.0.9-3.el8.x86_64
  libXcomposite-0.4.4-14.el8.x86_64                                        libXcursor-1.1.15-3.el8.x86_64
  libXdamage-1.1.4-14.el8.x86_64                                           libXext-1.3.4-1.el8.x86_64
  libXfixes-5.0.3-7.el8.x86_64                                             libXft-2.3.3-1.el8.x86_64
  libXi-1.7.10-1.el8.x86_64                                                libXinerama-1.1.4-1.el8.x86_64
  libXrandr-1.5.2-1.el8.x86_64                                             libXrender-0.9.10-7.el8.x86_64
  libXtst-1.2.3-7.el8.x86_64                                               libdatrie-0.2.9-7.el8.x86_64
  libepoxy-1.5.8-1.el8.x86_64                                              libfontenc-1.1.3-8.el8.x86_64
  libgusb-0.3.0-1.el8.x86_64                                               libjpeg-turbo-1.5.3-12.el8.x86_64
  libmodman-2.0.1-17.el8.x86_64                                            libpkgconf-1.4.2-1.el8.x86_64
  libpng-2:1.6.34-5.el8.x86_64                                             libproxy-0.4.15-5.2.el8.x86_64
  libsoup-2.62.3-2.el8.x86_64                                              libthai-0.1.27-2.el8.x86_64
  libtiff-4.0.9-20.el8.x86_64                                              libwayland-client-1.19.0-1.el8.x86_64
  libwayland-cursor-1.19.0-1.el8.x86_64                                    libwayland-egl-1.19.0-1.el8.x86_64
  libxcb-1.13.1-1.el8.x86_64                                               lksctp-tools-1.0.18-3.el8.x86_64
  lua-5.3.4-12.el8.x86_64                                                  nspr-4.32.0-1.el8_4.x86_64
  nss-3.67.0-7.el8_5.x86_64                                                nss-softokn-3.67.0-7.el8_5.x86_64
  nss-softokn-freebl-3.67.0-7.el8_5.x86_64                                 nss-sysinit-3.67.0-7.el8_5.x86_64
  nss-util-3.67.0-7.el8_5.x86_64                                           pango-1.42.4-8.el8.x86_64
  pixman-0.38.4-1.el8.x86_64                                               pkgconf-1.4.2-1.el8.x86_64
  pkgconf-m4-1.4.2-1.el8.noarch                                            pkgconf-pkg-config-1.4.2-1.el8.x86_64
  rest-0.8.1-2.el8.x86_64                                                  ttmkfdir-3.0.9-54.el8.x86_64
  tzdata-java-2021e-1.el8.noarch                                           xorg-x11-font-utils-1:7.5-41.el8.x86_64
  xorg-x11-fonts-Type1-7.5-19.el8.noarch

Complete!
[root@889e0484bdd2 /]#
```



验证：

```sh
[root@889e0484bdd2 /]# java -version
bash: /usr/bin/java: No such file or directory
[root@889e0484bdd2 /]#
```







## yum管理软件组

yum 命令除了可以对软件包进行查询、安装、升级和卸载外，还可完成对软件包组的查询、安装和卸载操作。



### 查询软件组包含的软件

既然是软件包组，说明包含不只一个软件包，通过 yum 命令可以查询某软件包组中具体包含的软件包



命令：

```sh
yum groupinfo 软件组名
```



### 安装软件组



命令：

```sh
yum groupinstall 软件组名
```





### 卸载软件组



命令：

```sh
yum groupremove 软件组名
```







## 函数库的安装

函数库就是一些函数的集合，每个函数都具有独立的功能且能被外界调用



CentOS 中，安装函数库可直接使用 yum 命令

安装命令：

```sh
yum install 函数库名
```



查看可执行程序调用了哪些函数库：

```sh
ldd -v 可执行文件名
```









## Ubuntu系统apt命令

此命令类似于centOS的yum命令



```sh
mao@ubuntu:~/桌面$ apt
apt 2.0.6 (amd64)
用法： apt [选项] 命令

命令行软件包管理器 apt 提供软件包搜索，管理和信息查询等功能。
它提供的功能与其他 APT 工具相同（像 apt-get 和 apt-cache），
但是默认情况下被设置得更适合交互。

常用命令：
  list - 根据名称列出软件包
  search - 搜索软件包描述
  show - 显示软件包细节
  install - 安装软件包
  reinstall - 重新安装软件包
  remove - 移除软件包
  autoremove - 卸载所有自动安装且不再使用的软件包
  update - 更新可用软件包列表
  upgrade - 通过 安装/升级 软件来更新系统
  full-upgrade - 通过 卸载/安装/升级 来更新系统
  edit-sources - 编辑软件源信息文件
  satisfy - 使系统满足依赖关系字符串

参见 apt(8) 以获取更多关于可用命令的信息。
程序配置选项及语法都已经在 apt.conf(5) 中阐明。
欲知如何配置软件源，请参阅 sources.list(5)。
软件包及其版本偏好可以通过 apt_preferences(5) 来设置。
关于安全方面的细节可以参考 apt-secure(8).
                                         本 APT 具有超级牛力。
mao@ubuntu:~/桌面$ 
```



最常用的 Linux 包管理命令都被分散在了 apt-get、apt-cache 和 apt-config 这三条命令当中。

apt 命令的引入就是为了解决命令过于分散的问题，它包括了 apt-get 命令出现以来使用最广泛的功能选项，以及 apt-cache 和 apt-config 命令中很少用到的功能。

在使用 apt 命令时，用户不必再由 apt-get 转到 apt-cache 或 apt-config，而且 apt 更加结构化，并为用户提供了管理软件包所需的必要选项。





### 参数



| 参数 | 说明 |
| :--: | :--: |
|-h 	|	帮助文件。 |
|-q 	|	输出到日志 - 无进展指示 |
|-qq 	|	不输出信息，错误除外 |
|-d 	|	仅下载 - 不安装或解压归档文件 |
| -s 	|	不实际安装。模拟执行命令 |
| -y 	|	在需要确认的场景中回应 yes|
| -f    |尝试修正系统依赖损坏处|
| -m 	|	如果归档无法定位，尝试继续 |
| -u 	|	同时显示更新软件包的列表 |
| -b 	|	获取源码包后编译 |
| -V 	|	显示详细的版本号 |
| -c=? 	|	阅读此配置文件 |
| -o=? 		|设置自定的配置选项，如 -o dir::cache=/tmp |





### 升级和安装



| 命令 | 说明 |
| :--: | :--: |
|apt-get update			|			 更新源文件，并不会做任何安装升级操作|
|apt-get upgrade				|		 升级所有已安装的包|
|apt-get install packagename			|	 安装指定的包|
|apt-get install packagename --only-upgrade	|	仅升级指定的包|
|apt-get install packagename --reinstall  | 		 重新安装包|
|apt-get -f install   				|	 修复安装|
|apt-get build-dep packagename		|		安装相关的编译环境|
|apt-get source packagename  		|		下载该包的源代码|
|apt-get dist-upgrade 			|		 升级系统|







### 查询和显示



| 命令 | 说明 |
| :--: | :--: |
|apt-cache search packagename 		|		查询指定的包  　　|
|apt-cache show packagename 		|		显示包的相关信息，如说明、大小、版本等 |
|apt-cache depends packagename 		|		了解使用该包依赖哪些包|
|apt-cache rdepends packagename 	|			 查看该包被哪些包依赖|







### 删除和清理



| 命令 | 说明 |
| :--: | :--: |
|apt-get remove packagename		|		删除包  　　|
|apt-get remove packagename -- purge 		|	删除包，包括删除配置文件等 |
|apt-get autoremove packagename --purge |			删除包及其依赖的软件+配置文件等（只对6.10有效，推荐使用）|
|apt-get clean 					|	 清理无用的包 |
|apt-get autoclean 			|		 清理无用的包 |
|apt-get check 				|		 检查是否有损坏的依赖|











# 用户和用户组管理

## 关系

Linux 是多用户多任务操作系统，换句话说，Linux 系统支持多个用户在同一时间内登陆，不同用户可以执行不同的任务，并且互不影响。



用户和用户组的对应关系有以下 4 种：

1. 一对一：一个用户可以存在一个组中，是组中的唯一成员；
2. 一对多：一个用户可以存在多个用户组中，此用户具有这多个组的共同权限；
3. 多对一：多个用户可以存在一个组中，这些用户具有和组相同的权限；
4. 多对多：多个用户可以存在多个组中，也就是以上 3 种关系的扩展。







## UID和GID

UID和GID，即用户ID和组ID，User ID，简称 UID，Group ID，简称 GID



登陆 Linux 系统时，虽然输入的是自己的用户名和密码，但其实 Linux 并不认识你的用户名称，它只认识用户名对应的 ID 号（也就是一串数字）。Linux 系统将所有用户的名称与 ID 的对应关系都存储在 /etc/passwd 文件中。





## /etc/passwd

Linux 系统中的 /etc/passwd 文件，是系统用户配置文件，存储了系统中所有用户的基本信息，并且所有用户都可以对此文件执行读操作。





```sh
mao@ubuntu:~/桌面$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
systemd-timesync:x:102:104:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:103:106::/nonexistent:/usr/sbin/nologin
syslog:x:104:110::/home/syslog:/usr/sbin/nologin
_apt:x:105:65534::/nonexistent:/usr/sbin/nologin
tss:x:106:111:TPM software stack,,,:/var/lib/tpm:/bin/false
uuidd:x:107:114::/run/uuidd:/usr/sbin/nologin
tcpdump:x:108:115::/nonexistent:/usr/sbin/nologin
avahi-autoipd:x:109:116:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
usbmux:x:110:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
rtkit:x:111:117:RealtimeKit,,,:/proc:/usr/sbin/nologin
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
cups-pk-helper:x:113:120:user for cups-pk-helper service,,,:/home/cups-pk-helper:/usr/sbin/nologin
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/run/speech-dispatcher:/bin/false
avahi:x:115:121:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
saned:x:117:123::/var/lib/saned:/usr/sbin/nologin
nm-openvpn:x:118:124:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
hplip:x:119:7:HPLIP system user,,,:/run/hplip:/bin/false
whoopsie:x:120:125::/nonexistent:/bin/false
colord:x:121:126:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:122:127::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:123:128:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:124:65534::/run/gnome-initial-setup/:/bin/false
gdm:x:125:130:Gnome Display Manager:/var/lib/gdm3:/bin/false
sssd:x:126:131:SSSD system user,,,:/var/lib/sss:/usr/sbin/nologin
mao:x:1000:1000:linux,,,:/home/mao:/bin/bash
systemd-coredump:x:999:999:systemd Core Dumper:/:/usr/sbin/nologin
mao@ubuntu:~/桌面$ 
```



/etc/passwd 文件中的内容非常规律，每行记录对应一个用户。



这些用户中的绝大多数是系统或服务正常运行所必需的用户，这种用户通常称为系统用户或伪用户。系统用户无法用来登录系统，但也不能删除，因为一旦删除，依赖这些用户运行的服务或程序就不能正常执行，会导致系统问题。



每行用户信息都以 "：" 作为分隔符，划分为 7 个字段，每个字段所表示的含义如下：

```sh
用户名：密码：UID（用户ID）：GID（组ID）：描述性信息：主目录：默认Shell
```



### 用户名

用户名，就是一串代表用户身份的字符串。

Linux 系统是通过 UID 来识别用户身份，分配用户权限的。/etc/passwd 文件中就定义了用户名和 UID 之间的对应关系。



### 密码

"x" 表示此用户设有密码，但不是真正的密码，真正的密码保存在 /etc/shadow 文件中，此文件只有 root 用户可以浏览和操作



### UID

UID，也就是用户 ID。每个用户都有唯一的一个 UID，Linux 系统通过 UID 来识别不同的用户。

UID 就是一个 0~65535 之间的数，不同范围的数字表示不同的用户身份



| UID 范围  |                           用户身份                           |
| :-------: | :----------------------------------------------------------: |
|     0     | 超级用户。UID 为 0 就代表这个账号是管理员账号。在 Linux 中，如何把普通用户升级成管理员呢？只需把其他用户的 UID 修改为 0 就可以了，这一点和 Windows 是不同的。不过不建议建立多个管理员账号。 |
|   1~499   | 系统用户（伪用户）。也就是说，此范围的 UID 保留给系统使用。其中，1~99 用于系统自行创建的账号；100~499 分配给有系统账号需求的用户。  其实，除了 0 之外，其他的 UID 并无不同，这里只是默认 500 以下的数字给系统作为保留账户，只是一个公认的习惯而已。 |
| 500~65535 |                          普通用户。                          |





### GID

全称“Group ID”，简称“组ID”，表示用户初始组的组 ID 号。

初始组，指用户登陆时就拥有这个用户组的相关权限。每个用户的初始组只能有一个，通常就是将和此用户的用户名相同的组名作为该用户的初始组。比如说，我们手工添加用户 lamp，在建立用户 lamp 的同时，就会建立 lamp 组作为 lamp 用户的初始组。

附加组，指用户可以加入多个其他的用户组，并拥有这些组的权限。每个用户只能有一个初始组，除初始组外，用户再加入其他的用户组，这些用户组就是这个用户的附加组。附加组可以有多个，而且用户可以有这些附加组的权限。





### 描述性信息

用来解释这个用户的意义





### 主目录

用户登录后有操作权限的访问目录，通常称为用户的主目录

root 超级管理员账户的主目录为 /root，普通用户的主目录为 /home/yourIDname





### 默认Shell

Shell 就是 Linux 的命令解释器，是用户和 Linux 内核之间沟通的桥梁







## /etc/shadow

/etc/shadow 文件，用于存储 Linux 系统中用户的密码信息

由于该文件允许所有用户读取，易导致用户密码泄露，因此 Linux 系统将用户的密码信息从 /etc/passwd 文件中分离出来，并单独放到了此文件中

/etc/shadow 文件只有 root 用户拥有读权限，其他用户没有任何权限，这样就保证了用户密码的安全性



```sh
mao@ubuntu:~/桌面$ sudo cat /etc/shadow
[sudo] mao 的密码： 
root:!:18915:0:99999:7:::
daemon:*:18858:0:99999:7:::
bin:*:18858:0:99999:7:::
sys:*:18858:0:99999:7:::
sync:*:18858:0:99999:7:::
games:*:18858:0:99999:7:::
man:*:18858:0:99999:7:::
lp:*:18858:0:99999:7:::
mail:*:18858:0:99999:7:::
news:*:18858:0:99999:7:::
uucp:*:18858:0:99999:7:::
proxy:*:18858:0:99999:7:::
www-data:*:18858:0:99999:7:::
backup:*:18858:0:99999:7:::
list:*:18858:0:99999:7:::
irc:*:18858:0:99999:7:::
gnats:*:18858:0:99999:7:::
nobody:*:18858:0:99999:7:::
systemd-network:*:18858:0:99999:7:::
systemd-resolve:*:18858:0:99999:7:::
systemd-timesync:*:18858:0:99999:7:::
messagebus:*:18858:0:99999:7:::
syslog:*:18858:0:99999:7:::
_apt:*:18858:0:99999:7:::
tss:*:18858:0:99999:7:::
uuidd:*:18858:0:99999:7:::
tcpdump:*:18858:0:99999:7:::
avahi-autoipd:*:18858:0:99999:7:::
usbmux:*:18858:0:99999:7:::
rtkit:*:18858:0:99999:7:::
dnsmasq:*:18858:0:99999:7:::
cups-pk-helper:*:18858:0:99999:7:::
speech-dispatcher:!:18858:0:99999:7:::
avahi:*:18858:0:99999:7:::
kernoops:*:18858:0:99999:7:::
saned:*:18858:0:99999:7:::
nm-openvpn:*:18858:0:99999:7:::
hplip:*:18858:0:99999:7:::
whoopsie:*:18858:0:99999:7:::
colord:*:18858:0:99999:7:::
geoclue:*:18858:0:99999:7:::
pulse:*:18858:0:99999:7:::
gnome-initial-setup:*:18858:0:99999:7:::
gdm:*:18858:0:99999:7:::
sssd:*:18858:0:99999:7:::
mao:$1$dvdYmO70$JMt6qRizm5GFCwQh6dk5/1:18915:0:99999:7:::
systemd-coredump:!!:18915::::::
mao@ubuntu:~/桌面$ 
```



文件中每行代表一个用户，同样使用 ":" 作为分隔符，不同之处在于，每行用户信息被划分为 9 个字段。每个字段的含义如下：

```sh
用户名：加密密码：最后一次修改时间：最小修改时间间隔：密码有效期：密码需要变更前的警告天数：密码过期后的宽限时间：账号失效时间：保留字段
```



### 用户名

用户名，就是一串代表用户身份的字符串。

Linux 系统是通过 UID 来识别用户身份，分配用户权限的。/etc/passwd 文件中就定义了用户名和 UID 之间的对应关系。





### 加密密码

这里保存的是真正加密的密码。目前 Linux 的密码采用的是 SHA512 散列加密算法，原来采用的是 MD5 或 DES 加密算法。SHA512 散列加密算法的加密等级更高，也更加安全。

所有伪用户的密码都是 "!!" 或 "*"，代表没有密码是不能登录的。当然，新创建的用户如果不设定密码，那么它的密码项也是 "!!"，代表这个用户没有密码，不能登录。





### 最后一次修改时间

此字段表示最后一次修改密码的时间

Linux 计算日期的时间是以 1970 年 1 月 1 日作为 1 不断累加得到的时间，到 1971 年 1 月 1 日，则为 366 天，则为365





### 最小修改时间间隔

该字段规定了从第 3 字段（最后一次修改密码的日期）起，多长时间之内不能修改密码。如果是 0，则密码可以随时修改；如果是 10，则代表密码修改后 10 天之内不能再次修改密码。





### 密码有效期

经常变更密码是个好习惯，为了强制要求用户变更密码，这个字段可以指定距离第 3 字段（最后一次更改密码）多长时间内需要再次变更密码，否则该账户密码进行过期阶段。
该字段的默认值为 99999，也就是 273 年，可认为是永久生效。如果改为 90，则表示密码被修改 90 天之后必须再次修改，否则该用户即将过期。管理服务器时，通过这个字段强制用户定期修改密码。





### 密码需要变更前的警告天数

当账户密码有效期快到时，系统会发出警告信息给此账户，提醒用户 "再过 n 天你的密码就要过期了，请尽快重新设置你的密码！"。

该字段的默认值是 7，也就是说，距离密码有效期的第 7 天开始，每次登录系统都会向该账户发出 "修改密码" 的警告信息。





### 密码过期后的宽限天数

也称为“口令失效日”，简单理解就是，在密码过期后，用户如果还是没有修改密码，则在此字段规定的宽限天数内，用户还是可以登录系统的；如果过了宽限天数，系统将不再让此账户登陆，也不会提示账户过期，是完全禁用。

比如说，此字段规定的宽限天数是 10，则代表密码过期 10 天后失效；如果是 0，则代表密码过期后立即失效；如果是 -1，则代表密码永远不会失效。





### 账号失效时间

该字段表示，账号在此字段规定的时间之外，不论你的密码是否过期，都将无法使用

该字段通常被使用在具有收费服务的系统中。









## /etc/group

/etc/group 文件是用户组配置文件，即用户组的所有信息都存放在此文件中。

此文件是记录组 ID（GID）和组名相对应的文件



```sh
mao@ubuntu:~/桌面$ cat /etc/group
root:x:0:
daemon:x:1:
bin:x:2:
sys:x:3:
adm:x:4:syslog,mao
tty:x:5:syslog
disk:x:6:
lp:x:7:
mail:x:8:
news:x:9:
uucp:x:10:
man:x:12:
proxy:x:13:
kmem:x:15:
dialout:x:20:
fax:x:21:
voice:x:22:
cdrom:x:24:mao
floppy:x:25:
tape:x:26:
sudo:x:27:mao
audio:x:29:pulse
dip:x:30:mao
www-data:x:33:
backup:x:34:
operator:x:37:
list:x:38:
irc:x:39:
src:x:40:
gnats:x:41:
shadow:x:42:
utmp:x:43:
video:x:44:
sasl:x:45:
plugdev:x:46:mao
staff:x:50:
games:x:60:
users:x:100:
nogroup:x:65534:
systemd-journal:x:101:
systemd-network:x:102:
systemd-resolve:x:103:
systemd-timesync:x:104:
crontab:x:105:
messagebus:x:106:
input:x:107:
kvm:x:108:
render:x:109:
syslog:x:110:
tss:x:111:
bluetooth:x:112:
ssl-cert:x:113:
uuidd:x:114:
tcpdump:x:115:
avahi-autoipd:x:116:
rtkit:x:117:
ssh:x:118:
netdev:x:119:
lpadmin:x:120:mao
avahi:x:121:
scanner:x:122:saned
saned:x:123:
nm-openvpn:x:124:
whoopsie:x:125:
colord:x:126:
geoclue:x:127:
pulse:x:128:
pulse-access:x:129:
gdm:x:130:
sssd:x:131:
lxd:x:132:mao
mao:x:1000:
sambashare:x:133:mao
systemd-coredump:x:999:
mao@ubuntu:~/桌面$ 
```



每个字段对应的含义为：

```sh
组名：密码：GID：该用户组中的用户列表
```





### 组名

也就是是用户组的名称，有字母或数字构成



### 组密码

和 /etc/passwd 文件一样，这里的 "x" 仅仅是密码标识，真正加密后的组密码默认保存在 /etc/gshadow 文件中



### 组ID

就是群组的 ID 号，Linux 系统就是通过 GID 来区分用户组的



### 组中的用户

此字段列出每个群组包含的所有用户。需要注意的是，如果该用户组是这个用户的初始组，则该用户不会写入这个字段，可以这么理解，该字段显示的用户都是这个用户组的附加用户。

每个用户都可以加入多个附加组，但是只能属于一个初始组







## /etc/gshadow

组用户信息存储在 /etc/group 文件中，而将组用户的密码信息存储在 /etc/gshadow 文件中



```sh
mao@ubuntu:~/桌面$ sudo cat /etc/gshadow
[sudo] mao 的密码： 
root:*::
daemon:*::
bin:*::
sys:*::
adm:*::syslog,mao
tty:*::syslog
disk:*::
lp:*::
mail:*::
news:*::
uucp:*::
man:*::
proxy:*::
kmem:*::
dialout:*::
fax:*::
voice:*::
cdrom:*::mao
floppy:*::
tape:*::
sudo:*::mao
audio:*::pulse
dip:*::mao
www-data:*::
backup:*::
operator:*::
list:*::
irc:*::
src:*::
gnats:*::
shadow:*::
utmp:*::
video:*::
sasl:*::
plugdev:*::mao
staff:*::
games:*::
users:*::
nogroup:*::
systemd-journal:!::
systemd-network:!::
systemd-resolve:!::
systemd-timesync:!::
crontab:!::
messagebus:!::
input:!::
kvm:!::
render:!::
syslog:!::
tss:!::
bluetooth:!::
ssl-cert:!::
uuidd:!::
tcpdump:!::
avahi-autoipd:!::
rtkit:!::
ssh:!::
netdev:!::
lpadmin:!::mao
avahi:!::
scanner:!::saned
saned:!::
nm-openvpn:!::
whoopsie:!::
colord:!::
geoclue:!::
pulse:!::
pulse-access:!::
gdm:!::
sssd:!::
lxd:!::mao
mao:!::
sambashare:!::mao
systemd-coredump:!!::
mao@ubuntu:~/桌面$ 
```



每个字段的含义如下：

```sh
组名：加密密码：组管理员：组附加用户列表
```





### 组名

同 /etc/group 文件中的组名相对应。



### 组密码

对于大多数用户来说，通常不设置组密码，因此该字段常为空，但有时为 "!"，指的是该群组没有组密码，也不设有群组管理员



### 组管理员

考虑到 Linux 系统中账号太多，而超级管理员 root 可能比较忙碌，因此当有用户想要加入某群组时，root 或许不能及时作出回应。这种情况下，如果有群组管理员，那么他就能将用户加入自己管理的群组中，也就免去麻烦 root 了



### 组中的附加用户

该字段显示这个用户组中有哪些附加用户





## /etc/login.defs

/etc/login.defs 文件用于在创建用户时，**对用户的一些基本属性做默认设置**，例如指定用户 UID 和 GID 的范围，用户的过期时间，密码的最大长度，等等

该文件的用户默认配置对 root 用户无效

当此文件中的配置与 /etc/passwd 和 /etc/shadow 文件中的用户信息有冲突时，系统会以/etc/passwd 和 /etc/shadow 为准



|          设置项          |                             含义                             |
| :----------------------: | :----------------------------------------------------------: |
| MAIL_DIR /var/spool/mail | 创建用户时，系统会在目录 /var/spool/mail 中创建一个用户邮箱  |
|   PASS_MAX_DAYS 99999    | 密码有效期，99999 是自 1970 年 1 月 1 日起密码有效的天数，相当于 273 年，可理解为密码始终有效。 |
|     PASS_MIN_DAYS 0      | 表示自上次修改密码以来，最少隔多少天后用户才能再次修改密码，默认值是 0。 |
|      PASS_MIN_LEN 5      | 指定密码的最小长度，默认不小于 5 位，但是现在用户登录时验证已经被 PAM 模块取代，所以这个选项并不生效。 |
|     PASS_WARN_AGE 7      | 指定在密码到期前多少天，系统就开始通过用户密码即将到期，默认为 7 天。 |
|       UID_MIN 500        | 指定最小 UID 为 500，也就是说，添加用户时，默认 UID 从 500 开始。注意，如果手工指定了一个用户的 UID 是 550，那么下一个创建的用户的 UID 就会从 551 开始，哪怕 500~549 之间的 UID 没有使用。 |
|      UID_MAX 60000       |                指定用户最大的 UID 为 60000。                 |
|       GID_MIN 500        | 指定最小 GID 为 500，也就是在添加组时，组的 GID 从 500 开始。 |
|      GID_MAX 60000       |                   用户 GID 最大为 60000。                    |
|     CREATE_HOME yes      | 指定在创建用户时，是否同时创建用户主目录，yes 表示创建，no 则不创建，默认是 yes。 |
|        UMASK 077         |               用户主目录的权限默认设置为 077。               |
|   USERGROUPS_ENAB yes    | 指定删除用户的时候是否同时删除用户组，准备地说，这里指的是删除用户的初始组，此项的默认值为 yes。 |
|  ENCRYPT_METHOD SHA512   | 指定用户密码采用的加密规则，默认采用 SHA512，这是新的密码加密模式，原先的 Linux 只能用 DES 或 MD5 加密。 |



```sh
mao@ubuntu:~/桌面$ cat -n /etc/login.defs
     1	#
     2	# /etc/login.defs - Configuration control definitions for the login package.
     3	#
     4	# Three items must be defined:  MAIL_DIR, ENV_SUPATH, and ENV_PATH.
     5	# If unspecified, some arbitrary (and possibly incorrect) value will
     6	# be assumed.  All other items are optional - if not specified then
     7	# the described action or option will be inhibited.
     8	#
     9	# Comment lines (lines beginning with "#") and blank lines are ignored.
    10	#
    11	# Modified for Linux.  --marekm
    12	
    13	# REQUIRED for useradd/userdel/usermod
    14	#   Directory where mailboxes reside, _or_ name of file, relative to the
    15	#   home directory.  If you _do_ define MAIL_DIR and MAIL_FILE,
    16	#   MAIL_DIR takes precedence.
    17	#
    18	#   Essentially:
    19	#      - MAIL_DIR defines the location of users mail spool files
    20	#        (for mbox use) by appending the username to MAIL_DIR as defined
    21	#        below.
    22	#      - MAIL_FILE defines the location of the users mail spool files as the
    23	#        fully-qualified filename obtained by prepending the user home
    24	#        directory before $MAIL_FILE
    25	#
    26	# NOTE: This is no more used for setting up users MAIL environment variable
    27	#       which is, starting from shadow 4.0.12-1 in Debian, entirely the
    28	#       job of the pam_mail PAM modules
    29	#       See default PAM configuration files provided for
    30	#       login, su, etc.
    31	#
    32	# This is a temporary situation: setting these variables will soon
    33	# move to /etc/default/useradd and the variables will then be
    34	# no more supported
    35	MAIL_DIR        /var/mail
    36	#MAIL_FILE      .mail
    37	
    38	#
    39	# Enable logging and display of /var/log/faillog login failure info.
    40	# This option conflicts with the pam_tally PAM module.
    41	#
    42	FAILLOG_ENAB		yes
    43	
    44	#
    45	# Enable display of unknown usernames when login failures are recorded.
    46	#
    47	# WARNING: Unknown usernames may become world readable. 
    48	# See #290803 and #298773 for details about how this could become a security
    49	# concern
    50	LOG_UNKFAIL_ENAB	no
    51	
    52	#
    53	# Enable logging of successful logins
    54	#
    55	LOG_OK_LOGINS		no
    56	
    57	#
    58	# Enable "syslog" logging of su activity - in addition to sulog file logging.
    59	# SYSLOG_SG_ENAB does the same for newgrp and sg.
    60	#
    61	SYSLOG_SU_ENAB		yes
    62	SYSLOG_SG_ENAB		yes
    63	
    64	#
    65	# If defined, all su activity is logged to this file.
    66	#
    67	#SULOG_FILE	/var/log/sulog
    68	
    69	#
    70	# If defined, file which maps tty line to TERM environment parameter.
    71	# Each line of the file is in a format something like "vt100  tty01".
    72	#
    73	#TTYTYPE_FILE	/etc/ttytype
    74	
    75	#
    76	# If defined, login failures will be logged here in a utmp format
    77	# last, when invoked as lastb, will read /var/log/btmp, so...
    78	#
    79	FTMP_FILE	/var/log/btmp
    80	
    81	#
    82	# If defined, the command name to display when running "su -".  For
    83	# example, if this is defined as "su" then a "ps" will display the
    84	# command is "-su".  If not defined, then "ps" would display the
    85	# name of the shell actually being run, e.g. something like "-sh".
    86	#
    87	SU_NAME		su
    88	
    89	#
    90	# If defined, file which inhibits all the usual chatter during the login
    91	# sequence.  If a full pathname, then hushed mode will be enabled if the
    92	# user's name or shell are found in the file.  If not a full pathname, then
    93	# hushed mode will be enabled if the file exists in the user's home directory.
    94	#
    95	HUSHLOGIN_FILE	.hushlogin
    96	#HUSHLOGIN_FILE	/etc/hushlogins
    97	
    98	#
    99	# *REQUIRED*  The default PATH settings, for superuser and normal users.
   100	#
   101	# (they are minimal, add the rest in the shell startup files)
   102	ENV_SUPATH	PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
   103	ENV_PATH	PATH=/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games
   104	
   105	#
   106	# Terminal permissions
   107	#
   108	#	TTYGROUP	Login tty will be assigned this group ownership.
   109	#	TTYPERM		Login tty will be set to this permission.
   110	#
   111	# If you have a "write" program which is "setgid" to a special group
   112	# which owns the terminals, define TTYGROUP to the group number and
   113	# TTYPERM to 0620.  Otherwise leave TTYGROUP commented out and assign
   114	# TTYPERM to either 622 or 600.
   115	#
   116	# In Debian /usr/bin/bsd-write or similar programs are setgid tty
   117	# However, the default and recommended value for TTYPERM is still 0600
   118	# to not allow anyone to write to anyone else console or terminal
   119	
   120	# Users can still allow other people to write them by issuing 
   121	# the "mesg y" command.
   122	
   123	TTYGROUP	tty
   124	TTYPERM		0600
   125	
   126	#
   127	# Login configuration initializations:
   128	#
   129	#	ERASECHAR	Terminal ERASE character ('\010' = backspace).
   130	#	KILLCHAR	Terminal KILL character ('\025' = CTRL/U).
   131	#	UMASK		Default "umask" value.
   132	#
   133	# The ERASECHAR and KILLCHAR are used only on System V machines.
   134	# 
   135	# UMASK is the default umask value for pam_umask and is used by
   136	# useradd and newusers to set the mode of the new home directories.
   137	# 022 is the "historical" value in Debian for UMASK
   138	# 027, or even 077, could be considered better for privacy
   139	# There is no One True Answer here : each sysadmin must make up his/her
   140	# mind.
   141	#
   142	# If USERGROUPS_ENAB is set to "yes", that will modify this UMASK default value
   143	# for private user groups, i. e. the uid is the same as gid, and username is
   144	# the same as the primary group name: for these, the user permissions will be
   145	# used as group permissions, e. g. 022 will become 002.
   146	#
   147	# Prefix these values with "0" to get octal, "0x" to get hexadecimal.
   148	#
   149	ERASECHAR	0177
   150	KILLCHAR	025
   151	UMASK		022
   152	
   153	#
   154	# Password aging controls:
   155	#
   156	#	PASS_MAX_DAYS	Maximum number of days a password may be used.
   157	#	PASS_MIN_DAYS	Minimum number of days allowed between password changes.
   158	#	PASS_WARN_AGE	Number of days warning given before a password expires.
   159	#
   160	PASS_MAX_DAYS	99999
   161	PASS_MIN_DAYS	0
   162	PASS_WARN_AGE	7
   163	
   164	#
   165	# Min/max values for automatic uid selection in useradd
   166	#
   167	UID_MIN			 1000
   168	UID_MAX			60000
   169	# System accounts
   170	#SYS_UID_MIN		  100
   171	#SYS_UID_MAX		  999
   172	
   173	#
   174	# Min/max values for automatic gid selection in groupadd
   175	#
   176	GID_MIN			 1000
   177	GID_MAX			60000
   178	# System accounts
   179	#SYS_GID_MIN		  100
   180	#SYS_GID_MAX		  999
   181	
   182	#
   183	# Max number of login retries if password is bad. This will most likely be
   184	# overriden by PAM, since the default pam_unix module has it's own built
   185	# in of 3 retries. However, this is a safe fallback in case you are using
   186	# an authentication module that does not enforce PAM_MAXTRIES.
   187	#
   188	LOGIN_RETRIES		5
   189	
   190	#
   191	# Max time in seconds for login
   192	#
   193	LOGIN_TIMEOUT		60
   194	
   195	#
   196	# Which fields may be changed by regular users using chfn - use
   197	# any combination of letters "frwh" (full name, room number, work
   198	# phone, home phone).  If not defined, no changes are allowed.
   199	# For backward compatibility, "yes" = "rwh" and "no" = "frwh".
   200	# 
   201	CHFN_RESTRICT		rwh
   202	
   203	#
   204	# Should login be allowed if we can't cd to the home directory?
   205	# Default in no.
   206	#
   207	DEFAULT_HOME	yes
   208	
   209	#
   210	# If defined, this command is run when removing a user.
   211	# It should remove any at/cron/print jobs etc. owned by
   212	# the user to be removed (passed as the first argument).
   213	#
   214	#USERDEL_CMD	/usr/sbin/userdel_local
   215	
   216	#
   217	# Enable setting of the umask group bits to be the same as owner bits
   218	# (examples: 022 -> 002, 077 -> 007) for non-root users, if the uid is
   219	# the same as gid, and username is the same as the primary group name.
   220	#
   221	# If set to yes, userdel will remove the user's group if it contains no
   222	# more members, and useradd will create by default a group with the name
   223	# of the user.
   224	#
   225	USERGROUPS_ENAB yes
   226	
   227	#
   228	# Instead of the real user shell, the program specified by this parameter
   229	# will be launched, although its visible name (argv[0]) will be the shell's.
   230	# The program may do whatever it wants (logging, additional authentification,
   231	# banner, ...) before running the actual shell.
   232	#
   233	# FAKE_SHELL /bin/fakeshell
   234	
   235	#
   236	# If defined, either full pathname of a file containing device names or
   237	# a ":" delimited list of device names.  Root logins will be allowed only
   238	# upon these devices.
   239	#
   240	# This variable is used by login and su.
   241	#
   242	#CONSOLE	/etc/consoles
   243	#CONSOLE	console:tty01:tty02:tty03:tty04
   244	
   245	#
   246	# List of groups to add to the user's supplementary group set
   247	# when logging in on the console (as determined by the CONSOLE
   248	# setting).  Default is none.
   249	#
   250	# Use with caution - it is possible for users to gain permanent
   251	# access to these groups, even when not logged in on the console.
   252	# How to do it is left as an exercise for the reader...
   253	#
   254	# This variable is used by login and su.
   255	#
   256	#CONSOLE_GROUPS		floppy:audio:cdrom
   257	
   258	#
   259	# If set to "yes", new passwords will be encrypted using the MD5-based
   260	# algorithm compatible with the one used by recent releases of FreeBSD.
   261	# It supports passwords of unlimited length and longer salt strings.
   262	# Set to "no" if you need to copy encrypted passwords to other systems
   263	# which don't understand the new algorithm.  Default is "no".
   264	#
   265	# This variable is deprecated. You should use ENCRYPT_METHOD.
   266	#
   267	#MD5_CRYPT_ENAB	no
   268	
   269	#
   270	# If set to MD5 , MD5-based algorithm will be used for encrypting password
   271	# If set to SHA256, SHA256-based algorithm will be used for encrypting password
   272	# If set to SHA512, SHA512-based algorithm will be used for encrypting password
   273	# If set to DES, DES-based algorithm will be used for encrypting password (default)
   274	# Overrides the MD5_CRYPT_ENAB option
   275	#
   276	# Note: It is recommended to use a value consistent with
   277	# the PAM modules configuration.
   278	#
   279	ENCRYPT_METHOD SHA512
   280	
   281	#
   282	# Only used if ENCRYPT_METHOD is set to SHA256 or SHA512.
   283	#
   284	# Define the number of SHA rounds.
   285	# With a lot of rounds, it is more difficult to brute forcing the password.
   286	# But note also that it more CPU resources will be needed to authenticate
   287	# users.
   288	#
   289	# If not specified, the libc will choose the default number of rounds (5000).
   290	# The values must be inside the 1000-999999999 range.
   291	# If only one of the MIN or MAX values is set, then this value will be used.
   292	# If MIN > MAX, the highest value will be used.
   293	#
   294	# SHA_CRYPT_MIN_ROUNDS 5000
   295	# SHA_CRYPT_MAX_ROUNDS 5000
   296	
   297	################# OBSOLETED BY PAM ##############
   298	#						#
   299	# These options are now handled by PAM. Please	#
   300	# edit the appropriate file in /etc/pam.d/ to	#
   301	# enable the equivelants of them.
   302	#
   303	###############
   304	
   305	#MOTD_FILE
   306	#DIALUPS_CHECK_ENAB
   307	#LASTLOG_ENAB
   308	#MAIL_CHECK_ENAB
   309	#OBSCURE_CHECKS_ENAB
   310	#PORTTIME_CHECKS_ENAB
   311	#SU_WHEEL_ONLY
   312	#CRACKLIB_DICTPATH
   313	#PASS_CHANGE_TRIES
   314	#PASS_ALWAYS_WARN
   315	#ENVIRON_FILE
   316	#NOLOGINS_FILE
   317	#ISSUE_FILE
   318	#PASS_MIN_LEN
   319	#PASS_MAX_LEN
   320	#ULIMIT
   321	#ENV_HZ
   322	#CHFN_AUTH
   323	#CHSH_AUTH
   324	#FAIL_DELAY
   325	
   326	################# OBSOLETED #######################
   327	#						  #
   328	# These options are no more handled by shadow.    #
   329	#                                                 #
   330	# Shadow utilities will display a warning if they #
   331	# still appear.                                   #
   332	#                                                 #
   333	###################################################
   334	
   335	# CLOSE_SESSIONS
   336	# LOGIN_STRING
   337	# NO_PASSWORD_CONSOLE
   338	# QMAIL_DIR
   339	
   340	
   341	
mao@ubuntu:~/桌面$ 
```







## useradd命令

**添加新的系统用户**



命令：

```sh
useradd [选项] 用户名
```



|    选项     |                             含义                             |
| :---------: | :----------------------------------------------------------: |
|   -u UID    |    手工指定用户的 UID，注意 UID 的范围（不要小于 500）。     |
|  -d 主目录  | 手工指定用户的主目录。主目录必须写绝对路径，而且如果需要手工指定主目录，则一定要注意权限； |
| -c 用户说明 | 手工指定/etc/passwd文件中各用户信息中第 5 个字段的描述性内容，可随意配置； |
|   -g 组名   | 手工指定用户的初始组。一般以和用户名相同的组作为用户的初始组，在创建用户时会默认建立初始组。一旦手动指定，则系统将不会在创建此默认的初始组目录。 |
|   -G 组名   |  指定用户的附加组。我们把用户加入其他组，一般都使用附加组；  |
|  -s shell   |         手工指定用户的登录 Shell，默认是 /bin/bash；         |
|   -e 曰期   | 指定用户的失效曰期，格式为 "YYYY-MM-DD"。也就是 /etc/shadow 文件的第八个字段； |
|     -o      | 允许创建的用户的 UID 相同。例如，执行 "useradd -u 0 -o usertest" 命令建立用户 usertest，它的 UID 和 root 用户的 UID 相同，都是 0； |
|     -m      | 建立用户时强制建立用户的家目录。在建立系统用户时，该选项是默认的； |
|     -r      | 创建系统用户，也就是 UID 在 1~499 之间，供系统程序使用的用户。由于系统用户主要用于运行系统所需服务的权限配置，因此系统用户的创建默认不会创建主目录。 |





创建一个名字为test的普通用户：

```sh
useradd test
```



```sh
mao@ubuntu:~/桌面$ sudo useradd test
[sudo] mao 的密码： 
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ cat /etc/passwd 
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
systemd-timesync:x:102:104:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:103:106::/nonexistent:/usr/sbin/nologin
syslog:x:104:110::/home/syslog:/usr/sbin/nologin
_apt:x:105:65534::/nonexistent:/usr/sbin/nologin
tss:x:106:111:TPM software stack,,,:/var/lib/tpm:/bin/false
uuidd:x:107:114::/run/uuidd:/usr/sbin/nologin
tcpdump:x:108:115::/nonexistent:/usr/sbin/nologin
avahi-autoipd:x:109:116:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
usbmux:x:110:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
rtkit:x:111:117:RealtimeKit,,,:/proc:/usr/sbin/nologin
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
cups-pk-helper:x:113:120:user for cups-pk-helper service,,,:/home/cups-pk-helper:/usr/sbin/nologin
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/run/speech-dispatcher:/bin/false
avahi:x:115:121:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
saned:x:117:123::/var/lib/saned:/usr/sbin/nologin
nm-openvpn:x:118:124:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
hplip:x:119:7:HPLIP system user,,,:/run/hplip:/bin/false
whoopsie:x:120:125::/nonexistent:/bin/false
colord:x:121:126:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:122:127::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:123:128:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:124:65534::/run/gnome-initial-setup/:/bin/false
gdm:x:125:130:Gnome Display Manager:/var/lib/gdm3:/bin/false
sssd:x:126:131:SSSD system user,,,:/var/lib/sss:/usr/sbin/nologin
mao:x:1000:1000:linux,,,:/home/mao:/bin/bash
systemd-coredump:x:999:999:systemd Core Dumper:/:/usr/sbin/nologin
test:x:1001:1001::/home/test:/bin/sh
mao@ubuntu:~/桌面$ 
```





## /etc/default/useradd 文件



查看 /etc/default/useradd 文件中包含哪些内容：

```sh
cat -n /etc/default/useradd
```



```sh
mao@ubuntu:~/桌面$ cat -n /etc/default/useradd
     1	# Default values for useradd(8)
     2	#
     3	# The SHELL variable specifies the default login shell on your
     4	# system.
     5	# Similar to DSHELL in adduser. However, we use "sh" here because
     6	# useradd is a low level utility and should be as general
     7	# as possible
     8	SHELL=/bin/sh
     9	#
    10	# The default group for users
    11	# 100=users on Debian systems
    12	# Same as USERS_GID in adduser
    13	# This argument is used when the -n flag is specified.
    14	# The default behavior (when -n and -g are not specified) is to create a
    15	# primary user group with the same name as the user being added to the
    16	# system.
    17	# GROUP=100
    18	#
    19	# The default home directory. Same as DHOME for adduser
    20	# HOME=/home
    21	#
    22	# The number of days after a password expires until the account 
    23	# is permanently disabled
    24	# INACTIVE=-1
    25	#
    26	# The default expire date
    27	# EXPIRE=
    28	#
    29	# The SKEL variable specifies the directory containing "skeletal" user
    30	# files; in other words, files such as a sample .profile that will be
    31	# copied to the new user's home directory when it is created.
    32	# SKEL=/etc/skel
    33	#
    34	# Defines whether the mail spool should be created while
    35	# creating the account
    36	# CREATE_MAIL_SPOOL=yes
    37	
mao@ubuntu:~/桌面$ 
```





|         参数          |                             含义                             |
| :-------------------: | :----------------------------------------------------------: |
|       GR0UP=100       | 这个选项用于建立用户的默认组，也就是说，在添加每个用户时，用户的初始组就是 GID 为 100 的这个用户组。但 CentOS 并不是这样的，而是在添加用户时会自动建立和用户名相同的组作为此用户的初始组。也就是说这个选项并不会生效。  Linux 中默认用户组有两种机制：一种是私有用户组机制，系统会创建一个和用户名相同的用户组作为用户的初始组；另一种是公共用户组机制，系统用 GID 是 100 的用户组作为所有新建用户的初始组。目前我们采用的是私有用户组机制。 |
|      HOME=/home       | 指的是用户主目录的默认位置，所有新建用户的主目录默认都在 /home/下 |
|      INACTIVE=-1      | 指的是密码过期后的宽限天数，也就是 /etc/shadow 文件的第七个字段。这里默认值是 -1，代表所有新建立的用户密码永远不会失效。 |
|        EXPIRE=        | 表示密码失效时间，也就是 /etc/shadow 文件的第八个字段。默认值是空，代表所有新建用户没有失效时间，永久有效。 |
|    SHELL=/bin/bash    |       表示所有新建立的用户默认 Shell 都是 /bin/bash。        |
|    SKEL=/etc/skel     | 在创建一个新用户后，你会发现，该用户主目录并不是空目录，而是有 .bash_profile、.bashrc 等文件，这些文件都是从 /etc/skel 目录中自动复制过来的。因此，更改 /etc/skel 目录下的内容就可以改变新建用户默认主目录中的配置文件信息。 |
| CREATE_MAIL_SPOOL=yes | 指的是给新建用户建立邮箱，默认是创建。也就是说，对于所有的新建用户，系统都会新建一个邮箱，放在 /var/spool/mail/ 目录下，和用户名相同。 |





## passwd命令

创建新用户时，并没有设定用户密码，因此还无法用来登陆系统，所以需要使用此命令修改密码



命令：

```sh
passwd [选项] 用户名
```



选项：

- -S：查询用户密码的状态，也就是 /etc/shadow 文件中此用户密码的内容。仅 root 用户可用；
- -l：暂时锁定用户，该选项会在 /etc/shadow 文件中指定用户的加密密码串前添加 "!"，使密码失效。仅 root 用户可用；
- -u：解锁用户，和 -l 选项相对应，也是只能 root 用户使用；
- --stdin：可以将通过管道符输出的数据作为用户的密码。主要在批量添加用户时使用；
- -n 天数：设置该用户修改密码后，多长时间不能再次修改密码，也就是修改 /etc/shadow 文件中各行密码的第 4 个字段；
- -x 天数：设置该用户的密码有效期，对应 /etc/shadow 文件中各行密码的第 5 个字段；
- -w 天数：设置用户密码过期前的警告天数，对于 /etc/shadow 文件中各行密码的第 6 个字段；
- -i 日期：设置用户密码失效日期，对应 /etc/shadow 文件中各行密码的第 7 个字段。





设置用户test的密码：

```sh
sudo passwd test
```



```sh
mao@ubuntu:~/桌面$ sudo passwd test
新的 密码： 
重新输入新的 密码： 
passwd：已成功更新密码
mao@ubuntu:~/桌面$ 
```



验证密码是否创建成功：

```sh
mao@ubuntu:~/桌面$ sudo cat /etc/shadow
root:!:18915:0:99999:7:::
daemon:*:18858:0:99999:7:::
bin:*:18858:0:99999:7:::
sys:*:18858:0:99999:7:::
sync:*:18858:0:99999:7:::
games:*:18858:0:99999:7:::
man:*:18858:0:99999:7:::
lp:*:18858:0:99999:7:::
mail:*:18858:0:99999:7:::
news:*:18858:0:99999:7:::
uucp:*:18858:0:99999:7:::
proxy:*:18858:0:99999:7:::
www-data:*:18858:0:99999:7:::
backup:*:18858:0:99999:7:::
list:*:18858:0:99999:7:::
irc:*:18858:0:99999:7:::
gnats:*:18858:0:99999:7:::
nobody:*:18858:0:99999:7:::
systemd-network:*:18858:0:99999:7:::
systemd-resolve:*:18858:0:99999:7:::
systemd-timesync:*:18858:0:99999:7:::
messagebus:*:18858:0:99999:7:::
syslog:*:18858:0:99999:7:::
_apt:*:18858:0:99999:7:::
tss:*:18858:0:99999:7:::
uuidd:*:18858:0:99999:7:::
tcpdump:*:18858:0:99999:7:::
avahi-autoipd:*:18858:0:99999:7:::
usbmux:*:18858:0:99999:7:::
rtkit:*:18858:0:99999:7:::
dnsmasq:*:18858:0:99999:7:::
cups-pk-helper:*:18858:0:99999:7:::
speech-dispatcher:!:18858:0:99999:7:::
avahi:*:18858:0:99999:7:::
kernoops:*:18858:0:99999:7:::
saned:*:18858:0:99999:7:::
nm-openvpn:*:18858:0:99999:7:::
hplip:*:18858:0:99999:7:::
whoopsie:*:18858:0:99999:7:::
colord:*:18858:0:99999:7:::
geoclue:*:18858:0:99999:7:::
pulse:*:18858:0:99999:7:::
gnome-initial-setup:*:18858:0:99999:7:::
gdm:*:18858:0:99999:7:::
sssd:*:18858:0:99999:7:::
mao:$1$dvdYmO70$JMt6qRizm5GFCwQh6dk5/1:18915:0:99999:7:::
systemd-coredump:!!:18915::::::
test:$6$..X31U4l0toFPADb$M4JoY10jlmpbfRv70/vMBLSHW.125ncGJIqoC.MYRUQO5cqXGO3X84DYEp7cXEKdyDBGid8BIpwGUWAH7SQH11:19177:0:99999:7:::
mao@ubuntu:~/桌面$ 
```







## usermod命令

**用于修改用户信息**



命令：

```sh
usermod [选项] 用户名
```



选项：

- -c 用户说明：修改用户的说明信息，即修改 /etc/passwd 文件目标用户信息的第 5 个字段；
- -d 主目录：修改用户的主目录，即修改 /etc/passwd 文件中目标用户信息的第 6 个字段，需要注意的是，主目录必须写绝对路径；
- -e 日期：修改用户的失效曰期，格式为 "YYYY-MM-DD"，即修改 /etc/shadow 文件目标用户密码信息的第 8 个字段；
- -g 组名：修改用户的初始组，即修改 /etc/passwd 文件目标用户信息的第 4 个字段（GID）；
- -u UID：修改用户的UID，即修改 /etc/passwd 文件目标用户信息的第 3 个字段（UID）；
- -G 组名：修改用户的附加组，其实就是把用户加入其他用户组，即修改 /etc/group 文件；
- -l 用户名：修改用户名称；
- -L：临时锁定用户（Lock）；
- -U：解锁用户（Unlock），和 -L 对应；
- -s shell：修改用户的登录 Shell，默认是 /bin/bash。



锁定用户：

```sh
mao@ubuntu:~/桌面$ sudo usermod -L test
[sudo] mao 的密码： 
mao@ubuntu:~/桌面$ sudo cat /etc/shadow
root:!:18915:0:99999:7:::
daemon:*:18858:0:99999:7:::
bin:*:18858:0:99999:7:::
sys:*:18858:0:99999:7:::
sync:*:18858:0:99999:7:::
games:*:18858:0:99999:7:::
man:*:18858:0:99999:7:::
lp:*:18858:0:99999:7:::
mail:*:18858:0:99999:7:::
news:*:18858:0:99999:7:::
uucp:*:18858:0:99999:7:::
proxy:*:18858:0:99999:7:::
www-data:*:18858:0:99999:7:::
backup:*:18858:0:99999:7:::
list:*:18858:0:99999:7:::
irc:*:18858:0:99999:7:::
gnats:*:18858:0:99999:7:::
nobody:*:18858:0:99999:7:::
systemd-network:*:18858:0:99999:7:::
systemd-resolve:*:18858:0:99999:7:::
systemd-timesync:*:18858:0:99999:7:::
messagebus:*:18858:0:99999:7:::
syslog:*:18858:0:99999:7:::
_apt:*:18858:0:99999:7:::
tss:*:18858:0:99999:7:::
uuidd:*:18858:0:99999:7:::
tcpdump:*:18858:0:99999:7:::
avahi-autoipd:*:18858:0:99999:7:::
usbmux:*:18858:0:99999:7:::
rtkit:*:18858:0:99999:7:::
dnsmasq:*:18858:0:99999:7:::
cups-pk-helper:*:18858:0:99999:7:::
speech-dispatcher:!:18858:0:99999:7:::
avahi:*:18858:0:99999:7:::
kernoops:*:18858:0:99999:7:::
saned:*:18858:0:99999:7:::
nm-openvpn:*:18858:0:99999:7:::
hplip:*:18858:0:99999:7:::
whoopsie:*:18858:0:99999:7:::
colord:*:18858:0:99999:7:::
geoclue:*:18858:0:99999:7:::
pulse:*:18858:0:99999:7:::
gnome-initial-setup:*:18858:0:99999:7:::
gdm:*:18858:0:99999:7:::
sssd:*:18858:0:99999:7:::
mao:$1$dvdYmO70$JMt6qRizm5GFCwQh6dk5/1:18915:0:99999:7:::
systemd-coredump:!!:18915::::::
test:!$6$..X31U4l0toFPADb$M4JoY10jlmpbfRv70/vMBLSHW.125ncGJIqoC.MYRUQO5cqXGO3X84DYEp7cXEKdyDBGid8BIpwGUWAH7SQH11:19177:0:99999:7:::
mao@ubuntu:~/桌面$ 
```



test账户密码的的最前面加了！



解锁用户：

```sh
mao@ubuntu:~/桌面$ sudo usermod -U test
mao@ubuntu:~/桌面$ 
mao@ubuntu:~/桌面$ sudo cat /etc/shadow
root:!:18915:0:99999:7:::
daemon:*:18858:0:99999:7:::
bin:*:18858:0:99999:7:::
sys:*:18858:0:99999:7:::
sync:*:18858:0:99999:7:::
games:*:18858:0:99999:7:::
man:*:18858:0:99999:7:::
lp:*:18858:0:99999:7:::
mail:*:18858:0:99999:7:::
news:*:18858:0:99999:7:::
uucp:*:18858:0:99999:7:::
proxy:*:18858:0:99999:7:::
www-data:*:18858:0:99999:7:::
backup:*:18858:0:99999:7:::
list:*:18858:0:99999:7:::
irc:*:18858:0:99999:7:::
gnats:*:18858:0:99999:7:::
nobody:*:18858:0:99999:7:::
systemd-network:*:18858:0:99999:7:::
systemd-resolve:*:18858:0:99999:7:::
systemd-timesync:*:18858:0:99999:7:::
messagebus:*:18858:0:99999:7:::
syslog:*:18858:0:99999:7:::
_apt:*:18858:0:99999:7:::
tss:*:18858:0:99999:7:::
uuidd:*:18858:0:99999:7:::
tcpdump:*:18858:0:99999:7:::
avahi-autoipd:*:18858:0:99999:7:::
usbmux:*:18858:0:99999:7:::
rtkit:*:18858:0:99999:7:::
dnsmasq:*:18858:0:99999:7:::
cups-pk-helper:*:18858:0:99999:7:::
speech-dispatcher:!:18858:0:99999:7:::
avahi:*:18858:0:99999:7:::
kernoops:*:18858:0:99999:7:::
saned:*:18858:0:99999:7:::
nm-openvpn:*:18858:0:99999:7:::
hplip:*:18858:0:99999:7:::
whoopsie:*:18858:0:99999:7:::
colord:*:18858:0:99999:7:::
geoclue:*:18858:0:99999:7:::
pulse:*:18858:0:99999:7:::
gnome-initial-setup:*:18858:0:99999:7:::
gdm:*:18858:0:99999:7:::
sssd:*:18858:0:99999:7:::
mao:$1$dvdYmO70$JMt6qRizm5GFCwQh6dk5/1:18915:0:99999:7:::
systemd-coredump:!!:18915::::::
test:$6$..X31U4l0toFPADb$M4JoY10jlmpbfRv70/vMBLSHW.125ncGJIqoC.MYRUQO5cqXGO3X84DYEp7cXEKdyDBGid8BIpwGUWAH7SQH11:19177:0:99999:7:::
mao@ubuntu:~/桌面$ 
```





修改用户说明：

```sh
ao@ubuntu:~/桌面$ sudo usermod -c "test user" test
mao@ubuntu:~/桌面$ sudo cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
systemd-timesync:x:102:104:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:103:106::/nonexistent:/usr/sbin/nologin
syslog:x:104:110::/home/syslog:/usr/sbin/nologin
_apt:x:105:65534::/nonexistent:/usr/sbin/nologin
tss:x:106:111:TPM software stack,,,:/var/lib/tpm:/bin/false
uuidd:x:107:114::/run/uuidd:/usr/sbin/nologin
tcpdump:x:108:115::/nonexistent:/usr/sbin/nologin
avahi-autoipd:x:109:116:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
usbmux:x:110:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
rtkit:x:111:117:RealtimeKit,,,:/proc:/usr/sbin/nologin
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
cups-pk-helper:x:113:120:user for cups-pk-helper service,,,:/home/cups-pk-helper:/usr/sbin/nologin
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/run/speech-dispatcher:/bin/false
avahi:x:115:121:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
saned:x:117:123::/var/lib/saned:/usr/sbin/nologin
nm-openvpn:x:118:124:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
hplip:x:119:7:HPLIP system user,,,:/run/hplip:/bin/false
whoopsie:x:120:125::/nonexistent:/bin/false
colord:x:121:126:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:122:127::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:123:128:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:124:65534::/run/gnome-initial-setup/:/bin/false
gdm:x:125:130:Gnome Display Manager:/var/lib/gdm3:/bin/false
sssd:x:126:131:SSSD system user,,,:/var/lib/sss:/usr/sbin/nologin
mao:x:1000:1000:linux,,,:/home/mao:/bin/bash
systemd-coredump:x:999:999:systemd Core Dumper:/:/usr/sbin/nologin
test:x:1001:1001:test user:/home/test:/bin/sh
mao@ubuntu:~/桌面$ 
```





## chage命令

chage 命令可以显示更加详细的用户密码信息，并且和 passwd 命令一样，提供了修改用户密码信息的功能



命令：

```sh
chage [选项] 用户名
```



- -l：列出用户的详细密码状态;
- -d 日期：修改 /etc/shadow 文件中指定用户密码信息的第 3 个字段，也就是最后一次修改密码的日期，格式为 YYYY-MM-DD；
- -m 天数：修改密码最短保留的天数，也就是 /etc/shadow 文件中的第 4 个字段；
- -M 天数：修改密码的有效期，也就是 /etc/shadow 文件中的第 5 个字段；
- -W 天数：修改密码到期前的警告天数，也就是 /etc/shadow 文件中的第 6 个字段；
- -i 天数：修改密码过期后的宽限天数，也就是 /etc/shadow 文件中的第 7 个字段；
- -E 日期：修改账号失效日期，格式为 YYYY-MM-DD，也就是 /etc/shadow 文件中的第 8 个字段。





查看用户密码状态：

```sh
mao@ubuntu:~/桌面$ sudo chage -l test
最近一次密码修改时间					： 7月 04, 2022
密码过期时间					： 从不
密码失效时间					： 从不
帐户过期时间						： 从不
两次改变密码之间相距的最小天数		：0
两次改变密码之间相距的最大天数		：99999
在密码过期之前警告的天数	：7
mao@ubuntu:~/桌面$ 
```





## userdel命令

**删除用户的相关数据**



命令：

```sh
userdel -r 用户名
```



-r 选项表示在删除用户的同时删除用户的家目录。



删除用户test：

```sh
mao@ubuntu:~/桌面$ sudo userdel test
[sudo] mao 的密码： 
mao@ubuntu:~/桌面$ 
```



验证：

```sh
mao@ubuntu:~/桌面$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
systemd-timesync:x:102:104:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:103:106::/nonexistent:/usr/sbin/nologin
syslog:x:104:110::/home/syslog:/usr/sbin/nologin
_apt:x:105:65534::/nonexistent:/usr/sbin/nologin
tss:x:106:111:TPM software stack,,,:/var/lib/tpm:/bin/false
uuidd:x:107:114::/run/uuidd:/usr/sbin/nologin
tcpdump:x:108:115::/nonexistent:/usr/sbin/nologin
avahi-autoipd:x:109:116:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
usbmux:x:110:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
rtkit:x:111:117:RealtimeKit,,,:/proc:/usr/sbin/nologin
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
cups-pk-helper:x:113:120:user for cups-pk-helper service,,,:/home/cups-pk-helper:/usr/sbin/nologin
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/run/speech-dispatcher:/bin/false
avahi:x:115:121:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
saned:x:117:123::/var/lib/saned:/usr/sbin/nologin
nm-openvpn:x:118:124:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
hplip:x:119:7:HPLIP system user,,,:/run/hplip:/bin/false
whoopsie:x:120:125::/nonexistent:/bin/false
colord:x:121:126:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:122:127::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:123:128:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:124:65534::/run/gnome-initial-setup/:/bin/false
gdm:x:125:130:Gnome Display Manager:/var/lib/gdm3:/bin/false
sssd:x:126:131:SSSD system user,,,:/var/lib/sss:/usr/sbin/nologin
mao:x:1000:1000:linux,,,:/home/mao:/bin/bash
systemd-coredump:x:999:999:systemd Core Dumper:/:/usr/sbin/nologin
mao@ubuntu:~/桌面$ 
```





## id命令

id 命令可以**查询用户的UID、GID 和附加组的信息**



命令：

```sh
id 用户名
```



```sh
mao@ubuntu:~/桌面$ id mao
用户id=1000(mao) 组id=1000(mao) 组=1000(mao),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),120(lpadmin),132(lxd),133(sambashare)
mao@ubuntu:~/桌面$ id root
用户id=0(root) 组id=0(root) 组=0(root)
mao@ubuntu:~/桌面$ 
```





## su命令

su 是最简单的用户切换命令，通过该命令可以实现任何身份的切换，包括从普通用户切换为 root 用户、从 root 用户切换为普通用户以及普通用户之间的切换。



普通用户之间切换以及普通用户切换至 root 用户，都需要知晓对方的密码，只有正确输入密码，才能实现切换；从 root 用户切换至其他用户，无需知晓对方密码，直接可切换成功。



命令：

```sh
su [选项] 用户名
```



选项：

- -：当前用户不仅切换为指定用户的身份，同时所用的工作环境也切换为此用户的环境（包括 PATH 变量、MAIL 变量等），使用 - 选项可省略用户名，默认会切换为 root 用户。
- -l：同 - 的使用类似，也就是在切换用户身份的同时，完整切换工作环境，但后面需要添加欲切换的使用者账号。
- -p：表示切换为指定用户的身份，但不改变当前的工作环境（不使用切换用户的配置文件）。
- -m：和 -p 一样；
- -c 命令：仅切换用户执行一次命令，执行后自动切换回来，该选项后通常会带有要执行的命令。





## whoami和who am i命令

whoami 命令和 who am i 命令是不同的 2 个命令，**前者用来打印当前执行操作的用户名，后者则用来打印登陆当前 Linux 系统的用户名。**



```sh
mao@ubuntu:~/桌面$ whoami
mao
mao@ubuntu:~/桌面$ who am i
mao@ubuntu:~/桌面$ sudo whoami
root
mao@ubuntu:~/桌面$ sudo who am i
mao@ubuntu:~/桌面$ 
```



执行 whoami 命令，等同于执行 id -un 命令；执行 who am i 命令，等同于执行 who -m 命令。







## groupadd命令

**添加用户组**



命令：

```sh
groupadd [选项] 组名
```



- -g GID：指定组 ID；
- -r：创建系统群组。





## groupmod命令

groupmod 命令用于**修改用户组的相关信息**



```sh
groupmod [选项] 组名
```



- -g GID：修改组 ID；
- -n 新组名：修改组名；





## groupdel命令

**用于删除用户组**



命令：

```sh
groupdel 组名
```



不能使用 groupdel 命令随意删除群组。此命令仅适用于删除那些 "不是任何用户初始组" 的群组





## gpasswd命令

**把用户添加进组或从组中删除**



命令：

```sh
gpasswd 选项 组名
```



|     选项     |                             功能                             |
| :----------: | :----------------------------------------------------------: |
|              |      选项为空时，表示给群组设置密码，仅 root 用户可用。      |
| -A user1,... | 将群组的控制权交给 user1,... 等用户管理，也就是说，设置 user1,... 等用户为群组的管理员，仅 root 用户可用。 |
| -M user1,... |       将 user1,... 加入到此群组中，仅 root 用户可用。        |
|      -r      |              移除群组的密码，仅 root 用户可用。              |
|      -R      |             让群组的密码失效，仅 root 用户可用。             |
|   -a user    |                  将 user 用户加入到群组中。                  |
|   -d user    |                  将 user 用户从群组中移除。                  |





## newgrp命令

newgrp 命令**可以从用户的附加组中选择一个群组，作为用户新的初始组**



命令：

```sh
newgrp 组名
```















# 权限管理

## chgrp命令

**修改文件和目录的所属组**



命令：

```sh
chgrp [-R] 所属组 文件名（目录名）
```



-R选项常常作用于更改目录的所属组，表示更改连同子目录中所有文件的所属组信息



创建组group1和文件test1.txt：

```sh
mao@ubuntu:~/桌面$ sudo groupadd group1
[sudo] mao 的密码： 
mao@ubuntu:~/桌面$ touch test1.txt
```



更改：

```sh
mao@ubuntu:~/桌面$ sudo chgrp group1 test1.txt
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao mao        4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao       20 7月   2 04:38 2.txt
-rw------- 1 mao mao     8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao    16984 12月 29  2021 a.out
-rw------- 1 mao mao     9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao     2956 11月  4  2021 filea.c
-rw------- 1 mao mao       96 10月 23  2021 func1.c
-rw------- 1 mao mao       98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao mao        6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao mao        7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao mao     2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao      242 10月 23  2021 main.c
-rw------- 1 mao mao      206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao     1668 7月   2 22:24 out.txt
-rw-rw-r-- 1 mao group1     3 7月   5 04:06 test1.txt
mao@ubuntu:~/桌面$ 
```







## chown命令

该命令主要**用于修改文件（或目录）的所有者，也可以修改文件（或目录）的所属组**



修改所有者时：

```sh
chown [-R] 所有者 文件或目录
```



更改所有者和所属组：

```sh
chown [-R] 所有者:所属组 文件或目录
```



```sh
mao@ubuntu:~/桌面$ sudo chown root test1.txt
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao  mao        4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao  mao       20 7月   2 04:38 2.txt
-rw------- 1 mao  mao     8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao    16984 12月 29  2021 a.out
-rw------- 1 mao  mao     9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao     2956 11月  4  2021 filea.c
-rw------- 1 mao  mao       96 10月 23  2021 func1.c
-rw------- 1 mao  mao       98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao  mao        6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao  mao        7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao  mao     2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao      242 10月 23  2021 main.c
-rw------- 1 mao  mao      206 10月 23  2021 main.h
-rw-rw-r-- 1 mao  mao     1668 7月   2 22:24 out.txt
-rw-rw-r-- 1 root group1     3 7月   5 04:06 test1.txt
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ sudo chown root:root test1.txt
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao  mao      4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao  mao     20 7月   2 04:38 2.txt
-rw------- 1 mao  mao   8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao  16984 12月 29  2021 a.out
-rw------- 1 mao  mao   9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao   2956 11月  4  2021 filea.c
-rw------- 1 mao  mao     96 10月 23  2021 func1.c
-rw------- 1 mao  mao     98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao  mao      6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao  mao      7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao  mao   2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao    242 10月 23  2021 main.c
-rw------- 1 mao  mao    206 10月 23  2021 main.h
-rw-rw-r-- 1 mao  mao   1668 7月   2 22:24 out.txt
-rw-rw-r-- 1 root root     3 7月   5 04:06 test1.txt
mao@ubuntu:~/桌面$ 
```





## 权限位

最常见的文件权限有 3 种，即对文件的读（用 r 表示）、写（用 w 表示）和执行（用 x 表示，针对可执行文件或目录）权限



比如：

```sh
-rw-rw-r-- 1 root root     3 7月   5 04:06 test1.txt
```



每行的第一列表示的就是各文件针对不同用户设定的权限，一共 11 位，但第 1 位用于表示文件的具体类型，最后一位此文件受 SELinux 的安全规则管理

为文件设定不同用户的读、写和执行权限，仅涉及到 9 位字符，即**rw-rw-r--**

Linux 将访问文件的用户分为 3 类，分别是文件的所有者，所属组（也就是文件所属的群组）以及其他人的权限

* 前三位是文件所有者的权限，即rw-
* 中间三位是所属组的权限，即rw-
* 最后三位是其他人的权限，即r--





## rwx 权限对文件的作用



|   rwx 权限    |                         对文件的作用                         |
| :-----------: | :----------------------------------------------------------: |
|  读权限（r）  | 表示可读取此文件中的实际内容，例如，可以对文件执行 cat、more、less、head、tail 等文件查看命令。 |
|  写权限（w）  | 表示可以编辑、新增或者修改文件中的内容，例如，可以对文件执行 vim、echo 等修改文件数据的命令。注意，无权限不赋予用户删除文件的权利，除非用户对文件的上级目录拥有写权限才可以。 |
| 执行权限（x） | 表示该文件具有被系统执行的权限。Window系统中查看一个文件是否为可执行文件，是通过扩展名（.exe、.bat 等），但在 Linux 系统中，文件是否能被执行，是通过看此文件是否具有 x 权限来决定的。也就是说，只要文件拥有 x 权限，则此文件就是可执行文件。但是，文件到底能够正确运行，还要看文件中的代码是否正确。 |





## rwx 权限对目录的作用



|   rwx 权限    |                         对目录的作用                         |
| :-----------: | :----------------------------------------------------------: |
|  读权限（r）  | 表示具有读取目录结构列表的权限，也就是说，可以看到目录中有哪些文件和子目录。一旦对目录拥有 r 权限，就可以在此目录下执行 ls 命令，查看目录中的内容。 |
|  写权限（w）  | 对于目录来说，w 权限是最高权限。对目录拥有 w 权限，表示可以对目录做以下操作：在此目录中建立新的文件或子目录；删除已存在的文件和目录（无论子文件或子目录的权限是怎样的）；对已存在的文件或目录做更名操作；移动此目录下的文件和目录的位置。一旦对目录拥有 w 权限，就可以在目录下执行 touch、rm、cp、mv 等命令。 |
| 执行权限（x） | 目录是不能直接运行的，对目录赋予 x 权限，代表用户可以进入目录，也就是说，赋予 x 权限的用户或群组可以使用 cd 命令。 |



对于目录来说，常用来设定目录的权限其实只有 0（---）、5（r-x）、7（rwx）这 3 种







## chmod命令

**用于修改文件或目录的权限**



linux使用进制位来表示权限，三种权限，一共三位二进制位

关系如下：

10进制：

```sh
r --> 4
w --> 2
x --> 1
```

二进制：

```sh
r --> nxx
w --> xnx
x --> xxn
```

n代表0或者1，x代码其它权限



比如：

```sh
rwx = 4+2+1 = 7,二机制111
rw- = 4+2 = 6，二进制110
r-x = 4+1 = 5，二进制101
r-- = 4 ，二进制100
```



命令：

```sh
chmod [-R] 权限值 文件名
```



-R选项表示连同子目录中的所有文件，也都修改设定的权限。



```sh
mao@ubuntu:~/桌面$ touch test2.txt
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao  mao      4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao  mao     20 7月   2 04:38 2.txt
-rw------- 1 mao  mao   8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao  16984 12月 29  2021 a.out
-rw------- 1 mao  mao   9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao   2956 11月  4  2021 filea.c
-rw------- 1 mao  mao     96 10月 23  2021 func1.c
-rw------- 1 mao  mao     98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao  mao      6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao  mao      7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao  mao   2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao    242 10月 23  2021 main.c
-rw------- 1 mao  mao    206 10月 23  2021 main.h
-rw-rw-r-- 1 mao  mao   1668 7月   2 22:24 out.txt
-rw-rw-r-- 1 root root     3 7月   5 04:06 test1.txt
-rw-rw-r-- 1 mao  mao      0 7月   5 04:51 test2.txt
mao@ubuntu:~/桌面$ chmod 777 test2.txt
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao  mao      4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao  mao     20 7月   2 04:38 2.txt
-rw------- 1 mao  mao   8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao  16984 12月 29  2021 a.out
-rw------- 1 mao  mao   9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao   2956 11月  4  2021 filea.c
-rw------- 1 mao  mao     96 10月 23  2021 func1.c
-rw------- 1 mao  mao     98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao  mao      6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao  mao      7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao  mao   2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao    242 10月 23  2021 main.c
-rw------- 1 mao  mao    206 10月 23  2021 main.h
-rw-rw-r-- 1 mao  mao   1668 7月   2 22:24 out.txt
-rw-rw-r-- 1 root root     3 7月   5 04:06 test1.txt
-rwxrwxrwx 1 mao  mao      0 7月   5 04:51 test2.txt
mao@ubuntu:~/桌面$ chmod 400 test2.txt
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao  mao      4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao  mao     20 7月   2 04:38 2.txt
-rw------- 1 mao  mao   8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao  16984 12月 29  2021 a.out
-rw------- 1 mao  mao   9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao   2956 11月  4  2021 filea.c
-rw------- 1 mao  mao     96 10月 23  2021 func1.c
-rw------- 1 mao  mao     98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao  mao      6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao  mao      7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao  mao   2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao    242 10月 23  2021 main.c
-rw------- 1 mao  mao    206 10月 23  2021 main.h
-rw-rw-r-- 1 mao  mao   1668 7月   2 22:24 out.txt
-rw-rw-r-- 1 root root     3 7月   5 04:06 test1.txt
-r-------- 1 mao  mao      0 7月   5 04:51 test2.txt
mao@ubuntu:~/桌面$ chmod 664 test2.txt
mao@ubuntu:~/桌面$ ls -l
总用量 92
-rw-rw-r-- 1 mao  mao      4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao  mao     20 7月   2 04:38 2.txt
-rw------- 1 mao  mao   8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao  16984 12月 29  2021 a.out
-rw------- 1 mao  mao   9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao   2956 11月  4  2021 filea.c
-rw------- 1 mao  mao     96 10月 23  2021 func1.c
-rw------- 1 mao  mao     98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao  mao      6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao  mao      7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao  mao   2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao    242 10月 23  2021 main.c
-rw------- 1 mao  mao    206 10月 23  2021 main.h
-rw-rw-r-- 1 mao  mao   1668 7月   2 22:24 out.txt
-rw-rw-r-- 1 root root     3 7月   5 04:06 test1.txt
-rw-rw-r-- 1 mao  mao      0 7月   5 04:51 test2.txt
mao@ubuntu:~/桌面$ 
```



还可以使用字母修改文件权限





## umask 命令

**令新建文件和目录拥有默认权限**

新建的文件和目录时通过继承上级目录的权限获得的初始权限，而 Linux 不同，它是通过使用 umask 默认权限来给所有新建的文件和目录赋予初始权限的。



使用：

```sh
mao@ubuntu:~/桌面$ umask
0002
mao@ubuntu:~/桌面$ 
```



root用户默认是0022，普通用户默认是 0002



umask 默认权限确实由 4 个八进制数组成，第 1 个数代表的是文件所具有的特殊权限，后 3 位数字是umask 权限值



文件和目录的真正初始权限，可通过以下的计算得到：

```sh
文件（或目录）的初始权限 = 文件（或目录）的最大默认权限 - umask权限
```



- 对文件来讲，其可拥有的最大默认权限是 666，即 rw-rw-rw-。也就是说，使用文件的任何用户都没有执行（x）权限。原因很简单，执行权限是文件的最高权限，赋予时绝对要慎重，因此绝不能在新建文件的时候就默认赋予，只能通过用户手工赋予。
- 对目录来讲，其可拥有的最大默认权限是 777，即 rwxrwxrwx。



修改权限命令：

```sh
umask 后三位的权限值
```



```sh
mao@ubuntu:~/桌面$ umask 022
mao@ubuntu:~/桌面$ umask
0022
mao@ubuntu:~/桌面$ umask 002
mao@ubuntu:~/桌面$ umask
0002
mao@ubuntu:~/桌面$ 
```





## ACL权限



说明：

1. 有一个 /project 目录，这是班级的项目目录。班级中的每个学员都可以访问和修改这个目录，老师需要拥有对该目录的最高权限，其他班级的学员当然不能访问这个目录

2. 老师使用 root 用户，作为这个目录的属主，权限为 rwx；班级所有的学员都加入 tgroup 组，使 tgroup 组作为 /project 目录的属组，权限是 rwx；其他人的权限设定为 0（也就是 ---）。这样一来，访问此目录的权限就符合我们的要求了。

3. 有一天，班里来了一位试听的学员 st，她必须能够访问 /project 目录，所以必须对这个目录拥有 r 和 x 权限；但是她又没有学习过以前的课程，所以不能赋予她 w 权限，怕她改错了目录中的内容，所以学员 st 的权限就是 r-x。可是如何分配她的身份呢？变为属主？当然不行，要不 root 该放哪里？加入 tgroup 组？也不行，因为 tgroup 组的权限是 rwx，而我们要求学员 st 的权限是 r-x。如果把其他人的权限改为 r-x 呢？这样一来，其他班级的所有学员都可以访问 /project 目录了。

4. 显然，普通权限的三种身份不够用了，无法实现对某个单独的用户设定访问权限，这种情况下，就需要使用 ACL 访问控制权限。



ACL，是 Access Control List（访问控制列表）的缩写，在 Linux 系统中， ACL 可实现对单一用户设定访问文件的权限。也可以这么说，设定文件的访问权限，除了用传统方式（3 种身份搭配 3 种权限），还可以使用 ACL 进行设定。拿本例中的 st 学员来说，既然赋予它传统的 3 种身份，无法解决问题，就可以考虑使用 ACL 权限控制的方式，直接对 st 用户设定访问文件的 r-x 权限。





## ACL权限设置

设定 ACl 权限，常用命令有 2 个，分别是 setfacl 和 getfacl 命令，前者用于给指定文件或目录设定 ACL 权限，后者用于查看是否配置成功。



查看文件或目录当前设定的 ACL 权限信息：

```sh
getfacl 文件名
```



设定用户或群组对指定文件的访问权限：

```sh
setfacl 选项 文件名
```



|  选项   |                             功能                             |
| :-----: | :----------------------------------------------------------: |
| -m 参数 | 设定 ACL 权限。如果是给予用户 ACL 权限，参数则使用 "u:用户名:权限" 的格式，例如 `setfacl -m u:st:rx /project` 表示设定 st 用户对 project 目录具有 rx 权限；如果是给予组 ACL 权限，参数则使用 "g:组名:权限" 格式，例如 `setfacl -m g:tgroup:rx /project` 表示设定群组 tgroup 对 project 目录具有 rx 权限。 |
| -x 参数 | 删除指定用户（参数使用 u:用户名）或群组（参数使用 g:群组名）的 ACL 权限，例如 `setfacl -x u:st /project` 表示删除 st 用户对 project 目录的 ACL 权限。 |
|   -b    | 删除所有的 ACL 权限，例如 `setfacl -b /project` 表示删除有关 project 目录的所有 ACL 权限。 |
|   -d    | 设定默认 ACL 权限，命令格式为 "setfacl -m d:u:用户名:权限 文件名"（如果是群组，则使用 d:g:群组名:权限），只对目录生效，指目录中新建立的文件拥有此默认权限，例如 `setfacl -m d:u:st:rx /project` 表示 st 用户对 project 目录中新建立的文件拥有 rx 权限。 |
|   -R    | 递归设定 ACL 权限，指设定的 ACL 权限会对目录下的所有子文件生效，命令格式为 "setfacl -m u:用户名:权限 -R 文件名"（群组使用 g:群组名:权限），例如 `setfacl -m u:st:rx -R /project` 表示 st 用户对已存在于 project 目录中的子文件和子目录拥有 rx 权限。 |
|   -k    |                     删除默认 ACL 权限。                      |



```sh
mao@ubuntu:~/桌面$ getfacl out.txt
# file: out.txt
# owner: mao
# group: mao
user::rw-
group::rw-
other::r--
```

```sh
mao@ubuntu:~/桌面$ setfacl -m u:mao:rx out.txt
```

```sh
mao@ubuntu:~/桌面$ getfacl out.txt
# file: out.txt
# owner: mao
# group: mao
user::rw-
user:mao:r-x
group::rw-
mask::rwx
other::r--

mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 96
-rw-rw-r--  1 mao  mao      4 12月 29  2021 1.txt
-rwxrwxr-x  1 mao  mao     20 7月   2 04:38 2.txt
-rw-------  1 mao  mao   8859 12月 30  2021 a.c
-rwxrwxr-x  1 mao  mao  16984 12月 29  2021 a.out
-rw-------  1 mao  mao   9221 12月 30  2021 English_early_education_machine_input.c
-rw-------  1 mao  mao   2956 11月  4  2021 filea.c
-rw-------  1 mao  mao     96 10月 23  2021 func1.c
-rw-------  1 mao  mao     98 10月 23  2021 func2.c
-rw-rw-r--  1 mao  mao      6 7月   2 21:48 in2.txt
-rw-rw-r--  1 mao  mao      7 7月   2 21:50 in.txt
-rwxrw-rw-  1 mao  mao   2324 12月 29  2021 linux_file.c
-rw-------  1 mao  mao    242 10月 23  2021 main.c
-rw-------  1 mao  mao    206 10月 23  2021 main.h
-rw-rwxr--+ 1 mao  mao   4682 7月   5 05:17 out.txt
-rw-rw-r--  1 root root     3 7月   5 04:06 test1.txt
-rw-rw-r--  1 mao  mao      0 7月   5 04:51 test2.txt
mao@ubuntu:~/桌面$ 
```



删除：

```sh
mao@ubuntu:~/桌面$ setfacl -b out.txt
mao@ubuntu:~/桌面$ getfacl out.txt
# file: out.txt
# owner: mao
# group: mao
user::rw-
group::rw-
other::r--

mao@ubuntu:~/桌面$ ls -l
总用量 96
-rw-rw-r-- 1 mao  mao      4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao  mao     20 7月   2 04:38 2.txt
-rw------- 1 mao  mao   8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao  16984 12月 29  2021 a.out
-rw------- 1 mao  mao   9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao   2956 11月  4  2021 filea.c
-rw------- 1 mao  mao     96 10月 23  2021 func1.c
-rw------- 1 mao  mao     98 10月 23  2021 func2.c
-rw-rw-r-- 1 mao  mao      6 7月   2 21:48 in2.txt
-rw-rw-r-- 1 mao  mao      7 7月   2 21:50 in.txt
-rwxrw-rw- 1 mao  mao   2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao    242 10月 23  2021 main.c
-rw------- 1 mao  mao    206 10月 23  2021 main.h
-rw-rw-r-- 1 mao  mao   4682 7月   5 05:17 out.txt
-rw-rw-r-- 1 root root     3 7月   5 04:06 test1.txt
-rw-rw-r-- 1 mao  mao      0 7月   5 04:51 test2.txt
mao@ubuntu:~/桌面$ 
```







## SetUID

SetUID，简称 SUID 特殊权限

SUID 特殊权限仅适用于可执行文件，所具有的功能是，只要用户对设有 SUID 的文件有执行权限，那么当用户执行此文件时，会以文件所有者的身份去执行此文件，一旦文件执行结束，身份的切换也随之消失



当普通用户使用 passwd 命令尝试更改自己的密码时，实际上是在以 root 的身份执行passwd命令，正因为 root 可以将密码写入 /etc/shadow 文件，所以普通用户也能做到。只不过，一旦命令执行完成，普通用户所具有的 root身份也随之消失。



查看/usr/bin/passwd权限：

```sh
mao@ubuntu:~/桌面$ ls -l /usr/bin/passwd
-rwsr-xr-x 1 root root 68208 7月  14  2021 /usr/bin/passwd
mao@ubuntu:~/桌面$ 
```



- 只有可执行文件才能设定 SetUID 权限，对目录设定 SUID，是无效的。
- 用户要对该文件拥有 x（执行）权限。
- 用户在执行该文件时，会以文件所有者的身份执行。
- SetUID 权限只在文件执行过程中有效，一旦执行完毕，身份的切换也随之消失。



**不要轻易设置SetUID（SUID）权限，否则会带来重大安全隐患**





## SetGID

当 s 权限位于所属组的 x 权限位时，就被称为 SetGID，简称 SGID 特殊权限

例如：rwx--s--x



与 SUID 不同的是，SGID 既可以对文件进行配置，也可以对目录进行配置。



SGID 具有如下几个特点：

- SGID 只针对可执行文件有效，换句话说，只有可执行文件才可以被赋予 SGID 权限，普通文件赋予 SGID 没有意义。
- 用户需要对此可执行文件有 x 权限；
- 用户在执行具有 SGID 权限的可执行文件时，用户的群组身份会变为文件所属群组；
- SGID 权限赋予用户改变组身份的效果，只在可执行文件运行过程中有效；



SUID 赋予用户的是文件所有者的权限，而 SGID 赋予用户的是文件所属组的权限





## Stick BIT

Sticky BIT，简称 SBIT 特殊权限，可意为粘着位、粘滞位、防删除位等

SBIT 权限仅对目录有效，一旦目录设定了 SBIT 权限，则用户在此目录下创建的文件或目录，就只有自己和 root 才有权利修改或删除该文件。



也就是说，当甲用户以目录所属组或其他人的身份进入 A 目录时，如果甲对该目录有 w 权限，则表示对于 A 目录中任何用户创建的文件或子目录，甲都可以进行修改甚至删除等操作。但是，如果 A 目录设定有 SBIT 权限，甲用户只能操作自己创建的文件或目录，而无法修改甚至删除其他用户创建的文件或目录。



存储临时文件的 /tmp 目录就设定有 SBIT 权限

```sh
mao@ubuntu:~/桌面$ ll -d /tmp
drwxrwxrwt 20 root root 4096 7月   5 05:45 /tmp/
mao@ubuntu:~/桌面$ 
```



在其他人身份的权限设定中，原来的 x 权限位被 t 权限占用了，这就表示此目录拥有 SBIT 权限





## 设置特殊权限

给文件或目录设定特殊权限，只需在这 3 个数字之前增加一个数字位，用来放置给文件或目录设定的特殊权限



```sh
4 --> SUID
2 --> SGID
1 --> SBIT
```



如果要将一个文件权限设置为 -rwsr-xr-x，怎么办呢？此文件的普通权限为 755，另外，此文件还有 SUID 权限，因此只需在 755 的前面，加上 SUID 对应的数字 4 即可。也就是说，只需执行`chmod 4755 文件名`命令，就完成了-rwsr-xr-x 权限的设定



* 如果某文件拥有 SUID 和 SGID 权限，则只需要给 chmod 命令传递 6---（- 表示数字）即可

* 如果某目录拥有 SGID 和 SBIT，只需要给 chmod 命令传递 3--- 即可





## chattr命令

chattr 命令，专门用来修改文件或目录的隐藏属性，只有 root 用户可以使用



命令：

```sh
chattr [+-=] [属性] 文件或目录名
```



\+ 表示给文件或目录添加属性，- 表示移除文件或目录拥有的某些属性，= 表示给文件或目录设定一些属性。



| 属性选项 |                             功能                             |
| :------: | :----------------------------------------------------------: |
|    i     | 如果对文件设置 i 属性，那么不允许对文件进行删除、改名，也不能添加和修改数据； 如果对目录设置 i 属性，那么只能修改目录下文件中的数据，但不允许建立和删除文件； |
|    a     | 如果对文件设置 a 属性，那么只能在文件中増加数据，但是不能删除和修改数据； 如果对目录设置 a 属性，那么只允许在目录中建立和修改文件，但是不允许删除文件； |
|    u     | 设置此属性的文件或目录，在删除时，其内容会被保存，以保证后期能够恢复，常用来防止意外删除文件或目录。 |
|    s     | 和 u 相反，删除文件或目录时，会被彻底删除（直接从硬盘上删除，然后用 0 填充所占用的区域），不可恢复。 |





给文件赋予 i 属性：

```sh
mao@ubuntu:~/桌面$ touch test.txt
mao@ubuntu:~/桌面$ ls -l
总用量 76
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao     0 7月   5 06:11 test.txt
mao@ubuntu:~/桌面$ sudo chattr +i test.txt
[sudo] mao 的密码： 
mao@ubuntu:~/桌面$ ls -l
总用量 76
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rwxrwxr-x 1 mao mao    20 7月   2 04:38 2.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao     0 7月   5 06:11 test.txt
mao@ubuntu:~/桌面$ 
```



修改：

```sh
mao@ubuntu:~/桌面$ echo 123 >> test.txt
bash: test.txt: 不允许的操作
mao@ubuntu:~/桌面$ sudo echo 123 >> test.txt
bash: test.txt: 不允许的操作
mao@ubuntu:~/桌面$ 
```



删除：

```sh
mao@ubuntu:~/桌面$ rm -rf test.txt
rm: 无法删除 'test.txt': 不允许的操作
mao@ubuntu:~/桌面$ 
```



移除：

```sh
sudo chattr -i test.txt
```

```sh
mao@ubuntu:~/桌面$ sudo chattr -i test.txt
mao@ubuntu:~/桌面$ 
```



修改：

```sh
ao@ubuntu:~/桌面$ echo 123 >> test.txt
mao@ubuntu:~/桌面$ cat test.txt
123
mao@ubuntu:~/桌面$ 
```





## lsattr命令

**lsattr 命令，用于显示文件或目录的隐藏属性**



命令：

```sh
lsattr [选项] 文件或目录名
```



选项：

- -a：后面不带文件或目录名，表示显示所有文件和目录（包括隐藏文件和目录）
- -d：如果目标是目录，只会列出目录本身的隐藏属性，而不会列出所含文件或子目录的隐藏属性信息；
- -R：和 -d 恰好相反，作用于目录时，会连同子目录的隐藏信息数据也一并显示出来。





查看刚才的文件：

```sh
mao@ubuntu:~/桌面$ lsattr test.txt
--------------e----- test.txt
mao@ubuntu:~/桌面$ 
```

添加权限：

```sh
mao@ubuntu:~/桌面$ sudo chattr +i test.txt
mao@ubuntu:~/桌面$ 
```

再次查看：

```sh
mao@ubuntu:~/桌面$ lsattr test.txt
----i---------e----- test.txt
mao@ubuntu:~/桌面$ 
```



查看目录：

```sh
mao@ubuntu:~/桌面$ lsattr ./
--------------e----- ./linux_file.c
--------------e----- ./filea.c
--------------e----- ./main.c
--------------e----- ./main.h
--------------e----- ./English_early_education_machine_input.c
--------------e----- ./a.c
--------------e----- ./1.txt
--------------e----- ./a.out
--------------e----- ./func1.c
--------------e----- ./func2.c
----i---------e----- ./test.txt
--------------e----- ./2.txt
mao@ubuntu:~/桌面$ 
```





## sudo命令



使用 su 命令可以让普通用户切换到 root 身份去执行某些特权命令，但存在一些问题：

- 仅仅为了一个特权操作就直接赋予普通用户控制系统的完整权限
- 当多人使用同一台主机时，如果大家都要使用 su 命令切换到 root 身份，那势必就需要 root 的密码，这就导致很多人都知道 root 的密码



考虑到使用 su 命令可能对系统安装造成的隐患，最常见的解决方法是使用 sudo 命令，此命令也可以让你切换至其他用户的身份去执行命令。

相对于使用 su 命令还需要新切换用户的密码，sudo 命令的运行只需要知道自己的密码即可



命令：

```sh
sudo [-b] [-u 新使用者账号] 要执行的命令
```



参数：

- -b ：将后续的命令放到背景中让系统自行运行，不对当前的 shell 环境产生影响。
- -u ：后面可以接欲切换的用户名，若无此项则代表切换身份为 root 。
- -l：此选项的用法为 sudo -l，用于显示当前用户可以用 sudo 执行哪些命令。
- -i：登录到root用户



```sh
mao@ubuntu:~/桌面$ sudo -i
root@ubuntu:~# pwd
/root
root@ubuntu:~# ls -l
总用量 4
drwxr-xr-x 3 root root 4096 10月 15  2021 snap
root@ubuntu:~# exit
注销
mao@ubuntu:~/桌面$ 
```













# 文件系统管理

## 文件系统

Windows 98 以前的微软操作系统使用 FAT(FAT16)文件系统，Windows 2000 以后的版本使用 NTFS 文件系统，而 Linux 的正统文件系统是 Ext2。早期的 Linux 使用 Ext2 文件系统格式，CentOS 5.x 默认使用 Ext3，CentOS 6.x 默认使用 Ext4，而目前最新的 CentOS 7.x 默认使用 xfs 格式。

Ext4 是 Ext3(Ext2) 文件系统的升级版，在性能、伸缩性和可靠性方面进行了大量改进，变化可以说是翻天覆地的：

- 向下兼容 Ext3；
- 最大 1EB 文件系统和 16TB 文件；
- 无限数量子目录；
- Extents 连续数据块概念；
- 多块分配、延迟分配、持久预分配；
- 快速 FSCK、日志校验、无日志模式、在线碎片整理、inode 增强、默认启用 barrier 等



Linux 系统能够支持的文件系统非常多，除 Linux 默认文件系统 Ext2、Ext3 和 Ext4 之外，还能支持 fat16、fat32、NTFS(需要重新编译内核)等 Windows 文件系统。也就是说，Linux 可以通过挂载的方式使用 Windows 文件系统中的数据。Linux 所能够支持的文件系统在 "/usr/src/kemels/当前系统版本/fs" 目录中(需要在安装时选择)，该目录中的每个子目录都是一个可以识别的文件系统。




| 文件系统 | 描述 |
| :-----: | :----------------------------------------------------------: |
| Ext     | Linux 中最早的文件系统，由于在性能和兼容性上具有很多缺陷，现在已经很少使用 |
| Ext2    | 是 Ext 文件系统的升级版本，Red Hat Linux 7.2 版本以前的系统默认都是 Ext2 文件系统。于 1993 年发布，支持最大 16TB 的分区和最大 2TB 的文件(1TB=1024GB=1024x1024KB) |
| Ext3    | 是 Ext2 文件系统的升级版本，最大的区别就是带日志功能，以便在系统突然停止时提高文件系统的可靠性。支持最大 16TB 的分区和最大 2TB 的文件 |
| Ext4    | 是 Ext3 文件系统的升级版。Ext4 在性能、伸缩性和可靠性方面进行了大量改进。Ext4 的变化可以说是翻天覆地的，比如向下兼容 Ext3、最大 1EB 文件系统和 16TB 文件、无限数量子目录、Extents 连续数据块 概念、多块分配、延迟分配、持久预分配、快速 FSCK、日志校验、无日志模式、在线碎片整理、inode 增强、默认启用 barrier 等。它是 CentOS 6.3 的默认文件系统 |
| xfs     | 被业界称为最先进、最具有可升级性的文件系统技术，由 SGI 公司设计，目前最新的 CentOS 7 版本默认使用的就是此文件系统。 |
| swap    | swap 是 Linux 中用于交换分区的文件系统(类似于 Windows 中的虚拟内存)，当内存不够用时，使用交换分区暂时替代内存。一般大小为内存的 2 倍，但是不要超过 2GB。它是 Linux 的必需分区 |
| NFS     | NFS 是网络文件系统(Network File System)的缩写，是用来实现不同主机之间文件共享的一种网络服务，本地主机可以通过挂载的方式使用远程共享的资源 |
| iso9660 | 光盘的标准文件系统。Linux 要想使用光盘，必须支持 iso9660 文件系统 |
| fat     | 就是 Windows 下的 fatl6 文件系统，在 Linux 中识别为 fat      |
| vfat    | 就是 Windows 下的 fat32 文件系统，在 Linux 中识别为 vfat。支持最大 32GB 的分区和最大 4GB 的文件 |
| NTFS    | 就是 Windows 下的 NTFS 文件系统，不过 Linux 默认是不能识别 NTFS 文件系统的，如果需要识别，则需要重新编译内核才能支持。它比 fat32 文件系统更加安全，速度更快，支持最大 2TB 的分区和最大 64GB 的文件 |
| ufs     | Sun 公司的操作系统 Solaris 和 SunOS 所采用的文件系统         |
| proc    | Linux 中基于内存的虚拟文件系统，用来管理内存存储目录 /proc   |
| sysfs   | 和 proc —样，也是基于内存的虚拟文件系统，用来管理内存存储目录 /sysfs |
| tmpfs   | 也是一种基于内存的虚拟文件系统，不过也可以使用 swap 交换分区 |







## 识别硬盘设备和硬盘分区

Linux 系统初始化时，会根据 MBR 来识别硬盘设备。

MBR，全称 Master Boot Record，可译为硬盘主引导记录，占据硬盘 0 磁道的第一个扇区。MBR 中，包括用来载入操作系统的可执行代码，实际上，此可执行代码就是 MBR 中前 446 个字节的 boot loader 程序（引导加载程序），而在 boot loader 程序之后的 64 个（16×4）字节的空间，就是存储的分区表（Partition table）相关信息。



在分区表（Partition table）中，主要存储的值息包括分区号（Partition id）、分区的起始磁柱和分区的磁柱数量。所以 Linux 操作系统在初始化时就可以根据分区表中以上 3 种信息来识别硬盘设备。其中，常见的分区号如下：

- 0x5（或 0xf）：可扩展分区（Extended partition）。
- 0x82：Linux 交换区（Swap partition）。
- 0x83：普通 Linux 分区（Linux partition）。
- 0x8e：Linux 逻辑卷管理分区（Linux LVM partition）。
- 0xfd：Linux 的 RAID 分区（Linux RAID auto partition）。



由于 MBR 留给分区表的磁盘空间只有 64 个字节，而每个分区表的大小为 16 个字节，所以在一个硬盘上最多可以划分出 4 个主分区。如果想要在一个硬盘上划分出 4 个以上的分区时，可以通过在硬盘上先划分出一个可扩展分区的方法来增加额外的分区。



不过，在 Linux 的 Kernel 中所支持的分区数量有如下限制：

- 一个 IDE 的硬盘最多可以使用 63 个分区；
- 一个 SCSI 的硬盘最多可以使用 15 个分区。



为什么要将一个硬盘划分成多个分区，而不是直接使用整个硬盘呢？

1. **方便管理和控制**
   首先，可以将系统中的数据（也包括程序）按不同的应用分成几类，之后将这些不同类型的数据分别存放在不同的磁盘分区中。由于在每个分区上存放的都是类似的数据或程序，这样管理和维护就简单多了。
2. **提高系统的效率**
   给硬盘分区，可以直接缩短系统读写磁盘时磁头移动的距离，也就是说，缩小了磁头搜寻的范围；反之，如果不使用分区，每次在硬盘上搜寻信息时可能要搜寻整个硬盘，所以速度会很慢。另外，硬盘分区也可以减轻碎片（文件不连续存放）所造成的系统效率下降的问题。
3. **使用磁盘配额的功能限制用户使用的磁盘量**
   由于限制用户使用磁盘配额的功能，只能在分区一级上使用，所以，为了限制用户使用磁盘的总量，防止用户浪费磁盘空间（甚至将磁盘空间耗光），最好将磁盘先分区，然后在分配给一般用户。
4. **便于备份和恢复**
   硬盘分区后，就可以只对所需的分区进行备份和恢复操作，这样的话，备份和恢复的数据量会大大地下降，而且也更简单和方便。





## df 命令

df 命令，用于**显示 Linux 系统中各文件系统的硬盘使用情况**，包括文件系统所在硬盘分区的总容量、已使用的容量、剩余容量等



整个文件系统有关的数据，都保存在 Super block（超级块）中，而 df 命令主要读取的数据几乎都针对的是整个文件系统，所以 df 命令主要是从各文件系统的 Super block 中读取数据



命令：

```sh
df [选项] [目录或文件名]
```



| 选项 |                             作用                             |
| :--: | :----------------------------------------------------------: |
|  -a  | 显示所有文件系统信息，包括系统特有的 /proc、/sysfs 等文件系统； |
|  -m  |                    以 MB 为单位显示容量；                    |
|  -k  |           以 KB 为单位显示容量，默认以 KB 为单位；           |
|  -h  |       使用人们习惯的 KB、MB 或 GB 等单位自行显示容量；       |
|  -T  |                  显示该分区的文件系统名称；                  |
|  -i  |      不用硬盘容量显示，而是以含有 inode 的数量来显示。       |



```sh
PS C:\Users\mao\Desktop> docker start -i centos
[root@889e0484bdd2 /]# df
Filesystem     1K-blocks    Used Available Use% Mounted on
overlay        263174212 5077344 244658712   3% /
tmpfs              65536       0     65536   0% /dev
tmpfs            6514324       0   6514324   0% /sys/fs/cgroup
shm                65536       0     65536   0% /dev/shm
/dev/sdc       263174212 5077344 244658712   3% /etc/hosts
tmpfs            6514324       0   6514324   0% /proc/acpi
tmpfs            6514324       0   6514324   0% /sys/firmware
[root@889e0484bdd2 /]#
```



- Filesystem：表示该文件系统位于哪个分区，因此该列显示的是设备名称；
- 1K-blocks：此列表示文件系统的总大小，默认以 KB 为单位；
- Used：表示用掉的硬盘空间大小；
- Available：表示剩余的硬盘空间大小；
- Use%：硬盘空间使用率。如果使用率高达 90% 以上，就需要额外注意，因为容量不足，会严重影响系统的正常运行；
- Mounted on：文件系统的挂载点，也就是硬盘挂载的目录位置。



```sh
[root@889e0484bdd2 /]# df -k
Filesystem     1K-blocks    Used Available Use% Mounted on
overlay        263174212 5077348 244658708   3% /
tmpfs              65536       0     65536   0% /dev
tmpfs            6514324       0   6514324   0% /sys/fs/cgroup
shm                65536       0     65536   0% /dev/shm
/dev/sdc       263174212 5077348 244658708   3% /etc/hosts
tmpfs            6514324       0   6514324   0% /proc/acpi
tmpfs            6514324       0   6514324   0% /sys/firmware
[root@889e0484bdd2 /]# df -m
Filesystem     1M-blocks  Used Available Use% Mounted on
overlay           257007  4959    238925   3% /
tmpfs                 64     0        64   0% /dev
tmpfs               6362     0      6362   0% /sys/fs/cgroup
shm                   64     0        64   0% /dev/shm
/dev/sdc          257007  4959    238925   3% /etc/hosts
tmpfs               6362     0      6362   0% /proc/acpi
tmpfs               6362     0      6362   0% /sys/firmware
[root@889e0484bdd2 /]#
```

```sh
[root@889e0484bdd2 /]# df -h
Filesystem      Size  Used Avail Use% Mounted on
overlay         251G  4.9G  234G   3% /
tmpfs            64M     0   64M   0% /dev
tmpfs           6.3G     0  6.3G   0% /sys/fs/cgroup
shm              64M     0   64M   0% /dev/shm
/dev/sdc        251G  4.9G  234G   3% /etc/hosts
tmpfs           6.3G     0  6.3G   0% /proc/acpi
tmpfs           6.3G     0  6.3G   0% /sys/firmware
[root@889e0484bdd2 /]#
```

```sh
[root@889e0484bdd2 /]# df -aT
Filesystem     Type    1K-blocks    Used Available Use% Mounted on
overlay        overlay 263174212 5077352 244658704   3% /
proc           proc            0       0         0    - /proc
tmpfs          tmpfs       65536       0     65536   0% /dev
devpts         devpts          0       0         0    - /dev/pts
sysfs          sysfs           0       0         0    - /sys
tmpfs          tmpfs     6514324       0   6514324   0% /sys/fs/cgroup
cpuset         cgroup          0       0         0    - /sys/fs/cgroup/cpuset
cpu            cgroup          0       0         0    - /sys/fs/cgroup/cpu
cpuacct        cgroup          0       0         0    - /sys/fs/cgroup/cpuacct
blkio          cgroup          0       0         0    - /sys/fs/cgroup/blkio
memory         cgroup          0       0         0    - /sys/fs/cgroup/memory
devices        cgroup          0       0         0    - /sys/fs/cgroup/devices
freezer        cgroup          0       0         0    - /sys/fs/cgroup/freezer
net_cls        cgroup          0       0         0    - /sys/fs/cgroup/net_cls
perf_event     cgroup          0       0         0    - /sys/fs/cgroup/perf_event
net_prio       cgroup          0       0         0    - /sys/fs/cgroup/net_prio
hugetlb        cgroup          0       0         0    - /sys/fs/cgroup/hugetlb
pids           cgroup          0       0         0    - /sys/fs/cgroup/pids
rdma           cgroup          0       0         0    - /sys/fs/cgroup/rdma
cgroup         cgroup          0       0         0    - /sys/fs/cgroup/systemd
mqueue         mqueue          0       0         0    - /dev/mqueue
shm            tmpfs       65536       0     65536   0% /dev/shm
/dev/sdc       ext4    263174212 5077352 244658704   3% /etc/resolv.conf
/dev/sdc       ext4    263174212 5077352 244658704   3% /etc/hostname
/dev/sdc       ext4    263174212 5077352 244658704   3% /etc/hosts
devpts         devpts          0       0         0    - /dev/console
proc           proc            0       0         0    - /proc/bus
proc           proc            0       0         0    - /proc/fs
proc           proc            0       0         0    - /proc/irq
proc           proc            0       0         0    - /proc/sys
tmpfs          tmpfs     6514324       0   6514324   0% /proc/acpi
tmpfs          tmpfs       65536       0     65536   0% /proc/kcore
tmpfs          tmpfs       65536       0     65536   0% /proc/keys
tmpfs          tmpfs       65536       0     65536   0% /proc/timer_list
tmpfs          tmpfs       65536       0     65536   0% /proc/sched_debug
tmpfs          tmpfs     6514324       0   6514324   0% /sys/firmware
[root@889e0484bdd2 /]#
```

```sh
[root@889e0484bdd2 /]# df -h /etc
Filesystem      Size  Used Avail Use% Mounted on
overlay         251G  4.9G  234G   3% /
[root@889e0484bdd2 /]#
```





## du命令

du命令用于**统计目录或文件所占磁盘空间大小**



命令：

```sh
du [选项] [目录或文件名]
```



选项：

- -a：显示每个子文件的磁盘占用量。默认只统计子目录的磁盘占用量
- -h：使用习惯单位显示磁盘占用量，如 KB、MB 或 GB 等；
- -s：统计总磁盘占用量，而不列出子目录和子文件的磁盘占用量



```sh
mao@ubuntu:~/桌面$ du -h -a
4.0K	./linux_file.c
12K	./.swk
12K	./.file.txt.swo
4.0K	./.modules.order.cmd
4.0K	./filea.c
4.0K	./main.c
12K	./.swn
4.0K	./main.h
12K	./English_early_education_machine_input.c
32K	./.hello.o.cmd
12K	./a.c
4.0K	./1.txt
4.0K	./.hello.mod.cmd
20K	./a.out
32K	./.hello.mod.o.cmd
12K	./.file.txt.swp
12K	./.swp
4.0K	./.Module.symvers.cmd
4.0K	./func1.c
4.0K	./func2.c
4.0K	./test.txt
12K	./.swo
12K	./.myfile.txt.swp
12K	./.file.c.swp
12K	./.swl
12K	./.swm
12K	./.swj
16K	./.a.c.swp
4.0K	./.hello.ko.cmd
4.0K	./2.txt
312K	.
mao@ubuntu:~/桌面$ 
```







## mount命令

**挂载Linux系统外的文件**



mount 命令的常用格式有以下几种：

```sh
mount [-l]
```

-l 选项，会额外显示出卷标名称



```sh
mount -a
```

-a 选项的含义是自动检查 /etc/fstab 文件中有无疏漏被挂载的设备文件，如果有，则进行自动挂载操作。



```sh
mount [-t 系统类型] [-L 卷标名] [-o 特殊选项] [-n] 设备文件名 挂载点
```



参数：

- -t 系统类型：指定欲挂载的文件系统类型。Linux 常见的支持类型有 EXT2、EXT3、EXT4、iso9660（光盘格式）、vfat、reiserfs 等。如果不指定具体类型，挂载时 Linux 会自动检测。
- -L 卷标名：除了使用设备文件名之外，还可以利用文件系统的卷标名称进行挂载。
- -n：在默认情况下，系统会将实际挂载的情况实时写入 /etc/mtab 文件中，但在某些场景下（例如单人维护模式），为了避免出现问题，会刻意不写入，此时就需要使用这个选项；
- -o 特殊选项：可以指定挂载的额外选项，比如读写权限、同步/异步等，如果不指定，则使用默认值（defaults）



|    选项     |                             功能                             |
| :---------: | :----------------------------------------------------------: |
|    rw/ro    | 是否对挂载的文件系统拥有读写权限，rw 为默认值，表示拥有读写权限；ro 表示只读权限。 |
| async/sync  | 此文件系统是否使用同步写入（sync）或异步（async）的内存机制，默认为异步 async。 |
|  dev/nodev  | 是否允许从该文件系统的 block 文件中提取数据，为了保证数据安装，默认是 nodev。 |
| auto/noauto | 是否允许此文件系统被以 mount -a 的方式进行自动挂载，默认是 auto。 |
| suid/nosuid |   设定文件系统是否拥有 SetUID 和 SetGID 权限，默认是拥有。   |
| exec/noexec |     设定在文件系统中是否允许执行可执行文件，默认是允许。     |
| user/nouser | 设定此文件系统是否允许让普通用户使用 mount 执行实现挂载，默认是不允许（nouser），仅有 root 可以。 |
|  defaults   | 定义默认值，相当于 rw、suid、dev、exec、auto、nouser、async 这 7 个选项。 |
|   remount   |     重新挂载已挂载的文件系统，一般用于指定修改特殊权限。     |





```sh
mao@ubuntu:~/桌面$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
udev on /dev type devtmpfs (rw,nosuid,noexec,relatime,size=1967912k,nr_inodes=491978,mode=755,inode64)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,noexec,relatime,size=399508k,mode=755,inode64)
/dev/sda5 on / type ext4 (rw,relatime,errors=remount-ro)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,inode64)
tmpfs on /run/lock type tmpfs (rw,nosuid,nodev,noexec,relatime,size=5120k,inode64)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,mode=755,inode64)
cgroup2 on /sys/fs/cgroup/unified type cgroup2 (rw,nosuid,nodev,noexec,relatime,nsdelegate)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
none on /sys/fs/bpf type bpf (rw,nosuid,nodev,noexec,relatime,mode=700)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/net_cls,net_prio type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls,net_prio)
cgroup on /sys/fs/cgroup/rdma type cgroup (rw,nosuid,nodev,noexec,relatime,rdma)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/pids type cgroup (rw,nosuid,nodev,noexec,relatime,pids)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpu,cpuacct)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=28,pgrp=1,timeout=0,minproto=5,maxproto=5,direct,pipe_ino=16034)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,pagesize=2M)
mqueue on /dev/mqueue type mqueue (rw,nosuid,nodev,noexec,relatime)
debugfs on /sys/kernel/debug type debugfs (rw,nosuid,nodev,noexec,relatime)
tracefs on /sys/kernel/tracing type tracefs (rw,nosuid,nodev,noexec,relatime)
fusectl on /sys/fs/fuse/connections type fusectl (rw,nosuid,nodev,noexec,relatime)
configfs on /sys/kernel/config type configfs (rw,nosuid,nodev,noexec,relatime)
vmware-vmblock on /run/vmblock-fuse type fuse.vmware-vmblock (rw,relatime,user_id=0,group_id=0,default_permissions,allow_other)
/var/lib/snapd/snaps/core18_2253.snap on /snap/core18/2253 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/core18_2409.snap on /snap/core18/2409 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/core20_1518.snap on /snap/core20/1518 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gnome-3-34-1804_72.snap on /snap/gnome-3-34-1804/72 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/bare_5.snap on /snap/bare/5 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gtk-common-themes_1519.snap on /snap/gtk-common-themes/1519 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gnome-3-38-2004_112.snap on /snap/gnome-3-38-2004/112 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gtk-common-themes_1535.snap on /snap/gtk-common-themes/1535 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/snapd_16010.snap on /snap/snapd/16010 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/snap-store_547.snap on /snap/snap-store/547 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/core20_1270.snap on /snap/core20/1270 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gnome-3-38-2004_87.snap on /snap/gnome-3-38-2004/87 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gnome-3-34-1804_77.snap on /snap/gnome-3-34-1804/77 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/snap-store_558.snap on /snap/snap-store/558 type squashfs (ro,nodev,relatime,x-gdu.hide)
/dev/sda1 on /boot/efi type vfat (rw,relatime,fmask=0077,dmask=0077,codepage=437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,size=399508k,mode=700,uid=1000,gid=1000,inode64)
gvfsd-fuse on /run/user/1000/gvfs type fuse.gvfsd-fuse (rw,nosuid,nodev,relatime,user_id=1000,group_id=1000)
mao@ubuntu:~/桌面$ 
```







## 挂载光盘

在 Windows 中，如果我们想要使用光盘，只需要将光盘放入光驱即可。但在 Linux 系统中，将光盘放入光驱后，还需要将光盘中的文件系统手动挂载到 Linux 系统中

同样，用完光盘后，Windows 系统可以直接弹出光驱并取出光盘，但 Linux 系统不行，必须先卸载才能取出光盘



建立挂载点：

```sh
mkdir/mnt/cdrom/
```



挂载光盘：

```sh
mount -t iso9660 /dev/cdrom /mnt/cdrom/
```

或者：

```sh
mount /dev/cdrom /mnt/cdrom/
```



光盘的文件系统是 iso9660，不过这个文件系统可以省略不写，系统会自动检测



查看挂载设备：

```sh
mount
```



挂载就是把光驱的设备文件和挂载点连接起来。挂载点 /mnt/cdrom 是我们手工建立的空目录。只要是已经建立的空目录都可以作为挂载点。/dev/cdrom 就是光驱的设备文件名。





## 挂载U盘

挂载 U 盘和挂载光盘的方式是一样的，只不过光盘的设备文件名是固定的（/dev/sr0 或 /dev/cdrom），而 U 盘的设备文件名是在插入 U 盘后系统自动分配的。



通过使用 fdisk 命令，即可查看到 U 盘的设备文件名：

```sh
fdisk -l
```



```sh
mao@ubuntu:~/桌面$ sudo fdisk -l
[sudo] mao 的密码： 
Disk /dev/loop0：4 KiB，4096 字节，8 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop1：55.5 MiB，58183680 字节，113640 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop2：55.55 MiB，58232832 字节，113736 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop3：61.95 MiB，64933888 字节，126824 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop4：219 MiB，229638144 字节，448512 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop5：65.22 MiB，68378624 字节，133552 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop6：91.7 MiB，96141312 字节，187776 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop7：400.82 MiB，420265984 字节，820832 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/sda：15 GiB，16106127360 字节，31457280 个扇区
Disk model: VMware Virtual S
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节
磁盘标签类型：dos
磁盘标识符：0x7b05fa2b

设备       启动    起点     末尾     扇区  大小 Id 类型
/dev/sda1  *       2048  1050623  1048576  512M  b W95 FAT32
/dev/sda2       1052670 31455231 30402562 14.5G  5 扩展
/dev/sda5       1052672 31455231 30402560 14.5G 83 Linux




Disk /dev/loop8：61.93 MiB，64913408 字节，126784 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop9：46.98 MiB，49233920 字节，96160 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop10：50.98 MiB，53432320 字节，104360 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop11：247.93 MiB，259948544 字节，507712 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop12：219 MiB，229638144 字节，448512 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节


Disk /dev/loop13：54.24 MiB，56872960 字节，111080 个扇区
单元：扇区 / 1 * 512 = 512 字节
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节
mao@ubuntu:~/桌面$ 
```



查看到 U 盘的设备文件名，接下来就要创建挂载点：

```sh
mkdir /mnt/usb
```



挂载：

```sh
mount U盘设备文件名 /mnt/usb/
```



访问U盘数据：

```sh
cd /mnt/usb/
```

```sh
ls -l
```





如果出现乱码，是因为 U 盘是 Windows 中保存的数据，而 Windows 中的中文编码格式和 Linux 中的不一致，只需在挂载的时候指定正确的编码格式就可以解决乱码问题：



挂载U盘，指定中文编码格式为UTF-8：

```sh
mount -o iocharset=utf8 U盘设备文件名 /mnt/usb/
```



再次访问U盘数据：

```sh
cd /mnt/usb/
```

```sh
ls -l
```



Linux 默认是不支持 NTFS 文件系统的，所以默认是不能挂载 NTFS 格式的移动硬盘的。要想让 Linux 支持移动硬盘，主要有三种方法：

1. 重新编译内核，加入 ntfs 模块，然后安装 ntfs 模块即可
2. 不自己编译内核，而是下载已经编译好的内核，直接安装即可
3. 安装 NTFS 文件系统的第三方插件，也可以支持 NTFS 文件系统





## umount命令

umount 命令**用于卸载已经挂载的硬件设备**



命令：

```sh
umount 设备文件名或挂载点
```



卸载命令后面既可以加设备文件名，也可以加挂载点，不过只能二选一





## fsck命令

fsck 命令**用于检查文件系统并尝试修复出现的错误**



命令：

```sh
fsck [选项] 分区设备文件名
```



|      选项       |                             功能                             |
| :-------------: | :----------------------------------------------------------: |
|       -a        |             自动修复文件系统，没有任何提示信息。             |
|       -r        | 采取互动的修复模式，在修改文件前会进行询问，让用户得以确认并决定处理方式。 |
|   -A（大写）    | 按照 /etc/fstab 配置文件的内容，检查文件内罗列的全部文件系统。 |
| -t 文件系统类型 |                  指定要检查的文件系统类型。                  |
|   -C（大写）    |                    显示检查分区的进度条。                    |
|       -f        | 强制检测，一般 fsck 命令如果没有发现分区有问题，则是不会检测的。如果强制检测，那么不管是否发现问题，都会检测。 |
|       -y        |    自动修复，和 -a 作用一致，不过有些文件系统只支持 -y。     |



在使用 fsck 命令修改某文件系统时，这个文件系统对应的磁盘分区一定要处于卸载状态，磁盘分区在挂载状态下进行修复是非常不安全的，数据可能会遭到破坏，也有可能会损坏磁盘

```sh
mao@ubuntu:~/桌面$ fsck -r /dev/sda5
fsck，来自 util-linux 2.34
e2fsck 1.45.5 (07-Jan-2020)
/dev/sda5 已挂载。



警告！！！该文件系统已被挂载。如果你继续操作将会
使文件系统遭受 *** 严重损坏 ***！


你真的想要继续吗<n>? 否
检查被中止。
/dev/sda5: status 0, rss 3528, real 18.310207, user 0.003392, sys 0.000000
mao@ubuntu:~/桌面$ o
```





## dumpe2fs命令

使用 dumpe2fs 命令可以查看文件系统的详细信息

命令：

```sh
dumpe2fs [-h] 文件名
```



-h 选项的含义是仅列出 superblock（超级块）的数据信息



```sh
mao@ubuntu:~/桌面$ df
文件系统          1K-块    已用    可用 已用% 挂载点
udev            1967912       0 1967912    0% /dev
tmpfs            399508    1856  397652    1% /run
/dev/sda5      14897128 9137592 4983088   65% /
tmpfs           1997540       0 1997540    0% /dev/shm
tmpfs              5120       4    5116    1% /run/lock
tmpfs           1997540       0 1997540    0% /sys/fs/cgroup
/dev/loop1        56832   56832       0  100% /snap/core18/2253
/dev/loop2        56960   56960       0  100% /snap/core18/2409
/dev/loop3        63488   63488       0  100% /snap/core20/1518
/dev/loop4       224256  224256       0  100% /snap/gnome-3-34-1804/72
/dev/loop0          128     128       0  100% /snap/bare/5
/dev/loop5        66816   66816       0  100% /snap/gtk-common-themes/1519
/dev/loop7       410496  410496       0  100% /snap/gnome-3-38-2004/112
/dev/loop6        93952   93952       0  100% /snap/gtk-common-themes/1535
/dev/loop9        48128   48128       0  100% /snap/snapd/16010
/dev/loop10       52224   52224       0  100% /snap/snap-store/547
/dev/loop8        63488   63488       0  100% /snap/core20/1270
/dev/loop11      253952  253952       0  100% /snap/gnome-3-38-2004/87
/dev/loop12      224256  224256       0  100% /snap/gnome-3-34-1804/77
/dev/loop13       55552   55552       0  100% /snap/snap-store/558
/dev/sda1        523248       4  523244    1% /boot/efi
tmpfs            399508      24  399484    1% /run/user/1000
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ sudo dumpe2fs -h /dev/sda5
dumpe2fs 1.45.5 (07-Jan-2020)
Filesystem volume name:   <none>
Last mounted on:          /
Filesystem UUID:          f016fec7-baa2-4d84-99bb-4b8bde2ff82c
Filesystem magic number:  0xEF53
Filesystem revision #:    1 (dynamic)
Filesystem features:      has_journal ext_attr resize_inode dir_index filetype needs_recovery extent 64bit flex_bg sparse_super large_file huge_file dir_nlink extra_isize metadata_csum
Filesystem flags:         signed_directory_hash 
Default mount options:    user_xattr acl
Filesystem state:         clean
Errors behavior:          Continue
Filesystem OS type:       Linux
Inode count:              950272
Block count:              3800320
Reserved block count:     190016
Free blocks:              1439838
Free inodes:              736751
First block:              0
Block size:               4096
Fragment size:            4096
Group descriptor size:    64
Reserved GDT blocks:      1024
Blocks per group:         32768
Fragments per group:      32768
Inodes per group:         8192
Inode blocks per group:   512
Flex block group size:    16
Filesystem created:       Fri Oct 15 04:10:36 2021
Last mount time:          Wed Jul  6 04:43:56 2022
Last write time:          Wed Jul  6 04:43:56 2022
Mount count:              25
Maximum mount count:      -1
Last checked:             Fri Oct 15 04:10:36 2021
Check interval:           0 (<none>)
Lifetime writes:          12 GB
Reserved blocks uid:      0 (user root)
Reserved blocks gid:      0 (group root)
First inode:              11
Inode size:	          256
Required extra isize:     32
Desired extra isize:      32
Journal inode:            8
First orphan inode:       266120
Default directory hash:   half_md4
Directory Hash Seed:      321309c4-e1c0-4497-8c62-6b72524951b4
Journal backup:           inode blocks
Checksum type:            crc32c
Checksum:                 0x048c4aba
Journal features:         journal_incompat_revoke journal_64bit journal_checksum_v3
Journal size:             64M
Journal length:           16384
Journal sequence:         0x000059e5
Journal start:            1
Journal checksum type:    crc32c
Journal checksum:         0x16c0ab38

mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ sudo dumpe2fs /dev/sda5
dumpe2fs 1.45.5 (07-Jan-2020)
Filesystem volume name:   <none>
Last mounted on:          /
Filesystem UUID:          f016fec7-baa2-4d84-99bb-4b8bde2ff82c
Filesystem magic number:  0xEF53
Filesystem revision #:    1 (dynamic)
Filesystem features:      has_journal ext_attr resize_inode dir_index filetype needs_recovery extent 64bit flex_bg sparse_super large_file huge_file dir_nlink extra_isize metadata_csum
Filesystem flags:         signed_directory_hash 
Default mount options:    user_xattr acl
Filesystem state:         clean
Errors behavior:          Continue
Filesystem OS type:       Linux
Inode count:              950272
Block count:              3800320
Reserved block count:     190016
Free blocks:              1439838
Free inodes:              736751
First block:              0
Block size:               4096
Fragment size:            4096
Group descriptor size:    64
Reserved GDT blocks:      1024
Blocks per group:         32768
Fragments per group:      32768
Inodes per group:         8192
Inode blocks per group:   512
Flex block group size:    16
Filesystem created:       Fri Oct 15 04:10:36 2021
Last mount time:          Wed Jul  6 04:43:56 2022
Last write time:          Wed Jul  6 04:43:56 2022
Mount count:              25
Maximum mount count:      -1
Last checked:             Fri Oct 15 04:10:36 2021
Check interval:           0 (<none>)
Lifetime writes:          12 GB
Reserved blocks uid:      0 (user root)
Reserved blocks gid:      0 (group root)
First inode:              11
Inode size:	          256
Required extra isize:     32
Desired extra isize:      32
Journal inode:            8
First orphan inode:       266120
Default directory hash:   half_md4
Directory Hash Seed:      321309c4-e1c0-4497-8c62-6b72524951b4
Journal backup:           inode blocks
Checksum type:            crc32c
Checksum:                 0x048c4aba
Journal features:         journal_incompat_revoke journal_64bit journal_checksum_v3
Journal size:             64M
Journal length:           16384
Journal sequence:         0x000059e5
Journal start:            1
Journal checksum type:    crc32c
Journal checksum:         0x16c0ab38


组 0：(块 0-32767) 校验值 0xcee9 [ITABLE_ZEROED]
  主 超级块位于 0，组描述符位于 1-2
  保留的GDT块位于 3-1026
  块位图位于 1027 (+1027)，校验值 0x547afb22
  Inode 位图位于 1043 (+1043)，校验值 0xddc327b2
  Inode表位于 1059-1570 (+1059)
  4709 个可用 块，0 个可用inode，1359 个目录 
  可用块数： 15092-15491, 20268-24575, 32767
  可用inode数： 
组 1：(块 32768-65535) 校验值 0xec00 [ITABLE_ZEROED]
  备份 超级块位于 32768，组描述符位于 32769-32770
  保留的GDT块位于 32771-33794
  块位图位于 1028 (bg #0 + 1028)，校验值 0x3020cafd
  Inode 位图位于 1044 (bg #0 + 1044)，校验值 0xddc327b2
  Inode表位于 1571-2082 (bg #0 + 1571)
  1020 个可用 块，0 个可用inode，1893 个目录 
  可用块数： 33795-33813, 33815-34815
  可用inode数： 
组 2：(块 65536-98303) 校验值 0x673d [ITABLE_ZEROED]
  块位图位于 1029 (bg #0 + 1029)，校验值 0x3253976a
  Inode 位图位于 1045 (bg #0 + 1045)，校验值 0x6d6c964e
  Inode表位于 2083-2594 (bg #0 + 2083)
  0 个可用 块，5711 个可用inode，535 个目录 ，5708个未使用的inodes
  可用块数： 
  可用inode数： 18866-24576
组 3：(块 98304-131071) 校验值 0xeba3 [INODE_UNINIT, ITABLE_ZEROED]
  备份 超级块位于 98304，组描述符位于 98305-98306
  保留的GDT块位于 98307-99330
  块位图位于 1030 (bg #0 + 1030)，校验值 0x18e68c76
  Inode 位图位于 1046 (bg #0 + 1046)，校验值 0x00000000
  Inode表位于 2595-3106 (bg #0 + 2595)
  1021 个可用 块，8192 个可用inode，0 个目录 ，8192个未使用的inodes
  可用块数： 99331-100351
  可用inode数： 24577-32768
...
...
...
组 32：(块 1048576-1081343) 校验值 0x4240 [ITABLE_ZEROED]
  块位图位于 1048576 (+0)，校验值 0xca5409f7
  Inode 位图位于 1048592 (+16)，校验值 0x11f848db
  Inode表位于 1048608-1049119 (+32)
  21514 个可用 块，29 个可用inode，1020 个目录 
  可用块数： 1057319-1057320, 1057323, 1057765, 1057783, 1057857, 1057873, 1057882, 1057896-1057897, 1057998, 1058066, 1058127, 1058144-1058157, 1058160-1058239, 1058256-1058319, 1058574-1058595, 1058597, 1058678-1058703, 1058824-1058913, 1059989-1059991, 1059999, 1060144-1081343
  可用inode数： 266081-266082, 266139, 267991, 267994-267995, 267997-267998, 268007, 269225, 269634-269639, 269652-269654, 269657, 269686, 269693, 269712-269717, 269726
组 33：(块 1081344-1114111) 校验值 0x5e26 [ITABLE_ZEROED]
  块位图位于 1048577 (bg #32 + 1)，校验值 0x9c4a2d8c
  Inode 位图位于 1048593 (bg #32 + 17)，校验值 0x320510cc
  Inode表位于 1049120-1049631 (bg #32 + 544)
  3380 个可用 块，1386 个可用inode，412 个目录 
  可用块数： 1086942-1086943, 1087360-1087423, 1087454-1087455, 1087584-1087631, 1087674-1087675, 1087744-1087751, 1087837, 1087846-1087847, 1087852-1087855, 1087872-1087903, 1087920-1087922, 1087931-1087939, 1087965-1087967, 1088033-1088037, 1088040-1088047, 1088053, 1088056-1088070, 1088108, 1088110-1088127, 1088164-1088165, 1088176-1088191, 1088218-1088219, 1088246-1088247, 1088252-1088253, 1088270-1088271, 1088284-1088285, 1088308-1088309, 1088312-1088313, 1088327-1088339, 1088346-1088351, 1088354-1088356, 1088364-1088368, 1088374-1088379, 1088395, 1088398-1088399, 1088404-1088417, 1088420-1088423, 1088430-1088436, 1088439-1088451, 1088456-1088472, 1088495-1088500, 1088502-1088511, 1088515-1088517, 1088526-1088532, 1088542-1088545, 1088550-1088560, 1088590-1088619, 1088648-1088701, 1088704-1088729, 1088731, 1088734-1088818, 1088820-1088839, 1088849-1088879, 1088913, 1088916-1088941, 1088950-1088963, 1088965, 1088974-1088975, 1088991-1089008, 1089025-1089037, 1089039, 1089061-1089062, 1089064-1089081, 1089093, 1089099-1089104, 1089106-1089110, 1089112-1089117, 1089134-1089146, 1089148-1089151, 1089169, 1089175-1089182, 1089184-1089195, 1089199, 1089204-1089206, 1089208-1089211, 1089215-1089217, 1089228-1089240, 1089244-1089245, 1089252-1089257, 1089260-1089261, 1089266-1089269, 1089272-1089273, 1089275, 1089278, 1089281, 1089288-1089293, 1089296-1089297, 1089300-1089301, 1089306-1089309, 1089314-1089317, 1089320-1089321, 1089325-1089327, 1089330-1089331, 1089334-1089335, 1089342-1089346, 1089350-1089352, 1089356-1089358, 1089361-1089362, 1089365-1089366, 1089374-1089379, 1089383-1089385, 1089389-1089391, 1089421-1089437, 1089440-1089443, 1089445-1089447, 1089450-1089451, 1089459-1089465, 1089470-1089471, 1089482-1089485, 1089488-1089491, 1089494-1089496, 1089501, 1089508-1089513, 1089517, 1089522-1089527, 1089530-1089531, 1089533, 1089545, 1089548-1089559, 1089563-1089565, 1089572, 1089574-1089577, 1089652-1089655, 1089664-1089690, 1089696-1089731, 1089733-1089803, 1089880-1089941, 1089958-1089974, 1089976, 1089980-1089982, 1089989-1089994, 1089998-1090000, 1090003, 1090010-1090034, 1090036-1090041, 1090075, 1090141-1090157, 1090160-1090193, 1090238-1090239, 1090249-1090278, 1090280-1090289, 1090292-1090298, 1090378-1090379, 1090409-1090438, 1090440-1090476, 1090478-1090488, 1090490-1090495, 1090513, 1090518-1090533, 1090535, 1090542-1090543, 1090568-1090589, 1090725, 1090728-1090827, 1090930-1090931, 1090974-1091085, 1091118-1091138, 1091140-1091146, 1091319, 1091324-1091384, 1091392-1091439, 1091469, 1091472-1091532, 1091538, 1091540-1091543, 1091583-1091613, 1091630-1091644, 1091656-1091663, 1091704-1091711, 1091719-1091725, 1091787-1091819, 1091823-1091845, 1091848-1091851, 1091862-1091863, 1091876-1091881, 1091884-1091893, 1091939-1091941, 1091960-1091991, 1092021, 1092031-1092048, 1092050-1092060, 1092071, 1092082-1092096, 1092105-1092108, 1092110-1092112, 1092114-1092115, 1092117, 1092120, 1092127, 1092139, 1092146-1092162, 1092179, 1092182-1092184, 1092188, 1092190-1092191, 1092194-1092197, 1092200-1092201, 1092211-1092217, 1092241-1092253, 1092256-1092257, 1092310, 1092376-1092413, 1092438-1092450, 1092452-1092453, 1092515-1092546, 1092548-1092556, 1092558-1092559, 1093215, 1093223, 1093242-1093243, 1093254, 1093297-1093300, 1093339, 1093376-1093389, 1093481, 1093500-1093518, 1093529-1093565, 1093567, 1093589-1093591, 1093790-1093791, 1093795, 1093800-1094348, 1094351-1094354, 1094356-1094577, 1094590, 1094592-1094599, 1094776-1094801, 1094968-1094971, 1094974, 1100695, 1101152-1101160, 1101162-1101177, 1101179, 1101184-1101187, 1101196-1101198, 1101200-1101203, 1101251, 1101260-1101300, 1101302-1101305, 1102420-1102423, 1102634-1102635, 1102720-1102768, 1102772-1102783, 1102796-1102799, 1103421-1103423, 1104143, 1104547, 1104671, 1113883-1113893, 1114064-1114071, 1114080-1114103
  可用inode数： 271429-271430, 271578-271579, 271651-271652, 271848, 271851-271853, 271942, 271948, 271954, 272364-272366, 272648, 272730, 276886, 276951, 277157-278019, 278024-278033, 278035-278040, 278042-278528
...
...
...
组 115：(块 3768320-3800319) 校验值 0xed16 [INODE_UNINIT, ITABLE_ZEROED]
  块位图位于 3670019 (bg #112 + 3)，校验值 0xcce1edd2
  Inode 位图位于 3670023 (bg #112 + 7)，校验值 0x00000000
  Inode表位于 3671560-3672071 (bg #112 + 1544)
  32000 个可用 块，8192 个可用inode，0 个目录 ，8192个未使用的inodes
  可用块数： 3768320-3800319
  可用inode数： 942081-950272
mao@ubuntu:~/桌面$ 
```







## fdisk命令

命令用于**给硬盘分区**

在 Linux 中有专门的分区命令 fdisk 和 parted。其中 fdisk 命令较为常用，但不支持大于 2TB 的分区；如果需要支持大于 2TB 的分区，则需要使用 parted 命令



列出系统分区：

```sh
fdisk ~l
```



给硬盘分区：

```sh
fdisk 设备文件名
```



千万不要在当前的硬盘上尝试使用 fdisk，这会完整删除整个系统，一定要再找一块硬盘，或者使用虚拟机



```sh
[root@localhost ~]# fdisk -l
#查询本机可以识别的硬盘和分区
Disk /dev/sda:32.2 GB, 32212254720 bytes
#硬盘文件名和硬盘大小
255 heads, 63 sectors/track, 3916 cylinders
#共255个磁头、63个扇区和3916个柱面
Units = cylinders of 16065 *512 = 8225280 bytes
#每个柱面的大小
Sector size (logical/physical): 512 bytes/512 bytes
#每个扇区的大小
I/O size (minimum/optimal): 512 bytes/512 bytes
Disk identifier: 0x0009e098
Device Boot Start End Blocks ld System
/dev/sda1 * 1 26 204800 83 Linux
Partition 1 does not end on cylinder boundary.
#分区1没有占满硬盘
/dev/sda2 26 281 2048000 82 Linux swap / Solaris
Partition 2 does not end on cylinder boundary
#分区2没有占满硬盘
/dev/sda3 281 3917 29203456 83 Linux
#设备文件名启动分区 起始柱面 终止柱面容量 ID 系统
Disk /dev/sdb: 21.5 GB, 21474836480 bytes #第二个硬盘识别，这个硬盘的大小
255 heads, 63 sectors/track, 2610 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes/512 bytes Disk identifier: 0x00000000
```



- Device：分区的设备文件名。
- Boot：是否为启动引导分区，在这里 /dev/sda1 为启动引导分区。
- Start：起始柱面，代表分区从哪里开始。
- End：终止柱面，代表分区到哪里结束。
- Blocks：分区的大小，单位是 KB。
- id：分区内文件系统的 ID。在 fdisk 命令中，可以 使用 "i" 查看。
- System：分区内安装的系统是什么。



fdisk 可以识别的交互命令：



| 命令 |                            说 明                             |
| :--: | :----------------------------------------------------------: |
|  a   |                        设置可引导标记                        |
|  b   |                      编辑 bsd 磁盘标签                       |
|  c   |                  设置 DOS 操作系统兼容标记                   |
|  d   |                         删除一个分区                         |
|  1   | 显示已知的文件系统类型。82 为 Linux swap 分区，83 为 Linux 分区 |
|  m   |                         显示帮助菜单                         |
|  n   |                           新建分区                           |
|  0   |                     建立空白 DOS 分区表                      |
|  P   |                         显示分区列表                         |
|  q   |                          不保存退出                          |
|  s   |                    新建空白 SUN 磁盘标签                     |
|  t   |                    改变一个分区的系统 ID                     |
|  u   |                       改变显示记录单位                       |
|  V   |                          验证分区表                          |
|  w   |                           保存退出                           |
|  X   |                      附加功能（仅专家）                      |







## 创建逻辑分区

扩展分区是不能被格式化和直接使用的，所以还要在扩展分区内部再建立逻辑分区



```sh
[root@localhost ~]# fdisk /dev/sdb
…省略部分输出…
Command (m for help): n
#建立新分区
Command action
l logical (5 or over)
p primary partition (1-4)
l
#建立逻辑分区
First cylinder (655-2610, default 655):
#不用指定分区号，默认会从5开始分配，所以直接选择起始柱面
#注意：逻辑分区是在扩展分区内部再划分的，所以柱面是和扩展分区重叠的
Using default value 655
Last cylinder, +cylinders or +size{K, M, G} (655-2610, default 2610):+2G
#分配2GB大小
Command (m for help): n
#再建立一个逻辑分区
Command action
l logical (5 or over)
p primary partition (1-4)
l
First cylinder (917-2610, default 917):
Using default value 917
Last cylinder, +cylinders or +size{K, M, G} (917-2610, default 2610):+2G
Command (m for help): p
#查看一下已经建立的分区
Disk /dev/sdb: 21.5GB, 21474836480 bytes
255 heads, 63 sectors/track, 2610 cylinders
Units = cylinders of 16065 *512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes Disk identifier: 0xb4b0720c
Device Boot Start End Blocks id System
/dev/sdb1 1 654
5253223+ 83 Linux
#主分区
/dev/sdb2 655 2610 15711570
5 Extended
#扩展分区
/dev/sdb5 655 916
2104483+ 83 Linux
#逻辑分区 1
/dev/sdb6 917 1178
2104483+ 83 Linux
#逻辑分区2
Command (m for help): w
#保存并退出
The partition table has been altered!
Calling ioctl。to re-read partition table.
Syncing disks.
[root@localhost -]#
```



所有的分区立过程中如果不保存并退出是不会生效的，所以建立错了也没有关系，使用 q 命令不保存退出即可。如果使用了 w 命令，就会保存退出。有时因为系统的分区表正忙，所以需要重新启动系统才能使新的分区表生效。命令如下：

```sh
Command (m for help): w
#保存并退出
The partition table has been altered!
Calling ioctl() to re-read partition table.
WARNING: Re-reading the partition table failed with error 16:
Device or resource busy.
The kernel still uses the old table.
The new table will be used at the next reboot.
#要求重新启动，才能格式化
Syncing disks.
```



重启启动或者执行以下命令：

```sh
partprobe
```







## parted命令

和fdisk命令的效果一样。



命令：

```sh
parted 硬盘设备文件名
```



|             parted交互命令              |                  说 明                   |
| :-------------------------------------: | :--------------------------------------: |
|              check NUMBER               |         做一次简单的文件系统检测         |
| cp [FROM-DEVICE] FROM-NUMBER TO-NUMBER  |         复制文件系统到另一个分区         |
|             help [COMMAND]              |            显示所有的命令帮助            |
|       mklabel,mktable LABEL-TYPE        |        创建新的磁盘卷标（分区表）        |
|           mkfs NUMBER FS-TYPE           |           在分区上建立文件系统           |
|  mkpart PART-TYPE [FS-TYPE] START END   |               创建一个分区               |
|  mkpartfs PART-TYPE FS-TYPE START END   |         创建分区，并建立文件系统         |
|          move NUMBER START END          |                 移动分区                 |
|            name NUMBER NAME             |                给分区命名                |
| print [devices\|free\|list,all\|NUMBER] | 显示分区表、活动设备、空闲空间、所有分区 |
|                  quit                   |                   退出                   |
|            rescue START END             |              修复丢失的分区              |
|         resize NUMBER START END         |               修改分区大小               |
|                rm NUMBER                |                 删除分区                 |
|              select DEVICE              |            选择需要编辑的设备            |
|          set NUMBER FLAG STATE          |               改变分区标记               |
|         toggle [NUMBER [FLAG]]          |             切换分区表的状态             |
|                unit UNIT                |              设置默认的单位              |
|                 Version                 |                 显示版本                 |





## mkfs命令

分区完成后，如果不格式化写入文件系统，则是不能正常使用的。这时就需要使用 mkfs 命令对硬盘分区进行格式化



命令：

```sh
mkfs [-t 文件系统格式] 分区设备文件名
```

-t 文件系统格式：用于指定格式化的文件系统





## mke2fs命令

和mkfs命令一样，但是mke2fs命令可以手动调整分区的默认参数



命令：

```sh
mke2fs [选项] 分区设备文件名
```



|    选项     |                          功能                           |
| :---------: | :-----------------------------------------------------: |
| -t 文件系统 |    指定格式化成哪个文件系统， 如 ext2、ext3、ext4；     |
|   -b 字节   |                   指定 block 的大小；                   |
|   -i 字节   | 指定"字节 inode "的比例，也就是多少字节分配一个 inode； |
|     -j      |           建立带有 ext3 日志功能的文件系统；            |
|  -L 卷标名  |                 给文件系统设置卷标名；                  |





## 虚拟内存和物理内存

* 物理内存就是系统硬件提供的内存大小，是真正的内存。相对于物理内存，在 Linux 下还有一个虚拟内存的概念，虚拟内存是为了满足物理内存的不足而提出的策略，它是利用磁盘空间虚拟出的一块逻辑内存。用作虚拟内存的磁盘空间被称为交换空间（又称 swap 空间）

* 作为物理内存的扩展，Linux 会在物理内存不足时，使用交换分区的虚拟内存，更详细地说，就是内核会将暂时不用的内存块信息写到交换空间，这样一来，物理内存得到了释放，这块内存就可以用于其他目的，当需要用到原始的内容时，这些信息会被重新从交换空间读入物理内存。

* Linux 的内存管理采取的是分页存取机制，为了保证物理内存能得到充分的利用，内核会在适当的时候将物理内存中不经常使用的数据块自动交换到虚拟内存中，而将经常使用的信息保留到物理内存



要了解 Linux 内存运行机制，需要知道下面提到的几个方面：

- 首先，Linux 系统会不时地进行页面交换操作，以保持尽可能多的空闲物理内存，即使并没有什么事情需要内存交换，Linux 也会交换出暂时不用的内存页面，因为这样可以大大节省等待交换所需的时间。
- 其次，Linux 进行页面交换是有条件的，不是所有页面在不用时都交换到虚拟内存，Linux 内核根据“最近最经常使用”算法，仅仅将一些不经常使用的页面文件交换到虚拟内存。



* 有时我们会看到这么一个现象，Linux 物理内存还有很多，但是交换空间也使用了很多，其实这并不奇怪。例如，一个占用很大内存的进程运行时，需要耗费很多内存资源，此时就会有一些不常用页面文件被交换到虚拟内存中，但后来这个占用很多内存资源的进程结束并释放了很多内存时，刚才被交换出去的页面文件并不会自动交换进物理内存（除非有这个必要），那么此时系统物理内存就会空闲很多，同时交换空间也在被使用，就出现了刚才所说的现象了。
* 最后，交换空间的页面在使用时会首先被交换到物理内存，如果此时没有足够的物理内存来容纳这些页面，它们又会被马上交换出去，如此一来，虚拟内存中可能没有足够的空间来存储这些交换页面，最终会导致 Linux 出现假死机、服务异常等问题。Linux 虽然可以在一段时间内自行恢复，但是恢复后的系统己经基本不可用了。



因此，合理规划和设计 Linux 内存的使用是非常重要的，关于物理内存和交换空间的大小设置问题，取决于实际所用的硬盘大小，但大致遵循这样一个基本原则：

1. 如果内存较小（根据经验，物理内存小于 4GB），一般设置 swap 分区大小为内存的 2 倍；
2. 如果物理内存大于 4GB，而小于 16GB，可以设置 swap 分区大小等于物理内存；
3. 如果内存大小在 16GB 以上，可以设置 swap 为 0，但并不建议这么做，因为设置一定大小的 swap 分区是有一定作用的。









# 高级文件系统管理

## 磁盘配额

磁盘配额（Quota）是 Linux 系统中用来限制特定的普通用户或用户组在指定的分区上占用的磁盘空间或文件个数

1. 磁盘配额限制的用户和用户组，只能是普通用户和用户组，超级用户 root 是不能做磁盘配额；
2. 磁盘配额限制只能针对分区，而不能针对某个目录，换句话说，磁盘配额仅能针对文件系统进行限制，举个例子，如果你的 /dev/sda5 是挂载在 /home 底下，那么，在 /home 下的所有目录都会受到磁盘配额的限制；
3. 我们可以限制用户占用的磁盘容量大小（block），当然也能限制用户允许占用的文件个数（inode）。



### 用户配额和组配额

用户配额是指针对用户个人的配额，而组配额是指针对整个用户组的配额。如果我们需要限制的用户数量并不多，则可以给每个用户单独指定配额。如果用户比较多，那么单独限制太过麻烦，这时我们可以把用户加入某个用户组，然后给组指定配额，就会简单得多。



### 磁盘容量限制和文件个数限制

我们除了可以通过限制用户可用的 block 数量来限制用户可用的磁盘容量，也可以通过限制用户可用的 inode 数量来限制用户可以上传或新建的文件个数。



### 软限制和硬限制

软限制可理解为警告限制，硬限制就是真正的限制了。比如，规定软限制为 100MB，硬限制为 200MB,那么，当用户使用的磁盘空间为 100~200MB 时，用户还可以继续上传和新建文件，但是每次登录时都会收到一条警告消息，告诉用户磁盘将满。



### 宽限时间

如果用户的空间占用数处于软限制和硬限制之间，那么系统会在用户登录时警告用户磁盘将满，但是这个警告不会一直进行，而是有时间限制的，这个时间就是宽限时间，默认是 7 天。如果到达宽限时间，用户的磁盘占用量还超过软限制，那么软限制就会升级为硬限制。







## 前期准备



查看/home 是否是独立的文件系统

```sh
df -h /home
```



如果/home目录是否是独立的文件系统，可以直接对其进行限制。如果/home目录不是独立的文件系统，则可能就要针对根目录做磁盘配额了，但是不建议这样做。



是独立的文件系统：

```sh
[root@localhost ~]# df -h /home
Filesystem     Size  Used Avail Use% Mounted on
/dev/hda3      4.8G  740M  3.8G  17% /home  <-- /home是独立的！
```



不是独立的文件系统：

```sh
mao@ubuntu:~/桌面$ df -h /home
文件系统        容量  已用  可用 已用% 挂载点
/dev/sda5        15G  8.8G  4.8G   65% /
mao@ubuntu:~/桌面$ 
```



由于 VFAT 文件系统并不支持磁盘配额功能，因此，这里需要查看 /home 的文件系统：

```sh
mount | grep home
```

如果为 VFAT 文件系统，则不支持



如果想要获得文件系统的支持，还需要为执行的文件系统添加挂载参数，分别是 usrquota（启用用户限额）和 grpquota（启动用户组限额）



如果只是想在本次启动中试验磁盘配额，则只需使用如下的方式手动添加挂载参数：

```sh
mount -o remount,usrquota,grpquota /home
```

```sh
mount | grep home
```

手动添加的方式，会在下次重新挂载时消失，因此我们可以直接修改 /etc/fstab 文件，将挂载参数写入到配置文件中





## quotacheck命令

用于**扫描文件系统并建立Quota记录文件**

磁盘配额（Quota）就是通过分析整个文件系统中每个用户和群组拥有的文件总数和总容量，再将这些数据记录在文件系统中的最顶层目录中，然后在此记录文件中使用各个用户和群组的配额限制值去规范磁盘使用量的。因此，建立 Quota 的记录文件是非常有必要的。



命令：

```sh
quotacheck [选项] 文件系统
```



|    选项    |                             功能                             |
| :--------: | :----------------------------------------------------------: |
|     -a     | 扫瞄所有在 /etc/mtab 中，含有 quota 支持的 filesystem，加上此参数后，后边的文件系统可以不写； |
|     -u     |    针对使用者扫瞄文件与目录的使用情况，会创建 aquota.user    |
|     -g     |    针对群组扫瞄文件与目录的使用情况，会创建 aquota.group     |
|     -v     |                     显示扫瞄的详细过程；                     |
|     -f     |         强制扫瞄文件系统，并写入新的 quota 记录文件          |
| -M（大写） |   强制以读写的方式扫瞄文件系统，只有在特殊情况下才会使用。   |



执行命令：

```sh
quotacheck -avug
```

```sh
ll -d /home/a*
```

注意：

* 此命令不要反复的执行

* 通过执行 quotacheck 命令，就可以成功创建支持配额的记录文件。不要去手动编辑这两个文件





## quotaon命令

用于**开启磁盘配额限制**

我们已经使用 quotacheck 命令创建好了磁盘配额（Quota）的记录文件，接下来就可以启动 Quota 了



命令：

```sh
quotaon [选项]
```

或者：

```sh
quotaon [选项] 文件系统名称
```



| 选项 |                             功能                             |
| :--: | :----------------------------------------------------------: |
|  -a  | 根据 /etc/mtab 文件中对文件系统的配置，启动相关的Quota服务，如果不使用 -a 选项，则此命令后面就需要明确写上特定的文件系统名称 |
|  -u  |        针对用户启动 Quota（根据记录文件 aquota.user）        |
|  -g  |       针对群组启动 Quota（根据记录文件 aquota.group）        |
|  -v  |                  显示启动服务过程的详细信息                  |



quotaon -auvg 命令只需要在第一次启动 Quota 服务时才需要进行，因为下次重新启动系统时，系统的 /etc/rc.d/rc.sysinit 初始化脚本会自动下达这个命令



如果要同时启动针对用户和群组的 Quota 服务，可以使用如下命令：

```sh
[root@localhost ~]# quotaon -auvg
/dev/hda3 [/home]: group quotas turned on
/dev/hda3 [/home]: user quotas turned on
```



如果只针对用户启动 /var 的 Quota 支持，可以使用如下命令：

```sh
quotaon -uv /var
```





## quotaoff命令

用于**关闭磁盘配额限制**



命令：

```sh
quotaoff [选项]
```

或者：

```sh
quotaoff [选项] 文件系统名称
```



| 选项 |                             功能                             |
| :--: | :----------------------------------------------------------: |
|  -a  | 根据 /etc/mtab 文件，关闭已启动的 Quota 服务，如果不使用 -a 选项，则此命令后面就需要明确写上特定的文件系统名称 |
|  -u  |               关闭针对用户启动的 Quota 服务。                |
|  -g  |               关闭针对群组启动的 Quota 服务。                |
|  -v  |                    显示服务过程的详细信息                    |





如果要关闭所有已开启的Quota服务，可以使用如下命令：

```sh
quotaoff -auvg
```



如果只针对用户关闭 /var 启动的 Quota 支持，可以使用如下命令：

```sh
quotaoff -uv /var
```







## edquota命令

用于**修改用户和群组的配额限制参数**，包括磁盘容量和文件个数限制、软限制和硬限制值、宽限时间



命令：

```sh
 edquota [-u 用户名] [-g 群组名]
```

或者：

```sh
edquota -t
```

或者：

```sh
edquota -p 源用户名 -u 新用户名
```



|   选项    |                             功能                             |
| :-------: | :----------------------------------------------------------: |
| -u 用户名 |        进入配额的 Vi 编辑界面，修改针对用户的配置值；        |
| -g 群组名 |        进入配额的 Vi 编辑界面，修改针对群组的配置值；        |
|    -t     |                  修改配额参数中的宽限时间；                  |
|    -p     | 将源用户（或群组）的磁盘配额设置，复制给其他用户（或群组）。 |





edquota 命令配额限制信息：



|           表头           |                             含义                             |
| :----------------------: | :----------------------------------------------------------: |
|  文件系统（filesystem）  |          说明该限制值是针对哪个文件系统（或分区）；          |
|    磁盘容量（blocks）    | 此列的数值是 quota 自己算出来的，单位为 Kbytes，不要手动修改； |
| 磁盘容量的软限制（soft） | 当用户使用的磁盘空间超过此限制值，则用户在登陆时会收到警告信息，告知用户磁盘已满，单位为 KB； |
| 磁盘容量的硬限制（hard） |   要求用户使用的磁盘空间最大不能超过此限制值，单位为 KB；    |
|    文件数量（inodes）    | 同 blocks 一样，此项也是 quota自己计算出来的，无需手动修改； |
| 文件数量的软限制（soft） |      当用户拥有的文件数量超过此值，系统会发出警告信息；      |
| 文件数量的硬限制（hard） |               用户拥有的文件数量不能超过此值。               |







## setquota命令

**非交互式设置磁盘配额**



命令：

```sh
setquota -u 用户名 容量软限制 容量硬限制 个数软限制 个数硬限制 分区名
```



设定用户在/disk分区中的容量软限制为10MB，硬限制为20MB；文件个数软限制为5个，硬限制为8个：

```sh
setquota -u 用户名 10000 20000 5 8/disk
```





## quota 命令

用于**查询用户或用户组配额**



命令：

```sh
quota [选项] [用户名或组名]
```



选项：

- -u 用户名：查询用户配额；
- -g 组名：查询组配额；
- -v：显示详细信息；
- -s：以习惯单位显示容量大小，如M、G；





## repquota命令

用于**查询文件系统配额**



命令：

```sh
repquota [选项] [分区名]
```



选项：

- -a：依据 /etc/mtab 文件查询配额。如果不加 -a 选项，就一定要加分区名；
- -u：查询用户配额；
- -g：查询组配额；
- -v：显示详细信息；
- -s：以习惯单位显示容量太小；





## LVM逻辑卷管理机制

在以前，要想调整分区大小，要么先新建立一个更大的分区，然后复制旧分区中的内容到新分区，最后使用软链接来替代旧分区；要么使用调整分区大小的工具（如 parted），parted 虽然可以调整分区大小，但是它需要卸载分区之后才可以进行，也就是说需要停止服务。

我们就需要有一种管理机制来帮助我们动态地管理存储，LVM 就提供了这种功能。LVM 最大的好处就是可以随时调整分区的大小，分区中的现有数据不会丟失，并且不需要卸载分区、停止服务

LVM 是 Logical Volume Manager 的简称，译为中文就是逻辑卷管理。它是 Linux 下对硬盘分区的一种管理机制。LVM 适合于管理大存储设备，并允许用户动态调整文件系统的大小。此外，LVM 的快照功能可以帮助我们快速备份数据。LVM 为我们提供了逻辑概念上的磁盘，使得文件系统不再关心底层物理磁盘的概念。

Linux LVM 允许我们在逻辑卷在线的状态下将其复制到另一设备上，此成功被称为快照功能。快照允许我们在复制的同时，保证运行关键任务的 Web 服务器或数据库服务继续工作。



LVM 是在硬盘分区之上建立一个逻辑层，这个逻辑层让多个硬盘或分区看起来像一块逻辑硬盘，然后将这块逻辑硬盘分成逻辑卷之后使用，从而大大提高了分区的灵活性。我们把真实的物理硬盘或分区称作物理卷（PV）；由多个物理卷组成一块大的逻辑硬盘，叫作卷组（VG）；将卷组划分成多个可以使用的分区，叫作逻辑卷（LV）。而在 LVM 中最小的存储单位不再是 block，而是物理扩展块（Physical Extend，PE）



- 物理卷（Physical Volume，PV）：就是真正的物理硬盘或分区。
- 卷组（Volume Group，VG）：将多个物理卷合起来就组成了卷组。组成同一个卷组的物理卷可以是同一块硬盘的不同分区，也可以是不同硬盘上的不同分区。我们可以把卷组想象为一块逻辑硬盘。
- 逻辑卷（Logical Volume，LV）：卷组是一块逻辑硬盘，硬盘必须分区之后才能使用，我们把这个分区称作逻辑卷。逻辑卷可以被格式化和写入数据。我们可以把逻辑卷想象为分区。
- 物理扩展（Physical Extend，PE）：PE 是用来保存数据的最小单元，我们的数据实际上都是写入 PE 当中的。PE 的大小是可以配置的，默认是 4MB。



我们在建立 LVM 的时候，需要按照以下步骤来进行：

1. 把物理硬盘分成分区，当然也可以是整块物理硬盘；
2. 把物理分区建立为物理卷（PV），也可以直接把整块硬盘都建立为物理卷。
3. 把物理卷整合为卷组（VG）。卷组就已经可以动态地调整大小了，可以把物理分区加入卷组，也可以把物理分区从卷组中删除。
4. 把卷组再划分为逻辑卷（LV），当然逻辑卷也是可以直接调整大小的。我们说逻辑卷可以想象为分区，所以也需要格式化和挂载。





## PV物理卷

### 建立物理卷

命令：

```sh
pvcreate [设备文件名]
```

在建立物理卷时，我们既可以把整块硬盘都建立成物理卷，也可以把某个分区建立成物理卷。如果要把整块硬盘都建立成物理卷，则命令如下：

```sh
pvcreate /dev/sdb
```





### 查看物理卷

命令：

```sh
pvscan
```

或者：

```sh
pvdisplay
```





### 删除物理卷

命令：

```sh
pvremove 设备文件名
```





## VG卷组

### 建立卷组

命令：

```sh
vgcreate [-s PE 大小] 卷组名 物理卷名
```

[-s PE 大小] 选项的含义是指定 PE 的大小，单位可以是 MB、GB、TB 等。如果不写，则默认 PE 大小是 4MB。这里的卷组名指的就是要创建的卷组的名称，而物理卷名则指的是希望添加到此卷组的所有硬盘区分或者整个硬盘。





### 激活卷组

命令：

```sh
vgchange -a y 卷组名
```





### 停用卷组

```sh
vachange -a n 卷组名
```





### 查看卷组

命令：

```sh
vgscan
```

或者：

```sh
vgdisplay
```





### 增加卷组容量

命令：

```sh
vgextend scvg 设备文件名
```





### 减少卷组容量

命令：

```sh
vgreduce scvg 设备文件名
```





### 删除卷组

命令：

```sh
vgremove scvg
```

只有在删除卷组之后，才能删除物理卷。





## LV逻辑卷

### 建立逻辑卷

命令：

```sh
lvcreate [选项] [-n 逻辑卷名] 卷组名
```

选项：

- -L 容量：指定逻辑卷大小，单位为 MB、GB、TB 等；
- -l 个数：按照 PE 个数指定逻辑卷大小，这个参数需要换算容量，太麻烦；
- -n 逻辑卷名：指定逻辑卷名；



建立完逻辑卷，还要在格式化和挂载之后才能正常使用。





### 查看逻辑卷

命令：

```sh
lvscan
```

或者：

```sh
lvdisplay
```





### 调整逻辑卷大小

命令：

```sh
lvresize [选项] 逻辑卷的设备文件名
```



选项：

- -L 容量：安装容量调整大小，单位为 KB、GB、TB 等。使用 + 増加空间，- 代表减少空间。如果直接写容量，则代表设定逻辑卷大小为指定大小；
- -l 个数：按照 PE 个数调整逻辑卷大小；





### 删除逻辑卷

命令：

```sh
lvremove 逻辑卷的设备文件名
```









## 磁盘阵列

RAID（Redundant Arrays of Inexpensive Disks，磁盘阵列），翻译过来就是廉价的、具有冗余功能的磁盘阵列。其原理是通过软件或硬件将多块较小的分区组合成一个容量较大的磁盘组。这个较大的磁盘组读写性能更好，更重要的是具有数据冗余功能。

冗余就是多余的、重复的。在磁盘阵列中，冗余是指由多块硬盘组成一个磁盘组，在这个磁盘组中，数据存储在多块硬盘的不同地方，这样即使某块硬盘出现问题，数据也不会丟失，也就是磁盘数据具有了保护功能。

RAID 用于在多个硬盘上分散存储数据，并且能够“恰当”地重复存储数据，从而保证其中某块硬盘发生故障后，不至于影响整个系统的运转。RAID 将几块独立的硬盘组合在一起，形成一个逻辑上的 RAID 硬盘，这块“硬盘”在外界看来，和真实的硬盘一样，没有任何区别。



### RAID 0

RAID 0 也叫 Stripe 或 Striping（带区卷），是 RAID 级别中存储性能最好的一个。RAID 0 最好由相同容量的两块或两块以上的硬盘组成。如果组成 RAID 0 的两块硬盘大小不一致，则会影响 RAID 0 的性能。

比如由 3 块硬盘组成 RAID 0，数据的写入速度就是同样的数据向一块硬盘中写入速度的3倍

每块硬盘负责的数据写入量都是整体数据的 1/3，当然写入时间也只有原始时间的 1/3。



RAID 0 的优点：

- 通过把多块硬盘合并成一块大的逻辑硬盘，实现了数据跨硬盘存储。
- 通过把数据分割成等大小的区块，分别存入不同的硬盘，加快了数据的读写速度。数据的读/写性能是几种 RAID 中最好的。
- 多块硬盘合并成 RAID 0，几块小硬盘组成了更大容量的硬盘，而且没有容量损失。RAID 0 的总容量就是几块硬盘的容量之和。



缺点：

* 没有数据冗余功能，RAID 0 中的任何一块硬盘损坏，RAID 0 中所有的数据都将丟失





### RAID 1

RAID 1也叫 Mirror 或 Mirroring（镜像卷），由两块硬盘组成。两块硬盘的大小最好一致，否则总容量以容量小的那块硬盘为主。RAID 1 就具备了数据冗余功能，因为这种模式是把同一份数据同时写入两块硬盘。

比如有两块硬盘，组成了 RAID 1，当有数据写入时，相同的数据既写入硬盘 1，也写入硬盘 2。这样相当于给数据做了备份，所以任何一块硬盘损坏，数据都可以在另一块硬盘中找回。



RAID 1 具有了数据冗余功能，但是硬盘的容量却减少了 50%，因为两块硬盘当中保存的数据是一样的，所以两块硬盘际上只保存了一块硬盘那么多的数据



RAID 1 的优点：

- 具备了数据冗余功能，任何一块硬盘出现故障，数据都不会丟失。
- 数据的读取性能虽然不如RAID 0，但是比单一硬盘要好，因为数据有两份备份在不同的硬盘上，当多个进程读取同一数据时，RAID会自动分配读取进程。



RAID 1 的缺点：

- RAID 1 的容量只有两块硬盘容量的 50%，因为每块硬盘中保存的数据都一样。
- 数据写入性能较差，因为相同的数据会写入两块硬盘当中，相当于写入数据的总容量变大了。虽然 CPU 的速度足够快，但是负责数据写入的芯片只有一个。





### RAID 10 或 RAID 01

RAID 0 虽然数据读/写性能非常好，但是没有数据冗余功能；而 RAID 1 虽然具有了数据冗余功能，但是数据写入速度实在是太慢了

我们先用两块硬盘组成 RAID 1，再用两块硬盘组成另一个 RAID 1，最后把这两个 RAID 1组成 RAID 0，这种 RAID 方法称作 RAID 10。那先组成 RAID 0，再组成 RAID 1 的方法我们作 RAID 01



这样的组成方式，既有了 RAID 0 的性能优点，也有了 RAID 1 的数据冗余优点





### RAID 5

RAID 5 最少需要由 3 块硬盘组成，当然硬盘的容量也应当一致。当组成 RAID 5 时，同样需要把硬盘分隔成大小相同的区块。当有数据写入时，数据也被划分成等大小的区块，然后循环向 RAID 5 中写入。

每次循环写入数据的过程中，在其中一块硬盘中加入一个奇偶校验值（Parity），这个奇偶校验值的内容是这次循环写入时其他硬盘数据的备份。当有一块硬盘损坏时，采用这个奇偶校验值进行数据恢复。

我们使用三块硬盘组成了 RAID 5。当有数据循环写入时，每次循环都会写入一个奇偶校验值（Parity），并且每次奇偶校验值都会写入不同的硬盘。这个奇偶校验值就是其他两块硬盘中的数据经过换算之后产生的。因为每次奇偶校验值都会写入不同的硬盘，所以任何一块硬盘损坏之后，都可以依赖其他两块硬盘中保存的数据恢复这块损坏的硬盘中的数据。

每次数据循环写入时，都会有一块硬盘用来保存奇偶校验值，所以在 RAID 5 中可以使用的总容量是硬盘总数减去一块的容量之和。



RAID 5 的优点：

- 因为奇偶校验值的存在，RAID 5 具有了数据冗余功能。
- 硬盘容量损失比 RAID 1 小，而且组成 RAID 5 的硬盘数量越多，容量损失占比越小。
- RAID 5的数据读/写性能要比 RAID 1 更好，但是在数据写入性能上比 RAID 0 差。



RAID 5 的缺点：

- 不管由多少块硬盘组成 RAID 5，只支持一块硬盘损坏之后的数据恢复。
- RAID 5 的实际容量是组成 RAID 5 的硬盘总数减去一块的容量之和。也就是有一块硬盘用来保存奇偶校验值，但不能保存数据。





### 软 RAID 和硬 RAID

我们要想在服务器上实现 RAID，可以采用磁盘阵列卡（RAID 卡）来组成 RAID，也就是硬 RAID。RAID 卡上有专门的芯片负责 RAID 任务，因此性能要好得多，而且不占用系统性能，缺点是 RAID 卡比较昂贵。

如果我们既不想花钱又想使用 RAID，那就只能使用软 RAID 了。软 RAID 是指通过软件实现 RAID 功能，没有多余的费用，但是更加耗费服务器系统性能，而数据的写入速度比硬 RAID 慢。





## mdadm命令建立磁盘阵列

 建立RAID 5

### 建立分区

建立三个 2GB 大小的分区，构建 RAID 5。

命令：

```sh
fdisk -l
```





### 建立 RAID 5

命令：

```sh
mdadm [模式] [RAID设备文件名] [选项]
```



模式：

- Assemble：加入一个已经存在的阵列；
- Build：创建一个没有超级块的阵列；
- Create：创建一个阵列，每个设备都具有超级块；
- Manage：管理阵列，如添加设备和删除损坏设备；
- Misc：允许单独对阵列中的设备进行操作，如停止阵列；
- Follow or Monitor：监控RAID状态； Grow：改变RAID的容量或阵列中的数目；



选项：

- -s,-scan：扫描配置文件或/proc/mdstat文件，发现丟失的信息；
- -D,-detail：查看磁盘阵列详细信息；
- -C,-create：建立新的磁盘阵列，也就是调用 Create模式；
- -a,-auto=yes：采用标准格式建立磁阵列
- -n,-raicklevices=数字：使用几块硬盘或分区组成RAID
- -l,-level=级别：创建RAID的级别，可以是0,1,5
- -x,-spare-devices=数字：使用几块硬盘或分区组成备份设备
- -a,-add 设备文件名：在已经存在的RAID中加入设备
- -r,-remove 设备文件名名：在已经存在的RAID中移除设备
- -f,-fail设备文件名：把某个组成RAID的设备设置为错误状态
- -S,-stop：停止RAID设备
- -A,-assemble：按照配置文件加载RAID



```sh
mdadm -create -auto=yes /dev/md0-level=5 \
-raid-devices=3 -spare-devices=1 /dev/sdb5/dev/sdb6 /dev/sdb7 /dev/sdb8
```



/proc/mdstat 文件保存了 RAID 的相关信息

```sh
cat /proc/mdstat
```





### 格式化与挂载RAID

格式化命令：

```sh
mkfs -t ext4 /dev/md0
```

建立挂载点：

```sh
mkdir /raid
```

挂载/dev/md0：

```sh
mount /dev/md0 /raid/
```

```sh
mount
```





### 生成mdadm配置文件

命令：

```sh
echo Device /dev/sdb[5-8] >>/etc/mdadm.conf
```

```sh
mdadm -Ds >>/etc/mdadm.conf
```

```sh
cat /etc/mdadm.conf
```





### 设置开机后自动挂载

自动挂载也要修改 /etc/fstab 配置文件：

```sh
vi /etc/fstab
```

内容：

```sh
/dev/mdO /raid
ext4 defaults 12
```





### 启动或停止RAID

停止/dev/md0设备：

```sh
mdadm -S /dev/md0
```













# Linux系统管理

## 使用任务管理器的目的

1. 利用"应用程序"和"进程"标签来査看系统中到底运行了哪些程序和进程；
2. 利用"性能"和"用户"标签来判断服务器的健康状态；
3. 在"应用程序"和"进程"标签中强制中止任务和进程；



## 进程和程序

进程是正在执行的一个程序或命令，每个进程都是一个运行的实体，都有自己的地址空间，并占用一定的系统资源。程序是人使用计算机语言编写的可以实现特定目标或解决特定问题的代码集合。

程序=代码+数据+文档

当程序被执行时，执行人的权限和属性，以及程序的代码都会被加载入内存，操作系统给这个进程分配一个 ID，称为 PID（进程 ID）



在操作系统中，所有可以执行的程序与命令都会产生进程。只是有些程序和命令非常简单，如 ls 命令、touch 命令等，它们在执行完后就会结束，相应的进程也就会终结，所以我们很难捕捉到这些进程。但是还有一些程和命令，比如mysql服务进程，启动之后就会一直驻留在系统当中，我们把这样的进程称作常驻内存进程。

某些进程会产生一些新的进程，我们把这些进程称作子进程，而把这个进程本身称作父进程。比如，我们必须正常登录到 Shell 环境中才能执行系统命令，而 Linux 的标准 Shell 是 bash。我们在 bash 当中执行了 ls 命令，那么 bash 就是父进程，而 ls 命令是在 bash 进程中产生的进程，所以 ls 进程是 bash 进程的子进程。也就是说，子进程是依赖父进程而产生的，如果父进程不存在，那么子进程也不存在了。







## 进程管理的作用

### 判断服务器的健康状态

运维工程师最主要的工作就是保证服务器安全、稳定地运行。理想的状态是，在服务器出现问题，但是还没有造成服务器宕机或停止服务时，就人为干预解决了问题。

### 查看系统中所有的进程

我们需要查看看系统中所有正在运行的进程，通过这些进程可以判断系统中运行了哪些服务、是否有非法服务在运行。

### 杀死进程

这是进程管理中最不常用的手段。当需要停止服务时，会通过正确关闭命令来停止服务。只有在正确终止进程的手段失效的情况下，才会考虑使用 kill 命令杀死进程。





## 进程启动的方式

启动一个进程主要有 2 种途径，分别是通过手工启动和通过调度启动



### 手工启动进程

手工启动进程指的是由用户输入命令直接启动一个进程，根据所启动的进程类型和性质的不同，其又可以细分为前台启动和后台启动 2 种方式。

#### 前台启动进程

这是手工启动进程最常用的方式，因为当用户输入一个命令并运行，就已经启动了一个进程，而且是一个前台的进程，此时系统其实已经处于一个多进程的状态（一个是 Shell 进程，另一个是新启动的进程）。

#### 后台启动进程

启动一个启动后一直运行的进程，可以使用后台启动的方式，比如启动Tomcat进程和redis进程



### 调度启动进程

在 Linux 系统中，任务可以被配置在指定的时间、日期或者系统平均负载量低于指定值时自动启动。

例如，Linux 预配置了重要系统任务的运行，以便可以使系统能够实时被更新，系统管理员也可以使用自动化的任务来定期对重要数据进行备份。





## ps命令

ps 命令是最常用的监控进程的命令，通过此命令**可以查看系统中所有运行进程的详细信息**。



命令：

查看系统中所有的进程，使用 BS 操作系统格式：

```sh
ps aux
```

查看系统中所有的进程，使用 Linux 标准命令格式：

```sh
ps -le
```

查看当前 Shell 产生的进程：

```sh
ps -l
```



选项：

- a：显示一个终端的所有进程，除会话引线外；
- u：显示进程的归属用户及内存的使用情况；
- x：显示没有控制终端的进程；
- -l：长格式显示更加详细的信息；
- -e：显示所有进程；





|  表头   |                             含义                             |
| :-----: | :----------------------------------------------------------: |
|  USER   |                  该进程是由哪个用户产生的。                  |
|   PID   |                         进程的 ID。                          |
|  %CPU   | 该进程占用 CPU 资源的百分比，占用的百分比越高，进程越耗费资源。 |
|  %MEM   | 该进程占用物理内存的百分比，占用的百分比越高，进程越耗费资源。 |
|   VSZ   |            该进程占用虚拟内存的大小，单位为 KB。             |
|   RSS   |          该进程占用实际物理内存的大小，单位为 KB。           |
|   TTY   | 该进程是在哪个终端运行的。其中，tty1 ~ tty7 代表本地控制台终端（可以通过 Alt+F1 ~ F7 快捷键切换不同的终端），tty1~tty6 是本地的字符界面终端，tty7 是图形终端。pts/0 ~ 255 代表虚拟终端，一般是远程连接的终端，第一个远程连接占用 pts/0，第二个远程连接占用 pts/1，依次増长。 |
|  STAT   | 进程状态。常见的状态有以下几种：-D：不可被唤醒的睡眠状态，通常用于 I/O 情况。-R：该进程正在运行。-S：该进程处于睡眠状态，可被唤醒。-T：停止状态，可能是在后台暂停或进程处于除错状态。-W：内存交互状态（从 2.6 内核开始无效）。-X：死掉的进程（应该不会出现）。-Z：僵尸进程。进程已经中止，但是部分程序还在内存当中。-<：高优先级（以下状态在 BSD 格式中出现）。-N：低优先级。-L：被锁入内存。-s：包含子进程。-l：多线程（小写 L）。-+：位于后台。 |
|  START  |                      该进程的启动时间。                      |
|  TIME   |        该进程占用 CPU 的运算时间，注意不是系统时间。         |
| COMMAND |                     产生此进程的命令名。                     |



```sh
mao@ubuntu:~/桌面$ ps
    PID TTY          TIME CMD
   2260 pts/0    00:00:00 bash
   2373 pts/0    00:00:00 ps
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  3.6  0.2 167644 11480 ?        Ss   06:08   0:07 /sbin/init au
root           2  0.0  0.0      0     0 ?        S    06:08   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        I<   06:08   0:00 [rcu_gp]
root           4  0.0  0.0      0     0 ?        I<   06:08   0:00 [rcu_par_gp]
root           5  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/0:0-
root           6  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/0:0H
root           7  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/0:1-
root           8  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root           9  0.0  0.0      0     0 ?        I<   06:08   0:00 [mm_percpu_wq
root          10  0.0  0.0      0     0 ?        S    06:08   0:00 [rcu_tasks_ru
root          11  0.0  0.0      0     0 ?        S    06:08   0:00 [rcu_tasks_tr
root          12  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/0]
root          13  0.0  0.0      0     0 ?        I    06:08   0:00 [rcu_sched]
root          14  0.0  0.0      0     0 ?        S    06:08   0:00 [migration/0]
root          15  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          16  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/0]
root          17  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/1]
root          18  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          19  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/1]
root          20  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/1]
root          21  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/1:0-
root          22  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/1:0H
root          23  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/2]
root          24  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          25  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/2]
root          26  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/2]
root          27  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/2:0-
root          28  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/2:0H
root          29  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/3]
root          30  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          31  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/3]
root          32  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/3]
root          33  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/3:0-
root          34  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/3:0H
root          35  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/4]
root          36  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          37  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/4]
root          38  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/4]
root          39  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/4:0-
root          40  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/4:0H
root          41  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/5]
root          42  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          43  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/5]
root          44  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/5]
root          45  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/5:0-
root          46  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/5:0H
root          47  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/6]
root          48  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          49  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/6]
root          50  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/6]
root          51  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/6:0-
root          52  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/6:0H
root          53  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/7]
root          54  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          55  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/7]
root          56  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/7]
root          57  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/7:0-
root          58  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/7:0H
root          59  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/8]
root          60  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          61  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/8]
root          62  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/8]
root          63  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/8:0-
root          64  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/8:0H
root          65  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/9]
root          66  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          67  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/9]
root          68  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/9]
root          69  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/9:0-
root          70  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/9:0H
root          71  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/10]
root          72  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          73  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/10
root          74  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/10
root          75  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/10:0
root          76  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/10:0
root          77  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/11]
root          78  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          79  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/11
root          80  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/11
root          81  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/11:0
root          82  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/11:0
root          83  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/12]
root          84  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          85  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/12
root          86  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/12
root          87  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/12:0
root          88  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/12:0
root          89  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/13]
root          90  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          91  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/13
root          92  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/13
root          93  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/13:0
root          94  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/13:0
root          95  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/14]
root          96  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root          97  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/14
root          98  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/14
root          99  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/14:0
root         100  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/14:0
root         101  0.0  0.0      0     0 ?        S    06:08   0:00 [cpuhp/15]
root         102  0.0  0.0      0     0 ?        S    06:08   0:00 [idle_inject/
root         103  0.4  0.0      0     0 ?        S    06:08   0:00 [migration/15
root         104  0.0  0.0      0     0 ?        S    06:08   0:00 [ksoftirqd/15
root         105  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/15:0
root         106  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/15:0
root         107  0.0  0.0      0     0 ?        S    06:08   0:00 [kdevtmpfs]
root         108  0.0  0.0      0     0 ?        I<   06:08   0:00 [netns]
root         109  0.0  0.0      0     0 ?        I<   06:08   0:00 [inet_frag_wq
root         110  0.0  0.0      0     0 ?        S    06:08   0:00 [kauditd]
root         111  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/0:2-
root         112  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/1:1-
root         113  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/1:2-
root         114  0.0  0.0      0     0 ?        S    06:08   0:00 [khungtaskd]
root         115  0.0  0.0      0     0 ?        S    06:08   0:00 [oom_reaper]
root         116  0.0  0.0      0     0 ?        I<   06:08   0:00 [writeback]
root         117  0.0  0.0      0     0 ?        S    06:08   0:00 [kcompactd0]
root         118  0.0  0.0      0     0 ?        SN   06:08   0:00 [ksmd]
root         119  0.0  0.0      0     0 ?        SN   06:08   0:00 [khugepaged]
root         123  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/12:1
root         166  0.0  0.0      0     0 ?        I<   06:08   0:00 [kintegrityd]
root         167  0.0  0.0      0     0 ?        I<   06:08   0:00 [kblockd]
root         168  0.0  0.0      0     0 ?        I<   06:08   0:00 [blkcg_punt_b
root         169  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/2:1-
root         170  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/8:1-
root         171  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/3:1-
root         172  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/4:1-
root         173  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/6:1-
root         174  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/5:1-
root         175  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/7:1-
root         176  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/9:1-
root         177  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/11:1
root         178  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/10:1
root         179  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/15:1
root         180  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/13:1
root         181  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/14:1
root         182  0.0  0.0      0     0 ?        I<   06:08   0:00 [tpm_dev_wq]
root         183  0.0  0.0      0     0 ?        I<   06:08   0:00 [ata_sff]
root         184  0.0  0.0      0     0 ?        I<   06:08   0:00 [md]
root         185  0.0  0.0      0     0 ?        I<   06:08   0:00 [edac-poller]
root         186  0.0  0.0      0     0 ?        I<   06:08   0:00 [devfreq_wq]
root         187  0.0  0.0      0     0 ?        S    06:08   0:00 [watchdogd]

root         225  0.0  0.0      0     0 ?        S    06:08   0:00 [irq/53-pcieh
root         226  0.0  0.0      0     0 ?        S    06:08   0:00 [irq/54-pcieh
root         227  0.0  0.0      0     0 ?        S    06:08   0:00 [irq/55-pcieh
root         228  0.0  0.0      0     0 ?        I<   06:08   0:00 [acpi_thermal
root         229  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/9:2-
root         230  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/10:2
root         231  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/11:2
root         232  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/12:2
root         233  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/13:2
root         234  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/14:2
root         235  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/15:2
root         236  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/8:2-
root         237  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_0]
root         238  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_0]
root         239  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_1]
root         240  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_1]
root         241  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         242  0.0  0.0      0     0 ?        I<   06:08   0:00 [vfio-irqfd-c

root         366  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_23]
root         367  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_23]
root         368  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_24]
root         369  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_24]
root         370  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_25]
root         371  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_25]
root         372  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_26]
root         373  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_26]
root         374  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_27]
root         375  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_27]
root         376  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_28]
root         377  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_28]
root         378  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_29]
root         379  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_29]
root         380  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_30]
root         381  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_30]
root         382  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_31]
root         383  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_31]
root         384  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         385  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         386  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         387  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         388  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         389  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         390  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         391  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         392  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         393  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         394  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         395  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         396  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         397  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         398  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         399  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         400  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         401  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         402  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         403  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         404  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         405  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         406  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         407  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         408  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         409  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         410  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/u256
root         411  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/5:2-
root         412  0.0  0.0      0     0 ?        S    06:08   0:00 [scsi_eh_32]
root         413  0.0  0.0      0     0 ?        I<   06:08   0:00 [scsi_tmf_32]
root         415  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/6:1H
root         417  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/14:1
root         419  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/5:1H
root         437  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/0:1H
root         438  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/4:1H
root         440  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/2:1H
root         441  0.0  0.0      0     0 ?        S    06:08   0:00 [jbd2/sda5-8]
root         442  0.0  0.0      0     0 ?        I<   06:08   0:00 [ext4-rsv-con
root         447  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/12:1
root         477  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/8:1H
root         483  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/15:1
root         484  0.3  0.8  66760 33532 ?        S<s  06:08   0:00 /lib/systemd/
root         490  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/11:1
root         496  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/6:2-
root         502  0.0  0.0      0     0 ?        I<   06:08   0:00 [kworker/1:1H
root         507  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop0]
root         509  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/7:2-
root         516  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop1]
root         519  0.0  0.0      0     0 ?        S    06:08   0:00 [irq/16-vmwgf
root         520  0.0  0.0      0     0 ?        I<   06:08   0:00 [ttm_swap]
root         521  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc0]
root         522  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc1]
root         523  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc2]
root         525  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc3]
root         526  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc4]
root         527  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc5]
root         528  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc6]
root         529  0.0  0.0      0     0 ?        S    06:08   0:00 [card0-crtc7]
root         531  0.3  0.1  24140  7404 ?        Ss   06:08   0:00 /lib/systemd/
root         532  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop2]
root         539  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/1:3-
root         540  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop3]
root         543  0.0  0.0 150668   320 ?        Ssl  06:08   0:00 vmware-vmbloc
root         546  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop4]
root         547  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop5]
root         548  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop6]
root         549  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop7]
root         580  0.1  0.0      0     0 ?        S<   06:08   0:00 [loop8]
root         617  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop9]
root         632  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop10]
root         655  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/4:2-
root         656  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop11]
root         694  0.0  0.0      0     0 ?        I<   06:08   0:00 [cryptd]
root         715  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop12]
root         768  0.0  0.0      0     0 ?        S<   06:08   0:00 [loop13]
root         845  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/3:2-
systemd+     872  0.0  0.2  23904 11940 ?        Ss   06:08   0:00 /lib/systemd/
systemd+     873  0.0  0.1  90260  6020 ?        Ssl  06:08   0:00 /lib/systemd/
root         876  0.0  0.2  58772 10660 ?        Ss   06:08   0:00 /usr/bin/VGAu
root         879  0.2  0.1 248076  7420 ?        Ssl  06:08   0:00 /usr/bin/vmto
root         896  0.0  0.2 250532  9508 ?        Ssl  06:08   0:00 /usr/lib/acco
root         897  0.0  0.0   2548   712 ?        Ss   06:08   0:00 /usr/sbin/acp
root         898  0.0  0.0  16720   772 ?        Ss   06:08   0:00 /usr/sbin/ana
avahi        900  0.0  0.0   8532  3480 ?        Ss   06:08   0:00 avahi-daemon:
root         901  0.0  0.0  18052  3224 ?        Ss   06:08   0:00 /usr/sbin/cro
message+     903  0.4  0.1   9904  6520 ?        Ss   06:08   0:00 /usr/bin/dbus
root         905  0.4  0.5 421500 22544 ?        Ssl  06:08   0:00 /usr/sbin/Net
root         913  0.0  0.0  81960  3776 ?        Ssl  06:08   0:00 /usr/sbin/irq
root         917  0.1  0.5  47968 20068 ?        Ss   06:08   0:00 /usr/bin/pyth
root         920  0.8  0.3 253568 13720 ?        Ssl  06:08   0:01 /usr/lib/poli
syslog       924  0.1  0.1 224356  4792 ?        Ssl  06:08   0:00 /usr/sbin/rsy
root         932  1.3  1.0 1760900 40216 ?       Ssl  06:08   0:02 /usr/lib/snap
root         933  0.0  0.1 244348  6752 ?        Ssl  06:08   0:00 /usr/libexec/
root         934  0.1  0.2  16764  8052 ?        Ss   06:08   0:00 /lib/systemd/
root         936  0.0  0.3 395636 14236 ?        Ssl  06:08   0:00 /usr/lib/udis
root         939  0.0  0.1  13688  4988 ?        Ss   06:08   0:00 /sbin/wpa_sup
avahi        952  0.0  0.0   8352   324 ?        S    06:08   0:00 avahi-daemon:
root         995  0.0  0.3 178400 12832 ?        Ssl  06:08   0:00 /usr/sbin/cup
root        1000  0.0  0.2 313756 10376 ?        Ssl  06:08   0:00 /usr/sbin/Mod
root        1005  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/15:3
root        1009  0.0  0.5 126660 22696 ?        Ssl  06:08   0:00 /usr/bin/pyth
root        1020  0.0  0.0      0     0 ?        I    06:08   0:00 [kworker/9:3-
root        1034  0.0  0.2  36948  8636 ?        Ss   06:08   0:00 /usr/sbin/cup
root        1036  0.0  0.2 248248  8864 ?        Ssl  06:08   0:00 /usr/sbin/gdm
lp          1040  0.0  0.1  15336  6580 ?        S    06:08   0:00 /usr/lib/cups
whoopsie    1115  0.0  0.4 253528 15984 ?        Ssl  06:08   0:00 /usr/bin/whoo
kernoops    1120  0.0  0.0  11264   448 ?        Ss   06:08   0:00 /usr/sbin/ker
kernoops    1127  0.0  0.0  11264   448 ?        Ss   06:08   0:00 /usr/sbin/ker
rtkit       1148  0.0  0.0 152940  3084 ?        SNsl 06:08   0:00 /usr/libexec/
root        1252  0.0  0.2 260728  9704 ?        Ssl  06:08   0:00 /usr/lib/upow
root        1396  0.0  0.4 294028 16868 ?        Ssl  06:08   0:00 /usr/lib/pack
colord      1526  0.0  0.4 257568 16904 ?        Ssl  06:08   0:00 /usr/libexec/
root        1613  0.0  0.2 175828  9716 ?        Sl   06:08   0:00 gdm-session-w
mao         1621  0.2  0.2  19088 10312 ?        Ss   06:08   0:00 /lib/systemd/
mao         1622  0.0  0.0 169004  3464 ?        S    06:08   0:00 (sd-pam)
mao         1627  0.1  0.5 1491488 20184 ?       S<sl 06:08   0:00 /usr/bin/puls
mao         1629  0.0  0.6 520024 24788 ?        SNsl 06:08   0:00 /usr/libexec/
mao         1632  0.2  0.1   9832  7036 ?        Ss   06:08   0:00 /usr/bin/dbus
mao         1637  0.0  0.1 249096  7832 ?        Sl   06:08   0:00 /usr/bin/gnom
mao         1640  0.0  0.1 248440  7936 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1646  0.0  0.2 382064  8228 ?        Sl   06:08   0:00 /usr/libexec/
mao         1665  0.0  0.2 326084 11452 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1672  0.0  0.1 244336  6260 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1676  0.0  0.1 244508  6272 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1681  0.0  0.9 553836 36612 ?        Sl   06:08   0:00 /usr/libexec/
mao         1689  0.0  0.2 327168 11496 ?        Sl   06:08   0:00 /usr/libexec/
mao         1694  0.0  0.1 246612  6836 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1699  0.0  0.2 325356  9248 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1707  0.0  0.1 172804  6484 tty2     Ssl+ 06:08   0:00 /usr/lib/gdm3
mao         1709  1.2  1.6 288720 63956 tty2     Sl+  06:08   0:02 /usr/lib/xorg
mao         1726  0.0  0.3 199456 15684 tty2     Sl+  06:08   0:00 /usr/libexec/
mao         1793  0.0  0.0   6040   456 ?        Ss   06:08   0:00 /usr/bin/ssh-
mao         1812  0.0  0.2 309824  9156 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1817  0.0  0.1   7248  4392 ?        S    06:08   0:00 /usr/bin/dbus
mao         1821  0.0  0.1  98860  4428 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1828  0.1  0.4 495904 17976 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1842  3.6  6.4 4237996 257520 ?      Ssl  06:08   0:06 /usr/bin/gnom
mao         1868  0.0  0.2 397436 10608 ?        Sl   06:08   0:00 ibus-daemon -
mao         1872  0.0  0.2 249288  9096 ?        Sl   06:08   0:00 /usr/libexec/
mao         1873  0.5  0.8 287400 33892 ?        Sl   06:08   0:01 /usr/libexec/
mao         1875  0.1  0.7 209656 30568 ?        Sl   06:08   0:00 /usr/libexec/
mao         1877  0.0  0.2 249132  9184 ?        Sl   06:08   0:00 /usr/libexec/
mao         1891  0.0  0.1 162836  7448 ?        Sl   06:08   0:00 /usr/libexec/
mao         1895  0.0  0.1 244504  4736 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1900  0.0  0.5 581640 21092 ?        Sl   06:08   0:00 /usr/libexec/
mao         1906  0.0  0.6 399508 26900 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1915  0.1  0.7 847876 30692 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1918  0.0  0.1 156220  5536 ?        Sl   06:08   0:00 /usr/libexec/
mao         1928  0.1  0.8 756424 33656 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1941  0.0  0.6 2939420 27196 ?       Sl   06:08   0:00 /usr/bin/gjs 
mao         1955  0.0  0.2 326200 10676 ?        Sl   06:08   0:00 /usr/libexec/
mao         1960  0.0  0.2 322892  9220 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1961  0.1  0.7 432244 31668 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1964  0.0  0.4 383344 17448 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1967  0.0  0.2 323176  9980 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1971  0.2  0.7 357664 31212 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1973  0.2  0.8 912908 33248 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1976  0.2  0.7 431804 31676 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1980  0.2  1.5 647404 62052 ?        Sl   06:08   0:00 /usr/libexec/
mao         1985  0.0  0.2 256932 11432 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1986  0.0  0.1 465928  6268 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1987  0.4  1.0 302064 42716 ?        Sl   06:08   0:00 /usr/bin/vmto
mao         1991  0.0  0.1 244336  6368 ?        Ssl  06:08   0:00 /usr/libexec/
mao         1996  0.0  0.3 477880 12512 ?        Ssl  06:08   0:00 /usr/libexec/
mao         2001  0.0  0.2 327052 10892 ?        Ssl  06:08   0:00 /usr/libexec/
mao         2002  0.0  0.1 231800  5648 ?        Sl   06:08   0:00 /usr/libexec/
mao         2005  0.0  0.2 330764 11076 ?        Ssl  06:08   0:00 /usr/libexec/
mao         2011  0.0  0.2 396852  9532 ?        Ssl  06:08   0:00 /usr/libexec/
mao         2018  0.2  0.7 357224 30812 ?        Ssl  06:08   0:00 /usr/libexec/
mao         2028  0.0  0.2 327216 10652 ?        Ssl  06:08   0:00 /usr/libexec/
mao         2033  0.2  0.8 358504 32236 ?        Ssl  06:08   0:00 /usr/libexec/
mao         2060  0.0  0.3 351016 15308 ?        Sl   06:08   0:00 /usr/libexec/
mao         2117  0.0  0.2 175456  9064 ?        Sl   06:08   0:00 /usr/libexec/
mao         2251  0.5  1.6 908324 64236 ?        Rsl  06:09   0:00 /usr/libexec/
mao         2260  0.0  0.1  19252  4820 pts/0    Ss   06:09   0:00 bash
mao         2269  0.0  0.1 170988  6392 ?        Ssl  06:09   0:00 /usr/libexec/
mao         2272  0.2  1.4 823316 57544 ?        Sl   06:09   0:00 update-notifi
mao         2365  0.0  0.3 435900 12876 ?        Sl   06:10   0:00 /usr/libexec/
mao         2374  0.0  0.0  20148  3316 pts/0    R+   06:11   0:00 ps aux
mao@ubuntu:~/桌面$ 
```





| 表头  |                             含义                             |
| :---: | :----------------------------------------------------------: |
|   F   | 进程标志，说明进程的权限，常见的标志有两个: 1：进程可以被复制，但是不能被执行；4：进程使用超级用户权限； |
|   S   |    进程状态。具体的状态和"psaux"命令中的 STAT 状态一致；     |
|  UID  |                   运行此进程的用户的 ID；                    |
|  PID  |                         进程的 ID；                          |
| PPID  |                        父进程的 ID；                         |
|   C   |             该进程的 CPU 使用率，单位是百分比；              |
|  PRI  | 进程的优先级，数值越小，该进程的优先级越高，越早被 CPU 执行； |
|  NI   |          进程的优先级，数值越小，该进程越早被执行；          |
| ADDR  |                   该进程在内存的哪个位置；                   |
|  SZ   |                     该进程占用多大内存；                     |
| WCHAN |              该进程是否运行。"-"代表正在运行；               |
|  TTY  |                    该进程由哪个终端产生；                    |
| TIME  |        该进程占用 CPU 的运算时间，注意不是系统时间；         |
|  CMD  |                     产生此进程的命令名；                     |





```sh
mao@ubuntu:~/桌面$ ps -le
F S   UID     PID    PPID  C PRI  NI ADDR SZ WCHAN  TTY          TIME CMD
4 S     0       1       0  3  80   0 - 41911 -      ?        00:00:07 systemd
1 S     0       2       0  0  80   0 -     0 -      ?        00:00:00 kthreadd
1 I     0       3       2  0  60 -20 -     0 -      ?        00:00:00 rcu_gp
1 I     0       4       2  0  60 -20 -     0 -      ?        00:00:00 rcu_par_gp
1 I     0       5       2  0  80   0 -     0 -      ?        00:00:00 kworker/0:
1 I     0       6       2  0  60 -20 -     0 -      ?        00:00:00 kworker/0:
5 I     0       7       2  0  80   0 -     0 -      ?        00:00:00 kworker/0:
1 I     0       8       2  0  80   0 -     0 -      ?        00:00:00 kworker/u2
1 I     0       9       2  0  60 -20 -     0 -      ?        00:00:00 mm_percpu_
1 S     0      10       2  0  80   0 -     0 -      ?        00:00:00 rcu_tasks_
1 S     0      11       2  0  80   0 -     0 -      ?        00:00:00 rcu_tasks_
1 S     0      12       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      13       2  0  80   0 -     0 -      ?        00:00:00 rcu_sched
1 S     0      14       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      15       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      16       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/0
5 S     0      17       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/1
1 S     0      18       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      19       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      20       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      21       2  0  80   0 -     0 -      ?        00:00:00 kworker/1:
1 I     0      22       2  0  60 -20 -     0 -      ?        00:00:00 kworker/1:
5 S     0      23       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/2
1 S     0      24       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      25       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      26       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      27       2  0  80   0 -     0 -      ?        00:00:00 kworker/2:
1 I     0      28       2  0  60 -20 -     0 -      ?        00:00:00 kworker/2:
5 S     0      29       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/3
1 S     0      30       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      31       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      32       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      33       2  0  80   0 -     0 -      ?        00:00:00 kworker/3:
1 I     0      34       2  0  60 -20 -     0 -      ?        00:00:00 kworker/3:
5 S     0      35       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/4
1 S     0      36       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      37       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      38       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      39       2  0  80   0 -     0 -      ?        00:00:00 kworker/4:
1 I     0      40       2  0  60 -20 -     0 -      ?        00:00:00 kworker/4:
5 S     0      41       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/5
1 S     0      42       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      43       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      44       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      45       2  0  80   0 -     0 -      ?        00:00:00 kworker/5:
1 I     0      46       2  0  60 -20 -     0 -      ?        00:00:00 kworker/5:
5 S     0      47       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/6
1 S     0      48       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      49       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      50       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      51       2  0  80   0 -     0 -      ?        00:00:00 kworker/6:
1 I     0      52       2  0  60 -20 -     0 -      ?        00:00:00 kworker/6:
5 S     0      53       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/7
1 S     0      54       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      55       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      56       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      57       2  0  80   0 -     0 -      ?        00:00:00 kworker/7:
1 I     0      58       2  0  60 -20 -     0 -      ?        00:00:00 kworker/7:
5 S     0      59       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/8
1 S     0      60       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      61       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      62       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      63       2  0  80   0 -     0 -      ?        00:00:00 kworker/8:
1 I     0      64       2  0  60 -20 -     0 -      ?        00:00:00 kworker/8:
5 S     0      65       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/9
1 S     0      66       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      67       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      68       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      69       2  0  80   0 -     0 -      ?        00:00:00 kworker/9:
1 I     0      70       2  0  60 -20 -     0 -      ?        00:00:00 kworker/9:
5 S     0      71       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/10
1 S     0      72       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      73       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      74       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      75       2  0  80   0 -     0 -      ?        00:00:00 kworker/10
1 I     0      76       2  0  60 -20 -     0 -      ?        00:00:00 kworker/10
5 S     0      77       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/11
1 S     0      78       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      79       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      80       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      81       2  0  80   0 -     0 -      ?        00:00:00 kworker/11
1 I     0      82       2  0  60 -20 -     0 -      ?        00:00:00 kworker/11
5 S     0      83       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/12
1 S     0      84       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      85       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      86       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      87       2  0  80   0 -     0 -      ?        00:00:00 kworker/12
1 I     0      88       2  0  60 -20 -     0 -      ?        00:00:00 kworker/12
5 S     0      89       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/13
1 S     0      90       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      91       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      92       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      93       2  0  80   0 -     0 -      ?        00:00:00 kworker/13
1 I     0      94       2  0  60 -20 -     0 -      ?        00:00:00 kworker/13
5 S     0      95       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/14
1 S     0      96       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0      97       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0      98       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0      99       2  0  80   0 -     0 -      ?        00:00:00 kworker/14
1 I     0     100       2  0  60 -20 -     0 -      ?        00:00:00 kworker/14
5 S     0     101       2  0  80   0 -     0 -      ?        00:00:00 cpuhp/15
1 S     0     102       2  0   9   - -     0 -      ?        00:00:00 idle_injec
1 S     0     103       2  0 -40   - -     0 -      ?        00:00:00 migration/
1 S     0     104       2  0  80   0 -     0 -      ?        00:00:00 ksoftirqd/
1 I     0     105       2  0  80   0 -     0 -      ?        00:00:00 kworker/15
1 I     0     106       2  0  60 -20 -     0 -      ?        00:00:00 kworker/15
5 S     0     107       2  0  80   0 -     0 -      ?        00:00:00 kdevtmpfs
1 I     0     108       2  0  60 -20 -     0 -      ?        00:00:00 netns
1 I     0     109       2  0  60 -20 -     0 -      ?        00:00:00 inet_frag_
1 S     0     110       2  0  80   0 -     0 -      ?        00:00:00 kauditd
1 I     0     111       2  0  80   0 -     0 -      ?        00:00:00 kworker/0:
1 I     0     112       2  0  80   0 -     0 -      ?        00:00:00 kworker/1:
1 I     0     113       2  0  80   0 -     0 -      ?        00:00:00 kworker/1:
1 S     0     114       2  0  80   0 -     0 -      ?        00:00:00 khungtaskd
1 S     0     115       2  0  80   0 -     0 -      ?        00:00:00 oom_reaper
1 I     0     116       2  0  60 -20 -     0 -      ?        00:00:00 writeback
1 S     0     117       2  0  80   0 -     0 -      ?        00:00:00 kcompactd0
1 S     0     118       2  0  85   5 -     0 -      ?        00:00:00 ksmd
1 S     0     119       2  0  99  19 -     0 -      ?        00:00:00 khugepaged
1 I     0     123       2  0  80   0 -     0 -      ?        00:00:00 kworker/12
1 I     0     166       2  0  60 -20 -     0 -      ?        00:00:00 kintegrity
1 I     0     167       2  0  60 -20 -     0 -      ?        00:00:00 kblockd
1 I     0     168       2  0  60 -20 -     0 -      ?        00:00:00 blkcg_punt
1 I     0     169       2  0  80   0 -     0 -      ?        00:00:00 kworker/2:
1 I     0     170       2  0  80   0 -     0 -      ?        00:00:00 kworker/8:
1 I     0     171       2  0  80   0 -     0 -      ?        00:00:00 kworker/3:
1 I     0     172       2  0  80   0 -     0 -      ?        00:00:00 kworker/4:
1 I     0     173       2  0  80   0 -     0 -      ?        00:00:00 kworker/6:
1 I     0     174       2  0  80   0 -     0 -      ?        00:00:00 kworker/5:
1 I     0     175       2  0  80   0 -     0 -      ?        00:00:00 kworker/7:
1 I     0     176       2  0  80   0 -     0 -      ?        00:00:00 kworker/9:
1 I     0     177       2  0  80   0 -     0 -      ?        00:00:00 kworker/11
1 I     0     178       2  0  80   0 -     0 -      ?        00:00:00 kworker/10
1 I     0     179       2  0  80   0 -     0 -      ?        00:00:00 kworker/15
1 I     0     180       2  0  80   0 -     0 -      ?        00:00:00 kworker/13
1 I     0     181       2  0  80   0 -     0 -      ?        00:00:00 kworker/14
1 I     0     182       2  0  60 -20 -     0 -      ?        00:00:00 tpm_dev_wq
1 I     0     183       2  0  60 -20 -     0 -      ?        00:00:00 ata_sff
1 I     0     184       2  0  60 -20 -     0 -      ?        00:00:00 md
1 I     0     185       2  0  60 -20 -     0 -      ?        00:00:00 edac-polle
1 I     0     186       2  0  60 -20 -     0 -      ?        00:00:00 devfreq_wq
1 S     0     187       2  0   9   - -     0 -      ?        00:00:00 watchdogd
1 I     0     188       2  0  80   0 -     0 -      ?        00:00:00 kworker/u2
1 I     0     189       2  0  80   0 -     0 -      ?        00:00:00 kworker/2:
1 I     0     190       2  0  60 -20 -     0 -      ?        00:00:00 kworker/3:
1 S     0     192       2  0  80   0 -     0 -      ?        00:00:00 kswapd0
1 S     0     193       2  0  80   0 -     0 -      ?        00:00:00 ecryptfs-k
1 I     0     195       2  0  60 -20 -     0 -      ?        00:00:00 kthrotld

1 S     0     226       2  0   9   - -     0 -      ?        00:00:00 irq/54-pci
1 S     0     227       2  0   9   - -     0 -      ?        00:00:00 irq/55-pci
1 I     0     228       2  0  60 -20 -     0 -      ?        00:00:00 acpi_therm
1 I     0     229       2  0  80   0 -     0 -      ?        00:00:00 kworker/9:
1 I     0     230       2  0  80   0 -     0 -      ?        00:00:00 kworker/10
1 I     0     231       2  0  80   0 -     0 -      ?        00:00:00 kworker/11
1 I     0     232       2  0  80   0 -     0 -      ?        00:00:00 kworker/12
1 I     0     233       2  0  80   0 -     0 -      ?        00:00:00 kworker/13
1 I     0     234       2  0  80   0 -     0 -      ?        00:00:00 kworker/14
1 I     0     235       2  0  80   0 -     0 -      ?        00:00:00 kworker/15
1 I     0     236       2  0  80   0 -     0 -      ?        00:00:00 kworker/8:
1 S     0     237       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_0
1 I     0     238       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_0
1 S     0     239       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_1
1 I     0     240       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 I     0     241       2  0  80   0 -     0 -      ?        00:00:00 kworker/u2
1 I     0     242       2  0  60 -20 -     0 -      ?        00:00:00 vfio-irqfd
1 I     0     243       2  0  60 -20 -     0 -      ?        00:00:00 ipv6_addrc
1 I     0     244       2  0  60 -20 -     0 -      ?        00:00:00 kworker/10
1 I     0     245       2  0  80   0 -     0 -      ?        00:00:00 kworker/u2

1 S     0     338       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_9
1 I     0     339       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_9
1 S     0     340       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_10
1 I     0     341       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     342       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_11
1 I     0     343       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     344       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_12
1 I     0     345       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     346       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_13
1 I     0     347       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     348       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_14
1 I     0     349       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     350       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_15
1 I     0     351       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     352       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_16
1 I     0     353       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     354       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_17
1 I     0     355       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     356       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_18
1 I     0     357       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     358       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_19
1 I     0     359       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_1
1 S     0     360       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_20
1 I     0     361       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     362       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_21
1 I     0     363       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     364       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_22
1 I     0     365       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     366       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_23
1 I     0     367       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     368       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_24
1 I     0     369       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     370       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_25
1 I     0     371       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     372       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_26
1 I     0     373       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     374       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_27
1 I     0     375       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     376       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_28
1 I     0     377       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     378       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_29
1 I     0     379       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_2
1 S     0     380       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_30
1 I     0     381       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_3
1 S     0     382       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_31
1 I     0     383       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_3
1 I     0     384       2  0  80   0 -     0 -      ?        00:00:00 kworker/u2

1 I     0     411       2  0  80   0 -     0 -      ?        00:00:00 kworker/5:
1 S     0     412       2  0  80   0 -     0 -      ?        00:00:00 scsi_eh_32
1 I     0     413       2  0  60 -20 -     0 -      ?        00:00:00 scsi_tmf_3
1 I     0     415       2  0  60 -20 -     0 -      ?        00:00:00 kworker/6:
1 I     0     417       2  0  60 -20 -     0 -      ?        00:00:00 kworker/14
1 I     0     419       2  0  60 -20 -     0 -      ?        00:00:00 kworker/5:
1 I     0     437       2  0  60 -20 -     0 -      ?        00:00:00 kworker/0:
1 I     0     438       2  0  60 -20 -     0 -      ?        00:00:00 kworker/4:
1 I     0     440       2  0  60 -20 -     0 -      ?        00:00:00 kworker/2:
1 S     0     441       2  0  80   0 -     0 -      ?        00:00:00 jbd2/sda5-
1 I     0     442       2  0  60 -20 -     0 -      ?        00:00:00 ext4-rsv-c
1 I     0     447       2  0  60 -20 -     0 -      ?        00:00:00 kworker/12
1 I     0     477       2  0  60 -20 -     0 -      ?        00:00:00 kworker/8:
1 I     0     483       2  0  60 -20 -     0 -      ?        00:00:00 kworker/15
4 S     0     484       1  0  79  -1 - 16690 -      ?        00:00:00 systemd-jo
1 I     0     490       2  0  60 -20 -     0 -      ?        00:00:00 kworker/11
1 I     0     496       2  0  80   0 -     0 -      ?        00:00:00 kworker/6:
1 I     0     502       2  0  60 -20 -     0 -      ?        00:00:00 kworker/1:
1 S     0     507       2  0  60 -20 -     0 -      ?        00:00:00 loop0
1 I     0     509       2  0  80   0 -     0 -      ?        00:00:00 kworker/7:
1 S     0     516       2  0  60 -20 -     0 -      ?        00:00:00 loop1
1 S     0     519       2  0   9   - -     0 -      ?        00:00:00 irq/16-vmw
1 I     0     520       2  0  60 -20 -     0 -      ?        00:00:00 ttm_swap
1 S     0     521       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
1 S     0     522       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
1 S     0     523       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
1 S     0     525       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
1 S     0     526       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
1 S     0     527       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
1 S     0     528       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
1 S     0     529       2  0   9   - -     0 -      ?        00:00:00 card0-crtc
4 S     0     531       1  0  80   0 -  6035 -      ?        00:00:00 systemd-ud
1 S     0     532       2  0  60 -20 -     0 -      ?        00:00:00 loop2
1 I     0     539       2  0  80   0 -     0 -      ?        00:00:00 kworker/1:
1 S     0     540       2  0  60 -20 -     0 -      ?        00:00:00 loop3
1 S     0     543       1  0  80   0 - 37667 -      ?        00:00:00 vmware-vmb
1 S     0     546       2  0  60 -20 -     0 -      ?        00:00:00 loop4
1 S     0     547       2  0  60 -20 -     0 -      ?        00:00:00 loop5
1 S     0     548       2  0  60 -20 -     0 -      ?        00:00:00 loop6
1 S     0     549       2  0  60 -20 -     0 -      ?        00:00:00 loop7
1 S     0     580       2  0  60 -20 -     0 -      ?        00:00:00 loop8
1 S     0     617       2  0  60 -20 -     0 -      ?        00:00:00 loop9
1 S     0     632       2  0  60 -20 -     0 -      ?        00:00:00 loop10
1 I     0     655       2  0  80   0 -     0 -      ?        00:00:00 kworker/4:
1 S     0     656       2  0  60 -20 -     0 -      ?        00:00:00 loop11
1 I     0     694       2  0  60 -20 -     0 -      ?        00:00:00 cryptd
1 S     0     715       2  0  60 -20 -     0 -      ?        00:00:00 loop12
1 S     0     768       2  0  60 -20 -     0 -      ?        00:00:00 loop13
1 I     0     845       2  0  80   0 -     0 -      ?        00:00:00 kworker/3:
4 S   101     872       1  0  80   0 -  5976 -      ?        00:00:00 systemd-re
4 S   102     873       1  0  80   0 - 22565 -      ?        00:00:00 systemd-ti
4 S     0     876       1  0  80   0 - 14693 -      ?        00:00:00 VGAuthServ
4 S     0     879       1  0  80   0 - 62019 -      ?        00:00:00 vmtoolsd
4 S     0     896       1  0  80   0 - 62633 -      ?        00:00:00 accounts-d
4 S     0     897       1  0  80   0 -   637 -      ?        00:00:00 acpid
4 S     0     898       1  0  80   0 -  4180 -      ?        00:00:00 anacron
4 S   115     900       1  0  80   0 -  2133 -      ?        00:00:00 avahi-daem
4 S     0     901       1  0  80   0 -  4513 -      ?        00:00:00 cron
4 S   103     903       1  0  80   0 -  2476 -      ?        00:00:00 dbus-daemo
4 S     0     905       1  0  80   0 - 105375 -     ?        00:00:00 NetworkMan
4 S     0     913       1  0  80   0 - 20490 -      ?        00:00:00 irqbalance
4 S     0     917       1  0  80   0 - 11992 -      ?        00:00:00 networkd-d
4 S     0     920       1  0  80   0 - 63392 -      ?        00:00:01 polkitd
4 S   104     924       1  0  80   0 - 56089 -      ?        00:00:00 rsyslogd
4 S     0     932       1  1  80   0 - 440225 -     ?        00:00:02 snapd
4 S     0     933       1  0  80   0 - 61087 -      ?        00:00:00 switcheroo
4 S     0     934       1  0  80   0 -  4191 -      ?        00:00:00 systemd-lo
4 S     0     936       1  0  80   0 - 98909 -      ?        00:00:00 udisksd
4 S     0     939       1  0  80   0 -  3422 -      ?        00:00:00 wpa_suppli
1 S   115     952     900  0  80   0 -  2088 -      ?        00:00:00 avahi-daem
4 S     0     995       1  0  80   0 - 44600 -      ?        00:00:00 cups-brows
4 S     0    1000       1  0  80   0 - 78439 -      ?        00:00:00 ModemManag
1 I     0    1005       2  0  80   0 -     0 -      ?        00:00:00 kworker/15
4 S     0    1009       1  0  80   0 - 31665 -      ?        00:00:00 unattended
1 I     0    1020       2  0  80   0 -     0 -      ?        00:00:00 kworker/9:
4 S     0    1034       1  0  80   0 -  9237 -      ?        00:00:00 cupsd
4 S     0    1036       1  0  80   0 - 62062 -      ?        00:00:00 gdm3
4 S     7    1040    1034  0  80   0 -  3834 -      ?        00:00:00 dbus
4 S   120    1115       1  0  80   0 - 63382 -      ?        00:00:00 whoopsie
1 S   116    1120       1  0  80   0 -  2816 -      ?        00:00:00 kerneloops
1 S   116    1127       1  0  80   0 -  2816 -      ?        00:00:00 kerneloops
4 S   111    1148       1  0  81   1 - 38235 -      ?        00:00:00 rtkit-daem
4 S     0    1252       1  0  80   0 - 65182 -      ?        00:00:00 upowerd
4 S     0    1396       1  0  80   0 - 73507 -      ?        00:00:00 packagekit
4 S   121    1526       1  0  80   0 - 64392 -      ?        00:00:00 colord
4 S     0    1613    1036  0  80   0 - 43957 -      ?        00:00:00 gdm-sessio
4 S  1000    1621       1  0  80   0 -  4772 ep_pol ?        00:00:00 systemd
5 S  1000    1622    1621  0  80   0 - 42251 -      ?        00:00:00 (sd-pam)
0 S  1000    1627    1621  0  69 -11 - 372872 poll_s ?       00:00:00 pulseaudio
0 S  1000    1629    1621  0  99   - - 130006 poll_s ?       00:00:00 tracker-mi
0 S  1000    1632    1621  0  80   0 -  2458 ep_pol ?        00:00:00 dbus-daemo
1 S  1000    1637       1  0  80   0 - 62274 -      ?        00:00:00 gnome-keyr
0 S  1000    1640    1621  0  80   0 - 62110 poll_s ?        00:00:00 gvfsd
0 S  1000    1646    1621  0  80   0 - 95516 futex_ ?        00:00:00 gvfsd-fuse
0 S  1000    1665    1621  0  80   0 - 81521 poll_s ?        00:00:00 gvfs-udisk
0 S  1000    1672    1621  0  80   0 - 61084 poll_s ?        00:00:00 gvfs-mtp-v
0 S  1000    1676    1621  0  80   0 - 61127 poll_s ?        00:00:00 gvfs-goa-v
0 S  1000    1681    1621  0  80   0 - 138459 poll_s ?       00:00:00 goa-daemon
0 S  1000    1689    1621  0  80   0 - 81792 poll_s ?        00:00:00 goa-identi
0 S  1000    1694    1621  0  80   0 - 61653 poll_s ?        00:00:00 gvfs-gphot
0 S  1000    1699    1621  0  80   0 - 81339 poll_s ?        00:00:00 gvfs-afc-v
4 S  1000    1707    1613  0  80   0 - 43201 poll_s tty2     00:00:00 gdm-x-sess
4 S  1000    1709    1707  2  80   0 - 72180 ep_pol tty2     00:00:06 Xorg
0 S  1000    1726    1707  0  80   0 - 49864 poll_s tty2     00:00:00 gnome-sess
1 S  1000    1793    1726  0  80   0 -  1510 -      ?        00:00:00 ssh-agent
0 S  1000    1812    1621  0  80   0 - 77456 poll_s ?        00:00:00 at-spi-bus
0 S  1000    1817    1812  0  80   0 -  1812 ep_pol ?        00:00:00 dbus-daemo
0 S  1000    1821    1621  0  80   0 - 24715 poll_s ?        00:00:00 gnome-sess
0 S  1000    1828    1621  0  80   0 - 123976 poll_s ?       00:00:00 gnome-sess
0 S  1000    1842    1621  3  80   0 - 1059499 poll_s ?      00:00:08 gnome-shel
0 S  1000    1868    1842  0  80   0 - 99359 poll_s ?        00:00:00 ibus-daemo
0 S  1000    1872    1868  0  80   0 - 62322 poll_s ?        00:00:00 ibus-dconf
0 S  1000    1873    1868  0  80   0 - 71850 poll_s ?        00:00:01 ibus-exten
0 S  1000    1875    1621  0  80   0 - 52414 poll_s ?        00:00:00 ibus-x11
0 S  1000    1877    1621  0  80   0 - 62283 poll_s ?        00:00:00 ibus-porta
0 S  1000    1891    1621  0  80   0 - 40709 poll_s ?        00:00:00 at-spi2-re
0 S  1000    1895    1621  0  80   0 - 61126 poll_s ?        00:00:00 xdg-permis
0 S  1000    1900    1621  0  80   0 - 145410 poll_s ?       00:00:00 gnome-shel
0 S  1000    1906    1621  0  80   0 - 99877 poll_s ?        00:00:00 evolution-
0 S  1000    1915    1621  0  80   0 - 211969 poll_s ?       00:00:00 evolution-
0 S  1000    1918    1621  0  80   0 - 39055 poll_s ?        00:00:00 dconf-serv
0 S  1000    1928    1621  0  80   0 - 189106 poll_s ?       00:00:00 evolution-
0 S  1000    1941    1621  0  80   0 - 734855 poll_s ?       00:00:00 gjs
0 S  1000    1955    1640  0  80   0 - 81550 poll_s ?        00:00:00 gvfsd-tras
0 S  1000    1960    1621  0  80   0 - 80723 poll_s ?        00:00:00 gsd-a11y-s
0 S  1000    1961    1621  0  80   0 - 108061 poll_s ?       00:00:00 gsd-color
0 S  1000    1964    1621  0  80   0 - 95836 poll_s ?        00:00:00 gsd-dateti
0 S  1000    1967    1621  0  80   0 - 80794 poll_s ?        00:00:00 gsd-housek
0 S  1000    1971    1621  0  80   0 - 89416 poll_s ?        00:00:00 gsd-keyboa
0 S  1000    1973    1621  0  80   0 - 228227 poll_s ?       00:00:00 gsd-media-
0 S  1000    1976    1621  0  80   0 - 107951 poll_s ?       00:00:00 gsd-power
0 S  1000    1980    1828  0  80   0 - 161851 poll_s ?       00:00:00 evolution-
0 S  1000    1985    1621  0  80   0 - 64233 poll_s ?        00:00:00 gsd-print-
0 S  1000    1986    1621  0  80   0 - 116482 poll_s ?       00:00:00 gsd-rfkill
0 S  1000    1987    1621  0  80   0 - 75516 poll_s ?        00:00:00 vmtoolsd
0 S  1000    1991    1621  0  80   0 - 61084 poll_s ?        00:00:00 gsd-screen
0 S  1000    1996    1621  0  80   0 - 119470 poll_s ?       00:00:00 gsd-sharin
0 S  1000    2001    1621  0  80   0 - 81763 poll_s ?        00:00:00 gsd-smartc
0 S  1000    2002    1828  0  80   0 - 57950 poll_s ?        00:00:00 gsd-disk-u
0 S  1000    2005    1621  0  80   0 - 82691 poll_s ?        00:00:00 gsd-sound
0 S  1000    2011    1621  0  80   0 - 99213 poll_s ?        00:00:00 gsd-usb-pr
0 S  1000    2018    1621  0  80   0 - 89306 poll_s ?        00:00:00 gsd-wacom
0 S  1000    2028    1621  0  80   0 - 81804 poll_s ?        00:00:00 gsd-wwan
0 S  1000    2033    1621  0  80   0 - 89626 poll_s ?        00:00:00 gsd-xsetti
0 S  1000    2060    1621  0  80   0 - 87754 poll_s ?        00:00:00 gsd-printe
0 S  1000    2117    1868  0  80   0 - 43864 poll_s ?        00:00:00 ibus-engin
0 R  1000    2251    1621  0  80   0 - 227081 flush_ ?       00:00:01 gnome-term
0 S  1000    2260    2251  0  80   0 -  4813 do_wai pts/0    00:00:00 bash
0 S  1000    2269    1621  0  80   0 - 42747 poll_s ?        00:00:00 gvfsd-meta
0 S  1000    2272    1828  0  80   0 - 205829 poll_s ?       00:00:00 update-not
0 S  1000    2365    1828  0  80   0 - 108975 poll_s ?       00:00:00 deja-dup-m
0 R  1000    2375    2260  0  80   0 -  5017 -      pts/0    00:00:00 ps
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ ps -l
F S   UID     PID    PPID  C PRI  NI ADDR SZ WCHAN  TTY          TIME CMD
0 S  1000    2260    2251  0  80   0 -  4813 do_wai pts/0    00:00:00 bash
0 R  1000    2495    2260  0  80   0 -  5017 -      pts/0    00:00:00 ps
mao@ubuntu:~/桌面$ 
```







## top命令

