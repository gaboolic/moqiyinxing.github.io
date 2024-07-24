# 每个人都可以训练自己的语言模型

{% embed url="https://github.com/gaboolic/rime-build-grammar" %}

简要步骤：

1 收集语料

2 分词，变成txt格式，词和词之间按空格分开 脚本可以参考[https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/yuliao\_fenci\_to\_txt.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/yuliao\_fenci\_to\_txt.py)

3 生成.arpa文件 可以使用开源库 [https://github.com/kpu/kenlm](https://github.com/kpu/kenlm)

4 把arpa转成librime-octagram的tool用的格式 [https://github.com/gaboolic/rime-build-grammar/blob/main/arpa.py](https://github.com/gaboolic/rime-build-grammar/blob/main/arpa.py)

5 执行librime-octagram的build\_grammar
