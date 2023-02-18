# Timer Sample GTK3

* Install Eclipse on CentOS

## Enable snaps on CentOS and install Eclipse

https://snapcraft.io/install/eclipse/centos

## Compiler Command GTK3

~]$ su -

~]# yum makecache

~]# yum -y install gcc-c++.x86_64 gtk3.x86_64 gtk-devel.x86_64 glib.x86_64 libsigc++20.x86_64 gtkmm30.x86_64 meson.noarch glade3.x86_64  

~]$ gcc `pkg-config --cflags --libs gtk+-3.0` timer-sample.c -o timer-sample

~]$ ./timer-sample
