# “珠算”代码大模型Python编程辅助插件
本插件基于开源项目[llm-vscode](https://github.com/huggingface/llm-vscode)开发  
- [“珠算”代码大模型Python编程辅助插件](#珠算代码大模型python编程辅助插件)
  - [1 使用方法](#1-使用方法)
  - [2 自定义配置](#2-自定义配置)
    - [2.1 更改文件过滤器](#21-更改文件过滤器)
    - [2.2 关闭自动生成](#22-关闭自动生成)
    - [2.3 自定义推理参数](#23-自定义推理参数)
    - [2.4 自定义热键](#24-自定义热键)
  - [3 相关链接](#3-相关链接)  
## 1 使用方法
打开任意后缀名为“.py”的文件，将光标置于想要填充代码的位置。有两种方式可以触发生成建议代码：  
①按下`Alt+Shift+L`（Mac系统为`Cmd+Shift+L`）  
②对代码进行任意修改（可以通过配置关闭，[关闭自动生成](#22-关闭自动生成)）  
生成建议代码后，按下`TAB`接受全部，按下`Ctrl+→`可以向右接受一个词。如果生成了多个建议代码，可以按下`Alt+]`切换。  
## 2 自定义配置
### 2.1 更改文件过滤器
按下`Ctrl+,`打开vscode配置页面，搜索Abacus，点击`Abacus: Document Filter`条目下的`Edit in settings.json`  
![document_filter_1.png](https://img.picui.cn/free/2024/11/01/67247023331e7.png)
修改`Abacus.documentFilter`中的pattern列表，默认为"**/*.py"  
![document_filter_2.png](https://img.picui.cn/free/2024/11/01/6724702328442.png)
### 2.2 关闭自动生成
按下`Ctrl+,`打开vscode配置页面，搜索Abacus，取消勾选`Abacus: Enable Auto Suggest`  
![auto_generate.png](https://img.picui.cn/free/2024/11/01/6724702325c80.png)
### 2.3 自定义推理参数
按下`Ctrl+,`打开vscode配置页面，搜索Abacus，点击`Abacus: Request Body`条目下的`Edit in settings.json`  
![parameters_1.png](https://img.picui.cn/free/2024/11/01/67247023331b9.png)
三个可配置参数自上而下依次为token数、温度与采样率  
![parameters_2.png](https://img.picui.cn/free/2024/11/01/6724702517b39.png)

### 2.4 自定义热键
按下`Ctrl+Shift+P`打开命令面板，点击`Preferences: Open Keyboard Shortcuts (JSON)`  
![keybinding_1.png](https://img.picui.cn/free/2024/11/01/67247023347cf.png)  
在打开的文件中添加新的配置项，格式如下
```
    {
        "key": "alt+shift+l",
        "command": "editor.action.inlineSuggest.trigger",
        "when": "editorTextFocus"
    }
```

## 3 相关链接
llm-vscode项目地址：https://github.com/huggingface/llm-vscode  
珠算代码大模型GitHub主页：https://github.com/HIT-SCIR/Abacus  
珠算代码大模型公众号介绍：https://mp.weixin.qq.com/s/T24_U-aR1WuwQh9iDjCWCg