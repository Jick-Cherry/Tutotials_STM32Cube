# CAN通信——电机控制
一种常用的无刷伺服电机控制（通信）方法  
现场总线
## CAN通信的基本原理

## CAN初始化参数

## CAN的配置方法实操
首先是例行的基本配置：
1. RCC->HSE  ->Crystal/Ceramic Resonator
2. SYS->Debug->Serial Wire

接下来配置CAN控制器参数  
用到哪个CAN控制器x就是几  
3. CANx->activate