# hugo-theme-stack-setup

## 下載下載 Hugo 擴展版本
[download hugo extended version 下載 Hugo 擴展版本](https://github.com/gohugoio/hugo/releases)
<br />

## 建立新站點
```pwsh
hugo new site stack-test1
```
<br />

## 下載 Stack 佈景
* [Theme Stack GitHub](https://github.com/CaiJimmy/hugo-theme-stack)
* [Stack Doc 說明文件](https://stack.jimmycai.com/)
```pwsh
git clone https://github.com/CaiJimmy/hugo-theme-stack/ themes/hugo-theme-stack
```
<br />

## 複製 exampleSite 裡的 content 資料夾
```pwsh
Copy-Item .\themes\hugo-theme-stack\exampleSite\content\ .\ -Recurse -Force
```
<br />

## 複製 exampleSite 裡的 config.yaml 設定檔
```pwsh
Copy-Item .\themes\hugo-theme-stack\exampleSite\config.yaml .\stack.yaml
```
<br />

## 指定載入 stack.yaml 設定檔
```pwsh
hugo server --config stack.yaml
```
<br />

## Hugo 參考輸出的訊息
```pwsh
WARN  Search page not found. Create a page with layout: search.
WARN  Archives page not found. Create a page with layout: archives.

                   | EN | ZH-CN | AR
-------------------+----+-------+-----
  Pages            | 47 |    17 | 20
  Paginator pages  |  1 |     0 |  0
  Non-page files   |  5 |     4 |  1
  Static files     |  0 |     0 |  0
  Processed images | 21 |    11 |  3
  Aliases          | 23 |     7 |  9
  Sitemaps         |  2 |     1 |  1
  Cleaned          |  0 |     0 |  0

Built in 166 ms
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```
<br />

## 參考
1. [Markdown 程式碼高亮支援清單](https://www.gushiciku.cn/pl/amoE/zh-tw)
