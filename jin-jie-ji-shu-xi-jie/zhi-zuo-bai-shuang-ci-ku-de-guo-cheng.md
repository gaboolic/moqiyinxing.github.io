# 制作白霜词库的过程

作者最初使用的是雾凇拼音里的词库，用了一段时间发现有一些问题，例如字频过高，废词、黄词有点多，输入“衍射与折射”，“打几把游戏”，“喝一杯蜜雪”等词句时不符合预期，上屏很尴尬的结果。于是重新制作。

第一步是在雾凇词库的基础上，所有字的字频/100，手工去掉诸如“的吧”、“的了”这种不是词的词。手动大量修改了字频 词频。第一步是做了减法。

第二步，使用修改后的词库，生成结巴分词使用的自定义分词词库的格式，脚本见[https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/generate\_custom\_fenci\_dict.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/generate\_custom\_fenci\_dict.py)

第三步，下载mnbvc的语料库，清洗数据，产生txt格式的纯净文字，脚本见[https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/get\_dict.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/get\_dict.py)

第四步，把第三步得到的txt文件，每个都去调用结巴分词，并统计词频，脚本见[https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/yuliao\_fenci.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/yuliao\_fenci.py)

第五步，合并多个txt文件的词频，脚本见[https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/merge\_fenci\_freq\_result.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/merge\_fenci\_freq\_result.py)

第六步，修改白霜词库的词频为上面分词词频合并的结果，脚本见[https://github.com/gaboolic/rime-frost/blob/master/others/program/reduce\_freq\_base\_to\_zhifreq.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/reduce\_freq\_base\_to\_zhifreq.py)

第七步，重新生成结巴分词自定义词库，测试新词频效果，脚本见[https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/fenci\_test.py](https://github.com/gaboolic/rime-frost/blob/master/others/program/mnbvc/fenci\_test.py)

第八步，手工打字，评估新词频效果。手工剔除一些影响分词效果的长词，例如“时间和”，“鱼的”等等词。

以上1-8步重复多次执行，自我迭代，效果会越来越好。

第九步，添加细胞词库，也用到了一些去重、注音的脚本，都在[https://github.com/gaboolic/rime-frost/blob/master/others/program](https://github.com/gaboolic/rime-frost/blob/master/others/program)。
