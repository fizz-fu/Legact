<!--
源文件：用户上传的 RPPS-200 用户手册 PDF，共14页。
本文直接转换原文，不改型号、参数、原有措辞或测试结论。
正文和4张表格可编辑；合并单元格使用 Markdown 内嵌 HTML table 实现。
图片均来自原PDF。请将 README.md 与 images 文件夹放在同一目录。
GitHub会使用自己的字体、表格主题和间距；不会完整保留PDF固定页高和背景色。
如需按原PDF版面阅读，请打开同目录的“原版式阅读.md”（页内内容为图片）。
-->

<!-- PDF page 01 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

<h1 align="center">RPPS-200<br>用户手册</h1>

<br><br>
<p align="center">
  <img src="images/figures/cover-product.png" alt="RPPS-200 传感器与采集模块" width="230" align="middle">
  &emsp;
  <img src="images/figures/cover-heatmap.png" alt="RPPS-200 热力图" width="150" align="middle">
</p>
<br><br>

---

语言：简体中文  
固件版本：V1.0  
LEGACT RPPS-200测试软件版本：V1.0

---

<!-- PDF page 02 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

<h1 align="center">目录</h1>

<p>
修改记录................................................................................01<br>
1. 产品简介............................................................................02<br>
2. 产品外观............................................................................02<br>
3. 产品规格............................................................................03<br>
　　3.1 产品基本性能参数 .........................................................03<br>
　　3.2 传感器结构尺寸图 .........................................................04<br>
　　3.3 采集模块尺寸视图 .........................................................04<br>
4. 通信协议............................................................................05<br>
　　4.1 串口配置参数 ................................................................05<br>
　　4.2 数据结构 ......................................................................05<br>
5. 产品使用步骤 ....................................................................06<br>
6. 软件连接............................................................................07<br>
7. 上位机使用说明.................................................................09<br>
8. 注意事项............................................................................11<br>
9. 常见问题............................................................................11<br>
10. 更多帮助..........................................................................12
</p>

---

<!-- PDF page 03 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

<h2 align="center">修改记录</h2>

<table border="1" cellspacing="0" cellpadding="8" width="100%">
  <thead>
    <tr bgcolor="#54BEDF">
<th align="center">版本</th>
<th align="center">修订日期</th>
<th align="center">修订人员</th>
<th align="center">修订内容</th>
</tr>
  </thead>
  <tbody>
    <tr>
<td align="center">V1.0</td>
<td align="center">26/03/31</td>
<td align="center">FQH</td>
<td align="center">开始版本</td>
</tr>
    <tr>
<td align="center">V1.1</td>
<td align="center">26/05/19</td>
<td align="center">LSY</td>
<td align="center">用户手册排版</td>
</tr>
  </tbody>
</table>

<p align="center">01</p>

---

<!-- PDF page 04 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

## 1. 产品简介

RPPS-200是基于FS-ARR-10X20-P1.5薄膜压力分布传感器的压力感知系统，主要应用于机器人夹爪或手指指腹等场景，可对夹持过程中的接触分布、压力变化、受力中心偏移及滑移趋势进行可视化与数据记录。整个系统的结构示意图如下所示：

<p align="center">
  <img src="images/figures/system-overview.png" alt="系统结构示意图" width="720">
</p>

<p align="center">图1-1 系统结构示意图</p>

该系统配备一个拥有200个感应点的薄膜压阻传感器，搭配力感科技自研的采集模块，输出TTL电平信号，经CH340或CP2102（USB转TTL模块）转换与PC端通信；并提供一款方便用户测试的上位机，可实时显示各个感应点的AD值或热力图像，还支持压力中心点、压力中心点轨迹、滑移方向矢量以及标尺显示。

## 2. 产品外观

<p align="center">
  <img src="images/figures/product-appearance.png" alt="实物连接图" width="500">
</p>

<p align="center">图2-1 实物连接图</p>

<p align="center">02</p>

---

<!-- PDF page 05 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

## 3. 产品规格

