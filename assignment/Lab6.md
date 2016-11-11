# Lab5. ROS.md


##参考网站(http://wiki.ros.org/jade/Installation/Ubuntu)

        目录

    1.Ubuntu install of ROS Jade
        Installation
        Configure your Ubuntu repositories
        Setup your sources.list
        Set up your keys
        Installation
        Initialize rosdep
        Environment setup
        Getting rosinstall
        Build farm status
    2.Tutorials
        Obtain source code of the installed packages
 

###1. 安装
>1.1Configure your Ubuntu repositories
    
    Configure your Ubuntu repositories
    Configure your Ubuntu repositories to allow "restricted," "universe," 
    and "multiverse." You can follow the Ubuntu guide for instructions on
    doing this.
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/1.PNG)
>1.2Setup your sources.list

        sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/2.PNG)
    
>1.4Installation
      
        sudo apt-get update
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/3.PNG)
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/4.PNG)
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/5.PNG)
    
        sudo apt-get install ros-jade-desktop-full
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/6.PNG)
    
>1.5Initialize rosdep

        sudo rosdep init
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/7.PNG)
        rosdep update
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/8.PNG)
         
>1.6Environment setup

        echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
        source ~/.bashrc
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/9.PNG)
     
>1.7Getting rosinstall

        sudo apt-get install python-rosinstall
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/10.PNG)
     .
     .
     .
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab5ROS/11.PNG)
     
>1.8Build farm status
        不知道怎么看。。


# Lab6. cartographer.md


##参考网站(http://google-cartographer-ros.readthedocs.io/en/latest/)

       

###Building & Installation
> Install wstool and rosdep.

        sudo apt-get update
        sudo apt-get install -y python-wstool python-rosdep ninja-build
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/1.PNG)
> Create a new workspace in 'catkin_ws'.

        mkdir catkin_ws
        cd catkin_ws
        wstool init src
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/2.PNG)

> Merge the cartographer_ros.rosinstall file and fetch code for dependencies.

        wstool merge -t src https://raw.githubusercontent.com/googlecartographer/cartographer_ros/master/cartographer_ros.rosinstall
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/3.PNG)
    
        wstool update -t src
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/4.PNG)

> Install deb dependencies.

    rosdep init
>可能会出现如图的情况,直接进行更新操作
![p1](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/p1.PNG)
        rosdep update
    
![5](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/5.PNG)
        rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y
    若成功如图所示
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/6.PNG)

> Build and install.

        catkin_make_isolated --install --use-ninja
在安装途中出现了这个问题
![p2](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/7.PNG)
经过询问此步骤需要进行翻墙，所以暂时停止在这个步骤。
        source install_isolated/setup.bash
        
##此时更换按照新的教程进行安装
>###1.首先安装ceres solver，选择的版本是1.11,路径随意

    1.     git clone https://github.com/hitcm/ceres-solver-1.11.0.git
![new_1](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_1.PNG)

    2.      cd ceres-solver-1.11.0/build
>在ceres-solver-1.11.0中间一个叫build文件夹才能继续
   
    3.      cmake ..
![new_2](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_2.PNG)

![new_3](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_3.PNG)
   
    4.      make 
>成功后最后显示如图

![new_4](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_4.PNG)

    5.      
>成功ing后显示如图
![new_5](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_5.PNG)

![new_6](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_6.PNG)

>###2.然后安装 cartographer,路径随意
    1.      git clone https://github.com/hitcm/cartographer.git
![new_7](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_7.PNG)
    
    2 .     cd cartographer/build 
>需要自己在该文件夹下新建bulid文件夹

    3.       cmake .. -G Ninja 
![new_8](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_8.PNG)

![new_9](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_9.PNG)
    4.       ninja 
![new_10](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_10.PNG)
    5.       ninja test 
>成功后最后显示如图

![new_11](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_11.PNG)
    
    6.       sudo ninja install 
    
>成功后最后显示如图

![new_12](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_12.PNG)

>###3.安装cartographer_ros。
>下载到catkin_ws下面的src文件夹下面 
    cd catkin_ws/的src
    git clone https://github.com/hitcm/cartographer_ros.git
    
![new_13](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_13.PNG)

    catkin_ws下面运行catkin_make
    
>成功后最后显示如图
![new_14](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab6Cartographer/new_14.PNG)

>这个实验就到了这里停下了。。

##实验感想
        这次实验是安装ROS与cartographer。在安装时，ROS的进行比较顺利，根据给出的参考网站
    按照给出的步骤进行即可，没有遇上什么问题。但是在安装cartographer时，进行到build和
    instal时出现问题，无法访问到给出的网站，进行尝试登入时发现网站为外网，需要翻墙才能得
    到相应的数据。所以后来是需要根据一个新的安装教程进行安装的。
        在步骤cd ceres-solver-1.11.0/build时出现错误，是需要找到这个 ceres-solver-1.11.0
    文件，然后再在里面新建一个build文件夹，然后才能继续进行。第四步教程中使用的是make -j
    但是这个指令会报错，所以使用make即可。但是最大的问题出现在了下载包，第一个500m的还是
    能正常下载但是另外一个包足足有8个G就出现问题了。暂时无法继续进行该安装实验。
