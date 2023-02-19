# Timer Sample GTK3

## The GTK Project 

* https://www.gtk.org/docs/installations/linux/

## Red Hat - CentOS

![images](https://user-images.githubusercontent.com/98597119/219901835-cc6a9f58-4935-483a-9c9c-059783ab1eb8.png)

## Install eclipseIDE 2022-12 on CentOS

* Enable snaps on CentOS and install Eclipse

* https://snapcraft.io/install/eclipse/centos

## Accessing the command line using the console

~]$ sudo passwd root

~]$ su -

~]# rpm -q centos-release

~]# yum makecache

~]# yum -y clean all

~]# yum -y install epel-release

~]# yum -y update

~]# yum -y upgrade

~]# yum -y install vim wget unzip net-tools yum-utils htop NetworkManager-tui

~]# yum -y install make gcc kernel-headers kernel-devel perl dkms bzip2 binutils patch libgomp glibc-headers glibc-devel elfutils-libelf-devel

~]# yum -y install gcc-c++.x86_64 gtk3.x86_64 gtk-devel.x86_64 glib.x86_64 libsigc++20.x86_64 gtkmm30.x86_64 meson.noarch glade3.x86_64

~]# yum -y install kernel-devel-$(uname -r)

~]# yum -y install java-11-openjdk.x86_64 java-11-openjdk-devel.x86_64 java-11-openjdk-javadoc.x86_64 java-11-openjdk-headless.x86_64 java-11-openjdk-jmods.x86_64 java-11-openjdk-static-libs.x86_64

~]# readlink -f $(which java)

~]# export JAVA_HOME=$(readlink -f /usr/bin/java | sed "s:/jre/bin/java::")

~]# export PATH=$PATH:$JAVA_HOME/bin

~]# export CLASSPATH=.:$JAVA_HOME/jre/lib:$JAVA_HOME/lib:$JAVA_HOME/lib/tools.jar

~]# echo $JAVA_HOME

~]# ls -l $JAVA_HOME

~]# echo $PATH

* Note: Change Version Java

~]# alternatives --config java

~]# java -version

~]# yum -y install ant

~]# export ANT_HOME=/usr/share/ant

~]# echo $ANT_HOME

~]# ls -l $ANT_HOME

~]# export PATH=$PATH:$ANT_HOME/bin

~]# echo $PATH

~]# ant -version

~]# exit

~]$ vim timer-sample.c

* copy code to timer-sample.c

* https://github.com/metatroncorporation/timer-sample/blob/main/src/timer-sample.c

* Type key escape (esc) to exit
* save text in vim with :x

:x

* Compiler Command GTK3

![command](https://user-images.githubusercontent.com/98597119/219903758-cca0c95f-33b1-4d8c-9551-928e79cd0ad3.png)

~]$ gcc `pkg-config --cflags --libs gtk+-3.0` timer-sample.c -o timer-sample

~]$ ./timer-sample

## EclipseIDE 2022-12

~]$ su - 

~]# yum install snapd

~]# systemctl enable --now snapd.socket

~]# ln -s /var/lib/snapd/snap /snap

~]# snap install eclipse --classic

~]# exit

## Eclipse Marketplace

### Install Eclipse C/C++ IDE CDT and The Complete Eclipse C/C++ IDE 11.0

* Menu: Help > Eclipse Marketplace -> Search -> Find - CDT - Click Button, GO
