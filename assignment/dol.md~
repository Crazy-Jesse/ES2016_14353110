# Lab3 assignment dol.md


##1. 改完的*.dot截图 
####修改example2，让3个square模块变成2个
![]()
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab3/example2.PNG)
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab3/%E8%BF%90%E8%A1%8C2.PNG)
####修改example1，使其输出3次方数
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab3/%E8%BF%90%E8%A1%8C1.PNG)
![](https://github.com/Crazy-Jesse/ES2016_14353110/blob/master/DOL/lab3/example1.PNG)
##2. 具体如何修改的解释
>修改example2，让3个square模块变成2个
    
    修改xml的iterator,找到定义模块数量的位置
    将variable value 等于3修改为2 这样之后进行的迭代次数就是两次
>修改example1，使其输出3次方数，tips:修改square.c
    
    square.c中有行代码是DOL_read((void*)PORT_OUT,&i,sizeof(float),p);
    下是定义了i=i*i做了个平方，我们要实现三次方，就将i=i*i*i就可以实现三次方的。
##3. 实验感想
    
    本次实验主要是看懂代码，其实需要修改的部分不多，关键是要看懂代码的分类，不同文件的含义（生产者，消费者，处理模块等）的功能定义
    /src 文件夹内包含2种文件：*.c, 与对应的.h，就是实现的模块，就是*.dot的框框的功能描述。（每个模块要实现2个接口，xxx_init和xxx_fire两个函数，分别是初始化这个模块是干了什么，以及这个模块开干的时候做什么）
    ./example*.xml 里面定义了模块与模块之间是怎么连接的，就是有哪些框，哪些线，比如A框跟B框用一根线连起来，他们就在一起了。嗯，他们。
    这个xml是这样的：process就是那些框, sw_channel那些线, connection就是把线的那头连到框的那头。
    运行example1之后的dot图，其中包含生产者、平方模块、消费者
    src里面，对应gennerator这个模块的代码就是gennerator.h, generator.c
    还有各种进程的定义，不同函数代表的意义等等。实现修改的部分提示还是比较明显和易懂的。所以还是比较好完成的。

