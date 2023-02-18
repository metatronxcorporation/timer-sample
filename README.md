# Timer Sample GTK3

![images](https://user-images.githubusercontent.com/98597119/219901835-cc6a9f58-4935-483a-9c9c-059783ab1eb8.png)

## Install Eclipse on CentOS

* Enable snaps on CentOS and install Eclipse

https://snapcraft.io/install/eclipse/centos

## The GTK Project 

* https://www.gtk.org/docs/installations/linux/

* Compiler Command GTK3

~]$ su -

~]# yum makecache

~]# yum -y install gcc-c++.x86_64 gtk3.x86_64 gtk-devel.x86_64 glib.x86_64 libsigc++20.x86_64 gtkmm30.x86_64 meson.noarch glade3.x86_64  

~]$ gcc `pkg-config --cflags --libs gtk+-3.0` timer-sample.c -o timer-sample

~]$ ./timer-sample
