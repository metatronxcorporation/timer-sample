# Timer Sample GTK3

## Red Hat - CentOS

![images](https://user-images.githubusercontent.com/98597119/219901835-cc6a9f58-4935-483a-9c9c-059783ab1eb8.png)

## The GTK Project 

* https://docs.gtk.org/gtk3/index.html

![docs-gtk-linux](https://user-images.githubusercontent.com/98597119/219905386-9ad9f785-7f9d-40ad-ae70-693c0c44e146.svg)

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

~]$ pkg-config --cflags --libs gtk+-3.0

![command](https://user-images.githubusercontent.com/98597119/219903758-cca0c95f-33b1-4d8c-9551-928e79cd0ad3.png)

~]$ gcc `pkg-config --cflags --libs gtk+-3.0` timer-sample.c -o timer-sample

~]$ ./timer-sample

## Install eclipseIDE 2022-12 on CentOS

* Enable snaps on CentOS and install Eclipse

* https://snapcraft.io/install/eclipse/centos

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

### Install Pkg-config support for Eclipse CDT 1.0.0

* Menu: Help > Eclipse Marketplace -> Search -> Find - pkg-config - Click Button, GO

### Configure Project Timer Sample GTK3 in Eclipse C/C++ IDE CDT

* Menu: Project > Properties > C/C++ Build > Settings -> Configuration: [All Configuration]

* Guide > Tools Settings > GCC C++ Compiler 

* Guide > Tools Settings > GCC C Compiler

* Guide > Tools Settings > GCC C++ Linker

* Guide > Tools Settings > GCC Assembler

* ADD Command:

Expert Settings:

* Command line pattern: ${COMMAND} ${FLAGS} ${OUTPUT_FLAG} ${OUTPUT_PREFIX}${OUTPUT} ${INPUTS} ${EXTRA_FLAGS} `pkg-config --cflags --libs gtk+-3.0`

![Untitled](https://user-images.githubusercontent.com/98597119/221999119-fddd95b1-1e4e-4e53-9947-c1b78b0d5b4d.png)

ADD ` in command pkg-config --cflags --libs gtk+-3.0

Eg: 

![command](https://user-images.githubusercontent.com/98597119/219903758-cca0c95f-33b1-4d8c-9551-928e79cd0ad3.png)

* Menu: Project > Properties > C/C++ General > Paths and Symbols -> Configuration: [All Configuration]

* Guide > includes > Languages: Assembly | Include directories: /usr/include/gtk-3.0/gtk

* Guide > includes > Languages: GNU C | Include directories: /usr/include/gtk-3.0/gtk

* Guide > includes > Languages: GNU C++ | Include directories: /usr/include/gtk-3.0/gtk

![Untitledvv](https://user-images.githubusercontent.com/98597119/222009481-1d379bf2-1233-4056-9c70-bae4cef6f4a6.png)

