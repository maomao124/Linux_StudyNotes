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





