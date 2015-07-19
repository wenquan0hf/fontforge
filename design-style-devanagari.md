# 设计天城体样式

*感谢Adam Twardoch、Erin McLaughlin、Neelakash Kshetrimayum、Dan Reynolds、Pooja Saxena、Dr Girish Dalvi为本页贡献了如此多的想法*

设计一个新的原创的`天城体`样式遵循的流程非常类似设计新的原创的拉丁文的流程。从自由字体的*自由*中能够获得的独特的好处是你可以为字体的初创者从没相处的新目的修改并重用它们–例如设计一个天城体并改造一个已有的拉丁字体来解决它。

## 天城体字形

天城体包含这些不同类型的字形：

- 辅音（36）
- 独立的元音（28）
- 元音 maatras
- 字距
- 天城体数字（10）
- 拉丁数字（新的或者或者将已有的调整到与天城文字相适应）
- nukta 组合
- 半形式
- 连接（独特的连字字形）
- 不同长度的“I”元音 maatras
- 天城体标点符号
- 拉丁标点符号（新的或者调整已有的）
- 拉丁字母

咨询（天城体 Unicode 页面）和（微软天城体 OpenType 字体开发页面）来学习更多关于这些字形和印度语形状引擎如何工作的内容。

写书法或者与此接近学习字帖来学习书写字母如何工作是有帮助的，这样你会明白什么字母在结构上应该与什么其他字母相似。这些 Aksharaya 的天城体书法字帖中的2页可以用作笔的角度和字母比例的参考。

## 首先做什么

在设计一个天城体和拉丁字体样式时，以在天城体旁边绘制拉丁文字开始是重要的。最早一步是设计“关键”字形，以此通过基础形状和间距（这在拉丁文中可能是‘adhesion’或者‘videospan’）来建立字体样式的个性。进程早期设计最低和最高的“高度极值”。

你将会需要大量的元音标记来开始质地和缩放的测试。

印度理工大学孟买分校的字体排印教授 Girish Dalvi 博士在他的博士论文中写到，

>通过这一研究的结果我们可以推断出 10 个字母 अ इ ए ख त भ द ध थ ष 可以捕获几乎所有的剩余天城体字母的正式属性。在这些字母中，字母 अ इ ख भ द ध ष 定义了大多数字母的特性，是最具决定性的。因此我们认为通过首先设计这些字母，天城体设计的流程可以为学生和字体设计师简化，剩下的字母可以通过这些衍生出来。

Erin McLaughlin 建议将这些字形作为一个初始连字：**पाव + किमीनुफू + भरसगदह + र्मों ड्डू (height extremes) + यथधआछड … 连续字符集合**并建议关注“Au”元音标记+reph+anusvara 连字！这里的 Ma 是为了后继。

字形的高度极值允许你确定竖直度量值和如何缩放两个书写系统来共同工作。Adobe 发布了非常大的字体家族覆盖各种不同的正字法。它们根据共享的一般比例分成不同的家族；Myriad Pro 包含 Latin,、Greek 和 Cyrillic，而 Hebrew 与 Arabic 设计打包成分来的家族，包含在改进的 Latin 中。

下面是 Myriad Pro Latin 和 Myriad Arabic 并排：

![myriad_pro_vs_arabic.png](\images\myriad_pro_vs_arabic.png)

（认出 Adobe 的整洁的选择：Myriad Arabic 的大写高度是 Myriad Pro Latin 的 x 高度）

需要注意的是在 Lohit 字符集中，最低的字形是形式，意味着靠下的字符将会下沉到比基线低很多的地方：

待办事项：添加 vattu+U，vattu+Uu，U，Uu和 subscript V（用于合词）的图片

（Vattu 是底基线样式的 reph。详情参见`微软术语`页面）

理想地，这些应该堆叠在你最低的竖直堆叠结合以下，就像左边的例子（Lohit 并不完全竖直适应，在右边）

## 间距方法

设计拉丁字体有代表性地涉及了一系列艰巨字符串像这样：

>HHxHOHOxOO  
>nnXnonoXoo

其中 X 代表了你关注间距的字母，概念是看这个字母挨着有点平的字符和圆的字符。

Pa 与 Va 或 Da 是天城体相等的：

>पपXपवपवXवव  
>पपXपदपदXदद

当刚刚开始一个项目的时候，从使用 Pa 完全填充一个页面开始，以此得到笔画粗细、对立面大小和间距的正确平衡。

>पपपपपपपपपपपपपपपपपपपपप 

一旦 Pa 有了正确的“color”，你可以开始添加其他基本常见的字符：

