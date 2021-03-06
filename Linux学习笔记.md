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

top 命令**可以动态地持续监听进程地运行状态**，与此同时，该命令还提供了一个交互界面，用户可以根据需要，人性化地定制自己的输出，进而更清楚地了进程的运行状态。



命令：

```sh
top [选项]
```



选项：

- -d 秒数：指定 top 命令每隔几秒更新。默认是 3 秒；
- -b：使用批处理模式输出。一般和"-n"选项合用，用于把 top 命令重定向到文件中；
- -n 次数：指定 top 命令执行的次数。一般和"-"选项合用；
- -p 进程PID：仅查看指定 ID 的进程；
- -s：使 top 命令在安全模式中运行，避免在交互模式中出现错误；
- -u 用户名：只监听某个用户的进程；



在 top 命令的显示窗口中，还可以使用如下按键，进行一下交互操作：

- ? 或 h：显示交互模式的帮助；
- P：按照 CPU 的使用率排序，默认就是此选项；
- M：按照内存的使用率排序；
- N：按照 PID 排序；
- T：按照 CPU 的累积运算时间排序，也就是按照 TIME+ 项排序；
- k：按照 PID 给予某个进程一个信号。一般用于中止某个进程，信号 9 是强制中止的信号；
- r：按照 PID 给某个进程重设优先级（Nice）值；
- q：退出 top 命令；



```sh
mao@ubuntu:~/桌面$ top

top - 06:26:05 up 18 min,  1 user,  load average: 0.09, 0.09, 0.08
任务: 403 total,   1 running, 402 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.3 us,  0.1 sy,  0.0 ni, 99.6 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2052.6 free,    968.0 used,    880.9 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2694.4 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND  
   1709 mao       20   0  288504  63956  39756 S   6.0   1.6   0:13.07 Xorg     
   2251 mao       20   0  910848  64848  48036 S   3.3   1.6   0:03.57 gnome-t+ 
   1842 mao       20   0 4238056 256756 114024 S   2.7   6.4   0:11.18 gnome-s+ 
   1987 mao       20   0  302064  42716  30616 S   0.7   1.1   0:02.57 vmtoolsd 
   1873 mao       20   0  287400  33892  20100 S   0.3   0.8   0:01.03 ibus-ex+ 
   2018 mao       20   0  357224  30812  20508 S   0.3   0.8   0:00.40 gsd-wac+ 
   2272 mao       20   0  823316  57544  44396 S   0.3   1.4   0:00.30 update-+ 
   2790 mao       20   0   20804   3944   3168 R   0.3   0.1   0:00.03 top      
      1 root      20   0  168676  12744   8352 S   0.0   0.3   0:08.09 systemd  
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.05 kthreadd 
      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp   
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par+ 
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+ 
      7 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker+ 
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 mm_perc+ 
     10 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_tas+ 
     11 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_tas+ 
mao@ubuntu:~/桌面$ 
```



1. 第一部分是前五行，显示的是整个系统的资源使用状况，我们就是通过这些输出来判断服务器的资源使用状态的；
2. 第二部分从第六行开始，显示的是系统中进程的信息；





### 第一部分

第一行为任务队列信息



|             内 容              |                            说 明                             |
| :----------------------------: | :----------------------------------------------------------: |
|            06:26:05            |                         系统当前时间                         |
|           up 18 min            |             系统的运行时间.本机己经运行 18 分钟              |
|             1 user             |                      当前登录了1个用户                       |
| load average: 0.09, 0.09, 0.08 | 系统在之前 1 分钟、5 分钟、15 分钟的平均负载。如果 CPU 是单核的，则这个数值超过 1 就是高负载：如果 CPU 是四核的，则这个数值超过 4 就是高负载 （这个平均负载完全是依据个人经验来进行判断的，一般认为不应该超过服务器 CPU 的核数） |



第二行为进程信息



|      内 容      |                     说 明                      |
| :-------------: | :--------------------------------------------: |
| 任务: 403 total |                系统中的进程总数                |
|    1 running    |                正在运行的进程数                |
|  402 sleeping   |                  睡眠的进程数                  |
|    0 stopped    |                正在停止的进程数                |
|    0 zombie     | 僵尸进程数。如果不是 0，则需要手工检查僵尸进程 |





第三行为 CPU 信息



|      内 容       |                            说 明                             |
| :--------------: | :----------------------------------------------------------: |
| %Cpu(s):  0.3 us |                  用户模式占用的 CPU 百分比                   |
|      0.1 sy      |                  系统模式占用的 CPU 百分比                   |
|      0.0 ni      |           改变过优先级的用户进程占用的 CPU 百分比            |
|     99.6 id      |                  空闲 CPU 占用的 CPU 百分比                  |
|      0.0 wa      |             等待输入/输出的进程占用的 CPU 百分比             |
|      0.0 hi      |               硬中断请求服务占用的 CPU 百分比                |
|      0.0 si      |               软中断请求服务占用的 CPU 百分比                |
|      0.0 st      | st（steal time）意为虚拟时间百分比，就是当有虚拟机时，虚拟 CPU 等待实际 CPU 的时间百分比 |



第四行为物理内存信息



|          内 容           |          说 明           |
| :----------------------: | :----------------------: |
| MiB Mem :   3901.4 total | 物理内存的总量，单位为MB |
|        968.0 used        |  己经使用的物理内存数量  |
|       2052.6 free        |    空闲的物理内存数量    |
|     880.9 buff/cache     |    作为缓冲的内存数量    |



第五行为交换分区（swap）信息



|          内 容           |            说 明             |
| :----------------------: | :--------------------------: |
| MiB Swap:    687.5 total | 交换分区（虚拟内存）的总大小 |
|         0.0 used         |   已经使用的交换分区的大小   |
|        687.5 free        |      空闲交换分区的大小      |
|     2694.4 avail Mem     |   作为缓存的交换分区的大小   |





缓冲（buffer）和缓存（cache）的区别：

- 缓存（cache）是在读取硬盘中的数据时，把最常用的数据保存在内存的缓存区中，再次读取该数据时，就不去硬盘中读取了，而在缓存中读取。
- 缓冲（buffer）是在向硬盘写入数据时，先把数据放入缓冲区,然后再一起向硬盘写入，把分散的写操作集中进行，减少磁盘碎片和硬盘的反复寻道，从而提高系统性能。



简单来说，缓存（cache）是用来加速数据从硬盘中"读取"的，而缓冲（buffer）是用来加速数据"写入"硬盘的。





### 第二部分



- PID：进程的 ID。
- USER：该进程所属的用户。
- PR：优先级，数值越小优先级越高。
- NI：优先级，数值越小、优先级越高。
- VIRT：该进程使用的虚拟内存的大小，单位为 KB。
- RES：该进程使用的物理内存的大小，单位为 KB。
- SHR：共享内存大小，单位为 KB。
- S：进程状态。
- %CPU：该进程占用 CPU 的百分比。
- %MEM：该进程占用内存的百分比。
- TIME+：该进程共占用的 CPU 时间。
- COMMAND：进程的命令名。





### 示例

1. 用top 命令查看某个进程：

例如查看进程号为1的进程：

```sh
top -p 1
```



```sh
任务:   1 total,   0 running,   1 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2048.9 free,    970.1 used,    882.4 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2692.8 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND  
      1 root      20   0  168676  12744   8352 S   0.0   0.3   0:08.11 systemd  
```





2. 按照内存的使用率排序：

输入top命令后按M键



```sh
mao@ubuntu:~/桌面$ top

top - 06:47:54 up 39 min,  1 user,  load average: 0.08, 0.02, 0.01
任务: 396 total,   1 running, 395 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   1990.5 free,   1028.4 used,    882.5 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2634.5 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND              
   1842 mao       20   0 4286708 256984 114168 S   1.0   6.4   0:15.53 gnome-shell          
   1709 mao       20   0  300612  73980  39792 S   2.0   1.9   0:19.92 Xorg                 
   2251 mao       20   0  910848  64920  48108 S   1.3   1.6   0:06.11 gnome-terminal-      
   1980 mao       20   0  647404  62052  45940 S   0.0   1.6   0:00.48 evolution-alarm      
   2272 mao       20   0  823316  57544  44396 S   0.0   1.4   0:00.36 update-notifier      
   1987 mao       20   0  302064  42716  30616 S   0.3   1.1   0:05.54 vmtoolsd             
   2699 root      20   0 1613444  41008  19936 S   0.0   1.0   0:02.39 snapd                
   1681 mao       20   0  553836  36612  30696 S   0.0   0.9   0:00.09 goa-daemon           
   1873 mao       20   0  287400  33892  20100 S   0.0   0.8   0:01.05 ibus-extension-      
    484 root      19  -1   74956  33820  32196 S   0.0   0.8   0:00.81 systemd-journal      
   1928 mao       20   0  756424  33656  27752 S   0.0   0.8   0:00.22 evolution-addre      
   1973 mao       20   0  912908  33248  22504 S   0.0   0.8   0:00.43 gsd-media-keys       
   2033 mao       20   0  358504  32236  21400 S   0.0   0.8   0:00.45 gsd-xsettings        
   1976 mao       20   0  431804  31676  21324 S   0.0   0.8   0:00.44 gsd-power            
   1961 mao       20   0  432244  31668  21368 S   0.0   0.8   0:00.37 gsd-color            
   1971 mao       20   0  357664  31212  20888 S   0.3   0.8   0:00.41 gsd-keyboard         
   2018 mao       20   0  357224  30812  20508 S   0.0   0.8   0:00.42 gsd-wacom            
   1915 mao       20   0  847876  30692  26888 S   0.0   0.8   0:00.19 evolution-calen      
   1875 mao       20   0  209656  30568  20520 S   0.0   0.8   0:00.37 ibus-x11             
   1941 mao       20   0 2939420  27196  22056 S   0.0   0.7   0:00.07 gjs                  
   1906 mao       20   0  399508  26900  23060 S   0.0   0.7   0:00.11 evolution-sourc      
mao@ubuntu:~/桌面$ 
```







3. top 命令重定向到文件中

```sh
mao@ubuntu:~/桌面$ top -n 1 -b >> out.txt 
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ cat -n out.txt
     1	top - 06:51:34 up 43 min,  1 user,  load average: 0.09, 0.04, 0.00
     2	任务: 397 total,   2 running, 395 sleeping,   0 stopped,   0 zombie
     3	%Cpu(s):  6.5 us,  0.4 sy,  0.0 ni, 93.1 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
     4	MiB Mem :   3901.4 total,   1990.0 free,   1028.7 used,    882.8 buff/cache
     5	MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2634.1 avail Mem 
     6	
     7	 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND
     8	   1842 mao       20   0 4548892 257396 114384 R 106.7   6.4   0:17.56 gnome-shell
     9	   1709 mao       20   0  300612  73980  39792 S   6.7   1.9   0:24.22 Xorg
    10	   2269 mao       20   0  171028   6392   5804 S   6.7   0.2   0:00.01 gvfsd-metadata
    11	   2827 mao       20   0   20808   4072   3348 R   6.7   0.1   0:00.01 top
    12	      1 root      20   0  168676  12744   8352 S   0.0   0.3   0:08.12 systemd
    13	      2 root      20   0       0      0      0 S   0.0   0.0   0:00.05 kthreadd
    14	      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp
    15	      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par_gp
    16	      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-kblockd
    17	      7 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/0:1-events
    18	      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 mm_percpu_wq
    19	     10 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_tasks_rude_
    20	     11 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_tasks_trace
    21	     12 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/0
    22	     13 root      20   0       0      0      0 I   0.0   0.0   0:01.07 rcu_sched
    23	     14 root      rt   0       0      0      0 S   0.0   0.0   0:00.05 migration/0
    24	     15 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
    25	     16 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
    26	     17 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
    27	     18 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
    28	     19 root      rt   0       0      0      0 S   0.0   0.0   0:00.91 migration/1
    29	     20 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/1
    30	     22 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/1:0H-kblockd
    31	     23 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
    32	     24 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
    33	     25 root      rt   0       0      0      0 S   0.0   0.0   0:00.92 migration/2
    34	     26 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/2
    35	     28 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/2:0H-kblockd
    36	     29 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
    37	     30 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/3
    38	     31 root      rt   0       0      0      0 S   0.0   0.0   0:00.93 migration/3
    39	     32 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/3
    40	     34 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/3:0H-events+
    41	     35 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/4
    42	     36 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/4
    43	     37 root      rt   0       0      0      0 S   0.0   0.0   0:00.95 migration/4
    44	     38 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/4
    45	     40 root       0 -20       0      0      0 I   0.0   0.0   0:00.01 kworker/4:0H-kblockd
    46	     41 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/5
    47	     42 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/5
    48	     43 root      rt   0       0      0      0 S   0.0   0.0   0:00.95 migration/5
    49	     44 root      20   0       0      0      0 S   0.0   0.0   0:00.02 ksoftirqd/5
    50	     46 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/5:0H-kblockd
    51	     47 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/6
    52	     48 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/6
    53	     49 root      rt   0       0      0      0 S   0.0   0.0   0:00.96 migration/6
    54	     50 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/6
    55	     52 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/6:0H-events+
    56	     53 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/7
    57	     54 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/7
    58	     55 root      rt   0       0      0      0 S   0.0   0.0   0:00.96 migration/7
    59	     56 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/7
    60	     58 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/7:0H-events+
    61	     59 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/8
    62	     60 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/8
    63	     61 root      rt   0       0      0      0 S   0.0   0.0   0:00.97 migration/8
    64	     62 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/8
    65	     64 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/8:0H-kblockd
    66	     65 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/9
    67	     66 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/9
    68	     67 root      rt   0       0      0      0 S   0.0   0.0   0:00.97 migration/9
    69	     68 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/9
    70	     70 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/9:0H-events+
    71	     71 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/10
    72	     72 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/10
    73	     73 root      rt   0       0      0      0 S   0.0   0.0   0:00.99 migration/10
    74	     74 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/10
    75	     76 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/10:0H-event+
    76	     77 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/11
    77	     78 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/11
    78	     79 root      rt   0       0      0      0 S   0.0   0.0   0:00.99 migration/11
    79	     80 root      20   0       0      0      0 S   0.0   0.0   0:00.10 ksoftirqd/11
    80	     82 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/11:0H-event+
    81	     83 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/12
    82	     84 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/12
    83	     85 root      rt   0       0      0      0 S   0.0   0.0   0:01.01 migration/12
    84	     86 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/12
    85	     88 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/12:0H-event+
    86	     89 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/13
    87	     90 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/13
    88	     91 root      rt   0       0      0      0 S   0.0   0.0   0:01.01 migration/13
    89	     92 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/13
    90	     94 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/13:0H-event+
    91	     95 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/14
    92	     96 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/14
    93	     97 root      rt   0       0      0      0 S   0.0   0.0   0:01.02 migration/14
    94	     98 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/14
    95	    100 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/14:0H-event+
    96	    101 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/15
    97	    102 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/15
    98	    103 root      rt   0       0      0      0 S   0.0   0.0   0:01.02 migration/15
    99	    104 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/15
   100	    105 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/15:0-rcu_pa+
   101	    106 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/15:0H-event+
   102	    107 root      20   0       0      0      0 S   0.0   0.0   0:00.01 kdevtmpfs
   103	    108 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 netns
   104	    109 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 inet_frag_wq
   105	    110 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kauditd
   106	    111 root      20   0       0      0      0 I   0.0   0.0   0:00.17 kworker/0:2-events
   107	    114 root      20   0       0      0      0 S   0.0   0.0   0:00.00 khungtaskd
   108	    115 root      20   0       0      0      0 S   0.0   0.0   0:00.00 oom_reaper
   109	    116 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 writeback
   110	    117 root      20   0       0      0      0 S   0.0   0.0   0:00.22 kcompactd0
   111	    118 root      25   5       0      0      0 S   0.0   0.0   0:00.00 ksmd
   112	    119 root      39  19       0      0      0 S   0.0   0.0   0:00.00 khugepaged
   113	    166 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kintegrityd
   114	    167 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kblockd
   115	    168 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 blkcg_punt_bio
   116	    170 root      20   0       0      0      0 I   0.0   0.0   0:00.11 kworker/8:1-events
   117	    171 root      20   0       0      0      0 I   0.0   0.0   0:00.08 kworker/3:1-rcu_gp
   118	    172 root      20   0       0      0      0 I   0.0   0.0   0:00.06 kworker/4:1-rcu_gp
   119	    173 root      20   0       0      0      0 I   0.0   0.0   0:00.54 kworker/6:1-events
   120	    174 root      20   0       0      0      0 I   0.0   0.0   0:00.08 kworker/5:1-rcu_gp
   121	    175 root      20   0       0      0      0 I   0.0   0.0   0:00.23 kworker/7:1-events
   122	    180 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/13:1-events
   123	    181 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/14:1-events
   124	    182 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 tpm_dev_wq
   125	    183 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 ata_sff
   126	    184 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 md
   127	    185 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 edac-poller
   128	    186 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 devfreq_wq
   129	    187 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 watchdogd
   130	    189 root      20   0       0      0      0 I   0.0   0.0   0:00.08 kworker/2:2-events
   131	    190 root       0 -20       0      0      0 I   0.0   0.0   0:00.01 kworker/3:1H-kblockd
   132	    192 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kswapd0
   133	    193 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ecryptfs-kthrea
   134	    195 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kthrotld
   135	    196 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/24-pciehp
   136	    197 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/25-pciehp
   137	    198 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/26-pciehp
   138	    199 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/27-pciehp
   139	    200 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/28-pciehp
   140	    201 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/29-pciehp
   141	    202 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/30-pciehp
   142	    203 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/31-pciehp
   143	    204 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/32-pciehp
   144	    205 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/33-pciehp
   145	    206 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/34-pciehp
   146	    207 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/35-pciehp
   147	    208 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/36-pciehp
   148	    209 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/37-pciehp
   149	    210 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/38-pciehp
   150	    211 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/39-pciehp
   151	    212 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/40-pciehp
   152	    213 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/41-pciehp
   153	    214 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/42-pciehp
   154	    215 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/43-pciehp
   155	    216 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/44-pciehp
   156	    217 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/45-pciehp
   157	    218 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/46-pciehp
   158	    219 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/47-pciehp
   159	    220 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/48-pciehp
   160	    221 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/49-pciehp
   161	    222 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/50-pciehp
...
...
...
   280	    529 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 card0-crtc7
   281	    531 root      20   0   24140   7404   3892 S   0.0   0.2   0:00.67 systemd-udevd
   282	    532 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop2
   283	    539 root      20   0       0      0      0 I   0.0   0.0   0:00.13 kworker/1:3-mm_perc+
   284	    540 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop3
   285	    543 root      20   0  150668    320     56 S   0.0   0.0   0:00.00 vmware-vmblock-
   286	    546 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop4
   287	    547 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop5
   288	    548 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop6
   289	    549 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop7
   290	    580 root       0 -20       0      0      0 S   0.0   0.0   0:00.32 loop8
   291	    617 root       0 -20       0      0      0 S   0.0   0.0   0:00.02 loop9
   292	    632 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop10
   293	    656 root       0 -20       0      0      0 S   0.0   0.0   0:00.02 loop11
   294	    694 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 cryptd
   295	    715 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop12
   296	    768 root       0 -20       0      0      0 S   0.0   0.0   0:00.01 loop13
   297	    872 systemd+  20   0   23904  11940   8016 S   0.0   0.3   0:00.20 systemd-resolve
   298	    873 systemd+  20   0   90260   6020   5248 S   0.0   0.2   0:00.11 systemd-timesyn
   299	    876 root      20   0   58772  10660   9220 S   0.0   0.3   0:00.02 VGAuthService
   300	    879 root      20   0  248076   7420   6408 S   0.0   0.2   0:05.84 vmtoolsd
   301	    896 root      20   0  250532   9508   8472 S   0.0   0.2   0:00.19 accounts-daemon
   302	    897 root      20   0    2548    712    644 S   0.0   0.0   0:00.07 acpid
   303	    900 avahi     20   0    8532   3480   3156 S   0.0   0.1   0:00.16 avahi-daemon
   304	    901 root      20   0   18052   3224   3012 S   0.0   0.1   0:00.01 cron
   305	    903 message+  20   0    9904   6520   3984 S   0.0   0.2   0:01.05 dbus-daemon
   306	    905 root      20   0  421500  22544  18924 S   0.0   0.6   0:01.05 NetworkManager
   307	    913 root      20   0   81960   3776   3404 S   0.0   0.1   0:00.15 irqbalance
   308	    917 root      20   0   47968  20068  11836 S   0.0   0.5   0:00.28 networkd-dispat
   309	    920 root      20   0  253568  13720   9592 S   0.0   0.3   0:01.64 polkitd
   310	    924 syslog    20   0  224356   4792   3756 S   0.0   0.1   0:00.30 rsyslogd
   311	    933 root      20   0  244348   6752   6080 S   0.0   0.2   0:00.04 switcheroo-cont
   312	    934 root      20   0   16764   8052   6988 S   0.0   0.2   0:00.30 systemd-logind
   313	    936 root      20   0  395636  14416  12008 S   0.0   0.4   0:00.15 udisksd
   314	    939 root      20   0   13688   4988   4400 S   0.0   0.1   0:00.07 wpa_supplicant
   315	    952 avahi     20   0    8352    324      0 S   0.0   0.0   0:00.00 avahi-daemon
   316	    995 root      20   0  178400  12832  11184 S   0.0   0.3   0:00.12 cups-browsed
   317	   1000 root      20   0  313756  10376   8704 S   0.0   0.3   0:00.15 ModemManager
   318	   1005 root      20   0       0      0      0 I   0.0   0.0   0:00.17 kworker/15:3-events
   319	   1009 root      20   0  126660  22696  14560 S   0.0   0.6   0:00.17 unattended-upgr
   320	   1034 root      20   0   36948   8636   7304 S   0.0   0.2   0:00.02 cupsd
   321	   1036 root      20   0  248248   8864   7640 S   0.0   0.2   0:00.06 gdm3
   322	   1040 lp        20   0   15336   6580   5780 S   0.0   0.2   0:00.01 dbus
   323	   1115 whoopsie  20   0  253528  15984  14028 S   0.0   0.4   0:00.04 whoopsie
   324	   1120 kernoops  20   0   11264    448      0 S   0.0   0.0   0:00.05 kerneloops
   325	   1127 kernoops  20   0   11264    448      0 S   0.0   0.0   0:00.04 kerneloops
   326	   1148 rtkit     21   1  152940   3084   2852 S   0.0   0.1   0:00.12 rtkit-daemon
   327	   1252 root      20   0  260728   9704   8548 S   0.0   0.2   0:00.10 upowerd
   328	   1526 colord    20   0  257568  16904  11664 S   0.0   0.4   0:00.18 colord
   329	   1613 root      20   0  175828   9716   8196 S   0.0   0.2   0:00.02 gdm-session-wor
   330	   1621 mao       20   0   19088  10312   8044 S   0.0   0.3   0:00.42 systemd
   331	   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam)
   332	   1627 mao        9 -11 1753632  20316  15596 S   0.0   0.5   0:00.33 pulseaudio
   333	   1629 mao       39  19  520024  24788  16660 S   0.0   0.6   0:00.18 tracker-miner-f
   334	   1632 mao       20   0    9832   7036   3888 S   0.0   0.2   0:00.52 dbus-daemon
   335	   1637 mao       20   0  249096   7832   6856 S   0.0   0.2   0:00.06 gnome-keyring-d
   336	   1640 mao       20   0  248440   7936   6948 S   0.0   0.2   0:00.06 gvfsd
   337	   1646 mao       20   0  382064   8228   7368 S   0.0   0.2   0:00.01 gvfsd-fuse
   338	   1665 mao       20   0  326084  11452   9852 S   0.0   0.3   0:00.11 gvfs-udisks2-vo
   339	   1672 mao       20   0  244336   6260   5676 S   0.0   0.2   0:00.02 gvfs-mtp-volume
   340	   1676 mao       20   0  244508   6272   5760 S   0.0   0.2   0:00.02 gvfs-goa-volume
   341	   1681 mao       20   0  553836  36612  30696 S   0.0   0.9   0:00.09 goa-daemon
   342	   1689 mao       20   0  327168  11496  10196 S   0.0   0.3   0:00.05 goa-identity-se
   343	   1694 mao       20   0  246612   6836   6140 S   0.0   0.2   0:00.02 gvfs-gphoto2-vo
   344	   1699 mao       20   0  325356   9248   8260 S   0.0   0.2   0:00.26 gvfs-afc-volume
   345	   1707 mao       20   0  172804   6484   5848 S   0.0   0.2   0:00.02 gdm-x-session
   346	   1726 mao       20   0  199456  15684  13920 S   0.0   0.4   0:00.06 gnome-session-b
   347	   1793 mao       20   0    6040    456      0 S   0.0   0.0   0:00.02 ssh-agent
   348	   1812 mao       20   0  309824   9156   8288 S   0.0   0.2   0:00.02 at-spi-bus-laun
   349	   1817 mao       20   0    7248   4392   3924 S   0.0   0.1   0:00.06 dbus-daemon
   350	   1821 mao       20   0   98860   4428   4012 S   0.0   0.1   0:00.00 gnome-session-c
   351	   1828 mao       20   0  495904  17976  15288 S   0.0   0.4   0:00.20 gnome-session-b
   352	   1868 mao       20   0  397436  10608   8936 S   0.0   0.3   0:00.05 ibus-daemon
   353	   1872 mao       20   0  249288   9096   8348 S   0.0   0.2   0:00.01 ibus-dconf
   354	   1873 mao       20   0  287400  33892  20100 S   0.0   0.8   0:01.07 ibus-extension-
   355	   1875 mao       20   0  209656  30568  20520 S   0.0   0.8   0:00.38 ibus-x11
   356	   1877 mao       20   0  249132   9184   8428 S   0.0   0.2   0:00.05 ibus-portal
   357	   1891 mao       20   0  162836   7448   6668 S   0.0   0.2   0:00.74 at-spi2-registr
   358	   1895 mao       20   0  244504   4736   4300 S   0.0   0.1   0:00.01 xdg-permission-
   359	   1900 mao       20   0  581640  21092  18384 S   0.0   0.5   0:00.15 gnome-shell-cal
   360	   1906 mao       20   0  399508  26900  23060 S   0.0   0.7   0:00.11 evolution-sourc
   361	   1915 mao       20   0  847876  30692  26888 S   0.0   0.8   0:00.19 evolution-calen
   362	   1918 mao       20   0  156220   5536   4968 S   0.0   0.1   0:00.01 dconf-service
   363	   1928 mao       20   0  756424  33656  27752 S   0.0   0.8   0:00.22 evolution-addre
   364	   1941 mao       20   0 2939420  27196  22056 S   0.0   0.7   0:00.07 gjs
   365	   1955 mao       20   0  326200  10676   9388 S   0.0   0.3   0:00.06 gvfsd-trash
   366	   1960 mao       20   0  322892   9220   8336 S   0.0   0.2   0:00.02 gsd-a11y-settin
   367	   1961 mao       20   0  432244  31668  21368 S   0.0   0.8   0:00.40 gsd-color
   368	   1964 mao       20   0  383344  17448  15328 S   0.0   0.4   0:00.04 gsd-datetime
   369	   1967 mao       20   0  323176   9980   8976 S   0.0   0.2   0:00.11 gsd-housekeepin
   370	   1971 mao       20   0  357664  31212  20888 S   0.0   0.8   0:00.43 gsd-keyboard
   371	   1973 mao       20   0  912908  33248  22504 S   0.0   0.8   0:00.46 gsd-media-keys
   372	   1976 mao       20   0  431804  31676  21324 S   0.0   0.8   0:00.46 gsd-power
   373	   1980 mao       20   0  647404  62052  45940 S   0.0   1.6   0:00.50 evolution-alarm
   374	   1985 mao       20   0  256932  11432  10024 S   0.0   0.3   0:00.03 gsd-print-notif
   375	   1986 mao       20   0  465928   6268   5652 S   0.0   0.2   0:00.03 gsd-rfkill
   376	   1987 mao       20   0  302064  42716  30616 S   0.0   1.1   0:05.99 vmtoolsd
   377	   1991 mao       20   0  244336   6368   5784 S   0.0   0.2   0:00.01 gsd-screensaver
   378	   1996 mao       20   0  477880  12512  11060 S   0.0   0.3   0:00.04 gsd-sharing
   379	   2001 mao       20   0  327052  10892   9816 S   0.0   0.3   0:00.03 gsd-smartcard
   380	   2002 mao       20   0  231800   5648   4608 S   0.0   0.1   0:00.05 gsd-disk-utilit
   381	   2005 mao       20   0  330764  11076   9824 S   0.0   0.3   0:00.03 gsd-sound
   382	   2011 mao       20   0  396852   9532   8572 S   0.0   0.2   0:00.03 gsd-usb-protect
   383	   2018 mao       20   0  357224  30812  20508 S   0.0   0.8   0:00.44 gsd-wacom
   384	   2028 mao       20   0  327216  10652   9484 S   0.0   0.3   0:00.04 gsd-wwan
   385	   2033 mao       20   0  358504  32236  21400 S   0.0   0.8   0:00.48 gsd-xsettings
   386	   2060 mao       20   0  351016  15308  13416 S   0.0   0.4   0:00.04 gsd-printer
   387	   2117 mao       20   0  175456   9064   8328 S   0.0   0.2   0:00.02 ibus-engine-sim
   388	   2251 mao       20   0  910848  64920  48108 S   0.0   1.6   0:07.39 gnome-terminal-
   389	   2260 mao       20   0   19252   4824   3376 S   0.0   0.1   0:00.05 bash
   390	   2272 mao       20   0  823316  57544  44396 S   0.0   1.4   0:00.39 update-notifier
   391	   2482 root      20   0       0      0      0 I   0.0   0.0   0:00.06 kworker/9:0-events
   392	   2483 root      20   0       0      0      0 I   0.0   0.0   0:00.09 kworker/10:0-events
   393	   2485 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/12:0
   394	   2489 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/1:0-events
   395	   2657 root      20   0       0      0      0 I   0.0   0.0   0:00.14 kworker/u256:1-even+
   396	   2683 root       0 -20       0      0      0 S   0.0   0.0   0:00.02 loop14
   397	   2699 root      20   0 1613444  41008  19936 S   0.0   1.0   0:02.41 snapd
   398	   2738 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/2:0
   399	   2768 root      20   0       0      0      0 I   0.0   0.0   0:00.01 kworker/3:0-events
   400	   2769 root      20   0       0      0      0 I   0.0   0.0   0:00.08 kworker/4:0-events
   401	   2779 root      20   0       0      0      0 I   0.0   0.0   0:00.10 kworker/5:0-events
   402	   2782 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/9:1-cgroup_+
   403	   2807 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/11:1-cgroup+
   404	   2826 root      20   0       0      0      0 I   0.0   0.0   0:00.01 kworker/u256:0-even+
mao@ubuntu:~/桌面$ 
```





4. 只监听用户mao的进程

```sh
top -u mao
```



```sh
mao@ubuntu:~/桌面$ top -u mao

top - 06:55:52 up 47 min,  1 user,  load average: 0.07, 0.11, 0.04
任务: 397 total,   1 running, 396 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   1988.5 free,   1020.2 used,    892.7 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2642.3 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND              
   1709 mao       20   0  300828  74120  39932 S   3.7   1.9   0:44.74 Xorg                 
   2251 mao       20   0  910848  65796  48968 S   1.3   1.6   0:10.77 gnome-terminal-      
   1842 mao       20   0 4538024 257564 114384 S   1.0   6.4   0:25.28 gnome-shell          
   1987 mao       20   0  302064  42716  30616 S   0.3   1.1   0:06.59 vmtoolsd             
   2882 mao       20   0   20808   4096   3312 R   0.3   0.1   0:00.01 top                  
   1621 mao       20   0   19088  10312   8044 S   0.0   0.3   0:00.42 systemd              
   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam)             
   1627 mao        9 -11 1753632  20320  15600 S   0.0   0.5   0:00.34 pulseaudio           
   1629 mao       39  19  520164  24872  16744 S   0.0   0.6   0:00.19 tracker-miner-f      
   1632 mao       20   0    9832   7036   3888 S   0.0   0.2   0:00.59 dbus-daemon          
   1637 mao       20   0  249096   7832   6856 S   0.0   0.2   0:00.08 gnome-keyring-d      
   1640 mao       20   0  248440   7936   6948 S   0.0   0.2   0:00.06 gvfsd                
   1646 mao       20   0  382064   8228   7368 S   0.0   0.2   0:00.01 gvfsd-fuse           
   1665 mao       20   0  326084  11452   9852 S   0.0   0.3   0:00.12 gvfs-udisks2-vo      
   1672 mao       20   0  244336   6260   5676 S   0.0   0.2   0:00.03 gvfs-mtp-volume      
   1676 mao       20   0  244508   6272   5760 S   0.0   0.2   0:00.02 gvfs-goa-volume      
   1681 mao       20   0  553836  36612  30696 S   0.0   0.9   0:00.09 goa-daemon           
   1689 mao       20   0  327168  11496  10196 S   0.0   0.3   0:00.05 goa-identity-se      
   1694 mao       20   0  246612   6836   6140 S   0.0   0.2   0:00.03 gvfs-gphoto2-vo      
   1699 mao       20   0  325356   9248   8260 S   0.0   0.2   0:00.30 gvfs-afc-volume      
   1707 mao       20   0  172804   6484   5848 S   0.0   0.2   0:00.02 gdm-x-session        
mao@ubuntu:~/桌面$ 
```







5. 终止任务

输入top -u mao 命令后按k键

```sh
mao@ubuntu:~/桌面$ top -u mao

top - 06:57:52 up 49 min,  1 user,  load average: 0.05, 0.10, 0.04
任务: 397 total,   1 running, 396 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   1987.8 free,   1021.0 used,    892.7 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2641.5 avail Mem 
PID to signal/kill [default pid = 1709] 
 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND              
   1709 mao       20   0  300612  74120  39932 S   2.0   1.9   0:46.12 Xorg                 
   2251 mao       20   0  910848  65796  48968 S   1.3   1.6   0:11.22 gnome-terminal-      
   1842 mao       20   0 4538020 257564 114384 S   1.0   6.4   0:26.01 gnome-shell          
   1891 mao       20   0  162836   7448   6668 S   0.3   0.2   0:01.24 at-spi2-registr      
   2885 mao       20   0   20808   4164   3380 R   0.3   0.1   0:00.02 top                  
   1621 mao       20   0   19088  10312   8044 S   0.0   0.3   0:00.42 systemd              
   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam)             
   1627 mao        9 -11 1753632  20320  15600 S   0.0   0.5   0:00.34 pulseaudio           
   1629 mao       39  19  520164  24872  16744 S   0.0   0.6   0:00.19 tracker-miner-f      
   1632 mao       20   0    9832   7036   3888 S   0.0   0.2   0:00.59 dbus-daemon          
   1637 mao       20   0  249096   7832   6856 S   0.0   0.2   0:00.08 gnome-keyring-d      
   1640 mao       20   0  248440   7936   6948 S   0.0   0.2   0:00.06 gvfsd                
   1646 mao       20   0  382064   8228   7368 S   0.0   0.2   0:00.01 gvfsd-fuse           
   1665 mao       20   0  326084  11452   9852 S   0.0   0.3   0:00.12 gvfs-udisks2-vo      
   1672 mao       20   0  244336   6260   5676 S   0.0   0.2   0:00.03 gvfs-mtp-volume      
   1676 mao       20   0  244508   6272   5760 S   0.0   0.2   0:00.02 gvfs-goa-volume      
   1681 mao       20   0  553836  36612  30696 S   0.0   0.9   0:00.09 goa-daemon           
   1689 mao       20   0  327168  11496  10196 S   0.0   0.3   0:00.05 goa-identity-se      
   1694 mao       20   0  246612   6836   6140 S   0.0   0.2   0:00.03 gvfs-gphoto2-vo      
   1699 mao       20   0  325356   9248   8260 S   0.0   0.2   0:00.31 gvfs-afc-volume      
   1707 mao       20   0  172804   6484   5848 S   0.0   0.2   0:00.02 gdm-x-session        
```



输入信号，信号9代表强制中止

```sh
top - 06:59:27 up 51 min,  1 user,  load average: 0.01, 0.07, 0.03
任务: 397 total,   1 running, 396 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.4 us,  0.0 sy,  0.0 ni, 99.6 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   1987.8 free,   1021.0 used,    892.7 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2641.5 avail Mem 
Send pid 1709 signal [15/sigterm] 
 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND              
   1709 mao       20   0  300612  74120  39932 S   6.7   1.9   0:47.53 Xorg                 
   1842 mao       20   0 4538020 257528 114384 S   6.7   6.4   0:26.68 gnome-shell          
   1621 mao       20   0   19088  10312   8044 S   0.0   0.3   0:00.42 systemd              
   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam)             
   1627 mao        9 -11 1753632  20320  15600 S   0.0   0.5   0:00.34 pulseaudio           
   1629 mao       39  19  520164  24872  16744 S   0.0   0.6   0:00.19 tracker-miner-f      
   1632 mao       20   0    9832   7036   3888 S   0.0   0.2   0:00.60 dbus-daemon          
   1637 mao       20   0  249096   7832   6856 S   0.0   0.2   0:00.08 gnome-keyring-d      
   1640 mao       20   0  248440   7936   6948 S   0.0   0.2   0:00.06 gvfsd                
   1646 mao       20   0  382064   8228   7368 S   0.0   0.2   0:00.01 gvfsd-fuse           
   1665 mao       20   0  326084  11452   9852 S   0.0   0.3   0:00.12 gvfs-udisks2-vo      
   1672 mao       20   0  244336   6260   5676 S   0.0   0.2   0:00.03 gvfs-mtp-volume      
   1676 mao       20   0  244508   6272   5760 S   0.0   0.2   0:00.02 gvfs-goa-volume      
   1681 mao       20   0  553836  36612  30696 S   0.0   0.9   0:00.09 goa-daemon           
   1689 mao       20   0  327168  11496  10196 S   0.0   0.3   0:00.05 goa-identity-se      
   1694 mao       20   0  246612   6836   6140 S   0.0   0.2   0:00.03 gvfs-gphoto2-vo      
   1699 mao       20   0  325356   9248   8260 S   0.0   0.2   0:00.31 gvfs-afc-volume      
   1707 mao       20   0  172804   6484   5848 S   0.0   0.2   0:00.02 gdm-x-session        
   1726 mao       20   0  199456  15684  13920 S   0.0   0.4   0:00.06 gnome-session-b      
   1793 mao       20   0    6040    456      0 S   0.0   0.0   0:00.02 ssh-agent            
   1812 mao       20   0  309824   9156   8288 S   0.0   0.2   0:00.02 at-spi-bus-laun      

```





6. 改变某个进程的优先级

使用用 "r" 交互命令。我们能够修改的只有 Nice 的优先级，而不能修改 Priority 的优先级



```sh
top - 07:02:29 up 54 min,  1 user,  load average: 0.16, 0.09, 0.04
任务: 409 total,   1 running, 408 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2011.9 free,    971.8 used,    917.8 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2690.2 avail Mem 
PID to renice [default pid = 3509] 
 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND  
   3509 mao       20   0  288780  64292  40092 S   4.3   1.6   0:01.85 Xorg     
   3624 mao       20   0 4305384 259044 114464 S   3.0   6.5   0:04.90 gnome-s+ 
   3965 mao       20   0  908328  63192  47064 S   1.7   1.6   0:00.55 gnome-t+ 
   3671 mao       20   0  162836   7532   6756 S   0.7   0.2   0:00.04 at-spi2+ 
   4085 mao       20   0   20804   4032   3256 R   0.3   0.1   0:00.02 top      
   1621 mao       20   0   19156  10380   8044 S   0.0   0.3   0:00.86 systemd  
   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam) 
   2925 mao        9 -11 1344248  19924  15276 S   0.0   0.5   0:00.08 pulseau+ 
   3420 mao       20   0    8868   6032   3908 S   0.0   0.2   0:00.45 dbus-da+ 
   3502 mao       20   0  249096   7960   6976 S   0.0   0.2   0:00.07 gnome-k+ 
   3507 mao       20   0  172804   6816   6184 S   0.0   0.2   0:00.01 gdm-x-s+ 
   3517 mao       20   0  199592  15888  14116 S   0.0   0.4   0:00.03 gnome-s+ 
   3580 mao       20   0  248504   7904   6952 S   0.0   0.2   0:00.06 gvfsd    
   3585 mao       20   0  382064   8196   7332 S   0.0   0.2   0:00.01 gvfsd-f+ 
   3594 mao       20   0  309824   9228   8352 S   0.0   0.2   0:00.02 at-spi-+ 
   3599 mao       20   0    7248   4260   3808 S   0.0   0.1   0:00.03 dbus-da+ 
   3603 mao       20   0   98860   4336   3912 S   0.0   0.1   0:00.00 gnome-s+ 
```



把ni优先级设置为-20



```sh
top - 07:04:09 up 56 min,  1 user,  load average: 0.05, 0.07, 0.04
任务: 410 total,   1 running, 409 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.4 us,  0.4 sy,  0.0 ni, 99.2 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2011.2 free,    972.5 used,    917.8 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2689.5 avail Mem 
Renice PID 3509 to value -20
 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND  
   3509 mao       20   0  288504  64328  40128 S  13.3   1.6   0:02.36 Xorg     
   1621 mao       20   0   19156  10380   8044 S   0.0   0.3   0:00.86 systemd  
   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam) 
   2925 mao        9 -11 1344248  19924  15276 S   0.0   0.5   0:00.08 pulseau+ 
   3420 mao       20   0    8868   6032   3908 S   0.0   0.2   0:00.45 dbus-da+ 
   3502 mao       20   0  249096   7960   6976 S   0.0   0.2   0:00.07 gnome-k+ 
   3507 mao       20   0  172804   6816   6184 S   0.0   0.2   0:00.01 gdm-x-s+ 
   3517 mao       20   0  199592  15888  14116 S   0.0   0.4   0:00.03 gnome-s+ 
   3580 mao       20   0  248504   7904   6952 S   0.0   0.2   0:00.06 gvfsd    
   3585 mao       20   0  382064   8196   7332 S   0.0   0.2   0:00.01 gvfsd-f+ 
   3594 mao       20   0  309824   9228   8352 S   0.0   0.2   0:00.02 at-spi-+ 
   3599 mao       20   0    7248   4260   3808 S   0.0   0.1   0:00.03 dbus-da+ 
   3603 mao       20   0   98860   4336   3912 S   0.0   0.1   0:00.00 gnome-s+ 
   3610 mao       20   0  422172  18060  15368 S   0.0   0.5   0:00.16 gnome-s+ 
   3624 mao       20   0 4303332 257936 114464 S   0.0   6.5   0:05.32 gnome-s+ 
   3648 mao       20   0  397440  10820   9156 S   0.0   0.3   0:00.05 ibus-da+ 
   3652 mao       20   0  249288   9116   8360 S   0.0   0.2   0:00.01 ibus-dc+ 
```



权限不够可以使用sudo命令：

```sh
mao@ubuntu:~/桌面$ sudo top -u mao
[sudo] mao 的密码： 

top - 07:06:38 up 58 min,  1 user,  load average: 0.00, 0.04, 0.02
任务: 397 total,   2 running, 395 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2012.8 free,    970.1 used,    918.6 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2691.9 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND  
   3509 mao       20   0  288504  64328  40128 R   8.3   1.6   0:04.31 Xorg     
   3624 mao       20   0 4303332 257900 114464 S   5.3   6.5   0:06.70 gnome-s+ 
   3965 mao       20   0  908328  63508  47380 S   3.0   1.6   0:01.53 gnome-t+ 
   3836 mao       20   0  302060  42504  30408 S   0.3   1.1   0:00.95 vmtoolsd 
   1621 mao       20   0   19156  10380   8044 S   0.0   0.3   0:00.86 systemd  
   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam) 
   2925 mao        9 -11 1344248  19924  15276 S   0.0   0.5   0:00.08 pulseau+ 
   3420 mao       20   0    8868   6032   3908 S   0.0   0.2   0:00.45 dbus-da+ 
   3502 mao       20   0  249096   7960   6976 S   0.0   0.2   0:00.07 gnome-k+ 
   3507 mao       20   0  172804   6816   6184 S   0.0   0.2   0:00.01 gdm-x-s+ 
   3517 mao       20   0  199592  15888  14116 S   0.0   0.4   0:00.03 gnome-s+ 
   3580 mao       20   0  248504   7904   6952 S   0.0   0.2   0:00.06 gvfsd    
   3585 mao       20   0  382064   8196   7332 S   0.0   0.2   0:00.01 gvfsd-f+ 
   3594 mao       20   0  309824   9228   8352 S   0.0   0.2   0:00.02 at-spi-+ 
   3599 mao       20   0    7248   4260   3808 S   0.0   0.1   0:00.03 dbus-da+ 
   3603 mao       20   0   98860   4336   3912 S   0.0   0.1   0:00.00 gnome-s+ 
   3610 mao       20   0  422172  18060  15368 S   0.0   0.5   0:00.16 gnome-s+ 
mao@ubuntu:~/桌面$ 
```



更改后：

```sh
mao@ubuntu:~/桌面$ sudo top -u mao

top - 07:07:25 up 59 min,  1 user,  load average: 0.00, 0.03, 0.02
任务: 397 total,   1 running, 396 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2012.8 free,    970.0 used,    918.6 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2692.0 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND  
   3509 mao        0 -20  288504  64328  40128 S   2.0   1.6   0:05.27 Xorg     
   3965 mao       20   0  908328  63508  47380 S   0.7   1.6   0:01.94 gnome-t+ 
   3624 mao       20   0 4303332 257900 114464 S   0.3   6.5   0:07.20 gnome-s+ 
   3836 mao       20   0  302060  42504  30408 S   0.3   1.1   0:01.05 vmtoolsd 
   1621 mao       20   0   19156  10380   8044 S   0.0   0.3   0:00.86 systemd  
   1622 mao       20   0  169004   3464      4 S   0.0   0.1   0:00.00 (sd-pam) 
   2925 mao        9 -11 1344248  19924  15276 S   0.0   0.5   0:00.08 pulseau+ 
   3420 mao       20   0    8868   6032   3908 S   0.0   0.2   0:00.45 dbus-da+ 
   3502 mao       20   0  249096   7960   6976 S   0.0   0.2   0:00.07 gnome-k+ 
   3507 mao       20   0  172804   6816   6184 S   0.0   0.2   0:00.01 gdm-x-s+ 
   3517 mao       20   0  199592  15888  14116 S   0.0   0.4   0:00.03 gnome-s+ 
   3580 mao       20   0  248504   7904   6952 S   0.0   0.2   0:00.06 gvfsd    
   3585 mao       20   0  382064   8196   7332 S   0.0   0.2   0:00.01 gvfsd-f+ 
   3594 mao       20   0  309824   9228   8352 S   0.0   0.2   0:00.02 at-spi-+ 
   3599 mao       20   0    7248   4260   3808 S   0.0   0.1   0:00.03 dbus-da+ 
   3603 mao       20   0   98860   4336   3912 S   0.0   0.1   0:00.00 gnome-s+ 
   3610 mao       20   0  422172  18060  15368 S   0.0   0.5   0:00.16 gnome-s+ 
mao@ubuntu:~/桌面$ 
```









## pstree命令

pstree 命令是**以树形结构显示程序和进程之间的关系**



命令：

```sh
pstree [选项] [PID或用户名]
```



| 选项 |                             含义                             |
| :--: | :----------------------------------------------------------: |
|  -a  | 显示启动每个进程对应的完整指令，包括启动进程的路径、参数等。 |
|  -c  | 不使用精简法显示进程信息，即显示的进程中包含子进程和父进程。 |
|  -n  |    根据进程 PID 号来排序输出，默认是以程序名排序输出的。     |
|  -p  |                       显示进程的 PID。                       |
|  -u  |                   显示进程对应的用户名称。                   |



在使用 pstree 命令时，如果不指定进程的 PID 号，也不指定用户名称，则会以 init 进程为根进程，显示系统中所有程序和进程的信息；反之，若指定 PID 号或用户名，则将以 PID 或指定命令为根进程，显示 PID 或用户对应的所有程序和进程。

init 进程是系统启动的第一个进程，进程的 PID 是 1，也是系统中所有进程的父进程。





```sh
mao@ubuntu:~/桌面$ pstree
systemd─┬─ModemManager───2*[{ModemManager}]
        ├─NetworkManager───2*[{NetworkManager}]
        ├─VGAuthService
        ├─accounts-daemon───2*[{accounts-daemon}]
        ├─acpid
        ├─avahi-daemon───avahi-daemon
        ├─colord───2*[{colord}]
        ├─cron
        ├─cups-browsed───2*[{cups-browsed}]
        ├─cupsd───dbus
        ├─dbus-daemon
        ├─gdm3─┬─gdm-session-wor─┬─gdm-x-session─┬─Xorg───{Xorg}
        │      │                 │               ├─gnome-session-b───2*[{gnome-+
        │      │                 │               └─2*[{gdm-x-session}]
        │      │                 └─2*[{gdm-session-wor}]
        │      └─2*[{gdm3}]
        ├─gnome-keyring-d───3*[{gnome-keyring-d}]
        ├─irqbalance───{irqbalance}
        ├─2*[kerneloops]
        ├─networkd-dispat
        ├─polkitd───2*[{polkitd}]
        ├─rsyslogd───3*[{rsyslogd}]
        ├─rtkit-daemon───2*[{rtkit-daemon}]
        ├─snapd───20*[{snapd}]
        ├─switcheroo-cont───2*[{switcheroo-cont}]
        ├─systemd─┬─(sd-pam)
        │         ├─at-spi-bus-laun─┬─dbus-daemon
        │         │                 └─3*[{at-spi-bus-laun}]
        │         ├─at-spi2-registr───2*[{at-spi2-registr}]
        │         ├─dbus-daemon
        │         ├─dconf-service───2*[{dconf-service}]
        │         ├─evolution-addre───5*[{evolution-addre}]
        │         ├─evolution-calen───8*[{evolution-calen}]
        │         ├─evolution-sourc───3*[{evolution-sourc}]
        │         ├─gjs───10*[{gjs}]
        │         ├─gnome-session-b─┬─evolution-alarm───5*[{evolution-alarm}]
        │         │                 ├─gsd-disk-utilit───2*[{gsd-disk-utilit}]
        │         │                 ├─update-notifier───4*[{update-notifier}]
        │         │                 └─3*[{gnome-session-b}]
        │         ├─gnome-session-c───{gnome-session-c}
        │         ├─gnome-shell─┬─ibus-daemon─┬─ibus-dconf───3*[{ibus-dconf}]
        │         │             │             ├─ibus-engine-sim───2*[{ibus-engi+
        │         │             │             ├─ibus-extension-───3*[{ibus-exte+
        │         │             │             └─2*[{ibus-daemon}]
        │         │             └─11*[{gnome-shell}]
        │         ├─gnome-shell-cal───5*[{gnome-shell-cal}]
        │         ├─gnome-terminal-─┬─bash───pstree
        │         │                 └─4*[{gnome-terminal-}]
        │         ├─goa-daemon───3*[{goa-daemon}]
        │         ├─goa-identity-se───2*[{goa-identity-se}]
        │         ├─gsd-a11y-settin───3*[{gsd-a11y-settin}]
        │         ├─gsd-color───3*[{gsd-color}]
        │         ├─gsd-datetime───3*[{gsd-datetime}]
        │         ├─gsd-housekeepin───3*[{gsd-housekeepin}]
        │         ├─gsd-keyboard───3*[{gsd-keyboard}]
        │         ├─gsd-media-keys───3*[{gsd-media-keys}]
        │         ├─gsd-power───3*[{gsd-power}]
        │         ├─gsd-print-notif───2*[{gsd-print-notif}]
        │         ├─gsd-printer───2*[{gsd-printer}]
        │         ├─gsd-rfkill───2*[{gsd-rfkill}]
        │         ├─gsd-screensaver───2*[{gsd-screensaver}]
        │         ├─gsd-sharing───3*[{gsd-sharing}]
        │         ├─gsd-smartcard───4*[{gsd-smartcard}]
        │         ├─gsd-sound───3*[{gsd-sound}]
        │         ├─gsd-usb-protect───3*[{gsd-usb-protect}]
        │         ├─gsd-wacom───2*[{gsd-wacom}]
        │         ├─gsd-wwan───3*[{gsd-wwan}]
        │         ├─gsd-xsettings───3*[{gsd-xsettings}]
        │         ├─gvfs-afc-volume───3*[{gvfs-afc-volume}]
        │         ├─gvfs-goa-volume───2*[{gvfs-goa-volume}]
        │         ├─gvfs-gphoto2-vo───2*[{gvfs-gphoto2-vo}]
        │         ├─gvfs-mtp-volume───2*[{gvfs-mtp-volume}]
        │         ├─gvfs-udisks2-vo───3*[{gvfs-udisks2-vo}]
        │         ├─gvfsd─┬─gvfsd-trash───2*[{gvfsd-trash}]
        │         │       └─2*[{gvfsd}]
        │         ├─gvfsd-fuse───5*[{gvfsd-fuse}]
        │         ├─gvfsd-metadata───2*[{gvfsd-metadata}]
        │         ├─ibus-portal───2*[{ibus-portal}]
        │         ├─ibus-x11───2*[{ibus-x11}]
        │         ├─pulseaudio───2*[{pulseaudio}]
        │         ├─vmtoolsd───3*[{vmtoolsd}]
        │         └─xdg-permission-───2*[{xdg-permission-}]
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-resolve
        ├─systemd-timesyn───{systemd-timesyn}
        ├─systemd-udevd
        ├─udisksd───4*[{udisksd}]
        ├─unattended-upgr───{unattended-upgr}
        ├─upowerd───2*[{upowerd}]
        ├─vmtoolsd───3*[{vmtoolsd}]
        ├─vmware-vmblock-───2*[{vmware-vmblock-}]
        ├─whoopsie───2*[{whoopsie}]
        └─wpa_supplicant
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ pstree -a
systemd auto noprompt
  ├─ModemManager --filter-policy=strict
  │   └─2*[{ModemManager}]
  ├─NetworkManager --no-daemon
  │   └─2*[{NetworkManager}]
  ├─VGAuthService
  ├─accounts-daemon
  │   └─2*[{accounts-daemon}]
  ├─acpid
  ├─avahi-daemon
  │   └─avahi-daemon
  ├─colord
  │   └─2*[{colord}]
  ├─cron -f
  ├─cups-browsed
  │   └─2*[{cups-browsed}]
  ├─cupsd -l
  │   └─dbus dbus:// 
  ├─dbus-daemon --system --address=systemd: --nofork --nopidfile--systemd-
  ├─gdm3
  │   ├─gdm-session-wor
  │   │   ├─gdm-x-session --run-scriptenv GNOME_SHELL_SESSION_MODE=ubuntu /us
  │   │   │   ├─Xorg vt2 -displayfd 3 -auth /run/user/1000/gdm/Xauthority...
  │   │   │   │   └─{Xorg}
  │   │   │   ├─gnome-session-b --systemd --systemd --session=ubuntu
  │   │   │   │   └─2*[{gnome-session-b}]
  │   │   │   └─2*[{gdm-x-session}]
  │   │   └─2*[{gdm-session-wor}]
  │   └─2*[{gdm3}]
  ├─gnome-keyring-d --daemonize --login
  │   └─3*[{gnome-keyring-d}]
  ├─irqbalance --foreground
  │   └─{irqbalance}
  ├─kerneloops --test
  ├─kerneloops
  ├─networkd-dispat /usr/bin/networkd-dispatcher --run-startup-triggers
  ├─polkitd --no-debug
  │   └─2*[{polkitd}]
  ├─rsyslogd -n -iNONE
  │   └─3*[{rsyslogd}]
  ├─rtkit-daemon
  │   └─2*[{rtkit-daemon}]
  ├─snapd
  │   └─20*[{snapd}]
  ├─switcheroo-cont
  │   └─2*[{switcheroo-cont}]
  ├─systemd --user
  │   ├─(sd-pam)
  │   ├─at-spi-bus-laun
  │   │   ├─dbus-daemon...
  │   │   └─3*[{at-spi-bus-laun}]
  │   ├─at-spi2-registr --use-gnome-session
  │   │   └─2*[{at-spi2-registr}]
  │   ├─dbus-daemon --session --address=systemd: --nofork --nopidfile--systemd
  │   ├─dconf-service
  │   │   └─2*[{dconf-service}]
  │   ├─evolution-addre
  │   │   └─5*[{evolution-addre}]
  │   ├─evolution-calen
  │   │   └─8*[{evolution-calen}]
  │   ├─evolution-sourc
  │   │   └─3*[{evolution-sourc}]
  │   ├─gjs /usr/share/gnome-shell/org.gnome.Shell.Notifications
  │   │   └─10*[{gjs}]
  │   ├─gnome-session-b --systemd-service --session=ubuntu
  │   │   ├─evolution-alarm
  │   │   │   └─5*[{evolution-alarm}]
  │   │   ├─gsd-disk-utilit
  │   │   │   └─2*[{gsd-disk-utilit}]
  │   │   ├─update-notifier
  │   │   │   └─4*[{update-notifier}]
  │   │   └─3*[{gnome-session-b}]
  │   ├─gnome-session-c --monitor
  │   │   └─{gnome-session-c}
  │   ├─gnome-shell
  │   │   ├─ibus-daemon --panel disable --xim
  │   │   │   ├─ibus-dconf
  │   │   │   │   └─3*[{ibus-dconf}]
  │   │   │   ├─ibus-engine-sim
  │   │   │   │   └─2*[{ibus-engine-sim}]
  │   │   │   ├─ibus-extension-
  │   │   │   │   └─3*[{ibus-extension-}]
  │   │   │   └─2*[{ibus-daemon}]
  │   │   └─11*[{gnome-shell}]
  │   ├─gnome-shell-cal
  │   │   └─5*[{gnome-shell-cal}]
  │   ├─gnome-terminal-
  │   │   ├─bash
  │   │   │   └─pstree -a
  │   │   └─4*[{gnome-terminal-}]
  │   ├─goa-daemon
  │   │   └─3*[{goa-daemon}]
  │   ├─goa-identity-se
  │   │   └─2*[{goa-identity-se}]
  │   ├─gsd-a11y-settin
  │   │   └─3*[{gsd-a11y-settin}]
  │   ├─gsd-color
  │   │   └─3*[{gsd-color}]
  │   ├─gsd-datetime
  │   │   └─3*[{gsd-datetime}]
  │   ├─gsd-housekeepin
  │   │   └─3*[{gsd-housekeepin}]
  │   ├─gsd-keyboard
  │   │   └─3*[{gsd-keyboard}]
  │   ├─gsd-media-keys
  │   │   └─3*[{gsd-media-keys}]
  │   ├─gsd-power
  │   │   └─3*[{gsd-power}]
  │   ├─gsd-print-notif
  │   │   └─2*[{gsd-print-notif}]
  │   ├─gsd-printer
  │   │   └─2*[{gsd-printer}]
  │   ├─gsd-rfkill
  │   │   └─2*[{gsd-rfkill}]
  │   ├─gsd-screensaver
  │   │   └─2*[{gsd-screensaver}]
  │   ├─gsd-sharing
  │   │   └─3*[{gsd-sharing}]
  │   ├─gsd-smartcard
  │   │   └─4*[{gsd-smartcard}]
  │   ├─gsd-sound
  │   │   └─3*[{gsd-sound}]
  │   ├─gsd-usb-protect
  │   │   └─3*[{gsd-usb-protect}]
  │   ├─gsd-wacom
  │   │   └─2*[{gsd-wacom}]
  │   ├─gsd-wwan
  │   │   └─3*[{gsd-wwan}]
  │   ├─gsd-xsettings
  │   │   └─3*[{gsd-xsettings}]
  │   ├─gvfs-afc-volume
  │   │   └─3*[{gvfs-afc-volume}]
  │   ├─gvfs-goa-volume
  │   │   └─2*[{gvfs-goa-volume}]
  │   ├─gvfs-gphoto2-vo
  │   │   └─2*[{gvfs-gphoto2-vo}]
  │   ├─gvfs-mtp-volume
  │   │   └─2*[{gvfs-mtp-volume}]
  │   ├─gvfs-udisks2-vo
  │   │   └─3*[{gvfs-udisks2-vo}]
  │   ├─gvfsd
  │   │   ├─gvfsd-trash --spawner :1.7 /org/gtk/gvfs/exec_spaw/0
  │   │   │   └─2*[{gvfsd-trash}]
  │   │   └─2*[{gvfsd}]
  │   ├─gvfsd-fuse /run/user/1000/gvfs -f -o big_writes
  │   │   └─5*[{gvfsd-fuse}]
  │   ├─gvfsd-metadata
  │   │   └─2*[{gvfsd-metadata}]
  │   ├─ibus-portal
  │   │   └─2*[{ibus-portal}]
  │   ├─ibus-x11 --kill-daemon
  │   │   └─2*[{ibus-x11}]
  │   ├─pulseaudio --daemonize=no --log-target=journal
  │   │   └─2*[{pulseaudio}]
  │   ├─vmtoolsd -n vmusr --blockFd 3
  │   │   └─3*[{vmtoolsd}]
  │   └─xdg-permission-
  │       └─2*[{xdg-permission-}]
  ├─systemd-journal
  ├─systemd-logind
  ├─systemd-resolve
  ├─systemd-timesyn
  │   └─{systemd-timesyn}
  ├─systemd-udevd
  ├─udisksd
  │   └─4*[{udisksd}]
  ├─unattended-upgr ...
  │   └─{unattended-upgr}
  ├─upowerd
  │   └─2*[{upowerd}]
  ├─vmtoolsd
  │   └─3*[{vmtoolsd}]
  ├─vmware-vmblock- /run/vmblock-fuse -orw,subtype=vmware-vmblock,default_permi
  │   └─2*[{vmware-vmblock-}]
  ├─whoopsie -f
  │   └─2*[{whoopsie}]
  └─wpa_supplicant -u -s -O /run/wpa_supplicant
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ pstree -c
systemd─┬─ModemManager─┬─{ModemManager}
        │              └─{ModemManager}
        ├─NetworkManager─┬─{NetworkManager}
        │                └─{NetworkManager}
        ├─VGAuthService
        ├─accounts-daemon─┬─{accounts-daemon}
        │                 └─{accounts-daemon}
        ├─acpid
        ├─avahi-daemon───avahi-daemon
        ├─colord─┬─{colord}
        │        └─{colord}
        ├─cron
        ├─cups-browsed─┬─{cups-browsed}
        │              └─{cups-browsed}
        ├─cupsd───dbus
        ├─dbus-daemon
        ├─gdm3─┬─gdm-session-wor─┬─gdm-x-session─┬─Xorg───{Xorg}
        │      │                 │               ├─gnome-session-b─┬─{gnome-ses+
        │      │                 │               │                 └─{gnome-ses+
        │      │                 │               ├─{gdm-x-session}
        │      │                 │               └─{gdm-x-session}
        │      │                 ├─{gdm-session-wor}
        │      │                 └─{gdm-session-wor}
        │      ├─{gdm3}
        │      └─{gdm3}
        ├─gnome-keyring-d─┬─{gnome-keyring-d}
        │                 ├─{gnome-keyring-d}
        │                 └─{gnome-keyring-d}
        ├─irqbalance───{irqbalance}
        ├─kerneloops
        ├─kerneloops
        ├─networkd-dispat
        ├─polkitd─┬─{polkitd}
        │         └─{polkitd}
        ├─rsyslogd─┬─{rsyslogd}
        │          ├─{rsyslogd}
        │          └─{rsyslogd}
        ├─rtkit-daemon─┬─{rtkit-daemon}
        │              └─{rtkit-daemon}
        ├─snapd─┬─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       ├─{snapd}
        │       └─{snapd}
        ├─switcheroo-cont─┬─{switcheroo-cont}
        │                 └─{switcheroo-cont}
        ├─systemd─┬─(sd-pam)
        │         ├─at-spi-bus-laun─┬─dbus-daemon
        │         │                 ├─{at-spi-bus-laun}
        │         │                 ├─{at-spi-bus-laun}
        │         │                 └─{at-spi-bus-laun}
        │         ├─at-spi2-registr─┬─{at-spi2-registr}
        │         │                 └─{at-spi2-registr}
        │         ├─dbus-daemon
        │         ├─dconf-service─┬─{dconf-service}
        │         │               └─{dconf-service}
        │         ├─evolution-addre─┬─{evolution-addre}
        │         │                 ├─{evolution-addre}
        │         │                 ├─{evolution-addre}
        │         │                 ├─{evolution-addre}
        │         │                 └─{evolution-addre}
        │         ├─evolution-calen─┬─{evolution-calen}
        │         │                 ├─{evolution-calen}
        │         │                 ├─{evolution-calen}
        │         │                 ├─{evolution-calen}
        │         │                 ├─{evolution-calen}
        │         │                 ├─{evolution-calen}
        │         │                 ├─{evolution-calen}
        │         │                 └─{evolution-calen}
        │         ├─evolution-sourc─┬─{evolution-sourc}
        │         │                 ├─{evolution-sourc}
        │         │                 └─{evolution-sourc}
        │         ├─gjs─┬─{gjs}
        │         │     ├─{gjs}
        │         │     ├─{gjs}
        │         │     ├─{gjs}
        │         │     ├─{gjs}
        │         │     ├─{gjs}
        │         │     ├─{gjs}
        │         │     ├─{gjs}
        │         │     ├─{gjs}
        │         │     └─{gjs}
        │         ├─gnome-session-b─┬─evolution-alarm─┬─{evolution-alarm}
        │         │                 │                 ├─{evolution-alarm}
        │         │                 │                 ├─{evolution-alarm}
        │         │                 │                 ├─{evolution-alarm}
        │         │                 │                 └─{evolution-alarm}
        │         │                 ├─gsd-disk-utilit─┬─{gsd-disk-utilit}
        │         │                 │                 └─{gsd-disk-utilit}
        │         │                 ├─update-notifier─┬─{update-notifier}
        │         │                 │                 ├─{update-notifier}
        │         │                 │                 ├─{update-notifier}
        │         │                 │                 └─{update-notifier}
        │         │                 ├─{gnome-session-b}
        │         │                 ├─{gnome-session-b}
        │         │                 └─{gnome-session-b}
        │         ├─gnome-session-c───{gnome-session-c}
        │         ├─gnome-shell─┬─ibus-daemon─┬─ibus-dconf─┬─{ibus-dconf}
        │         │             │             │            ├─{ibus-dconf}
        │         │             │             │            └─{ibus-dconf}
        │         │             │             ├─ibus-engine-sim─┬─{ibus-engine-+
        │         │             │             │                 └─{ibus-engine-+
        │         │             │             ├─ibus-extension-─┬─{ibus-extensi+
        │         │             │             │                 ├─{ibus-extensi+
        │         │             │             │                 └─{ibus-extensi+
        │         │             │             ├─{ibus-daemon}
        │         │             │             └─{ibus-daemon}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             ├─{gnome-shell}
        │         │             └─{gnome-shell}
        │         ├─gnome-shell-cal─┬─{gnome-shell-cal}
        │         │                 ├─{gnome-shell-cal}
        │         │                 ├─{gnome-shell-cal}
        │         │                 ├─{gnome-shell-cal}
        │         │                 └─{gnome-shell-cal}
        │         ├─gnome-terminal-─┬─bash───pstree
        │         │                 ├─{gnome-terminal-}
        │         │                 ├─{gnome-terminal-}
        │         │                 ├─{gnome-terminal-}
        │         │                 └─{gnome-terminal-}
        │         ├─goa-daemon─┬─{goa-daemon}
        │         │            ├─{goa-daemon}
        │         │            └─{goa-daemon}
        │         ├─goa-identity-se─┬─{goa-identity-se}
        │         │                 └─{goa-identity-se}
        │         ├─gsd-a11y-settin─┬─{gsd-a11y-settin}
        │         │                 ├─{gsd-a11y-settin}
        │         │                 └─{gsd-a11y-settin}
        │         ├─gsd-color─┬─{gsd-color}
        │         │           ├─{gsd-color}
        │         │           └─{gsd-color}
        │         ├─gsd-datetime─┬─{gsd-datetime}
        │         │              ├─{gsd-datetime}
        │         │              └─{gsd-datetime}
        │         ├─gsd-housekeepin─┬─{gsd-housekeepin}
        │         │                 ├─{gsd-housekeepin}
        │         │                 └─{gsd-housekeepin}
        │         ├─gsd-keyboard─┬─{gsd-keyboard}
        │         │              ├─{gsd-keyboard}
        │         │              └─{gsd-keyboard}
        │         ├─gsd-media-keys─┬─{gsd-media-keys}
        │         │                ├─{gsd-media-keys}
        │         │                └─{gsd-media-keys}
        │         ├─gsd-power─┬─{gsd-power}
        │         │           ├─{gsd-power}
        │         │           └─{gsd-power}
        │         ├─gsd-print-notif─┬─{gsd-print-notif}
        │         │                 └─{gsd-print-notif}
        │         ├─gsd-printer─┬─{gsd-printer}
        │         │             └─{gsd-printer}
        │         ├─gsd-rfkill─┬─{gsd-rfkill}
        │         │            └─{gsd-rfkill}
        │         ├─gsd-screensaver─┬─{gsd-screensaver}
        │         │                 └─{gsd-screensaver}
        │         ├─gsd-sharing─┬─{gsd-sharing}
        │         │             ├─{gsd-sharing}
        │         │             └─{gsd-sharing}
        │         ├─gsd-smartcard─┬─{gsd-smartcard}
        │         │               ├─{gsd-smartcard}
        │         │               ├─{gsd-smartcard}
        │         │               └─{gsd-smartcard}
        │         ├─gsd-sound─┬─{gsd-sound}
        │         │           ├─{gsd-sound}
        │         │           └─{gsd-sound}
        │         ├─gsd-usb-protect─┬─{gsd-usb-protect}
        │         │                 ├─{gsd-usb-protect}
        │         │                 └─{gsd-usb-protect}
        │         ├─gsd-wacom─┬─{gsd-wacom}
        │         │           └─{gsd-wacom}
        │         ├─gsd-wwan─┬─{gsd-wwan}
        │         │          ├─{gsd-wwan}
        │         │          └─{gsd-wwan}
        │         ├─gsd-xsettings─┬─{gsd-xsettings}
        │         │               ├─{gsd-xsettings}
        │         │               └─{gsd-xsettings}
        │         ├─gvfs-afc-volume─┬─{gvfs-afc-volume}
        │         │                 ├─{gvfs-afc-volume}
        │         │                 └─{gvfs-afc-volume}
        │         ├─gvfs-goa-volume─┬─{gvfs-goa-volume}
        │         │                 └─{gvfs-goa-volume}
        │         ├─gvfs-gphoto2-vo─┬─{gvfs-gphoto2-vo}
        │         │                 └─{gvfs-gphoto2-vo}
        │         ├─gvfs-mtp-volume─┬─{gvfs-mtp-volume}
        │         │                 └─{gvfs-mtp-volume}
        │         ├─gvfs-udisks2-vo─┬─{gvfs-udisks2-vo}
        │         │                 ├─{gvfs-udisks2-vo}
        │         │                 └─{gvfs-udisks2-vo}
        │         ├─gvfsd─┬─gvfsd-trash─┬─{gvfsd-trash}
        │         │       │             └─{gvfsd-trash}
        │         │       ├─{gvfsd}
        │         │       └─{gvfsd}
        │         ├─gvfsd-fuse─┬─{gvfsd-fuse}
        │         │            ├─{gvfsd-fuse}
        │         │            ├─{gvfsd-fuse}
        │         │            ├─{gvfsd-fuse}
        │         │            └─{gvfsd-fuse}
        │         ├─gvfsd-metadata─┬─{gvfsd-metadata}
        │         │                └─{gvfsd-metadata}
        │         ├─ibus-portal─┬─{ibus-portal}
        │         │             └─{ibus-portal}
        │         ├─ibus-x11─┬─{ibus-x11}
        │         │          └─{ibus-x11}
        │         ├─pulseaudio─┬─{pulseaudio}
        │         │            └─{pulseaudio}
        │         ├─vmtoolsd─┬─{vmtoolsd}
        │         │          ├─{vmtoolsd}
        │         │          └─{vmtoolsd}
        │         └─xdg-permission-─┬─{xdg-permission-}
        │                           └─{xdg-permission-}
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-resolve
        ├─systemd-timesyn───{systemd-timesyn}
        ├─systemd-udevd
        ├─udisksd─┬─{udisksd}
        │         ├─{udisksd}
        │         ├─{udisksd}
        │         └─{udisksd}
        ├─unattended-upgr───{unattended-upgr}
        ├─upowerd─┬─{upowerd}
        │         └─{upowerd}
        ├─vmtoolsd─┬─{vmtoolsd}
        │          ├─{vmtoolsd}
        │          └─{vmtoolsd}
        ├─vmware-vmblock-─┬─{vmware-vmblock-}
        │                 └─{vmware-vmblock-}
        ├─whoopsie─┬─{whoopsie}
        │          └─{whoopsie}
        └─wpa_supplicant
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ pstree -p -n -u
systemd(1)─┬─systemd-journal(484)
           ├─systemd-udevd(531)
           ├─vmware-vmblock-(543)─┬─{vmware-vmblock-}(544)
           │                      └─{vmware-vmblock-}(545)
           ├─systemd-resolve(872,systemd-resolve)
           ├─systemd-timesyn(873,systemd-timesync)───{systemd-timesyn}(894)
           ├─VGAuthService(876)
           ├─vmtoolsd(879)─┬─{vmtoolsd}(965)
           │               ├─{vmtoolsd}(966)
           │               └─{vmtoolsd}(1067)
           ├─accounts-daemon(896)─┬─{accounts-daemon}(907)
           │                      └─{accounts-daemon}(988)
           ├─acpid(897)
           ├─avahi-daemon(900,avahi)───avahi-daemon(952)
           ├─cron(901)
           ├─dbus-daemon(903,messagebus)
           ├─NetworkManager(905)─┬─{NetworkManager}(1001)
           │                     └─{NetworkManager}(1003)
           ├─irqbalance(913)───{irqbalance}(929)
           ├─networkd-dispat(917)
           ├─polkitd(920)─┬─{polkitd}(938)
           │              └─{polkitd}(989)
           ├─rsyslogd(924,syslog)─┬─{rsyslogd}(953)
           │                      ├─{rsyslogd}(954)
           │                      └─{rsyslogd}(955)
           ├─switcheroo-cont(933)─┬─{switcheroo-cont}(949)
           │                      └─{switcheroo-cont}(991)
           ├─systemd-logind(934)
           ├─udisksd(936)─┬─{udisksd}(957)
           │              ├─{udisksd}(990)
           │              ├─{udisksd}(1023)
           │              └─{udisksd}(1096)
           ├─wpa_supplicant(939)
           ├─cups-browsed(995)─┬─{cups-browsed}(1042)
           │                   └─{cups-browsed}(1044)
           ├─ModemManager(1000)─┬─{ModemManager}(1024)
           │                    └─{ModemManager}(1030)
           ├─unattended-upgr(1009)───{unattended-upgr}(1100)
           ├─cupsd(1034)───dbus(1040,lp)
           ├─gdm3(1036)─┬─{gdm3}(1041)
           │            ├─{gdm3}(1043)
           │            └─gdm-session-wor(3495)─┬─{gdm-session-wor}(3496)
           │                                    ├─{gdm-session-wor}(3497)
           │                                    └─gdm-x-session(3507,mao)─┬─{gdm-x-session}(3508)
           │                                                              ├─Xorg(3509)───{Xorg}(3514)
           │                                                              ├─{gdm-x-session}(3515)
           │                                                              └─gnome-session-b(3517)─┬─{gnome-sess+
           │                                                                                      └─{gnome-sess+
           ├─whoopsie(1115,whoopsie)─┬─{whoopsie}(1132)
           │                         └─{whoopsie}(1133)
           ├─kerneloops(1120,kernoops)
           ├─kerneloops(1127,kernoops)
           ├─rtkit-daemon(1148,rtkit)─┬─{rtkit-daemon}(1155)
           │                          └─{rtkit-daemon}(1156)
           ├─upowerd(1252)─┬─{upowerd}(1256)
           │               └─{upowerd}(1257)
           ├─colord(1526,colord)─┬─{colord}(1570)
           │                     └─{colord}(1572)
           ├─systemd(1621,mao)─┬─(sd-pam)(1622)
           │                   ├─pulseaudio(2925)─┬─{pulseaudio}(2938)
           │                   │                  └─{pulseaudio}(2940)
           │                   ├─dbus-daemon(3420)
           │                   ├─gvfsd(3580)─┬─{gvfsd}(3581)
           │                   │             ├─{gvfsd}(3582)
           │                   │             └─gvfsd-trash(3773)─┬─{gvfsd-trash}(3774)
           │                   │                                 └─{gvfsd-trash}(3775)
           │                   ├─gvfsd-fuse(3585)─┬─{gvfsd-fuse}(3589)
           │                   │                  ├─{gvfsd-fuse}(3590)
           │                   │                  ├─{gvfsd-fuse}(3591)
           │                   │                  ├─{gvfsd-fuse}(3592)
           │                   │                  └─{gvfsd-fuse}(3593)
           │                   ├─at-spi-bus-laun(3594)─┬─{at-spi-bus-laun}(3595)
           │                   │                       ├─{at-spi-bus-laun}(3596)
           │                   │                       ├─{at-spi-bus-laun}(3597)
           │                   │                       └─dbus-daemon(3599)
           │                   ├─gnome-session-c(3603)───{gnome-session-c}(3607)
           │                   ├─gnome-session-b(3610)─┬─{gnome-session-b}(3611)
           │                   │                       ├─{gnome-session-b}(3612)
           │                   │                       ├─{gnome-session-b}(3614)
           │                   │                       ├─evolution-alarm(3823)─┬─{evolution-alarm}(3906)
           │                   │                       │                       ├─{evolution-alarm}(3909)
           │                   │                       │                       ├─{evolution-alarm}(3912)
           │                   │                       │                       ├─{evolution-alarm}(3915)
           │                   │                       │                       └─{evolution-alarm}(3926)
           │                   │                       ├─gsd-disk-utilit(3845)─┬─{gsd-disk-utilit}(3848)
           │                   │                       │                       └─{gsd-disk-utilit}(3858)
           │                   │                       └─update-notifier(3993)─┬─{update-notifier}(3996)
           │                   │                                               ├─{update-notifier}(3997)
           │                   │                                               ├─{update-notifier}(3998)
           │                   │                                               └─{update-notifier}(4083)
           │                   ├─gnome-shell(3624)─┬─{gnome-shell}(3635)
           │                   │                   ├─{gnome-shell}(3637)
           │                   │                   ├─{gnome-shell}(3638)
           │                   │                   ├─{gnome-shell}(3640)
           │                   │                   ├─{gnome-shell}(3641)
           │                   │                   ├─{gnome-shell}(3642)
           │                   │                   ├─{gnome-shell}(3643)
           │                   │                   ├─{gnome-shell}(3644)
           │                   │                   ├─{gnome-shell}(3645)
           │                   │                   ├─{gnome-shell}(3646)
           │                   │                   ├─{gnome-shell}(3647)
           │                   │                   └─ibus-daemon(3648)─┬─{ibus-daemon}(3649)
           │                   │                                       ├─{ibus-daemon}(3650)
           │                   │                                       ├─ibus-dconf(3652)─┬─{ibus-dconf}(3658)
           │                   │                                       │                  ├─{ibus-dconf}(3659)
           │                   │                                       │                  └─{ibus-dconf}(3664)
           │                   │                                       ├─ibus-extension-(3653)─┬─{ibus-extensio+
           │                   │                                       │                       ├─{ibus-extensio+
           │                   │                                       │                       └─{ibus-extensio+
           │                   │                                       └─ibus-engine-sim(3887)─┬─{ibus-engine-s+
           │                   │                                                               └─{ibus-engine-s+
           │                   ├─ibus-x11(3655)─┬─{ibus-x11}(3668)
           │                   │                └─{ibus-x11}(3669)
           │                   ├─ibus-portal(3657)─┬─{ibus-portal}(3660)
           │                   │                   └─{ibus-portal}(3661)
           │                   ├─at-spi2-registr(3671)─┬─{at-spi2-registr}(3672)
           │                   │                       └─{at-spi2-registr}(3673)
           │                   ├─xdg-permission-(3675)─┬─{xdg-permission-}(3676)
           │                   │                       └─{xdg-permission-}(3680)
           │                   ├─gnome-shell-cal(3679)─┬─{gnome-shell-cal}(3681)
           │                   │                       ├─{gnome-shell-cal}(3683)
           │                   │                       ├─{gnome-shell-cal}(3684)
           │                   │                       ├─{gnome-shell-cal}(3685)
           │                   │                       └─{gnome-shell-cal}(3696)
           │                   ├─evolution-sourc(3686)─┬─{evolution-sourc}(3687)
           │                   │                       ├─{evolution-sourc}(3688)
           │                   │                       └─{evolution-sourc}(3689)
           │                   ├─goa-daemon(3694)─┬─{goa-daemon}(3698)
           │                   │                  ├─{goa-daemon}(3701)
           │                   │                  └─{goa-daemon}(3703)
           │                   ├─evolution-calen(3697)─┬─{evolution-calen}(3702)
           │                   │                       ├─{evolution-calen}(3707)
           │                   │                       ├─{evolution-calen}(3712)
           │                   │                       ├─{evolution-calen}(3713)
           │                   │                       ├─{evolution-calen}(3714)
           │                   │                       ├─{evolution-calen}(3716)
           │                   │                       ├─{evolution-calen}(3718)
           │                   │                       └─{evolution-calen}(3724)
           │                   ├─goa-identity-se(3706)─┬─{goa-identity-se}(3708)
           │                   │                       └─{goa-identity-se}(3710)
           │                   ├─dconf-service(3719)─┬─{dconf-service}(3721)
           │                   │                     └─{dconf-service}(3722)
           │                   ├─evolution-addre(3720)─┬─{evolution-addre}(3725)
           │                   │                       ├─{evolution-addre}(3726)
           │                   │                       ├─{evolution-addre}(3728)
           │                   │                       ├─{evolution-addre}(3729)
           │                   │                       └─{evolution-addre}(3731)
           │                   ├─gvfs-udisks2-vo(3732)─┬─{gvfs-udisks2-vo}(3733)
           │                   │                       ├─{gvfs-udisks2-vo}(3734)
           │                   │                       └─{gvfs-udisks2-vo}(3735)
           │                   ├─gvfs-mtp-volume(3737)─┬─{gvfs-mtp-volume}(3738)
           │                   │                       └─{gvfs-mtp-volume}(3740)
           │                   ├─gvfs-goa-volume(3741)─┬─{gvfs-goa-volume}(3742)
           │                   │                       └─{gvfs-goa-volume}(3743)
           │                   ├─gvfs-gphoto2-vo(3745)─┬─{gvfs-gphoto2-vo}(3746)
           │                   │                       └─{gvfs-gphoto2-vo}(3748)
           │                   ├─gvfs-afc-volume(3749)─┬─{gvfs-afc-volume}(3750)
           │                   │                       ├─{gvfs-afc-volume}(3751)
           │                   │                       └─{gvfs-afc-volume}(3753)
           │                   ├─gjs(3761)─┬─{gjs}(3765)
           │                   │           ├─{gjs}(3766)
           │                   │           ├─{gjs}(3767)
           │                   │           ├─{gjs}(3768)
           │                   │           ├─{gjs}(3769)
           │                   │           ├─{gjs}(3770)
           │                   │           ├─{gjs}(3771)
           │                   │           ├─{gjs}(3772)
           │                   │           ├─{gjs}(3777)
           │                   │           └─{gjs}(3778)
           │                   ├─gsd-a11y-settin(3786)─┬─{gsd-a11y-settin}(3791)
           │                   │                       ├─{gsd-a11y-settin}(3795)
           │                   │                       └─{gsd-a11y-settin}(3830)
           │                   ├─gsd-color(3787)─┬─{gsd-color}(3850)
           │                   │                 ├─{gsd-color}(3879)
           │                   │                 └─{gsd-color}(3888)
           │                   ├─gsd-datetime(3788)─┬─{gsd-datetime}(3814)
           │                   │                    ├─{gsd-datetime}(3828)
           │                   │                    └─{gsd-datetime}(3877)
           │                   ├─gsd-housekeepin(3790)─┬─{gsd-housekeepin}(3797)
           │                   │                       ├─{gsd-housekeepin}(3801)
           │                   │                       └─{gsd-housekeepin}(3832)
           │                   ├─gsd-keyboard(3792)─┬─{gsd-keyboard}(3840)
           │                   │                    ├─{gsd-keyboard}(3854)
           │                   │                    └─{gsd-keyboard}(3870)
           │                   ├─gsd-media-keys(3794)─┬─{gsd-media-keys}(3862)
           │                   │                      ├─{gsd-media-keys}(3869)
           │                   │                      └─{gsd-media-keys}(3905)
           │                   ├─gsd-power(3796)─┬─{gsd-power}(3859)
           │                   │                 ├─{gsd-power}(3861)
           │                   │                 └─{gsd-power}(3910)
           │                   ├─gsd-print-notif(3799)─┬─{gsd-print-notif}(3808)
           │                   │                       └─{gsd-print-notif}(3817)
           │                   ├─gsd-rfkill(3803)─┬─{gsd-rfkill}(3806)
           │                   │                  └─{gsd-rfkill}(3815)
           │                   ├─gsd-screensaver(3804)─┬─{gsd-screensaver}(3809)
           │                   │                       └─{gsd-screensaver}(3812)
           │                   ├─gsd-sharing(3805)─┬─{gsd-sharing}(3820)
           │                   │                   ├─{gsd-sharing}(3835)
           │                   │                   └─{gsd-sharing}(3863)
           │                   ├─gsd-smartcard(3807)─┬─{gsd-smartcard}(3818)
           │                   │                     ├─{gsd-smartcard}(3826)
           │                   │                     ├─{gsd-smartcard}(3864)
           │                   │                     └─{gsd-smartcard}(3882)
           │                   ├─gsd-sound(3810)─┬─{gsd-sound}(3824)
           │                   │                 ├─{gsd-sound}(3834)
           │                   │                 └─{gsd-sound}(3880)
           │                   ├─gsd-usb-protect(3813)─┬─{gsd-usb-protect}(3821)
           │                   │                       ├─{gsd-usb-protect}(3825)
           │                   │                       └─{gsd-usb-protect}(3876)
           │                   ├─gsd-wacom(3816)─┬─{gsd-wacom}(3871)
           │                   │                 └─{gsd-wacom}(3889)
           │                   ├─gsd-wwan(3819)─┬─{gsd-wwan}(3827)
           │                   │                ├─{gsd-wwan}(3837)
           │                   │                └─{gsd-wwan}(3881)
           │                   ├─gsd-xsettings(3822)─┬─{gsd-xsettings}(3885)
           │                   │                     ├─{gsd-xsettings}(3890)
           │                   │                     └─{gsd-xsettings}(3904)
           │                   ├─vmtoolsd(3836)─┬─{vmtoolsd}(3919)
           │                   │                ├─{vmtoolsd}(3921)
           │                   │                └─{vmtoolsd}(3947)
           │                   ├─gsd-printer(3884)─┬─{gsd-printer}(3892)
           │                   │                   └─{gsd-printer}(3894)
           │                   ├─gnome-terminal-(3965)─┬─{gnome-terminal-}(3966)
           │                   │                       ├─{gnome-terminal-}(3967)
           │                   │                       ├─{gnome-terminal-}(3968)
           │                   │                       ├─{gnome-terminal-}(3972)
           │                   │                       └─bash(3973)───pstree(4129)
           │                   └─gvfsd-metadata(3990)─┬─{gvfsd-metadata}(3991)
           │                                          └─{gvfsd-metadata}(3992)
           ├─snapd(2699)─┬─{snapd}(2709)
           │             ├─{snapd}(2710)
           │             ├─{snapd}(2711)
           │             ├─{snapd}(2712)
           │             ├─{snapd}(2713)
           │             ├─{snapd}(2714)
           │             ├─{snapd}(2715)
           │             ├─{snapd}(2726)
           │             ├─{snapd}(2727)
           │             ├─{snapd}(2730)
           │             ├─{snapd}(2731)
           │             ├─{snapd}(2739)
           │             ├─{snapd}(2751)
           │             ├─{snapd}(2770)
           │             ├─{snapd}(2771)
           │             ├─{snapd}(2772)
           │             ├─{snapd}(2774)
           │             ├─{snapd}(2775)
           │             ├─{snapd}(2776)
           │             └─{snapd}(2777)
           └─gnome-keyring-d(3502,mao)─┬─{gnome-keyring-d}(3503)
                                       ├─{gnome-keyring-d}(3504)
                                       └─{gnome-keyring-d}(3608)
mao@ubuntu:~/桌面$ 
```







## lsof命令

lsof 命令，“list opened files”的缩写，直译过来，就是**列举系统中已经被打开的文件**。通过 lsof 命令，我们就可以根据文件找到对应的进程信息，也可以根据进程信息找到进程打开的文件。



命令：

```sh
lsof [选项]
```



|   选项    |                 功能                 |
| :-------: | :----------------------------------: |
| -c 字符串 | 只列出以字符串开头的进程打开的文件。 |
| +d 目录名 | 列出某个目录中所有被进程调用的文件。 |
| -u 用户名 |   只列出某个用户的进程打开的文件。   |
|  -p pid   |    列出某个 PID 进程打开的文件。     |





执行命令：

```sh
lsof -u mao
```



```sh
deja-dup- 2322  mao  mem       REG                8,5    26304     272833 /usr/share/locale-langpack/zh_CN/LC_MESSAGES/deja-dup.mo
deja-dup- 2322  mao  mem       REG                8,5   346336     266282 /usr/lib/x86_64-linux-gnu/deja-dup/libdeja.so
deja-dup- 2322  mao  mem       REG                8,5   191472     666296 /usr/lib/x86_64-linux-gnu/ld-2.31.so
deja-dup- 2322  mao  mem       REG               0,52        2         39 /run/user/1000/dconf/user
deja-dup- 2322  mao    0r      CHR                1,3      0t0          5 /dev/null
deja-dup- 2322  mao    1u     unix 0x0000000000000000      0t0      84502 type=STREAM
deja-dup- 2322  mao    2u     unix 0x0000000000000000      0t0      84503 type=STREAM
deja-dup- 2322  mao    3u  a_inode               0,13        0      14514 [eventfd]
deja-dup- 2322  mao    4u  a_inode               0,13        0      14514 [eventfd]
deja-dup- 2322  mao    5u  a_inode               0,13        0      14514 [eventfd]
deja-dup- 2322  mao    6u     unix 0x0000000000000000      0t0      63294 type=STREAM
deja-dup- 2322  mao    7u  a_inode               0,13        0      14514 [eventfd]
deja-dup- 2322  mao    9u  netlink                         0t0      65026 ROUTE
deja-dup- 2322  mao   10u     unix 0x0000000000000000      0t0      65027 type=STREAM
lsof      2369  mao  cwd       DIR                8,5     4096     271582 /home/mao/桌面
lsof      2369  mao  rtd       DIR                8,5     4096          2 /
lsof      2369  mao  txt       REG                8,5   175744     656069 /usr/bin/lsof
lsof      2369  mao  mem       REG                8,5    51832     667294 /usr/lib/x86_64-linux-gnu/libnss_files-2.31.so
lsof      2369  mao  mem       REG                8,5 14537584     663577 /usr/lib/locale/locale-archive
lsof      2369  mao  mem       REG                8,5   157224     667438 /usr/lib/x86_64-linux-gnu/libpthread-2.31.so
lsof      2369  mao  mem       REG                8,5    18816     666655 /usr/lib/x86_64-linux-gnu/libdl-2.31.so
lsof      2369  mao  mem       REG                8,5   584392     667381 /usr/lib/x86_64-linux-gnu/libpcre2-8.so.0.9.0
lsof      2369  mao  mem       REG                8,5  2029224     666514 /usr/lib/x86_64-linux-gnu/libc-2.31.so
lsof      2369  mao  mem       REG                8,5   163200     667537 /usr/lib/x86_64-linux-gnu/libselinux.so.1
lsof      2369  mao  mem       REG                8,5   191472     666296 /usr/lib/x86_64-linux-gnu/ld-2.31.so
lsof      2369  mao    0u      CHR              136,0      0t0          3 /dev/pts/0
lsof      2369  mao    1u      CHR              136,0      0t0          3 /dev/pts/0
lsof      2369  mao    2u      CHR              136,0      0t0          3 /dev/pts/0
lsof      2369  mao    3r      DIR               0,23        0          1 /proc
lsof      2369  mao    4r      DIR               0,23        0      58349 /proc/2369/fd
lsof      2369  mao    5w     FIFO               0,12      0t0      58354 pipe
lsof      2369  mao    6r     FIFO               0,12      0t0      58355 pipe
lsof      2370  mao  cwd       DIR                8,5     4096     271582 /home/mao/桌面
lsof      2370  mao  rtd       DIR                8,5     4096          2 /
lsof      2370  mao  txt       REG                8,5   175744     656069 /usr/bin/lsof
lsof      2370  mao  mem       REG                8,5    51832     667294 /usr/lib/x86_64-linux-gnu/libnss_files-2.31.so
lsof      2370  mao  mem       REG                8,5 14537584     663577 /usr/lib/locale/locale-archive
lsof      2370  mao  mem       REG                8,5   157224     667438 /usr/lib/x86_64-linux-gnu/libpthread-2.31.so
lsof      2370  mao  mem       REG                8,5    18816     666655 /usr/lib/x86_64-linux-gnu/libdl-2.31.so
lsof      2370  mao  mem       REG                8,5   584392     667381 /usr/lib/x86_64-linux-gnu/libpcre2-8.so.0.9.0
lsof      2370  mao  mem       REG                8,5  2029224     666514 /usr/lib/x86_64-linux-gnu/libc-2.31.so
lsof      2370  mao  mem       REG                8,5   163200     667537 /usr/lib/x86_64-linux-gnu/libselinux.so.1
lsof      2370  mao  mem       REG                8,5   191472     666296 /usr/lib/x86_64-linux-gnu/ld-2.31.so
lsof      2370  mao    4r     FIFO               0,12      0t0      58354 pipe
lsof      2370  mao    7w     FIFO               0,12      0t0      58355 pipe
mao@ubuntu:~/桌面$ 
```

只列举一部分



执行命令：

```sh
lsof +d /home/mao
```

```sh
mao@ubuntu:~/桌面$ lsof +d /home/mao
COMMAND    PID USER   FD   TYPE DEVICE SIZE/OFF   NODE NAME
tracker-m 1632  mao  cwd    DIR    8,5     4096 688519 /home/mao
dbus-daem 1636  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfsd     1642  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfsd-fus 1648  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfs-udis 1668  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfs-mtp- 1675  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfs-goa- 1680  mao  cwd    DIR    8,5     4096 688519 /home/mao
goa-daemo 1685  mao  cwd    DIR    8,5     4096 688519 /home/mao
goa-ident 1692  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfs-gpho 1697  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfs-afc- 1702  mao  cwd    DIR    8,5     4096 688519 /home/mao
gdm-x-ses 1710  mao  cwd    DIR    8,5     4096 688519 /home/mao
Xorg      1712  mao  cwd    DIR    8,5     4096 688519 /home/mao
gnome-ses 1730  mao  cwd    DIR    8,5     4096 688519 /home/mao
at-spi-bu 1819  mao  cwd    DIR    8,5     4096 688519 /home/mao
dbus-daem 1824  mao  cwd    DIR    8,5     4096 688519 /home/mao
gnome-ses 1828  mao  cwd    DIR    8,5     4096 688519 /home/mao
gnome-ses 1835  mao  cwd    DIR    8,5     4096 688519 /home/mao
gnome-she 1849  mao  cwd    DIR    8,5     4096 688519 /home/mao
ibus-daem 1873  mao  cwd    DIR    8,5     4096 688519 /home/mao
ibus-dcon 1877  mao  cwd    DIR    8,5     4096 688519 /home/mao
ibus-exte 1878  mao  cwd    DIR    8,5     4096 688519 /home/mao
ibus-x11  1880  mao  cwd    DIR    8,5     4096 688519 /home/mao
ibus-port 1882  mao  cwd    DIR    8,5     4096 688519 /home/mao
at-spi2-r 1895  mao  cwd    DIR    8,5     4096 688519 /home/mao
xdg-permi 1899  mao  cwd    DIR    8,5     4096 688519 /home/mao
gnome-she 1904  mao  cwd    DIR    8,5     4096 688519 /home/mao
evolution 1910  mao  cwd    DIR    8,5     4096 688519 /home/mao
evolution 1920  mao  cwd    DIR    8,5     4096 688519 /home/mao
dconf-ser 1925  mao  cwd    DIR    8,5     4096 688519 /home/mao
evolution 1937  mao  cwd    DIR    8,5     4096 688519 /home/mao
gjs       1950  mao  cwd    DIR    8,5     4096 688519 /home/mao
gvfsd-tra 1964  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-a11y- 1979  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-color 1980  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-datet 1982  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-house 1986  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-keybo 1987  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-media 1989  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-power 1993  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-print 1995  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-rfkil 1996  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-scree 1997  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-shari 2000  mao  cwd    DIR    8,5     4096 688519 /home/mao
evolution 2004  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-smart 2006  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-sound 2011  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-usb-p 2017  mao  cwd    DIR    8,5     4096 688519 /home/mao
vmtoolsd  2019  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-wacom 2020  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-wwan  2023  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-xsett 2028  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-disk- 2029  mao  cwd    DIR    8,5     4096 688519 /home/mao
ibus-engi 2071  mao  cwd    DIR    8,5     4096 688519 /home/mao
gsd-print 2076  mao  cwd    DIR    8,5     4096 688519 /home/mao
bash      2169  mao  cwd    DIR    8,5     4096 271582 /home/mao/桌面
gvfsd-met 2213  mao  cwd    DIR    8,5     4096 688519 /home/mao
update-no 2226  mao  cwd    DIR    8,5     4096 688519 /home/mao
deja-dup- 2322  mao  cwd    DIR    8,5     4096 688519 /home/mao
lsof      2418  mao  cwd    DIR    8,5     4096 271582 /home/mao/桌面
lsof      2419  mao  cwd    DIR    8,5     4096 271582 /home/mao/桌面
mao@ubuntu:~/桌面$ 
```



执行命令：

```sh
lsof -c lsof
```

```sh
mao@ubuntu:~/桌面$ lsof -c lsof
COMMAND  PID USER   FD   TYPE DEVICE SIZE/OFF   NODE NAME
lsof    2431  mao  cwd    DIR    8,5     4096 271582 /home/mao/桌面
lsof    2431  mao  rtd    DIR    8,5     4096      2 /
lsof    2431  mao  txt    REG    8,5   175744 656069 /usr/bin/lsof
lsof    2431  mao  mem    REG    8,5 14537584 663577 /usr/lib/locale/locale-archive
lsof    2431  mao  mem    REG    8,5   157224 667438 /usr/lib/x86_64-linux-gnu/libpthread-2.31.so
lsof    2431  mao  mem    REG    8,5    18816 666655 /usr/lib/x86_64-linux-gnu/libdl-2.31.so
lsof    2431  mao  mem    REG    8,5   584392 667381 /usr/lib/x86_64-linux-gnu/libpcre2-8.so.0.9.0
lsof    2431  mao  mem    REG    8,5  2029224 666514 /usr/lib/x86_64-linux-gnu/libc-2.31.so
lsof    2431  mao  mem    REG    8,5   163200 667537 /usr/lib/x86_64-linux-gnu/libselinux.so.1
lsof    2431  mao  mem    REG    8,5   191472 666296 /usr/lib/x86_64-linux-gnu/ld-2.31.so
lsof    2431  mao    0u   CHR  136,0      0t0      3 /dev/pts/0
lsof    2431  mao    1u   CHR  136,0      0t0      3 /dev/pts/0
lsof    2431  mao    2u   CHR  136,0      0t0      3 /dev/pts/0
lsof    2431  mao    3r   DIR   0,23        0      1 /proc
lsof    2431  mao    4r   DIR   0,23        0  86115 /proc/2431/fd
lsof    2431  mao    5w  FIFO   0,12      0t0  86120 pipe
lsof    2431  mao    6r  FIFO   0,12      0t0  86121 pipe
lsof    2432  mao  cwd    DIR    8,5     4096 271582 /home/mao/桌面
lsof    2432  mao  rtd    DIR    8,5     4096      2 /
lsof    2432  mao  txt    REG    8,5   175744 656069 /usr/bin/lsof
lsof    2432  mao  mem    REG    8,5 14537584 663577 /usr/lib/locale/locale-archive
lsof    2432  mao  mem    REG    8,5   157224 667438 /usr/lib/x86_64-linux-gnu/libpthread-2.31.so
lsof    2432  mao  mem    REG    8,5    18816 666655 /usr/lib/x86_64-linux-gnu/libdl-2.31.so
lsof    2432  mao  mem    REG    8,5   584392 667381 /usr/lib/x86_64-linux-gnu/libpcre2-8.so.0.9.0
lsof    2432  mao  mem    REG    8,5  2029224 666514 /usr/lib/x86_64-linux-gnu/libc-2.31.so
lsof    2432  mao  mem    REG    8,5   163200 667537 /usr/lib/x86_64-linux-gnu/libselinux.so.1
lsof    2432  mao  mem    REG    8,5   191472 666296 /usr/lib/x86_64-linux-gnu/ld-2.31.so
lsof    2432  mao    4r  FIFO   0,12      0t0  86120 pipe
lsof    2432  mao    7w  FIFO   0,12      0t0  86121 pipe
mao@ubuntu:~/桌面$ 
```







## 进程优先级

Linux 是一个多用户、多任务的操作系统，系统中通常运行着非常多的进程。但是 CPU 在一个时钟周期内只能运算一条指令。谁应该先运算，谁应该后运算呢？这就需要由进程的优先级来决定了。

CPU 在运算数据时，不是把一个集成算完成，再进行下一个进程的运算，而是先运算进程 1，再运算进程 2，接下来运算进程 3，然后再运算进程 1，直到进程任务结束。不仅如此，由于进程优先级的存在，进程并不是依次运算的，而是哪个进程的优先级高，哪个进程会在一次运算循环中被更多次地运算。



在ps -le命令中，PRI 代表 Priority，NI 代表 Nice。这两个值都表示优先级，数值越小代表该进程越优先被 CPU 处理。不过，PRI值是由内核动态调整的，用户不能直接修改。所以我们只能通过修改 NI 值来影响 PRI 值，间接地调整进程优先级。



PRI 和 NI 的关系如下：

```
PRI (最终值) = PRI (原始值) + NI
```

NI 值越小，进程的 PRI 就会降低，该进程就越优先被 CPU 处理；反之，NI 值越大，进程的 PRI 值就会増加，该进程就越靠后被 CPU 处理



修改 NI 值时有几个注意事项：

- NI 范围是 -20~19。
- 普通用户调整 NI 值的范围是 0~19，而且只能调整自己的进程。
- 普通用户只能调高 NI 值，而不能降低。如原本 NI 值为 0，则只能调整为大于 0。
- 只有 root 用户才能设定进程 NI 值为负值，而且可以调整任何用户的进程。







## nice命令

**改变进程优先级**

nice 命令可以给要启动的进程赋予 NI 值，但是不能修改已运行进程的 NI 值。



命令：

```sh
nice [-n NI值] 命令
```



-n NI值：给命令赋予 NI 值，该值的范围为 -20~19



```sh
mao@ubuntu:~/桌面$ nice --help
用法：nice [选项] [命令 [参数]...]
以指定的优先级运行命令，这会影响相应进程的调度。
如果不指定命令，程序会显示当前的优先级。优先级的范围是从 -20
（最大优先级）到 19（最小优先级）。

必选参数对长短选项同时适用。
  -n, --adjustment=N   在优先级数值上加上数字 N（默认为 10）
      --help		显示此帮助信息并退出
      --version		显示版本信息并退出
```





## renice 命令

renice 命令同nice 命令恰恰相反，renice 命令**可以在进程运行时修改其 NI 值，从而调整优先级**。



命令：

```sh
renice [优先级] PID
```



```sh
mao@ubuntu:~/桌面$ top -u mao

top - 07:08:20 up 23 min,  1 user,  load average: 0.06, 0.02, 0.05
任务: 396 total,   2 running, 394 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2174.3 free,    973.0 used,    754.1 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2689.7 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND                                
   1712 mao       20   0  298788  71416  39580 S   2.3   1.8   0:18.55 Xorg                                   
   1849 mao       20   0 4304276 257368 113568 S   1.7   6.4   0:17.88 gnome-shell                            
   2161 mao       20   0  908648  66740  50176 S   1.0   1.7   0:06.54 gnome-terminal-                        
   2019 mao       20   0  302056  42840  30748 R   0.7   1.1   0:03.19 vmtoolsd                               
   1895 mao       20   0  162836   7660   6888 S   0.3   0.2   0:00.81 at-spi2-registr                        
   2541 mao       20   0   20812   4084   3292 R   0.3   0.1   0:00.08 top                                    
   1624 mao       20   0   19100  10316   8036 S   0.0   0.3   0:00.35 systemd                                
   1625 mao       20   0  169024   3492      4 S   0.0   0.1   0:00.00 (sd-pam)                               
   1630 mao        9 -11 1491488  20332  15608 S   0.0   0.5   0:00.24 pulseaudio                             
   1632 mao       39  19  520156  25080  17020 S   0.0   0.6   0:00.19 tracker-miner-f                        
   1636 mao       20   0   11152   8332   3996 S   0.0   0.2   0:00.61 dbus-daemon                            
   1640 mao       20   0  249128   7500   6592 S   0.0   0.2   0:00.08 gnome-keyring-d                        
   1642 mao       20   0  248432   7996   6992 S   0.0   0.2   0:00.07 gvfsd                                  
   1648 mao       20   0  382064   8040   7184 S   0.0   0.2   0:00.02 gvfsd-fuse                             
   1668 mao       20   0  326080  11580   9700 S   0.0   0.3   0:00.05 gvfs-udisks2-vo                        
   1675 mao       20   0  244336   6504   5924 S   0.0   0.2   0:00.03 gvfs-mtp-volume                        
   1680 mao       20   0  244508   6196   5672 S   0.0   0.2   0:00.03 gvfs-goa-volume                        
   1685 mao       20   0  553836  36768  30824 S   0.0   0.9   0:00.08 goa-daemon                             
   1692 mao       20   0  327168  11552  10244 S   0.0   0.3   0:00.04 goa-identity-se                        
   1697 mao       20   0  246612   6904   6208 S   0.0   0.2   0:00.03 gvfs-gphoto2-vo                        
   1702 mao       20   0  325356   8912   7912 S   0.0   0.2   0:00.16 gvfs-afc-volume                        
   1710 mao       20   0  172804   6520   5888 S   0.0   0.2   0:00.01 gdm-x-session                          
   1730 mao       20   0  199456  15668  13920 S   0.0   0.4   0:00.08 gnome-session-b                        
mao@ubuntu:~/桌面$ 
```



更改Xorg进程的nice优先级为20（可能权限不够）：

```sh
renice -20 1712
```



```sh
mao@ubuntu:~/桌面$ renice -20 1712
renice: 设置 1712 的优先级失败(process ID): 权限不够
mao@ubuntu:~/桌面$ 
```



加权限

```sh
sudo renice -20 1712
```



```sh
mao@ubuntu:~/桌面$ sudo renice -20 1712
[sudo] mao 的密码： 
1712 (process ID) 旧优先级为 0，新优先级为 -20
mao@ubuntu:~/桌面$ 
```



验证：

```sh
mao@ubuntu:~/桌面$ top -u mao

top - 07:11:16 up 26 min,  1 user,  load average: 0.00, 0.02, 0.04
任务: 396 total,   1 running, 395 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.4 total,   2174.3 free,    972.2 used,    754.9 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2690.5 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND                                
   1712 mao        0 -20  298788  71416  39580 S   2.3   1.8   0:19.95 Xorg                                   
   2161 mao       20   0  908648  66740  50176 S   1.3   1.7   0:07.21 gnome-terminal-                        
   1849 mao       20   0 4304276 257368 113568 S   1.0   6.4   0:18.93 gnome-shell                            
   2019 mao       20   0  302056  42840  30748 S   0.7   1.1   0:03.61 vmtoolsd                               
   2546 mao       20   0   20812   4048   3260 R   0.7   0.1   0:00.02 top                                    
   1624 mao       20   0   19100  10316   8036 S   0.0   0.3   0:00.35 systemd                                
   1625 mao       20   0  169024   3492      4 S   0.0   0.1   0:00.00 (sd-pam)                               
   1630 mao        9 -11 1491488  20332  15608 S   0.0   0.5   0:00.24 pulseaudio                             
   1632 mao       39  19  520156  25080  17020 S   0.0   0.6   0:00.19 tracker-miner-f                        
   1636 mao       20   0   11152   8332   3996 S   0.0   0.2   0:00.61 dbus-daemon                            
   1640 mao       20   0  249128   7500   6592 S   0.0   0.2   0:00.08 gnome-keyring-d                        
   1642 mao       20   0  248432   7996   6992 S   0.0   0.2   0:00.07 gvfsd                                  
   1648 mao       20   0  382064   8040   7184 S   0.0   0.2   0:00.02 gvfsd-fuse                             
   1668 mao       20   0  326080  11580   9700 S   0.0   0.3   0:00.05 gvfs-udisks2-vo                        
   1675 mao       20   0  244336   6504   5924 S   0.0   0.2   0:00.03 gvfs-mtp-volume                        
   1680 mao       20   0  244508   6196   5672 S   0.0   0.2   0:00.03 gvfs-goa-volume                        
   1685 mao       20   0  553836  36768  30824 S   0.0   0.9   0:00.08 goa-daemon                             
   1692 mao       20   0  327168  11552  10244 S   0.0   0.3   0:00.04 goa-identity-se                        
   1697 mao       20   0  246612   6904   6208 S   0.0   0.2   0:00.03 gvfs-gphoto2-vo                        
   1702 mao       20   0  325356   8912   7912 S   0.0   0.2   0:00.18 gvfs-afc-volume                        
   1710 mao       20   0  172804   6520   5888 S   0.0   0.2   0:00.01 gdm-x-session                          
   1730 mao       20   0  199456  15668  13920 S   0.0   0.4   0:00.08 gnome-session-b                        
   1799 mao       20   0    6040    452      0 S   0.0   0.0   0:00.01 ssh-agent                              
mao@ubuntu:~/桌面$ 
```







## 进程间通信常用信号



查看信号：

```sh
mao@ubuntu:~/桌面$ kill -l
 1) SIGHUP	 2) SIGINT	 3) SIGQUIT	 4) SIGILL	 5) SIGTRAP
 6) SIGABRT	 7) SIGBUS	 8) SIGFPE	 9) SIGKILL	10) SIGUSR1
11) SIGSEGV	12) SIGUSR2	13) SIGPIPE	14) SIGALRM	15) SIGTERM
16) SIGSTKFLT	17) SIGCHLD	18) SIGCONT	19) SIGSTOP	20) SIGTSTP
21) SIGTTIN	22) SIGTTOU	23) SIGURG	24) SIGXCPU	25) SIGXFSZ
26) SIGVTALRM	27) SIGPROF	28) SIGWINCH	29) SIGIO	30) SIGPWR
31) SIGSYS	34) SIGRTMIN	35) SIGRTMIN+1	36) SIGRTMIN+2	37) SIGRTMIN+3
38) SIGRTMIN+4	39) SIGRTMIN+5	40) SIGRTMIN+6	41) SIGRTMIN+7	42) SIGRTMIN+8
43) SIGRTMIN+9	44) SIGRTMIN+10	45) SIGRTMIN+11	46) SIGRTMIN+12	47) SIGRTMIN+13
48) SIGRTMIN+14	49) SIGRTMIN+15	50) SIGRTMAX-14	51) SIGRTMAX-13	52) SIGRTMAX-12
53) SIGRTMAX-11	54) SIGRTMAX-10	55) SIGRTMAX-9	56) SIGRTMAX-8	57) SIGRTMAX-7
58) SIGRTMAX-6	59) SIGRTMAX-5	60) SIGRTMAX-4	61) SIGRTMAX-3	62) SIGRTMAX-2
63) SIGRTMAX-1	64) SIGRTMAX	
mao@ubuntu:~/桌面$ 
```



| 信号代号 | 信号名称 |                            说 明                             |
| :------: | :------: | :----------------------------------------------------------: |
|    1     |  SIGHUP  |      该信号让进程立即关闭，然后重新读取配置文件之后重启      |
|    2     |  SIGINT  |   程序中止信号，用于中止前台进程。相当于输出 Ctrl+C 快捷键   |
|    8     |  SIGFPE  | 在发生致命的算术运算错误时发出。不仅包括浮点运算错误，还包括溢出及除数为 0 等其他所有的算术运算错误 |
|    9     | SIGKILL  | 用来立即结束程序的运行。本信号不能被阻塞、处理和忽略。般用于强制中止进程 |
|    14    | SIGALRM  | 时钟定时信号，计算的是实际的时间或时钟时间。alarm 函数使用该信号 |
|    15    | SIGTERM  | 正常结束进程的信号，kill 命令的默认信号。如果进程已经发生了问题，那么这 个信号是无法正常中止进程的，这时我们才会尝试 SIGKILL 信号，也就是信号 9 |
|    18    | SIGCONT  |       该信号可以让暂停的进程恢复执行。本信号不能被阻断       |
|    19    | SIGSTOP  | 该信号可以暂停前台进程，相当于输入 Ctrl+Z 快捷键。本信号不能被阻断 |







## kill命令

终止进程

kill 命令只是用来向进程发送一个信号，至于这个信号是什么，是用户指定的



命令：

```sh
kill [信号] PID
```

kill 命令是按照 PID 来确定进程的，所以 kill 命令只能识别 PID，而不能识别进程名



| 信号编号 | 信号名 |                             含义                             |
| :------: | :----: | :----------------------------------------------------------: |
|    0     |  EXIT  |                    程序退出时收到该信息。                    |
|    1     |  HUP   | 终端连接的挂起信号，这个信号也会造成某些进程在没有终止的情况下重新初始化。 |
|    2     |  INT   | 表示结束进程，但并不是强制性的，常用的 "Ctrl+C" 组合键发出就是一个 kill -2 的信号。 |
|    3     |  QUIT  |                            退出。                            |
|    9     |  KILL  |                  杀死进程，即强制结束进程。                  |
|    11    |  SEGV  |                           段错误。                           |
|    15    |  TERM  |            正常结束进程，是 kill 命令的默认信号。            |



```sh
PS C:\Users\mao\Desktop> docker ps -a
CONTAINER ID   IMAGE                     COMMAND                  CREATED              STATUS                          PORTS              NAMES
7527b9b49817   docker_compose_boot:1.0   "java -jar Docker_co…"   About a minute ago   Up About a minute               80/tcp, 8080/tcp   sad_archimedes
889e0484bdd2   centos                    "/bin/bash"              6 days ago           Exited (130) 3 days ago                            centos
e331c5c18f3f   ubuntu                    "bash"                   8 days ago           Exited (137) 5 days ago                            ubuntu
bc3a894f3f5a   mysql                     "docker-entrypoint.s…"   2 weeks ago          Exited (0) 2 weeks ago                             mysql3
acc4ae47d7fe   mysql                     "docker-entrypoint.s…"   2 weeks ago          Exited (0) 2 weeks ago                             mysql2
1219851e3bc5   grafana/grafana           "/run.sh"                2 weeks ago          Exited (0) 2 minutes ago                           desktop_grafana_1
059cf60a61b1   google/cadvisor           "/usr/bin/cadvisor -…"   2 weeks ago          Exited (0) 2 minutes ago                           desktop_cadvisor_1
71da6b2b40a2   tutum/influxdb:0.9        "/run.sh"                2 weeks ago          Exited (0) About a minute ago                      desktop_influxdb_1
e955fb5f7a77   docker_compose_boot:1.0   "java -jar Docker_co…"   2 weeks ago          Exited (143) 2 weeks ago                           docker_compose_boot1
72a29340a31e   redis                     "docker-entrypoint.s…"   2 weeks ago          Exited (0) 2 weeks ago                             compose_redis
ce530f498cc4   mysql                     "docker-entrypoint.s…"   2 weeks ago          Exited (0) 2 weeks ago                             compose_mysql
8a8076944128   redis                     "docker-entrypoint.s…"   3 weeks ago          Exited (0) 23 hours ago                            redis1
2d379d342bb6   mysql                     "docker-entrypoint.s…"   3 weeks ago          Exited (0) 3 weeks ago                             mysql1
3ca156e4541d   tomcat                    "catalina.sh run"        3 weeks ago          Exited (143) 2 weeks ago                           tomcat1
PS C:\Users\mao\Desktop> docker exec -it 7527b9b49817 /bin/bash
root@7527b9b49817:/usr/local#

```

```sh
root@7527b9b49817:/usr/local# top
top - 13:20:55 up 3 min,  0 users,  load average: 0.02, 0.05, 0.01
Tasks:   4 total,   1 running,   3 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.1 sy,  0.0 ni, 99.8 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :  12723.3 total,  10776.9 free,    792.8 used,   1153.5 buff/cache
MiB Swap:   4096.0 total,   4096.0 free,      0.0 used.  11681.3 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    1 root      20   0 8865520 293864  26828 S   0.3   2.3   0:19.13 java
   56 root      20   0    2884    952    860 S   0.0   0.0   0:00.02 sh
   81 root      20   0    4620   3592   3112 S   0.0   0.0   0:00.02 bash
   89 root      20   0    7336   3344   2776 R   0.0   0.0   0:00.00 top
```



查看日志：

```sh
root@7527b9b49817:/usr/local# cat server.log
2022-07-09 13:17:54.969  INFO 1 --- [main] m.d.DockerComposeBootApplication         : Starting DockerComposeBootApplication v0.0.1-SNAPSHOT using Java 17.0.3.1 on 7527b9b49817 with PID 1 (/usr/local/Docker_compose_boot.jar started by root in /usr/local)
2022-07-09 13:17:54.973 DEBUG 1 --- [main] m.d.DockerComposeBootApplication         : Running with Spring Boot v2.7.0, Spring v5.3.20
2022-07-09 13:17:54.973  INFO 1 --- [main] m.d.DockerComposeBootApplication         : The following 1 profile is active: "dev"
2022-07-09 13:17:55.874  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2022-07-09 13:17:55.878  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data Redis repositories in DEFAULT mode.
2022-07-09 13:17:55.906  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 9 ms. Found 0 Redis repository interfaces.
2022-07-09 13:17:56.714  INFO 1 --- [main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-07-09 13:17:56.729  INFO 1 --- [main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-07-09 13:17:56.730  INFO 1 --- [main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.63]
2022-07-09 13:17:56.810  INFO 1 --- [main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-07-09 13:17:56.811  INFO 1 --- [main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1769 ms
2022-07-09 13:17:56.924  INFO 1 --- [main] c.a.d.s.b.a.DruidDataSourceAutoConfigure : Init DruidDataSource
2022-07-09 13:17:57.191  INFO 1 --- [main] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} inited
2022-07-09 13:17:58.613  INFO 1 --- [main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-07-09 13:17:58.630  INFO 1 --- [main] m.d.DockerComposeBootApplication         : Started DockerComposeBootApplication in 4.4 seconds (JVM running for 5.044)
root@7527b9b49817:/usr/local#
```



杀死pid为1的进程，使用信号2，这是一个spring boot项目实例

```sh
kill 2 1
```



```sh
root@7527b9b49817:/usr/local# kill 2 1
bash: kill: (2) - No such process
root@7527b9b49817:/usr/local#
PS C:\Users\mao\Desktop>
```



再次通过查看日志，通过docker命令

```sh
PS C:\Users\mao\Desktop> docker logs 7527b9b49817

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.0)

2022-07-09 13:17:54.969  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : Starting DockerComposeBootApplication v0.0.1-SNAPSHOT using Java 17.0.3.1 on 7527b9b49817 with PID 1 (/usr/local/Docker_compose_boot.jar started by root in /usr/local)
2022-07-09 13:17:54.973 DEBUG 1 --- [           main] m.d.DockerComposeBootApplication         : Running with Spring Boot v2.7.0, Spring v5.3.20
2022-07-09 13:17:54.973  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : The following 1 profile is active: "dev"
2022-07-09 13:17:55.874  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2022-07-09 13:17:55.878  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data Redis repositories in DEFAULT mode.
2022-07-09 13:17:55.906  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 9 ms. Found 0 Redis repository interfaces.
2022-07-09 13:17:56.714  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-07-09 13:17:56.729  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-07-09 13:17:56.730  INFO 1 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.63]
2022-07-09 13:17:56.810  INFO 1 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-07-09 13:17:56.811  INFO 1 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1769 ms
2022-07-09 13:17:56.924  INFO 1 --- [           main] c.a.d.s.b.a.DruidDataSourceAutoConfigure : Init DruidDataSource
2022-07-09 13:17:57.191  INFO 1 --- [           main] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} inited
 _ _   |_  _ _|_. ___ _ |    _
| | |\/|_)(_| | |_\  |_)||_|_\
     /               |
                        3.5.1
2022-07-09 13:17:58.613  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-07-09 13:17:58.630  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : Started DockerComposeBootApplication in 4.4 seconds (JVM running for 5.044)
2022-07-09 13:26:38.035  INFO 1 --- [ionShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closing ...
2022-07-09 13:26:38.036  INFO 1 --- [ionShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closed
PS C:\Users\mao\Desktop>
```



发现使用信号2 ，退出前打印了一部分内容

```sh
2022-07-09 13:26:38.035  INFO 1 --- [ionShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closing ...
2022-07-09 13:26:38.036  INFO 1 --- [ionShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closed
```



再次启动，进入容器：

```sh
docker start 7527b9b49817
```

```sh
docker exec -it 7527b9b49817 /bin/bash
```





查看日志：

```sh
root@7527b9b49817:/usr/local# ls
Docker_compose_boot.jar  bin  etc  games  include  java  lib  man  sbin  server.log  share  src
root@7527b9b49817:/usr/local# cat server.log
2022-07-09 13:17:54.969  INFO 1 --- [main] m.d.DockerComposeBootApplication         : Starting DockerComposeBootApplication v0.0.1-SNAPSHOT using Java 17.0.3.1 on 7527b9b49817 with PID 1 (/usr/local/Docker_compose_boot.jar started by root in /usr/local)
2022-07-09 13:17:54.973 DEBUG 1 --- [main] m.d.DockerComposeBootApplication         : Running with Spring Boot v2.7.0, Spring v5.3.20
2022-07-09 13:17:54.973  INFO 1 --- [main] m.d.DockerComposeBootApplication         : The following 1 profile is active: "dev"
2022-07-09 13:17:55.874  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2022-07-09 13:17:55.878  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data Redis repositories in DEFAULT mode.
2022-07-09 13:17:55.906  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 9 ms. Found 0 Redis repository interfaces.
2022-07-09 13:17:56.714  INFO 1 --- [main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-07-09 13:17:56.729  INFO 1 --- [main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-07-09 13:17:56.730  INFO 1 --- [main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.63]
2022-07-09 13:17:56.810  INFO 1 --- [main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-07-09 13:17:56.811  INFO 1 --- [main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1769 ms
2022-07-09 13:17:56.924  INFO 1 --- [main] c.a.d.s.b.a.DruidDataSourceAutoConfigure : Init DruidDataSource
2022-07-09 13:17:57.191  INFO 1 --- [main] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} inited
2022-07-09 13:17:58.613  INFO 1 --- [main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-07-09 13:17:58.630  INFO 1 --- [main] m.d.DockerComposeBootApplication         : Started DockerComposeBootApplication in 4.4 seconds (JVM running for 5.044)
2022-07-09 13:26:38.035  INFO 1 --- [SpringApplicationShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closing ...
2022-07-09 13:26:38.036  INFO 1 --- [SpringApplicationShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closed
2022-07-09 13:31:48.914  INFO 1 --- [main] m.d.DockerComposeBootApplication         : Starting DockerComposeBootApplication v0.0.1-SNAPSHOT using Java 17.0.3.1 on 7527b9b49817 with PID 1 (/usr/local/Docker_compose_boot.jar started by root in /usr/local)
2022-07-09 13:31:48.917 DEBUG 1 --- [main] m.d.DockerComposeBootApplication         : Running with Spring Boot v2.7.0, Spring v5.3.20
2022-07-09 13:31:48.918  INFO 1 --- [main] m.d.DockerComposeBootApplication         : The following 1 profile is active: "dev"
2022-07-09 13:31:49.677  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2022-07-09 13:31:49.680  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data Redis repositories in DEFAULT mode.
2022-07-09 13:31:49.703  INFO 1 --- [main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 8 ms. Found 0 Redis repository interfaces.
2022-07-09 13:31:50.367  INFO 1 --- [main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-07-09 13:31:50.378  INFO 1 --- [main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-07-09 13:31:50.378  INFO 1 --- [main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.63]
2022-07-09 13:31:50.442  INFO 1 --- [main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-07-09 13:31:50.443  INFO 1 --- [main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1469 ms
2022-07-09 13:31:50.537  INFO 1 --- [main] c.a.d.s.b.a.DruidDataSourceAutoConfigure : Init DruidDataSource
2022-07-09 13:31:50.747  INFO 1 --- [main] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} inited
2022-07-09 13:31:51.852  INFO 1 --- [main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-07-09 13:31:51.868  INFO 1 --- [main] m.d.DockerComposeBootApplication         : Started DockerComposeBootApplication in 3.589 seconds (JVM running for 4.021)
root@7527b9b49817:/usr/local#
```



杀死pid为1的进程，使用信号9：

```sh
kill 9 1
```



```sh
root@7527b9b49817:/usr/local# kill 9 1
root@7527b9b49817:/usr/local#
PS C:\Users\mao\Desktop>
```



查看日志：

```sh
PS C:\Users\mao\Desktop> docker logs 7527b9b49817

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.0)

2022-07-09 13:17:54.969  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : Starting DockerComposeBootApplication v0.0.1-SNAPSHOT using Java 17.0.3.1 on 7527b9b49817 with PID 1 (/usr/local/Docker_compose_boot.jar started by root in /usr/local)
2022-07-09 13:17:54.973 DEBUG 1 --- [           main] m.d.DockerComposeBootApplication         : Running with Spring Boot v2.7.0, Spring v5.3.20
2022-07-09 13:17:54.973  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : The following 1 profile is active: "dev"
2022-07-09 13:17:55.874  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2022-07-09 13:17:55.878  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data Redis repositories in DEFAULT mode.
2022-07-09 13:17:55.906  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 9 ms. Found 0 Redis repository interfaces.
2022-07-09 13:17:56.714  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-07-09 13:17:56.729  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-07-09 13:17:56.730  INFO 1 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.63]
2022-07-09 13:17:56.810  INFO 1 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-07-09 13:17:56.811  INFO 1 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1769 ms
2022-07-09 13:17:56.924  INFO 1 --- [           main] c.a.d.s.b.a.DruidDataSourceAutoConfigure : Init DruidDataSource
2022-07-09 13:17:57.191  INFO 1 --- [           main] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} inited
 _ _   |_  _ _|_. ___ _ |    _
| | |\/|_)(_| | |_\  |_)||_|_\
     /               |
                        3.5.1
2022-07-09 13:17:58.613  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-07-09 13:17:58.630  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : Started DockerComposeBootApplication in 4.4 seconds (JVM running for 5.044)
2022-07-09 13:26:38.035  INFO 1 --- [ionShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closing ...
2022-07-09 13:26:38.036  INFO 1 --- [ionShutdownHook] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} closed

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.0)

2022-07-09 13:31:48.914  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : Starting DockerComposeBootApplication v0.0.1-SNAPSHOT using Java 17.0.3.1 on 7527b9b49817 with PID 1 (/usr/local/Docker_compose_boot.jar started by root in /usr/local)
2022-07-09 13:31:48.917 DEBUG 1 --- [           main] m.d.DockerComposeBootApplication         : Running with Spring Boot v2.7.0, Spring v5.3.20
2022-07-09 13:31:48.918  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : The following 1 profile is active: "dev"
2022-07-09 13:31:49.677  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2022-07-09 13:31:49.680  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data Redis repositories in DEFAULT mode.
2022-07-09 13:31:49.703  INFO 1 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 8 ms. Found 0 Redis repository interfaces.
2022-07-09 13:31:50.367  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-07-09 13:31:50.378  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-07-09 13:31:50.378  INFO 1 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.63]
2022-07-09 13:31:50.442  INFO 1 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-07-09 13:31:50.443  INFO 1 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1469 ms
2022-07-09 13:31:50.537  INFO 1 --- [           main] c.a.d.s.b.a.DruidDataSourceAutoConfigure : Init DruidDataSource
2022-07-09 13:31:50.747  INFO 1 --- [           main] com.alibaba.druid.pool.DruidDataSource   : {dataSource-1} inited
 _ _   |_  _ _|_. ___ _ |    _
| | |\/|_)(_| | |_\  |_)||_|_\
     /               |
                        3.5.1
2022-07-09 13:31:51.852  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-07-09 13:31:51.868  INFO 1 --- [           main] m.d.DockerComposeBootApplication         : Started DockerComposeBootApplication in 3.589 seconds (JVM running for 4.021)
PS C:\Users\mao\Desktop>
```









## killall命令

killall 也是用于关闭进程的一个命令，但和 kill 不同的是，killall 命令不再依靠 PID 来杀死单个进程，而是**通过程序的进程名来杀死一类进程**



命令：

```sh
killall [选项] [信号] 进程名
```



选项：

- -i：交互式，询问是否要杀死某个进程；
- -I：忽略进程名的大小写；





## pkill命令

pkill 命令和 killall 命令的用法相同，都是**通过进程名杀死一类进程**



命令：

```sh
pkill [信号] 进程名
```



| 信号编号 | 信号名 |                             含义                             |
| :------: | :----: | :----------------------------------------------------------: |
|    0     |  EXIT  |                    程序退出时收到该信息。                    |
|    1     |  HUP   | 挂掉电话线或终端连接的挂起信号，这个信号也会造成某些进程在没有终止的情况下重新初始化。 |
|    2     |  INT   | 表示结束进程，但并不是强制性的，常用的 "Ctrl+C" 组合键发出就是一个 kill -2 的信号。 |
|    3     |  QUIT  |                            退出。                            |
|    9     |  KILL  |                  杀死进程，即强制结束进程。                  |
|    11    |  SEGV  |                           段错误。                           |
|    15    |  TERM  |            正常结束进程，是 kill 命令的默认信号。            |





```sh
root@7527b9b49817:/usr/local# top
top - 13:39:12 up 21 min,  0 users,  load average: 0.13, 0.16, 0.07
Tasks:   3 total,   1 running,   2 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :  12723.3 total,  10579.5 free,    988.9 used,   1154.9 buff/cache
MiB Swap:   4096.0 total,   4096.0 free,      0.0 used.  11485.3 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    1 root      20   0 8798960 313236  27220 S   0.0   2.4   0:19.84 java
   68 root      20   0    4620   3780   3192 S   0.0   0.0   0:00.02 bash
   77 root      20   0    7336   3276   2708 R   0.0   0.0   0:00.00 top
```



```sh
pkill java
```

```sh
root@7527b9b49817:/usr/local# pkill java
root@7527b9b49817:/usr/local#
PS C:\Users\mao\Desktop>
```





**pkill命令踢出登陆用户：**

```sh
pkill [-t 终端号] 进程名
```

[-t 终端号] 选项用于按照终端号踢出用户；







## 命令放入后台运行

方法一：

在命令后面加入 `空格 &`。使用这种方法放入后台的命令，在后台处于执行状态。



方法二：

命令执行过裎中按 Ctrl+Z 快捷键，命令在后台处于暂停状态



```sh
mao@ubuntu:~/桌面$ ps
    PID TTY          TIME CMD
   2157 pts/0    00:00:00 bash
   2334 pts/0    00:00:00 ps
mao@ubuntu:~/桌面$ ps &
[1] 2335
mao@ubuntu:~/桌面$     PID TTY          TIME CMD
   2157 pts/0    00:00:00 bash
   2335 pts/0    00:00:00 ps

[1]+  已完成               ps
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ top

top - 21:28:49 up 4 min,  1 user,  load average: 0.13, 0.26, 0.14
任务: 445 total,   2 running, 443 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.1 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3901.5 total,   2092.5 free,    986.9 used,    822.1 buff/cache
MiB Swap:    687.5 total,    687.5 free,      0.0 used.   2676.7 avail Mem 

 进程号 USER      PR  NI    VIRT    RES    SHR    %CPU  %MEM     TIME+ COMMAND  
    931 root      20   0 1613188  40232  19788 S   2.0   1.0   0:02.81 snapd    
   1703 mao       20   0  291376  66184  39620 S   2.0   1.7   0:07.07 Xorg     
   2149 mao       20   0  908324  63656  47432 S   1.3   1.6   0:01.90 gnome-t+ 
   1837 mao       20   0 4289004 261860 118428 S   1.0   6.6   0:10.74 gnome-s+ 
    872 root      20   0  248076   7484   6472 S   0.7   0.2   0:01.17 vmtoolsd 
   1693 mao       20   0  325356   9144   8148 S   0.3   0.2   0:00.06 gvfs-af+ 
   1995 mao       20   0  302052  42384  30296 S   0.3   1.1   0:01.18 vmtoolsd 
   2337 mao       20   0   20804   4244   3204 R   0.3   0.1   0:00.03 top      
      1 root      20   0  167596  11432   8336 S   0.0   0.3   0:07.94 systemd  
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.06 kthreadd 
      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp   
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par+ 
      5 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker+ 
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker+ 
      7 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker+ 
      8 root      20   0       0      0      0 I   0.0   0.0   0:00.01 kworker+ 
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 mm_perc+ 
[1]+  已停止               top
mao@ubuntu:~/桌面$ 
```







## jobs 命令

jobs 命令可以**用来查看当前终端放入后台的工作**



命令：

```sh
jobs [选项]
```



|      选项      |                  含义                  |
| :------------: | :------------------------------------: |
| -l（L 的小写） |          列出进程的 PID 号。           |
|       -n       | 只列出上次发出通知后改变了状态的进程。 |
|       -p       |         只列出进程的 PID 号。          |
|       -r       |          只列出运行中的进程。          |
|       -s       |          只列出已停止的进程。          |



+"号代表最近一个放入后台的工作，也是工作恢复时默认恢复的工作。"-"号代表倒数第二个放入后台的工作，而第三个以后的工作就没有"+-"标志了



```sh
mao@ubuntu:~/桌面$ jobs
[1]+  已停止               top
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ jobs -l
[1]+  2337 停止 (信号)         top
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ jobs -n
mao@ubuntu:~/桌面$ jobs -p
2337
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ jobs -r
mao@ubuntu:~/桌面$ jobs -s
[1]+  已停止               top
mao@ubuntu:~/桌面$ 
```





## fg命令

fg 命令**用于把后台工作恢复到前台执行**



命令：

```sh
fg %工作号
```

在使用此命令时，％ 可以省略，但若将`% 工作号`全部省略，则此命令会将带有 + 号的工作恢复到前台。



```sh
mao@ubuntu:~/桌面$ jobs
[1]+  已停止               vi
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ fg 1
vi
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ jobs
mao@ubuntu:~/桌面$ 
```





top 命令是不能在后台执行的，所以，如果要想中止 top 命令，要么把 top 命令恢复到前台，然后正常退出；要么找到 top 命令的 PID，使用 kill 命令杀死这个进程。







## bg命令

bg 命令用于**把后台暂停的工作恢复到后台执行**



命令：

```sh
bg ％工作号
```



```sh
mao@ubuntu:~/桌面$ jobs
mao@ubuntu:~/桌面$ vi

[1]+  已停止               vi
mao@ubuntu:~/桌面$ jobs
[1]+  已停止               vi
mao@ubuntu:~/桌面$ bg 1
[1]+ vi &
mao@ubuntu:~/桌面$ 
```





## nohup命令

nohup 命令的作用就是**让后台工作在离开操作终端时，也能够正确地在后台执行**



命令：

```sh
nohup [命令] &
```



&’表示此命令会在终端后台工作；反之，如果没有‘&’，则表示此命令会在终端前台工作







## at命令

安装at 软件包，并开启 atd 服务



```sh
yum -y install at
```

或者

```sh
sudo apt install at
```



```sh
mao@ubuntu:~/桌面$ at

Command 'at' not found, but can be installed with:

sudo apt install at

mao@ubuntu:~/桌面$ sudo apt install at
[sudo] mao 的密码： 
正在读取软件包列表... 完成
正在分析软件包的依赖关系树       
正在读取状态信息... 完成       
将会同时安装下列软件：
  libfl2
建议安装：
  default-mta | mail-transport-agent
下列【新】软件包将被安装：
  at libfl2
升级了 0 个软件包，新安装了 2 个软件包，要卸载 0 个软件包，有 61 个软件包未被升级。
需要下载 50.1 kB 的归档。
解压缩后会消耗 241 kB 的额外空间。
您希望继续执行吗？ [Y/n] y
获取:1 http://cn.archive.ubuntu.com/ubuntu focal/main amd64 libfl2 amd64 2.6.4-6.2 [11.5 kB]
获取:2 http://cn.archive.ubuntu.com/ubuntu focal/main amd64 at amd64 3.1.23-1ubuntu1 [38.7 kB]
已下载 50.1 kB，耗时 7秒 (7,230 B/s)                                           
正在选中未选择的软件包 libfl2:amd64。
(正在读取数据库 ... 系统当前共安装有 195447 个文件和目录。)
准备解压 .../libfl2_2.6.4-6.2_amd64.deb  ...
正在解压 libfl2:amd64 (2.6.4-6.2) ...
正在选中未选择的软件包 at。
准备解压 .../at_3.1.23-1ubuntu1_amd64.deb  ...
正在解压 at (3.1.23-1ubuntu1) ...
正在设置 libfl2:amd64 (2.6.4-6.2) ...
正在设置 at (3.1.23-1ubuntu1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/atd.service → /lib/s
ystemd/system/atd.service.
正在处理用于 systemd (245.4-4ubuntu3.11) 的触发器 ...
正在处理用于 man-db (2.9.1-1) 的触发器 ...
正在处理用于 libc-bin (2.31-0ubuntu9.2) 的触发器 ...
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ type at
at 已被录入哈希表 (/usr/bin/at)
mao@ubuntu:~/桌面$ at
Garbled time
mao@ubuntu:~/桌面$ 
```



at 命令要想正确执行，还需要 atd 服务的支持。atd 服务是独立的服务，启动的命令如下：

```sh
service atd start
```



需要验证密码

```sh
mao@ubuntu:~/桌面$ service atd start
mao@ubuntu:~/桌面$ 
```



如果想让 atd 服务开机时自启动，则可以使用如下命令：

```sh
chkconfig atd on
```

独立服务的自启动也可以修改 /etc/rc.local 配置文件

我系统无此命令





**访问控制**指的是允许哪些用户使用 at 命令设定定时任务，或者不允许哪些用户使用 at 命令。



at 命令的访问控制是依靠 /etc/at.allow（白名单）和 /etc/at.deny（黑名单）这两个文件来实现的，具体规则如下：

- 如果系统中有 /etc/at.allow 文件，那么只有写入 /etc/at.allow 文件（白名单）中的用户可以使用 at 命令，其他用户不能使用 at 命令（注意，/etc/at.allow 文件的优先级更高，也就是说，如果同一个用户既写入 /etc/at.allow 文件，又写入 /etc/at.deny 文件，那么这个用户是可以使用 at 命令的）。
- 如果系统中没有 /etc/at.allow 文件，只有 /etc/at.deny 文件，那么写入 /etc/at.deny 文件（黑名单）中的用户不能使用 at 命令，其他用户可以使用 at 命令。不过这个文件对 root 用户不生效。
- 如果系统中这两个文件都不存在，那么只有 root 用户可以使用 at 命令。



系统中默认只有 /etc/at.deny 文件，而且这个文件是空的，因此，系统中所有的用户都可以使用 at 命令





at命令：

```sh
at [选项] [时间]
```



|     选项      |                             含义                             |
| :-----------: | :----------------------------------------------------------: |
|      -m       | 当 at 工作完成后，无论命令是否输出，都用 E-mail 通知执行 at 命令的用户。 |
| -c 工作标识号 |                  显示该 at 工作的实际内容。                  |
|    -t 时间    |   在指定时间提交工作并执行，时间格式为 [[CC]YY]MMDDhhmm。    |
|      -d       | 删除某个工作，需要提供相应的工作标识号（ID），同 atrm 命令的作用相同。 |
|      -l       |  列出当前所有等待运行的工作，和 atq 命令具有相同的额作用。   |
|  -f 脚本文件  |                   指定所要提交的脚本文件。                   |



|            格式            |                             用法                             |
| :------------------------: | :----------------------------------------------------------: |
|           HH:MM            | 比如 04:00 AM。如果时间已过，则它会在第二天的同一时间执行。  |
|    Midnight（midnight）    |                代表 12:00 AM（也就是 00:00）                 |
|        Noon（noon）        |                代表 12:00 PM（相当于 12:00）                 |
|     Teatime（teatime）     |                 代表 4:00 PM（相当于 16:00）                 |
|     英文月名 日期 年份     | 比如 January 15 2018 表示 2018 年 1 月 15 号，年份可有可无。 |
| MMDDYY、MM/DD/YY、MM.DD.YY |            比如 011518 表示 2018 年 1 月 15 号。             |
|          now+时间          | 以 minutes、hours、days 或 weeks 为单位，例如 now+5 days 表示命令在 5 天之后的此时此刻执行。 |



at 命令只要指定正确的时间，就可以输入需要在指定时间执行的命令。这个命令可以是系统命令，也可以是 Shell 脚本

使用Ctrl+D快捷键保存at任务



```sh
mao@ubuntu:~/桌面$ touch 3.txt
mao@ubuntu:~/桌面$ cat 1.txt
123
mao@ubuntu:~/桌面$ at now +1 minutes
warning: commands will be executed using /bin/sh
at> cat 1.txt > 3.txt
at> <EOT>
job 3 at Sat Jul  9 22:14:00 2022
mao@ubuntu:~/桌面$ 
mao@ubuntu:~/桌面$ cat 3.txt
123
mao@ubuntu:~/桌面$ 
```



atq 命令用于查看当前等待运行的工作，atrm 命令后者用于删除指定的工作







## crontab命令

循环执行定时任务

crontab 命令需要 crond 服务支持。crond 是 Linux 下用来周期地执行某种任务或等待处理某些事件的一个守护进程



启动crond ：

```sh
service crond restart
```

设定crond服务为开机自启动：

```sh
chkconfig crond on
```



该命令和 at 命令类似，也是通过 /etc/cron.allow 和 /etc/cron.deny 文件来限制某些用户是否可以使用 crontab 命令的。而且原则也非常相似：

- 当系统中有 /etc/cron.allow 文件时，只有写入此文件的用户可以使用 crontab 命令，没有写入的用户不能使用 crontab 命令。同样，如果有此文件，/etc/cron.deny 文件会被忽略，因为 /etc/cron.allow 文件的优先级更高。
- 当系统中只有 /etc/cron.deny 文件时，写入此文件的用户不能使用 crontab 命令，没有写入文件的用户可以使用 crontab 命令。
- 这个规则基本和 at 命令的规则一致，同样是 /etc/cron.allow 文件比 /etc/cron.deny 文件的优先级高，Linux 系统中默认只有 /etc/cron.deny 文件。



命令：

```sh
crontab [选项] [file]
```

 file 指的是命令文件的名字，表示将 file 作为 crontab 的任务列表文件并载入 crontab，若在命令行中未指定文件名，则此命令将接受标准输入（键盘）上键入的命令，并将它们键入 crontab



|  选项   |                             功能                             |
| :-----: | :----------------------------------------------------------: |
| -u user | 用来设定某个用户的 crontab 服务，例如 "-u demo" 表示设备 demo 用户的 crontab 服务，此选项一般有 root 用户来运行。 |
|   -e    | 编辑某个用户的 crontab 文件内容。如果不指定用户，则表示编辑当前用户的 crontab 文件。 |
|   -l    | 显示某用户的 crontab 文件内容，如果不指定用户，则表示显示当前用户的 crontab 文件内容。 |
|   -r    | 从 /var/spool/cron 删除某用户的 crontab 文件，如果不指定用户，则默认删除当前用户的 crontab 文件。 |
|   -i    |          在删除用户的 crontab 文件时，给确认提示。           |



|   项目    |              含义              |          范围           |
| :-------: | :----------------------------: | :---------------------: |
| 第一个"*" | 一小时当中的第几分钟（minute） |          0~59           |
| 第二个"*" |   一天当中的第几小时（hour）   |          0~23           |
| 第三个"*" |   一个月当中的第几天（day）    |          1~31           |
| 第四个"*" |  一年当中的第几个月（month）   |          1~12           |
| 第五个"*" |    一周当中的星期几（week）    | 0~7（0和7都代表星期日） |



|  特殊符号   |                             含义                             |
| :---------: | :----------------------------------------------------------: |
|  *（星号）  | 代表任何时间。比如第一个"*"就代表一小时种每分钟都执行一次的意思。 |
|  ,（逗号）  | 代表不连续的时间。比如"0 8，12，16***命令"就代表在每天的 8 点 0 分、12 点 0 分、16 点 0 分都执行一次命令。 |
|  -（中杠）  | 代表连续的时间范围。比如"0 5 ** 1-6命令"，代表在周一到周六的凌晨 5 点 0 分执行命令。 |
| /（正斜线） | 代表每隔多久执行一次。比如"*/10****命令"，代表每隔 10 分钟就执行一次命令。 |



|       时间        |                        含义                         |
| :---------------: | :-------------------------------------------------: |
|   45 22 ***命令   |               在 22 点 45 分执行命令                |
|   0 17 ** 1命令   |            在每周一的 17 点 0 分执行命令            |
|  0 5 1，15**命令  |     在每月 1 日和 15 日的凌晨 5 点 0 分执行命令     |
|  40 4 ** 1-5命令  |       在每周一到周五的凌晨 4 点 40 分执行命令       |
|  */10 4 ***命令   |     在每天的凌晨 4 点，每隔 10 分钟执行一次命令     |
| 0 0 1，15 * 1命令 | 在每月 1 日和 15 日，每周一个 0 点 0 分都会执行命令 |





## anacron命令

anacron 会以 1 天、1周（7天）、一个月作为检测周期，判断是否有定时任务在关机之后没有执行。如果有这样的任务，那么 anacron 会在特定的时间重新执行这些定时任务。



命令：

```sh
 anacron [选项] [工作名]
```



| 选项 |                             功能                             |
| :--: | :----------------------------------------------------------: |
|  -f  |                强制执行相关工作，忽略时间戳。                |
|  -u  | 更新 /var/spool/anacron/cron.{daily，weekly，monthly} 文件中的时间戳为当前日期，但不执行任何工作。 |
|  -s  | 依据 /etc/anacrontab 文件中设定的延迟时间顺序执行工作，在前一个工作未完成前，不会开始下一个工作。 |
|  -n  | 立即执行 /etc/anacrontab 中所有的工作，忽略所有的延迟时间。  |
|  -q  |         禁止将信息输出到标准错误，常和 -d 选项合用。         |







## vmstat命令

vmstat命令，是 Virtual Meomory Statistics（虚拟内存统计）的缩写，可用来监控 CPU 使用、进程状态、内存使用、虚拟内存使用、硬盘输入/输出状态等信息。



命令：

```sh
vmstat [-a] [刷新延时 刷新次数]
```

或者：

```sh
vmstat [选项]
```





|       选项        |                             含义                             |
| :---------------: | :----------------------------------------------------------: |
|        -fs        | -f：显示从启动到目前为止，系统复制（fork）的程序数，此信息是从 /proc/stat 中的 processes 字段中取得的。 -s：将从启动到目前为止，由一些事件导致的内存变化情况列表说明。 |
|      -S 单位      |     令输出的数据显示单位，例如用 K/M 取代 bytes 的容量。     |
|        -d         |                列出硬盘有关读写总量的统计表。                |
| -p 分区设备文件名 |                 查看硬盘分区的读写情况。选项                 |





|  字段  |                             含义                             |
| :----: | :----------------------------------------------------------: |
| procs  | 进程信息字段：r：等待运行的进程数，数量越大，系统越繁忙。b：不可被唤醒的进程数量，数量越大，系统越繁忙。 |
| memory | 内存信息字段：swpd：虚拟内存的使用情况，单位为 KB。free：空闲的内存容量，单位为 KB。buff：缓冲的内存容量，单位为 KB。cache：缓存的内存容量，单位为 KB。 |
|  swap  | 交换分区信息字段：si：从磁盘中交换到内存中数据的数量，单位为 KB。so：从内存中交换到磁盘中数据的数量，单位为 KB。这两个数越大，表明数据需要经常在磁盘和内存之间进行交换，系统性能越差。 |
|   io   | 磁盘读/写信息字段：bi：从块设备中读入的数据的总量，单位是块。bo：写到块设备的数据的总量，单位是块。这两个数越大，代表系统的 I/O 越繁忙。 |
| system | 系统信息字段：in：每秒被中断的进程次数。cs：每秒进行的事件切换次数。这两个数越大，代表系统与接口设备的通信越繁忙。 |
|  cpu   | CPU信息字段：us：非内核进程消耗 CPU 运算时间的百分比。sy：内核进程消耗 CPU 运算时间的百分比。id：空闲 CPU 的百分比。wa：等待 I/O 所消耗的 CPU 百分比。st：被虚拟机所盗用的 CPU 百分比。 |



每隔1秒刷新一次，共刷新15次：

```sh
vmstat -a 1 15
```



```sh
mao@ubuntu:~/桌面$ vmstat -a 1 15
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b 交换 空闲 不活动 活动   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 1867624 1030148 452564    0    0    11     3   17   23  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  452  671  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  592  906  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  484  707  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  156  232  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  408  604  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  204  289  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  601  849  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  219  320  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  427  610  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  405  590  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  473  672  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  787 1069  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  517  717  0  0 100  0  0
 0  0      0 1867616 1030148 452564    0    0     0     0  564  799  0  0 100  0  0
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ vmstat -fs
         4943 forks
mao@ubuntu:~/桌面$ vmstat -fs
         4944 forks
mao@ubuntu:~/桌面$ vmstat -fs
         4945 forks
mao@ubuntu:~/桌面$ vmstat -fs
         4946 forks
mao@ubuntu:~/桌面$ vmstat -fs
         4948 forks
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ vmstat -S M
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b 交换 空闲 缓冲 缓存   si   so    bi    bo   in   cs us sy id wa st
 1  0      0   1823     51    965    0    0    10     3   16   22  0  0 100  0  0
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ vmstat -d
disk- ------------reads------------ ------------writes----------- -----IO------
      总用量 merged  扇区      ms 总用量 merged  扇区      ms    cur    sec
loop0     14      0      34       4      0      0       0       0      0      0
loop1     48      0     716      45      0      0       0       0      0      0
loop2     50      0     730      40      0      0       0       0      0      0
loop3     62      0    2134     127      0      0       0       0      0      0
loop4     57      0    2112     118      0      0       0       0      0      0
loop5     61      0    2166     189      0      0       0       0      0      0
loop6     54      0    2162     115      0      0       0       0      0      0
loop7     52      0    2168     127      0      0       0       0      0      0
sr0       11      0       5       2      0      0       0       0      0      0
sda    20102   6975 1744428   15268   8778  10551  489978   12812      0     19
loop8     43      0     696      82      0      0       0       0      0      0
loop9     43      0     694      65      0      0       0       0      0      0
loop10     45      0     700      51      0      0       0       0      0      0
loop11    521      0   34586     556      0      0       0       0      0      2
loop12     43      0     694      79      0      0       0       0      0      0
loop13     48      0     718      61      0      0       0       0      0      0
loop14     59      0    2186      77      0      0       0       0      0      0
loop15     12      0      36       1      0      0       0       0      0      0
mao@ubuntu:~/桌面$ 
```







## dmesg命令

显示开机信息



命令：

```sh
dmesg
```





```sh
mao@ubuntu:~/桌面$ dmesg | grep CPU
[    0.398178] smpboot: Allowing 128 CPUs, 112 hotplug CPUs
[    0.398266] setup_percpu: NR_CPUS:8192 nr_cpumask_bits:128 nr_cpu_ids:128 nr_node_ids:1
[    0.762294] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=128, Nodes=1
[    0.781546] rcu: 	RCU restricting CPUs from NR_CPUS=8192 to nr_cpu_ids=128.
[    0.787384] random: crng done (trusting CPU's manufacturer)
[    0.855304] smpboot: CPU0: AMD Ryzen 7 2700 Eight-Core Processor (family: 0x17, model: 0x8, stepping: 0x2)
[    0.884684] smp: Bringing up secondary CPUs ...
[    0.885688] .... node  #0, CPUs:          #1
[    0.046778] smpboot: CPU 2 Converting physical 0 to logical die 1
[    0.046778] smpboot: CPU 4 Converting physical 0 to logical die 2
[    0.046778] smpboot: CPU 6 Converting physical 0 to logical die 3
[    0.046778] smpboot: CPU 8 Converting physical 0 to logical die 4
[    0.046778] smpboot: CPU 10 Converting physical 0 to logical die 5
[    0.046778] smpboot: CPU 12 Converting physical 0 to logical die 6
[    0.046778] smpboot: CPU 14 Converting physical 0 to logical die 7
[    0.999089] smp: Brought up 1 node, 16 CPUs
[    7.619568] ledtrig-cpu: registered to indicate activity on CPUs
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ dmesg
[    0.000000] Linux version 5.11.0-38-generic (buildd@lgw01-amd64-041) (gcc (Ubuntu 9.3.0-17ubuntu1~20.04) 9.3.0, GNU ld (GNU Binutils for Ubuntu) 2.34) #42~20.04.1-Ubuntu SMP Tue Sep 28 20:41:07 UTC 2021 (Ubuntu 5.11.0-38.42~20.04.1-generic 5.11.22)
[    0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz-5.11.0-38-generic root=UUID=f016fec7-baa2-4d84-99bb-4b8bde2ff82c ro find_preseed=/preseed.cfg auto noprompt priority=critical locale=en_US quiet
[    0.000000] KERNEL supported cpus:
[    0.000000]   Intel GenuineIntel
[    0.000000]   AMD AuthenticAMD
[    0.000000]   Hygon HygonGenuine
[    0.000000]   Centaur CentaurHauls
[    0.000000]   zhaoxin   Shanghai  
[    0.000000] [Firmware Bug]: TSC doesn't count with P0 frequency!
[    0.000000] x86/fpu: Supporting XSAVE feature 0x001: 'x87 floating point registers'
[    0.000000] x86/fpu: Supporting XSAVE feature 0x002: 'SSE registers'
[    0.000000] x86/fpu: Supporting XSAVE feature 0x004: 'AVX registers'
[    0.000000] x86/fpu: xstate_offset[2]:  576, xstate_sizes[2]:  256
[    0.000000] x86/fpu: Enabled xstate features 0x7, context size is 832 bytes, using 'compacted' format.
[    0.000000] BIOS-provided physical RAM map:
[    0.000000] BIOS-e820: [mem 0x0000000000000000-0x000000000009e7ff] usable
[    0.000000] BIOS-e820: [mem 0x000000000009e800-0x000000000009ffff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000000dc000-0x00000000000fffff] reserved
[    0.000000] BIOS-e820: [mem 0x0000000000100000-0x00000000bfecffff] usable
[    0.000000] BIOS-e820: [mem 0x00000000bfed0000-0x00000000bfefefff] ACPI data
[    0.000000] BIOS-e820: [mem 0x00000000bfeff000-0x00000000bfefffff] ACPI NVS
[    0.000000] BIOS-e820: [mem 0x00000000bff00000-0x00000000bfffffff] usable
[    0.000000] BIOS-e820: [mem 0x00000000f0000000-0x00000000f7ffffff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000fec00000-0x00000000fec0ffff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000fee00000-0x00000000fee00fff] reserved
[    0.000000] BIOS-e820: [mem 0x00000000fffe0000-0x00000000ffffffff] reserved
[    0.000000] BIOS-e820: [mem 0x0000000100000000-0x000000013fffffff] usable
[    0.000000] NX (Execute Disable) protection: active
[    0.000000] SMBIOS 2.7 present.
[    0.000000] DMI: VMware, Inc. VMware Virtual Platform/440BX Desktop Reference Platform, BIOS 6.00 07/22/2020
[    0.000000] vmware: hypercall mode: 0x01
[    0.000000] Hypervisor detected: VMware
[    0.000000] vmware: TSC freq read from hypervisor : 3800.051 MHz
[    0.000000] vmware: Host bus clock speed read from hypervisor : 66000000 Hz
[    0.000000] vmware: using clock offset of 36772570590 ns
[    0.000049] tsc: Detected 3800.051 MHz processor
[    0.002925] e820: update [mem 0x00000000-0x00000fff] usable ==> reserved
[    0.003013] e820: remove [mem 0x000a0000-0x000fffff] usable
[    0.003071] last_pfn = 0x140000 max_arch_pfn = 0x400000000
[    0.003204] MTRR default type: uncachable
[    0.003223] MTRR fixed ranges enabled:
[    0.003242]   00000-9FFFF write-back
[    0.003261]   A0000-BFFFF uncachable
[    0.003280]   C0000-CFFFF write-protect
[    0.003300]   D0000-EFFFF uncachable
[    0.003324]   F0000-FFFFF write-protect
[    0.003343] MTRR variable ranges enabled:
[    0.003362]   0 base 000000000000 mask 1FE000000000 write-back
[    0.003382]   1 base 0000C0000000 mask 1FFFC0000000 uncachable
[    0.003402]   2 disabled
[    0.003421]   3 disabled
[    0.003439]   4 disabled
[    0.003458]   5 disabled
[    0.003476]   6 disabled
[    0.003495]   7 disabled
[    0.003528] x86/PAT: Configuration [0-7]: WB  WC  UC- UC  WB  WP  UC- WT  
[    0.003568] total RAM covered: 130048M
[    0.004154] Found optimal setting for mtrr clean up
[    0.004172]  gran_size: 64K 	chunk_size: 64K 	num_reg: 7  	lose cover RAM: 0G
[    0.004308] e820: update [mem 0xc0000000-0xffffffff] usable ==> reserved
[    0.004423] last_pfn = 0xc0000 max_arch_pfn = 0x400000000
[    0.008068] found SMP MP-table at [mem 0x000f6a70-0x000f6a7f]
[    0.013132] check: Scanning 1 areas for low memory corruption
[    0.017563] Using GB pages for direct mapping
[    0.021441] RAMDISK: [mem 0x31abf000-0x34d56fff]
...
```







## free命令

free 命令用来**显示系统内存状态**，包括系统物理内存、虚拟内存（swap 交换分区）、共享内存和系统缓存的使用情况



命令：

```sh
free [选项]
```



|    选项     |                             含义                             |
| :---------: | :----------------------------------------------------------: |
|     -b      |          以 Byte（字节）为单位，显示内存使用情况。           |
|     -k      | 以 KB 为单位，显示内存使用情况，此选项是 free 命令的默认选项。 |
|     -m      |               以 MB 为单位，显示内存使用情况。               |
|     -g      |               以 GB 为单位，显示内存使用情况。               |
|     -t      |       在输出的最终结果中，输出内存和 swap 分区的总量。       |
|     -o      |                   不显示系统缓冲区这一列。                   |
| -s 间隔秒数 |          根据指定的间隔时间，持续显示内存使用情况。          |



```sh
mao@ubuntu:~/桌面$ free --help

用法：
 free [选项]

选项：
 -b, --bytes         以字节显示输出
     --kilo          使用千字节显示输出
     --mega          使用兆字节显示输出
     --giga          使用吉字节显示输出
     --tera          使用太字节显示输出
     --peta          show output in petabytes
 -k, --kibi          show output in kibibytes
 -m, --mebi          show output in mebibytes
 -g, --gibi          show output in gibibytes
     --tebi          show output in tebibytes
     --pebi          show output in pebibytes
 -h, --human         显示人类可读的输出
     --si            使用 1000 的倍数而非使用 1024
 -l, --lohi          show detailed low and high memory statistics
 -t, --total         show total for RAM + swap
 -s N, --seconds N   repeat printing every N seconds
 -c N, --count N     repeat printing N times, then exit
 -w, --wide          宽版输出

     --help     显示此帮助信息并退出
 -V, --version  显示程序版本然后离开

欲了解更多详细信息，请参见 free(1)。
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ free
              总计         已用        空闲      共享    缓冲/缓存    可用
内存：     3995088     1081812     1870568        2500     1042708     2664640
交换：      703976           0      703976
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ free -m
              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901        1056        1826           2        1018        2601
交换：         687           0         687
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ free -h
              总计         已用        空闲      共享    缓冲/缓存    可用
内存：       3.8Gi       1.0Gi       1.8Gi       2.0Mi       1.0Gi       2.5Gi
交换：       687Mi          0B       687Mi
mao@ubuntu:~/桌面$ 
```





## w命令

查看服务器上目前已登录的用户信息

w 命令除了能知道目前已登陆的用户信息，还可以知道每个用户执行任务的情况



w 命令：

```sh
w [选项] [用户名]
```





| 选项 |                      含义                       |
| :--: | :---------------------------------------------: |
|  -h  |              不显示输出信息的标题               |
|  -l  |                  用长格式输出                   |
|  -s  | 用短格式输出，不显示登陆时间，JCPU 和 PCPU 时间 |
|  -V  |                  显示版本信息                   |



```sh
mao@ubuntu:~/桌面$ w --help

用法：
 w [选项]

选项：
 -h, --no-header     do not print header
 -u, --no-current    ignore current process username
 -s, --short         short format
 -f, --from          show remote hostname field
 -o, --old-style     旧格式输出
 -i, --ip-addr       display IP address instead of hostname (if possible)

     --help     显示此帮助信息并退出
 -V, --version  显示程序版本然后离开

欲了解更多详细信息，请参见 w(1)。
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ w
 05:12:42 up  1:57,  1 user,  load average: 0.00, 0.00, 0.00
USER     TTY      来自           LOGIN@   IDLE   JCPU   PCPU WHAT
mao      :0       :0               21:24   ?xdm?   4:02   0.02s /usr/lib/gdm3/gdm-x-session --run-script env GNOME_S
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ w -h
mao      :0       :0               21:24   ?xdm?   4:03   0.02s /usr/lib/gdm3/gdm-x-session --run-script env GNOME_S
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ w -s
 05:14:17 up  1:59,  1 user,  load average: 0.00, 0.00, 0.00
USER     TTY      来自            空闲等待
mao      :0       :0               ?xdm?  /usr/lib/gdm3/gdm-x-session --run-script env GNOME_SHELL_SESSION_MODE=ub
mao@ubuntu:~/桌面$ 
```





## who命令

查看服务器上目前已登录的用户信息



who 命令：

```sh
who [选项] [file]
```



|   选项   |                             含义                             |
| :------: | :----------------------------------------------------------: |
|    -a    |                列出所有信息，相当于所有选项。                |
|    -b    |                 列出系统最近启动的时间日期。                 |
|    -l    |                  列出所有可登陆的终端信息。                  |
|    -m    |  仅列出关于当前终端的信息，`who -m` 命令等同于 `who am i`。  |
|    -q    |            列出在本地系统上的用户和用户数的清单。            |
|    -r    |                   显示当前系统的运行级别。                   |
|    -s    |  仅显示名称、线路和时间字段信息，这是 who 命令的默认选项。   |
|    -u    | 显示当前每个用户的用户名、登陆终端、登陆时间、线路活动和进程标识。 |
| -T 或 -w | 显示 tty 终端的状态，“+”表示对任何人可写，“-”表示仅对 root 用户或所有者可写，“？”表示遇到线路故障。 |





```sh
mao@ubuntu:~/桌面$ who --help
用法：who [选项]... [ 文件 | 参数1 参数2 ]
显示当前已登录的用户信息。

  -a, --all		等于-b -d --login -p -r -t -T -u 选项的组合
  -b, --boot		上次系统启动时间
  -d, --dead		显示已死的进程
  -H, --heading	输出头部的标题列
      --ips         print ips instead of hostnames. with --lookup,
                    canonicalizes based on stored IP, if available,
                    rather than stored hostname
  -l，--login		显示系统登录进程
      --lookup		尝试通过 DNS 规范化主机名
  -m			只针对和标准输入有直接交互的主机和用户
  -p, --process	显示由 init 进程衍生的活动进程
  -q, --count		列出所有已登录用户的登录名与用户数量
  -r, --runlevel	显示当前的运行级别
  -s, --short		只显示名称、线路和时间(默认)
  -T, -w, --mesg	用+，- 或 ? 标注用户消息状态
  -u, --users		列出已登录的用户
      --message	等于-T
      --writable	等于-T
      --help		显示此帮助信息并退出
      --version		显示版本信息并退出

如果文件未被指定，则使用/var/run/utmp。/var/log/wtmp 是通用的相关文件。
如果给定了参数1和参数2，则假定同时启用了 -m 参数：常见的参数例子如
"am i" 或 "mom likes"。

完整文档请见：<https://www.gnu.org/software/coreutils/who>
或者在本地使用：info '(coreutils) who invocation'
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ who
mao      :0           2022-07-09 21:24 (:0)
mao@ubuntu:~/桌面$ who -s
mao      :0           2022-07-09 21:24 (:0)
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ who -a
           系统引导 2022-07-09 21:24
           运行级别 5 2022-07-09 21:24
mao      ? :0           2022-07-09 21:24   ?          1701 (:0)
mao@ubuntu:~/桌面$ 
```





## last 命令

last 命令可以查看当前和过去登陆系统用户的相关信息



命令：

```sh
last [选项]
```



|    选项     |                        含义                        |
| :---------: | :------------------------------------------------: |
|     -a      | 把从何处登陆系统的主机名或 IP 地址显示在最后一行。 |
|     -R      |         不显示登陆系统的主机名或 IP 地址。         |
|     -x      |  显示系统关机、重新开机以及执行等级的改变等信息。  |
| -n 显示列数 |              设置列出信息的显示列数。              |
|     -d      |          将显示的 IP 地址转换成主机名称。          |



```sh
mao@ubuntu:~/桌面$ last --help

用法：
 last [选项] [<用户名>...] [<tty>...]

显示上次登录用户的列表。

选项：
 -<数字>              显示行数
 -a, --hostlast       最后一列显示主机名
 -d, --dns            将 IP 号转换回主机名
 -F, --file <文件>    用指定文件代替 /var/log/wtmp
 -F, --fulltimes      打印完整的登录和注销时间和日期
 -i, --ip             以数字和点的形式显示 IP 号
 -n, --limit <数字>   要显示的行数
 -R, --nohostname     不显示主机名字段
 -s, --since <时间>   显示从指定时间起的行
 -t, --until <时间>   显示到指定时间为止的行
 -p, --present <时间> 显示在指定时间谁在场(present)
 -w, --fullnames      显示完整的用户名和域名
 -x, --system         显示系统关机项和运行级别更改
     --time-format <格式>    以指定<格式>显示时间戳：
                               notime|short|full|iso

 -h, --help           display this help
 -V, --version        display version

更多信息请参阅 last(1)。
mao@ubuntu:~/桌面$ 
```





```sh
mao@ubuntu:~/桌面$ last
mao      :0           :0               Sat Jul  9 21:24    gone - no logout
reboot   system boot  5.11.0-38-generi Sat Jul  9 21:24   still running
mao      :0           :0               Fri Jul  8 06:45 - crash (1+14:38)
reboot   system boot  5.11.0-38-generi Fri Jul  8 06:44   still running
mao      :0           :0               Thu Jul  7 07:00 - crash  (23:43)
mao      :0           :0               Thu Jul  7 06:08 - 07:00  (00:52)
reboot   system boot  5.11.0-38-generi Thu Jul  7 06:08   still running
mao      :0           :0               Wed Jul  6 22:10 - crash  (07:57)
reboot   system boot  5.11.0-38-generi Wed Jul  6 22:10   still running
mao      :0           :0               Wed Jul  6 04:44 - down   (01:51)
reboot   system boot  5.11.0-38-generi Wed Jul  6 04:43 - 06:35  (01:51)
mao      :0           :0               Tue Jul  5 04:00 - down   (02:39)
reboot   system boot  5.11.0-38-generi Tue Jul  5 03:59 - 06:40  (02:40)
mao      :0           :0               Mon Jul  4 21:46 - crash  (06:13)
reboot   system boot  5.11.0-38-generi Mon Jul  4 21:44 - 06:40  (08:56)
mao      :0           :0               Mon Jul  4 04:37 - crash  (17:06)
reboot   system boot  5.11.0-38-generi Mon Jul  4 04:37 - 06:40 (1+02:03)
mao      :0           :0               Sat Jul  2 21:46 - crash (1+06:51)
reboot   system boot  5.11.0-38-generi Sat Jul  2 21:46 - 06:40 (2+08:54)
mao      :0           :0               Sat Jul  2 04:23 - down   (02:43)
reboot   system boot  5.11.0-38-generi Sat Jul  2 04:22 - 07:07  (02:44)
mao      :0           :0               Thu Dec 30 04:32 - crash (183+22:50)
reboot   system boot  5.11.0-38-generi Thu Dec 30 04:30 - 07:07 (184+01:36)
mao      :0           :0               Wed Dec 29 03:11 - crash (1+01:19)
reboot   system boot  5.11.0-38-generi Wed Dec 29 03:10 - 07:07 (185+02:56)
mao      :0           :0               Wed Dec 29 02:38 - crash  (00:32)
reboot   system boot  5.11.0-38-generi Wed Dec 29 02:36 - 07:07 (185+03:30)
mao      :0           :0               Fri Nov 19 20:59 - crash (39+05:36)
reboot   system boot  5.11.0-38-generi Fri Nov 19 20:57 - 07:07 (224+09:09)
mao      :0           :0               Fri Nov 19 20:37 - crash  (00:19)
reboot   system boot  5.11.0-38-generi Fri Nov 19 20:37 - 07:07 (224+09:29)
mao      :0           :0               Fri Nov 19 20:20 - down   (00:16)
reboot   system boot  5.11.0-38-generi Fri Nov 19 20:20 - 20:37  (00:16)
mao      :0           :0               Fri Nov  5 05:21 - down   (00:20)
reboot   system boot  5.11.0-38-generi Fri Nov  5 05:20 - 05:42  (00:21)
mao      :0           :0               Thu Nov  4 22:21 - crash  (06:59)
reboot   system boot  5.11.0-38-generi Thu Nov  4 22:20 - 05:42  (07:21)
mao      :0           :0               Sat Oct 23 04:59 - crash (12+17:21)
reboot   system boot  5.11.0-38-generi Sat Oct 23 04:59 - 05:42 (13+00:43)
mao      :0           :0               Sat Oct 23 04:15 - down   (00:03)
reboot   system boot  5.11.0-38-generi Sat Oct 23 04:15 - 04:19  (00:04)
mao      :0           :0               Sat Oct 23 03:51 - down   (00:20)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:51 - 04:12  (00:20)
mao      :0           :0               Sat Oct 23 03:41 - down   (00:07)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:41 - 03:49  (00:07)
mao      :0           :0               Sat Oct 23 03:16 - down   (00:19)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:16 - 03:35  (00:19)
mao      :0           :0               Sat Oct 23 03:12 - down   (00:01)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:11 - 03:14  (00:02)
mao      :0           :0               Sat Oct 23 02:09 - crash  (01:02)
reboot   system boot  5.11.0-38-generi Sat Oct 23 02:08 - 03:14  (01:05)
mao      :0           :0               Fri Oct 22 23:22 - crash  (02:45)
reboot   system boot  5.11.0-38-generi Fri Oct 22 23:21 - 03:14  (03:53)
mao      :0           :0               Fri Oct 22 05:05 - crash  (18:15)
reboot   system boot  5.11.0-27-generi Fri Oct 22 05:05 - 03:14  (22:09)
mao      :0           :0               Fri Oct 15 05:21 - down   (00:03)
mao      :0           :0               Fri Oct 15 04:22 - 05:21  (00:59)
reboot   system boot  5.11.0-27-generi Fri Oct 15 04:20 - 05:24  (01:04)

wtmp begins Fri Oct 15 04:20:13 2021
mao@ubuntu:~/桌面$ 
```





## astlog 命令

lastlog 命令可以查看到每个系统用户最近一次登陆系统的时间



```sh
mao@ubuntu:~/桌面$ lastlog --help
用法：lastlog [选项]

选项：
  -b, --before DAYS             仅打印早于 DAYS 的最近登录记录
  -C, --clear                   清除一个用户的最近登录记录(须配合 -u 使用)
  -h, --help                    显示此帮助信息并退出
  -R, --root CHROOT_DIR         chroot 到的目录
  -S, --set                     设置最近登录记录为当前时间(须配合 -u 使用)
  -t, --time DAYS               仅打印晚于 DAYS 的最近登录记录
  -u, --user LOGIN              打印 LOGIN 用户的最近登录记录

mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ lastlog
用户名           端口     来自             最后登录时间
root                                       **从未登录过**
daemon                                     **从未登录过**
bin                                        **从未登录过**
sys                                        **从未登录过**
sync                                       **从未登录过**
games                                      **从未登录过**
man                                        **从未登录过**
lp                                         **从未登录过**
mail                                       **从未登录过**
news                                       **从未登录过**
uucp                                       **从未登录过**
proxy                                      **从未登录过**
www-data                                   **从未登录过**
backup                                     **从未登录过**
list                                       **从未登录过**
irc                                        **从未登录过**
gnats                                      **从未登录过**
nobody                                     **从未登录过**
systemd-network                            **从未登录过**
systemd-resolve                            **从未登录过**
systemd-timesync                           **从未登录过**
messagebus                                 **从未登录过**
syslog                                     **从未登录过**
_apt                                       **从未登录过**
tss                                        **从未登录过**
uuidd                                      **从未登录过**
tcpdump                                    **从未登录过**
avahi-autoipd                              **从未登录过**
usbmux                                     **从未登录过**
rtkit                                      **从未登录过**
dnsmasq                                    **从未登录过**
cups-pk-helper                             **从未登录过**
speech-dispatcher                           **从未登录过**
avahi                                      **从未登录过**
kernoops                                   **从未登录过**
saned                                      **从未登录过**
nm-openvpn                                 **从未登录过**
hplip                                      **从未登录过**
whoopsie                                   **从未登录过**
colord                                     **从未登录过**
geoclue                                    **从未登录过**
pulse                                      **从未登录过**
gnome-initial-setup                           **从未登录过**
gdm                                        **从未登录过**
sssd                                       **从未登录过**
mao                                        **从未登录过**
systemd-coredump                           **从未登录过**
mao@ubuntu:~/桌面$ 
```

















# 数据备份与恢复

## 备份策略

### 完全备份

完全备份是指把所有需要备份的数据全部备份。当然，完全备份可以备份整块硬盘、整个分区或某个具体的目录。对于 Linux 操作系统来说，完全备份指的就是将根目录下的所有文件进行备份。

* 优点：所有数据都进行了备份，系统中任何数据丢失都能恢复，且恢复效率较高。如果完全备份备份的是整块硬盘，那么甚至不需要数据恢复，只要把备份硬盘安装上，服务器就会恢复正常。
* 缺点：需要备份的数据量较大，备份时间较长，备份了很多无用数据，占用的空间较大





### 累计增量备份

累计增量备份是指先进行一次完全备份，服务器运行一段时间之后，比较当前系统和完全备份的备份数据之间的差异，只备份有差异的数据。服务器继续运行，再经过一段时间，进行第二次增量备份。在进行第二次增量备份时，当前系统和第一次增量备份的数据进行比较，也是只备份有差异的数据。第三次增量备份是和第二次增量备份的数据进行比较，以此类推。

假设我们在第一天进行一次完全备份。第二天增量备份时，只会备份第二天和第一天之间的差异数据，但是第二天的总备份数据是完全备份加第一次增量备份的数据。第三天增量备份时，只会备份第三天和第二天之间的差异数据，但是第三天的总备份数据是完全备份加第一次增量备份的数据，再加第二次增量备份的数据。当然，第四天增量备份时，只会备份第四天和第三天的差异数据，但是第四天的总备份数据是完全备份加第一次增量备份的数据，加第二次增量备份的数据，再加第三次增量备份的数据。

* 优点：每次备份需要备份的数据较少，耗时较短，占用的空间较小
* 缺点：数据恢复比较麻烦。当进行数据恢复时，就要先恢复完全备份的数据，再依次恢复第一次增量备份的数据、第二次增量备份的数据和第三次增量备份的数据，最终才能恢复所有的数据





### 差异增量备份

差异增量备份也要先进行一次完全备份，但是和累计增量备份不同的是，每次差异备份都备份和原始的完全备份不同的数据。也就是说，差异备份每次备份的参照物都是原始的完全备份，而不是上一次的差异备份。

假设我们在第一天也进行一次完全备份。第二天差异备份时，会备份第二天和第一天之间的差异数据，而第二天的备份数据是完全备份加第一次差异备份的数据。第三天进行差异备份时，仍和第一天的原始数据进行对比，把第二天和第三天所有的数据都备份在第二次差异备份中，第三天的备份数据是完全备份加第二次差异备份的数据。第四天进行差异备份时，仍和第一天的原始数据进行对比，把第二天、第三天和第四天所有的不同数据都备份到第三次差异备份中，第四天的备份数据是完全备份加第三次差异备份的数据。

* 优点：差异备份既不像完全备份一样把所有数据都进行备份，也不像增量备份在进行数据恢复时那么麻烦，只要先恢复完全备份的数据，再恢复差异备份的数据即可。
* 缺点：随着时间的增加，和完全备份相比，变动的数据越来越多，那么差异备份也可能会变得数据量庞大、备份速度缓慢、占用空间较大。





## dump命令

系统默认没有安装此命令，需要安装



CentOS：

```sh
yum -y install dump
```



ubuntu：

```sh
sudo apt install dump
```





```sh
mao@ubuntu:~/桌面$ sudo apt install dump
[sudo] mao 的密码： 
正在读取软件包列表... 完成
正在分析软件包的依赖关系树       
正在读取状态信息... 完成       
下列【新】软件包将被安装：
  dump
升级了 0 个软件包，新安装了 1 个软件包，要卸载 0 个软件包，有 61 个软件包未被升级。
需要下载 130 kB 的归档。
解压缩后会消耗 372 kB 的额外空间。
获取:1 http://cn.archive.ubuntu.com/ubuntu focal/universe amd64 dump amd64 0.4b46-6 [130 kB]
已下载 130 kB，耗时 6秒 (21.6 kB/s)                                            
正在选中未选择的软件包 dump。
(正在读取数据库 ... 系统当前共安装有 195480 个文件和目录。)
准备解压 .../dump_0.4b46-6_amd64.deb  ...
正在解压 dump (0.4b46-6) ...
正在设置 dump (0.4b46-6) ...
update-alternatives: 使用 /usr/sbin/rmt-dump 来在自动模式中提供 /usr/sbin/rmt (r
mt)
正在处理用于 man-db (2.9.1-1) 的触发器 ...
mao@ubuntu:~/桌面$ 
```





> dump 命令使用“备份级别”来实现增量备份，它支持 0～9 共 10 个备份级别。其中，0 级别指的就是完全备份，1～9 级别都是增量备份级别。

> 只有在备份整个分区或整块硬盘时，才能支持 1～9 的增量备份级别；如果只是备份某个文件或不是分区的目录，则只能使用 0 级别进行完全备份。



命令：

```sh
dump [选项] 备份之后的文件名 原文件或目录
```

选项：
-level：就是我们说的 0～9 共 10 个备份级别；
-f 文件名：指定备份之后的文件名；
-u：备份成功之后，把备份时间、备份级别以及实施备份的文件系统等信息，都记录在 /etc/dumpdates 文件中；
-v：显示备份过程中更多的输出信息；
-j：调用 bzlib 库压缩备份文件，其实就是把备份文件压缩为 .bz2 格式，默认压缩等级是 2；
-W：显示允许被 dump 的分区的备份等级及备份时间；





```sh
sudo dump -0j -f backup.bz2 a.c
```



```sh
mao@ubuntu:~/桌面$ sudo dump -0j -f backup.bz2 a.c
  DUMP: Date of this level 0 dump: Mon Jul 11 22:16:03 2022
  DUMP: Dumping /dev/sda5 (/ (dir home/mao/桌面/a.c)) to backup.bz2
  DUMP: Label: none
  DUMP: Writing 10 Kilobyte records
  DUMP: Compressing output at transformation level 2 (bzlib)
  DUMP: mapping (Pass I) [regular files]
  DUMP: mapping (Pass II) [directories]
  DUMP: estimated 272 blocks.
  DUMP: Volume 1 started with block 1 at: Mon Jul 11 22:16:03 2022
  DUMP: dumping (Pass III) [directories]
  DUMP: dumping (Pass IV) [regular files]
  DUMP: Closing backup.bz2
  DUMP: Volume 1 completed at: Mon Jul 11 22:16:03 2022
  DUMP: 260 blocks (0.25MB) on 1 volume(s)
  DUMP: finished in less than a second
  DUMP: Date of this level 0 dump: Mon Jul 11 22:16:03 2022
  DUMP: Date this dump completed:  Mon Jul 11 22:16:03 2022
  DUMP: Average transfer rate: 0 kB/s
  DUMP: Wrote 260kB uncompressed, 16kB compressed, 16.250:1
  DUMP: DUMP IS DONE
mao@ubuntu:~/桌面$ 
```



```sh
sudo dump -0j -f backup2.bz2 /home/mao/
```



```sh
mao@ubuntu:~/桌面$ sudo dump -0j -f backup2.bz2 /home/mao/
  DUMP: Date of this level 0 dump: Mon Jul 11 22:19:06 2022
  DUMP: Dumping /dev/sda5 (/ (dir home/mao)) to backup2.bz2
  DUMP: Label: none
  DUMP: Writing 10 Kilobyte records
  DUMP: Compressing output at transformation level 2 (bzlib)
  DUMP: mapping (Pass I) [regular files]
  DUMP: mapping (Pass II) [directories]
  DUMP: estimated 65690 blocks.
  DUMP: Volume 1 started with block 1 at: Mon Jul 11 22:19:06 2022
  DUMP: dumping (Pass III) [directories]
  DUMP: dumping (Pass IV) [regular files]
  DUMP: Closing backup2.bz2
  DUMP: Volume 1 completed at: Mon Jul 11 22:19:10 2022
  DUMP: Volume 1 took 0:00:04
  DUMP: Volume 1 transfer rate: 5854 kB/s
  DUMP: Volume 1 65420kB uncompressed, 23417kB compressed, 2.794:1
  DUMP: 65420 blocks (63.89MB) on 1 volume(s)
  DUMP: finished in 4 seconds, throughput 16355 kBytes/sec
  DUMP: Date of this level 0 dump: Mon Jul 11 22:19:06 2022
  DUMP: Date this dump completed:  Mon Jul 11 22:19:10 2022
  DUMP: Average transfer rate: 5854 kB/s
  DUMP: Wrote 65420kB uncompressed, 23417kB compressed, 2.794:1
  DUMP: DUMP IS DONE
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ ls -l
总用量 23644
-rw-rw-r-- 1 mao  mao         4 12月 29  2021 1.txt
-rw------- 1 mao  mao      8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao  mao     16984 12月 29  2021 a.out
-rw-r--r-- 1 root root 23979218 7月  11 22:19 backup2.bz2
-rw-r--r-- 1 root root    16765 7月  11 22:17 backup.bz2
-rw------- 1 mao  mao      9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao  mao      2956 11月  4  2021 filea.c
-rw------- 1 mao  mao        96 10月 23  2021 func1.c
-rw------- 1 mao  mao        98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao  mao      2324 12月 29  2021 linux_file.c
-rw------- 1 mao  mao       242 10月 23  2021 main.c
-rw------- 1 mao  mao       206 10月 23  2021 main.h
-rw------- 1 mao  mao        20 7月   9 21:52 nohup.out
-rw-rw-r-- 1 mao  mao    123464 7月  10 04:50 out.txt
-rw-rw-r-- 1 mao  mao         4 7月   5 06:18 test.txt
mao@ubuntu:~/桌面$ 
```







## restore命令

restore 命令是 dump 命令的配套命令，dump 命令是用来备份分区和数据的，而 restore 命令是用来恢复数据的。



命令：

```sh
restore [模式选项] [-f]
```



- -C：比较备份数据和实际数据的变化。如果实际数据中的现有数据发生了变化，那么这个选项能够检测到这个变化。但是如果实际数据中新增了数据，那么这个选项是不能检测到变化的。
- -i：进入交互模式，手工选择需要恢复的文件；
- -t：查看模式，用于查看备份文件中拥有哪些数据；
- -r：还原模式，用于数据还原；
- -f ：用于指定备份文件的文件名



```sh
restore -t -f backup.bz2
```

```sh
mao@ubuntu:~/桌面$ restore -t -f backup.bz2
Dump tape is compressed.
Dump   date: Mon Jul 11 22:17:18 2022
Dumped from: the epoch
Level 0 dump of / (dir home/mao/桌面/a.c) on ubuntu:/dev/sda5
Label: none
         2	.
    655361	./home
    688519	./home/mao
    271582	./home/mao/桌面
    266055	./home/mao/桌面/a.c
mao@ubuntu:~/桌面$ 
```



```sh
restore -t -f backup2.bz2
```

```sh
Dump   date: Mon Jul 11 22:19:06 2022
Dumped from: the epoch
Level 0 dump of / (dir home/mao) on ubuntu:/dev/sda5
Label: none
         2	.
    655361	./home
    688519	./home/mao
    664557	./home/mao/.bashrc
    682460	./home/mao/.profile
    682461	./home/mao/.bash_logout
    411074	./home/mao/.config
    411082	./home/mao/.config/pulse
    411088	./home/mao/.config/pulse/2cd3a15613614cc6b0f466b652abd32b-device-volumes.tdb
    411089	./home/mao/.config/pulse/2cd3a15613614cc6b0f466b652abd32b-stream-volumes.tdb
    411090	./home/mao/.config/pulse/2cd3a15613614cc6b0f466b652abd32b-card-database.tdb
    411091	./home/mao/.config/pulse/cookie
    411146	./home/mao/.config/pulse/2cd3a15613614cc6b0f466b652abd32b-default-sink
    411147	./home/mao/.config/pulse/2cd3a15613614cc6b0f466b652abd32b-default-source
    411096	./home/mao/.config/goa-1.0
    411130	./home/mao/.config/dconf
    411132	./home/mao/.config/dconf/user
    411144	./home/mao/.config/user-dirs.locale
    404494	./home/mao/.config/user-dirs.dirs
    411148	./home/mao/.config/ibus
    411149	./home/mao/.config/ibus/bus
    393703	./home/mao/.config/ibus/bus/2cd3a15613614cc6b0f466b652abd32b-unix-0
    411182	./home/mao/.config/evolution
    411183	./home/mao/.config/evolution/sources
    411186	./home/mao/.config/evolution/sources/system-proxy.source
    411200	./home/mao/.config/gtk-3.0
    425526	./home/mao/.config/gtk-3.0/bookmarks
    411210	./home/mao/.config/nautilus
    411072	./home/mao/.config/update-notifier
    434253	./home/mao/.config/gnome-session
    434254	./home/mao/.config/gnome-session/saved-session
    434266	./home/mao/.config/enchant
    395809	./home/mao/.config/enchant/en_AU.dic
    395838	./home/mao/.config/enchant/en_AU.exc
    411233	./home/mao/.config/gnome-initial-setup-done
    434267	./home/mao/.config/gedit
    395865	./home/mao/.config/gedit/accels
    411245	./home/mao/.config/gnome-control-center
    419144	./home/mao/.config/gnome-control-center/backgrounds
    419145	./home/mao/.config/gnome-control-center/backgrounds/last-edited.xml
    411185	./home/mao/.config/procps
    411083	./home/mao/.local
    411084	./home/mao/.local/share
    411085	./home/mao/.local/share/tracker
    411111	./home/mao/.local/share/tracker/data
    411100	./home/mao/.local/share/tracker/data/.meta.isrunning
    411118	./home/mao/.local/share/tracker/data/tracker-store.ontology.journal
    411122	./home/mao/.local/share/tracker/data/tracker-store.journal
    411119	./home/mao/.local/share/xorg
    411114	./home/mao/.local/share/xorg/Xorg.0.log
    411143	./home/mao/.local/share/xorg/Xorg.0.log.old
    411129	./home/mao/.local/share/keyrings
    411131	./home/mao/.local/share/keyrings/login.keyring
    411133	./home/mao/.local/share/keyrings/user.keystore
    411145	./home/mao/.local/share/gnome-shell
    411214	./home/mao/.local/share/gnome-shell/gnome-overrides-migrated
    427127	./home/mao/.local/share/gnome-shell/application_state
    411243	./home/mao/.local/share/gnome-shell/notifications
...
...
...
    684378	./home/mao/.viminfo
    684433	./home/mao/.selected_editor
    655995	./home/mao/.pam_environment
    271582	./home/mao/桌面
    285751	./home/mao/桌面/.swp
    285752	./home/mao/桌面/.swo
    285753	./home/mao/桌面/.swn
    285754	./home/mao/桌面/.swm
    285755	./home/mao/桌面/.swl
    285756	./home/mao/桌面/.myfile.txt.swp
    285757	./home/mao/桌面/.file.txt.swp
    272001	./home/mao/桌面/.swk
    266344	./home/mao/桌面/.file.txt.swo
    267996	./home/mao/桌面/a.out
    272170	./home/mao/桌面/.file.c.swp
    276907	./home/mao/桌面/main.h
    276917	./home/mao/桌面/main.c
    277010	./home/mao/桌面/func2.c
    277095	./home/mao/桌面/func1.c
    266106	./home/mao/桌面/filea.c
    266130	./home/mao/桌面/linux_file.c
    266145	./home/mao/桌面/1.txt
    266074	./home/mao/桌面/.swj
    266055	./home/mao/桌面/a.c
    266096	./home/mao/桌面/.hello.o.cmd
    266107	./home/mao/桌面/.hello.mod.cmd
    266036	./home/mao/桌面/test.txt
    266112	./home/mao/桌面/.modules.order.cmd
    266118	./home/mao/桌面/.a.c.swp
    267994	./home/mao/桌面/out.txt
    266115	./home/mao/桌面/.Module.symvers.cmd
    267992	./home/mao/桌面/English_early_education_machine_input.c
    266119	./home/mao/桌面/nohup.out
    266116	./home/mao/桌面/.hello.mod.o.cmd
    266127	./home/mao/桌面/.hello.ko.cmd
    266120	./home/mao/桌面/backup.bz2
    271585	./home/mao/下载
    271586	./home/mao/模板
    271587	./home/mao/公共的
    271649	./home/mao/文档
    271653	./home/mao/音乐
    271813	./home/mao/图片
    271814	./home/mao/视频
```





```sh
restore -r -f ./../backup.bz2
```

```sh
mao@ubuntu:~/桌面$ mkdir test
mao@ubuntu:~/桌面$ cd test
mao@ubuntu:~/桌面/test$ ls-l
ls-l：未找到命令
mao@ubuntu:~/桌面/test$ ls -l
总用量 0
mao@ubuntu:~/桌面/test$ restore -r -f ./../backup.bz2
Dump tape is compressed.
./lost+found: (inode 11) not found on tape
./boot: (inode 131073) not found on tape
./swapfile: (inode 12) not found on tape
./etc: (inode 786433) not found on tape
./media: (inode 262145) not found on tape
./var: (inode 524289) not found on tape
./bin: (inode 13) not found on tape
./dev: (inode 393217) not found on tape
./home/mao/.bashrc: (inode 664557) not found on tape
./home/mao/.profile: (inode 682460) not found on tape
./home/mao/.bash_logout: (inode 682461) not found on tape
./home/mao/.config: (inode 411074) not found on tape
./home/mao/.local: (inode 411083) not found on tape
./home/mao/.cache: (inode 411092) not found on tape
./home/mao/.gnupg: (inode 411125) not found on tape
./home/mao/.bash_history: (inode 656580) not found on tape
./home/mao/.sudo_as_admin_successful: (inode 657925) not found on tape
./home/mao/.mozilla: (inode 665730) not found on tape
./home/mao/.viminfo: (inode 684378) not found on tape
./home/mao/.selected_editor: (inode 684433) not found on tape
./home/mao/.pam_environment: (inode 655995) not found on tape
./home/mao/桌面/.swp: (inode 285751) not found on tape
./home/mao/桌面/.swo: (inode 285752) not found on tape
./home/mao/桌面/.swn: (inode 285753) not found on tape
./home/mao/桌面/.swm: (inode 285754) not found on tape
./home/mao/桌面/.swl: (inode 285755) not found on tape
./home/mao/桌面/.myfile.txt.swp: (inode 285756) not found on tape
./home/mao/桌面/.file.txt.swp: (inode 285757) not found on tape
./home/mao/桌面/.swk: (inode 272001) not found on tape
./home/mao/桌面/.file.txt.swo: (inode 266344) not found on tape
./home/mao/桌面/a.out: (inode 267996) not found on tape
./home/mao/桌面/.file.c.swp: (inode 272170) not found on tape
./home/mao/桌面/main.h: (inode 276907) not found on tape
./home/mao/桌面/main.c: (inode 276917) not found on tape
./home/mao/桌面/func2.c: (inode 277010) not found on tape
./home/mao/桌面/func1.c: (inode 277095) not found on tape
./home/mao/桌面/filea.c: (inode 266106) not found on tape
./home/mao/桌面/linux_file.c: (inode 266130) not found on tape
./home/mao/桌面/1.txt: (inode 266145) not found on tape
./home/mao/桌面/.swj: (inode 266074) not found on tape
./home/mao/桌面/.hello.o.cmd: (inode 266096) not found on tape
./home/mao/桌面/.hello.mod.cmd: (inode 266107) not found on tape
./home/mao/桌面/test.txt: (inode 266036) not found on tape
./home/mao/桌面/.modules.order.cmd: (inode 266112) not found on tape
./home/mao/桌面/.a.c.swp: (inode 266118) not found on tape
./home/mao/桌面/out.txt: (inode 267994) not found on tape
./home/mao/桌面/.Module.symvers.cmd: (inode 266115) not found on tape
./home/mao/桌面/English_early_education_machine_input.c: (inode 267992) not found on tape
./home/mao/桌面/nohup.out: (inode 266119) not found on tape
./home/mao/桌面/.hello.mod.o.cmd: (inode 266116) not found on tape
./home/mao/桌面/.hello.ko.cmd: (inode 266127) not found on tape
./home/mao/桌面/backup.bz2: (inode 266120) not found on tape
./home/mao/下载: (inode 271585) not found on tape
./home/mao/模板: (inode 271586) not found on tape
./home/mao/公共的: (inode 271587) not found on tape
./home/mao/文档: (inode 271649) not found on tape
./home/mao/音乐: (inode 271653) not found on tape
./home/mao/图片: (inode 271813) not found on tape
./home/mao/视频: (inode 271814) not found on tape
./lib: (inode 14) not found on tape
./lib32: (inode 15) not found on tape
./lib64: (inode 16) not found on tape
./libx32: (inode 17) not found on tape
./mnt: (inode 655362) not found on tape
./opt: (inode 393218) not found on tape
./proc: (inode 786435) not found on tape
./root: (inode 786436) not found on tape
./run: (inode 131075) not found on tape
./sbin: (inode 18) not found on tape
./snap: (inode 262148) not found on tape
./srv: (inode 393219) not found on tape
./sys: (inode 655363) not found on tape
./tmp: (inode 262149) not found on tape
./usr: (inode 655364) not found on tape
./cdrom: (inode 802079) not found on tape
restore: chown: Operation not permitted
restore: chown: Operation not permitted
mao@ubuntu:~/桌面/test$ ls -l
总用量 1504
drwxr-xr-x 3 mao mao    4096 10月 15  2021 home
-rw------- 1 mao mao 1533984 7月  11 22:32 restoresymtable
mao@ubuntu:~/桌面/test$ cd home/mao
mao@ubuntu:~/桌面/test/home/mao$ ls -l
总用量 4
drwxr-xr-x 2 mao mao 4096 7月  11 22:16 桌面
mao@ubuntu:~/桌面/test/home/mao$ cd 桌面
mao@ubuntu:~/桌面/test/home/mao/桌面$ ls -l
总用量 12
-rw------- 1 mao mao 8859 12月 30  2021 a.c
mao@ubuntu:~/桌面/test/home/mao/桌面$ 
```







## dd命令

dd 命令主要用来进行数据备份，并且可以在备份的过程中进行格式转换。其实 dd 命令可以把源数据复制成目标数据，而且不管源数据是文件、分区、磁盘还是光盘，都可以进行数据备份。



命令：

```sh
dd if="输入文件" of="输出文件" bs="数据块" count="数量"
```



参数：

1. if：定义输入数据的文件，也可以是输入设备；
2. of：定义输出数据的文件，也可以是输出设备；
3. bs：指定数据块的大小，也就是定义一次性读取或写入多少字节。模式数据块大小是 512 字节；
4. count：指定 bs 的数量；
5. conv=标志：依据标志转换文件。标志有以下这些：
   - ascii：由 EBCDIC 码转换至 ASCII 码；
   - ebcdic：由 ASCII 码转换至 EBCDIC 码；
   - ibm：由 ASCII 码转换至替换的 EBCDIC 码；
   - block：将结束字符块里的换行替换成等长的空格；
   - unblock：将 cbs 大小的块中尾部的空格替换为一个换行符；
   - lcase：将大写字符转换为小写；
   - notrunc：不截断输出文件；
   - ucase：将小写字符转换为大写；
   - swab：交换每一对输入数据字节；
   - noerror：读取数据发生错误后仍然继续；
   - sync：将每个输入数据块以 NUL 字符填满至 ibs 的大小；当配合 block 或 unblock 时，会以空格代替 NUL 字符填充；



```sh
mao@ubuntu:~/桌面$ dd --help
用法：dd [操作数] ...
　或：dd 选项
复制文件，依照指定操作数转换并格式化。

  bs=字节数      一次读写的比特数（默认：512）；
                 会覆盖 ibs 和 obs 选项
  cbs=字节数     一次转换的字节数
  conv=CONVS     依照每个逗号分割的符号列表转换文件
  count=块数     只将复制指定数量的输入块
  ibs=字节数     一次读取的字节数（默认：512)
  if=文件         从指定文件而非标准输入来进行读取
  iflag=标志      按照以逗号分隔的符号列表指定的方式读取
  obs=字节数      一次写入指定字节数（默认：512）
  of=文件         写入到指定文件而非标准输出
  oflag=标志      按照以逗号分隔的符号列表指定的方式写入
  seek=块数       在输出开始处跳过指定的 obs 大小的块数
  skip=块数       在输入开始处跳过指定的 ibs 大小的块数
  status=等级     要输出到标准错误的信息等级；
                  'none' 将仅输出错误信息，
                  'noxfer' 将不输出最终传输统计信息，
                  'progress' 将显示周期性的传输统计信息

N and BYTES may be followed by the following multiplicative suffixes:
c =1, w =2, b =512, kB =1000, K =1024, MB =1000*1000, M =1024*1024, xM =M,
GB =1000*1000*1000, G =1024*1024*1024, and so on for T, P, E, Z, Y.

Each CONV symbol may be:

  ascii     from EBCDIC to ASCII
  ebcdic    from ASCII to EBCDIC
  ibm       from ASCII to alternate EBCDIC
  block     pad newline-terminated records with spaces to cbs-size
  unblock   replace trailing spaces in cbs-size records with newline
  lcase     change upper case to lower case
  ucase     change lower case to upper case
  sparse    try to seek rather than write the output for NUL input blocks
  swab      swap every pair of input bytes
  sync      pad every input block with NULs to ibs-size; when used
            with block or unblock, pad with spaces rather than NULs
  excl      如果输出文件已存在则认为操作失败
  nocreat   不要创建输出文件
  notrunc   不要截断输出文件
  noerror   读取数据发生错误后仍然继续
  fdatasync  结束前将输出文件数据物理上写入磁盘
  fsync     与上者类似，但也将元数据一同写入

FLAG 符号可以是：

  append	追加模式(仅对输出有意义；隐含了conv=notrunc)
  direct    使用直接I/O 存取模式
  directory  除非是目录，否则操作失败
  dsync     使用同步 I/O 存取模式
  sync      与上者类似，但同时也对元数据生效
  fullblock	为输入积累完整块(仅iflag)
  nonblock	使用无阻塞I/O 存取模式
  noatime   不更新访问时间
  nocache   请求不使用缓存。参见 oflag=sync
  noctty	不根据文件指派控制终端
  nofollow  不跟随链接文件
  count_bytes  把 'count=N' 看作字节计数（仅 iflag）
  skip_bytes  把 'skip=N' 看作字节计数（仅 iflag）
  seek_bytes  把 'seek=N' 看作字节计数（仅 oflag）

向正在运行的 'dd' 进程发送 USR1 信号可以令其向标准错误输出 I/O
统计数据并继续进行复制。

选项有：

      --help		显示此帮助信息并退出
      --version		显示版本信息并退出

完整文档请见：<https://www.gnu.org/software/coreutils/dd>
或者在本地使用：info '(coreutils) dd invocation'
mao@ubuntu:~/桌面$ 
```





备份一个文件：

```sh
dd if=./a.c of=./backup.bak
```

```sh
mao@ubuntu:~/桌面$ dd if=./a.c of=./backup.bak
记录了17+1 的读入
记录了17+1 的写出
8859字节（8.9 kB，8.7 KiB）已复制，0.000606253 s，14.6 MB/s
mao@ubuntu:~/桌面$ ls -l
总用量 168
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao  8859 7月  11 22:45 backup.bak
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao 78631 7月  11 22:28 out.txt
-rw-rw-r-- 1 mao mao     4 7月   5 06:18 test.txt
mao@ubuntu:~/桌面$ 
```



备份分区为一个备份文件：

```sh
dd if=/dev/sda5 of=/tmp/sda5.bak
```



整盘备份：

```sh
dd if=/dev/sda of=/dev/sdb
```







## rsync命令

rsync 可以理解为 remote sync（远程同步），但它不仅可以远程同步数据（类似于 scp 命令），还可以本地同步数据（类似于 cp 命令）。不同于 cp 或 scp 的一点是，使用 rsync 命令备份数据时，不会直接覆盖以前的数据（如果数据已经存在），而是先判断已经存在的数据和新数据的差异，只有数据不同时才会把不相同的部分覆盖。



命令：

```sh
[root@localhost ~]# rsync [OPTION] SRC DEST
[root@localhost ~]# rsync [OPTION] SRC [USER@]HOST:DEST
[root@localhost ~]# rsync [OPTION] [USER@]HOST:SRC DEST
[root@localhost ~]# rsync [OPTION] [USER@]HOST::SRC DEST
[root@localhost ~]# rsync [OPTION] SRC [USER@]HOST::DEST
```



使用 rsync 在远程传输数据（备份数据）前，是需要进行登陆认证的，这个过程需要借助 ssh 协议或者 rsync 协议才能完成。在 rsync 命令中，如果使用单个冒号（:），则默认使用 ssh 协议；反之，如果使用两个冒号（::），则使用 rsync 协议。

ssh 协议和 rsync 协议的区别在于，rsync 协议在使用时需要额外配置，增加了工作量，但优势是更加安全；反之，ssh 协议使用方便，无需进行配置，但有泄漏服务器密码的风险。

- SRC：用来表示要备份的目标数据所在的位置（路径）；
- DEST：用于表示将数据备份到什么位置；
- USER@：当做远程同步操作时，需指明系统登录的用户名，如果不显示指定，默认为以 root 身份登录系统并完成同步操作。



|    OPTION选项     |                             功能                             |
| :---------------: | :----------------------------------------------------------: |
|        -a         | 这是归档模式，表示以递归方式传输文件，并保持所有属性，它等同于-r、-l、-p、-t、-g、-o、-D 选项。-a 选项后面可以跟一个 --no-OPTION，表示关闭 -r、-l、-p、-t、-g、-o、-D 中的某一个，比如-a --no-l 等同于 -r、-p、-t、-g、-o、-D 选项。 |
|        -r         | 表示以递归模式处理子目录，它主要是针对目录来说的，如果单独传一个文件不需要加 -r 选项，但是传输目录时必须加。 |
|        -v         |         表示打印一些信息，比如文件列表、文件数量等。         |
|        -l         |                       表示保留软连接。                       |
|        -L         | 表示像对待常规文件一样处理软连接。如果是 SRC 中有软连接文件，则加上该选项后，将会把软连接指向的目标文件复制到 DEST。 |
|        -p         |                      表示保持文件权限。                      |
|        -o         |                    表示保持文件属主信息。                    |
|        -g         |                    表示保持文件属组信息。                    |
|        -D         |                    表示保持设备文件信息。                    |
|        -t         |                    表示保持文件时间信息。                    |
|     --delete      |              表示删除 DEST 中 SRC 没有的文件。               |
| --exclude=PATTERN | 表示指定排除不需要传输的文件，等号后面跟文件名，可以是通配符模式（如 *.txt）。 |
|    --progress     | 表示在同步的过程中可以看到同步的过程状态，比如统计要同步的文件数量、 同步的文件传输速度等。 |
|        -u         |      表示把 DEST 中比 SRC 还新的文件排除掉，不会覆盖。       |
|        -z         |              加上该选项，将会在传输过程中压缩。              |





```sh
mao@ubuntu:~/桌面$ rsync --help
rsync  version 3.1.3  protocol version 31
Copyright (C) 1996-2018 by Andrew Tridgell, Wayne Davison, and others.
Web site: http://rsync.samba.org/
Capabilities:
    64-bit files, 64-bit inums, 64-bit timestamps, 64-bit long ints,
    socketpairs, hardlinks, symlinks, IPv6, batchfiles, inplace,
    append, ACLs, xattrs, iconv, symtimes, prealloc

rsync comes with ABSOLUTELY NO WARRANTY.  This is free software, and you
are welcome to redistribute it under certain conditions.  See the GNU
General Public Licence for details.

rsync is a file transfer program capable of efficient remote update
via a fast differencing algorithm.

Usage: rsync [OPTION]... SRC [SRC]... DEST
  or   rsync [OPTION]... SRC [SRC]... [USER@]HOST:DEST
  or   rsync [OPTION]... SRC [SRC]... [USER@]HOST::DEST
  or   rsync [OPTION]... SRC [SRC]... rsync://[USER@]HOST[:PORT]/DEST
  or   rsync [OPTION]... [USER@]HOST:SRC [DEST]
  or   rsync [OPTION]... [USER@]HOST::SRC [DEST]
  or   rsync [OPTION]... rsync://[USER@]HOST[:PORT]/SRC [DEST]
The ':' usages connect via remote shell, while '::' & 'rsync://' usages connect
to an rsync daemon, and require SRC or DEST to start with a module name.

Options
 -v, --verbose               increase verbosity
     --info=FLAGS            fine-grained informational verbosity
     --debug=FLAGS           fine-grained debug verbosity
     --msgs2stderr           special output handling for debugging
 -q, --quiet                 suppress non-error messages
     --no-motd               suppress daemon-mode MOTD (see manpage caveat)
 -c, --checksum              skip based on checksum, not mod-time & size
 -a, --archive               archive mode; equals -rlptgoD (no -H,-A,-X)
     --no-OPTION             turn off an implied OPTION (e.g. --no-D)
 -r, --recursive             recurse into directories
 -R, --relative              use relative path names
     --no-implied-dirs       don't send implied dirs with --relative
 -b, --backup                make backups (see --suffix & --backup-dir)
     --backup-dir=DIR        make backups into hierarchy based in DIR
     --suffix=SUFFIX         set backup suffix (default ~ w/o --backup-dir)
 -u, --update                skip files that are newer on the receiver
     --inplace               update destination files in-place (SEE MAN PAGE)
     --append                append data onto shorter files
     --append-verify         like --append, but with old data in file checksum
 -d, --dirs                  transfer directories without recursing
 -l, --links                 copy symlinks as symlinks
 -L, --copy-links            transform symlink into referent file/dir
     --copy-unsafe-links     only "unsafe" symlinks are transformed
     --safe-links            ignore symlinks that point outside the source tree
     --munge-links           munge symlinks to make them safer (but unusable)
 -k, --copy-dirlinks         transform symlink to a dir into referent dir
 -K, --keep-dirlinks         treat symlinked dir on receiver as dir
 -H, --hard-links            preserve hard links
 -p, --perms                 preserve permissions
 -E, --executability         preserve the file's executability
     --chmod=CHMOD           affect file and/or directory permissions
 -A, --acls                  preserve ACLs (implies --perms)
 -X, --xattrs                preserve extended attributes
 -o, --owner                 preserve owner (super-user only)
 -g, --group                 preserve group
     --devices               preserve device files (super-user only)
     --copy-devices          copy device contents as regular file
     --specials              preserve special files
 -D                          same as --devices --specials
 -t, --times                 preserve modification times
 -O, --omit-dir-times        omit directories from --times
 -J, --omit-link-times       omit symlinks from --times
     --super                 receiver attempts super-user activities
     --fake-super            store/recover privileged attrs using xattrs
 -S, --sparse                turn sequences of nulls into sparse blocks
     --preallocate           allocate dest files before writing them
 -n, --dry-run               perform a trial run with no changes made
 -W, --whole-file            copy files whole (without delta-xfer algorithm)
     --checksum-choice=STR   choose the checksum algorithms
 -x, --one-file-system       don't cross filesystem boundaries
 -B, --block-size=SIZE       force a fixed checksum block-size
 -e, --rsh=COMMAND           specify the remote shell to use
     --rsync-path=PROGRAM    specify the rsync to run on the remote machine
     --existing              skip creating new files on receiver
     --ignore-existing       skip updating files that already exist on receiver
     --remove-source-files   sender removes synchronized files (non-dirs)
     --del                   an alias for --delete-during
     --delete                delete extraneous files from destination dirs
     --delete-before         receiver deletes before transfer, not during
     --delete-during         receiver deletes during the transfer
     --delete-delay          find deletions during, delete after
     --delete-after          receiver deletes after transfer, not during
     --delete-excluded       also delete excluded files from destination dirs
     --ignore-missing-args   ignore missing source args without error
     --delete-missing-args   delete missing source args from destination
     --ignore-errors         delete even if there are I/O errors
     --force                 force deletion of directories even if not empty
     --max-delete=NUM        don't delete more than NUM files
     --max-size=SIZE         don't transfer any file larger than SIZE
     --min-size=SIZE         don't transfer any file smaller than SIZE
     --partial               keep partially transferred files
     --partial-dir=DIR       put a partially transferred file into DIR
     --delay-updates         put all updated files into place at transfer's end
 -m, --prune-empty-dirs      prune empty directory chains from the file-list
     --numeric-ids           don't map uid/gid values by user/group name
     --usermap=STRING        custom username mapping
     --groupmap=STRING       custom groupname mapping
     --chown=USER:GROUP      simple username/groupname mapping
     --timeout=SECONDS       set I/O timeout in seconds
     --contimeout=SECONDS    set daemon connection timeout in seconds
 -I, --ignore-times          don't skip files that match in size and mod-time
 -M, --remote-option=OPTION  send OPTION to the remote side only
     --size-only             skip files that match in size
 -@, --modify-window=NUM     set the accuracy for mod-time comparisons
 -T, --temp-dir=DIR          create temporary files in directory DIR
 -y, --fuzzy                 find similar file for basis if no dest file
     --compare-dest=DIR      also compare destination files relative to DIR
     --copy-dest=DIR         ... and include copies of unchanged files
     --link-dest=DIR         hardlink to files in DIR when unchanged
 -z, --compress              compress file data during the transfer
     --compress-level=NUM    explicitly set compression level
     --skip-compress=LIST    skip compressing files with a suffix in LIST
 -C, --cvs-exclude           auto-ignore files the same way CVS does
 -f, --filter=RULE           add a file-filtering RULE
 -F                          same as --filter='dir-merge /.rsync-filter'
                             repeated: --filter='- .rsync-filter'
     --exclude=PATTERN       exclude files matching PATTERN
     --exclude-from=FILE     read exclude patterns from FILE
     --include=PATTERN       don't exclude files matching PATTERN
     --include-from=FILE     read include patterns from FILE
     --files-from=FILE       read list of source-file names from FILE
 -0, --from0                 all *-from/filter files are delimited by 0s
 -s, --protect-args          no space-splitting; only wildcard special-chars
     --address=ADDRESS       bind address for outgoing socket to daemon
     --port=PORT             specify double-colon alternate port number
     --sockopts=OPTIONS      specify custom TCP options
     --blocking-io           use blocking I/O for the remote shell
     --stats                 give some file-transfer stats
 -8, --8-bit-output          leave high-bit chars unescaped in output
 -h, --human-readable        output numbers in a human-readable format
     --progress              show progress during transfer
 -P                          same as --partial --progress
 -i, --itemize-changes       output a change-summary for all updates
     --out-format=FORMAT     output updates using the specified FORMAT
     --log-file=FILE         log what we're doing to the specified FILE
     --log-file-format=FMT   log updates using the specified FMT
     --password-file=FILE    read daemon-access password from FILE
     --list-only             list the files instead of copying them
     --bwlimit=RATE          limit socket I/O bandwidth
     --stop-at=y-m-dTh:m     Stop rsync at year-month-dayThour:minute
     --time-limit=MINS       Stop rsync after MINS minutes have elapsed
     --outbuf=N|L|B          set output buffering to None, Line, or Block
     --write-batch=FILE      write a batched update to FILE
     --only-write-batch=FILE like --write-batch but w/o updating destination
     --read-batch=FILE       read a batched update from FILE
     --protocol=NUM          force an older protocol version to be used
     --iconv=CONVERT_SPEC    request charset conversion of filenames
     --checksum-seed=NUM     set block/file checksum seed (advanced)
     --noatime               do not alter atime when opening source files
 -4, --ipv4                  prefer IPv4
 -6, --ipv6                  prefer IPv6
     --version               print version number
(-h) --help                  show this help (-h is --help only if used alone)

Use "rsync --daemon --help" to see the daemon-mode command-line options.
Please see the rsync(1) and rsyncd.conf(5) man pages for full documentation.
See http://rsync.samba.org/ for updates, bug reports, and answers
mao@ubuntu:~/桌面$ 
```





本地备份文件：

```sh
rsync -av ./a.c ./b.c
```

```sh
mao@ubuntu:~/桌面$ rsync -av ./a.c ./b.c
sending incremental file list
a.c

sent 8,953 bytes  received 35 bytes  17,976.00 bytes/sec
total size is 8,859  speedup is 0.99
mao@ubuntu:~/桌面$ ls -l
总用量 180
-rw-rw-r-- 1 mao mao     4 12月 29  2021 1.txt
-rw------- 1 mao mao  8859 12月 30  2021 a.c
-rwxrwxr-x 1 mao mao 16984 12月 29  2021 a.out
-rw-rw-r-- 1 mao mao  8859 7月  11 22:45 backup.bak
-rw------- 1 mao mao  8859 12月 30  2021 b.c
-rw------- 1 mao mao  9221 12月 30  2021 English_early_education_machine_input.c
-rw------- 1 mao mao  2956 11月  4  2021 filea.c
-rw------- 1 mao mao    96 10月 23  2021 func1.c
-rw------- 1 mao mao    98 10月 23  2021 func2.c
-rwxrw-rw- 1 mao mao  2324 12月 29  2021 linux_file.c
-rw------- 1 mao mao   242 10月 23  2021 main.c
-rw------- 1 mao mao   206 10月 23  2021 main.h
-rw-rw-r-- 1 mao mao 78631 7月  11 22:28 out.txt
-rw-rw-r-- 1 mao mao     4 7月   5 06:18 test.txt
mao@ubuntu:~/桌面$ 
```



远程备份文件：

```sh
rsync -av ./a.c mao127.0.0.1:/home/mao/桌面/c.c
```











# 系统服务管理

## 系统服务及其分类

系统服务是在后台运行的应用程序，并且可以提供一些本地系统或网络的功能。我们把这些应用程序称作服务，也就是 Service

守护进程就是为了实现服务、功能的进程。守护进程就是服务在后台运行的真实进程。



Linux 中的服务按照安装方法不同可以分为 RPM 包默认安装的服务和源码包安装的服务两大类。其中，RPM 包默认安装的服务又因为启动与自启动管理方法不同分为独立的服务和基于 xinetd 的服务。



- 独立的服务：就是独立启动的意思，这种服务可以自行启动，而不用依赖其他的管理服务。因为不依赖其他的管理服务，所以，当客户端请求访问时，独立的服务响应请求更快速。目前，Linux 中的大多数服务都是独立的服务，如 apache 服务、FTP 服务、Samba 服务等。
- 基于 xinetd 的服务：这种服务就不能独立启动了，而要依靠管理服务来调用。这个负责管理的服务就是 xinetd 服务。xinetd 服务是系统的超级守护进程，其作用就是管理不能独立启动的服务。当有客户端请求时，先请求 xinetd 服务，由 xinetd 服务去唤醒相对应的服务。当客户端请求结束后，被唤醒的服务会关闭并释放资源。这样做的好处是只需要持续启动 xinetd 服务，而其他基于 xinetd 的服务只有在需要时才被启动，不会占用过多的服务器资源。但是这种服务由于在有客户端请求时才会被唤醒，所以响应时间相对较长。





## 查询已经安装的服务和区分服务

如何区分这些服务呢？首先要区分 RPM 包默认安装的服务和源码包安装的服务。源码包安装的服务是不能被服务管理命令直接找到的，而且一般会安装到 /usr/local/ 目录中。

也就是说，在 /usr/local/ 目录中的服务都应该是通过源码包安装的服务。RPM 包默认安装的服务都会安装到系统默认位置，所以是可以被服务管理命令（如 service、chkconfig）识别的。



区分独立的服务和基于 xinetd 的服务：

```sh
chkconfig --list [服务名]
```

选项：

- --list：列出 RPM 包默认安装的所有服务的自启动状态；







## 端口

为了统一整个互联网的端口和网络服务的对应关系，以便让所有的主机都能使用相同的机制来请求或提供服务，同一个服务使用相同的端口，这就是协议。

计算机中的协议主要分为两大类：

- 面向连接的可靠的TCP协议（Transmission Control Protocol，传输控制协议）；
- 面向无连接的不可靠的UDP协议（User Datagram Protocol，用户数据报协议）；



这两种协议都支持 216，也就是 65535 个端口



```sh
mao@ubuntu:~/桌面$ cat -n  /etc/services
     1	# Network services, Internet style
     2	#
     3	# Note that it is presently the policy of IANA to assign a single well-known
     4	# port number for both TCP and UDP; hence, officially ports have two entries
     5	# even if the protocol doesn't support UDP operations.
     6	#
     7	# Updated from https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml .
     8	#
     9	# New ports will be added on request if they have been officially assigned
    10	# by IANA and used in the real-world or are needed by a debian package.
    11	# If you need a huge list of used numbers please install the nmap package.
    12	
    13	tcpmux		1/tcp				# TCP port service multiplexer
    14	echo		7/tcp
    15	echo		7/udp
    16	discard		9/tcp		sink null
    17	discard		9/udp		sink null
    18	systat		11/tcp		users
    19	daytime		13/tcp
    20	daytime		13/udp
    21	netstat		15/tcp
    22	qotd		17/tcp		quote
    23	chargen		19/tcp		ttytst source
    24	chargen		19/udp		ttytst source
    25	ftp-data	20/tcp
    26	ftp		21/tcp
    27	fsp		21/udp		fspd
    28	ssh		22/tcp				# SSH Remote Login Protocol
    29	telnet		23/tcp
    30	smtp		25/tcp		mail
    31	time		37/tcp		timserver
    32	time		37/udp		timserver
    33	whois		43/tcp		nicname
    34	tacacs		49/tcp				# Login Host Protocol (TACACS)
    35	tacacs		49/udp
    36	domain		53/tcp				# Domain Name Server
    37	domain		53/udp
    38	bootps		67/udp
    39	bootpc		68/udp
    40	tftp		69/udp
    41	gopher		70/tcp				# Internet Gopher
    42	finger		79/tcp
    43	http		80/tcp		www		# WorldWideWeb HTTP
    44	kerberos	88/tcp		kerberos5 krb5 kerberos-sec	# Kerberos v5
    45	kerberos	88/udp		kerberos5 krb5 kerberos-sec	# Kerberos v5
    46	iso-tsap	102/tcp		tsap		# part of ISODE
    47	acr-nema	104/tcp		dicom		# Digital Imag. & Comm. 300
    48	pop3		110/tcp		pop-3		# POP version 3
    49	sunrpc		111/tcp		portmapper	# RPC 4.0 portmapper
    50	sunrpc		111/udp		portmapper
    51	auth		113/tcp		authentication tap ident
    52	nntp		119/tcp		readnews untp	# USENET News Transfer Protocol
    53	ntp		123/udp				# Network Time Protocol
    54	epmap		135/tcp		loc-srv		# DCE endpoint resolution
    55	netbios-ns	137/tcp				# NETBIOS Name Service
    56	netbios-ns	137/udp
    57	netbios-dgm	138/tcp				# NETBIOS Datagram Service
    58	netbios-dgm	138/udp
    59	netbios-ssn	139/tcp				# NETBIOS session service
    60	netbios-ssn	139/udp
    61	imap2		143/tcp		imap		# Interim Mail Access P 2 and 4
    62	snmp		161/tcp				# Simple Net Mgmt Protocol
    63	snmp		161/udp
    64	snmp-trap	162/tcp		snmptrap	# Traps for SNMP
    65	snmp-trap	162/udp		snmptrap
    66	cmip-man	163/tcp				# ISO mgmt over IP (CMOT)
    67	cmip-man	163/udp
    68	cmip-agent	164/tcp
    69	cmip-agent	164/udp
    70	mailq		174/tcp			# Mailer transport queue for Zmailer
    71	xdmcp		177/udp			# X Display Manager Control Protocol
    72	bgp		179/tcp				# Border Gateway Protocol
    73	smux		199/tcp				# SNMP Unix Multiplexer
    74	qmtp		209/tcp				# Quick Mail Transfer Protocol
    75	z3950		210/tcp		wais		# NISO Z39.50 database
    76	ipx		213/udp				# IPX [RFC1234]
    77	ptp-event	319/udp
    78	ptp-general	320/udp
    79	pawserv		345/tcp				# Perf Analysis Workbench
    80	zserv		346/tcp				# Zebra server
    81	rpc2portmap	369/tcp
    82	rpc2portmap	369/udp				# Coda portmapper
    83	codaauth2	370/tcp
    84	codaauth2	370/udp				# Coda authentication server
    85	clearcase	371/udp		Clearcase
    86	ldap		389/tcp			# Lightweight Directory Access Protocol
    87	ldap		389/udp
    88	svrloc		427/tcp				# Server Location
    89	svrloc		427/udp
    90	https		443/tcp				# http protocol over TLS/SSL
    91	snpp		444/tcp				# Simple Network Paging Protocol
    92	microsoft-ds	445/tcp				# Microsoft Naked CIFS
    93	microsoft-ds	445/udp
    94	kpasswd		464/tcp
    95	kpasswd		464/udp
    96	submissions	465/tcp		ssmtp smtps urd # Submission over TLS [RFC8314]
    97	saft		487/tcp			# Simple Asynchronous File Transfer
    98	isakmp		500/udp				# IPSEC key management
    99	rtsp		554/tcp			# Real Time Stream Control Protocol
   100	rtsp		554/udp
   101	nqs		607/tcp				# Network Queuing system
   102	asf-rmcp	623/udp		# ASF Remote Management and Control Protocol
   103	qmqp		628/tcp
   104	ipp		631/tcp				# Internet Printing Protocol
   105	#
   106	# UNIX specific services
   107	#
   108	exec		512/tcp
   109	biff		512/udp		comsat
   110	login		513/tcp
   111	who		513/udp		whod
   112	shell		514/tcp		cmd syslog	# no passwords used
   113	syslog		514/udp
   114	printer		515/tcp		spooler		# line printer spooler
   115	talk		517/udp
   116	ntalk		518/udp
   117	route		520/udp		router routed	# RIP
   118	gdomap		538/tcp				# GNUstep distributed objects
   119	gdomap		538/udp
   120	uucp		540/tcp		uucpd		# uucp daemon
   121	klogin		543/tcp				# Kerberized `rlogin' (v5)
   122	kshell		544/tcp		krcmd		# Kerberized `rsh' (v5)
   123	dhcpv6-client	546/udp
   124	dhcpv6-server	547/udp
   125	afpovertcp	548/tcp				# AFP over TCP
   126	nntps		563/tcp		snntp		# NNTP over SSL
   127	submission	587/tcp				# Submission [RFC4409]
   128	ldaps		636/tcp				# LDAP over SSL
   129	ldaps		636/udp
   130	tinc		655/tcp				# tinc control port
   131	tinc		655/udp
   132	silc		706/tcp
   133	kerberos-adm	749/tcp				# Kerberos `kadmin' (v5)
   134	#
   135	domain-s	853/tcp				# DNS over TLS [RFC7858]
   136	domain-s	853/udp				# DNS over DTLS [RFC8094]
   137	rsync		873/tcp
   138	ftps-data	989/tcp				# FTP over SSL (data)
   139	ftps		990/tcp
   140	telnets		992/tcp				# Telnet over SSL
   141	imaps		993/tcp				# IMAP over SSL
   142	pop3s		995/tcp				# POP-3 over SSL
   143	#
   144	# From ``Assigned Numbers'':
   145	#
   146	#> The Registered Ports are not controlled by the IANA and on most systems
   147	#> can be used by ordinary user processes or programs executed by ordinary
   148	#> users.
   149	#
   150	#> Ports are used in the TCP [45,106] to name the ends of logical
   151	#> connections which carry long term conversations.  For the purpose of
   152	#> providing services to unknown callers, a service contact port is
   153	#> defined.  This list specifies the port used by the server process as its
   154	#> contact port.  While the IANA can not control uses of these ports it
   155	#> does register or list uses of these ports as a convienence to the
   156	#> community.
   157	#
   158	socks		1080/tcp			# socks proxy server
   159	proofd		1093/tcp
   160	rootd		1094/tcp
   161	openvpn		1194/tcp
   162	openvpn		1194/udp
   163	rmiregistry	1099/tcp			# Java RMI Registry
   164	lotusnote	1352/tcp	lotusnotes	# Lotus Note
   165	ms-sql-s	1433/tcp			# Microsoft SQL Server
   166	ms-sql-s	1433/udp
   167	ms-sql-m	1434/tcp			# Microsoft SQL Monitor
   168	ms-sql-m	1434/udp
   169	ingreslock	1524/tcp
   170	datametrics	1645/tcp	old-radius
   171	datametrics	1645/udp	old-radius
   172	sa-msg-port	1646/tcp	old-radacct
   173	sa-msg-port	1646/udp	old-radacct
   174	kermit		1649/tcp
   175	groupwise	1677/tcp
   176	l2f		1701/udp	l2tp
   177	radius		1812/tcp
   178	radius		1812/udp
   179	radius-acct	1813/tcp	radacct		# Radius Accounting
   180	radius-acct	1813/udp	radacct
   181	cisco-sccp	2000/tcp			# Cisco SCCP
   182	nfs		2049/tcp			# Network File System
   183	nfs		2049/udp			# Network File System
   184	gnunet		2086/tcp
   185	gnunet		2086/udp
   186	rtcm-sc104	2101/tcp			# RTCM SC-104 IANA 1/29/99
   187	rtcm-sc104	2101/udp
   188	gsigatekeeper	2119/tcp
   189	gris		2135/tcp		# Grid Resource Information Server
...
...
...
   298	zabbix-agent	10050/tcp			# Zabbix Agent
   299	zabbix-trapper	10051/tcp			# Zabbix Trapper
   300	amanda		10080/tcp			# amanda backup services
   301	dicom		11112/tcp
   302	hkp		11371/tcp			# OpenPGP HTTP Keyserver
   303	db-lsp		17500/tcp			# Dropbox LanSync Protocol
   304	dcap		22125/tcp			# dCache Access Protocol
   305	gsidcap		22128/tcp			# GSI dCache Access Protocol
   306	wnn6		22273/tcp			# wnn6
   307	
   308	#
   309	# Datagram Delivery Protocol services
   310	#
   311	rtmp		1/ddp			# Routing Table Maintenance Protocol
   312	nbp		2/ddp			# Name Binding Protocol
   313	echo		4/ddp			# AppleTalk Echo Protocol
   314	zip		6/ddp			# Zone Information Protocol
   315	
   316	#=========================================================================
   317	# The remaining port numbers are not as allocated by IANA.
   318	#=========================================================================
   319	
   320	# Kerberos (Project Athena/MIT) services
   321	kerberos4	750/udp		kerberos-iv kdc	# Kerberos (server)
   322	kerberos4	750/tcp		kerberos-iv kdc
   323	kerberos-master	751/udp		kerberos_master	# Kerberos authentication
   324	kerberos-master	751/tcp
   325	passwd-server	752/udp		passwd_server	# Kerberos passwd server
   326	krb-prop	754/tcp		krb_prop krb5_prop hprop # Kerberos slave propagation
   327	zephyr-srv	2102/udp			# Zephyr server
   328	zephyr-clt	2103/udp			# Zephyr serv-hm connection
   329	zephyr-hm	2104/udp			# Zephyr hostmanager
   330	iprop		2121/tcp			# incremental propagation
   331	supfilesrv	871/tcp			# Software Upgrade Protocol server
   332	supfiledbg	1127/tcp		# Software Upgrade Protocol debugging
   333	
   334	#
   335	# Services added for the Debian GNU/Linux distribution
   336	#
   337	poppassd	106/tcp				# Eudora
   338	poppassd	106/udp
   339	moira-db	775/tcp		moira_db	# Moira database
   340	moira-update	777/tcp		moira_update	# Moira update protocol
   341	moira-ureg	779/udp		moira_ureg	# Moira user registration
   342	spamd		783/tcp				# spamassassin daemon
   343	skkserv		1178/tcp			# skk jisho server port
   344	predict		1210/udp			# predict -- satellite tracking
   345	rmtcfg		1236/tcp			# Gracilis Packeten remote config server
   346	xtel		1313/tcp			# french minitel
   347	xtelw		1314/tcp			# french minitel
   348	support		1529/tcp			# GNATS
   349	cfinger		2003/tcp			# GNU Finger
   350	frox		2121/tcp			# frox: caching ftp proxy
   351	zebrasrv	2600/tcp			# zebra service
   352	zebra		2601/tcp			# zebra vty
   353	ripd		2602/tcp			# ripd vty (zebra)
   354	ripngd		2603/tcp			# ripngd vty (zebra)
   355	ospfd		2604/tcp			# ospfd vty (zebra)
   356	bgpd		2605/tcp			# bgpd vty (zebra)
   357	ospf6d		2606/tcp			# ospf6d vty (zebra)
   358	ospfapi		2607/tcp			# OSPF-API
   359	isisd		2608/tcp			# ISISd vty (zebra)
   360	afbackup	2988/tcp			# Afbackup system
   361	afbackup	2988/udp
   362	afmbackup	2989/tcp			# Afmbackup system
   363	afmbackup	2989/udp
   364	fax		4557/tcp			# FAX transmission service (old)
   365	hylafax		4559/tcp			# HylaFAX client-server protocol (new)
   366	distmp3		4600/tcp			# distmp3host daemon
   367	munin		4949/tcp	lrrd		# Munin
   368	enbd-cstatd	5051/tcp			# ENBD client statd
   369	enbd-sstatd	5052/tcp			# ENBD server statd
   370	pcrd		5151/tcp			# PCR-1000 Daemon
   371	noclog		5354/tcp			# noclogd with TCP (nocol)
   372	noclog		5354/udp			# noclogd with UDP (nocol)
   373	hostmon		5355/tcp			# hostmon uses TCP (nocol)
   374	hostmon		5355/udp			# hostmon uses UDP (nocol)
   375	rplay		5555/udp			# RPlay audio service
   376	nrpe		5666/tcp			# Nagios Remote Plugin Executor
   377	nsca		5667/tcp			# Nagios Agent - NSCA
   378	mrtd		5674/tcp			# MRT Routing Daemon
   379	bgpsim		5675/tcp			# MRT Routing Simulator
   380	canna		5680/tcp			# cannaserver
   381	syslog-tls	6514/tcp			# Syslog over TLS [RFC5425]
   382	sane-port	6566/tcp	sane saned	# SANE network scanner daemon
   383	ircd		6667/tcp			# Internet Relay Chat
   384	zope-ftp	8021/tcp			# zope management by ftp
   385	tproxy		8081/tcp			# Transparent Proxy
   386	omniorb		8088/tcp			# OmniORB
   387	omniorb		8088/udp
   388	clc-build-daemon 8990/tcp			# Common lisp build daemon
   389	xinetd		9098/tcp
   390	mandelspawn	9359/udp	mandelbrot	# network mandelbrot
   391	git		9418/tcp			# Git Version Control System
   392	zope		9673/tcp			# zope server
   393	webmin		10000/tcp
   394	kamanda		10081/tcp			# amanda backup services (Kerberos)
   395	amandaidx	10082/tcp			# amanda backup services
   396	amidxtape	10083/tcp			# amanda backup services
   397	smsqp		11201/tcp			# Alamin SMS gateway
   398	smsqp		11201/udp
   399	xpilot		15345/tcp			# XPilot Contact Port
   400	xpilot		15345/udp
   401	sgi-cmsd	17001/udp		# Cluster membership services daemon
   402	sgi-crsd	17002/udp
   403	sgi-gcd		17003/udp			# SGI Group membership daemon
   404	sgi-cad		17004/tcp			# Cluster Admin daemon
   405	isdnlog		20011/tcp			# isdn logging system
   406	isdnlog		20011/udp
   407	vboxd		20012/tcp			# voice box system
   408	vboxd		20012/udp
   409	binkp		24554/tcp			# binkp fidonet protocol
   410	asp		27374/tcp			# Address Search Protocol
   411	asp		27374/udp
   412	csync2		30865/tcp			# cluster synchronization tool
   413	dircproxy	57000/tcp			# Detachable IRC Proxy
   414	tfido		60177/tcp			# fidonet EMSI over telnet
   415	fido		60179/tcp			# fidonet EMSI over TCP
   416	
   417	# Local services
mao@ubuntu:~/桌面$ 
```





## 查询系统中已经启动的服务

通过查询服务器中开启的端口，来判断当前服务器开启了哪些服务：

```sh
netstat 选项
```



选项：

- -a：列出系统中所有网络连接，包括已经连接的网络服务、监听的网络服务和 Socket 套接字；
- -t：列出 TCP 数据；
- -u：列出 UDP 数据；
- -l：列出正在监听的网络服务（不包含已经连接的网络服务）；
- -n：用端口号来显示而不用服务名；
- -p：列出该服务的进程 ID (PID)；



```sh
mao@ubuntu:~/桌面$ netstat --help
usage: netstat [-vWeenNcCF] [<Af>] -r         netstat {-V|--version|-h|--help}
       netstat [-vWnNcaeol] [<Socket> ...]
       netstat { [-vWeenNac] -i | [-cnNe] -M | -s [-6tuw] }

        -r, --route              显示路由表
        -i, --interfaces         display interface table
        -g, --groups             display multicast group memberships
        -s, --statistics         display networking statistics (like SNMP)
        -M, --masquerade         display masqueraded connections

        -v, --verbose            显示详细信息
        -W, --wide               don't truncate IP addresses
        -n, --numeric            不解析名称
        --numeric-hosts          不解析主机名
        --numeric-ports          忽略端口名称
        --numeric-users          忽略用户名
        -N, --symbolic           resolve hardware names
        -e, --extend             显示更多信息
        -p, --programs           display PID/Program name for sockets
        -o, --timers             display timers
        -c, --continuous         continuous listing

        -l, --listening          display listening server sockets
        -a, --all                display all sockets (default: connected)
        -F, --fib                display Forwarding Information Base (default)
        -C, --cache              display routing cache instead of FIB
        -Z, --context            display SELinux security context for sockets

  <Socket>={-t|--tcp} {-u|--udp} {-U|--udplite} {-S|--sctp} {-w|--raw}
           {-x|--unix} --ax25 --ipx --netrom
  <AF>=Use '-6|-4' or '-A <af>' or '--<af>'；默认： inet
  列出所有支持的协议：
    inet (DARPA Internet) inet6 (IPv6) ax25 (AMPR AX.25) 
    netrom (AMPR NET/ROM) ipx (Novell IPX) ddp (Appletalk DDP) 
    x25 (CCITT X.25) 
mao@ubuntu:~/桌面$ 
```



列出系统中所有已经启动的服务（已经监听的端口），但不包含已经连接的网络服务：

```sh
mao@ubuntu:~/桌面$  netstat -tlunp
（并非所有进程都能被检测到，所有非本用户的进程信息将不会显示，如果想看到所有信息，则必须切换到 root 用户）
激活Internet连接 (仅服务器)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      -                   
tcp6       0      0 ::1:631                 :::*                    LISTEN      -                   
udp        0      0 0.0.0.0:51042           0.0.0.0:*                           -                   
udp        0      0 127.0.0.53:53           0.0.0.0:*                           -                   
udp        0      0 0.0.0.0:631             0.0.0.0:*                           -                   
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           -                   
udp6       0      0 :::55966                :::*                                -                   
udp6       0      0 :::5353                 :::*                                -                   
mao@ubuntu:~/桌面$ sudo netstat -tlunp
[sudo] mao 的密码： 
激活Internet连接 (仅服务器)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      862/systemd-resolve 
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      988/cupsd           
tcp6       0      0 ::1:631                 :::*                    LISTEN      988/cupsd           
udp        0      0 0.0.0.0:51042           0.0.0.0:*                           895/avahi-daemon: r 
udp        0      0 127.0.0.53:53           0.0.0.0:*                           862/systemd-resolve 
udp        0      0 0.0.0.0:631             0.0.0.0:*                           995/cups-browsed    
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           895/avahi-daemon: r 
udp6       0      0 :::55966                :::*                                895/avahi-daemon: r 
udp6       0      0 :::5353                 :::*                                895/avahi-daemon: r 
mao@ubuntu:~/桌面$ 
```



- Proto：数据包的协议。分为 TCP 和 UDP 数据包；
- Recv-Q：表示收到的数据已经在本地接收缓冲，但是还没有被进程取走的数据包数量；
- Send-Q：对方没有收到的数据包数量；或者没有 Ack 回复的，还在本地缓冲区的数据包数量；
- Local Address：本地 IP : 端口。通过端口可以知道本机开启了哪些服务；
- Foreign Address：远程主机：端口。也就是远程是哪个 IP、使用哪个端口连接到本机。由于这条命令只能查看监听端口，所以没有 IP 连接到到本机；
- State:连接状态。主要有已经建立连接（ESTABLISED）和监听（LISTEN）两种状态，当前只能查看监听状态；
- PID/Program name：进程 ID 和进程命令；





查看所有的网络连接，包括已连接的网络服务、监听的网络服务和Socket套接字：

```sh
ao@ubuntu:~/桌面$ netstat -an
激活Internet连接 (服务器和已建立连接的)
Proto Recv-Q Send-Q Local Address           Foreign Address         State      
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN     
tcp6       0      0 ::1:631                 :::*                    LISTEN     
udp        0      0 0.0.0.0:51042           0.0.0.0:*                          
udp        0      0 127.0.0.53:53           0.0.0.0:*                          
udp        0      0 192.168.202.128:68      192.168.202.254:67      ESTABLISHED
udp        0      0 0.0.0.0:631             0.0.0.0:*                          
udp        0      0 0.0.0.0:5353            0.0.0.0:*                          
udp6       0      0 :::55966                :::*                               
udp6       0      0 :::5353                 :::*                               
raw6       0      0 :::58                   :::*                    7          
活跃的UNIX域套接字 (服务器和已建立连接的)
Proto RefCnt Flags       Type       State         I-Node   路径
unix  3      [ ]         数据报                34457    /run/systemd/notify
unix  2      [ ACC ]     流        LISTENING     34460    /run/systemd/private
unix  2      [ ACC ]     流        LISTENING     34462    /run/systemd/userdb/io.systemd.DynamicUser
unix  2      [ ]         数据报                34471    /run/systemd/journal/syslog
unix  2      [ ]         数据报                58079    /run/user/1000/systemd/notify
unix  2      [ ACC ]     流        LISTENING     34473    /run/systemd/fsck.progress
unix  2      [ ACC ]     流        LISTENING     58082    /run/user/1000/systemd/private
unix  2      [ ACC ]     流        LISTENING     58087    /run/user/1000/bus
unix  16     [ ]         数据报                34481    /run/systemd/journal/dev-log
unix  2      [ ACC ]     流        LISTENING     34483    /run/systemd/journal/stdout
unix  8      [ ]         数据报                34485    /run/systemd/journal/socket
unix  2      [ ACC ]     流        LISTENING     58088    /run/user/1000/gnupg/S.dirmngr
unix  2      [ ACC ]     SEQPACKET  LISTENING     34487    /run/udev/control
unix  2      [ ACC ]     流        LISTENING     58089    /run/user/1000/gnupg/S.gpg-agent.browser
unix  2      [ ACC ]     流        LISTENING     58090    /run/user/1000/gnupg/S.gpg-agent.extra
unix  2      [ ACC ]     流        LISTENING     58091    /run/user/1000/gnupg/S.gpg-agent.ssh
unix  2      [ ACC ]     流        LISTENING     58092    /run/user/1000/gnupg/S.gpg-agent
unix  2      [ ACC ]     流        LISTENING     58093    /run/user/1000/pk-debconf-socket
unix  2      [ ACC ]     流        LISTENING     58094    /run/user/1000/pulse/native
unix  2      [ ACC ]     流        LISTENING     45902    @/tmp/.ICE-unix/1817
unix  2      [ ACC ]     流        LISTENING     58095    /run/user/1000/snapd-session-agent.socket
unix  2      [ ACC ]     流        LISTENING     39872    @/tmp/dbus-79uqNDt0
unix  2      [ ACC ]     流        LISTENING     52863    @/tmp/.X11-unix/X0
unix  2      [ ACC ]     流        LISTENING     54126    /run/user/1000/keyring/control
unix  2      [ ACC ]     流        LISTENING     21493    /run/systemd/journal/io.systemd.journal
unix  2      [ ACC ]     流        LISTENING     58805    /run/user/1000/keyring/pkcs11
unix  2      [ ACC ]     流        LISTENING     58829    /run/user/1000/keyring/ssh
unix  2      [ ACC ]     流        LISTENING     52864    /tmp/.X11-unix/X0
unix  2      [ ACC ]     流        LISTENING     44891    /tmp/ssh-hpKPX3PkCrcQ/agent.1715
unix  2      [ ACC ]     流        LISTENING     45903    /tmp/.ICE-unix/1817
unix  2      [ ACC ]     流        LISTENING     52466    @/tmp/dbus-MxgQM50k
unix  2      [ ACC ]     流        LISTENING     61143    @/home/mao/.cache/ibus/dbus-O08ewsTm
unix  2      [ ACC ]     流        LISTENING     36076    /run/acpid.socket
unix  2      [ ACC ]     流        LISTENING     36078    /run/avahi-daemon/socket
unix  2      [ ACC ]     流        LISTENING     36080    /run/cups/cups.sock
unix  2      [ ACC ]     流        LISTENING     36082    /run/dbus/system_bus_socket
unix  2      [ ACC ]     流        LISTENING     36084    /run/snapd.socket
unix  2      [ ACC ]     流        LISTENING     36086    /run/snapd-snap.socket
unix  2      [ ACC ]     流        LISTENING     44263    /var/run/vmware/guestServicePipe
unix  2      [ ACC ]     流        LISTENING     36088    /run/uuidd/request
unix  2      [ ACC ]     流        LISTENING     39871    @/tmp/dbus-Cc8TByyF
unix  2      [ ACC ]     流        LISTENING     52465    @/tmp/dbus-jCwV600x
unix  2      [ ACC ]     流        LISTENING     54190    @/tmp/dbus-oaJ2tknJpD
unix  2      [ ACC ]     流        LISTENING     26072    /run/irqbalance//irqbalance909.sock
unix  3      [ ]         流        已连接     62593    /run/user/1000/bus
unix  3      [ ]         流        已连接     49490    
unix  3      [ ]         流        已连接     48277    
unix  3      [ ]         流        已连接     29675    
unix  3      [ ]         流        已连接     25987    /run/systemd/journal/stdout
unix  2      [ ]         数据报                58069    
unix  3      [ ]         流        已连接     52581    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     29688    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     57090    
unix  3      [ ]         流        已连接     58703    /run/user/1000/bus
unix  3      [ ]         流        已连接     49495    
unix  3      [ ]         流        已连接     25967    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     30330    
unix  3      [ ]         流        已连接     18127    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     58836    
unix  2      [ ]         数据报                45846    
unix  2      [ ]         数据报                60937    
unix  3      [ ]         流        已连接     66573    
unix  3      [ ]         流        已连接     62691    /run/user/1000/bus
unix  3      [ ]         流        已连接     53532    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     39400    
unix  3      [ ]         流        已连接     58083    
unix  2      [ ]         数据报                44405    
unix  3      [ ]         流        已连接     44418    /run/dbus/system_bus_socket
unix  2      [ ]         数据报                46294    
unix  3      [ ]         流        已连接     58701    
unix  3      [ ]         流        已连接     45843    
unix  3      [ ]         流        已连接     64555    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     18421    /run/systemd/journal/stdout
unix  2      [ ]         流        已连接     39643    
unix  3      [ ]         流        已连接     30309    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     45995    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     30648    
unix  3      [ ]         流        已连接     45044    
unix  3      [ ]         流        已连接     28469    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     58803    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     39783    @/tmp/dbus-jCwV600x
unix  3      [ ]         流        已连接     45996    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     45913    
...
...
...
unix  3      [ ]         流        已连接     45749    
unix  3      [ ]         流        已连接     61895    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     61583    /run/user/1000/bus
unix  2      [ ]         数据报                30683    
unix  3      [ ]         流        已连接     52915    
unix  3      [ ]         流        已连接     48911    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     49703    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     36265    
unix  3      [ ]         流        已连接     55765    
unix  3      [ ]         流        已连接     58314    
unix  3      [ ]         流        已连接     30619    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     39846    
unix  3      [ ]         流        已连接     64567    /run/user/1000/bus
unix  3      [ ]         数据报                47501    
unix  3      [ ]         流        已连接     45932    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     50942    /run/user/1000/bus
unix  3      [ ]         流        已连接     45926    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     62596    
unix  3      [ ]         流        已连接     45899    /run/user/1000/bus
unix  3      [ ]         流        已连接     49872    /run/user/1000/bus
unix  3      [ ]         流        已连接     63610    /run/user/1000/bus
unix  3      [ ]         流        已连接     18153    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     63607    
unix  3      [ ]         流        已连接     45838    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     66634    
unix  3      [ ]         流        已连接     64581    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     63604    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     62863    
unix  3      [ ]         流        已连接     55766    
unix  3      [ ]         流        已连接     58118    
unix  3      [ ]         流        已连接     52919    
unix  3      [ ]         流        已连接     48122    
unix  3      [ ]         流        已连接     54870    
unix  3      [ ]         流        已连接     55779    
unix  2      [ ]         数据报                21495    
unix  3      [ ]         流        已连接     62642    
unix  3      [ ]         流        已连接     45927    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     58117    
unix  3      [ ]         流        已连接     30676    
unix  3      [ ]         流        已连接     52970    
unix  3      [ ]         流        已连接     45048    /run/systemd/journal/stdout
unix  2      [ ]         数据报                47649    
unix  3      [ ]         流        已连接     61255    @/tmp/.X11-unix/X0
unix  3      [ ]         流        已连接     59748    
unix  3      [ ]         流        已连接     55805    
unix  3      [ ]         流        已连接     44413    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     62758    
unix  3      [ ]         流        已连接     56823    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     54750    
unix  3      [ ]         流        已连接     55639    
unix  3      [ ]         流        已连接     52948    
unix  3      [ ]         流        已连接     51292    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     54127    
unix  3      [ ]         流        已连接     55701    @/tmp/.X11-unix/X0
unix  3      [ ]         流        已连接     60982    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     39869    /run/user/1000/bus
unix  3      [ ]         流        已连接     60926    /run/user/1000/bus
unix  3      [ ]         流        已连接     30679    
unix  3      [ ]         流        已连接     58323    @/tmp/.ICE-unix/1817
unix  3      [ ]         流        已连接     56819    /run/dbus/system_bus_socket
unix  2      [ ]         数据报                54112    
unix  3      [ ]         流        已连接     55778    
unix  3      [ ]         流        已连接     55696    
unix  3      [ ]         流        已连接     60981    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     44955    /run/user/1000/bus
unix  3      [ ]         流        已连接     49701    /run/dbus/system_bus_socket
unix  3      [ ]         数据报                47502    
unix  3      [ ]         流        已连接     39850    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     61896    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     60055    @/home/mao/.cache/ibus/dbus-O08ewsTm
unix  3      [ ]         流        已连接     55802    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     60997    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     54571    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     63606    
unix  3      [ ]         流        已连接     56567    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     62819    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     54867    
unix  2      [ ]         数据报                36870    
unix  3      [ ]         流        已连接     39867    /run/user/1000/bus
unix  3      [ ]         流        已连接     39854    
unix  3      [ ]         流        已连接     52969    
unix  3      [ ]         流        已连接     60110    
unix  3      [ ]         流        已连接     60100    
unix  3      [ ]         流        已连接     55799    
unix  3      [ ]         流        已连接     51044    
unix  3      [ ]         数据报                36872    
unix  3      [ ]         流        已连接     45994    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     58365    
unix  3      [ ]         流        已连接     54775    
unix  3      [ ]         流        已连接     64561    /run/user/1000/bus
unix  3      [ ]         流        已连接     47586    
unix  3      [ ]         流        已连接     30618    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     59757    
unix  2      [ ]         数据报                55812    
unix  3      [ ]         流        已连接     53298    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     18176    
unix  3      [ ]         流        已连接     60346    @/tmp/.X11-unix/X0
unix  3      [ ]         流        已连接     45989    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     66578    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     61244    
unix  3      [ ]         流        已连接     63603    
unix  3      [ ]         流        已连接     45919    /run/user/1000/bus
unix  3      [ ]         流        已连接     62690    /run/user/1000/bus
unix  3      [ ]         流        已连接     56906    /run/user/1000/bus
unix  3      [ ]         流        已连接     62585    
unix  3      [ ]         流        已连接     45818    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     61856    /run/user/1000/bus
unix  3      [ ]         流        已连接     30650    
unix  3      [ ]         流        已连接     52924    
unix  3      [ ]         流        已连接     25988    /run/systemd/journal/stdout
unix  2      [ ]         数据报                47497    
unix  3      [ ]         流        已连接     63605    
unix  3      [ ]         流        已连接     64565    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     18177    
unix  3      [ ]         数据报                36873    
unix  3      [ ]         流        已连接     62687    
unix  3      [ ]         流        已连接     56822    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     54766    
unix  3      [ ]         流        已连接     66583    /run/user/1000/bus
unix  3      [ ]         流        已连接     33566    
unix  3      [ ]         流        已连接     44408    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     62762    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     60056    
unix  3      [ ]         流        已连接     63608    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         数据报                36482    
unix  3      [ ]         流        已连接     62865    
unix  3      [ ]         流        已连接     55638    
unix  3      [ ]         流        已连接     52922    /run/user/1000/pulse/native
unix  3      [ ]         流        已连接     54823    
unix  3      [ ]         流        已连接     45936    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     58104    
unix  2      [ ]         数据报                28370    
unix  3      [ ]         流        已连接     47514    
unix  3      [ ]         流        已连接     55714    /run/user/1000/bus
unix  3      [ ]         流        已连接     54114    
unix  3      [ ]         流        已连接     63569    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     45591    
unix  3      [ ]         流        已连接     58366    
unix  2      [ ]         数据报                55694    
unix  3      [ ]         流        已连接     64564    /run/systemd/journal/stdout
unix  2      [ ]         数据报                47811    
unix  3      [ ]         流        已连接     54101    
unix  3      [ ]         流        已连接     58904    @/tmp/.X11-unix/X0
unix  3      [ ]         流        已连接     62685    
unix  3      [ ]         流        已连接     58321    
unix  3      [ ]         流        已连接     55698    
unix  2      [ ]         数据报                51047    
unix  3      [ ]         流        已连接     52866    
unix  3      [ ]         流        已连接     50940    
unix  3      [ ]         数据报                47500    
unix  3      [ ]         流        已连接     63572    
unix  3      [ ]         流        已连接     63626    @/dbus-vfs-daemon/socket-VJqkFTAK
unix  3      [ ]         流        已连接     54776    
unix  3      [ ]         流        已连接     52920    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     58838    @/home/mao/.cache/ibus/dbus-O08ewsTm
unix  3      [ ]         流        已连接     52947    
unix  3      [ ]         流        已连接     60068    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     47984    
unix  3      [ ]         流        已连接     54779    @/tmp/.X11-unix/X0
unix  3      [ ]         流        已连接     60072    @/home/mao/.cache/ibus/dbus-O08ewsTm
unix  3      [ ]         流        已连接     55767    /run/user/1000/bus
unix  3      [ ]         流        已连接     54116    /run/user/1000/bus
unix  3      [ ]         流        已连接     54768    @/home/mao/.cache/ibus/dbus-O08ewsTm
unix  3      [ ]         流        已连接     60066    
unix  3      [ ]         流        已连接     60112    @/tmp/.X11-unix/X0
unix  3      [ ]         流        已连接     26073    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     45520    /run/systemd/journal/stdout
unix  3      [ ]         流        已连接     58313    
unix  3      [ ]         流        已连接     54769    
unix  3      [ ]         流        已连接     60114    /run/user/1000/bus
unix  3      [ ]         流        已连接     66577    /run/dbus/system_bus_socket
unix  3      [ ]         流        已连接     60052    
unix  3      [ ]         流        已连接     54194    
unix  3      [ ]         流        已连接     52985    
unix  3      [ ]         流        已连接     55804    
unix  3      [ ]         流        已连接     62862    
unix  3      [ ]         流        已连接     65606    @/tmp/dbus-oaJ2tknJpD
unix  3      [ ]         流        已连接     55795    /run/user/1000/bus
unix  3      [ ]         流        已连接     30675    
mao@ubuntu:~/桌面$ 
```



- Proto：协议，一般是unix；
- RefCnt：连接到此Socket的进程数量；
- Flags：连接标识；
- Type：Socket访问类型；
- State：状态，LISTENING表示监听，CONNECTED表示已经建立连接；
- I-Node：程序文件的 i 节点号；
- Path：Socke程序的路径，或者相关数据的输出路径；





## 独立服务管理

### 独立服务的启动管理

独立的服务要想启动，主要有两种方法。

1. **使用/etc/init.d/目录中的启动脚本来启动独立的服务**



```sh
/etc/init.d独立服务名 start| stop|status|restart|...
```



参数：

- start：启动服务；
- stop：停止服务；
- status：查看服务状态；
- restart：重启动服务；



2. **使用service命令来启动独立的服务**



```sh
service 独立服务名 start|stop|restart|...
```



service 命令还可以查看所有独立服务的启动状态：

```sh
service --status-all
```



```sh
mao@ubuntu:~/桌面$ service --status-all
 [ + ]  acpid
 [ - ]  alsa-utils
 [ - ]  anacron
 [ + ]  apparmor
 [ + ]  apport
 [ + ]  atd
 [ + ]  avahi-daemon
 [ - ]  bluetooth
 [ - ]  console-setup.sh
 [ + ]  cron
 [ + ]  cups
 [ + ]  cups-browsed
 [ + ]  dbus
 [ + ]  gdm3
 [ - ]  grub-common
 [ - ]  hwclock.sh
 [ + ]  irqbalance
 [ + ]  kerneloops
 [ - ]  keyboard-setup.sh
 [ + ]  kmod
 [ + ]  network-manager
 [ + ]  open-vm-tools
 [ + ]  openvpn
 [ - ]  plymouth
 [ - ]  plymouth-log
 [ - ]  pppd-dns
 [ + ]  procps
 [ - ]  pulseaudio-enable-autospawn
 [ - ]  quota
 [ - ]  quotarpc
 [ - ]  rsync
 [ + ]  rsyslog
 [ - ]  saned
 [ - ]  speech-dispatcher
 [ - ]  spice-vdagent
 [ + ]  udev
 [ + ]  ufw
 [ + ]  unattended-upgrades
 [ - ]  uuidd
 [ + ]  whoopsie
 [ - ]  x11-common
mao@ubuntu:~/桌面$ 
```





### 独立服务的自启动管理

自启动指的是在系统之后，服务是否随着系统的启动而自动启动。

独立服务的自启动方法有三种



1. **使用 chkconfig 服务自启动管理命令**



```sh
chkconfig --list
```



使用 chkconfig 命令除了可以查看所有 RPM 包默认安装服务的自启动状态，也可以修改和设置 RPM 包默认安装服务的自启动状态，只是独立的服务和基于 xinetd 的服务的设定方法稍有不同。

```sh
chkconfig [--level 运行级别][独立服务名][on|off]
```

- --level: 设定在哪个运行级别中开机自启动（on），或者关闭自启动（off）





2. **修改 /etc/rc.d/rc.local 文件，设置服务自启动**

在文件中加入服务的启动命令。这个文件是在系统启动时，在输入用户名和密码之前最后读取的文件。这个文件中有什么命令，都会在系统启动时调用。

如果我们把服务的启动命令放入这个文件，这个服务就会在开机时自启动





3. 使用 ntsysv 命令管理自启动



```sh
ntsysv [--level 运行级别]
```

- --level 运行级别：可以指定设定自启动的运行级别







## xinetd服务管理

### 启动

基于 xinetd 的服务没有自己独立的启动脚本程序，是需要依赖 xinetd 的启动脚本来启动的。xinetd 本身是独立的服务，所以 xinetd 服务自己的启动方法和独立服务的启动方法是一致的。

但是，所有基于 xinetd 这个超级守护进程的其他服务就不是这样的了，必须修改该服务的配置文件，才能启动基于 xinetd 的服务。所有基于 xinetd 服务的配置文件都保存在 /etc/xinetd.d/ 目录中

Telnet 服务也是分为"客户端/服务器端"的，其中服务器端是用来启动 Telnet 服务的，并不安全；客户端是用来连接服务器端或测试服务器的端口是否开启的，在实际工作中我们主要使用 Telnet 客户端来测试远程服务器开启了哪些端口



客户端的命令格式如下：

```sh
telnet 服务器IP
telnet 服务器IP 端口
```



虽然 Telnet 服务不安全，但 Telnet 服务是基于 xinetd 的服务，我们使用 Telnet 服务来学习一下基于 xinetd 服务的启动管理。在目前的 Linux 系统中，Telnet 的服务器端都是不安装的，如果进行测试，则需要手工安装。

```sh
rpm-ivh/mnt/cdroin/Packages/telnet-server-0.17-47.el6.i686.rpm
```



基于 xinetd 服务的配置文件都在 /etc/xinetd.d/ 目录中，那么 Telnet 服务的配置文件就是 /etc/xinetd.d/telnet

```sh
cat -n /etc/xinetd.d/telnet
```

```sh
#default: on
#description: The telnet server serves telnet sessions; it uses \
#unencrypted username/password pairs for authentication.
service telnet
#服务的名称为telnet
{
flags = REUSE
#标志为REUSE，设定TCP/IP socket可重用
socketjtype = stream
#使用 TCP协议数据包
wait = no
#允许多个连接同时连接
user = root
#启动服务的用户为root
server = /usr/sbin/in.telnetd
#服务的启动程序
log_on_failure += USERID
#登录失败后，记录用户的ID
disable = yes
#服务不启动
}
```



如果想要启动 Telnet 服务，则只需要把 /etc/xinetd.d/telnet 文件中的"disable=yes"改为"disable=no"即可，"disable"代表取消，"disable=yes"代表取消是 yes，当然不启动服务；"disable=no"代表取消是 no





### 自启动



使用 chkconfig 命令管理自启动

```sh
chkconfig 服务名 on|off
```





## 常见服务



|    服务名称     |                           功能简介                           | 建议 |
| :-------------: | :----------------------------------------------------------: | :--: |
|      acpid      | 电源管理接口。如果是笔记本电脑用户，则建议开启，可以监听内核层的相关电源事件 | 开启 |
|     anacron     | 系统的定时任务程序。是 cron 的一个子系统，如果定时任务错过了执行时间，则可以通过 anacron 继续唤醒执行 | 关闭 |
|    alsasound    |          alsa 声卡驱动。如果使用 alsa 声卡，则开启           | 关闭 |
|      apmd       |    电源管理模块。如果支持 acpid，就不需要 apmd，可以关闭     | 关闭 |
|       atd       | 指定系统在特定时间执行某个任务，只能执行一次。如果需要则开启，但我们一般使用 crond 来执行循环定时任务 | 关闭 |
|     auditd      | 审核子系统。如果开启了此服务，那么 SELinux 的审核信息会写入 /var/log/audit/ audit.log 文件；如果不开启，那么审核信息会记录在 syslog 中 | 开启 |
|     autofs      | 让服务器可以自动挂载网络中其他服务器的共享数据,一般用来自动挂载 NFS 服务。如果没有 NFS 服务，则建议关闭 | 关闭 |
|  avahi-daemon   | avahi 是 zeroconf 协议的实现，它可以在没有 DNS 服务的局域网里发现基于 zeroconf 协议的设备和服务。除非有兼容设备或使用 zeroconf 协议，否则关闭 | 关闭 |
|    bluetooth    |     蓝牙设备支持。一般不会在服务器上启用蓝牙设备，关闭它     | 关闭 |
|      capi       |                 仅对使用 ISND 设备的用户有用                 | 关闭 |
|  chargen-dgram  | 使用 UDP 协议的 chargen server。其主要提供类似远程打字的功能 | 关闭 |
| chargen-stream  |                             同上                             | 关闭 |
|    cpuspeed     | 可以用来调整 CPU 的频率。当闲置时，可以自动降低 CPU 频率来节省电量 | 开启 |
|      crond      | 系统的定时任务，一般的 Linux 服务器都需要定时任务来协助系统维护。建议开启 | 开启 |
|       cvs       |                       一个版本控制系统                       | 关闭 |
|  daytime-dgram  | 使用 TCP 协议的 daytime 守护进程，该协议为客户机实现从远程服务器获取日期和时间的功能 | 关闭 |
| daytime-slream  |                             同上                             | 关闭 |
|     dovecot     | 邮件服务中 POP3/IMAP 服务的守护进程，主要用来接收信件。如果启动了邮件服务则开启：否则关闭 | 关闭 |
|   echo-dgram    |                   服务器回显客户服务的进程                   | 关闭 |
|   echo-stream   |                             同上                             | 关闭 |
|    firstboot    | 系统安装完成后，有一个欢迎界面，需要对系统进行初始设定，这就是这个服务的作用。既然不是第一次启动了，则建议关闭 | 关闭 |
|       gpm       | 在字符终端 (ttyl~tty6) 中可以使用鼠标复制和粘贴，这就是这个服务的功能 | 开启 |
|    haldaemon    | 检测和支持 USB 设备。如果是服务器则可以关闭，个人机则建议开启 | 关闭 |
|      hidd       |    蓝牙鼠标、键盘等蓝牙设备检测。必须启动 bluetooth 服务     | 关闭 |
|      hplip      |           HP 打印机支持，如果没有 HP 打印机则关闭            | 关闭 |
|      httpd      |      apache 服务的守护进程。如果需要启动 apache，就开启      | 开启 |
|    ip6tables    |      IPv6 的防火墙。目前 IPv6 协议并没有使用，可以关闭       | 关闭 |
|    iptables     | 防火墙功能。Linux 中的防火墙是内核支持功能。这是服务器的主要防护手段，必须开启 | 开启 |
|      irda       | IrDA 提供红外线设备（笔记本电脑、PDA’s、手机、计算器等）间的通信支持。建议关闭 | 关闭 |
|   irqbalance    | 支持多核处理器，让 CPU 可以自动分配系统中断（IRQ)，提高系统性能。目前服务器多是多核 CPU，请开启 | 开启 |
|      isdn       | 使用 ISDN 设备连接网络。目前主流的联网方式是光纤接入和 ADSL，ISDN 己经非常少见，请关闭 | 关闭 |
|      kudzu      | 该服务可以在开机时进行硬件检测，并会调用相关的设置软件。建议关闭，仅在需要时开启 | 关闭 |
|  lvm2-monitor   | 该服务可以让系统支持LVM逻辑卷组，如果分区采用的是LVM方式，那么应该开启。建议开启 | 开启 |
|    mcstrans     |                 SELinux 的支持服务。建议开启                 | 开启 |
|    mdmonitor    | 该服务用来监测 Software RAID 或 LVM 的信息。不是必需服务，建议关闭 | 关闭 |
|      mdmpd      |    该服务用来监测 Multi-Path 设备。不是必需服务，建议关闭    | 关闭 |
|   messagebus    | 这是 Linux 的 IPC (Interprocess Communication，进程间通信）服务，用来在各个软件中交换信息。建议关闭 | 关闭 |
| microcode _ctl  | Intel 系列的 CPU 可以通过这个服务支持额外的微指令集。建议关闭 | 关闭 |
|     mysqld      |         MySQL 数据库服务器。如果需要就开启；否则关闭         | 开启 |
|      named      | DNS 服务的守护进程，用来进行域名解析。如果是 DNS 服务器则开启；否则关闭 | 关闭 |
|      netfs      | 该服务用于在系统启动时自动挂载网络中的共享文件空间，比如 NFS、Samba 等。 需要就开启，否则关闭 | 关闭 |
|     network     |      提供网络设罝功能。通过这个服务来管理网络，建议开启      | 开启 |
|       nfs       | NFS (Network File System) 服务，Linux 与 Linux 之间的文件共享服务。需要就开启，否则关闭 | 关闭 |
|     nfslock     | 在 Linux 中如果使用了 NFS 服务，那么，为了避免同一个文件被不同的用户同时编辑，所以有这个锁服务。有 NFS 时开启，否则关闭 | 关闭 |
|      ntpd       | 该服务可以通过互联网自动更新系统时间.使系统时间永远准确。需要则开启，但不是必需服务 | 关闭 |
|      pcscd      |                   智能卡检测服务，可以关闭                   | 关闭 |
|     portmap     | 用在远程过程调用 (RPC) 的服务，如果没有任何 RPC 服务，则可以关闭。主要是 NFS 和 NIS 服务需要 | 关闭 |
|     psacct      |             该守护进程支持几个监控进程活动的工具             | 关闭 |
|      rdisc      |                     客户端 ICMP 路由协议                     | 关闭 |
| readahead_early | 在系统开启的时候，先将某些进程加载入内存整理，可以加快启动速度 | 关闭 |
| readahead_later |                             同上                             | 关闭 |
|   restorecond   | 用于给 SELinux 监测和重新加载正确的文件上下文。如果开启 SELinux，则需要开启 | 关闭 |
|     rpcgssd     |         与 NFS 有关的客户端功能。如果没有 NFS 就关闭         | 关闭 |
|    rpcidmapd    |                             同上                             | 关闭 |
|      rsync      |                     远程数据备份守护进程                     | 关闭 |
|    sendmail     | sendmail 邮件服务的守护进程。如果有邮件服务就开启；否则关闭  | 关闭 |
| setroubleshoot  | 该服务用于将 SELinux 相关信息记录在日志 /var/log/messages 中。建议开启 | 开启 |
|     smartd      |             该服务用于自动检测硬盘状态。建议开启             | 开启 |
|       smb       | 网络服务 samba 的守护进程。可以让 Linux 和 Windows 之间共享数据。如果需要则开启 | 关闭 |
|      squid      |         代理服务的守护进程。如果需要则开启：否则关闭         | 关闭 |
|      sshd       | ssh 加密远程登录管理的服务。服务器的远程管理必须使用此服务，不要关闭 | 开启 |
|     syslog      |                        日志的守护进程                        | 开启 |
|     vsftpd      |   vsftp 服务的守护进程。如果需要 FTP 服务则开启；否则关闭    | 关闭 |
|       xfs       | 这是 X Window 的字体守护进程，为图形界面提供字体服务。如果不启动图形界面，就不用开启 | 关闭 |
|     xinetd      |      超级守护进程。如果有依赖 xinetd 的服务，就必须开启      | 开启 |
|     ypbind      |       为 NIS (网络信息系统）客户机激活 ypbind 服务进程       | 关闭 |
|  yum-updatesd   |                      yum 的在线升级服务                      | 关闭 |





## 影响系统性能的因素

### CPU

CPU 是操作系统稳定运行的根本，CPU 的速度与性能很大一部分决定了系统整体的性能，CPU 数量越多、主频越高，服务器性能也就相对越好。



### 内存

内存的大小也是影响 Linux 性能的一个重要的因素。内存太小，系统进程将被阻塞，应用也将变得缓慢，甚至失去响应；内存太大，会导致资源浪费。



### 磁盘读写能力

磁盘的 I/O 能力会直接影响应用程序的性能。比如说，在一个需要频繁读写的应用中，如果磁盘 I/O 性能得不到满足，就会导致应用的停滞。

可以使用 RAID 技术



### 网络带宽

低速的、不稳定的网络将导致网络应用程序的访问阻塞；而稳定、高速的带宽，可以保证应用程序在网络上畅通无阻地运行





## sar命令

sar命令可以全面地获取系统的 CPU、运行队列、磁盘读写（I/O）、分区（交换区）、内存、CPU 中断和网络等性能数据。

安装命令：

```sh
sudo apt install sysstat
```





命令：

```sh
sar [options] [-o filename] interval [count]
```



- -o filename：其中，filename 为文件名，此选项表示将命令结果以二进制格式存放在文件中；
- interval：表示采样间隔时间，该参数必须手动设置；
- count：表示采样次数，是可选参数，其默认值为 1；



| sar命令选项 |                             功能                             |
| :---------: | :----------------------------------------------------------: |
|     -A      |     显示系统所有资源设备（CPU、内存、磁盘）的运行状况。      |
|     -u      |          显示系统所有 CPU 在采样时间内的负载状态。           |
|     -P      |             显示当前系统中指定 CPU 的使用情况。              |
|     -d      |         显示系统所有硬盘设备在采样时间内的使用状态。         |
|     -r      |             显示系统内存在采样时间内的使用情况。             |
|     -b      |              显示缓冲区在采样时间内的使用情况。              |
|     -v      |        显示 inode 节点、文件和其他内核表的统计信息。         |
|     -n      | 显示网络运行状态，此选项后可跟 DEV（显示网络接口信息）、EDEV（显示网络错误的统计数据）、SOCK（显示套接字信息）和 FULL（等同于使用 DEV、EDEV和SOCK）等，有关更多的选项，可通过执行 man sar 命令查看。 |
|     -q      |      显示运行列表中的进程数、进程大小、系统平均负载等。      |
|     -R      |                 显示进程在采样时的活动情况。                 |
|     -y      |              显示终端设备在采样时间的活动情况。              |
|     -w      |             显示系统交换活动在采样时间内的状态。             |



```sh
mao@ubuntu:~/桌面$ sudo apt install sysstat
[sudo] mao 的密码： 
正在读取软件包列表... 完成
正在分析软件包的依赖关系树       
正在读取状态信息... 完成       
建议安装：
  isag
下列【新】软件包将被安装：
  sysstat
升级了 0 个软件包，新安装了 1 个软件包，要卸载 0 个软件包，有 360 个软件包未被升级。
需要下载 448 kB 的归档。
解压缩后会消耗 1,511 kB 的额外空间。
获取:1 http://cn.archive.ubuntu.com/ubuntu focal-updates/main amd64 sysstat amd64 12.2.0-2ubuntu0.1 [448 kB]
已下载 448 kB，耗时 23秒 (19.4 kB/s)                                                                            
正在预设定软件包 ...
正在选中未选择的软件包 sysstat。
(正在读取数据库 ... 系统当前共安装有 195538 个文件和目录。)
准备解压 .../sysstat_12.2.0-2ubuntu0.1_amd64.deb  ...
正在解压 sysstat (12.2.0-2ubuntu0.1) ...
正在设置 sysstat (12.2.0-2ubuntu0.1) ...

Creating config file /etc/default/sysstat with new version
update-alternatives: 使用 /usr/bin/sar.sysstat 来在自动模式中提供 /usr/bin/sar (sar)
Created symlink /etc/systemd/system/multi-user.target.wants/sysstat.service → /lib/systemd/system/sysstat.service.
正在处理用于 man-db (2.9.1-1) 的触发器 ...
正在处理用于 systemd (245.4-4ubuntu3.11) 的触发器 ...
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ sar --help
用法: sar [ 选项 ] [ <时间间隔> [ <次数> ] ]
主要选项和报告（报告名以方括号分隔）：
	-B	分页状况 [A_PAGE]
	-b	I/O 和传输速率信息状况 [A_IO]
	-d	块设备状况 [A_DISK]
	-F [ MOUNT ]
		文件系统统计信息 [A_FS]
	-H	巨大页面利用率 [A_HUGE]
	-I { <中断列表> | SUM | ALL }
		中断信息状况 [A_IRQ]
	-m { <关键字> [,...] | ALL }
		电源管理统计信息 [A_PWR_...]
		关键字：
		CPU	CPU 瞬时时钟频率
		FAN	风扇速度
\t\tFREQ\tCPU 平均时钟频率
		IN	输入电压
		TEMP	设备温度
\t\tUSB\t连接的 USB 设备
	-n { <关键字> [,...] | ALL }
		网络统计信息 [A_NET_...]
		关键字：
		DEV	网络接口
		EDEV	网络接口（错误）
		NFS	NFS 客户端
		NFSD	NFS 服务端
		SOCK	Sockets	(v4)
		IP	IP 流	(v4)
		EIP	IP 流	(v4)（错误）
		ICMP	ICMP 流	(v4)
		EICMP	ICMP 流	(v4)（错误）
		TCP	TCP 流	(v4)
		ETCP	TCP 流	(v4) (错误)
		UDP	UDP 流	(v4)
		SOCK6	Sockets	(v6)
		IP6	IP 流	(v6)
		EIP6	IP 流	(v6)（错误）
		ICMP6	ICMP 流	(v6)
		EICMP6	ICMP 流	(v6) (错误)
		UDP6	UDP 流	(v6)
		FC	Fibre channel HBAs
		SOFT	基于软件的网络处理
	-q	队列长度和平均负载统计信息 [A_QUEUE]
	-r [ ALL ]
		内存利用率信息 [A_MEMORY]
	-S	交换空间利用率信息 [A_MEMORY]
	-u [ ALL ]
		CPU 利用率信息 [A_CPU]
	-v	内核表统计信息 [A_KTABLES]
	-W	交换信息 [A_SWAP]
	-w	任务创建与系统切换信息 [A_PCSW]
	-y	TTY 设备信息 [A_SERIAL]
mao@ubuntu:~/桌面$ 
```



查看系统 CPU 的整理负载状况，每 3 秒统计一次，统计 5 次：

```sh
sar -u 3 5
```

```sh
mao@ubuntu:~/桌面$ sar -u 3 5
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时18分12秒     CPU     %user     %nice   %system   %iowait    %steal     %idle
03时18分15秒     all      0.02      0.00      0.04      0.00      0.00     99.94
03时18分18秒     all      0.06      0.00      0.00      0.00      0.00     99.94
03时18分21秒     all      0.02      0.00      0.02      0.00      0.00     99.96
03时18分24秒     all      0.02      2.44      0.33      0.00      0.00     97.20
03时18分27秒     all      0.02      4.79      1.42      0.00      0.00     93.76
平均时间:     all      0.03      1.45      0.36      0.00      0.00     98.16
mao@ubuntu:~/桌面$ 
```



- %user：用于表示用户模式下消耗的 CPU 时间的比例；
- %nice：通过 nice 改变了进程调度优先级的进程，在用户模式下消耗的 CPU 时间的比例；
- %system：系统模式下消耗的 CPU 时间的比例；
- %iowait：CPU 等待磁盘 I/O 导致空闲状态消耗的时间比例；
- %steal：利用 Xen 等操作系统虚拟化技术，等待其它虚拟 CPU 计算占用的时间比例；
- %idle：CPU 空闲时间比例。



查看系统磁盘的读写性能，每 2 秒统计一次，统计 5 次：

```sh
sar -d 2 5
```

```sh
mao@ubuntu:~/桌面$ sar -d 2 5
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时21分03秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时21分05秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev8-0      2.00      0.00     10.00      0.00      5.00      0.00      0.25      0.40
03时21分05秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分05秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

03时21分05秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时21分07秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev8-0      3.50      0.00     30.00      0.00      8.57      0.00      0.43      0.40
03时21分07秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分07秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

03时21分07秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时21分09秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev8-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分09秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

03时21分09秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时21分11秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev8-0      1.50      0.00      6.00      0.00      4.00      0.00      0.33      0.20
03时21分11秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分11秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

03时21分11秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时21分13秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev8-0      1.00      0.00     20.00      0.00     20.00      0.00      0.50      0.20
03时21分13秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时21分13秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

平均时间:       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
平均时间:    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev8-0      1.60      0.00     13.20      0.00      8.25      0.00      0.38      0.24
平均时间:    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
mao@ubuntu:~/桌面$ 
```



- tps：每秒从物理磁盘 I/O 的次数。注意，多个逻辑请求会被合并为一个 I/O 磁盘请求，一次传输的大小是不确定的；
- rd_sec/s：每秒读扇区的次数；
- wr_sec/s：每秒写扇区的次数；
- avgrq-sz：平均每次设备 I/O 操作的数据大小（扇区）；
- avgqu-sz：磁盘请求队列的平均长度；
- await：从请求磁盘操作到系统完成处理，每次请求的平均消耗时间，包括请求队列等待时间，单位是毫秒（1 秒=1000 毫秒）；
- svctm：系统处理每次请求的平均时间，不包括在请求队列中消耗的时间；
- %util：I/O 请求占 CPU 的百分比，比率越大，说明越饱和。



查看系统内存的情况，每 1 秒统计一次，统计 10 次：

```sh
mao@ubuntu:~/桌面$ sar -r 1 10
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时22分41秒 kbmemfree   kbavail kbmemused  %memused kbbuffers  kbcached  kbcommit   %commit  kbactive   kbinact   kbdirty
03时22分42秒   2143668   2742404    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分43秒   2143668   2742404    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分44秒   2143676   2742412    909416     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分45秒   2143660   2742396    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分46秒   2143660   2742396    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分47秒   2143660   2742396    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分48秒   2143660   2742396    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分49秒   2143660   2742396    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分50秒   2143660   2742396    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
03时22分51秒   2143660   2742396    909424     22.76     48096    709220   3267968     69.55    353660    905228         0
平均时间:   2143663   2742399    909423     22.76     48096    709220   3267968     69.55    353660    905228         0
mao@ubuntu:~/桌面$ 
```



- kbmemfree：表示空闲的物理内存的大小；
- kbmemeused：表示已使用的物理内存的大小；
- %memused：表示已使用内存占总内存大小的百分比；
- kbbuffers：表示缓冲区所使用的物理内存的大小；
- kbcached：表示告诉缓存所使用的物理内存的大小；
- kbcommit 和 %commit：分别表示当前系统中应用程序使用的内存大小和百分比；



```sh
mao@ubuntu:~/桌面$ sar -v 1 10
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时23分52秒 dentunusd   file-nr  inode-nr    pty-nr
03时23分53秒     40696      6944     73583         1
03时23分54秒     40696      6944     73583         1
03时23分55秒     40696      6944     73583         1
03时23分56秒     40696      6944     73583         1
03时23分57秒     40696      6944     73583         1
03时23分58秒     40696      6944     73583         1
03时23分59秒     40696      6944     73583         1
03时24分00秒     40696      6944     73583         1
03时24分01秒     40696      6944     73583         1
03时24分02秒     40696      6944     73583         1
平均时间:     40696      6944     73583         1
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ sar -b 1 10
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时24分29秒       tps      rtps      wtps      dtps   bread/s   bwrtn/s   bdscd/s
03时24分30秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分31秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分32秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分33秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分34秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分35秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分36秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分37秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分38秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时24分39秒      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:      0.00      0.00      0.00      0.00      0.00      0.00      0.00
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ sar -q 1 5
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时25分29秒   runq-sz  plist-sz   ldavg-1   ldavg-5  ldavg-15   blocked
03时25分30秒         0       635      0.00      0.02      0.04         0
03时25分31秒         0       635      0.00      0.02      0.04         0
03时25分32秒         0       635      0.00      0.02      0.04         0
03时25分33秒         0       635      0.00      0.02      0.04         0
03时25分34秒         0       635      0.00      0.02      0.04         0
平均时间:         0       635      0.00      0.02      0.04         0
mao@ubuntu:~/桌面$ 
```







## 查看CPU运行状态的方式

### vmstat命令

vmstat 命令可以显示关于系统各种资源之间相关性能的简要信息

```sh
vmstat 1 5
```



```sh
mao@ubuntu:~/桌面$ vmstat 1 5
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b 交换 空闲 缓冲 缓存   si   so    bi    bo   in   cs us sy id wa st
 0  0      0 2127952  48844 806760    0    0    37     7   33   41  0  0 100  0  0
 0  0      0 2127952  48844 806760    0    0     0     0  404  587  0  0 100  0  0
 0  0      0 2127960  48844 806760    0    0     0     0  176  283  0  0 100  0  0
 0  0      0 2127968  48844 806760    0    0     0     0  205  299  0  0 100  0  0
 0  0      0 2127968  48844 806760    0    0     0     0  740 1146  0  0 100  0  0
mao@ubuntu:~/桌面$ 
```



- r 列表示运行和等待 CPU 时间片的进程数，如果这个值长期大于系统 CPU 的个数，就说明 CPU 不足，需要增加 CPU。
- swpd 列表示切换到内存交换区的内存数量（以 kB 为单位）。如果 swpd 的值不为 0，或者比较大，而且 si、so 的值长期为 0，那么这种情况下一般不用担心，不用影响系统性能。
- cache 列表示缓存的内存数量，一般作为文件系统缓存，频繁访问的文件都会被缓存。如果缓存值较大，就说明缓存的文件数较多，如果此时 I/O 中 bi 比较小，就表明文件系统效率比较好。
- 一般情况下，si（数据由硬盘调入内存）、so（数据由内存调入硬盘） 的值都为 0，如果 si、so 的值长期不为 0，则表示系统内存不足，需要增加系统内存。
- 如果 bi+bo 的参考值为 1000 甚至超过 1000，而且 wa 值较大，则表示系统磁盘 I/O 有问题，应该考虑提高磁盘的读写性能。
- 输出结果中，CPU 项显示了 CPU 的使用状态，其中当 us 列的值较高时，说明用户进程消耗的 CPU 时间多，如果其长期大于 50%，就需要考虑优化程序或算法；sy 列的值较高时，说明内核消耗的 CPU 资源较多。通常情况下，us+sy 的参考值为 80%，如果其值大于 80%，则表明可能存在 CPU 资源不足的情况。



### sar命令

```sh
sar -u 2 5
```



```sh
mao@ubuntu:~/桌面$ sar -u 2 5
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时32分15秒     CPU     %user     %nice   %system   %iowait    %steal     %idle
03时32分17秒     all      0.06      0.00      0.09      0.00      0.00     99.84
03时32分19秒     all      0.00      0.00      0.00      0.00      0.00    100.00
03时32分21秒     all      0.00      0.00      0.00      0.00      0.00    100.00
03时32分23秒     all      0.00      0.00      0.00      0.00      0.00    100.00
03时32分25秒     all      0.03      0.00      0.00      0.00      0.00     99.97
平均时间:     all      0.02      0.00      0.02      0.00      0.00     99.96
mao@ubuntu:~/桌面$ 
```



单独查看系统中每个 CPU 的运行状态：

第一颗CPU：

```sh
sar -P 0 2 5
```

第10颗CPU：

```sh
sar -P 9 2 5
```



```sh
mao@ubuntu:~/桌面$ sar -P 0 2 5
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时33分26秒     CPU     %user     %nice   %system   %iowait    %steal     %idle
03时33分28秒       0      0.00      0.00      0.00      0.00      0.00    100.00
03时33分30秒       0      0.00      0.00      0.00      0.00      0.00    100.00
03时33分32秒       0      0.00      0.00      0.00      0.00      0.00    100.00
03时33分34秒       0      0.00      0.00      0.00      0.00      0.00    100.00
03时33分36秒       0      0.00      0.00      0.00      0.00      0.00    100.00
平均时间:       0      0.00      0.00      0.00      0.00      0.00    100.00
mao@ubuntu:~/桌面$ 
```

```sh
mao@ubuntu:~/桌面$ sar -P 9 2 5
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时35分15秒     CPU     %user     %nice   %system   %iowait    %steal     %idle
03时35分17秒       9      0.00      0.00      0.00      0.00      0.00    100.00
03时35分19秒       9      0.00      0.00      0.00      0.00      0.00    100.00
03时35分21秒       9      0.00      0.00      0.00      0.00      0.00    100.00
03时35分23秒       9      0.00      0.00      0.00      0.00      0.00    100.00
03时35分25秒       9      1.01      0.00      0.51      0.00      0.00     98.48
平均时间:       9      0.20      0.00      0.10      0.00      0.00     99.70
mao@ubuntu:~/桌面$ 
```





### iostat命令

iostat 命令主要用于统计磁盘 I/O 状态，但也能用来查看 CPU 的使用情况



```sh
iostat -c
```



```sh
mao@ubuntu:~/桌面$ iostat -c
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.11    0.05    0.16    0.02    0.00   99.65



mao@ubuntu:~/桌面$ iostat -c
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.11    0.05    0.16    0.02    0.00   99.65



mao@ubuntu:~/桌面$ 
```





### uptime命令

```sh
uptime
```



```sh
mao@ubuntu:~/桌面$ uptime
 03:37:36 up 26 min,  1 user,  load average: 0.11, 0.03, 0.02
mao@ubuntu:~/桌面$ uptime
 03:37:37 up 26 min,  1 user,  load average: 0.11, 0.03, 0.02
mao@ubuntu:~/桌面$ uptime
 03:37:38 up 26 min,  1 user,  load average: 0.11, 0.03, 0.02
mao@ubuntu:~/桌面$ 
```

各个数据所代表的含义依次是：系统当前时间、系统运行时长、当前登陆系统的用户数量、系统分别在 1 分钟、5 分钟和 15 分钟内的平均负载







## 查看内存使用情况的方式

### free命令



```sh
free -m
```



```sh
mao@ubuntu:~/桌面$ free -m
              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901         989        2076           2         835        2674
交换：         687           0         687
mao@ubuntu:~/桌面$ 
```



实时地监控内存的使用状况：

```sh
free -m -s 1
```



```sh
mao@ubuntu:~/桌面$ free -m -s 1
              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901         989        2076           2         835        2674
交换：         687           0         687

              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901         989        2076           2         835        2674
交换：         687           0         687

              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901         989        2076           2         835        2674
交换：         687           0         687

              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901         989        2076           2         835        2674
交换：         687           0         687

              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901         989        2076           2         835        2674
交换：         687           0         687

              总计         已用        空闲      共享    缓冲/缓存    可用
内存：        3901         989        2076           2         835        2674
交换：         687           0         687

^C
mao@ubuntu:~/桌面$ 
```





### watch 命令

```sh
watch -n 1 -d free
```



```sh
mao@ubuntu:~/桌面$ watch --help

用法：
 watch [options] command

选项：
  -b, --beep             如果命令以非零返回值退出的话则发出哔声
  -c, --color            interpret ANSI color and style sequences
  -d, --differences[=<permanent>]
                         highlight changes between updates
  -e, --errexit          exit if command has a non-zero exit
  -g, --chgexit          exit when output from command changes
  -n, --interval <secs>  seconds to wait between updates
  -p, --precise          尝试以精确的间隔运行命令
  -t, --no-title         关闭头部显示
  -x, --exec             将命令传给 exec 而非“sh -c”

 -h, --help     显示此帮助然后离开
 -v, --version  output version information and exit

mao@ubuntu:~/桌面$ 
```





```sh
mao@ubuntu:~/桌面$ watch -n 1 -d free
mao@ubuntu:~/桌面$ 

```

```sh
Every 1.0s: free                                                                 ubuntu: Thu Jul 14 03:42:22 2022

              总计         已用        空闲      共享    缓冲/缓存    可用
内存：     3995088     1015164     2123816        2236      856108     2736224
交换：      703976           0      703976




```





### vmstat命令

```sh
vmstat 2 3
```



```sh
mao@ubuntu:~/桌面$ vmstat 2 3
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b 交换 空闲 缓冲 缓存   si   so    bi    bo   in   cs us sy id wa st
 2  0      0 2087880  49040 807804    0    0    21     4   24   31  0  0 100  0  0
 1  0      0 2089724  49040 807816    0    0     0     0  764  741  5  1 94  0  0
 1  0      0 2088472  49040 807816    0    0     0     0  747  697  6  0 94  0  0
mao@ubuntu:~/桌面$ 
```





### sar命令

```sh
sar -r 1 5
```



```sh
mao@ubuntu:~/桌面$ sar -r 1 5
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时47分04秒 kbmemfree   kbavail kbmemused  %memused kbbuffers  kbcached  kbcommit   %commit  kbactive   kbinact   kbdirty
03时47分05秒   2088196   2701300    950132     23.78     49064    722552   3380096     71.93    371228    947536         0
03时47分06秒   2088204   2701308    950124     23.78     49064    722552   3380096     71.93    371228    947536         0
03时47分07秒   2088204   2701308    950124     23.78     49064    722552   3380096     71.93    371228    947536         0
03时47分08秒   2088204   2701308    950124     23.78     49064    722552   3380096     71.93    371228    947536         0
03时47分09秒   2088204   2701308    950124     23.78     49064    722552   3380016     71.93    371228    947536         0
平均时间:   2088202   2701306    950126     23.78     49064    722552   3380080     71.93    371228    947536         0
mao@ubuntu:~/桌面$ 
```







## 查看硬盘读写情况的方式

### sar命令

```sh
sar -d 1 3
```



```sh
mao@ubuntu:~/桌面$ sar -d 1 3
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

03时49分48秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时49分49秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev8-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分49秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

03时49分49秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时49分50秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev8-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分50秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

03时49分50秒       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
03时49分51秒    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev8-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
03时49分51秒   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00

平均时间:       DEV       tps     rkB/s     wkB/s     dkB/s   areq-sz    aqu-sz     await     %util
平均时间:    dev7-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-1      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-2      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-3      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-4      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-5      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-6      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-7      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev11-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev8-0      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-8      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:    dev7-9      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-10      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-11      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-12      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-13      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-14      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
平均时间:   dev7-15      0.00      0.00      0.00      0.00      0.00      0.00      0.00      0.00
mao@ubuntu:~/桌面$ 
```





### iostat命令

```sh
iostat -d 1 3
```



```sh
mao@ubuntu:~/桌面$ iostat -d 1 3
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

Device             tps    kB_read/s    kB_wrtn/s    kB_dscd/s    kB_read    kB_wrtn    kB_dscd
loop0             0.01         0.01         0.00         0.00         17          0          0
loop1             0.02         0.14         0.00         0.00        347          0          0
loop10            0.02         0.14         0.00         0.00        347          0          0
loop11            0.02         0.45         0.00         0.00       1084          0          0
loop12            0.03         0.44         0.00         0.00       1067          0          0
loop13            0.02         0.15         0.00         0.00        359          0          0
loop14            0.02         0.14         0.00         0.00        348          0          0
loop15            0.00         0.01         0.00         0.00         18          0          0
loop2             0.02         0.15         0.00         0.00        350          0          0
loop3             0.02         0.15         0.00         0.00        365          0          0
loop4             0.02         0.44         0.00         0.00       1056          0          0
loop5             0.03         0.45         0.00         0.00       1083          0          0
loop6             0.02         0.45         0.00         0.00       1081          0          0
loop7             0.02         0.45         0.00         0.00       1093          0          0
loop8             0.02         0.15         0.00         0.00        358          0          0
loop9             0.21         7.04         0.00         0.00      16973          0          0
sda               9.08       287.35        58.63         0.00     692474     141293          0
scd0              0.00         0.00         0.00         0.00          2          0          0


Device             tps    kB_read/s    kB_wrtn/s    kB_dscd/s    kB_read    kB_wrtn    kB_dscd
loop0             0.00         0.00         0.00         0.00          0          0          0
loop1             0.00         0.00         0.00         0.00          0          0          0
loop10            0.00         0.00         0.00         0.00          0          0          0
loop11            0.00         0.00         0.00         0.00          0          0          0
loop12            0.00         0.00         0.00         0.00          0          0          0
loop13            0.00         0.00         0.00         0.00          0          0          0
loop14            0.00         0.00         0.00         0.00          0          0          0
loop15            0.00         0.00         0.00         0.00          0          0          0
loop2             0.00         0.00         0.00         0.00          0          0          0
loop3             0.00         0.00         0.00         0.00          0          0          0
loop4             0.00         0.00         0.00         0.00          0          0          0
loop5             0.00         0.00         0.00         0.00          0          0          0
loop6             0.00         0.00         0.00         0.00          0          0          0
loop7             0.00         0.00         0.00         0.00          0          0          0
loop8             0.00         0.00         0.00         0.00          0          0          0
loop9             0.00         0.00         0.00         0.00          0          0          0
sda               1.00         0.00        72.00         0.00          0         72          0
scd0              0.00         0.00         0.00         0.00          0          0          0


Device             tps    kB_read/s    kB_wrtn/s    kB_dscd/s    kB_read    kB_wrtn    kB_dscd
loop0             0.00         0.00         0.00         0.00          0          0          0
loop1             0.00         0.00         0.00         0.00          0          0          0
loop10            0.00         0.00         0.00         0.00          0          0          0
loop11            0.00         0.00         0.00         0.00          0          0          0
loop12            0.00         0.00         0.00         0.00          0          0          0
loop13            0.00         0.00         0.00         0.00          0          0          0
loop14            0.00         0.00         0.00         0.00          0          0          0
loop15            0.00         0.00         0.00         0.00          0          0          0
loop2             0.00         0.00         0.00         0.00          0          0          0
loop3             0.00         0.00         0.00         0.00          0          0          0
loop4             0.00         0.00         0.00         0.00          0          0          0
loop5             0.00         0.00         0.00         0.00          0          0          0
loop6             0.00         0.00         0.00         0.00          0          0          0
loop7             0.00         0.00         0.00         0.00          0          0          0
loop8             0.00         0.00         0.00         0.00          0          0          0
loop9             0.00         0.00         0.00         0.00          0          0          0
sda               0.00         0.00         0.00         0.00          0          0          0
scd0              0.00         0.00         0.00         0.00          0          0          0


mao@ubuntu:~/桌面$ 
```



iostat 命令还提供了统计指定硬盘 I/O 状况的方法：

```sh
iostat -x /dev/sda 1 3
```



```sh
mao@ubuntu:~/桌面$ iostat -x /dev/sda 1 3
Linux 5.11.0-38-generic (ubuntu) 	2022年07月14日 	_x86_64_	(16 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.24    0.36    0.24    0.01    0.00   99.15

Device            r/s     rkB/s   rrqm/s  %rrqm r_await rareq-sz     w/s     wkB/s   wrqm/s  %wrqm w_await wareq-sz     d/s     dkB/s   drqm/s  %drqm d_await dareq-sz  aqu-sz  %util
sda              6.63    263.16     2.63  28.44    0.69    39.68    1.78     72.47     3.01  62.87    1.01    40.79    0.00      0.00     0.00   0.00    0.00     0.00    0.01   0.59


avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.00    0.00    0.00    0.00    0.00  100.00

Device            r/s     rkB/s   rrqm/s  %rrqm r_await rareq-sz     w/s     wkB/s   wrqm/s  %wrqm w_await wareq-sz     d/s     dkB/s   drqm/s  %drqm d_await dareq-sz  aqu-sz  %util
sda              0.00      0.00     0.00   0.00    0.00     0.00    1.00   1224.00     1.00  50.00    2.00  1224.00    0.00      0.00     0.00   0.00    0.00     0.00    0.00   0.40


avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.13    0.00    0.06    0.00    0.00   99.81

Device            r/s     rkB/s   rrqm/s  %rrqm r_await rareq-sz     w/s     wkB/s   wrqm/s  %wrqm w_await wareq-sz     d/s     dkB/s   drqm/s  %drqm d_await dareq-sz  aqu-sz  %util
sda              0.00      0.00     0.00   0.00    0.00     0.00    0.00      0.00     0.00   0.00    0.00     0.00    0.00      0.00     0.00   0.00    0.00     0.00    0.00   0.00


mao@ubuntu:~/桌面$ 

```



- rrqm/s：表示每秒被合并的读操作数目（文件系统会对读取同一 block 块的请求进行合并）
- wrqm/s：表示每秒被合并的写操作数目；
- r/s：表示每秒完成读 I/O 设备的次数；
- w/s：表示每秒完成写 I/O 设备的次数；
- rsec/s：表示每秒读取的扇区数；
- wsec/s：表示每秒写入的扇区数；





### vmstat命令

```sh
vmstat -d 1 3
```



```sh
mao@ubuntu:~/桌面$ vmstat -d 1 3
disk- ------------reads------------ ------------writes----------- -----IO------
      总用量 merged  扇区      ms 总用量 merged  扇区      ms    cur    sec
loop0     14      0      34       4      0      0       0       0      0      0
loop1     43      0     694      38      0      0       0       0      0      0
loop2     45      0     700      37      0      0       0       0      0      0
loop3     50      0     730      33      0      0       0       0      0      0
loop4     57      0    2112      85      0      0       0       0      0      0
loop5     61      0    2166      79      0      0       0       0      0      0
loop6     54      0    2162      75      0      0       0       0      0      0
loop7     59      0    2186      77      0      0       0       0      0      0
sr0       11      0       5       2      0      0       0       0      0      0
sda    17456   6936 1385468   12064   4711   7950  391242    4763      0     15
loop8     48      0     716      34      0      0       0       0      0      0
loop9    515      0   33946     490      0      0       0       0      0      2
loop10     43      0     694      29      0      0       0       0      0      0
loop11     52      0    2168      41      0      0       0       0      0      0
loop12     62      0    2134      78      0      0       0       0      0      0
loop13     48      0     718      40      0      0       0       0      0      0
loop14     43      0     696      34      0      0       0       0      0      0
loop15     12      0      36       1      0      0       0       0      0      0
loop0     14      0      34       4      0      0       0       0      0      0
loop1     43      0     694      38      0      0       0       0      0      0
loop2     45      0     700      37      0      0       0       0      0      0
loop3     50      0     730      33      0      0       0       0      0      0
loop4     57      0    2112      85      0      0       0       0      0      0
loop5     61      0    2166      79      0      0       0       0      0      0
loop6     54      0    2162      75      0      0       0       0      0      0
loop7     59      0    2186      77      0      0       0       0      0      0
sr0       11      0       5       2      0      0       0       0      0      0
sda    17456   6936 1385468   12064   4716   7950  394730    4769      0     15
loop8     48      0     716      34      0      0       0       0      0      0
loop9    515      0   33946     490      0      0       0       0      0      2
loop10     43      0     694      29      0      0       0       0      0      0
loop11     52      0    2168      41      0      0       0       0      0      0
loop12     62      0    2134      78      0      0       0       0      0      0
loop13     48      0     718      40      0      0       0       0      0      0
loop14     43      0     696      34      0      0       0       0      0      0
disk- ------------reads------------ ------------writes----------- -----IO------
      总用量 merged  扇区      ms 总用量 merged  扇区      ms    cur    sec
loop15     12      0      36       1      0      0       0       0      0      0
loop0     14      0      34       4      0      0       0       0      0      0
loop1     43      0     694      38      0      0       0       0      0      0
loop2     45      0     700      37      0      0       0       0      0      0
loop3     50      0     730      33      0      0       0       0      0      0
loop4     57      0    2112      85      0      0       0       0      0      0
loop5     61      0    2166      79      0      0       0       0      0      0
loop6     54      0    2162      75      0      0       0       0      0      0
loop7     59      0    2186      77      0      0       0       0      0      0
sr0       11      0       5       2      0      0       0       0      0      0
sda    17456   6936 1385468   12064   4723   7961  395146    4772      0     15
loop8     48      0     716      34      0      0       0       0      0      0
loop9    515      0   33946     490      0      0       0       0      0      2
loop10     43      0     694      29      0      0       0       0      0      0
loop11     52      0    2168      41      0      0       0       0      0      0
loop12     62      0    2134      78      0      0       0       0      0      0
loop13     48      0     718      40      0      0       0       0      0      0
loop14     43      0     696      34      0      0       0       0      0      0
loop15     12      0      36       1      0      0       0       0      0      0
mao@ubuntu:~/桌面$ 
```











# 系统日志管理

## rsyslogd服务

在 CentOS 6.x 中，日志服务已经由 rsyslogd 取代了原先的 syslogd。Red Hat 公司认为 syslogd 已经不能满足工作中的需求，rsyslogd 相比 syslogd 具有一些新的特点：

- 基于TCP网络协议传输日志信息。
- 更安全的网络传输方式。
- 有日志信息的即时分析框架。
- 后台数据库。
- 在配置文件中可以写简单的逻辑判断。
- 与syslog配置文件相兼容。



rsyslogd 日志服务更加先进，功能更多。



系统中的绝大多数日志文件是由 rsyslogd 服务来统一管理的，只要各个进程将信息给予这个服务，它就会自动地把日志按照特定的格式记录到不同的日志文件中。也就是说，采用 rsyslogd 服务管理的日志文件，它们的格式应该是统一的。



查询 rsyslogd 服务的自启动状态：

```sh
ps aux | grep "rsyslog" | grep -v "grep"
```

```sh
chkconfig --list | grep rsyslog
```



```sh
mao@ubuntu:~/桌面$ ps aux | grep "rsyslog" | grep -v "grep"
syslog       933  0.0  0.1 224356  4436 ?        Ssl  03:11   0:00 /usr/sbin/rsyslogd -n -iNONE
mao@ubuntu:~/桌面$ 
```





## 日志文件及其功能



|     日志文件      |                            说 明                             |
| :---------------: | :----------------------------------------------------------: |
|   /var/log/cron   |                 记录与系统定时任务相关的曰志                 |
|  /var/log/cups/   |                      记录打印信息的曰志                      |
|  /var/log/dmesg   | 记录了系统在开机时内核自检的日志。也可以使用dmesg命令直接查看内核自检信息 |
|   /var/log/btmp   | 记录错误登陆的日志。这个文件是二进制文件，不能直接用Vi查看，而要使用lastb命令查看。命令如下：lastb |
| /var/log/lasllog  | 记录系统中所有用户最后一次的登录时间的曰志。这个文件也是二进制文件.不能直接用Vi 查看。而要使用lastlog命令查看 |
|  /var/log/mailog  |                      记录邮件信息的曰志                      |
| /var/log/messages | 它是核心系统日志文件，其中包含了系统启动时的引导信息，以及系统运行时的其他状态消息。I/O 错误、网络错误和其他系统错误都会记录到此文件中。其他信息，比如某个人的身份切换为 root，已经用户自定义安装软件的日志，也会在这里列出。 |
|  /var/log/secure  | 记录验证和授权方面的倍息，只要涉及账户和密码的程序都会记录，比如系统的登录、ssh的登录、su切换用户，sudo授权，甚至添加用户和修改用户密码都会记录在这个日志文件中 |
|   /var/log/wtmp   | 永久记录所有用户的登陆、注销信息，同时记录系统的后动、重启、关机事件。同样，这个文件也是二进制文件。不能直接用Vi查看，而要使用last命令查看 |
|   /var/tun/ulmp   | 记录当前已经登录的用户的信息。这个文件会随着用户的登录和注销而不断变化，只记录当前登录用户的信息。同样，这个文件不能直接用Vi查看，而要使用w、who、users等命令查看 |

 

|    日志文件     |                说明                 |
| :-------------: | :---------------------------------: |
| /var/log/httpd/ | RPM包安装的apache取务的默认日志目录 |
| /var/log/mail/  |  RPM包安装的邮件服务的额外日志因录  |
| /var/log/samba/ |   RPM色安装的Samba服务的日志目录    |
| /var/log/sssd/  |        守护进程安全服务目录         |





```sh
mao@ubuntu:~/桌面$ ls -l /var/log/cups/
总用量 40
-rw-r----- 1 root adm 765 7月  14 04:09 access_log
-rw-r----- 1 root adm 765 7月  12 22:37 access_log.1
-rw-r----- 1 root adm 182 7月  11 22:58 access_log.2.gz
-rw-r----- 1 root adm 167 7月  10 05:12 access_log.3.gz
-rw-r----- 1 root adm 232 7月  10 04:15 access_log.4.gz
-rw-r----- 1 root adm 182 7月   8 06:46 access_log.5.gz
-rw-r----- 1 root adm 221 7月   7 07:01 access_log.6.gz
-rw-r----- 1 root adm 278 7月   6 23:09 access_log.7.gz
-rw-r----- 1 root adm   0 7月   6 04:43 error_log
-rw-r----- 1 root adm  91 7月   5 06:40 error_log.1
-rw-r----- 1 root adm 118 10月 23  2021 error_log.2.gz
mao@ubuntu:~/桌面$ cd /var/log/cups/
mao@ubuntu:/var/log/cups$ cat -n error_log.1
     1	W [05/Jul/2022:06:40:23 -0700] Notifier for subscription 91 (dbus://) went away, retrying!
mao@ubuntu:/var/log/cups$ cat -n access_log
     1	localhost - - [14/Jul/2022:03:11:06 -0700] "POST / HTTP/1.1" 200 349 Create-Printer-Subscriptions successful-ok
     2	localhost - - [14/Jul/2022:03:11:06 -0700] "POST / HTTP/1.1" 200 176 Create-Printer-Subscriptions successful-ok
     3	localhost - - [14/Jul/2022:03:11:10 -0700] "POST / HTTP/1.1" 200 359 Create-Printer-Subscriptions successful-ok
     4	localhost - - [14/Jul/2022:03:11:23 -0700] "POST / HTTP/1.1" 200 359 Create-Printer-Subscriptions successful-ok
     5	localhost - - [14/Jul/2022:03:11:25 -0700] "POST / HTTP/1.1" 200 151 Cancel-Subscription successful-ok
     6	localhost - - [14/Jul/2022:03:11:25 -0700] "POST / HTTP/1.1" 200 151 Cancel-Subscription client-error-not-found
     7	localhost - - [14/Jul/2022:04:09:42 -0700] "POST / HTTP/1.1" 200 182 Renew-Subscription successful-ok
mao@ubuntu:/var/log/cups$ 
```



```sh
mao@ubuntu:/var/log/cups$ cat -n /var/log/dmesg
     1	[    0.000000] kernel: Linux version 5.11.0-38-generic (buildd@lgw01-amd64-041) (gcc (Ubuntu 9.3.0-17ubuntu1~20.04) 9.3.0, GNU ld (GNU Binutils for Ubuntu) 2.34) #42~20.04.1-Ubuntu SMP Tue Sep 28 20:41:07 UTC 2021 (Ubuntu 5.11.0-38.42~20.04.1-generic 5.11.22)
     2	[    0.000000] kernel: Command line: BOOT_IMAGE=/boot/vmlinuz-5.11.0-38-generic root=UUID=f016fec7-baa2-4d84-99bb-4b8bde2ff82c ro find_preseed=/preseed.cfg auto noprompt priority=critical locale=en_US quiet
     3	[    0.000000] kernel: KERNEL supported cpus:
     4	[    0.000000] kernel:   Intel GenuineIntel
     5	[    0.000000] kernel:   AMD AuthenticAMD
     6	[    0.000000] kernel:   Hygon HygonGenuine
     7	[    0.000000] kernel:   Centaur CentaurHauls
     8	[    0.000000] kernel:   zhaoxin   Shanghai  
     9	[    0.000000] kernel: [Firmware Bug]: TSC doesn't count with P0 frequency!
    10	[    0.000000] kernel: x86/fpu: Supporting XSAVE feature 0x001: 'x87 floating point registers'
    11	[    0.000000] kernel: x86/fpu: Supporting XSAVE feature 0x002: 'SSE registers'
    12	[    0.000000] kernel: x86/fpu: Supporting XSAVE feature 0x004: 'AVX registers'
    13	[    0.000000] kernel: x86/fpu: xstate_offset[2]:  576, xstate_sizes[2]:  256
    14	[    0.000000] kernel: x86/fpu: Enabled xstate features 0x7, context size is 832 bytes, using 'compacted' format.
    15	[    0.000000] kernel: BIOS-provided physical RAM map:
    16	[    0.000000] kernel: BIOS-e820: [mem 0x0000000000000000-0x000000000009e7ff] usable
    17	[    0.000000] kernel: BIOS-e820: [mem 0x000000000009e800-0x000000000009ffff] reserved
    18	[    0.000000] kernel: BIOS-e820: [mem 0x00000000000dc000-0x00000000000fffff] reserved
    19	[    0.000000] kernel: BIOS-e820: [mem 0x0000000000100000-0x00000000bfecffff] usable
    20	[    0.000000] kernel: BIOS-e820: [mem 0x00000000bfed0000-0x00000000bfefefff] ACPI data
    21	[    0.000000] kernel: BIOS-e820: [mem 0x00000000bfeff000-0x00000000bfefffff] ACPI NVS
    22	[    0.000000] kernel: BIOS-e820: [mem 0x00000000bff00000-0x00000000bfffffff] usable
    23	[    0.000000] kernel: BIOS-e820: [mem 0x00000000f0000000-0x00000000f7ffffff] reserved
    24	[    0.000000] kernel: BIOS-e820: [mem 0x00000000fec00000-0x00000000fec0ffff] reserved
    25	[    0.000000] kernel: BIOS-e820: [mem 0x00000000fee00000-0x00000000fee00fff] reserved
    26	[    0.000000] kernel: BIOS-e820: [mem 0x00000000fffe0000-0x00000000ffffffff] reserved
    27	[    0.000000] kernel: BIOS-e820: [mem 0x0000000100000000-0x000000013fffffff] usable
    28	[    0.000000] kernel: NX (Execute Disable) protection: active
    29	[    0.000000] kernel: SMBIOS 2.7 present.
    30	[    0.000000] kernel: DMI: VMware, Inc. VMware Virtual Platform/440BX Desktop Reference Platform, BIOS 6.00 07/22/2020
    31	[    0.000000] kernel: vmware: hypercall mode: 0x01
    32	[    0.000000] kernel: Hypervisor detected: VMware
    33	[    0.000000] kernel: vmware: TSC freq read from hypervisor : 3800.048 MHz
    34	[    0.000000] kernel: vmware: Host bus clock speed read from hypervisor : 66000000 Hz
    35	[    0.000000] kernel: vmware: using clock offset of 34315765264 ns
    36	[    0.000025] kernel: tsc: Detected 3800.048 MHz processor
    37	[    0.001937] kernel: e820: update [mem 0x00000000-0x00000fff] usable ==> reserved
    38	[    0.001942] kernel: e820: remove [mem 0x000a0000-0x000fffff] usable
    39	[    0.001947] kernel: last_pfn = 0x140000 max_arch_pfn = 0x400000000
    40	[    0.002027] kernel: MTRR default type: uncachable
    41	[    0.002030] kernel: MTRR fixed ranges enabled:
    42	[    0.002031] kernel:   00000-9FFFF write-back
    43	[    0.002032] kernel:   A0000-BFFFF uncachable
    44	[    0.002033] kernel:   C0000-CFFFF write-protect
    45	[    0.002034] kernel:   D0000-EFFFF uncachable
    46	[    0.002035] kernel:   F0000-FFFFF write-protect
    47	[    0.002036] kernel: MTRR variable ranges enabled:
    48	[    0.002037] kernel:   0 base 000000000000 mask 1FE000000000 write-back
    49	[    0.002039] kernel:   1 base 0000C0000000 mask 1FFFC0000000 uncachable
    50	[    0.002041] kernel:   2 disabled
    51	[    0.002042] kernel:   3 disabled
    52	[    0.002042] kernel:   4 disabled
    53	[    0.002043] kernel:   5 disabled
    54	[    0.002043] kernel:   6 disabled
    55	[    0.002044] kernel:   7 disabled
    56	[    0.002056] kernel: x86/PAT: Configuration [0-7]: WB  WC  UC- UC  WB  WP  UC- WT  
    57	[    0.002071] kernel: total RAM covered: 130048M
    58	[    0.002450] kernel: Found optimal setting for mtrr clean up
    59	[    0.002451] kernel:  gran_size: 64K         chunk_size: 64K         num_reg: 7          lose cover RAM: 0G
    60	[    0.002518] kernel: e820: update [mem 0xc0000000-0xffffffff] usable ==> reserved
    61	[    0.002526] kernel: last_pfn = 0xc0000 max_arch_pfn = 0x400000000
    62	[    0.004960] kernel: found SMP MP-table at [mem 0x000f6a70-0x000f6a7f]
    63	[    0.050847] kernel: check: Scanning 1 areas for low memory corruption
    64	[    0.050912] kernel: Using GB pages for direct mapping
    65	[    0.051104] kernel: RAMDISK: [mem 0x31abf000-0x34d56fff]
    66	[    0.051111] kernel: ACPI: Early table checksum verification disabled
    67	[    0.051115] kernel: ACPI: RSDP 0x00000000000F6A00 000024 (v02 PTLTD )
    68	[    0.051120] kernel: ACPI: XSDT 0x00000000BFEDC633 00005C (v01 INTEL  440BX    06040000 VMW  01324272)
    69	[    0.051126] kernel: ACPI: FACP 0x00000000BFEFEE73 0000F4 (v04 INTEL  440BX    06040000 PTL  000F4240)
    70	[    0.051131] kernel: ACPI: DSDT 0x00000000BFEDD9E8 02148B (v01 PTLTD  Custom   06040000 MSFT 03000001)
    71	[    0.051154] kernel: ACPI: FACS 0x00000000BFEFFFC0 000040
    72	[    0.051159] kernel: ACPI: FACS 0x00000000BFEFFFC0 000040
    73	[    0.051162] kernel: ACPI: BOOT 0x00000000BFEDD9C0 000028 (v01 PTLTD  $SBFTBL$ 06040000  LTP 00000001)
    74	[    0.051165] kernel: ACPI: APIC 0x00000000BFEDD27E 000742 (v01 PTLTD  ? APIC   06040000  LTP 00000000)
    75	[    0.051168] kernel: ACPI: MCFG 0x00000000BFEDD242 00003C (v01 PTLTD  $PCITBL$ 06040000  LTP 00000001)
    76	[    0.051171] kernel: ACPI: SRAT 0x00000000BFEDC72F 0008D0 (v02 VMWARE MEMPLUG  06040000 VMW  00000001)
    77	[    0.051174] kernel: ACPI: HPET 0x00000000BFEDC6F7 000038 (v01 VMWARE VMW HPET 06040000 VMW  00000001)
    78	[    0.051177] kernel: ACPI: WAET 0x00000000BFEDC6CF 000028 (v01 VMWARE VMW WAET 06040000 VMW  00000001)
    79	[    0.051180] kernel: ACPI: Reserving FACP table memory at [mem 0xbfefee73-0xbfefef66]
    80	[    0.051182] kernel: ACPI: Reserving DSDT table memory at [mem 0xbfedd9e8-0xbfefee72]
    81	[    0.051183] kernel: ACPI: Reserving FACS table memory at [mem 0xbfefffc0-0xbfefffff]
    82	[    0.051184] kernel: ACPI: Reserving FACS table memory at [mem 0xbfefffc0-0xbfefffff]
    83	[    0.051185] kernel: ACPI: Reserving BOOT table memory at [mem 0xbfedd9c0-0xbfedd9e7]
    84	[    0.051186] kernel: ACPI: Reserving APIC table memory at [mem 0xbfedd27e-0xbfedd9bf]
    85	[    0.051187] kernel: ACPI: Reserving MCFG table memory at [mem 0xbfedd242-0xbfedd27d]
    86	[    0.051188] kernel: ACPI: Reserving SRAT table memory at [mem 0xbfedc72f-0xbfedcffe]
    87	[    0.051188] kernel: ACPI: Reserving HPET table memory at [mem 0xbfedc6f7-0xbfedc72e]
    88	[    0.051189] kernel: ACPI: Reserving WAET table memory at [mem 0xbfedc6cf-0xbfedc6f6]
    89	[    0.051232] kernel: ACPI: Local APIC address 0xfee00000
    90	[    0.051314] kernel: SRAT: PXM 0 -> APIC 0x00 -> Node 0
...
...
...
   216	[    0.051408] kernel: SRAT: PXM 0 -> APIC 0x7e -> Node 0
   217	[    0.051408] kernel: SRAT: PXM 0 -> APIC 0x7f -> Node 0
   218	[    0.051411] kernel: ACPI: SRAT: Node 0 PXM 0 [mem 0x00000000-0x0009ffff]
   219	[    0.051413] kernel: ACPI: SRAT: Node 0 PXM 0 [mem 0x00100000-0xbfffffff]
   220	[    0.051414] kernel: ACPI: SRAT: Node 0 PXM 0 [mem 0x100000000-0x13fffffff]
   221	[    0.051416] kernel: ACPI: SRAT: Node 0 PXM 0 [mem 0x140000000-0x103fffffff] hotplug
   222	[    0.051418] kernel: NUMA: Node 0 [mem 0x00000000-0x0009ffff] + [mem 0x00100000-0xbfffffff] -> [mem 0x00000000-0xbfffffff]
   223	[    0.051420] kernel: NUMA: Node 0 [mem 0x00000000-0xbfffffff] + [mem 0x100000000-0x13fffffff] -> [mem 0x00000000-0x13fffffff]
   224	[    0.051428] kernel: NODE_DATA(0) allocated [mem 0x13ffd6000-0x13fffffff]
   225	[    0.052668] kernel: Zone ranges:
   226	[    0.052670] kernel:   DMA      [mem 0x0000000000001000-0x0000000000ffffff]
   227	[    0.052673] kernel:   DMA32    [mem 0x0000000001000000-0x00000000ffffffff]
   228	[    0.052674] kernel:   Normal   [mem 0x0000000100000000-0x000000013fffffff]
   229	[    0.052676] kernel:   Device   empty
   230	[    0.052677] kernel: Movable zone start for each node
   231	[    0.052679] kernel: Early memory node ranges
   232	[    0.052680] kernel:   node   0: [mem 0x0000000000001000-0x000000000009dfff]
   233	[    0.052681] kernel:   node   0: [mem 0x0000000000100000-0x00000000bfecffff]
   234	[    0.052682] kernel:   node   0: [mem 0x00000000bff00000-0x00000000bfffffff]
   235	[    0.052683] kernel:   node   0: [mem 0x0000000100000000-0x000000013fffffff]
   236	[    0.052685] kernel: Initmem setup node 0 [mem 0x0000000000001000-0x000000013fffffff]
   237	[    0.052686] kernel: On node 0 totalpages: 1048429
   238	[    0.052687] kernel:   DMA zone: 64 pages used for memmap
   239	[    0.052688] kernel:   DMA zone: 21 pages reserved
   240	[    0.052689] kernel:   DMA zone: 3997 pages, LIFO batch:0
   241	[    0.052690] kernel:   DMA32 zone: 12224 pages used for memmap
   242	[    0.052691] kernel:   DMA32 zone: 782288 pages, LIFO batch:63
   243	[    0.052692] kernel:   Normal zone: 4096 pages used for memmap
   244	[    0.052693] kernel:   Normal zone: 262144 pages, LIFO batch:63
   245	[    0.052772] kernel: On node 0, zone DMA: 1 pages in unavailable ranges
   246	[    0.053984] kernel: On node 0, zone DMA: 98 pages in unavailable ranges
   247	[    0.283709] kernel: On node 0, zone DMA32: 48 pages in unavailable ranges
   248	[    0.379059] kernel: ACPI: PM-Timer IO Port: 0x1008
   249	[    0.379064] kernel: ACPI: Local APIC address 0xfee00000
   250	[    0.379080] kernel: ACPI: LAPIC_NMI (acpi_id[0x00] high edge lint[0x1])
...
...
...
   369	[    0.379177] kernel: ACPI: LAPIC_NMI (acpi_id[0x77] high edge lint[0x1])
   370	[    0.379177] kernel: ACPI: LAPIC_NMI (acpi_id[0x78] high edge lint[0x1])
   371	[    0.379178] kernel: ACPI: LAPIC_NMI (acpi_id[0x79] high edge lint[0x1])
   372	[    0.379179] kernel: ACPI: LAPIC_NMI (acpi_id[0x7a] high edge lint[0x1])
   373	[    0.379180] kernel: ACPI: LAPIC_NMI (acpi_id[0x7b] high edge lint[0x1])
   374	[    0.379181] kernel: ACPI: LAPIC_NMI (acpi_id[0x7c] high edge lint[0x1])
   375	[    0.379181] kernel: ACPI: LAPIC_NMI (acpi_id[0x7d] high edge lint[0x1])
   376	[    0.379182] kernel: ACPI: LAPIC_NMI (acpi_id[0x7e] high edge lint[0x1])
   377	[    0.379183] kernel: ACPI: LAPIC_NMI (acpi_id[0x7f] high edge lint[0x1])
   378	[    0.379359] kernel: IOAPIC[0]: apic_id 128, version 32, address 0xfec00000, GSI 0-23
   379	[    0.379366] kernel: ACPI: INT_SRC_OVR (bus 0 bus_irq 0 global_irq 2 high edge)
   380	[    0.379370] kernel: ACPI: IRQ0 used by override.
   381	[    0.379371] kernel: ACPI: IRQ9 used by override.
   382	[    0.379373] kernel: Using ACPI (MADT) for SMP configuration information
   383	[    0.379375] kernel: ACPI: HPET id: 0x8086af01 base: 0xfed00000
   384	[    0.379418] kernel: smpboot: Allowing 128 CPUs, 112 hotplug CPUs
   385	[    0.379435] kernel: PM: hibernation: Registered nosave memory: [mem 0x00000000-0x00000fff]
   386	[    0.379437] kernel: PM: hibernation: Registered nosave memory: [mem 0x0009e000-0x0009efff]
   387	[    0.379438] kernel: PM: hibernation: Registered nosave memory: [mem 0x0009f000-0x0009ffff]
   388	[    0.379439] kernel: PM: hibernation: Registered nosave memory: [mem 0x000a0000-0x000dbfff]
   389	[    0.379439] kernel: PM: hibernation: Registered nosave memory: [mem 0x000dc000-0x000fffff]
   390	[    0.379441] kernel: PM: hibernation: Registered nosave memory: [mem 0xbfed0000-0xbfefefff]
   391	[    0.379442] kernel: PM: hibernation: Registered nosave memory: [mem 0xbfeff000-0xbfefffff]
   392	[    0.379500] kernel: PM: hibernation: Registered nosave memory: [mem 0xc0000000-0xefffffff]
   393	[    0.379502] kernel: PM: hibernation: Registered nosave memory: [mem 0xf0000000-0xf7ffffff]
   394	[    0.379503] kernel: PM: hibernation: Registered nosave memory: [mem 0xf8000000-0xfebfffff]
   395	[    0.379504] kernel: PM: hibernation: Registered nosave memory: [mem 0xfec00000-0xfec0ffff]
   396	[    0.379505] kernel: PM: hibernation: Registered nosave memory: [mem 0xfec10000-0xfedfffff]
   397	[    0.379505] kernel: PM: hibernation: Registered nosave memory: [mem 0xfee00000-0xfee00fff]
   398	[    0.379506] kernel: PM: hibernation: Registered nosave memory: [mem 0xfee01000-0xfffdffff]
   399	[    0.379507] kernel: PM: hibernation: Registered nosave memory: [mem 0xfffe0000-0xffffffff]
   400	[    0.379508] kernel: [mem 0xc0000000-0xefffffff] available for PCI devices
   401	[    0.379510] kernel: Booting paravirtualized kernel on VMware hypervisor
   402	[    0.379512] kernel: clocksource: refined-jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645519600211568 ns
   403	[    0.379520] kernel: setup_percpu: NR_CPUS:8192 nr_cpumask_bits:128 nr_cpu_ids:128 nr_node_ids:1
   404	[    0.540401] kernel: percpu: Embedded 56 pages/cpu s192512 r8192 d28672 u262144
   405	[    0.540418] kernel: pcpu-alloc: s192512 r8192 d28672 u262144 alloc=1*2097152
   406	[    0.540421] kernel: pcpu-alloc: [0] 000 001 002 003 004 005 006 007 
   407	[    0.540427] kernel: pcpu-alloc: [0] 008 009 010 011 012 013 014 015 
   408	[    0.540432] kernel: pcpu-alloc: [0] 016 017 018 019 020 021 022 023 
   409	[    0.540437] kernel: pcpu-alloc: [0] 024 025 026 027 028 029 030 031 
   410	[    0.540442] kernel: pcpu-alloc: [0] 032 033 034 035 036 037 038 039 
   411	[    0.540447] kernel: pcpu-alloc: [0] 040 041 042 043 044 045 046 047 
   412	[    0.540452] kernel: pcpu-alloc: [0] 048 049 050 051 052 053 054 055 
   413	[    0.540457] kernel: pcpu-alloc: [0] 056 057 058 059 060 061 062 063 
   414	[    0.540462] kernel: pcpu-alloc: [0] 064 065 066 067 068 069 070 071 
   415	[    0.540467] kernel: pcpu-alloc: [0] 072 073 074 075 076 077 078 079 
   416	[    0.540472] kernel: pcpu-alloc: [0] 080 081 082 083 084 085 086 087 
   417	[    0.540477] kernel: pcpu-alloc: [0] 088 089 090 091 092 093 094 095 
   418	[    0.540482] kernel: pcpu-alloc: [0] 096 097 098 099 100 101 102 103 
   419	[    0.540487] kernel: pcpu-alloc: [0] 104 105 106 107 108 109 110 111 
   420	[    0.540492] kernel: pcpu-alloc: [0] 112 113 114 115 116 117 118 119 
   421	[    0.540497] kernel: pcpu-alloc: [0] 120 121 122 123 124 125 126 127 
   422	[    0.540591] kernel: Built 1 zonelists, mobility grouping on.  Total pages: 1032024
   423	[    0.540595] kernel: Policy zone: Normal
   424	[    0.540597] kernel: Kernel command line: BOOT_IMAGE=/boot/vmlinuz-5.11.0-38-generic root=UUID=f016fec7-baa2-4d84-99bb-4b8bde2ff82c ro find_preseed=/preseed.cfg auto noprompt priority=critical locale=en_US quiet
   425	[    0.540706] kernel: printk: log_buf_len individual max cpu contribution: 4096 bytes
   426	[    0.540708] kernel: printk: log_buf_len total cpu_extra contributions: 520192 bytes
   427	[    0.540708] kernel: printk: log_buf_len min size: 262144 bytes
   428	[    0.562781] kernel: printk: log_buf_len: 1048576 bytes
   429	[    0.562785] kernel: printk: early log buf free: 236800(90%)
   430	[    0.582114] kernel: Dentry cache hash table entries: 524288 (order: 10, 4194304 bytes, linear)
   431	[    0.591703] kernel: Inode-cache hash table entries: 262144 (order: 9, 2097152 bytes, linear)
   432	[    0.592629] kernel: mem auto-init: stack:off, heap alloc:on, heap free:off
   433	[    0.751572] kernel: Memory: 3935528K/4193716K available (14345K kernel code, 3478K rwdata, 5460K rodata, 2688K init, 5976K bss, 257928K reserved, 0K cma-reserved)
   434	[    0.751580] kernel: random: get_random_u64 called from __kmem_cache_create+0x2d/0x430 with crng_init=0
   435	[    0.752577] kernel: SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=128, Nodes=1
   436	[    0.752677] kernel: ftrace: allocating 48695 entries in 191 pages
   437	[    0.769110] kernel: ftrace: allocated 191 pages with 7 groups
   438	[    0.771216] kernel: rcu: Hierarchical RCU implementation.
   439	[    0.771218] kernel: rcu:         RCU restricting CPUs from NR_CPUS=8192 to nr_cpu_ids=128.
   440	[    0.771220] kernel:         Rude variant of Tasks RCU enabled.
   441	[    0.771220] kernel:         Tracing variant of Tasks RCU enabled.
   442	[    0.771221] kernel: rcu: RCU calculated value of scheduler-enlistment delay is 25 jiffies.
   443	[    0.771222] kernel: rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=128
   444	[    0.776062] kernel: NR_IRQS: 524544, nr_irqs: 1448, preallocated irqs: 16
   445	[    0.777010] kernel: random: crng done (trusting CPU's manufacturer)
   446	[    0.812333] kernel: Console: colour VGA+ 80x25
   447	[    0.812359] kernel: printk: console [tty0] enabled
   448	[    0.812497] kernel: ACPI: Core revision 20201113
   449	[    0.814361] kernel: clocksource: hpet: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 133484882848 ns
   450	[    0.814722] kernel: APIC: Switch to symmetric I/O mode setup
   451	[    0.815826] kernel: x2apic enabled
   452	[    0.816350] kernel: Switched APIC routing to physical x2apic.
   453	[    0.821112] kernel: ..TIMER: vector=0x30 apic1=0 pin1=2 apic2=-1 pin2=-1
   454	[    0.821155] kernel: clocksource: tsc-early: mask: 0xffffffffffffffff max_cycles: 0x6d8d08c86a3, max_idle_ns: 881590493188 ns
   455	[    0.821162] kernel: Calibrating delay loop (skipped) preset value.. 7600.09 BogoMIPS (lpj=15200194)
   456	[    0.821164] kernel: pid_max: default: 131072 minimum: 1024
   457	[    0.821245] kernel: LSM: Security Framework initializing
   458	[    0.821258] kernel: Yama: becoming mindful.
   459	[    0.821452] kernel: AppArmor: AppArmor initialized
   460	[    0.821931] kernel: Mount-cache hash table entries: 8192 (order: 4, 65536 bytes, linear)
   461	[    0.822242] kernel: Mountpoint-cache hash table entries: 8192 (order: 4, 65536 bytes, linear)
   462	[    0.823762] kernel: unchecked MSR access error: RDMSR from 0x852 at rIP: 0xffffffffbc47c4c8 (native_read_msr+0x8/0x40)
   463	[    0.823762] kernel: Call Trace:
   464	[    0.823762] kernel:  native_apic_msr_read+0x1c/0x30
   465	[    0.823762] kernel:  setup_APIC_eilvt+0x54/0x140
   466	[    0.823762] kernel:  mce_amd_feature_init+0x3c0/0x420
   467	[    0.823762] kernel:  __mcheck_cpu_init_vendor+0x6c/0xd0
   468	[    0.823762] kernel:  mcheck_cpu_init+0x157/0x480
   469	[    0.823762] kernel:  identify_cpu+0x413/0x580
   470	[    0.823762] kernel:  identify_boot_cpu+0x10/0x9a
   471	[    0.823762] kernel:  check_bugs+0x2a/0x8af
   472	[    0.823762] kernel:  start_kernel+0x6a5/0x6df
   473	[    0.823762] kernel:  x86_64_start_reservations+0x24/0x26
   474	[    0.823762] kernel:  x86_64_start_kernel+0x8b/0x8f
   475	[    0.823762] kernel:  secondary_startup_64_no_verify+0xc2/0xcb
   476	[    0.823762] kernel: LVT offset 2 assigned for vector 0xf4
   477	[    0.823762] kernel: [Firmware Bug]: cpu 0, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   478	[    0.825159] kernel: Last level iTLB entries: 4KB 1024, 2MB 1024, 4MB 512
   479	[    0.825159] kernel: Last level dTLB entries: 4KB 1536, 2MB 1536, 4MB 768, 1GB 0
   480	[    0.825159] kernel: Spectre V1 : Mitigation: usercopy/swapgs barriers and __user pointer sanitization
   481	[    0.825159] kernel: Spectre V2 : Mitigation: Full AMD retpoline
   482	[    0.825159] kernel: Spectre V2 : Spectre v2 / SpectreRSB mitigation: Filling RSB on context switch
   483	[    0.825159] kernel: Spectre V2 : mitigation: Enabling conditional Indirect Branch Prediction Barrier
   484	[    0.825159] kernel: Speculative Store Bypass: Mitigation: Speculative Store Bypass disabled via prctl and seccomp
   485	[    0.825159] kernel: Freeing SMP alternatives memory: 40K
   486	[    0.833159] kernel: smpboot: CPU0: AMD Ryzen 7 2700 Eight-Core Processor (family: 0x17, model: 0x8, stepping: 0x2)
   487	[    0.833409] kernel: Performance Events: AMD PMU driver.
   488	[    0.833562] kernel: ... version:                0
   489	[    0.833563] kernel: ... bit width:              48
   490	[    0.833564] kernel: ... generic registers:      4
   491	[    0.833564] kernel: ... value mask:             0000ffffffffffff
   492	[    0.833565] kernel: ... max period:             00007fffffffffff
   493	[    0.833566] kernel: ... fixed-purpose events:   0
   494	[    0.833566] kernel: ... event mask:             000000000000000f
   495	[    0.833806] kernel: rcu: Hierarchical SRCU implementation.
   496	[    0.834607] kernel: NMI watchdog: Enabled. Permanently consumes one hw-PMU counter.
   497	[    0.854625] kernel: smp: Bringing up secondary CPUs ...
   498	[    0.856142] kernel: x86: Booting SMP configuration:
   499	[    0.856144] kernel: .... node  #0, CPUs:          #1
   500	[    0.044234] kernel: [Firmware Bug]: cpu 1, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   501	[    0.862491] kernel:    #2
   502	[    0.044234] kernel: [Firmware Bug]: cpu 2, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   503	[    0.044234] kernel: smpboot: CPU 2 Converting physical 0 to logical die 1
   504	[    0.870457] kernel:    #3
   505	[    0.044234] kernel: [Firmware Bug]: cpu 3, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   506	[    0.874397] kernel:    #4
   507	[    0.044234] kernel: [Firmware Bug]: cpu 4, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   508	[    0.044234] kernel: smpboot: CPU 4 Converting physical 0 to logical die 2
   509	[    0.882462] kernel:    #5
   510	[    0.044234] kernel: [Firmware Bug]: cpu 5, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   511	[    0.890197] kernel:    #6
   512	[    0.044234] kernel: [Firmware Bug]: cpu 6, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   513	[    0.044234] kernel: smpboot: CPU 6 Converting physical 0 to logical die 3
   514	[    0.898395] kernel:    #7
   515	[    0.044234] kernel: [Firmware Bug]: cpu 7, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   516	[    0.902402] kernel:    #8
   517	[    0.044234] kernel: [Firmware Bug]: cpu 8, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   518	[    0.044234] kernel: smpboot: CPU 8 Converting physical 0 to logical die 4
   519	[    0.910561] kernel:    #9
   520	[    0.044234] kernel: [Firmware Bug]: cpu 9, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   521	[    0.918235] kernel:   #10
   522	[    0.044234] kernel: [Firmware Bug]: cpu 10, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   523	[    0.044234] kernel: smpboot: CPU 10 Converting physical 0 to logical die 5
   524	[    0.926369] kernel:   #11
   525	[    0.044234] kernel: [Firmware Bug]: cpu 11, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   526	[    0.931031] kernel:   #12
   527	[    0.044234] kernel: [Firmware Bug]: cpu 12, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   528	[    0.044234] kernel: smpboot: CPU 12 Converting physical 0 to logical die 6
   529	[    0.938360] kernel:   #13
   530	[    0.044234] kernel: [Firmware Bug]: cpu 13, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   531	[    0.946601] kernel:   #14
   532	[    0.044234] kernel: [Firmware Bug]: cpu 14, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   533	[    0.044234] kernel: smpboot: CPU 14 Converting physical 0 to logical die 7
   534	[    0.954236] kernel:   #15
   535	[    0.044234] kernel: [Firmware Bug]: cpu 15, try to use APIC520 (LVT offset 2) for vector 0xf4, but the register is already in use for vector 0x0 on this cpu
   536	[    0.962051] kernel: smp: Brought up 1 node, 16 CPUs
   537	[    0.964458] kernel: smpboot: Max logical packages: 64
   538	[    0.964461] kernel: smpboot: Total of 16 processors activated (121601.55 BogoMIPS)
   539	[    0.969618] kernel: devtmpfs: initialized
   540	[    0.969618] kernel: x86/mm: Memory block size: 128MB
   541	[    0.970504] kernel: PM: Registering ACPI NVS region [mem 0xbfeff000-0xbfefffff] (4096 bytes)
   542	[    0.970504] kernel: clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
   543	[    0.981470] kernel: futex hash table entries: 32768 (order: 9, 2097152 bytes, linear)
   544	[    0.981837] kernel: pinctrl core: initialized pinctrl subsystem
   545	[    0.982482] kernel: PM: RTC time: 10:10:55, date: 2022-07-14
   546	[    0.983887] kernel: NET: Registered protocol family 16
   547	[    0.985159] kernel: DMA: preallocated 512 KiB GFP_KERNEL pool for atomic allocations
   548	[    0.985159] kernel: DMA: preallocated 512 KiB GFP_KERNEL|GFP_DMA pool for atomic allocations
   549	[    0.985159] kernel: DMA: preallocated 512 KiB GFP_KERNEL|GFP_DMA32 pool for atomic allocations
   550	[    0.985159] kernel: audit: initializing netlink subsys (disabled)
   551	[    0.985315] kernel: audit: type=2000 audit(1657793455.168:1): state=initialized audit_enabled=0 res=1
   552	[    0.985636] kernel: thermal_sys: Registered thermal governor 'fair_share'
   553	[    0.985638] kernel: thermal_sys: Registered thermal governor 'bang_bang'
   554	[    0.985639] kernel: thermal_sys: Registered thermal governor 'step_wise'
   555	[    0.985639] kernel: thermal_sys: Registered thermal governor 'user_space'
   556	[    0.985640] kernel: thermal_sys: Registered thermal governor 'power_allocator'
   557	[    0.985646] kernel: EISA bus registered
   558	[    0.985682] kernel: cpuidle: using governor ladder
   559	[    0.989162] kernel: cpuidle: using governor menu
   560	[    0.993228] kernel: Simple Boot Flag at 0x36 set to 0x80
   561	[    0.993364] kernel: ACPI: bus type PCI registered
   562	[    0.993367] kernel: acpiphp: ACPI Hot Plug PCI Controller Driver version: 0.5
   563	[    0.994186] kernel: PCI: MMCONFIG for domain 0000 [bus 00-7f] at [mem 0xf0000000-0xf7ffffff] (base 0xf0000000)
   564	[    0.994191] kernel: PCI: MMCONFIG at [mem 0xf0000000-0xf7ffffff] reserved in E820
   565	[    0.994204] kernel: PCI: Using configuration type 1 for base access
   566	[    0.997124] kernel: Kprobes globally optimized
   567	[    0.997428] kernel: HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
   568	[    0.997428] kernel: HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
   569	[    1.021482] kernel: ACPI: Added _OSI(Module Device)
   570	[    1.021484] kernel: ACPI: Added _OSI(Processor Device)
   571	[    1.021485] kernel: ACPI: Added _OSI(3.0 _SCP Extensions)
   572	[    1.021486] kernel: ACPI: Added _OSI(Processor Aggregator Device)
   573	[    1.021486] kernel: ACPI: Added _OSI(Linux-Dell-Video)
   574	[    1.021487] kernel: ACPI: Added _OSI(Linux-Lenovo-NV-HDMI-Audio)
   575	[    1.021488] kernel: ACPI: Added _OSI(Linux-HPI-Hybrid-Graphics)
   576	[    1.052010] kernel: ACPI: 1 ACPI AML tables successfully acquired and loaded
   577	[    1.054288] kernel: ACPI: [Firmware Bug]: BIOS _OSI(Linux) query ignored
   578	[    1.079227] kernel: ACPI: Interpreter enabled
   579	[    1.079240] kernel: ACPI: (supports S0 S1 S4 S5)
   580	[    1.079242] kernel: ACPI: Using IOAPIC for interrupt routing
   581	[    1.079267] kernel: PCI: Using host bridge windows from ACPI; if necessary, use "pci=nocrs" and report a bug
   582	[    1.081002] kernel: ACPI: Enabled 4 GPEs in block 00 to 0F
   583	[    1.352848] kernel: ACPI: PCI Root Bridge [PCI0] (domain 0000 [bus 00-7f])
   584	[    1.352857] kernel: acpi PNP0A03:00: _OSC: OS supports [ExtendedConfig ASPM ClockPM Segments MSI HPX-Type3]
   585	[    1.353230] kernel: acpi PNP0A03:00: _OSC: platform does not support [AER LTR]
   586	[    1.353533] kernel: acpi PNP0A03:00: _OSC: OS now controls [PCIeHotplug SHPCHotplug PME PCIeCapability]
   587	[    1.357206] kernel: PCI host bridge to bus 0000:00
   588	[    1.357210] kernel: pci_bus 0000:00: root bus resource [bus 00-7f]
   589	[    1.357211] kernel: pci_bus 0000:00: root bus resource [io  0x0000-0x0cf7 window]
   590	[    1.357213] kernel: pci_bus 0000:00: root bus resource [io  0x0d00-0xfeff window]
   591	[    1.357214] kernel: pci_bus 0000:00: root bus resource [mem 0x000a0000-0x000bffff window]
   592	[    1.357215] kernel: pci_bus 0000:00: root bus resource [mem 0x000d0000-0x000dbfff window]
   593	[    1.357217] kernel: pci_bus 0000:00: root bus resource [mem 0xc0000000-0xfebfffff window]
   594	[    1.357418] kernel: pci 0000:00:00.0: [8086:7190] type 00 class 0x060000
   595	[    1.361159] kernel: pci 0000:00:01.0: [8086:7191] type 01 class 0x060400
   596	[    1.383507] kernel: pci 0000:00:07.0: [8086:7110] type 00 class 0x060100
   597	[    1.385870] kernel: pci 0000:00:07.1: [8086:7111] type 00 class 0x01018a
   598	[    1.388651] kernel: pci 0000:00:07.1: reg 0x20: [io  0x1060-0x106f]
   599	[    1.389731] kernel: pci 0000:00:07.1: legacy IDE quirk: reg 0x10: [io  0x01f0-0x01f7]
   600	[    1.389734] kernel: pci 0000:00:07.1: legacy IDE quirk: reg 0x14: [io  0x03f6]
   601	[    1.389735] kernel: pci 0000:00:07.1: legacy IDE quirk: reg 0x18: [io  0x0170-0x0177]
   602	[    1.389736] kernel: pci 0000:00:07.1: legacy IDE quirk: reg 0x1c: [io  0x0376]
   603	[    1.390208] kernel: pci 0000:00:07.3: [8086:7113] type 00 class 0x068000
   604	[    1.393159] kernel: pci 0000:00:07.3: quirk: [io  0x1000-0x103f] claimed by PIIX4 ACPI
   605	[    1.393159] kernel: pci 0000:00:07.3: quirk: [io  0x1040-0x104f] claimed by PIIX4 SMB
   606	[    1.393402] kernel: pci 0000:00:07.7: [15ad:0740] type 00 class 0x088000
   607	[    1.394671] kernel: pci 0000:00:07.7: reg 0x10: [io  0x1080-0x10bf]
   608	[    1.395782] kernel: pci 0000:00:07.7: reg 0x14: [mem 0xfebfe000-0xfebfffff 64bit]
   609	[    1.429159] kernel: pci 0000:00:0f.0: [15ad:0405] type 00 class 0x030000
   610	[    1.430619] kernel: pci 0000:00:0f.0: reg 0x10: [io  0x1070-0x107f]
   611	[    1.434304] kernel: pci 0000:00:0f.0: reg 0x14: [mem 0xe8000000-0xefffffff pref]
   612	[    1.436563] kernel: pci 0000:00:0f.0: reg 0x18: [mem 0xfe000000-0xfe7fffff]
   613	[    1.446366] kernel: pci 0000:00:0f.0: reg 0x30: [mem 0x00000000-0x00007fff pref]
   614	[    1.452145] kernel: pci 0000:00:10.0: [1000:0030] type 00 class 0x010000
   615	[    1.453162] kernel: pci 0000:00:10.0: reg 0x10: [io  0x1400-0x14ff]
   616	[    1.457166] kernel: pci 0000:00:10.0: reg 0x14: [mem 0xfeba0000-0xfebbffff 64bit]
   617	[    1.458923] kernel: pci 0000:00:10.0: reg 0x1c: [mem 0xfebc0000-0xfebdffff 64bit]
   618	[    1.464577] kernel: pci 0000:00:10.0: reg 0x30: [mem 0x00000000-0x00003fff pref]
   619	[    1.466746] kernel: pci 0000:00:11.0: [15ad:0790] type 01 class 0x060401
   620	[    1.481613] kernel: pci 0000:00:15.0: [15ad:07a0] type 01 class 0x060400
   621	[    1.483627] kernel: pci 0000:00:15.0: PME# supported from D0 D3hot D3cold
   622	[    1.484546] kernel: pci 0000:00:15.1: [15ad:07a0] type 01 class 0x060400
   623	[    1.486592] kernel: pci 0000:00:15.1: PME# supported from D0 D3hot D3cold
   624	[    1.487620] kernel: pci 0000:00:15.2: [15ad:07a0] type 01 class 0x060400
   625	[    1.489677] kernel: pci 0000:00:15.2: PME# supported from D0 D3hot D3cold
   626	[    1.490563] kernel: pci 0000:00:15.3: [15ad:07a0] type 01 class 0x060400
   627	[    1.492531] kernel: pci 0000:00:15.3: PME# supported from D0 D3hot D3cold
   628	[    1.493514] kernel: pci 0000:00:15.4: [15ad:07a0] type 01 class 0x060400
   629	[    1.495473] kernel: pci 0000:00:15.4: PME# supported from D0 D3hot D3cold
   630	[    1.497424] kernel: pci 0000:00:15.5: [15ad:07a0] type 01 class 0x060400
   631	[    1.499389] kernel: pci 0000:00:15.5: PME# supported from D0 D3hot D3cold
...
...
...
  1676	[    9.526981] kernel: [drm]   IntraSurface copy.
  1677	[    9.526981] kernel: [drm]   DX3.
  1678	[    9.526981] kernel: [drm] Max GMR ids is 64
  1679	[    9.526982] kernel: [drm] Max number of GMR pages is 65536
  1680	[    9.526983] kernel: [drm] Max dedicated hypervisor surface memory is 0 kiB
  1681	[    9.526983] kernel: [drm] Maximum display memory size is 262144 kiB
  1682	[    9.526984] kernel: [drm] VRAM at 0xe8000000 size is 4096 kiB
  1683	[    9.526985] kernel: [drm] MMIO at 0xfe000000 size is 256 kiB
  1684	[    9.527874] kernel: [TTM] Zone  kernel: Available graphics memory: 1997544 KiB
  1685	[    9.529079] systemd[1]: Mounting Mount unit for gtk-common-themes, revision 1535...
  1686	[    9.530825] kernel: [drm] Screen Target Display device initialized
  1687	[    9.531074] kernel: [drm] width 640
  1688	[    9.531110] kernel: [drm] height 480
  1689	[    9.531147] kernel: [drm] bpp 32
  1690	[    9.532268] systemd[1]: Mounting Mount unit for snap-store, revision 547...
  1691	[    9.532961] kernel: [drm] Fifo max 0x00040000 min 0x00001000 cap 0x0000077f
  1692	[    9.533596] kernel: [drm] Using command buffers with DMA pool.
  1693	[    9.533603] kernel: [drm] Atomic: yes.
  1694	[    9.533604] kernel: [drm] SM5 support available.
  1695	[    9.534158] systemd[1]: Mounting Mount unit for snap-store, revision 558...
  1696	[    9.536693] kernel: fbcon: svgadrmfb (fb0) is primary device
  1697	[    9.537558] systemd[1]: Mounting Mount unit for snapd, revision 16010...
  1698	[    9.538441] kernel: Console: switching to colour frame buffer device 100x37
  1699	[    9.541259] systemd[1]: Mounting Mount unit for snapd, revision 16292...
  1700	[    9.545961] systemd[1]: Starting udev Kernel Device Manager...
  1701	[    9.550524] kernel: [drm] Initialized vmwgfx 2.18.0 20200114 for 0000:00:0f.0 on minor 0
  1702	[    9.550673] kernel: loop1: detected capacity change from 0 to 113640
  1703	[    9.552164] systemd[1]: Finished Load Kernel Modules.
  1704	[    9.555005] systemd[1]: Mounting FUSE Control File System...
  1705	[    9.557351] systemd[1]: Mounting Kernel Configuration File System...
  1706	[    9.560486] systemd[1]: Starting Apply Kernel Variables...
  1707	[    9.563751] systemd[1]: Mounted FUSE Control File System.
  1708	[    9.563867] systemd[1]: Mounted Kernel Configuration File System.
  1709	[    9.566187] systemd[1]: Mounting VMware vmblock fuse mount...
  1710	[    9.572070] systemd[1]: Started Journal Service.
  1711	[    9.586748] kernel: loop2: detected capacity change from 0 to 126784
  1712	[    9.642493] kernel: loop3: detected capacity change from 0 to 126824
  1713	[    9.665834] kernel: loop4: detected capacity change from 0 to 448512
  1714	[    9.682122] kernel: loop5: detected capacity change from 0 to 820832
  1715	[    9.711688] kernel: loop6: detected capacity change from 0 to 507712
  1716	[    9.734637] kernel: loop7: detected capacity change from 0 to 187776
  1717	[    9.789112] kernel: loop8: detected capacity change from 0 to 113736
  1718	[    9.867197] kernel: loop9: detected capacity change from 0 to 96176
  1719	[    9.954472] kernel: loop10: detected capacity change from 0 to 96160
  1720	[    9.975731] kernel: vmw_vmci 0000:00:07.7: Found VMCI PCI device at 0x11080, irq 16
  1721	[    9.976144] kernel: vmw_vmci 0000:00:07.7: Using capabilities 0x1c
  1722	[    9.977828] kernel: Guest personality initialized and is active
  1723	[    9.979045] kernel: VMCI host device registered (name=vmci, major=10, minor=122)
  1724	[    9.979049] kernel: Initialized host personality
  1725	[   10.031706] kernel: loop11: detected capacity change from 0 to 133552
  1726	[   10.073146] kernel: RAPL PMU: API unit is 2^-32 Joules, 0 fixed counters, 10737418240 ms ovfl timer
  1727	[   10.097635] kernel: cryptd: max_cpu_qlen set to 1000
  1728	[   10.133213] kernel: AVX2 version of gcm_enc/dec engaged.
  1729	[   10.133218] kernel: AES CTR mode by8 optimization enabled
  1730	[   10.187508] kernel: loop12: detected capacity change from 0 to 448512
  1731	[   10.193144] kernel: Decoding supported only on Scalable MCA processors.
  1732	[   10.239997] kernel: Decoding supported only on Scalable MCA processors.
  1733	[   10.262118] kernel: loop13: detected capacity change from 0 to 111080
  1734	[   10.289481] kernel: Decoding supported only on Scalable MCA processors.
  1735	[   10.374959] kernel: loop14: detected capacity change from 0 to 104360
  1736	[   10.409795] kernel: Decoding supported only on Scalable MCA processors.
  1737	[   10.468085] kernel: Decoding supported only on Scalable MCA processors.
  1738	[   10.524081] kernel: Decoding supported only on Scalable MCA processors.
  1739	[   10.572351] kernel: Decoding supported only on Scalable MCA processors.
  1740	[   10.629795] kernel: Decoding supported only on Scalable MCA processors.
  1741	[   10.677537] kernel: Decoding supported only on Scalable MCA processors.
  1742	[   10.727933] kernel: Decoding supported only on Scalable MCA processors.
  1743	[   10.769672] kernel: Decoding supported only on Scalable MCA processors.
  1744	[   10.825311] kernel: Decoding supported only on Scalable MCA processors.
  1745	[   10.884318] kernel: Decoding supported only on Scalable MCA processors.
  1746	[   10.936418] kernel: Decoding supported only on Scalable MCA processors.
  1747	[   10.993956] kernel: Decoding supported only on Scalable MCA processors.
  1748	[   11.054940] kernel: Decoding supported only on Scalable MCA processors.
  1749	[   11.239505] kernel: audit: type=1400 audit(1657793466.324:2): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-xpdfimport" pid=868 comm="apparmor_parser"
  1750	[   11.240634] kernel: audit: type=1400 audit(1657793466.324:3): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-senddoc" pid=870 comm="apparmor_parser"
  1751	[   11.241356] kernel: audit: type=1400 audit(1657793466.324:4): apparmor="STATUS" operation="profile_load" profile="unconfined" name="libreoffice-oopslash" pid=856 comm="apparmor_parser"
  1752	[   11.241800] kernel: audit: type=1400 audit(1657793466.328:5): apparmor="STATUS" operation="profile_load" profile="unconfined" name="ippusbxd" pid=862 comm="apparmor_parser"
  1753	[   11.241806] kernel: audit: type=1400 audit(1657793466.328:6): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe" pid=857 comm="apparmor_parser"
  1754	[   11.241811] kernel: audit: type=1400 audit(1657793466.328:7): apparmor="STATUS" operation="profile_load" profile="unconfined" name="nvidia_modprobe//kmod" pid=857 comm="apparmor_parser"
  1755	[   11.242848] kernel: audit: type=1400 audit(1657793466.328:8): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/man" pid=860 comm="apparmor_parser"
  1756	[   11.242860] kernel: audit: type=1400 audit(1657793466.328:9): apparmor="STATUS" operation="profile_load" profile="unconfined" name="man_filter" pid=860 comm="apparmor_parser"
  1757	[   11.242863] kernel: audit: type=1400 audit(1657793466.328:10): apparmor="STATUS" operation="profile_load" profile="unconfined" name="man_groff" pid=860 comm="apparmor_parser"
  1758	[   11.243477] kernel: audit: type=1400 audit(1657793466.328:11): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/lib/snapd/snap-confine" pid=867 comm="apparmor_parser"
  1759	[   11.349966] kernel: NET: Registered protocol family 40
  1760	[   11.943372] kernel: e1000: ens33 NIC Link is Up 1000 Mbps Full Duplex, Flow Control: None
  1761	[   11.946840] kernel: IPv6: ADDRCONF(NETDEV_CHANGE): ens33: link becomes ready
  1762	[   13.399005] kernel: loop15: detected capacity change from 0 to 8
mao@ubuntu:/var/log/cups$ 
```



```sh
mao@ubuntu:/var/log/cups$ lastb
lastb: 打不开 /var/log/btmp: 权限不够
mao@ubuntu:/var/log/cups$ sudo lastb
[sudo] mao 的密码： 
root     pts/0                         Mon Jul  4 22:13 - 22:13  (00:00)
root     pts/0                         Mon Jul  4 22:13 - 22:13  (00:00)
root     pts/0                         Mon Jul  4 22:12 - 22:12  (00:00)
root     pts/0                         Mon Jul  4 22:12 - 22:12  (00:00)
root     pts/0                         Mon Jul  4 22:11 - 22:11  (00:00)
root     pts/0                         Mon Jul  4 22:11 - 22:11  (00:00)
root     pts/0                         Mon Jul  4 22:00 - 22:00  (00:00)
root     pts/0                         Mon Jul  4 21:59 - 21:59  (00:00)
root     pts/0                         Mon Jul  4 21:58 - 21:58  (00:00)
root     pts/0                         Mon Jul  4 05:06 - 05:06  (00:00)
root     pts/0                         Mon Jul  4 05:06 - 05:06  (00:00)
root     pts/0                         Mon Jul  4 05:06 - 05:06  (00:00)
root     pts/0                         Mon Jul  4 05:06 - 05:06  (00:00)
root     pts/0                         Mon Jul  4 05:06 - 05:06  (00:00)
root     pts/0                         Mon Jul  4 05:05 - 05:05  (00:00)
root     pts/0                         Mon Jul  4 05:05 - 05:05  (00:00)
root     pts/0                         Sat Jul  2 04:38 - 04:38  (00:00)
root     pts/0                         Sat Jul  2 04:38 - 04:38  (00:00)

btmp begins Sat Jul  2 04:38:16 2022
mao@ubuntu:/var/log/cups$ 
```



```sh
mao@ubuntu:/var/log/cups$ lastlog
用户名           端口     来自             最后登录时间
root                                       **从未登录过**
daemon                                     **从未登录过**
bin                                        **从未登录过**
sys                                        **从未登录过**
sync                                       **从未登录过**
games                                      **从未登录过**
man                                        **从未登录过**
lp                                         **从未登录过**
mail                                       **从未登录过**
news                                       **从未登录过**
uucp                                       **从未登录过**
proxy                                      **从未登录过**
www-data                                   **从未登录过**
backup                                     **从未登录过**
list                                       **从未登录过**
irc                                        **从未登录过**
gnats                                      **从未登录过**
nobody                                     **从未登录过**
systemd-network                            **从未登录过**
systemd-resolve                            **从未登录过**
systemd-timesync                           **从未登录过**
messagebus                                 **从未登录过**
syslog                                     **从未登录过**
_apt                                       **从未登录过**
tss                                        **从未登录过**
uuidd                                      **从未登录过**
tcpdump                                    **从未登录过**
avahi-autoipd                              **从未登录过**
usbmux                                     **从未登录过**
rtkit                                      **从未登录过**
dnsmasq                                    **从未登录过**
cups-pk-helper                             **从未登录过**
speech-dispatcher                           **从未登录过**
avahi                                      **从未登录过**
kernoops                                   **从未登录过**
saned                                      **从未登录过**
nm-openvpn                                 **从未登录过**
hplip                                      **从未登录过**
whoopsie                                   **从未登录过**
colord                                     **从未登录过**
geoclue                                    **从未登录过**
pulse                                      **从未登录过**
gnome-initial-setup                           **从未登录过**
gdm                                        **从未登录过**
sssd                                       **从未登录过**
mao                                        **从未登录过**
systemd-coredump                           **从未登录过**
mao@ubuntu:/var/log/cups$ 
```



```sh
mao@ubuntu:/var/log/cups$ cat -n /var/Iog/mailog
cat: /var/Iog/mailog: 没有那个文件或目录
mao@ubuntu:/var/log/cups$ cat -n /var/log/messages
cat: /var/log/messages: 没有那个文件或目录
mao@ubuntu:/var/log/cups$ 
mao@ubuntu:/var/log/cups$ cat /var/log/mailog
cat: /var/log/mailog: 没有那个文件或目录
mao@ubuntu:/var/log/cups$ 
mao@ubuntu:/var/log/cups$ cat -n /var/log/secure
cat: /var/log/secure: 没有那个文件或目录
mao@ubuntu:/var/log/cups$ last
mao      :0           :0               Thu Jul 14 03:11   still logged in
reboot   system boot  5.11.0-38-generi Thu Jul 14 03:11   still running
mao      :0           :0               Tue Jul 12 21:39 - crash (1+05:31)
reboot   system boot  5.11.0-38-generi Tue Jul 12 21:38   still running
mao      :0           :0               Mon Jul 11 22:00 - crash  (23:38)
reboot   system boot  5.11.0-38-generi Mon Jul 11 21:59   still running
mao      :0           :0               Sat Jul  9 21:24 - crash (2+00:35)
reboot   system boot  5.11.0-38-generi Sat Jul  9 21:24   still running
mao      :0           :0               Fri Jul  8 06:45 - crash (1+14:38)
reboot   system boot  5.11.0-38-generi Fri Jul  8 06:44   still running
mao      :0           :0               Thu Jul  7 07:00 - crash  (23:43)
mao      :0           :0               Thu Jul  7 06:08 - 07:00  (00:52)
reboot   system boot  5.11.0-38-generi Thu Jul  7 06:08   still running
mao      :0           :0               Wed Jul  6 22:10 - crash  (07:57)
reboot   system boot  5.11.0-38-generi Wed Jul  6 22:10   still running
mao      :0           :0               Wed Jul  6 04:44 - down   (01:51)
reboot   system boot  5.11.0-38-generi Wed Jul  6 04:43 - 06:35  (01:51)
mao      :0           :0               Tue Jul  5 04:00 - down   (02:39)
reboot   system boot  5.11.0-38-generi Tue Jul  5 03:59 - 06:40  (02:40)
mao      :0           :0               Mon Jul  4 21:46 - crash  (06:13)
reboot   system boot  5.11.0-38-generi Mon Jul  4 21:44 - 06:40  (08:56)
mao      :0           :0               Mon Jul  4 04:37 - crash  (17:06)
reboot   system boot  5.11.0-38-generi Mon Jul  4 04:37 - 06:40 (1+02:03)
mao      :0           :0               Sat Jul  2 21:46 - crash (1+06:51)
reboot   system boot  5.11.0-38-generi Sat Jul  2 21:46 - 06:40 (2+08:54)
mao      :0           :0               Sat Jul  2 04:23 - down   (02:43)
reboot   system boot  5.11.0-38-generi Sat Jul  2 04:22 - 07:07  (02:44)
mao      :0           :0               Thu Dec 30 04:32 - crash (183+22:50)
reboot   system boot  5.11.0-38-generi Thu Dec 30 04:30 - 07:07 (184+01:36)
mao      :0           :0               Wed Dec 29 03:11 - crash (1+01:19)
reboot   system boot  5.11.0-38-generi Wed Dec 29 03:10 - 07:07 (185+02:56)
mao      :0           :0               Wed Dec 29 02:38 - crash  (00:32)
reboot   system boot  5.11.0-38-generi Wed Dec 29 02:36 - 07:07 (185+03:30)
mao      :0           :0               Fri Nov 19 20:59 - crash (39+05:36)
reboot   system boot  5.11.0-38-generi Fri Nov 19 20:57 - 07:07 (224+09:09)
mao      :0           :0               Fri Nov 19 20:37 - crash  (00:19)
reboot   system boot  5.11.0-38-generi Fri Nov 19 20:37 - 07:07 (224+09:29)
mao      :0           :0               Fri Nov 19 20:20 - down   (00:16)
reboot   system boot  5.11.0-38-generi Fri Nov 19 20:20 - 20:37  (00:16)
mao      :0           :0               Fri Nov  5 05:21 - down   (00:20)
reboot   system boot  5.11.0-38-generi Fri Nov  5 05:20 - 05:42  (00:21)
mao      :0           :0               Thu Nov  4 22:21 - crash  (06:59)
reboot   system boot  5.11.0-38-generi Thu Nov  4 22:20 - 05:42  (07:21)
mao      :0           :0               Sat Oct 23 04:59 - crash (12+17:21)
reboot   system boot  5.11.0-38-generi Sat Oct 23 04:59 - 05:42 (13+00:43)
mao      :0           :0               Sat Oct 23 04:15 - down   (00:03)
reboot   system boot  5.11.0-38-generi Sat Oct 23 04:15 - 04:19  (00:04)
mao      :0           :0               Sat Oct 23 03:51 - down   (00:20)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:51 - 04:12  (00:20)
mao      :0           :0               Sat Oct 23 03:41 - down   (00:07)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:41 - 03:49  (00:07)
mao      :0           :0               Sat Oct 23 03:16 - down   (00:19)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:16 - 03:35  (00:19)
mao      :0           :0               Sat Oct 23 03:12 - down   (00:01)
reboot   system boot  5.11.0-38-generi Sat Oct 23 03:11 - 03:14  (00:02)
mao      :0           :0               Sat Oct 23 02:09 - crash  (01:02)
reboot   system boot  5.11.0-38-generi Sat Oct 23 02:08 - 03:14  (01:05)
mao      :0           :0               Fri Oct 22 23:22 - crash  (02:45)
reboot   system boot  5.11.0-38-generi Fri Oct 22 23:21 - 03:14  (03:53)
mao      :0           :0               Fri Oct 22 05:05 - crash  (18:15)
reboot   system boot  5.11.0-27-generi Fri Oct 22 05:05 - 03:14  (22:09)
mao      :0           :0               Fri Oct 15 05:21 - down   (00:03)
mao      :0           :0               Fri Oct 15 04:22 - 05:21  (00:59)
reboot   system boot  5.11.0-27-generi Fri Oct 15 04:20 - 05:24  (01:04)

wtmp begins Fri Oct 15 04:20:13 2021
mao@ubuntu:/var/log/cups$ 
```







## 日志文件格式

日志文件的格式包含以下 4 列：

- 事件产生的时间。
- 产生事件的服务器的主机名。
- 产生事件的服务名或程序名。
- 事件的具体信息。





## rsyslogd配置文件

rsyslogd 服务是依赖其配置文件 /etc/rsyslog.conf 来确定哪个服务的什么等级的日志信息会被记录在哪个位置的。也就是说，日志服务的配置文件中主要定义了服务的名称、日志等级和日志记录位置。



```sh
mao@ubuntu:/var/log/cups$ cat -n /etc/rsyslog.conf
     1	# /etc/rsyslog.conf configuration file for rsyslog
     2	#
     3	# For more information install rsyslog-doc and see
     4	# /usr/share/doc/rsyslog-doc/html/configuration/index.html
     5	#
     6	# Default logging rules can be found in /etc/rsyslog.d/50-default.conf
     7	
     8	
     9	#################
    10	#### MODULES ####
    11	#################
    12	
    13	module(load="imuxsock") # provides support for local system logging
    14	#module(load="immark")  # provides --MARK-- message capability
    15	
    16	# provides UDP syslog reception
    17	#module(load="imudp")
    18	#input(type="imudp" port="514")
    19	
    20	# provides TCP syslog reception
    21	#module(load="imtcp")
    22	#input(type="imtcp" port="514")
    23	
    24	# provides kernel logging support and enable non-kernel klog messages
    25	module(load="imklog" permitnonkernelfacility="on")
    26	
    27	###########################
    28	#### GLOBAL DIRECTIVES ####
    29	###########################
    30	
    31	#
    32	# Use traditional timestamp format.
    33	# To enable high precision timestamps, comment out the following line.
    34	#
    35	$ActionFileDefaultTemplate RSYSLOG_TraditionalFileFormat
    36	
    37	# Filter duplicated messages
    38	$RepeatedMsgReduction on
    39	
    40	#
    41	# Set the default permissions for all log files.
    42	#
    43	$FileOwner syslog
    44	$FileGroup adm
    45	$FileCreateMode 0640
    46	$DirCreateMode 0755
    47	$Umask 0022
    48	$PrivDropToUser syslog
    49	$PrivDropToGroup syslog
    50	
    51	#
    52	# Where to place spool and state files
    53	#
    54	$WorkDirectory /var/spool/rsyslog
    55	
    56	#
    57	# Include all config files in /etc/rsyslog.d/
    58	#
    59	$IncludeConfig /etc/rsyslog.d/*.conf
mao@ubuntu:/var/log/cups$ 
```



基本格式：

```sh
authpriv.* /var/log/secure
#服务名称[连接符号]日志等级 日志记录位置
#认证相关服务.所有日志等级 记录在/var/log/secure日志中
```



|           服务名称           |                            说 明                             |
| :--------------------------: | :----------------------------------------------------------: |
|        auth(LOG AUTH)        |                      安全和认证相关消息                      |
|    authpriv(LOG_AUTHPRIV)    |                 安全和认证相关消息（私有的）                 |
|       cron (LOG_CRON)        |               系统定时任务cront和at产生的日志                |
|     daemon (LOG_DAEMON)      |                   与各个守护进程相关的曰志                   |
|        ftp (LOG_FTP)         |                    ftp守护进程产生的曰志                     |
|        kern(LOG_KERN)        |             内核产生的曰志（不是用户进程产生的）             |
| Iocal0-local7 (LOG_LOCAL0-7) |                     为本地使用预留的服务                     |
|        lpr (LOG_LPR)         |                        打印产生的日志                        |
|       mail (LOG_MAIL)        |                         邮件收发信息                         |
|       news (LOG_NEWS)        |                    与新闻服务器相关的日志                    |
|     syslog (LOG_SYSLOG)      |                 存syslogd服务产生的曰志信息                  |
|       user (LOG_USER)        |                    用户等级类别的日志信息                    |
|       uucp (LOG_UUCP>        | uucp子系统的日志信息，uucp是早期Linux系统进行数据传递的协议，后来 也常用在新闻组服务中 |



连接符号

日志服务连接日志等级的格式如下：

```sh
日志服务[连接符号]日志等级 日志记录位置
```



|       等级名称       |                            说 明                             |
| :------------------: | :----------------------------------------------------------: |
|  debug (LOG_DEBUG)   |                      一般的调试信息说明                      |
|   info (LOG_INFO)    |                        基本的通知信息                        |
| nolice (LOG_NOTICE)  |                 普通信息，但是有一定的重要性                 |
| warning(LOG_WARNING) |          警吿信息，但是还不会影响到服务或系统的运行          |
|     err(LOG_ERR)     | 错误信息, 一般达到err等级的信息已经可以影响到服务成系统的运行了 |
|   crit (LOG_CRIT)    |               临界状况信思，比err等级还要严重                |
|  alert (LOG_ALERT)   |        状态信息，比crit等级还要严重，必须立即采取行动        |
|  emerg (LOG_EMERG)   |               疼痛等级信息，系统已经无法使用了               |
|          *           | 代表所有日志等级。比如，“authpriv.*”代表amhpriv认证信息服务产生的日志，所有的日志等级都记录 |







## 日志轮替

日志是重要的系统文件，记录和保存了系统中所有的重要事件。但是日志文件也需要进行定期的维护，因为日志文件是不断增长的，如果完全不进行日志维护，而任由其随意递增，那么用不了多久，我们的硬盘就会被写满。

**日志维护的最主要的工作就是把旧的日志文件删除，从而腾出空间保存新的日志文件。**这项工作如果靠管理员手工来完成，那其实是非常烦琐的，而且也容易忘记。

logrotate 就是用来进行日志轮替（也叫日志转储）的，也就是把旧的日志文件移动并改名，同时创建一个新的空日志文件用来记录新日志，当旧日志文件超出保存的范围时就删除。



### 日志文件的命名规则

日志轮替最主要的作用就是把旧的日志文件移动并改名，同时建立新的空日志文件，当旧日志文件超出保存的范围时就删除。那么，旧的日志文件改名之后，如何命名呢？主要依靠 /etc/logrotate.conf 配置文件中的“dateext”参数。

如果配置文件中有“dateext”参数，那么日志会用日期来作为日志文件的后缀，如“secure-20130605”。这样日志文件名不会重叠，也就不需要对日志文件进行改名，只需要保存指定的日志个数，删除多余的日志文件即可。

如果配置文件中没有“dateext”参数，那么日志文件就需要进行改名了。当第一次进行日志轮替时，当前的“secure”日志会自动改名为“secure.1”，然后新建“secure”日志，用来保存新的日志；当第二次进行日志轮替时，“secure.1”会自动改名为“secure.2”，当前的“secure”日志会自动改名为“secure.1”，然后也会新建“secure”日志，用来保存新的日志；以此类推。



```sh
mao@ubuntu:/var/log/cups$ cat -n /etc/logrotate.conf
     1	# see "man logrotate" for details
     2	# rotate log files weekly
     3	weekly
     4	
     5	# use the adm group by default, since this is the owning group
     6	# of /var/log/syslog.
     7	su root adm
     8	
     9	# keep 4 weeks worth of backlogs
    10	rotate 4
    11	
    12	# create new (empty) log files after rotating old ones
    13	create
    14	
    15	# use date as a suffix of the rotated file
    16	#dateext
    17	
    18	# uncomment this if you want your log files compressed
    19	#compress
    20	
    21	# packages drop log rotation information into this directory
    22	include /etc/logrotate.d
    23	
    24	# system-specific logs may be also be configured here.
mao@ubuntu:/var/log/cups$ 
```



|          参 致          |                           参数说明                           |
| :---------------------: | :----------------------------------------------------------: |
|          daily          |                     日志的轮替周期是毎天                     |
|         weekly          |                     日志的轮替周期是每周                     |
|         monthly         |                     日志的轮替周期是每月                     |
|       rotate数宇        |              保留的日志文件的个数。0指没有备份               |
|        compress         |             当进行日志轮替时，对旧的日志进行压缩             |
| create mode owner group | 建立新日志，同时指定新日志的权限与所有者和所属组.如create 0600 root utmp |
|      mail address       |    当进行日志轮替时，输出内存通过邮件发送到指定的邮件地址    |
|        missingok        |            如果日志不存在，则忽略该日志的警告信息            |
|       nolifempty        |              如果曰志为空文件，则不进行日志轮替              |
|      minsize 大小       | 日志轮替的最小值。也就是日志一定要达到这个最小值才会进行轮持，否则就算时间达到也不进行轮替 |
|        size 大小        | 日志只有大于指定大小才进行日志轮替，而不是按照时间轮替，如size 100k |
|         dateext         |      使用日期作为日志轮替文件的后缀，如secure-20130605       |
|      sharedscripts      |                在此关键宇之后的脚本只执行一次                |
|   prerotate/cndscript   |  在曰志轮替之前执行脚本命令。endscript标识prerotate脚本结束  |
|  postrolaie/endscript   | 在日志轮替之后执行脚本命令。endscripi标识postrotate脚本结束  |







### 把自己的日志加入日志轮替

- 第一种方法是直接在 /etc/logrotate.conf 配置文件中写入该日志的轮替策略，从而把日志加入轮替；
- 第二种方法是在 /etc/logrotate.d/ 目录中新建立该日志的轮替文件，在该轮替文件中写入正确的轮替策略，因为该目录中的文件都会被包含到主配置文件中，所以也可以把日志加入轮替。



先给日志文件赋予chattr的a属性，保证日志的安全：

```sh
chattr +a 日志文件位置
```

 /var/log/alert.log



```sh
vi /etc/logrotate.d/alter
#创建alter轮替文件,把/var/log/alert.log加入轮替
/var/log/alert.log {
    weekly
    #每周轮替一次
    rotate 6
    #保留6个轮替曰志
    sharedscripts
    #以下命令只执行一次
    prerotate
    #在日志轮替之前执行
        /usr/bin/chattr -a /var/log/alert.log
        #在日志轮替之前取消a属性,以便让日志可以轮替
    endscript
    #脚本结朿
    sharedscripts
    postrotate
    #在日志轮替之后执行
        /usr/bin/chattr +a /var/log/alert.log
        #在日志轮替之后,重新加入a属性
    endscript
    sharedscripts
    postrotate
    /bin/kill -HUP $(/bin/cat /var/run/syslogd.pid 2>/dev/null) fi>/dev/null
    endscript
    #重启rsyslog服务，保证日志轮替正常进行
}
```







## logrotate命令



```sh
logrotate [选项] 配置文件名
```

选项：

- 如果此命令没有选项，则会按照配置文件中的条件进行日志轮替
- -v：显示日志轮替过程。加入了-v选项，会显示日志的轮替过程
- -f： 强制进行日志轮替。不管日志轮替的条件是否符合，强制配置文件中所有的日志进行轮替



```sh
mao@ubuntu:/var/log/cups$ sudo logrotate -v /etc/logrotate.conf
[sudo] mao 的密码： 
reading config file /etc/logrotate.conf
including /etc/logrotate.d
reading config file alternatives
reading config file apport
reading config file apt
reading config file bootlog
reading config file btmp
reading config file cups-daemon
reading config file dpkg
reading config file ppp
reading config file rsyslog
reading config file speech-dispatcher
reading config file ubuntu-advantage-tools
reading config file ufw
reading config file unattended-upgrades
reading config file wtmp
Reading state from file: /var/lib/logrotate/status
Allocating hash table for state file, size 64 entries
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state
Creating new state

Handling 17 logs

rotating pattern: /var/log/alternatives.log  monthly (12 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/alternatives.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-12 21:39
  log does not need rotating (log has been rotated at 2022-7-12 21:39, that is not month ago yet)
switching euid to 0 and egid to 0

rotating pattern: /var/log/apport.log  after 1 days (7 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/apport.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-04 04:37
  log does not need rotating (log is empty)
switching euid to 0 and egid to 0

rotating pattern: /var/log/apt/term.log  monthly (12 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/apt/term.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-07 06:08
  log does not need rotating (log has been rotated at 2022-7-7 6:8, that is not month ago yet)
switching euid to 0 and egid to 0

rotating pattern: /var/log/apt/history.log  monthly (12 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/apt/history.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-07 06:08
  log does not need rotating (log has been rotated at 2022-7-7 6:8, that is not month ago yet)
switching euid to 0 and egid to 0

rotating pattern: /var/log/boot.log
 after 1 days (7 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/boot.log
  log /var/log/boot.log does not exist -- skipping
switching euid to 0 and egid to 0

rotating pattern: /var/log/btmp  monthly (1 rotations)
empty log files are rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/btmp
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-02 04:23
  log does not need rotating (log has been rotated at 2022-7-2 4:23, that is not month ago yet)
switching euid to 0 and egid to 0

rotating pattern: /var/log/cups/*log  after 1 days (7 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/cups/access_log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-14 03:11
  log does not need rotating (log has been rotated at 2022-7-14 3:11, that is not day ago yet)
considering log /var/log/cups/error_log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-06 04:43
  log does not need rotating (log is empty)
not running postrotate script, since no logs were rotated
switching euid to 0 and egid to 0

rotating pattern: /var/log/dpkg.log  monthly (12 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/dpkg.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-07 06:08
  log does not need rotating (log has been rotated at 2022-7-7 6:8, that is not month ago yet)
switching euid to 0 and egid to 0

rotating pattern: /var/log/ppp-connect-errors  weekly (4 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/ppp-connect-errors
  log /var/log/ppp-connect-errors does not exist -- skipping
switching euid to 0 and egid to 0

rotating pattern: /var/log/syslog
 after 1 days (7 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/syslog
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-14 03:11
  log does not need rotating (log has been rotated at 2022-7-14 3:11, that is not day ago yet)
switching euid to 0 and egid to 0

rotating pattern: /var/log/mail.info
/var/log/mail.warn
/var/log/mail.err
/var/log/mail.log
/var/log/daemon.log
/var/log/kern.log
/var/log/auth.log
/var/log/user.log
/var/log/lpr.log
/var/log/cron.log
/var/log/debug
/var/log/messages
 weekly (4 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/mail.info
  log /var/log/mail.info does not exist -- skipping
considering log /var/log/mail.warn
  log /var/log/mail.warn does not exist -- skipping
considering log /var/log/mail.err
  log /var/log/mail.err does not exist -- skipping
considering log /var/log/mail.log
  log /var/log/mail.log does not exist -- skipping
considering log /var/log/daemon.log
  log /var/log/daemon.log does not exist -- skipping
considering log /var/log/kern.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-10 04:15
  log does not need rotating (log has been rotated at 2022-7-10 4:15, that is not week ago yet)
considering log /var/log/auth.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-10 04:15
  log does not need rotating (log has been rotated at 2022-7-10 4:15, that is not week ago yet)
considering log /var/log/user.log
  log /var/log/user.log does not exist -- skipping
considering log /var/log/lpr.log
  log /var/log/lpr.log does not exist -- skipping
considering log /var/log/cron.log
  log /var/log/cron.log does not exist -- skipping
considering log /var/log/debug
  log /var/log/debug does not exist -- skipping
considering log /var/log/messages
  log /var/log/messages does not exist -- skipping
not running postrotate script, since no logs were rotated
switching euid to 0 and egid to 0

rotating pattern: /var/log/speech-dispatcher/speech-dispatcher.log /var/log/speech-dispatcher/speech-dispatcher-protocol.log  after 1 days (7 rotations)
empty log files are rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/speech-dispatcher/speech-dispatcher.log
  log /var/log/speech-dispatcher/speech-dispatcher.log does not exist -- skipping
considering log /var/log/speech-dispatcher/speech-dispatcher-protocol.log
  log /var/log/speech-dispatcher/speech-dispatcher-protocol.log does not exist -- skipping
not running postrotate script, since no logs were rotated
switching euid to 0 and egid to 0

rotating pattern: /var/log/speech-dispatcher/debug-epos-generic /var/log/speech-dispatcher/debug-festival /var/log/speech-dispatcher/debug-flite  after 1 days (2 rotations)
empty log files are rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/speech-dispatcher/debug-epos-generic
  log /var/log/speech-dispatcher/debug-epos-generic does not exist -- skipping
considering log /var/log/speech-dispatcher/debug-festival
  log /var/log/speech-dispatcher/debug-festival does not exist -- skipping
considering log /var/log/speech-dispatcher/debug-flite
  log /var/log/speech-dispatcher/debug-flite does not exist -- skipping
not running postrotate script, since no logs were rotated
switching euid to 0 and egid to 0

rotating pattern: /var/log/ubuntu-advantage.log  monthly (6 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/ubuntu-advantage.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-02 04:23
  log does not need rotating (log has been rotated at 2022-7-2 4:23, that is not month ago yet)
switching euid to 0 and egid to 0

rotating pattern: /var/log/ufw.log
 weekly (4 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/ufw.log
  log /var/log/ufw.log does not exist -- skipping
not running postrotate script, since no logs were rotated
switching euid to 0 and egid to 0

rotating pattern: /var/log/unattended-upgrades/unattended-upgrades.log 
/var/log/unattended-upgrades/unattended-upgrades-dpkg.log
/var/log/unattended-upgrades/unattended-upgrades-shutdown.log
 monthly (6 rotations)
empty log files are not rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/unattended-upgrades/unattended-upgrades.log
  Now: 2022-07-14 05:27
  Last rotated at 2022-07-02 04:23
  log does not need rotating (log has been rotated at 2022-7-2 4:23, that is not month ago yet)
considering log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log
  Now: 2022-07-14 05:27
  Last rotated at 2021-11-04 22:20
  log needs rotating
considering log /var/log/unattended-upgrades/unattended-upgrades-shutdown.log
  Now: 2022-07-14 05:27
  Last rotated at 2021-10-22 05:00
  log does not need rotating (log is empty)
rotating log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log, log->rotateCount is 6
dateext suffix '-20220714'
glob pattern '-[0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9]'
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.6.gz to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.7.gz (rotatecount 6, logstart 1, i 6), 
old log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.6.gz does not exist
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.5.gz to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.6.gz (rotatecount 6, logstart 1, i 5), 
old log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.5.gz does not exist
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.4.gz to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.5.gz (rotatecount 6, logstart 1, i 4), 
old log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.4.gz does not exist
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.3.gz to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.4.gz (rotatecount 6, logstart 1, i 3), 
old log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.3.gz does not exist
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.2.gz to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.3.gz (rotatecount 6, logstart 1, i 2), 
old log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.2.gz does not exist
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.1.gz to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.2.gz (rotatecount 6, logstart 1, i 1), 
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.0.gz to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.1.gz (rotatecount 6, logstart 1, i 0), 
old log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.0.gz does not exist
log /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.7.gz doesn't exist -- won't try to dispose of it
renaming /var/log/unattended-upgrades/unattended-upgrades-dpkg.log to /var/log/unattended-upgrades/unattended-upgrades-dpkg.log.1
creating new /var/log/unattended-upgrades/unattended-upgrades-dpkg.log mode = 0644 uid = 0 gid = 4
compressing log with: /bin/gzip
switching uid to 0 and gid to 4
switching euid to 0 and egid to 0

rotating pattern: /var/log/wtmp  monthly (1 rotations)
empty log files are rotated, only log files >= 1048576 bytes are rotated, old logs are removed
switching euid to 0 and egid to 4
considering log /var/log/wtmp
  Now: 2022-07-14 05:27
  Last rotated at 2021-10-22 05:00
  log does not need rotating ('minsize' directive is used and the log size is smaller than the minsize value)
switching euid to 0 and egid to 0
mao@ubuntu:/var/log/cups$ 
```



强制进行日志轮替，不管是否符合轮替条件：

```sh
logrotate -vf /etc/logrotate.conf
```







## 日志分析工具



日志分析工具： logwatch

需要安装



CentOS：

```sh
yum -y install logwatch
```



ubuntu：

```sh
sudo apt install logwatch
```



```sh
mao@ubuntu:~/桌面$ sudo apt install logwatch
正在读取软件包列表... 完成
正在分析软件包的依赖关系树       
正在读取状态信息... 完成       
下列软件包是自动安装的并且现在不需要了：
  linux-headers-5.11.0-27-generic linux-hwe-5.11-headers-5.11.0-27 linux-image-5.11.0-27-generic
  linux-modules-5.11.0-27-generic linux-modules-extra-5.11.0-27-generic
使用'sudo apt autoremove'来卸载它(它们)。
将会同时安装下列软件：
  libdate-manip-perl postfix
建议安装：
  libsys-cpu-perl libsys-meminfo-perl procmail postfix-mysql postfix-pgsql postfix-ldap postfix-pcre
  postfix-lmdb postfix-sqlite sasl2-bin | dovecot-common resolvconf postfix-cdb postfix-doc
下列【新】软件包将被安装：
  libdate-manip-perl logwatch postfix
升级了 0 个软件包，新安装了 3 个软件包，要卸载 0 个软件包，有 142 个软件包未被升级。
需要下载 2,474 kB 的归档。
解压缩后会消耗 19.7 MB 的额外空间。
您希望继续执行吗？ [Y/n] y
获取:1 http://cn.archive.ubuntu.com/ubuntu focal/main amd64 libdate-manip-perl all 6.79-1 [908 kB]
获取:1 http://cn.archive.ubuntu.com/ubuntu focal/main amd64 libdate-manip-perl all 6.79-1 [908 kB]         
获取:2 http://cn.archive.ubuntu.com/ubuntu focal-updates/main amd64 postfix amd64 3.4.13-0ubuntu1.2 [1,201 kB]
获取:3 http://cn.archive.ubuntu.com/ubuntu focal-updates/main amd64 logwatch all 7.5.2-1ubuntu1.3 [366 kB] 
已下载 2,013 kB，耗时 2分 26秒 (13.8 kB/s)                                                                 
正在预设定软件包 ...
正在选中未选择的软件包 libdate-manip-perl。
(正在读取数据库 ... 系统当前共安装有 230613 个文件和目录。)
准备解压 .../libdate-manip-perl_6.79-1_all.deb  ...
正在解压 libdate-manip-perl (6.79-1) ...
正在选中未选择的软件包 postfix。
准备解压 .../postfix_3.4.13-0ubuntu1.2_amd64.deb  ...
正在解压 postfix (3.4.13-0ubuntu1.2) ...
正在选中未选择的软件包 logwatch。
准备解压 .../logwatch_7.5.2-1ubuntu1.3_all.deb  ...
正在解压 logwatch (7.5.2-1ubuntu1.3) ...
正在设置 postfix (3.4.13-0ubuntu1.2) ...
正在添加组"postfix" (GID 134)...
完成。
正在添加系统用户"postfix" (UID 127)...
正在将新用户"postfix" (UID 127)添加到组"postfix"...
无法创建主目录"/var/spool/postfix"。
Creating /etc/postfix/dynamicmaps.cf
正在添加组"postdrop" (GID 135)...
完成。
setting myhostname: ubuntu.localdomain
setting alias maps
setting alias database
mailname is not a fully qualified domain name.  Not changing /etc/mailname.
setting destinations: $myhostname, ubuntu, localhost.localdomain, , localhost
setting relayhost: 
setting mynetworks: 127.0.0.0/8 [::ffff:127.0.0.0]/104 [::1]/128
setting mailbox_size_limit: 0
setting recipient_delimiter: +
setting inet_interfaces: all
setting inet_protocols: all
/etc/aliases does not exist, creating it.
WARNING: /etc/aliases exists, but does not have a root alias.

Postfix (main.cf) is now set up with a default configuration.  If you need to 
make changes, edit /etc/postfix/main.cf (and others) as needed.  To view 
Postfix configuration values, see postconf(1).

After modifying main.cf, be sure to run 'systemctl reload postfix'.

Running newaliases
Created symlink /etc/systemd/system/multi-user.target.wants/postfix.service → /lib/systemd/system/postfix.se
rvice.
正在设置 libdate-manip-perl (6.79-1) ...
正在设置 logwatch (7.5.2-1ubuntu1.3) ...
正在处理用于 ufw (0.36-6) 的触发器 ...
正在处理用于 systemd (245.4-4ubuntu3.15) 的触发器 ...
正在处理用于 man-db (2.9.1-1) 的触发器 ...
正在处理用于 rsyslog (8.2001.0-1ubuntu1.3) 的触发器 ...
正在处理用于 libc-bin (2.31-0ubuntu9.7) 的触发器 ...
mao@ubuntu:~/桌面$ 
```





```sh
mao@ubuntu:~/桌面$ logwatch --help

Usage: /usr/sbin/logwatch [--detail <level>] [--logfile <name>] [--output <output_type>]
   [--format <format_type>] [--encode <encoding>] [--numeric]
   [--mailto <addr>] [--archives] [--range <range>] [--debug <level>]
   [--filename <filename>] [--help|--usage] [--version] [--service <name>]
   [--hostformat <host_format type>] [--hostlimit <host1,host2>] [--html_wrap <num_characters>]

--detail <level>: Report Detail Level - High, Med, Low or any #.
--logfile <name>: *Name of a logfile definition to report on.
--logdir <name>: Name of default directory where logs are stored.
--service <name>: *Name of a service definition to report on.
--output <output type>: Report Output - stdout [default], mail, file.
--format <formatting>: Report Format - text [default], html.
--encode <encoding>: Encoding to use - none [default], base64.
--mailto <addr>: Mail report to <addr>.
--archives: Use archived log files too.
--filename <filename>: Used to specify they filename to save to. --filename <filename> [Forces output to file].
--range <range>: Date range: Yesterday, Today, All, Help
                             where help will describe additional options
--numeric: Display addresses numerically rather than symbolically and numerically
           (saves  a  nameserver address-to-name lookup).
--debug <level>: Debug Level - High, Med, Low or any #.
--hostformat: Host Based Report Options - none [default], split, splitmail.
--hostlimit: Limit report to hostname - host1,host2.
--hostname: overwrites hostname
--html_wrap <num_characters>: Default is 80.
--version: Displays current version.
--help: This message.
--usage: Same as --help.
* = Switch can be specified multiple times...

mao@ubuntu:~/桌面$ 
```



安装完成之后，需要手工生成 logwatch 的配置文件。默认配置文件是 /etc/logwatch/conf/logwatch.conf，不过这个配置文件是空的，需要把模板配置文件复制过来

```sh
cp /usr/share/logwatch/default.conf/logwatch.conf /etc/logwatch/conf/logwatch.conf
```



```sh
mao@ubuntu:~/桌面$ cp /usr/share/logwatch/default.conf/logwatch.conf /etc/logwatch/conf/logwatch.conf
cp: 无法创建普通文件'/etc/logwatch/conf/logwatch.conf': 权限不够
mao@ubuntu:~/桌面$ sudo cp /usr/share/logwatch/default.conf/logwatch.conf /etc/logwatch/conf/logwatch.conf
[sudo] mao 的密码： 
mao@ubuntu:~/桌面$ 
```



```sh
mao@ubuntu:~/桌面$ cat -n /etc/logwatch/conf/logwatch.conf
     1	########################################################
     2	# This was written and is maintained by:
     3	#    Kirk Bauer <kirk@kaybee.org>
     4	#
     5	# Please send all comments, suggestions, bug reports,
     6	#    etc, to kirk@kaybee.org.
     7	#
     8	########################################################
     9	
    10	# NOTE:
    11	#   All these options are the defaults if you run logwatch with no
    12	#   command-line arguments.  You can override all of these on the
    13	#   command-line.
    14	
    15	# You can put comments anywhere you want to.  They are effective for the
    16	# rest of the line.
    17	
    18	# this is in the format of <name> = <value>.  Whitespace at the beginning
    19	# and end of the lines is removed.  Whitespace before and after the = sign
    20	# is removed.  Everything is case *insensitive*.
    21	
    22	# Yes = True  = On  = 1
    23	# No  = False = Off = 0
    24	
    25	# Default Log Directory
    26	# All log-files are assumed to be given relative to this directory.
    27	LogDir = /var/log
    28	
    29	# You can override the default temp directory (/tmp) here
    30	TmpDir = /var/cache/logwatch
    31	
    32	#Output/Format Options
    33	#By default Logwatch will print to stdout in text with no encoding.
    34	#To make email Default set Output = mail to save to file set Output = file
    35	Output = stdout
    36	#To make Html the default formatting Format = html
    37	Format = text
    38	#To make Base64 [aka uuencode] Encode = base64
    39	Encode = none
    40	
    41	# Input Encoding
    42	# Logwatch assumes that the input is in UTF-8 encoding.  Defining CharEncoding
    43	# will use iconv to convert text to the UTF-8 encoding.  Set CharEncoding
    44	# to an empty string to use the default current locale.  If set to a valid
    45	# encoding, the input characters are converted to UTF-8, discarding any
    46	# illegal characters.  Valid encodings are as used by the iconv program,
    47	# and `iconv -l` lists valid character set encodings.   
    48	# Setting CharEncoding to UTF-8 simply discards illegal UTF-8 characters.
    49	#CharEncoding = ""
    50	
    51	# Default person to mail reports to.  Can be a local account or a
    52	# complete email address.  Variable Output should be set to mail, or
    53	# --output mail should be passed on command line to enable mail feature.
    54	MailTo = root
    55	# WHen using option --multiemail, it is possible to specify a different
    56	# email recipient per host processed.  For example, to send the report
    57	# for hostname host1 to user@example.com, use:
    58	#Mailto_host1 = user@example.com
    59	# Multiple recipients can be specified by separating them with a space.
    60	
    61	# Default person to mail reports from.  Can be a local account or a
    62	# complete email address.
    63	MailFrom = Logwatch
    64	
    65	# if set, the results will be saved in <filename> instead of mailed
    66	# or displayed. Be sure to set Output = file also.
    67	#Filename = /tmp/logwatch
    68	
    69	# Use archives?  If set to 'Yes', the archives of logfiles
    70	# (i.e. /var/log/messages.1 or /var/log/messages.1.gz) will
    71	# be searched in addition to the /var/log/messages file.
    72	# This usually will not do much if your range is set to just
    73	# 'Yesterday' or 'Today'... it is probably best used with Range = All
    74	# By default this is now set to Yes. To turn off Archives uncomment this.
    75	#Archives = No
    76	
    77	# The default time range for the report...
    78	# The current choices are All, Today, Yesterday
    79	Range = yesterday
    80	
    81	# The default detail level for the report.
    82	# This can either be Low, Med, High or a number.
    83	# Low = 0
    84	# Med = 5
    85	# High = 10
    86	Detail = Low
    87	
    88	
    89	# The 'Service' option expects either the name of a filter
    90	# (in /usr/share/logwatch/scripts/services/*) or 'All'.
    91	# The default service(s) to report on.  This should be left as All for
    92	# most people.
    93	Service = All
    94	# You can also disable certain services (when specifying all)
    95	Service = "-zz-network"     # Prevents execution of zz-network service, which
    96	                            # prints useful network configuration info.
    97	Service = "-zz-sys"         # Prevents execution of zz-sys service, which
    98	                            # prints useful system configuration info.
    99	Service = "-eximstats"      # Prevents execution of eximstats service, which
   100	                            # is a wrapper for the eximstats program.
   101	# If you only cared about FTP messages, you could use these 2 lines
   102	# instead of the above:
   103	#Service = ftpd-messages   # Processes ftpd messages in /var/log/messages
   104	#Service = ftpd-xferlog    # Processes ftpd messages in /var/log/xferlog
   105	# Maybe you only wanted reports on PAM messages, then you would use:
   106	#Service = pam_pwdb        # PAM_pwdb messages - usually quite a bit
   107	#Service = pam             # General PAM messages... usually not many
   108	
   109	# You can also choose to use the 'LogFile' option.  This will cause
   110	# logwatch to only analyze that one logfile.. for example:
   111	#LogFile = messages
   112	# will process /var/log/messages.  This will run all the filters that
   113	# process that logfile.  This option is probably not too useful to
   114	# most people.  Setting 'Service' to 'All' above analyzes all LogFiles
   115	# anyways...
   116	
   117	#
   118	# By default we assume that all Unix systems have sendmail or a sendmail-like MTA.
   119	# The mailer code prints a header with To: From: and Subject:.
   120	# At this point you can change the mailer to anything that can handle this output
   121	# stream.
   122	# TODO test variables in the mailer string to see if the To/From/Subject can be set
   123	# From here with out breaking anything. This would allow mail/mailx/nail etc..... -mgt
   124	mailer = "/usr/sbin/sendmail -t"
   125	
   126	#
   127	# With this option set to a comma separated list of hostnames, only log entries
   128	# for these particular hosts will be processed.  This can allow a log host to
   129	# process only its own logs, or Logwatch can be run once per a set of hosts
   130	# included in the logfiles.
   131	# Example: HostLimit = hosta,hostb,myhost
   132	#
   133	# The default is to report on all log entries, regardless of its source host.
   134	# Note that some logfiles do not include host information and will not be
   135	# influenced by this setting.
   136	#
   137	#HostLimit = myhost
   138	
   139	#
   140	# By default /var/adm is searched after LogDir.
   141	#AppendVarAdmToLogDirs = 1
   142	
   143	#
   144	# By default /var/log is to be searched after LogDir and /var/adm/ .
   145	#AppendVarLogToLogDirs = 1
   146	
   147	#
   148	# By default the current working directory is searched last after LogDir, /var/adm/, and /var/log/ .
   149	#AppendCWDToLogDirs = 1
   150	
   151	# vi: shiftwidth=3 tabstop=3 et
mao@ubuntu:~/桌面$ 
```



```sh
LogDir = /var/log
#logwatch会分析和统计/var/log/中的日志

TmpDir = /var/cache/logwatch
#指定logwatch的临时目录

MailTo = root
#日志的分析结果，给root用户发送邮件

MailFrom = Logwatch
#邮件的发送者是Logwatch，在接收邮件时显示

Print =
#是否打印。如果选择“yes”，那么日志分析会被打印到标准输出，而且不会发送邮件。我们在这里不打印，#而是给root用户发送邮件
#Save = /tmp/logwatch
#如果开启这一项，日志分析就不会发送邮件，而是保存在/tmp/logwatch文件中
#如果开启这一项，日志分析就不会发送邮件，而是保存在/tmp/logwatch文件中

Range = yesterday
#分析哪天的日志。可以识别“All”“Today”“Yesterday”，用来分析“所有日志”“今天日志”“昨天日志”

Detail = Low
#日志的详细程度。可以识别“Low”“Med”“High”。也可以用数字表示，范围为0～10，“0”代表最不详细，“10”代表最详细

Service = All
#分析和监控所有日志

Service = "-zz-network"
#但是不监控“-zz-network”服务的日志。“-服务名”表示不分析和监控此服务的日志

Service = "-zz-sys"
Service = "-eximstats"
```



如果想要让这个日志分析马上执行，则只需执行 logrotate 命令即可。













# 启动管理

## 系统启动流程

1. 服务器加电，加载 BIOS 信息，BIOS 进行系统检测。依照 BIOS 设定，找到第一个可以启动的设备（一般是硬盘）；
2. 读取第一个启动设备的 MBR (主引导记录），加载 MBR 中的 Boot Loader（启动引导程序，最为常见的是 GRUB）。
3. 依据 Boot Loader 的设置加载内核，内核会再进行一遍系统检测。系统一般会采用内核检测硬件的信息，而不一定采用 Bios 的自检信息。内核在检测硬件的同时，还会通过加载动态模块的形式加载硬件的驱动。
4. 内核启动系统的第一个进程，也就是 /sbin/init。
5. 由 /sbin/init 进程调用 /etc/init/rcS.conf 配置文件，通过这个配置文件调用 /etc/rc.d/rc.sysinit 配置文件。而 /etc/rc.d/rc.sysinit 配置文件是用来进行系统初始化的，主要用于配置计算机的初始环境。
6. 还是通过 /etc/init/rcS.conf 配置文件调用 /etc/inittab 配置文件。通过 /etc/inittab 配置文件来确定系统的默认运行级别。
7. 确定默认运行级别后，调用 /etc/init/rc.conf 配置文件。
8. 通过 /etc/init/rc.conf 配置文件调用并执行 /etc/rc.d/rc 脚本，并传入运行级别参数。
9. /etc/rc.d/rc 确定传入的运行级别，然后运行相应的运行级别目录 /etc/rc[0-6].d/ 中的脚本。
10. /etc/rc[0-6].d/ 目录中的脚本依据设定好的优先级依次启动和关闭。
11. 最后执行 /etc/rc.d/rc.local 中的程序。
12. 如果是字符界面启动，就可以看到登录界面了。如果是图形界面启动，就会调用相应的 X Window 接口。





## BIOS开机自检

服务器通电后，会直接进入 BIOS，BIOS 全称 Basic Input/Output System

BIOS 的初始化主要完成以下 3 项工作：

1. 第一次检查计算机硬件和外围设备，例如 CPU、内存。当 BIOS 一启动，就会做一个自我检测的工作，整个自检过程也被称为 POST（Power On Self Test）自检。
2. 如果自检没有问题，BIOS 开始对硬件进行初始化，并规定当前可启动设备的先后顺序，选择由那个设备来开机。
3. 选择好开启设备后，就会从该设备的 MBR（主引导目录）中读取 Boot Loader（启动引导程序）并执行。启动引导程序用于引导操作系统启动，Linux 系统中默认使用的启动引导程序是 GRUB。





## initramfe虚拟文件系统

Initramfs 虚拟文件系统主要有以下优点：

- initramfs 随着其中数据的増减自动増减容量。
- 在 initramfs 和页面缓存之间没有重复数据。
- initramfs 重复利用了 Linux caching 的代码，因此几乎没有増加内核尺寸，而 caching 的代码已经经过良好测试，所以 initramfs 的代码质量也有保证。
- 不需要额外的文件系统驱动。





## /sbin/init

在内核加载完毕，并完成硬件检测与驱动程序加载后，此时主机硬件已经准备完毕，内核会主动呼叫第一个进程，也就是 /sbin/init，此配置文件最主要的功能就是准备软件执行的环境，包括系统的主机名、网络设定、语言、文件系统格式及其他服务的启动等。



/etc/rc.d/rc.sysinit 配置文件工作：

- 获得网络环境和主机类型；
- 测试设备：除了挂载内存设备 /proc 之外，还会主动侦测系统上是否具有 usb 设备，如果有，则会主动加载 usb 的驱动程序，并尝试挂载 usb 文件系统；
- 开机启动画面 Plymouth（代替了以往的 RHGB）；
- 判断是否启用 SELinux；
- 显示开机过程中的欢迎画面；
- 初始化硬件；
- 用户自定义模块的加载，用户可以在 /etc/sysconfig/modules/*.modules 加入自订的模块，则此时会被加载到系统当中；
- 配置内核的参数，系统会主动去读取 /etc/sysctl.conf 这个文件的配置参数，使内核的功能成为我们想要的样子。
- 设置主机名。
- 同步存储器。
- 设备映射器及相关的初始化。
- 初始化软件磁盘阵列 (RAID)。
- 初始化 LVM 的文件系统功能。
- 检验磁盘文件系统 (fsck)。
- 设置磁盘配额 (quota)。
- 重新以可读写模式挂载系统磁盘。
- 更新 quota (非必要)。
- 启动系统虚拟随机数生成器。
- 配置机器（非必要）。
- 清除开机过程中的临时文件。
- 创建 ICE 目录。
- 启动交换分区（swap）。
- 将开机信息写入 /var/log/dmesg 文件中。



## /etc/inittab

/etc/inittab 配置文件只能用来设置系统的默认运行级别



| 运行级别 |                            含 义                            |
| :------: | :---------------------------------------------------------: |
|    0     |                            关机                             |
|    1     | 单用户模式，可以想象为 Windows 的安全模式，主要用于系统修复 |
|    2     |              不完全的命令行模式，不含 NFS 服务              |
|    3     |             完全的命令行模式，就是标准字符界面              |
|    4     |                          系统保留                           |
|    5     |                          图形模式                           |
|    6     |                          重新启动                           |



查看运行级别：

```sh
runlevel
```



```sh
mao@ubuntu:~/桌面$ runlevel
N 5
mao@ubuntu:~/桌面$ 
```



N代表在进入这个级别前，上一个级别是什么；3代表当前级别。"N" 就是 None 的意思



改变当前的运行级别：

```sh
init 运行级别
```





**系统默认运行级别**：

/etc/inittab 配置文件的功能就是确定系统的默认运行级别





## GRUB

优势：

- 支持更多的文件系统。
- GRUB 的主程序可以直接在文件系统中查找内核文件。
- 在系统启动时，可以利用 GRUB 的交互界面编辑和修改启动选项。
- 可以动态修改 GRUB 的配置文件，这样在修改配置文件之后不需要重新安装 GRUB，而只需重新启动就可以生效。



GRUB 的作用：

- 加载操作系统的内核；
- 拥有一个可以让用户选择的的菜单，来选择到底启动哪个系统；
- 可以调用其他的启动引导程序，来实现多系统引导。







----

end

----

mao

2022  07  17

----





