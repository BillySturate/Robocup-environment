#          			                               第二次培训(环境的搭建与Linux常用指令)

## 1.获得管理员权限

#### 1）进入root管理员模式

==sudo su root==

### 2)退出管理员模式

==exit==



## 2.重启和关机

### 1)重启

==init 6或 reboot==

### 2)关机

==init 0或halt==





## 3.清屏

### 1)清屏

==clear==

### 2)换页

==ctrl+l==



## 4.查看ip地址

==ip addr==

![ip](C:\Users\LH\Desktop\第二次培训\ip地址.png)





## 5.时间操作

### 查看时间

==date==





## 6.目录和文件

文件系统是像一棵树，树干是/(根)目录，树枝是子目录，树枝后面还有树枝(子目录中还有子目录)，树枝的最后是树叶，目录的最后是文件



![image.png](http://www.freecplus.net/runoobFiles/ueditor/image/20200502/1588381769799018485.png)

严谨的说，文件名是由**目录+文件名**组成的。

对于目录和文件，有一些约定的表述，我们以/usr/etc/readme.txt为例。

1）**全路径文件名**包含了完整的目录名和文件名，即/usr/etc/readme.txt，还有一个称呼是“**绝对路径文件名**”。

2）readme.txt是文件名，它在/usr/etc目录中。

3）目录和文件的**绝对路径**是从根（/）算起，在任何时候都不会有岐义。

4）登录Linux后，一定处在目录树的某个目录中，这个目录称之为当前工作目录，简称**当前目录**。

5）目录和文件的**相对路径**是从当前工作目录算起，如果当前工作目录是/usr，etc/readme.txt等同于/usr/etc/readme.txt；如果当前工作目录是/usr/etc，readme.txt等同于/usr/etc/readme.txt。

6）用Linux的命令操作目录和文件的时候，采用绝对路径和相对路径都可以。

7）一个圆点.表示当前工作目录；

8）两个圆点..表示当前工作目录的上一级目录。

**理解绝对路径和相对路径的概念非常重要，在日常操作中，绝对路径和相对路径会同时使用，但是我推荐大家尽量多使用绝对路径**



## 7.查看当前工作目录

==pwd==

![image.png](C:\Users\LH\Desktop\第二次培训\pwd.png)







## 8.改变当前工作目录

==cd目录名==

示例：

1）进入/tmp目录

==cd/tmp==

2）进入上一级目录

==cd ..==

3）进入用户的主目录

==cd==

## 9、列出目录和文件信息

==ls [-lt] 目录或文件名==

ls是list的缩写，通过ls 命令不仅可以查看目录和文件信息，还可以目录和文件权限、大小、主人和组等信息。

选项-l列出目录和文件的详细信息。

选项-lt列出目录和文件的详细信息，按时间降序显示。

示例：

1）列出当前工作目录下全部的目录和文件名信息。

==ls==

![image.png](C:\Users\LH\Desktop\第二次培训\ls.png)



2）列出当前工作目录下全部的目录和文件名详细的信息。

==ls -l==

![image.png](http://www.freecplus.net/runoobFiles/ueditor/image/20200502/1588381820246080796.png)





3）列出/lib目录下全部的目录和文件。

==ls /lib==

![image.png](C:\Users\LH\Desktop\第二次培训\lstmp.png)

4）正则表达式

正则表达式又称规则表达式、通配符，目录和文件名都支持正则表达式，正则表达式的规则比较多，在这里我只介绍最常用的两种：星号“*”和问号“?”。

星号“*”：匹配任意数量的字符。

问号“?”：匹配一个的字符。

5）列出/mnt/hgfs/freecplus目录下匹配*.h的目录和文件

![正则表达式](C:\Users\LH\Desktop\第二次培训\正则表达式.png)

## 10、创建目录

==mkdir 目录名==

示例：

1）在当前工作目录下创建aaa目录。

==mkdir aaa==

2）在当前工作目录的aaa目录下创建bbb目录。

==mkdir aaa/bbb==

3）创建/tmp/aaa目录。

==mkdir /tmp/aaa==



## 11、删除目录和文件

==rm [-r] 目录或文件列表==

选项-r可以删除目录，如果没有-r只能删除文件。

示例：

1）删除当前工作目录下匹配*.log的文件。

==rm *.log==

2）删除/tmp/aaa目录和文件。

==rm -r /tmp/aaa==



## 12、移动目录和文件

==mv 旧目录或文件名 新目录或文件名==

如果第二个参数是已经存在的目录，则把第一个参数（旧目录或文件名）移动到该目录中。

示例：

1）把当前工作目录中的book.c文件重命名为book1.c

==mv book.c book1.c==

2）如果/tmp/test3是一个已经存在的目录，以下命令将把当前工作目录下的book.c文件移动到/tmp/test3目录中。

==mv book.c /tmp/test3==

3）如果/tmp/test3目录不存在，以下命令将把当前工作目录下的book.c文件改名为/tmp/test3。

==mv book.c /tmp/test3==





## 13、复制目录和文件

==cp [-r] 旧目录或文件名 新目录或文件名==

选项-r可以复制目录，如果没有选项-r只能复制文件。

示例：

1）把当前工作目录下的book1.c文件复制为book2.c

==cp book1.c book2.c==

2）把当前工作目录下的aaa目录复制为bbb

==cp -r aaa bbb==

3）把当前工作目录下的book1.c文件复制为/tmp/book1.c

==cp book1.c /tmp/book1.c==

==cp book1.c /tmp/.==

以上两个命令的效果相同。

4）把当前工作目录下的aaa目录复制为/tmp/aaa

==cp -r aaa /tmp/aaa==

==cp -r aaa /tmp/.==

以上两个命令的效果相同。





## 14、打包压缩和解包解压 

tar命令用来打包压缩和解包解压文件，类似windows的winrar工具。

打包压缩的语法：

==tar zcvf 压缩包文件名 目录或文件名列表==

示例：

1）把当前工作目录的aaa、bbb和ccc目录打包压缩成123.tgz文件。

==tar zcvf 123.tgz aaa bbb ccc==

2）把/home/oracle/aaa、/home/oracle/bbb和/home/oracle/ccc目录打包压缩成/tmp/123.tgz文件。

==tar zcvf /tmp/123.tgz /home/oracle/aaa /home/oracle/bbb /home/oracle/ccc==

解包解压的语法：

tar zxvf压缩包文件名

示例：

1）把/tmp/123.tgz压缩包文件在当前工作目录下解压。

==tar zxvf /tmp/123.tgz==

2）把/tmp/123.tgz压缩包文件在/tmp/aaa目录下解压。

==cd /tmp/aaa==

==tar zxvf /tmp/123.tgz==



## 15、判断网络是否连通

==ping -c 包的个数 ip地址或域名==

ping用于确定本地主机是否能与另一台主机成功交换数据包，判断网络是否通畅。



## 16、显示文本文件的内容

显示文本文件的内容有两个命令：cat、more。

1）cat命令

==cat 文件名==

cat命令一次显示整个文件的内容。

==cat book1.c==

![](C:\Users\LH\Desktop\第二次培训\cat.png)



2）more命令

==more 文件名==

为了方便阅读，more命令分页显示文件的内容，按空格键显示下一页，按b键显上一页，按q键退出。

## 17、统计文本文件的行数、单词数和字节数

wc 文件名

示例：

1）统计当前工作目录处book2*.c文件的行数、单词数和字节数。

==wc book2*.c==

![image.png](http://www.freecplus.net/runoobFiles/ueditor/image/20200502/1588381947436056980.png)







## 18. 3d足球赛比赛环境的搭建

###1.查看本机wsl子系统的版本号

==wsl -l -v==



![](C:\Users\LH\Desktop\第二次培训\wsl.png)



### 2.导入命令

首先进入想要导入的目录，如图我在E盘中创建了wslstorage目录，将压缩包移到此目录下，打开cmd输入以下代码

==wsl --import ubuntu ./wsl ./Ubuntu.tar==

![](C:\Users\LH\Desktop\第二次培训\daoru.png)

### 3.注销wsl子系统

==wsl --unregister Ubuntu==



成功导入以后，我们就基本完成了比赛环境的搭建，这之后我们还需要一个roboviz，可以让我们用肉眼观察到仿真足球赛中发生的状况，详细的下载地址可以看学长的博客，上面写的很详细https://blog.flyme.tech/2020/11/29/robocup3d_wsl/



一切完成后我们就完成了环境的搭建

下面我给大家演示以下如何进入我们的比赛环境，在cmd中输入==wsl==命令进入wsl子系统，进入后，输入==rcsoccersim3d==命令，如下所示

![](C:\Users\LH\Desktop\第二次培训\cwrc.png)

接着打开roboviz，这样我们环境的搭建就完成了。















计科20-7刘浩 

2022.1.25