>पपपवपपपपपवपववपपव （）va，随机化的）  
>पपपापपपपापपाप （Aa maatra，岁计划的）  
>पपपदपपपपपदपददपपद （da，随机化的）

然后你可以开始使用上面的间距字符串来添加新的字形：

>पपरपदपदरदद  
>पपकपदपदकदद  
>पपलपदपदलदद  
>पपपीपदपदपीदद  

诸如此类！

你将希望在一个像那样长的列表中看看这些，这样你可以在屏幕或打印介质上向下滚动时一个一个地比较字形。做竖直检查比只是长的一行连续文本更有效。原因是：

当你在竖直列中看间距字符串时，你可以很容易地比较当前字符到上下行之间的间距。按同样的方式，你可以容易地从坏地设置完全调整的文本中识别出“rivers”，如果你比较剩下的间距字符串，那么可以容易地在间距上看到白色间隙或者暗点。

上面的间距字符串允许你比较非常不同的形状，这样间距甚至更加贯穿（而不是所有太松或太紧的圆的字符）。

中间的四个字形 Pa/Da/Pa/Da 允许你将比较字符与两个三字符集合相比较，也就是 Pa/Da/Pa 或者 Da/Pa/Da。

![deva-spacing.png](\images\deva-spacing.png)

在对一些元音和辅音绘制和调整间距后，你将能够只使用这些字母做出数量有限的词并开始用实际文本测试你的设计。

## 作品分解结构

在任何一个字体样式设计项目中，描绘出一个作品分解结构是好主意。

对于一些非常熟悉的人来说，有可能在大约 4-6 个月内设计出天城体样式的初始的细体和粗体。

这里有一个经验丰富的设计者在设计有些简单的“sans”时，制作 9 种不同粗细、直立和倾斜的插值替换的字体家族的时间表：

<table cellspacing="0" cellpadding="0">
    <tr>
        <td>Week</td>
		<td>Goal</td>
		<td>Glyphs</td>
    </tr>
    <tr>
        <td>1</td>
		<td>Establish design in 7-10 key glyphs</td>
		<td>10</td>
    </tr>
    <tr>
        <td>2</td>
		<td>Refine, design tallest glyphs, match heights and weights to Latin in Regular & Bold, test screen rendering with ttfautohint</td>
		<td>20</td>
    </tr>
    <tr>
        <td>3</td>
		<td>Refine proportions with native reader feedback</td>
		<td>40</td>
    </tr>
    <tr>
        <td>4</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>100</td>
    </tr>
    <tr>
        <td>5</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>200</td>
    </tr>
    <tr>
        <td>6</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>300</td>
    </tr>
    <tr>
        <td>7</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>400</td>
    </tr>
    <tr>
        <td>8</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>500</td>
    </tr>
    <tr>
        <td>9</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>600</td>
    </tr>
    <tr>
        <td>10</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>700</td>
    </tr>
    <tr>
        <td>11</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>800</td>
    </tr>
    <tr>
        <td>12</td>
		<td>Get native reader feedback, refine and add more conjuncts 	</td>
		<td>900</td>
    </tr>
    <tr>
        <td>13</td>
		<td>Derive Bold</td>
		<td>1,800</td>
    </tr>
    <tr>
        <td>14</td>
		<td> 	Refinements, Kerning, testing with native reader feedback</td>
		<td>1,800</td>
    </tr>
    <tr>
        <td>15</td>
		<td>Extrapolation and clean-up of Thin and Black weights, generation and clean-up of slanted styles</td>
		<td>3,600</td>
    </tr>
    <tr>
        <td>16</td>
		<td>Interpolated styles refinement</td>
		<td>3,600</td>
    </tr>
    <tr>
        <td>17</td>
		<td>General refinement of spacing, kerning & testing in all styles</td>
		<td>3,600</td>
    </tr>
    <tr>
        <td>18</td>
		<td>Finalisation</td>
		<td>3,600</td>
    </tr>
</table>

## 有用的资源

## 简介

- http://www.linotype.com/6896/devanagari.html

## 从哪里寻找灵感和创意

在 `http://indiantypefoundry.com` Google Fonts 发布的网站查看天城体，来找到字体形状变化的灵感。

另一个好的地方是搜索印地语“e-paper”电子报网站来看实际使用字体的广告通常有更多的字体多样性。`http://epaper.jagran.com` 是一个流通非常广泛的印度电子报纸。

Flickr也是一个形象化创意的好的来源：

- `https://www.flickr.com/groups/devanagari-script/`
- `https://www.flickr.com/groups/37703106@N00/`
- `https://www.flickr.com/groups/indicscripts/`
- `https://www.flickr.com/photos/pauldhunt/sets/72157603715699186`

