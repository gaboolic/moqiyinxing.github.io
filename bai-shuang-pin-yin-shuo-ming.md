# 白霜拼音说明

[白霜拼音](https://github.com/gaboolic/rime-frost)：蒹葭苍苍，白露为霜。白霜拼音使用使用745396750字的高质量语料，进行分词，重新统计字频、词频，归一化，打造纯净、词频准确、智能的词库。白霜词库是目前rime方案下最好的开源词库，立志于打造不输于商业输入法的输入体验。

#### 使用方法

使用方法基本同雾凇拼音，微调了一些触发指令，加入了lua辅助码的支持。辅助码是可选项，按下\`开启，不影响正常打字。

默认方案是全拼，可以切换输入方案，也支持自然码双拼、小鹤双拼、微软双拼、搜狗双拼等双拼方案。

* 符号 /fh 更多符号详见`https://github.com/gaboolic/rime-frost/blob/master/symbols_v.yaml`
* 带调韵母 /a /e /u 等
* 日期与时间 rq sj xq dt ts
* 开启辅助码 \` [墨奇辅助码拆分说明](https://moqiyinxing.chunqiujinjing.com/index/mo-qi-yin-xing-shuo-ming/fu-zhu-ma-shuo-ming/mo-qi-ma-chai-fen-shuo-ming)
* 部件拆字反查 uU
* unicode字符 U
* 数字金额大写 R
* 农历 N
* 计算器 V

#### 如何安装&配置文件路径

**手动下载安装**

下载本仓库的压缩包 Code - Download ZIP（或者下载[releases](https://github.com/gaboolic/rime-frost/releases)最新的 source-code.zip），解压到如下路径即可

* Windows:&#x20;
  * 小狼毫：`%APPDATA%\Roming\Rime` （可以在右下角小狼毫输入法右键打开菜单选用户文件夹）复制完之后，去输入法设定里选择白霜拼音，然后重新部署
  * 安装[墨奇输入法](https://github.com/gaboolic/moqi-im-windows)的自带方案。Rime配置文件夹在：`%APPDATA%\Roming\Moqi\Rime` （可以在右下角输入法右键打开菜单选用户文件夹）
* Mac
  * [鼠须管](https://github.com/rime/squirrel)路径为 `~/Library/Rime`
  * [fcitx5-Mac 版](https://github.com/fcitx-contrib/fcitx5-macos)路径为 `~/.local/share/fcitx5/rime`
* Linux
  * [fcitx5-rime](https://github.com/fcitx/fcitx5-rime)路径为 `~/.local/share/fcitx5/rime`
  * fcitx5 flatpak 版的路径 `~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime`
  * [ibus-rime](https://github.com/rime/ibus-rime)路径为 `~/.config/ibus/rime`
* Android
  * [fcitx5-安卓版](https://github.com/fcitx5-android/fcitx5-android)路径为 `/Android/data/org.fcitx.fcitx5.android/files/data/rime`
  * [同文](https://github.com/osfans/trime)路径为 `/rime`
  * [雨燕](https://github.com/gurecn/YuyanIme) 已内置白霜词库词频，直接安装使用即可
* iOS [仓输入法](https://github.com/imfuxiao/Hamster) 目前已内置，也可以通过【输入方案设置 - 右上角加号 - 方案下载 - 覆盖并部署】来更新白霜拼音。

**通过 Git 安装**

**首次安装：**

根据用户使用的系统、安装的软件不同，先cd到对应的配置文件的父级目录(例如Windows为`%APPDATA%`、mac鼠须管为`~/Library/`)，然后执行以下命令：

`git clone --depth 1 https://github.com/gaboolic/rime-frost Rime`

**后续更新：**

在 Rime 文件夹执行 `git pull` 即可。

* Mac: `cd ~/Library/Rime && git pull`
* Windows: `cd "$env:APPDATA\Rime" && git pull`
* 其他系统以此类推

**通过 东风破 安装**

选择配方（others/recipes/\*.recipe.yaml）来进行安装或更新：

* ℞ 安装或更新全部文件 执行bash rime-install gaboolic/rime-frost:others/recipes/full

####

#### 无智能模型时的输入效果

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/gegegojx.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/gegegojx.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/mggjdgg.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/mggjdgg.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/ddmdd.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/ddmdd.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/tushuguancangshu.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/tushuguancangshu.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/znjldkd.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/znjldkd.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/kudsvqw.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/kudsvqw.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/cqlbtdmdfu.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/cqlbtdmdfu.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/djbwv.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/djbwv.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/%E5%88%9A%E4%BA%A4%E7%9A%84%E6%9C%8B%E5%8F%8B.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/%E5%88%9A%E4%BA%A4%E7%9A%84%E6%9C%8B%E5%8F%8B.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/%E5%88%9A%E4%BA%A4%E7%9A%84%E5%A5%BD%E6%9C%8B%E5%8F%8B.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/%E5%88%9A%E4%BA%A4%E7%9A%84%E5%A5%BD%E6%9C%8B%E5%8F%8B.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/%E5%88%9A%E4%BA%A4%E7%9A%84%E5%A5%BD%E6%9C%8B%E5%8F%8B2.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/%E5%88%9A%E4%BA%A4%E7%9A%84%E5%A5%BD%E6%9C%8B%E5%8F%8B2.png)

[![alt text](https://github.com/gaboolic/rime-frost/raw/master/others/img/%E8%A1%8D%E5%B0%84.png)](https://github.com/gaboolic/rime-frost/blob/master/others/img/%E8%A1%8D%E5%B0%84.png)

####

#### 鸣谢

雾凇词库 [https://github.com/iDvel/rime-ice](https://github.com/iDvel/rime-ice) 白霜词库的初始词库、绝大部分配置来自雾凇词库

结巴中文分词 [https://github.com/fxsjy/jieba](https://github.com/fxsjy/jieba)

汉字转拼音(pypinyin) [https://github.com/mozillazg/python-pinyin](https://github.com/mozillazg/python-pinyin)

MNBVC 超大规模中文语料集 [https://github.com/esbatmop/MNBVC](https://github.com/esbatmop/MNBVC) 目前已有 33TB 数据量

kenlm [https://github.com/kpu/kenlm](https://github.com/kpu/kenlm) 官网[https://kheafield.com/code/kenlm/](https://kheafield.com/code/kenlm/)

kenlm 教程、python 调用 [https://github.com/mattzheng/py-kenlm-model](https://github.com/mattzheng/py-kenlm-model)

吉祥物(于2024-10-12捡来)：

[![](https://github.com/gaboolic/rime-frost/raw/master/others/img/white-cat.jpg)](https://github.com/gaboolic/rime-frost/blob/master/others/img/white-cat.jpg)

#### 友情链接



使用白霜词库的方案

墨奇音形 [https://github.com/gaboolic/rime-shuangpin-fuzhuma](https://github.com/gaboolic/rime-shuangpin-fuzhuma)

墨奇五笔整句 [https://github.com/gaboolic/rime-wubi-sentence](https://github.com/gaboolic/rime-wubi-sentence)

薄荷拼音 [https://github.com/Mintimate/oh-my-rime](https://github.com/Mintimate/oh-my-rime)

雨燕输入法 [https://github.com/gurecn/YuyanIme](https://github.com/gurecn/YuyanIme) 一个开箱即用的安卓输入法 内置白霜词库
