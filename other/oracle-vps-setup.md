---
title: 甲骨文雲 VPS 建立過程
date: 2023-12-16
---
<br />

> oracle vps setup

<br />

# 甲骨文雲 VPS 防火牆設定
1. 取得權限
    甲骨文雲 VPS 預設不允許 ROOT 遠端SSH登入。
```shell
sudo -i
```
<br />

2. 觀察 iptables 規則
    觀察主機一開始預設的 iptables 規則，基本上會看到很多我們並用不到的規則，大多數都是甲骨文雲服務相關。
```shell
iptables -L
```
<br />

3. 卸載 iptables 規則
    直接將規則一次性清空，再寫入我們需要的規則。
```shell
apt purge -y iptables-persistent
```
<br />

4. 重開機
```shell
reboot
```
<br />

5. 再次觀察 iptables 規則
```shell
iptables -L
```
看到下面的規則，表示規則移除成功。
```shell
Chain INPUT (policy ACCEPT)
target     prot opt source               destination         

Chain FORWARD (policy ACCEPT)
target     prot opt source               destination         

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination
```
<br />

6. 重新安裝iptables規則
    安裝過程中，大多數按 y 通過即可。
```shell
apt update -y && apt install -y iptables-persistent
```
<br />

7. 編輯規則
```shell
nano /etc/iptables/rules.v4
```

貼上下方編輯內容儲存退出。

```shell
*filter 

:INPUT DROP [0:0] 

:FORWARD DROP [0:0] 

:OUTPUT ACCEPT [0:0] 

-A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT 

-A OUTPUT -m state --state ESTABLISHED,RELATED -j ACCEPT 

-A INPUT -p tcp --dport 22 -j ACCEPT

-A INPUT -i lo -j ACCEPT

COMMIT
```
<br />

8. 加載剛剛編輯的規則
```shell
iptables-restore < /etc/iptables/rules.v4
```
<br />

9. 再次觀察iptables規則
```shell
iptables -L
```

出現下方訊息，表示新規則載入成功。

```shell
Chain INPUT (policy DROP)
target     prot opt source               destination         
ACCEPT     all  --  anywhere             anywhere             state RELATED,ESTABLISHED
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:ssh
ACCEPT     all  --  anywhere             anywhere            

Chain FORWARD (policy DROP)
target     prot opt source               destination         

Chain OUTPUT (policy ACCEPT)
target     prot opt source               destination         
ACCEPT     all  --  anywhere             anywhere             state RELATED,ESTABLISHED
```
<br />

10. 開機載入規則
```shell
systemctl enable netfilter-persistent
```

系統訊息：

```shell
Synchronizing state of netfilter-persistent.service with SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install enable netfilter-persistent
```
<br />

11. 也可以重啟服務
```shell
systemctl restart netfilter-persistent
```
<br />

12. 重開機
```shell
reboot
```
<br />

# 更改 SSH 預設服務端口 22
1. 新增檔案 ```/etc/ssh/sshd_config.d/local.conf``` 並編輯。
```shell
nano /etc/ssh/sshd_config.d/local.conf
```
```shell
# 禁止 Root 遠程 SSH 登入
PermitRootLogin no

# 禁止 SSH 使用密碼登入
PasswordAuthentication no

# 修改你自訂的 Port
Port 2222
```
<br />

2. 修改防火牆設定。
<br />

3. 防火牆修改好後，重新啟動 sshd 服務
```shell
sudo systemctl restart sshd
```
<br />

# 參考資料
1. 申請甲骨文雲：[零度解說：永久免費白嫖甲骨文 VPS](https://youtu.be/5a5tdJh8mKY?si=F9nIkVyApk6JQxIv)
2. SSH 連線：[云哥科技：甲骨文亚马逊主机SSH密钥改用户名密码登录连接演示](https://youtu.be/gnT7E-ASGjo?si=Ju18nNGcsNTlfg1i)
3. VPS 優化：[科技lion：甲骨文云VPS如何调教达到最佳状态？拿捏防火墙设置 探寻失联真相 原厂系统全面优化 无需DD系统](https://youtu.be/gKiM1kzjThs?si=yBMGqiwNhreLdpMF)
   * [科技lion博客](https://kejilion.blogspot.com/)
   * [科技lion博客導航頁](https://dh.kejilion.pro)
4. SSH 軟體：[SSH跨平台终端工具tabby推荐](https://blog.csdn.net/weixin_39510813/article/details/125864998)
5. https://blog.owo9.com/p/enhanced-ssh-login-system/
