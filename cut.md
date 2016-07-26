##  Cut 命令 

```
以/etc/passwd的前五行内容为例：
[rocrocket@rocrocket programming]$ cat /etc/passwd|head -n 5
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
[rocrocket@rocrocket programming]$ cat /etc/passwd|head -n 5|cut -d : -f 1
root
bin
daemon
adm
lp
看到了吧，用-d来设置间隔符为冒号，然后用-f来设置我要取的是第一个域，再按回车，所有的用户名就都列出来了
```


```
ubuntu@studio:~$ ifconfig wlan0 | grep "inet addr"
          inet addr:192.168.1.105  Bcast:192.168.1.255  Mask:255.255.255.0
ubuntu@studio:~$ 
```

读取本机wlan0的IP地址


```
ifconfig wlan0 | grep "inet addr" | cut -d :  -f 2 | cut -d " " -f 1
```

读取广播地址

```
ifconfig wlan0 | grep "inet addr" | cut -d :  -f 3 | cut -d " " -f 1
```

读取掩码

```
ifconfig wlan0 | grep "inet addr" | cut -d :  -f 4 | cut -d " " -f 1
```

### Reference

- cnblogs: [linux之cut用法](http://www.cnblogs.com/dong008259/archive/2011/12/09/2282679.html)
