```
[root@ip-172-31-32-24 ~]# cat /etc/krb5.conf
```

```
[libdefaults]
default_realm = CMERALTO.COM
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = arcfour-hmac
default_tkt_enctypes = arcfour-hmac
permitted_enctypes = arcfour-hmac
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
CMERALTO.COM = {
kdc = ip-172-31-32-24.eu-west-1.compute.internal
admin_server = ip-172-31-32-24.eu-west-1.compute.internal
}
```
