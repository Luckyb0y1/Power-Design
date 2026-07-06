# DC/DC电源转换的学习笔记

## 1.基础拓扑电路

### （1）Buck（降压）电路

<p align="center">
  <img src="./img/image.png?v=1" alt="Buck电路原理图-1">
</p>

电感：使电流无法突变的特性，使电流逐渐上升,同时因为电感无电阻，所以不会产生能量的多余损耗。
二极管：利用二极管的的反相稳压特性，使输出电压稳定在理想范围。
MOS管：反复开关，降低电源多余的热量输出。

<p align="center">
  <img src="./img/image-1.png?v=1" alt="输出电流图">
</p>

图中表明反复开关后的电流并不稳定，所以需要添加一个滤波电容。

<p align="center">
   <img src="./img/image-2.png?v=1" alt="Buck电路原理图-2">
</p>

### （2）Boost（升压）电路

[//]: # (<img src="" alt="">)

<p align="center">
   <img src="./img/image-3.png?v=1" alt="Boost（升压）电路-1">
</p>

按下开关，电流缓慢上升到需要的范围，然后松开开关，输出理想的电压值。
反复按下开关，实现稳定的电压输出。

<p align="center">
   <img src="./img/image-4.png?v=1" alt="Boost（升压）电路-2">
</p>

利用电容的电压不会突变效应，是电压稳定在理想范围，二极管防止电容释放的电流流向电源。

<p align="center">
   <img src="./img/image-5.png?v=1" alt="电压变化图">
</p>

最后将开关换成适应高频率的MOS管实现占空比的调节。

### （3）Buck——Boost（升降压）电路

<p align="center">
   <img src="./img/image-6.png?v=1" alt="电压变化图">
</p>

MOS管导通时电感上的电流增大，二极管阻挡电流流通，电容维持输出电压。
MOS管断开时电感上的电流给电容充电，同时流过电阻是输出理想范围的电压，二极管导通形成回路。

### （4）MOS管工作原理

<p align="center">
   <img src="./img/image-7.png?v=1" alt="MOS管原理图-1">
</p>

<p align="center">
   <img src="./img/image-8.png?v=1" alt="MOS管原理图-2">
</p>

控制栅极（g）的导通来控制电流的输出

### （5）反激电路

<p align="center">
   <img src="./img/image-9.png?v=1" alt="反激电路">
</p>

整流滤波后，mos管导通，输出无电流，电感储能；mos管断开后，输出电流，电感释放能量。线圈绕线方向相反。

### （6）正激电路

<p align="center">
   <img src="./img/image-10.png?v=1" alt="正激电路">
</p>

线圈绕线方向相同，mos管导通时，N1，N2同名端为正，D1截止，D2导通，D3截止。
mos管短路时，N1，N2同名端为负，D1、D3导通，D2截止，防止磁通炸管，维持输出稳定。
