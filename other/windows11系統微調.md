---
title: Windows 11 密技及系統微調
date: 2023-11-24
---
<br />

> 以下是觀看論壇文章 [一些關於 Windows 11 22H2 的密技](https://www.coolaler.com/forums/threads/windows-11-22h2.369846/)，及一些網路搜尋來的資訊所做的筆記。
> 
> 大部份的密技和系統微調不論是 Windows 10 或是 Windows 11 兩者都是差不多的，只是 Windows 11 做了一些介面的美化增加更多硬體支援，我覺得底層核心都是一樣的。
> 
> 真正有重大變革應該放在 Windows 12 上，因為可以預期的加上大量 AI 運用，倒是可以期待。
<br />

## <a id="top"></a>Windows 11 密技及系統微調
1. [Windows 11 安裝時建立「本機帳號」](#local_account)
2. [變更 Windows 預設輸入法](#IME)
3. [安裝 Windows 11 略過「TPM 2.0 及 Secure Boot」](#TPM)
4. [登入「Administrator 帳戶」](#admin_account)
5. [解除「本機帳號」密碼設置](#account_password)
6. [關閉「UAC 功能」](#UAC)
7. [安裝「Net Framework 3.5」](#framework35)
8. [Windows 11 啟動「安全模式」](#safemode)
9. [滑鼠右鍵回復為「傳統右鍵表單選項」](#rightclick_original)
10. [隱藏「檔案總管」本機「下載」](#hide_download)
11. [隱藏「檔案總管」本機「文件」](#hide_document)
12. [隱藏「檔案總管」本機「音樂」](#hide_music)
13. [隱藏「檔案總管」本機「桌面」](#hide_desktop)
14. [隱藏「檔案總管」本機「圖片」](#hide_picture)
15. [隱藏「檔案總管」本機「影片」](#hide_movie)
16. [隱藏「檔案總管」目錄欄中的「常用」](#quick_access)
17. [隱藏「檔案總管」目錄欄中的「OneDrive」](#hide_onedrive)
18. [隱藏「檔案總管」目錄欄中的「網路」](#hide_network)
19. [開始面板下方「電源開關」旁加入「設定、檔案總管」的捷徑](#powerkey_shortcut)
20. [關閉工具列的預覽功能](#close_thumbnail)
21. [關閉自動更新](#close_update)
22. [移除或關閉 Windows Defender](#close_defender)
23. [關閉「Windows 安全性通知」](#close_safenotify)
24. [隱藏工作列右邊的「通知圖示」](#close_notifyicon)
25. [關閉「自動播放」](#close_autoplay)
26. [啟動「沙盒 SandBox」功能](#sandbox)
27. [啟動 Windows 11](#startup)
<br />

## <a id="local_account"></a>Windows 11 安裝時建立「本機帳號」

1. 安裝前先拔除網路線，當安裝到「讓我們將您連線到網路 Let's connect you to a network」畫面時，按「Shift + F10」打開「命令提示字元」，鍵入 **oobe\bypassnro** 按 Enter，之後會自動重新開機，繼續安裝。
2. 一樣安裝到「讓我們將您連線到網路」畫面時，就會有「我沒有網際網路 I don't have internet」選項，點選「進行有限的安裝 Continue with limited setup」。
3. 之後就可以建立「本機帳戶」。
   
   [[回最上層目錄]](#top)
<br />

## <a id="IME"></a>變更 Windows 預設輸入法

1. 安裝慣用的輸入法如：「自然輸入法」，如果沒有可以跳過此步驟。
2. 點擊工具列上輸入法圖示「語言喜好設定」→ 「新增慣用語言」。
    **增加「English(United States)」**
3. 注意 Windows 顯示語言為「中文(台灣)」。
4. 移除微軟注音輸入法。
5. 點擊「輸入與鍵盤設定」→ 「進階鍵盤設定」「覆寫預設輸入法」選擇「英文(美國)-US」。
6. 重新開機即可完成設定。

   [[回最上層目錄]](#top)
<br />

## <a id="TPM"></a>安裝 Windows 11 略過「TPM 2.0 及 Secure Boot」

* 使用 [Rufus - 輕鬆製作可開機的USB 磁碟機](https://rufus.ie/zh_TW/)，製作可開機 USB，有進階選單可選。

   [[回最上層目錄]](#top)
<br />

## <a id="admin_account"></a>登入「Administrator 帳戶」
1. 按「Win + R」輸入「lusrmgr.msc」按確定。
2. 跳出「本機使用者和群組」先點選左方窗格的「使用者」，再按兩下中央窗格的「Administrator」
3. 跳出「Administrator 內容」對話盒，取消勾選「帳戶已停用」，按確定。
4. 切換使用者時「Administrator 帳戶」就會出現了。

   [[回最上層目錄]](#top)
<br />

## <a id="account_password"></a>解除「本機帳號」密碼設置
1. 「設定」→「帳戶」→「登入選項」→「密碼」→「變更」。
2. 畫面「輸入目前密碼」，若沒有則維持空白。
3. 畫面「變更您的密碼」，保持空白不要輸入，下一步，這就是解除密碼。
4. 同理如果您要變更新的密碼，就是在這邊輸入新的密碼。

   [[回最上層目錄]](#top)
<br />

## <a id="UAC"></a>關閉「UAC 功能」
* 「控制台」→「使用者帳戶」→「變更使用者帳戶控制設定」，將拉桿拉到最下面。

   [[回最上層目錄]](#top)
<br />

## <a id="framework35"></a>安裝「Net Framework 3.5」
1. 掛載 Windows 11 的安裝 ISO 檔案，假設掛載於 「G：」。
2. 以「系統管理員身份執行」開啟「命令提示字元」，輸入以下命令並執行。

   ```Shell
   Dism /online /enable-feature /featurename:NetFX3 /All /Source:G:\sources\sxs /LimitAccess
   ```
   
3. 在「開始」→「設定」→「應用程式」→「選用功能」→「更多選用功能」。
4. 確認「Net Framework 3.5」是否已經勾選。

   [[回最上層目錄]](#top)
<br />

## <a id="safemode"></a>Windows 11 啟動「安全模式」
1. 按住「Shift」鍵不放，再點「開始」→「電源」→「重新啟動」。
2. 出現「選擇選項」→「疑難排解」→「進階選項」→「啟動設定」→「重新啟動」。
3. 重新開機到「啟動設定」頁面，選「啟用安全模式」。

   [[回最上層目錄]](#top)
<br />

## <a id="rightclick_original"></a>滑鼠右鍵回復為「傳統右鍵表單選項」
1. 以「系統管理員身份執行」開啟「命令提示字元」，輸入以下命令並執行。

   ```Shell
   reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
   ```
   
   重新開機。
2. 若要恢複為 Windows 11 預設的，輸入以下命令並執行。

   ```Shell
   reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f
   ```
   
   重新開機。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_download"></a>隱藏「檔案總管」本機「下載」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions\{7d83ee9b-2244-4e70-b1f5-5393042af1e4}\PropertyBag
   ```

2. 將「ThisPCPolicy」的「字串」改為「Hide」，預設是「Show」。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_document"></a>隱藏「檔案總管」本機「文件」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions\{f42ee2d3-909f-4907-8871-4c22fc0bf756}\PropertyBag
   ```

2. 將「ThisPCPolicy」的「字串」改為「Hide」，預設是「Show」。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_music"></a>隱藏「檔案總管」本機「音樂」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions\{a0c69a99-21c8-4671-8703-7934162fcf1d}\PropertyBag
   ```

2. 將「ThisPCPolicy」的「字串」改為「Hide」，預設是「Show」。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_desktop"></a>隱藏「檔案總管」本機「桌面」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions\{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}\PropertyBag
   ```

2. 在右邊面板按「滑鼠右鍵」→「新增」→「字串值」。
3. 「數值名稱」輸入「ThisPCPolicy」。
4. 「數值資料」鍵入「Hide」。
5. Windows 11 Ver.22H2，預設是沒有這個字串的，必須手動新增。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_picture"></a>隱藏「檔案總管」本機「圖片」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions\{0ddd015d-b06c-45d5-8c4c-f59713854639}\PropertyBag
   ```

2. 將「ThisPCPolicy」的「字串」改為「Hide」，預設是「Show」。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_movie"></a>隱藏「檔案總管」本機「影片」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions\{35286a68-3c57-41a1-bbb1-0eae73d76c95}\PropertyBag
   ```

2. 將「ThisPCPolicy」的「字串」改為「Hide」，預設是「Show」。

   [[回最上層目錄]](#top)
<br />

## <a id="quick_access"></a>隱藏「檔案總管」目錄欄中的「常用」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer
   ```

2. 在右邊面板，按「滑鼠右鍵」→「新增」→「DWORD (32-bit) 值」。
3. 「數值名稱」鍵入「HubMode」。
4. 「數值資料」填入「1」。
5. 「底數」點選「十六進位」。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_onedrive"></a>隱藏「檔案總管」目錄欄中的「OneDrive」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_CLASSES_ROOT\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}
   ```

2. 修改「system.IsPinnedToNameSpaceTree」的值為 0 即可，預設值是 1。

   [[回最上層目錄]](#top)
<br />

## <a id="hide_network"></a>隱藏「檔案總管」目錄欄中的「網路」
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_CLASSES_ROOT\CLSID\{F02C1A0D-BE21-4350-88B0-7367FC96EF3C}
   ```

2. 必須先取得此位置的「權限」。
3. 在右邊面板，按「滑鼠右鍵」→「新增」→「DWORD (32-bit) 值」。
4. 「數值名稱」設為「System.IsPinnedToNameSpaceTree」。
5. 「數值資料」設為「0」。
6. 「底數」點選「十六進位」。

   [[回最上層目錄]](#top)
<br />

## <a id="powerkey_shortcut"></a>開始面板下方「電源開關」旁加入「設定、檔案總管」的捷徑
1. 「開始」→「設定」→「個人化」→「開始」→「資料夾 Folders」。
2. 將要加入的捷徑，如「設定」或「檔案總管」設為「開啟」。

   [[回最上層目錄]](#top)
<br />

## <a id="close_thumbnail"></a>關閉工具列的預覽功能
1. 「Win鍵 + R」輸入「regedit」開啟「登錄檔編輯程式」，找到下列登錄碼。

   ```Shell
   HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced
   ```

2. 在右邊面板，按「滑鼠右鍵」→「新增」→「DWORD (32-bit) 值」。
3. 「數值名稱」設「ExtendedUIHOVERTIME」。
4. 「數值資料」設為「9000」。
5. 「底數」點選「十六進位」。
6. 接著找到下列機碼。

   ```Shell
   HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Taskband
   ```

7. 在右邊面板，按「滑鼠右鍵」→「新增」→「DWORD (32-bit) 值」。
8. 「數值名稱」設「NUMTHUBBNAILS」。
9. 「數值資料」設為「0」。
10. 「底數」點選「十六進位」。

    [[回最上層目錄]](#top)
<br />

## <a id="close_update"></a>關閉自動更新
關閉自動更新使用第三方工具比較方便。
1. [UH Auto Update Stopper Ver.1.2](https://unikoshardware.com/2021/12/uh-auto-update-stopper-v1-2.html)
2. [Stop Updates Windows 10 Ver.3.7.2022.07.12](https://www.azofreeware.com/2018/04/stopupdates10.html?m=1)

   [[回最上層目錄]](#top)
<br />

## <a id="close_defender"></a>移除或關閉 Windows Defender
1. [Defender Control Ver.2.1](https://www.sordum.org/9480/defender-control-v2-1/)
2. [UH Auto Update Stopper Ver.1.2](https://unikoshardware.com/2021/12/uh-auto-update-stopper-v1-2.html)
3. Windows Defender Remover Script Ver.10.3.0.0

   [[回最上層目錄]](#top)
<br />

## <a id="close_safenotify"></a>關閉「Windows 安全性通知」
1. 「開始」→「設定」→「系統」→「通知」照下列順序設定。
2. 先將「設定」設為「關閉」。
3. 「啟動應用程式通知」設為「關閉」。
4. 「其它設定」裡的項目，全部不打勾。
5. 將「通知」設為「關閉」。
6. 將「請勿打擾」設為「關閉」。若設為「開啟」，則無法隱藏「通知圖示」。
7. 「設定優先順序通知」。
8. 「通話和提醒」下的項目，全部不打勾。
9. 「應用程式」下的每個「應用程式」，按右邊的「...」→「移除」。
10. 「Win鍵 + R」輸入「gpedit.msc」開啟「本機群組原則編輯器」展開到「電腦設定→「系統管理範本」→「開始功能表和工作列」→「通知」。
11. 將「關閉通知網路使用方式」設為「已啟用」。

    [[回最上層目錄]](#top)
<br />

## <a id="close_notifyicon"></a>隱藏工作列右邊的「通知圖示」
1. 「Win鍵 + R」輸入「gpedit.msc」開啟「本機群組原則編輯器」。
2. 展開到「使用者設定」→「系統管理範本」→「開始功能表和工作列」。
3. 將「移除通知與重要訊息中心」設為「已啟用」。

   [[回最上層目錄]](#top)
<br />

## <a id="close_autoplay"></a>關閉「自動播放」
1. 「Win鍵 + R」輸入「gpedit.msc」開啟「本機群組原則編輯器」。
2. 展開到「電腦設定」→「系統管理範本」→「Windows 元件」→「自動播放原則」。
3. 在右邊窗格中，雙擊「設定 AutoRun 的預設行為」。點選「已啟用」。
4. 「預設 AutoRun 行為」設為「不執行任何 AutoRun 命令」。

   [[回最上層目錄]](#top)
<br />

## <a id="sandbox"></a>啟動「沙盒 SandBox」功能
1. BIOS 中的「虛擬功能」必須「啟動」。
2. 在「開始」→「設定」→「應用程式」→「選用功能」→「更多 Windows 功能」裡，將「Windows 沙箱」打勾。重新啟動。

   [[回最上層目錄]](#top)
<br />

## <a id="startup"></a>啟動 Windows 11
* 以系統管理員執行命令提示字元。
* 依序輸入並執行下列命令

  ```Shell
  slmgr /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX

  slmgr /skms kms.loli.best

  slmgr /ato
  ```
  
   [[回最上層目錄]](#top)
<br />