### 3.1 产品基本性能参数

本公司生产的传感器均符合RoHS标准，产品部分性能参数如下：

<table border="1" cellspacing="0" cellpadding="8" width="100%">
  <thead>
    <tr bgcolor="#54BEDF">
<th align="center">类型</th>
<th align="center">名称</th>
<th align="center">详细参数</th>
</tr>
  </thead>
  <tbody>
    <tr bgcolor="#D5EDF3">
<td rowspan="14" align="center" valign="middle" bgcolor="#FFFFFF">传<br><br>感<br><br>器</td>
<td>厚度</td>
<td>0.3mm</td>
</tr>
    <tr>
<td>样式</td>
<td>薄片状</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>触发力</td>
<td>5g</td>
</tr>
    <tr>
<td>压力范围</td>
<td>5g~1200g或更大，单感应点</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>压力作用方式</td>
<td>按压</td>
</tr>
    <tr>
<td>未触发时电阻</td>
<td>大于20MΩ</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>使用温度</td>
<td>-20℃~+65℃</td>
</tr>
    <tr>
<td>重复精度</td>
<td>+/-5%@1Kg,单个</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>漂移</td>
<td>-10%，24H@1Kg</td>
</tr>
    <tr>
<td>迟滞</td>
<td>10%，24H@1Kg</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>耐久性</td>
<td>100万次以上,1Kg力</td>
</tr>
    <tr>
<td>响应时间</td>
<td>&lt;10us</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>电磁干扰EMI</td>
<td>不产生</td>
</tr>
    <tr>
<td>静电释放EDS</td>
<td>不敏感</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td rowspan="3" align="center" valign="middle" bgcolor="#FFFFFF">采集<br>模块</td>
<td>连接器(与传感器)</td>
<td>FPC 翻盖式 下接 30Pin 间距:0.5mm</td>
</tr>
    <tr>
