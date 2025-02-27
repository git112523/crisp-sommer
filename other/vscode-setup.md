---
title: VSCode 設定
date: 2025-2-27
---
<br />

## AutoCAD 指令
- [AutoCAD 指令](#autocad-指令)
- [Prettier 設定](#prettier-設定)
- [右鍵用 VSCode 編輯檔案](#右鍵用-vscode-編輯檔案)

## Prettier 設定
* Prettier 設定。  
   ```json
   "[javascript]": {  //預設javascript檔案由prettier格式化
        "editor.defaultFormatter": "esbenp.prettier-vscode",
        "prettier.singleQuote": true,
        "prettier.semi": false,
        "prettier.trailingComma": "es5"
    },
   ```
   [[回最上層目錄]](#top)
<br />

## 右鍵用 VSCode 編輯檔案
* 右鍵用 VSCode 編輯檔案.reg
  ```shell
   Windows Registry Editor Version 5.00
      
   [HKEY_CLASSES_ROOT\*\shell\VSCode]
   @="用 VSCode 編輯檔案"
   "Icon"="C:\\Program Files\\Microsoft VS Code\\Code.exe"
      
   [HKEY_CLASSES_ROOT\*\shell\VSCode\command]
   @="\"C:\\Program Files\\Microsoft VS Code\\Code.exe\" \"%1\""

   Windows Registry Editor Version 5.00
      
   [HKEY_CLASSES_ROOT\Directory\shell\VSCode]
   @="用 VSCode 開啟為專案"
   "Icon"="C:\\Program Files\\Microsoft VS Code\\Code.exe"
      
   [HKEY_CLASSES_ROOT\Directory\shell\VSCode\command]
   @="\"C:\\Program Files\\Microsoft VS Code\\Code.exe\" \"%V\""
      
   Windows Registry Editor Version 5.00
      
   [HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode]
   @="用 VSCode 開啟為專案"
   "Icon"="C:\\Program Files\\Microsoft VS Code\\Code.exe"
      
   [HKEY_CLASSES_ROOT\Directory\Background\shell\VSCode\command]
   @="\"C:\\Program Files\\Microsoft VS Code\\Code.exe\" \"%V\""
  ```