# 每个人都可以训练自己的语言模型

{% embed url="https://github.com/gaboolic/rime-build-grammar" %}

感谢rime输入法交流群雨辰、魔然作者ksqsf的研究。

把制作语言模型的步骤写下来，做个备忘。

语言模型简介：[https://fancyerii.github.io/dev287x/lm/](https://fancyerii.github.io/dev287x/lm/)

简要步骤：

1 收集语料

2 分词，变成txt格式，词和词之间按空格分开 脚本可以参考[https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/yuliao\_fenci\_to\_txt.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/yuliao\_fenci\_to\_txt.py)

3 生成.arpa文件 可以使用开源库 [https://github.com/kpu/kenlm](https://github.com/kpu/kenlm)

4 把arpa转成librime-octagram的tool用的格式 雨辰提供[https://github.com/gaboolic/rime-build-grammar/blob/main/arpa.py](https://github.com/gaboolic/rime-build-grammar/blob/main/arpa.py)

5 执行librime-octagram的build\_grammar