#### 历史资源

得到 H. M. Lambert 编写的由牛津大学出版社于 1953 年出版的 Introduction to the Devanagari Script 和 B. S. Naik 编写的孟买语言理事会 1971 年出版的 Typography of Devanagari（3 卷）的副本。

除了那些，还有至少两种欧洲 19 世纪字体的一般来源值得一看：英国和德国（主要是莱比锡）的字体样式。这些字体更多地用来设置梵文字文本而非印度文本。

同时也尝试从印度字体铸造中找到 19 世纪和 20 世纪的文本字体样式的例子。像你期望的那样，它们明显很少欧化。从 19 世纪起在欧洲学院 梵文字体中有一些靠不住的东西，它们看起来根本不存在于 20 世纪的印度的排印中。这些印度来源可能更难从西方图书馆中找到，但是可能 Erin McLaughlin 更加领先。例如 Matthew Carter 的 19 世纪 70 年代的天城体 Linotype 排字机是基于 Nirnaya Sagar 公司的字体样式。它们的字体和孟买字体公司的字体应该可以在一些西方大学或者国家图书馆中找到。我也推荐查找 Monotype 的天城体和 LinoType 天城体（1970 年代版和 1980/90 年代版，而非指示同名的原始的 1935 版）。

在荷兰的 Typefounders 并没有天城体（Charles Enschede, Harry Carter 1978）。无论你做什么，不要看 Bodoni 在 1818 年手工制作的字体。

一些来自 H. Berthold AG 的德国制造的天城体可能在 Reichsdruckerei 于 1924 年在柏林出版的 Alphabete und Schriftzeichen des Morgen- und des Abendlandes 的45-47 页看到。

### 文章

Sarang Kulkarni 写了`"Issues with Devanagari Display Type (PDF)"`

Yashodeep Gholap 写了 `Designing a Devanāgarī text font for newspaper use (PDF)`

Vaibhav Singh 的 MATD 论文 `Devanagari in multi-script typography`

### Lohit2 天城体

Lohit2 天城体可以通过使用其字形列表和 OpenType 布局码来作为新 OFL 字体的基础。想要使用可以通过原始 FontForge 来源 or as a UFO zip 下载

### OpenType 布局

微软天城体 OpenType 字体开发页面

### 天城体刨析

`Aksharaya 的天城体书法指南的 2 页`，可以用来作为笔锋角度和字母比例的参考。

印度理工学院孟买分校（比得上美国的麻省理工学院媒体实验室）的 Girish Davli 教授发表了这个`天城体刨析文章（PDF）`

如果你对天城体书写字母的不熟悉，那么知道传统书法笔锋力道是重要的，这与拉丁不同。这里有一个笔画角度和曲线如何传统地赋予粗细的快速文档。如果你遵循这些粗细原则来绘制你的曲线，而不是剪切粘贴拉丁字母的一部分，那么你的设计将会更加成功，并且看起来更少“拉丁化”。


`天城体 Unicode 页面`展示了基本字母，但没有连字。

### 测试工具

Adobe InDesign 对非欧洲书写字母的 OpenType 字体的支持只有在 Creative Cloud 中才可靠，甚至最新版本也没有改善。自由 Harfbuzz 与微软 OpenTyp e的实现是完成度最高的，因此你应该在 Windows 和 Mac OS X 下使用最新版本的 Chrome、Firefox 和微软 Word 来测试你的字体，以保证形状上的错误来自于字体而非底层引擎。

`Pablo Impallari 的天城体测试页面` （以及 `Github 上的源码`）提供了一些已经制作好的测试布局，你可以拖动你的 OTF 或者 TTF 字体到页面上来加载它。

`Pooja Saxena 的字体工具`（以及 `Github 上的源码`）来生成字母连接的测试文本。

`Adhesion 天城体文本`是 Miguel Sousa 构建的用来制造只包含可能使用你已经绘制的字形来书写的单词的假文本 的工具的一个特殊版本。插入你已经绘制的字形（अआईईउऊ 等），将会诞生一些你用于证明的示例单词。

Huerta Tipografica 的 `Devanaguide` 是一个开源工具，用来看和比较不同的天城体。它也允许你打字并同时在所有字体上预览。Devanaguide 也包含了一个`天城体词表`，对测试文本设计有帮助。

### 论坛讨论

Typophile

- `Adobe天城体`

Google字体目录讨论

- `关于相比于拉丁，放置肩线、顶部、底部等等的约定？`
- `从Lohit2开始与pdf`
- `Adobe字形列表`
- `rVocalic与rrVocalic`
- `天城体字符优先顺序`



