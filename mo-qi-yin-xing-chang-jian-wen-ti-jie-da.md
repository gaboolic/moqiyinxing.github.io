# 墨奇音形常见问题解答

[https://github.com/gaboolic/rime-shuangpin-fuzhuma/blob/main/md/FAQ.md](https://github.com/gaboolic/rime-shuangpin-fuzhuma/blob/main/md/FAQ.md)

1 为什么不能记住我打的词？

默认关了用户词库（为了固定词频），如有需要，修改你使用的方案.schema.yaml `enable_user_dict: true`开启 默认固定词频，编辑cn\_dicts\_common/user.dict.yaml来添加自定义的词；推荐在用户词库关闭的情况下使用ac引导造词，这样自造词是在系统词库后面，不会影响系统词的字频和词序。



2 如何不显示形码的辅助码？

修改你使用的方案.schema.yaml中spelling\_hints字段，改为0可以关闭

```
translator:
  dictionary: flypy_flypy.extended
  enable_completion: false
  # 默认为不超过 2 个字的候选项显示输入码；将 2 改为 0 可关闭编码提示，
  # 改为 1 则是只显示单字的输入码，依此类推。
  spelling_hints: 2
```



3 模糊音\
这个功能类似飞键。

以不分平翘舌音为例：\
在你使用的方案.schema.yaml中，修改以下部分

```
speller:
  algebra:
    ## 模糊音 可选择性开启
    - derive/^z([a-z])/v$1/
    - derive/^c([a-z])/i$1/
    - derive/^s([a-z])/u$1/
    - derive/^v([a-z])/z$1/
    - derive/^i([a-z])/c$1/
    - derive/^u([a-z])/s$1/
```

添加韵母的话，和上面类似

比如添加in和ing的模糊音，如果in是b，ing是k的话，可以这样：

```
- derive/^([a-z])b/$1k/    
- derive/^([a-z])k/$1b/
```
