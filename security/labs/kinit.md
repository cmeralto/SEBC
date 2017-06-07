- kinit

```
[cmeralto@ip-172-31-32-24 ~]$ kinit
Password for cmeralto@CMERALTO.COM:
```
 OR

 ```
[cmeralto@ip-172-31-32-24 ~]$ kinit cmeralto@CMERALTO.COM
Password for cmeralto@CMERALTO.COM:
```

- klist

```
[cmeralto@ip-172-31-32-24 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_500
Default principal: cmeralto@CMERALTO.COM

Valid starting     Expires            Service principal
06/07/17 18:27:21  06/08/17 18:27:21  krbtgt/CMERALTO.COM@CMERALTO.COM
        renew until 06/14/17 18:27:21
```