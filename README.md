CVE-2023-51385 poc

OpenSSH ProxyCommand RCE poc

OpenSSH <9.6 命令注入漏洞poc
[中文](README.zh.md)
<div align="center">
  <img src="https://github.com/WLaoDuo/CVE-2023-51385_poc-test/blob/main/clac.gif", alt="" />
</div>
<div align="center">
  <img src="https://github.com/WLaoDuo/CVE-2023-51385_poc-test/blob/main/pop%20firefox.gif", alt="" />
</div>

## 1.`vim ~/.ssh/config` or edit `C:/Users/username/.ssh/config` on windows system

```
host *.example.com
  ProxyCommand /usr/bin/nc -X connect -x 192.0.2.0:8080 %h %p
```

## 2. `git clone https://github.com/WLaoDuo/CVE-2023-51385_poc-test --recurse-submodules`

A submodule which would exploit this vulnerability to pop a firefox on kali or calc.exe on windows.


thanks to https://github.com/vin01/poc-proxycommand-vulnerable-v2
