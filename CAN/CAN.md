# CAN通信——电机控制
一种常用的无刷伺服电机控制（通信）方法  
现场总线
## CAN通信的基本原理

## CAN初始化参数

## CAN的配置方法实操
1. 首先是例行的基本配置：
   1. RCC->HSE  ->Crystal/Ceramic Resonator
   2. SYS->Debug->Serial Wire
2. 接下来配置CAN控制器参数  
   用到哪个CAN控制器x就是几  
    1. CANx->activate
       - 这里需要注意下引脚：大疆的C板上有两个CAN1输出，引脚为PD0\PD1,而STM32的CAN可选引脚有多条，因此在CubeMX配置中需要特别注意
    2. 设置CAN控制器参数（总线时钟为168M情况下，速率为1Mbps） %暂时还没弄懂
       - 预分频器Prescaler = 3
       - TBS1 = 10t
       - TBS2 = 3t
    3. 使能接收中断
3. 最后将上层驱动文件移植到自己的工程当中
   1. 将文件包复制到自己的工程路径下
   2. 将src即.c文件添加到项目树当中
   3. 将.h文件添加到IncludePath当中
   4. 添加预编译指令、初始化命令、主函数调用发送程序
4. 编译下试试吧