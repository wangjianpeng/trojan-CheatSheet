## trojan-go certificate failed to renew after 90 days.
if it's the last day. renew certificate 

stop nginx .
```
/etc/trojan_mgr.sh
```
![nginx stop ](/Images/nginx_stop.png)
```
[root@138 ~]# .acme.sh/acme.sh --renew -d domainname(for example :example.com) --ecc
[Fri Jul  8 23:04:04 CST 2022] Renew: 'domainname(for example :example.com)'
[Fri Jul  8 23:04:05 CST 2022] Using CA: https://acme-v02.api.letsencrypt.org/directory
[Fri Jul  8 23:04:05 CST 2022] Standalone mode.
[Fri Jul  8 23:04:05 CST 2022] Single domain='domainname(for example :example.com)'
[Fri Jul  8 23:04:05 CST 2022] Getting domain auth token for each domain
[Fri Jul  8 23:04:06 CST 2022] Getting webroot for domain='domainname(for example :example.com)'
[Fri Jul  8 23:04:06 CST 2022] Verifying: domainname(for example :example.com)
[Fri Jul  8 23:04:06 CST 2022] Standalone mode server
[Fri Jul  8 23:04:08 CST 2022] Pending, The CA is processing your order, please just wait. (1/30)
[Fri Jul  8 23:04:10 CST 2022] Success
[Fri Jul  8 23:04:10 CST 2022] Verify finished, start to sign.
[Fri Jul  8 23:04:10 CST 2022] Lets finalize the order.
[Fri Jul  8 23:04:10 CST 2022] Le_OrderFinalize='https://acme-v02.api.letsencrypt.org/acme/finalize/xxxxx/xxxxxx'
[Fri Jul  8 23:04:11 CST 2022] Downloading cert.
[Fri Jul  8 23:04:11 CST 2022] Le_LinkCert='https://acme-v02.api.letsencrypt.org/acme/cert/xxxxxxxx'
[Fri Jul  8 23:04:11 CST 2022] Cert success.
-----BEGIN CERTIFICATE-----
xxxxxxxxxx
-----END CERTIFICATE-----
[Fri Jul  8 23:04:11 CST 2022] Your cert is in: /root/.acme.sh/domainname(for example :example.com)_ecc/domainname(for example :example.com).cer
[Fri Jul  8 23:04:11 CST 2022] Your cert key is in: /root/.acme.sh/domainname(for example :example.com)_ecc/domainname(for example :example.com).key
[Fri Jul  8 23:04:11 CST 2022] The intermediate CA cert is in: /root/.acme.sh/domainname(for example :example.com)_ecc/ca.cer
[Fri Jul  8 23:04:11 CST 2022] And the full chain certs is there: /root/.acme.sh/domainname(for example :example.com)_ecc/fullchain.cer
[Fri Jul  8 23:04:12 CST 2022] Installing key to: /data/domainname(for example :example.com)/privkey.key
[Fri Jul  8 23:04:12 CST 2022] Installing full chain to: /data/domainname(for example :example.com)/fullchain.crt

```
.acme.sh path is /root/.acme.sh

domainname(for example :example.com) is the domain name.

![renew cert by manual](/Images/cert_check.png)

resart trojan-go

```
/etc/trojan_mgr.sh
```

if the trojan is still not working.

run the following code to start trojan-go

```
[root@138 ~]# /etc/trojan/bin/trojan-go -config /etc/trojan/conf/server.json 
[INFO]  2022/07/08 23:22:50 trojan-go v0.8.1 initializing
[WARN]  2022/07/08 23:22:50 empty tls fallback port
........
```

![start trojan-go by manual](/Images/start_bymanual.png)

at last, reset trojan-go with /etc/trojan_mgr.sh

![restart trojan-go by control panel](/Images/start_bycmd.png)

