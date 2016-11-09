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

