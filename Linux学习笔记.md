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

