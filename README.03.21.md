# 第四周学习报告
* @Author 谢林枫
* @Date 20202.03.21
#### 这周的课程上的内容和讲座比较多，大多时间是花在课程内容的学习上。在家的学习效率不行，想学的内容会拖很长时间，在一些课余时间在网上看了stm32的一些很基础的内容包括
1. ARM处理器的设计，芯片的大概应用， 命名规范
2. 内核与存储器，时钟，复位和电源的管理，低功耗和ADC，DMA和i/o端口
3. 51的前边内容的重新学习
#### 之后想试试机器学习，但是学习好难，效率太低了想哭，，这周的总结大概是这样。疑问：32的学习要学得很基础还是先在整体上把握再去细学？


* [学习内容1](#1) | [学习内容2](#2) | [学习内容3](#3) | [学习内容4](#4)
# <a id='1'>学习内容1</a>
# 低功耗和ADC
## 低功耗
1. 睡眠，停机和待机模式
2. Vbat为RTC和后备寄存器供电（防止断电信息消失）
3. 3个模式的关掉功能和唤醒方式

| 工作模式 | 关掉功能 | 唤醒方式 | 
| ------ | ------ | ------ |
| 睡眠模式 | ARM内核 | 所有内部，外部功能的中断或事件 | 
| 停机模式 | ARM内核，内部所有功能，pll分频器，hse | 外部中断输入接口exti（16个i/o口之一）电源电压监控中断pvd，rtc闹钟到时usb唤醒信号 |
| 待机模式 | ARM内核，内部所有功能，pll分频器，hse，SRAM（存储器）内容消失 | mrst接口的外部复位信号，独立看门狗iwdg复位，专门唤醒wkup（wake up）引脚，rtc闹钟到时 |
## ADC(模拟/数字转换器)
* **2个12位模数转换器，1us转换时间（多达16个输入通道，设置能输入读取adc的转换值，在扫描模式下，自动进行数据的扫描读取，刷新数据）
1. 转换范围：0-3.6v **正常情况下要么输入0v，要么是3.3v,但adc能够帮助读取0-3.3v里面的内容**
2. 双采样和保持功能
3. 温度传感器（用adc去读去温度电阻的值，读取单片机的内部温度值）
4. ADC可以进行OMA操作（DMA能独立的进行一些数据的缓存，能让CPU空闲出来去干别的事情）
   
