---
title: 設定 SSH 連線 GitLab / GitHub
date: 2023-12-23
---
>
> gitlab-ssh-connect-setup
>
<br />

# 設定 SSH 連線 GitLab / GitHub

## 檢查本地是否已經存在 SSH KEY

```shell
cd ~/.ssh
ls

// 看是否存在 id_rsa 和 id_rsa.pub檔案。
// 如果存在，說明已經有SSH Key。
```
<br />

## 產生金鑰
```shell
$ ssh-keygen -t rsa -b 4096 -C "git112523@gmail.com"
```
<br />

## 上傳公鑰
```shell
$ cat ~/.ssh/id_rsa.pub

// 將內容複製到 GitLab / GitHub 上。
```
<br />

## 測試 SSH 連線
* 出現 Welcome 訊息就連線成功
```shell
$ ssh -T git@gitlab.com
// or
$ ssh -T git@github.com
```
<br />

## 設定 SSH agent
```shell
$ eval $(ssh-agent -s)
$ ssh-add ~/.ssh/id_rsa
```
<br />

## Git UserName UserEmail 設定
```shell
$ git config --global user.name "Alex K"
$ git config --global user.email "git112523@gmail.com"

// 觀察目前設定檔
$ git config --list
```
<br />

## 參考
1. [git clone with SSH keys 或 HTTPS 設定步驟](https://tsengbatty.medium.com/git-%E8%B8%A9%E5%9D%91%E7%B4%80%E9%8C%84-%E4%BA%8C-git-clone-with-ssh-keys-%E6%88%96-https-%E8%A8%AD%E5%AE%9A%E6%AD%A5%E9%A9%9F-bdb721bd7cf2)