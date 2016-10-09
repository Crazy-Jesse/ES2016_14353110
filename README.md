##Description
  
 
##How to install   
###DOL 安装笔记
>1.首先是安装必要的环境
  
 	 $	sudo apt-get update
  
 	 $	sudo apt-get install ant
  
	 $ sudo apt-get install openjdk-7-jdk
  
 	 $	sudo apt-get install unzip
  
>2.下载文件
  	sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
  
  
>3.解压文件
  
  
  	新建dol的文件夹 
	$	mkdir dol
  
 	 将dolethz.zip解压到 dol文件夹中
	$	unzip dol_ethz.zip -d dol

	解压systemc
	$	tar -zxvf systemc-2.3.1.tgz
    
>4.编译systemc
  
	解压后进入systemc-2.3.1的目录下
	$	cd systemc-2.3.1
	新建一个临时文件夹objdir
	$	mkdir objdir
	进入该文件夹objdir
	$	cd objdir
	运行configure(能根据系统的环境设置一下参数，用于编译)
	$	../configure CXX=g++ --disable-async-updates

![after configure](https://github.com/Crazy-Jesse/ES2016_14353110/raw/master/DOL/2.PNG)

	$	sudo make install

![install1]( https://github.com/Crazy-Jesse/ES2016_14353110/raw/master/DOL/3.PNG)

![install2](https://github.com/Crazy-Jesse/ES2016_14353110/raw/master/DOL/4.PNG)


	记录当前的工作路径(会输出当前所在路径，记下来，待会有用)
	$	pwd
![pwd]( https://github.com/Crazy-Jesse/ES2016_14353110/raw/master/DOL/5.PNG)
这里表示我当前的工作路径为 home/ubantu/systemc-2.3.1

>5.编译dol
  
  
	进入刚刚dol的文件夹
	$	cd ../dol
修改build_zip.xml文件
找到下面这段话，就是说上面编译的systemc位置在哪里，
<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
把YYY改成上页pwd的结果即：home/ubantu/systemc-2.3.1
![build_zip.xml](https://github.com/Crazy-Jesse/ES2016_14353110/raw/master/DOL/9.PNG)

   再编译

   	$	ant -f build_zip.xml all
 ![build_zip.xml](https://github.com/Crazy-Jesse/ES2016_14353110/raw/master/DOL/6.PNG)

接着可以试试运行第一个例子
  
  
	进入build/bin/mian路径下
	$	cd build/bin/main
然后运行第一个例子
  
	$	ant -f runexample.xml -Dnumber=1
结果如下图
![第一个例子](https://github.com/Crazy-Jesse/ES2016_14353110/raw/master/DOL/7.PNG)


##Experimental experience   
###实验感想、实验心得 
    	这次实验是进行DOL配置。首先是需要配置虚拟机环境在配置过程中出现安装到中途因为C++缺失，通过sudo update g++来解决该问题，则可以从网上顺利下载并安装好。中间出现的问题并不是太多。按照PPT中的指导可以完成，没有什么大问题出现。与其他同学各种问题相比相当顺利。
       反而是在进行git实验时遇到了较多问题，例如在clone了之后的add操作是要进入文件夹里面，因为给出的知道是直接跟着的，所以一开始没有进文件夹就进行操作会一直报错。
       还有刚开始在没有对README.md进行改变时，无论如何更新，网页上的标志还是上一次初始化时的状态没有更新，进行指令commit还有push之后就是现实up-to-date，而网上显示的文件时间并没有改变。进行了多次实验依旧。最后是在同学提议下修改了readme.md的内容后再次实验，这次就会发生变化。这个地方折腾了很久时间。
        
