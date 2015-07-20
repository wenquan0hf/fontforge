# EM Square  
  
— 也被称作“EM size”或者“UPM”。在一个字体中，每个字符都放置在其空间容器内。在传统的金属字模中，这个容器就是每个字符的实际金属块。每个字符的高度是统一的，这样每个字模可以整齐地放进行和块中（如下）。  
  
![MetalTypeZoomIn.JPG](\images\MetalTypeZoomIn.JPG)  
  
字模的高度被称为“em”，起源于大写的字符“M”的宽度；这个字母的比例被做成了方形（因此有了“EM Square”的称呼）。em size 是根据字模计算出的点值。因此一个 10 磅的字体 em 也是 10 磅（如下）。  
  
![em-metal-type.svg](\images\em-metal-type.svg)   
  
在数字化字体中，em 是空间的数字化定义总量。在 OpenType 字体中，UPM 或 em 大小通常是1000 单位。在 TrueType 字体中，UPM 约定是 2 的幂，通常是 1024 或 2048。  
  
当时用字体来设置样式时，em 将会缩放到需要的点值。这意味着对于 10 磅的字体样式，1000 单位在这个实例中将会缩小到 10 磅。

因此如果你的大写的“H”时 700 单位高，那么它在一个 10 磅的字体中将会被缩放到 7 磅高。  
  
## 在字形窗口中设定

知道了你的字体将会使用 1000，1024 或 2048UPM 后，你需要设定你的字形的绘制，以保证你字体样式的所有面都充分地填入 UPM 空间内。  
  
Em square 的大小设定方法是 Element>Font Info…然后点击 General 选项卡，你将会看到 EM 设置。这个值将会分配到顶高和底深上，分别在基线的上下。  
  
基线：  
  
![baseline.png](\images\baseline.png)  
  
大写高度:  
  
![capheight.png](\images\capheight.png)  
  
x 高度:  
  
![xheight.png](\images\xheight.png)  
  
在你设计字体的后期，你需要设置 Blue 值，这个值为 PostScript 画轮廓而保留，也保留给 FontForge 自动微调–无论你在做哪个轮廓。  
  
你可以在 Element>Font Info…，PS Private 中找到这个设定。FontForge 可以首先根据你的轮廓猜测初始值，但是为了上突/下突，你必须自行修改—这个概念在几章后的创造“o”和“n”中；让我们先上手 FontForge 及其绘制功能。