# Ble-Nano 概述

![1](Ble-Nano_pic_zh/1.jpg)

## 产品简介

Ble-Nano是基于蓝牙4.0协议完美结合Arduino NanoV3.0由emakefun针对创客研发的一款革命性产品，功能和引脚完全兼容传统Arduino NanoV3.0主板，工作频段为2.4GHZ 范围，调制方式为 GFSK，最大发射功率为 0db，最大发射距离50米，采用进口原装TI CC2540芯片设计，支持用户通过AT命令修改查看设备名、服务UUID、发射功率、配对密码等指令，方便快捷使用灵活。产品身材却非常小，适合于很多对于体积有苛刻限制的应用。

我们提供Android和IOS手机demo，你可以快速开发出一款与手机通信的硬件设备。

正如现在非常火爆的可穿戴式手机周边设备，都可以用Ble-Nano这款平台开发，你可以使用Ble-Nano与蓝牙4.0设备连接，在两个蓝牙设备之间实现无线传输，主从机设置.甚至与PC建立蓝牙HID连接。同时我们为开发者提供了极大的自由度和支持准备，用户不仅可以通过AT指令调试Ble-Nano，你还可以在Ble-Nano控制器上添加Arduino兼容的扩展板、传感器、电机和舵机驱动等，emakefun独家研发蓝牙主机模式自动连接从机功能，并支持超过20个字节发送，使用更加方便。

## 产品参数  

* 与 Arduino Nano V3.0引脚和使用方法完全兼容  
* BLE芯片:TI CC2540
* 工作频道 2.4G
* 传输距离：空旷距离50m
* 支持AT指令配置BLE
* 支持USB虚拟串口，硬件串口,BLE三向透传 
* 支持主从机切换
* 主机模式下支持蓝牙自动连接从机
* 支持超过20byte发送,   自动分包  。
* 接口:Mirco-Usb
* 输入电压：Usb供电,Vin6~12V ，5V  
* 微处理器： ATmega328P-MU QFN32  
* Bootloader：最新Arduino1.8.8
* 引脚：两排2.54mm-15Pin
* 尺寸：   48mm x 19mm x 12mm  
* 重量： 18g

## 引脚说明

![2](Ble-Nano_pic_zh/2.jpg)

## 指示灯说明

* 当蓝牙未连接时蓝色灯光闪烁，连接后蓝色灯常亮
* 当有蓝牙数据通讯时或者usb有数据，或者Ble-Nano串口数据时绿色灯闪烁
* 当USB数据线连接成功时usb灯亮，如果连上usb后只有电源灯亮，但是usb指示灯不亮，代表这根USB-Micro线是坏的请更换

![3](Ble-Nano_pic_zh/3.jpg)

# Ble-Nano驱动安装准备

## Windows系统Ble-Nano驱动安装流程

1. 右键点击“我的电脑”-“属性”-“设备管理器”-查看“端口（COM和LT）”，如果看到如下图

![4](Ble-Nano_pic_zh/4.png)

则说明驱动已安装成功，这时我们打开IDE，在工具栏中选择对应的开发板型号和端口就正常使用了。如果出现如下图所示的界面，则说明电脑没有识别到开发板，需要自己安装驱动程序。



![5](Ble-Nano_pic_zh/5.png)



2. 右键单击“USB串行端口”并选择“更新驱动程序软件”选项



![7](Ble-Nano_pic_zh/7.png)



3. 点击“浏览计算机以查找驱动程序软件”



![8](Ble-Nano_pic_zh/8.png)



4. 再点击“浏览”



![9](Ble-Nano_pic_zh/9.png)



5. 选择驱动路径：“CC2540驱动\ ccxxxx_usb_cdc.inf”在点击“下一步”



![10](Ble-Nano_pic_zh/10.png)



6．弹出弹窗点击“始终安装此驱动程序软件”



![11](Ble-Nano_pic_zh/11.png)



​        此时，我们再返回“设备管理器”界面，可以看到电脑已成功识别到Arduino



![13](Ble-Nano_pic_zh/13.png)



此时，我们已经安装好了驱动，接下来我们安装Arduino IDE，安装好Arduino IDE就可以开始Arduino之旅了.



![12](Ble-Nano_pic_zh/12.png)



## Ble-Nano通过arduion IDE下载程序

