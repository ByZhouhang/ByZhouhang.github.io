---
title: 右键添加-在此处打开CMD
date: 2019-02-11 19:24:40
tags:
  - cmd
  - 右键   
categories: 注册表操作
---

## 操作说明
    新建文本文件，将后缀改为reg  然后点击运行  确认修改注册表
``` bash
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\shell\OpenCmdHere]
@="Open CMD in Here"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\Directory\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd "%V""

[HKEY_CLASSES_ROOT\Directory\Background\shell\OpenCmdHere]
@="Open CMD in Here"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd \"%V\""

[HKEY_CLASSES_ROOT\Drive\shell\OpenCmdHere]
@="Open CMD in Here"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\Drive\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd \"%V\""

[HKEY_CLASSES_ROOT\LibraryFolder\background\shell\OpenCmdHere]
@="Open CMD in Here"
"Icon"="cmd.exe"

[HKEY_CLASSES_ROOT\LibraryFolder\background\shell\OpenCmdHere\command]
@="cmd.exe /s /k pushd \"%V\""
```