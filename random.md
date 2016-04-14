We can use this command to create random passwords.

```
cat /dev/urandom|tr -dc "a-zA-Z0-9-_\$\?\*\%\$\@\(\)\_\+"|fold -w 13|head 
```