Ble-Uno烧写最新版本Bootloader所以需要使用最新IDE（1.8.8版本以上）来烧写程序
请前往 [Arduino官网](https://www.arduino.cc/en/Main/Software)  下载最新IDE

选择处理器为 ATmega328P

![14](Ble-Nano_pic_zh/14.png)

1.选择开发板类型为Arduino/Nano

![15](Ble-Nano_pic_zh/15.png)



2.勾选对应的端口号



![16](Ble-Nano_pic_zh/16.png)



3.打开串口监视器输入AT



![17](Ble-Nano_pic_zh/17.png)

# Ble-Nano和电子设备连接

## Ble-Nano和安卓手机连接

1)	打开Arduino IDE，连接串口



![18](Ble-Nano_pic_zh/18.png)



<img src="Ble-Nano_pic_zh/19.png" alt="19" style="zoom:50%;" />

2)	测试AT指令，设置BLE-Nano的USB和蓝牙数据传输模式设置为USB串口数据和BLE透传

注意如果是其他串口助手一定要发送回车换行作为结束符。

![20](Ble-Nano_pic_zh/20.png)

![21](Ble-Nano_pic_zh/21.png)



3)	安卓或则IOS从设置中是无法连接使用的，因为手机设置都是只能连接经典蓝牙兼容蓝牙耳机，蓝牙麦克风等外设，不能连接低功耗蓝牙。安卓手机（android4.2以上）安装BLE_TOOL.apk (注意需要打开蓝牙，和定位权限)如下图操作



![22](Ble-Nano_pic_zh/22.png)

![23](Ble-Nano_pic_zh/23.png)



（IOS手机应用商城搜索安装LightBlue），打开测试APP,界面。找到对应的蓝牙名（Ble-Nano）并点击进行连接,连接，此时会出现4个选项，分别用于测试不同的功能，因为这里我们只测试蓝牙是否可以正常收发数据，所以我们选择SK Service入，再选择SK_KEYPRESSED

![24](Ble-Nano_pic_zh/24.png)



![25](Ble-Nano_pic_zh/25.png)

![26](Ble-Nano_pic_zh/26.png)



![27](Ble-Nano_pic_zh/27.png)



4)	我们选择“SK-KEYPRESSED”,点击后如图3.1.9我们可以看到有一个“写入”按键，点击即可进入，我们点击“红色框”即可输入想发送的数据，输入完成后点击“发送”即可将数据发出去

![28](Ble-Nano_pic_zh/28.png)



![29](Ble-Nano_pic_zh/29.png)



5)	点击发送后，我们可以看到串口监视器上打印出了手机端发送的内容，如图3.1.11示，说明蓝牙模块是可以正常发送数据的，当然，为了测试准确度更高，可以多测试几次，并尝试在不同的环境中测试。



![30](Ble-Nano_pic_zh/30.png)



6） 我们可以在串口监视器上输入想发送的内容，完成后点击“Send”，便可将数据通过蓝牙发送到手机APP上

在上面的测试过程中，PC端和安卓端都可正常收发数据，说明Ble-Nano通讯正常，达到预期的效果.



![31](Ble-Nano_pic_zh/31.png)

![32](Ble-Nano_pic_zh/32.png)




## Ble-Nano和苹果手机连接

1)	在APP store 中搜索LightBlue,下载软件LightBlue○RExplorer。



![33](Ble-Nano_pic_zh/33.png)

2)	安装APP后，打开APP扫描到BLE-NANO

![34](Ble-Nano_pic_zh/34.png)

![35](Ble-Nano_pic_zh/35.png)





3)	连接BLE-NANO蓝牙



![36](Ble-Nano_pic_zh/36.png)

4)	选择字符类型，并点击Write  new value，输入字符即可给BLE-NANO 发送数据。



![37](Ble-Nano_pic_zh/37.png)



![39](Ble-Nano_pic_zh/39.png)




## Ble-Nano和Win10蓝牙连接

同样道理win10的设置里面是无法和我们BLE-Nano连接的，它只能连接经典蓝牙，但是我们可以微软官方应用商城下载 BluetoothLEExplorer

![40](Ble-Nano_pic_zh/40.png)

先把板子usb和蓝牙开关打开

![41](Ble-Nano_pic_zh/41.png)

点击开始扫描

![42](Ble-Nano_pic_zh/42.png)



找到我们名字为Ble-Nano的设备，点击连接



![43](Ble-Nano_pic_zh/43.png)

我们选择字符特征码Characteristic1

![44](Ble-Nano_pic_zh/44.png)



Win10发送helloword给到Ble-Nano如下

![45](Ble-Nano_pic_zh/45.png)

