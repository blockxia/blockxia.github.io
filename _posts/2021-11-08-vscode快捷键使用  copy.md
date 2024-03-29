---
layout: post
title:  "vscode开发快捷键使用"
categories: vscode
tags: vscode
author: blockxia


---
* content
{:toc}


## 1. 安装好vscode按住shift+ctrl+p输入setting.json选择打开设置首选项设置需要的格式即可(ps我的设置如下，有需要的根据自己需要自行更改)
```
{
  // 设置主题背景色
  "workbench.colorTheme": "Atom One Light",
  "go.useCodeSnippetsOnFunctionSuggest": true,
  // 控制是否将打开的编辑器显示为预览。预览编辑器将会重用至其被保留(例如，通过双击或编辑)，且其字体样式将为斜体。
  "workbench.editor.enablePreview": false,
  // 设置字体大小
  "editor.fontSize": 17,
  "workbench.colorCustomizations": {
    // 设置光标颜色
    "editorCursor.foreground": "#110202",
    "[Atom One Light]": {
      "editor.background": "#C7EDCC",
      "sideBar.background": "#C7EDCC",
      "activityBar.background": "#C7EDCC",
    },
  },
  "editor.fontFamily": "Consolas, 'Courier New', monospace",
  // 指定终端的字体 (注意名字要完全符合font名）
  "terminal.integrated.fontFamily": "Consolas, 'Courier New', monospace",
  // 指定终端字大小
  "terminal.integrated.fontSize": 16,
  // ----------设置字体大小  以上自行配置用户背景色---------
  //"editor.fontSize": 17,
  // vscode默认启用了根据文件类型自动设置tabsize的选项
  "editor.detectIndentation": false,
  // 重新设定tabsize
  "editor.tabSize": 2,
  // #每次保存的时候自动格式化 
  "editor.formatOnSave": true,
  // #去掉代码结尾的分号 
  "prettier.semi": true,
  // #使用单引号替代双引号 
  "prettier.singleQuote": true,
  // #让函数(名)和后面的括号之间加个空格
  "javascript.format.insertSpaceBeforeFunctionParenthesis": false,
  // #这个按用户自身习惯选择 
  "vetur.format.defaultFormatter.html": "js-beautify-html",
  // #让vue中的js按编辑器自带的ts格式进行格式化 
  "vetur.format.defaultFormatter.js": "vscode-typescript",
  "vetur.format.defaultFormatterOptions": {
    "js-beautify-html": {
      "wrap_line_length": 0, // 设置多个字符后换行 0 表示忽略
      "wrap_attributes": "auto", // html 标签属性 换行设置[auto|force|force-aligned|force-expand-multiline] ["auto"]
      "end_with_newline": false // 在文件结尾添加新行
    },
    "prettyhtml": {
      "singleQuote": false,
      "wrapAttributes": false,
      "sortAttributes": false
    }
  },
  // 格式化stylus, 需安装Manta's Stylus Supremacy插件
  "stylusSupremacy.insertColons": false, // 是否插入冒号
  "stylusSupremacy.insertSemicolons": false, // 是否插入分号
  "stylusSupremacy.insertBraces": false, // 是否插入大括号
  "stylusSupremacy.insertNewLineAroundImports": false, // import之后是否换行
  "stylusSupremacy.insertNewLineAroundBlocks": false,
  "explorer.confirmDelete": false, // 两个选择器中是否换行
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  // 每次保存的时候将代码按eslint格式进行修复
  // autoFixedOnSave 设置已废弃，采用如下新的设置
  "eslint.format.enable": true,
  // autoFix默认开启，只需输入字符串数组即可
  "eslint.validate": [
    "javascript",
    "vue",
    "html"
  ],
  "workbench.iconTheme": "vscode-icons",
  "files.autoSave": "off",
  "editor.suggestSelection": "first",
  "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
  "diffEditor.ignoreTrimWhitespace": false,
  "editor.multiCursorModifier": "ctrlCmd",
  "editor.formatOnPaste": true,
  "eslint.codeAction.showDocumentation": {
    "enable": true
  },
  // "workbench.editor.showTabs": true,
  "vue-helper.alias": {
    "@": "src"
  },
  "vue-helper.componentPrefix": {
    "alias": "@",
    "path": "src"
  },
  "peacock.surpriseMeOnStartup": true,
  "sync.gist": "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",
  "files.exclude": {
    "node_modules/": true //  node_modules是否展示在项目中
  },
  "security.workspace.trust.untrustedFiles": "open"
}

```


## 2. 终端快捷键是ctrl+`即可打开终端
```
ctrl+`即可打开终端
```


## 3.ctrl+k和ctrl+s同时按下可以打开快捷键设置，设置成自己习惯用的快捷键
```
ctrl+k和ctrl+s同时按下可以打开快捷键设置
```

## 4.打开左侧菜单栏倒数第二个可以下载前端所需的插件：eslint、Git History(快捷键shift+ctrl+p查找历史记录)、Vetur等
```
shift+ctrl+p查找历史记录
```

## 5.解决VSCode不能粘贴文件问题

```
一、vscede创建快捷方式，右键属性-兼容性-以管理员身份运行此程序

二、1. 以管理员身份运行PowerShell

2. 执行：get-ExecutionPolicy，回复Restricted，表示状态是禁止的

3.执行：set-ExecutionPolicy RemoteSigned

4.选择Y。注意：一定要以管理员的身份运行PowerShell，不是cmd窗口！
```