<td>采集模块尺寸</td>
<td>21*25*1.6(mm)</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>连接器(与转换模块）</td>
<td>SM04B-GHS-TB(LF)(SN)</td>
</tr>
    <tr>
<td rowspan="2" align="center" valign="middle" bgcolor="#FFFFFF">电学<br>参数</td>
<td>供电电压</td>
<td>5.0V</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>MCU工作电压</td>
<td>3.3V</td>
</tr>
    <tr>
<td rowspan="2" align="center" valign="middle" bgcolor="#FFFFFF">通信<br>接口</td>
<td>编程/调试接口</td>
<td>SWD烧录</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td>数据通信接口</td>
<td>UART通信</td>
</tr>
  </tbody>
</table>

<p align="center">表3-1 RPPS-200基本性能参数列表</p>

<p align="center">03</p>

---

<!-- PDF page 06 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

### 3.2 传感器结构尺寸图

感应区域面积：30(mm)x15(mm)

<p align="center">
  <img src="images/figures/sensor-dimensions.png" alt="FS-ARR-10X20-P1.5尺寸视图" width="740">
</p>

<p align="center">图3-2 FS- ARR-10X20-P1.5尺寸视图</p>

### 3.3 采集模块结构尺寸图

尺寸大小：21\*25\*1.6(mm)

<p align="center">
  <img src="images/figures/module-dimensions.png" alt="采集模块尺寸视图" width="350">
</p>

<p align="center">图3-3 采集模块尺寸视图</p>

<p align="center">04</p>

---

<!-- PDF page 07 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

## 4. 通信协议

### 4.1 串口配置参数

使用串口调试助手或其它上位机读取数据前请先确保串口配置参数一致，否则无法正确连接。

<table border="1" cellspacing="0" cellpadding="8" width="360" align="center">
  <tbody>
    <tr bgcolor="#D5EDF3">
<td align="center">波特率</td>
<td align="center">460800</td>
</tr>
    <tr>
<td align="center">数据位</td>
<td align="center">8 bits</td>
</tr>
    <tr bgcolor="#D5EDF3">
<td align="center">停止位</td>
<td align="center">1 bit</td>
</tr>
    <tr>
<td align="center">校验位</td>
<td align="center">无</td>
</tr>
  </tbody>
</table>

<p align="center">表4-1 串口配置参数</p>

### 4.2 数据结构

完整一帧共432个字节：前 430 字节为有效数据区，为10 行 × 43 字节样式；每行格式固定为 [0xFF][0xFE][行号] + 40 字节数据，其中行号为 0~9。在这 430 个字节末尾追加2 字节校验，校验方式为 16-bit 字节累加和，并以低字节在前、高字节在后的方式存放，用于校验整帧数据的完整性。

<table border="1" cellspacing="0" cellpadding="8" width="100%">
  <thead>
    <tr bgcolor="#54BEDF">
<th align="center">字节位置</th>
<th align="center">字节数</th>
<th align="center">内容</th>
<th align="center">说明</th>
</tr>
  </thead>
  <tbody>
    <tr bgcolor="#D5EDF3">
<td align="center">0~429</td>
<td align="center">430</td>
<td align="center">数据区</td>
<td>[0xFF][0xFE][行号] + 40 字节数据，<br>每个点位2个字节数据，低位在前、<br>高位在后。</td>
</tr>
    <tr>
<td align="center">430~431</td>
<td align="center">2</td>
<td align="center">16-bit 字节累加和校验</td>
<td>对前 430 字节逐字节相加取低16位。</td>
</tr>
  </tbody>
</table>

<p align="center">表4-2 数据结构列表</p>

<p align="center">05</p>

---

<!-- PDF page 08 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

## 5. 产品使用步骤

本产品具体使用步骤如下；  
硬件连接：将传感器通过FPC连接到采集模块，采集模块与CH340或者CP2102模块连接，插入PC机USB接口完成硬件连接：

<p align="center">
  <img src="images/figures/hardware-connection.png" alt="连接实物图" width="740">
</p>

<p align="center">图5-1 连接实物图</p>

此为传感器使用的正方向：

<p align="center">
  <img src="images/figures/sensor-orientation.png" alt="正方向使用图" width="510">
</p>

<p align="center">图5-2 正方向使用图</p>

<p align="center">06</p>

---

<!-- PDF page 09 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

## 6. 软件连接

与上位机通讯：硬件连接完成后，首先确认PC端有没有安装CH340或者CP2102驱动，否则无法识别设备，可通过设备管理器详细查看端口号：

<p align="center">
  <img src="images/figures/device-manager.png" alt="设备管理器中的串口" width="500">
</p>

打开配套文件包里的此文件夹：

<p align="left">
  <img src="images/figures/release-folder.png" alt="release-uifix 文件夹" width="170">
</p>

<p align="left">
  <img src="images/figures/application-folder.png" alt="win-unpacked 文件夹" width="170">
</p>

打开应用程序：

<p align="center">
  <img src="images/figures/application-executable.png" alt="Gripsense 200 Visualizer.exe 应用程序" width="720">
</p>

<p align="center">07</p>

---

<!-- PDF page 10 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

(1) 点击Connect连接：

<p align="center">
  <img src="images/figures/connect-button.png" alt="点击Connect连接" width="500">
</p>

(2) 点击对应的端口：

<p align="center">
  <img src="images/figures/select-port.png" alt="选择对应端口" width="350">
</p>

(3) 即可开始使用，如下：：

<p align="center">
  <img src="images/figures/connected-view.png" alt="连接成功后的界面" width="640">
</p>

<p align="center">08</p>

---

<!-- PDF page 11 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

## 7. 上位机使用说明

(1)视图切换；  
点击Visualizer切换至热力图视角。  
点击Raw Data切换至原始数据视角。

<p align="center">
  <img src="images/figures/view-switch.png" alt="Visualizer与Raw Data视图切换" width="660">
</p>

(2)热力图设置；  
通过滑动调节热力图的颜色区间范围，例如调小后，数值在低值时也能显示红色。  
左边的按钮可以调整热力图方格大小，关闭可以调大方格；中间的按钮可以关闭显示中心点的轨迹；右边的按钮可以关闭坐标系。

<p align="center">
  <img src="images/figures/heatmap-controls.png" alt="热力图颜色区间与显示按钮" width="690">
</p>

<p align="center">09</p>

---

<!-- PDF page 12 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

(3)右上侧功能区说明；

<p align="center">
  <img src="images/figures/cop-coordinates.png" alt="COP中心点坐标" width="560">
</p>

中心点坐标

<p align="center">
  <img src="images/figures/contact-features.png" alt="右上侧功能区" width="430">
</p>

(4)数据保存功能；

数据保存在如下两种文件：  
CSV：记录矩阵逐点压力值，例如 Row、Col、Pressure。  
JSON：记录时间戳、量程参数、总力、COP、Blob 数量、校准状态等元信息。

- 开始保存使用过程中的数据。

<p align="center">
  <img src="images/figures/start-recording.png" alt="开始保存使用过程中的数据" width="710">
</p>

<p align="center">10</p>

---

<!-- PDF page 13 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

- 保存结束，数据导出。

<p align="center">
  <img src="images/figures/export-data.png" alt="保存结束，数据导出" width="710">
</p>

## 8、重要注意事项

1.请平整安装传感器，勿过度弯折传感器的感应点区域，否则容易导致测试数据不准确，严重的话会损害传感器。  
2.传感器是敏感器件，勿使用尖锐和针刺的物体接触传感器。  
3.请勿在规定的电气参数外使用本产品。  
4.请勿在未断电的情况下进行产品接线操作。  
5.请严格按照本手册进行接线处理。

## 9、常见问题

**1.为什么将设备连接电脑后，找不到对应串口？**

(1)本产品配套使用的是CH340或CP2102转换模块，请先安装CH340或者CP2102驱动程序才能完成连接，驱动程序在产品配套的文件包里。  
(2)可能接触不良，可以尝试重新进行硬件连接或重启电脑。

**2.设备连接电脑后，可以找到对应的串口号，但是与上位机或者串口调试助手连接时没反应？**

(1)请先检查串口配置参数是否一一匹配正确。

<p align="center">11</p>

---

<!-- PDF page 14 -->

<p>
  <img src="images/figures/header-logo.png" alt="LEGACT 力感科技" width="180" align="middle">
  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <a href="https://www.film-sensor.com">www.film-sensor.com</a>
</p>

(2)可检查转接模块与采集模块之间的连线是否松动，或者是否接反，其中正确的接法是CH340的TX连接采集模块的RXD，CH340的RX连接采集模块的TXD，5V接5V，GND接GND。  
(3)检查整套模组的供电电压是否为5V。

**3.串口调试助手接收到的数据是一堆乱码？**

请选择十六进制显示。

**4.设备连接电脑，并正确连接上了串口调试助手或者上位机，但是无论怎么按压传感器，接收的数据都没有变化？**

检查传感器是否接反，本产品中与传感器相接的FPC使用的是下接翻盖型，请保证传感器裸露引脚向下接入FPC，并检查是否接入太浅或接歪。

## 10、更多帮助

1\. 本公司官网：[www.film-sensor.com](https://www.film-sensor.com)

<p align="center">
  <img src="images/figures/website-qr.png" alt="官网二维码" width="150">
  &emsp;&emsp;
  <img src="images/figures/wechat-qr.png" alt="公众号二维码" width="150">
</p>
<p align="center">(官网)&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;(公众号)</p>

2\. 邮箱：elianexiong@film-sensor.com  
3.公司地址：广东省深圳市宝安区西乡街道劳动社区万庭大厦3号楼1302

**注明:**  
以上信息被认为是正确的，是为专业的、有能力来正确评估和使用这些数据的终端用户而准备的。深圳市力感科技有限公司不保证这些数据的精确性，对在使用过程中发生的损坏不承担责任。

<p align="center">12</p>