Ble-Nano发送hellowin10

![46](Ble-Nano_pic_zh/46.png)


如果我们想通过win10自带蓝牙和Ble-Nano那么你需要基于Microsoft官方BLE SDK二次开发，请查看开发者说明
<https://docs.microsoft.com/zh-cn/windows/uwp/devices-sensors/gatt-server>
以及视频 <https://channel9.msdn.com/Events/Build/2017/P4177>
很幸运win10提供了专业的源代码请参考
<https://github.com/Microsoft/Windows-universal-samples/tree/master/Samples/BluetoothLE>
<https://github.com/Microsoft/BluetoothLEExplorer>
当然这是一个非常麻烦的事情，假如不是必要的话，强烈建议使用2块Ble-Nano设备来完成你的想法，详细参考后面章节《Ble-Nano结合Processing实际应用》

# AT指令介绍

## AT指令集

用户可以通过串口和 蓝牙芯片进行通信，串口使用Micro-USB数据线，波特率支持9600,19200,38400,57600,115200。串口默认波特率为9600bps。
（注：发AT指令时必须 回车换行， AT指令只能在模块未连接状态下才能生效，一旦蓝
牙模块与设备连接上，蓝牙模块即进入数据透传模式）



![47](Ble-Nano_pic_zh/47.png)

（AT指令区分大小写，均以回车、换行字符结尾：`\r\n`）

|序列  | 指令 | 作用 | 主从 |默认 |
|---- | ----| ----| ---- |---- |
|1 | AT+ALL	| 打印BLE配置所有的配置信息 | M/S |	|
|2 | AT+BAUD | 配置串口波特率	 | M/S	| 	9600 |
|3 | AT+PARITY | 设置串口校验位 | M/S	 | 	0 |
|4 | AT+STOPBIT | 设置串口停止位 | M/S | 	0 |
|5 |AT+NAME	配置蓝牙设备名字 |	M/S	 |	Ble-Uno |
|6 | 	AT+VER	 |查看BLE固件版本号 |	M/S |	V1.1 |
|7 |	AT+MAC	| 查看蓝牙12位mac地址	| S |  |
|8 |	AT+ROLE |	配置BLE主从模式 |	M/S	 | 1 |
|9 |	AT+SCAN |	扫描周边的蓝牙设备 |	M |  |
|10 |	AT+CONN	 |连接扫描结果对应下标的蓝牙	 |M |  |
|11 |	AT+CON |	连接对应Mac地址得蓝牙 |	M |  |
|12 |	AT+AUTOCON |	自动连接最近的从机蓝牙，重启生效 |	M |  |
|13 |	AT+DISCON |	断开当前的链接 | M |  |
|14 |	AT+AUTH	 | 设置蓝牙连接是否需要密码 | S | 0 |
|15 |	AT+PASS |	设置蓝牙连接密码 |	S  | 000000 |
|16 |	AT+ MODE |	设置蓝牙工作模式 |	M/S |	0 |
|17 |	AT+ BLEUSB | 设置蓝牙的USB和蓝牙数据传输模式 |	M/S | 0 |
|18 |	AT+ TXPOWER	 | 设置蓝牙发射功率 | M/S |	0 |
|19	| AT+MINI_INTERVAL |	设置BLE芯片最小通信间隔 |	M/S	 | 6 |
|20	| AT+MAX_INTERVAL |	设置BLE芯片最大通信间隔 |	M/S	 | 6  |
|21 |	AT+SRVUUID |	获取蓝牙特征码UUID |	M/S	 | 0xFFE0 |
|22 |	AT+CHARUUID |	获取字符特征码 |	M/S |	0xFFE1 |
|23 |	AT+RXGAIN |	设置BLE接收增益 |	M/S	 | 1 |
|24 |	AT+RESETR |	蓝牙设备软件重启 |	M/S |  |
|25 |	AT+SETTING |	系统设置 |	M/S |  |

## AT指令集详细说明

1、	测试指令

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT  |	+OK | 无 |

2、	打印Ble-Uno所有配置信息指令

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+ALL  | 详细配置信息 | 无 |

3、	配置串口波特率

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+BAUD=< Param >  | OK+Baud=< Param >+SUCCESS | 0:9600 <br> 1:19200 <br> 2:38400 <br> 3:57600 <br> 4:115200 |

4、	配置串口的校验位

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+PARITY=< Param >  |	OK+Parity=< Param >+SUCCESS  |	0:无 <br> 1:偶校验  <br> 2:奇校验 |

