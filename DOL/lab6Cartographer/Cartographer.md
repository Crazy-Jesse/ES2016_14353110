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
