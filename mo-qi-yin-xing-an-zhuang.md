# 墨奇音形安装

先安装rime中州韵输入法引擎，官网：[https://rime.im/download/](https://rime.im/download/)

然后下载墨奇音形配置包[https://github.com/gaboolic/rime-shuangpin-fuzhuma](https://github.com/gaboolic/rime-shuangpin-fuzhuma)，复制到rime配置文件夹即可。

网络不好的同学：加群696353204下载

#### 如何安装&配置文件路径

* windows：%APPDATA%\Rime
* mac
  * [鼠须管](https://github.com/rime/squirrel)路径为\~/Library/Rime
  * [fcitx5-mac版](https://github.com/fcitx-contrib/fcitx5-macos)路径为\~/.local/share/fcitx5/rime
* linux
  * [fcitx5-rime](https://github.com/fcitx/fcitx5-rime)路径为\~/.local/share/fcitx5/rime
  * fcitx5 flatpak版的路径\~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime
  * [ibus-rime](https://github.com/rime/ibus-rime)路径为\~/.config/ibus/rime
* android
  * [fcitx5-安卓版](https://github.com/fcitx5-android/fcitx5-android)路径为 /Android/data/org.fcitx.fcitx5.android/files/data/rime
  * [同文](https://github.com/osfans/trime)路径为 /rime
* ios [仓输入法](https://github.com/imfuxiao/Hamster) 目前已内置，也可以通过【输入方案设置 - 右上角加号 - 方案下载 - 覆盖并部署】来更新墨奇音形。

如果会使用git基本操作，可以直接用git管理配置，首次：例如mac可以打开\~/Library文件夹，然后`git clone --depth 1 https://github.com/gaboolic/rime-shuangpin-fuzhuma Rime` 后面在Rime文件夹执行`git pull`即可

现在也支持[东风破](https://github.com/rime/plum)，选择配方（recipes/\*.recipe.yaml）来进行安装或更新：

* ℞ 安装或更新全部文件 执行`bash rime-install gaboolic/rime-shuangpin-fuzhuma:recipes/full`
* ℞ 安装或更新所有的词库文件 执行`bash rime-install gaboolic/rime-shuangpin-fuzhuma:recipes/all_dicts`