5、	配置串口的停止位

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+STOPBIT=< Param > |	OK+StopBit=< Param >+SUCCESS |	0:1位 <br> 1:2位 |

6、	配置蓝牙名字

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+NAME=< Param > |	OK+Name=< Param >+SUCCESS	 | 蓝牙名字 |

7、	查询Ble-Uno固件版本

| 指令 | 响应 | 参数 |
|---- | ----| ----|
| AT+VER | 	OK+Version=<  Result  > | 无 |

8、	查询蓝牙的Mac地址

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+MAC |	OK+Mac=< Result >	 | 无 |

9、	查询设置蓝牙主从模式

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+ROLE=< Param > |	OK+RoleMode=< Param >+SUCCESS | 0:主机 <br> 1:从机 |

10、	蓝牙主从模式下扫描附近从机

| 指令 | 响应 | 参数 |
|---- | ----| ----|
| AT+SCAN |	OK+Scan <br> OK+DISC[0]:xxxx <br> OK+DISC[1]:xxxx <br> …… <br> OK+SCAN DONE |	无 |

11、	通过扫描返回下标连接从机蓝牙

| 指令 | 响应 | 参数 |
|---- | ----| ----|
| AT+CONN=<  Param  > |	OK+CONN=< Param > |	扫描从机蓝牙下标数字 |

12、	通过连接主从蓝牙Mac地址连接从机蓝牙

| 指令 | 响应 | 参数 |
|---- | ----| ----|
| AT+CON=< Param > |	OK+CON=< Param > |	从机蓝牙地址 |

OK+Scan
OK+DISC[0]:3234CFE9D1C3
OK+DISC[1]:464288AEAB8F
OK+DISC[2]:3CA5080A62FB
OK+DISC[3]:30AEA42BF189
OK+DISC[4]:58803C6EFB0A
OK+SCAN DONE
AT+CONN=1代表连接扫描得到的第二个蓝牙设备
AT+CON=464288AEAB8F 直接连接Mac地址为464288AEAB8F的设备

13、	开启蓝牙自动连接模式    开启后，蓝牙模块将自动连接上次成功连接过的设备

| 指令 | 响应 | 参数 |
|---- | ----| ----|
| AT+AUTOCON=<  Param  >  | OK+AutoCon=<  Param  >+SUCCESS  |  0:关闭自动连接 <br> 1:开机自动连接  |

14、	断开当前连接蓝牙设备

| 指令 | 响应 | 参数 |
|---- | ----| ----|
| AT+DISCON |	OK+Disconnect |	无 |

15、	设置蓝牙的连接是否需要密码

| 指令 | 响应 | 参数 |
|---- | ----| ----|
| AT+AUTH=<  Param  >  | OK+AuthMode=< Param >+SUCCESS | 0:连接无密码 <br>1:需要密码连接 |

16、	设置蓝牙的连接是密码

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+ PASS=< Param > |	OK+ PassWord=< Param >+SUCCESS |  |

17、	设置蓝牙的工作模式

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+ MODE=< Param > |	OK+ WorkMode=< Param >+SUCCESS | 0:透传<br>1:驱动模式<br>2:iBeacon |

18、	设置蓝牙的USB和蓝牙数据传输模式

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+ BLEUSB=< Param > | OK+UsbBleTransmitMode=< Param >+SUCCESS |	0:关闭<br>1:USB串口数据传给BLE<br>2:BLE数据传给USB串口<br>3:USB串口数据和BLE透传 |

19、	设置蓝牙的发射功率

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+MINI_INTERVAL=< Param > |	OK+ Mini_Interval=< Param > +SUCCESS |	PC和Android，建议设为为10 <br> iOS设备，建议设置为20 |

20 设置BLE芯片最大通信间隔，以毫秒为单位

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+MINI_INTERVAL=< Param > |	OK+ Mini_Interval=< Param >+SUCCESS |	PC和Android，建议设为为10 <br>iOS设备，建议设置为20 |

21、设置BLE芯片最大通信间隔，以毫秒为单位

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+MAX_INTERVAL=< Param >	 | OK+Max_Interval=< Param >+SUCCESS |	PC和Android，建议设为为10 <br> iOS设备，建议设置为40 |

22、设置BLE接收增益

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+RXGAIN=< Param > |	OK+RxGain =< Param >+SUCCESS |	0：标准增益 <br>1：高增益 |

