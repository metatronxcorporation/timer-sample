# Timer Sample GTK3

![images](https://user-images.githubusercontent.com/98597119/219901835-cc6a9f58-4935-483a-9c9c-059783ab1eb8.png)

## Install Eclipse on CentOS

* Enable snaps on CentOS and install Eclipse

* https://snapcraft.io/install/eclipse/centos

## The GTK Project 

* https://www.gtk.org/docs/installations/linux/

* Compiler Command GTK3

~]$ su -

~]# rpm -q centos-release

~]# yum makecache

~]# yum -y clean all

~]# yum -y install epel-release

~]# yum -y update

~]# yum -y upgrade

~]# yum -y install kernel-devel-$(uname -r)

~]# yum -y install make gcc kernel-headers kernel-devel perl dkms bzip2 binutils patch libgomp glibc-headers glibc-devel elfutils-libelf-devel

~]# yum -y install gcc-c++.x86_64 gtk3.x86_64 gtk-devel.x86_64 glib.x86_64 libsigc++20.x86_64 gtkmm30.x86_64 meson.noarch glade3.x86_64

~]# yum -y install vim wget unzip net-tools yum-utils htop NetworkManager-tui

~]# exit

~]$ vim timer-sample.c

* copy code to timer-sample.c

* https://github.com/metatroncorporation/timer-sample/blob/main/src/timer-sample.c

* Type key escape (esc) to exit
* save text in vim with :x

:x

~]$ gcc `pkg-config --cflags --libs gtk+-3.0` timer-sample.c -o timer-sample

~]$ ./timer-sample
