# 墨奇输入法说明

墨奇输入法在github上开源：[https://github.com/gaboolic/moqi-im-windows](https://github.com/gaboolic/moqi-im-windows)&#x20;

### 特色功能

* 托盘切换输入法状态
* 主题皮肤修改
* 原生ai功能 编辑C:\Users\用户名\AppData\Roaming\Moqi\Rime\ai\_config.json 可以接入ai大模型以及自定义提示词、快捷键

```
{
  "api": {
    "base_url": "",
    "api_key": "",
    "model": ""
  },
  "actions": [
    {
      "name": "写好评",
      "hotkey": "Ctrl+Shift+G",
      "prompt": "请围绕“{{candidate_1}}”生成最多 3 条适合直接发布的中文好评，每条 20 字左右。"
    },
    {
      "name": "优化整句",
      "hotkey": "Ctrl+Shift+O",
      "prompt": "上一句是：{{previous_commit}}\n原始输入拼音是：{{composition}}\n前三个候选词：\n{{candidates_top3}}\n请严格遵循原始输入拼音来选字，只能在符合这串拼音的候选范围内优化整句，不要凭空改成不匹配拼音的字词。只输出 1 条最通顺、最自然的整句候选，不要解释。"
    },
    {
      "name": "中译英",
      "hotkey": "Ctrl+Shift+E",
      "prompt": "请把当前中文内容翻译成自然、地道的英文。 “{{candidate_1}}” 只输出 1 条英文翻译，不要解释。"
    },
    {
      "name": "问答",
      "hotkey": "Ctrl+Shift+Q",
      "prompt": "用户询问： “{{candidate_1}}” 只输出 1 条答案，不要解释。"
    }
  ]
}
```

### 运行架构



```
┌─────────────────────────────────────────────┐
│           Windows 应用程序                 │
│      (记事本 / Word / 浏览器 / 其他)        │
├─────────────────────────────────────────────┤
│  MoqiTextService.dll                        │
│  - TSF 接口实现                             │
│  - 按键事件/组合串/候选窗处理               │
│  - 通过命名管道连接 Launcher                │
├─────────────────────────────────────────────┤
│  MoqiLauncher.exe                            │
│  - 读取 backends.json                       │
│  - 管理后端进程生命周期                     │
│  - 在命名管道与后端 stdin/stdout 之间转发消息│
├─────────────────────────────────────────────┤
│  moqi-ime\server.exe                        │
│  - Go 后端进程                              │
│  - 加载 input_methods\*\ime.json            │
│  - 返回候选、状态、上屏文本等               │
└─────────────────────────────────────────────┘
```

当前默认部署中，`backends.json` 指向 `moqi-ime\server.exe`；Windows 侧通过本地命名管道连到 `MoqLauncher`，`MoqLauncher` 再把请求按行写入后端的标准输入，并从标准输出读取响应。

### 核心职责



* **TSF 文本服务**：实现 `ITfTextInputProcessor`、`ITfKeyEventSink` 等接口
* **Windows UI**：管理候选窗口、消息窗口、语言栏按钮和 preserved keys
* **协议转换**：把按键与状态序列化为 JSON 请求，并应用后端返回的组合串、候选和提交文本
* **后端接入**：通过 `MoqLauncher` 读取 `backends.json`，按语言配置 GUID 路由到对应后端

### 与 `moqi-ime` 的关系



本仓库不实现拼音解析、候选生成、词库管理等输入法核心逻辑，这些能力由 `moqi-ime` 提供。

Windows 侧的职责主要是：

* 把 TSF 生命周期和按键事件转发给后端
* 根据后端返回结果更新候选窗、组合串和状态
* 从已安装后端目录扫描 `input_methods/*/ime.json`，为语言配置提供元数据与配置入口

因此，`moqi-im-windows` 与 `moqi-ime` 需要配套部署。