23、设置BLE特征码UUID

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+SRVUUID	 |Servic UUID=0XFFE0 |  |

24、设置BLE字符特征码
| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+CHARUUID |	Char UUID=0XFFE1 |  |

25、软件复位

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+RESETR | 无 |无 |

26、系统设置

| 指令 | 响应 | 参数 |
|---- | ----| ----|
|AT+SETTING=< Param >  | +SUCCESS | DEFAULT恢复出厂设置 <br> PARI_DEFAULT清除配对信息 |

## 开发说明

因为产品的蓝牙是透传功能，所以蓝牙编程，其实就是对arduino的串口(Serial)进行读写操作我们编程时需要注意两点
1、BLE协议规定每个蓝牙数据包长度不能超过20byte，我们蓝牙模块做了分包发送，但是有低概率丢包，所以超过20个字节的时候，arudino分包发送最为可靠。
2、每一包数据发送间隔需要超过150ms，否则容易丢包。

## Ble-Nano主从通讯以及结合Processing实际应用

很多时候我们是使用Ble-Nano和Processing来完成自己构想，那么最简单的方案如下图



![48](Ble-Nano_pic_zh/48.png)

Step1. usb连接从机(COM22)先读取到从机（COM21）的mac地址如下



![49](Ble-Nano_pic_zh/49.png)

Step2. Usb连接到主机Ble-Nano设置成主机（COM22）模式

![50](Ble-Nano_pic_zh/50.png)

Step3.把（COM21）自动连接功能打开方便下次上电可以直接连接

![51](Ble-Nano_pic_zh/51.png)



Step4. AT+BLEUSB=3 主机（COM22)把USB串口和蓝牙通讯功能打开这样蓝牙就可以和usb端口直接通讯

![52](Ble-Nano_pic_zh/52.png)



Step5. AT+CON加从机（COM21)mac地址即可直接连接

![53](Ble-Nano_pic_zh/53.png)




注意如果主机里面有其他程序会影响使用，建议主机arduino烧录一个空白程序进去主机接电脑会虚拟一个端口出来，在我的电脑 设备管理器可以查看到端口号，processing程序选择对应的端口号即可完成通讯


## 常见问题

**1)	问Ble-Nano和普通Nano板有何区别，我要如何开始使用这个开发板**

答： Ble-Uno是在原来官方arduino uno r3基础上添加CC2540蓝牙4.0功能
接口Mini-Usb升级成更加通用Micro-Usb接口，引脚功能完全兼容
Bootload烧写最新bootload需要使用1.8.8以上IDE才可以烧写，其他使用方法请参考官方arduino nano使用方法。

**2)	问：蓝牙如何手机电脑连接**
答： Ble-Nano为Ble设备，不能直接和手机设置里面蓝牙连接，需要通过BLETestTools.apk (IOS LightBlue)连接，如要开发参考源代码二次开发，windows的设置也是经典蓝牙连接方式，需要微软官网参考BLE SDK开发。


**3)	问：常见的蓝牙4.0之间通信不正常的问题。**

答：建议检查步骤：
1 更新固件至最新版本；
2 通过AT指令恢复出厂设置 (AT+SETTING=DEFAULT). （详见:通过AT指令配置BLE设备 ）
3 检查蓝牙模块、程序代码等相关地方的通信波特率是否一致；（晶振频率为8MHz的控制板支持最大38400bps的波特率。）
4.配对蓝牙设备是否支持4.0，还有CC2540和其他品牌蓝牙模组会存在兼容性问题，使用尽可能和CC25xx系类蓝牙模块连接

**4） 问：为什么我的手机连不上Ble-Nano，即使可以连上，但也不能通信？**

答：请检查您的手机是否支持蓝牙4.0。另外，请使用APP内的Scan按钮扫描连接Ble-Nano，连接不需要密码。不支持手机蓝牙设置界面、其他BLE APP连接。

**5）问：如何使用Ibeacon功能？**

答：不支持

**6）问：Ble-Nano支持多联吗？我想用一个主机连接很多从机，请问最多能连几个？**

答：Ble-Nano不支持多联，但是可以通过不断地切换绑定从机，实现多联的思想。

**7) 问：为什么Ble-Nano系列的蓝牙4.0产品无法连接蓝牙2.0的设备？**

答：由于我们的Ble-Nano系列为了实现极低的功耗，采用了单模蓝牙低功耗（Bluetooth Smart），硬件和软件上都做了优化，只能支持BLE，不支持连接蓝牙2.0设备。