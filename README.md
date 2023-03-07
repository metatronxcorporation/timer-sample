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

~]# yum -y clean all

~]# yum -y install epel-release

~]# yum makecache

~]# yum -y update

~]# yum -y upgrade

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

~]# yum -y install kernel-headers-$(uname -r)

~]# yum -y install kernel-devel-$(uname -r)

~]# yum -y install vim wget unzip net-tools yum-utils htop NetworkManager-tui

~]# yum -y install make gcc kernel-headers kernel-devel perl dkms bzip2 binutils patch libgomp glibc-headers glibc-devel elfutils-libelf-devel

~]# yum -y install gcc-c++.x86_64 gtk3.x86_64 gtk3-devel.x86_64 gtk3-devel-docs.x86_64 

~]# yum -y install glib.x86_64 libsigc++20.x86_64 gtkmm30.x86_64 meson.noarch glade3.x86_64

~]# exit

~]$ mkdir metatronlabs

~]$ ls

~]$ cd metatronlabs

~]$ pwd

/home/admin/metatronlabs

~]$ vim timer-sample.c

* copy code to timer-sample.c

* https://github.com/metatronxcorporation/timer-sample/blob/main/src/timer-sample.c

* Type key escape (esc) to exit
* save text in vim with :x

:x

* Check GTK3 Install

~]$ pkg-config --cflags --libs gtk+-3.0

* Compiler Command GTK3

![command](https://user-images.githubusercontent.com/98597119/219903758-cca0c95f-33b1-4d8c-9551-928e79cd0ad3.png)

* ADD ` in command at down.

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

~]# shutdown -r now

## Eclipse Marketplace

### Install Eclipse C/C++ IDE CDT 11.0 (2022-12) and The Complete Eclipse C/C++ IDE 11.0 (2022-12) 

* Menu: Help > Eclipse Marketplace -> Search > Find: CDT > Click Button, GO

### Install Pkg-config support for Eclipse CDT 1.0.0

* Menu: Help > Eclipse Marketplace -> Search > Find: pkg-config > Click Button, GO

### Configure Project Timer Sample GTK3 in Eclipse C/C++ IDE CDT

* Menu: Project > Properties > C/C++ Build > Settings -> Configuration: [All Configuration]

Guide > Tools Settings > GCC C++ Compiler 

Guide > Tools Settings > GCC C Compiler

Guide > Tools Settings > GCC C++ Linker

Guide > Tools Settings > GCC Assembler

* ADD Command:

Expert Settings:

Command line pattern: ${COMMAND} ${FLAGS} ${OUTPUT_FLAG} ${OUTPUT_PREFIX}${OUTPUT} ${INPUTS} ${EXTRA_FLAGS} `pkg-config --cflags --libs gtk+-3.0`

Obs:

ADD ` in command pkg-config --cflags --libs gtk+-3.0

Eg: 

![command](https://user-images.githubusercontent.com/98597119/219903758-cca0c95f-33b1-4d8c-9551-928e79cd0ad3.png)

![Screenshot from 2023-03-07 12-39-37](https://user-images.githubusercontent.com/98597119/223471728-c1f91f5e-40ce-4765-95fb-fa371b6ff53e.png)

* Menu: Project > Properties > C/C++ General > Paths and Symbols -> Configuration: [All Configuration]

Guide > includes > Languages: Assembly | Include directories: /usr/include/gtk-3.0/gtk

Guide > includes > Languages: GNU C | Include directories: /usr/include/gtk-3.0/gtk

Guide > includes > Languages: GNU C++ | Include directories: /usr/include/gtk-3.0/gtk

![Screenshot from 2023-03-07 12-36-23](https://user-images.githubusercontent.com/98597119/223470667-d4436f39-ba65-4fe4-b49f-c104ff8ba9fd.png)

* Build GTK3

![Screenshot from 2023-03-07 12-31-32](https://user-images.githubusercontent.com/98597119/223469466-516b2457-2b5e-48a2-9e3c-2cf8f0e13460.png)

* Run Timer Sample GTK3

![Screenshot from 2023-03-07 12-26-22](https://user-images.githubusercontent.com/98597119/223468169-caab85bf-680c-48d3-b325-cb604f285034.png)

### Students Reference Books

![-A1030-00-24-90-A103000249081-A103000249081-Lrg](https://user-images.githubusercontent.com/98597119/222013032-3fc830ac-8567-414e-8cb9-ed5dad5ce7be.jpg)

![-A1030-00-27-05-A103000270568-A103000270568-Lrg](https://user-images.githubusercontent.com/98597119/222013046-6572023b-36cb-450c-bbd5-52ec2ebbce45.jpg)

![-bigcovers-0134448235](https://user-images.githubusercontent.com/98597119/222013048-db3beaae-df63-4fad-97e1-57a9d1b208e6.jpg)

![1590597931 01 _SCLZZZZZZZ_SX500_](https://user-images.githubusercontent.com/98597119/222013678-b8d49069-c860-4b17-888f-c2b2046a95a0.jpg)

![-A1030-00-26-00-A103000260091-A103000260091-Lrg](https://user-images.githubusercontent.com/98597119/222013042-c2c77e73-8c7a-4091-961a-47f30fce8344.jpg)
