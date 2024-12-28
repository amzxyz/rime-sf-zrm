 
### 自然万象_随意码
### 自然码双拼结合4万字的辅助码的方案
说明：由于除了几个基础aeho与汉心设定相同，基本遵守收尾取字根，但遇到字型规整的字又会简单的取一下收尾很容易认识的字的读音，这又与自然码逻辑相同，视情况而定，不会完全追求递归到底，因此取码规则比较写意，权看个人认知，故而称之为……随意码！


辅助码它可以在输入一个确定得拼音后面继续输入一个字根的读音，使得这个字出现在靠前甚至第一位。这种方式易于理解，无须记忆字根，一切基于拼音得基础上。例如：

![截图_选择区域_20240704121653.png](https://storage.deepin.org/thread/202407041144502563_截图_选择区域_20240704121653.png)

**功能1**  直接辅助码：如果想要 ```镇``` 字显示在前面  那么在本方案下提供两种方式，第一种就是辅助码声母，```vf```继续输入```j``` 也就是金字旁得声母即可出现结果，如果还是出现不了你要的结果，可以输入另外主体字的声母来继续缩小范围。

![截图_选择区域_20240704121809.png](https://storage.deepin.org/thread/202407041147131421_截图_选择区域_20240704121809.png)

**功能2**  间接辅助码：这种方式是通过反查字库来定位，也叫辅助筛选，在输入主要拼音后，通过符号``` ` ```  来引导进入反查状态，引导后继续输入```j或者jn```金 则包含金的字就会被选出来；

![截图_选择区域_20240704121635.png](https://storage.deepin.org/thread/202407041149125588_截图_选择区域_20240704121635.png)

引导后继续输入```mu 木```则带```木```的字就会被选出来

![截图_选择区域_20240704121611.png](https://storage.deepin.org/thread/202407041149524870_截图_选择区域_20240704121611.png)

前面两种方案是雾凇和自然码辅码融合而来，其实雾凇我们还有一种输入方式可选：

**功能3**  通过 拼音状态下```az```字母来引导拆字模式 举例 ```震```  假设你不认识，你可以通过```雨和辰``` 来合并输入，拼音状态输入后，继续输入其它字符字母az会消失如下图，输入 ```yu if``` 即雨 辰，结果出现了我们要的震字，且给出了辅助码 ```y``` 和  ```i```  ，```y```是雨的声母```y```，```i```是辰的声母```ch```

![截图_选择区域_20240704150917.png](https://storage.deepin.org/thread/202409280324599355_%E6%88%AA%E5%9B%BE_%E9%80%89%E6%8B%A9%E5%8C%BA%E5%9F%9F_20240928112256.png)

**功能4**  句子中间或者单字输入时需要输入全位辅助码时由于与双拼词语重码，我们此时可以通过追加/的方式使其聚拢，这种方式是由于我们是直接辅助码导致的，如果我们通过一个符号引导辅助码，那么在输入时要每一个都用到符号，而采用这种方式我们只需要在必要的时候使用/节省了输入的按键开支，下面由两个图片说明问题：

![截图_选择区域_20240821093644.png](https://storage.deepin.org/thread/202408210142513354_截图_选择区域_20240821093644.png)

![截图_选择区域_20240821093701.png](https://storage.deepin.org/thread/202408210143144721_截图_选择区域_20240821093701.png)

**其它亮点功能**

- **日期时间：**
  输入：```date        time   week    datetime                   timestamp```
  
  得到：``` 2024-07-04  19:37  星期四  2024-07-04T19:38:47+08:00  1720093174```
- **农历：** lunar 获得当前日期的农历值
- **Unicode：** 大写 U 开头，如 U62fc 得到「拼」。
- **数字、金额大写：** 大写 R 开头，如 R1234 得到「一千二百三十四、壹仟贰佰叁拾肆元整」。
- **农历指定日期：** 大写 N 开头，如 N20240210 得到「二〇二四年正月初一」。
- **/模式：** 通过输入 /sx 快捷输入关于“数学”的特殊符号，具体能输入什么可以打开 symbols.yaml学习。
- **计算器：** 通过输入大写V引导继续输入如：V3+5  候选框就会有8和3+5=8，基础功能 `+ - * / % ^` 还支持 `sin(x) cos(x)` 等众多运算方式 [点击全面学习](https://github.com/gaboolic/rime-shuangpin-fuzhuma/blob/main/md/calc.md)
- **自动上屏：** 例如：三位、四位简码唯一时，自动上屏如```jjkw岌岌可危``` ```zmhu怎么回事``` 。默认未开启，方案文件中```speller:```字段下取消注释这两句开启 ```#  auto_select: true  #  auto_select_pattern: ^[a-z]+/|^[a-df-zA-DF-Z]\w{3}|^e\w{4}```；
- **错音错字提示：** 例如：输入```gz yu给予```，获得```jǐ yǔ```提示；
- **输入码显示声调：** Ctrl+s开启和关闭输入码声调显示；
- **超级注释：** 辅助码注释提示：任意长度候选词的辅助码提示能力，默认开启1个字的辅助码，Ctrl+a开启和关闭辅助码，Ctrl+z自然码拆字辅助，支持部件组字反查读音和辅助码提示，尤其是对生僻字友好
- **用户词删除：** 不管什么删除都不能直接作用于固定词典，使用Ctrl+del是rime系统删除用户词，基于lua的实现：对选中的候选词操作，使用Ctrl+d 删除，Ctrl+x隐藏，Ctrl+j降低词频，删除的词都在lua下文件中记录，你可以清空重新部署恢复，也可以根据列出去清除固定词典的编码，从而持续迭代。
- **Tab循环切换音节：** 当输入多个字词时想要给前面补充辅助码，可以多次按下tab循环切换，这种可能比那些复杂的快捷键好用一些；
- **翻译模式：** 输入状态按下Ctrl+E快捷键进入翻译模式，原理是opencc查表进行中英文互译，能否翻译取决于词表的丰富度；
- 更多功能可以编辑方案文件依据注释说明开启
