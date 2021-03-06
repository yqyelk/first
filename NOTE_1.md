# NOTE

###        定时器的分类？

​       定时器按位置可分为外设定时器和内核定时器；内核定时器有系统节拍定时器，外设定时器按功能可分为常规定时器和专用定时器；其中常规定时器分为高级定时器、通用定时器和基本定时器，而专用定时器可分为看门狗定时器、实时时钟和低功耗时钟。

###        高级定时器、通用定时器和基本定时器之间的区别？

​        基本定时器几乎没有任何输入/输出通道，常用作时基，实现基本的定时、计数功能。

​        通用定时器具备多路独立的捕获和比较通道，可以完成定时/计数、输入捕获、输出比较等功能。

​        高级定时器除具备通用定时器的功能外，还具备带死区控制的互补信号输出、紧急刹车关断输入等功能，可用于电机控制和数字电源设计。

###         基本定时器，通用定时器，高级定时器分别有哪些？

​       基本定时器：TIM6/7

​       通用定时器：TIM1/8

​       高级定时器：TIM2/5 3/4 10/11 9

###         查阅参考手册或教材系统时钟部分，解释整个时钟树的结构：

##### 系统时钟SYSCLK可以由哪些时钟源提供？

HSI 高速内部时钟(内部RC振荡)
HSE 高速外部时钟，接石英/陶瓷谐振器或者接外部时钟源
LSI 低速时钟，内部接RC振荡器
LSE 低速外部时钟，接石英晶体
PLL 锁相环倍频输出，其时钟输入源可选择为HSI/2、HSE或者HSE/2。倍频可选择为2~16倍，但是其输出频率最大不得超过72MHz。

##### 如何由系统时钟SYSCLK得到总线时钟HCLK？

​    系统时钟 SYSCLK 经过 AHB 预分频器分频之后得到总线时钟HCLK

##### STM32内部有哪些时钟总线?每条总线上挂载哪些外设?

​    外设总线时钟APB1  挂载TIM2/3/4/5
​    外设总线时钟APB2 挂载TIM1/9/10/11

###     查阅参考手册或教材定时器部分，解释以下概念:

#####     定时器时钟源

​    产生固定频率脉冲的器件

#####     计数器时钟

​    在计时脉冲控制下，用来统计时钟脉冲的个数的器件

#####     计数器

​    对周期固定或不固定的脉冲信号进行计数的器件

#####     自动重载寄存器

​    为计数器设置计数边界或重载值的器件

###     如何计算定时时间？

​    定时时间=计数值*计数周期
​    定时时间=计数值/计数频率
