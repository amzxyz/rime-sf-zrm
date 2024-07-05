#### 一个基于rime自然码双拼的纯净方案，支持辅助码、中英混输、拆字、计算器、农历、金额大写等 
辅助码是周先生最早提出的，它可以在输入一个确定得拼音后面继续输入一个偏旁得读音，使得这个字出现在靠前甚至第一位，这种方式易于理解，无须记忆字根，字符之类得内容，一切基于拼音得基础上。从实现方式上可以在输入一个符号來切分主要音节和辅助音节例如：

![截图_选择区域_20240704121653.png](https://storage.deepin.org/thread/202407041144502563_截图_选择区域_20240704121653.png)

**功能1**  如果想要 镇 字显示在前面  那么在本方案下提供两种方式，第一种就是辅助码声母，vf继续输入j 也就是金字旁得声母即可出现结果，如果还是出现不了你要的结果，可以输入偏旁外主体字的声母来继续缩小范围。

![截图_选择区域_20240704121809.png](https://storage.deepin.org/thread/202407041147131421_截图_选择区域_20240704121809.png)

**功能2**  第二种方式是通过反查字库来定位，只是通过不同的方案实现，在输入主要拼音后，通过符号\`  来引导进入反查状态，

引导后继续输入jn金 则包含金的字就会被选出来；

![截图_选择区域_20240704121635.png](https://storage.deepin.org/thread/202407041149125588_截图_选择区域_20240704121635.png)

引导后继续输入mu木则带木的字就会被选出来

![截图_选择区域_20240704121611.png](https://storage.deepin.org/thread/202407041149524870_截图_选择区域_20240704121611.png)

前面两种方案是我从何雾凇和自然码辅码融合而来，其实基于雾凇我们还有一种输入方式可选：

**功能3**  通过 拼音状态下uU字母来引导拆字模式 举例 震  假设你不认识，你可以通过雨和辰 来合并输入

![截图_选择区域_20240704150839.png](https://storage.deepin.org/thread/202407041150405343_截图_选择区域_20240704150839.png)

拼音状态输入后，继续输入u会消失如下图，输入 yu if 即雨 辰，结果出现了我们要的震字，且给出了辅助码 y 和  i  注意这不是 意 不要忘记我们用的是双拼，y是雨的声母y，i是辰的声母ch

![截图_选择区域_20240704150917.png](https://storage.deepin.org/thread/202407041151271858_截图_选择区域_20240704150917.png)

**功能4**

- **日期时间：**
  输入：```date        time   week    datetime                   timestamp```
  得到：``` 2024-07-04  19:37  星期四  2024-07-04T19:38:47+08:00  1720093174```
- **农历：** lunar
- **Unicode：** 大写 U 开头，如 U62fc 得到「拼」。
- **数字、金额大写：** 大写 R 开头，如 R1234 得到「一千二百三十四、壹仟贰佰叁拾肆元整」。
- **农历指定日期：** 大写 N 开头，如 N20240210 得到「二〇二四年正月初一」。
- **/模式：** 通过输入 /sx 快捷输入关于“数学”的特殊符号，具体能输入什么可以打开 symbols\_v.yaml学习。
- **计算器：** 通过输入大写V引导继续输入如：V3+5  候选框就会有8和3+5=8，基础功能 `+ - * / % ^` 还支持 `sin(x) cos(x)` 等众多运算方式 [点击全面学习](https://github.com/gaboolic/rime-shuangpin-fuzhuma/blob/main/md/calc.md)
