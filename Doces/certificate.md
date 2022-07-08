## trojan-go certificate failed to renew after 90 days.
if it's the last day. renew certificate 

stop nginx .
```
/etc/trojan_mgr.sh
```
```
[root@138 ~]# .acme.sh/acme.sh --renew -d trojanjx2.tmdjx.online --ecc
[Fri Jul  8 23:04:04 CST 2022] Renew: 'trojanjx2.tmdjx.online'
[Fri Jul  8 23:04:05 CST 2022] Using CA: https://acme-v02.api.letsencrypt.org/directory
[Fri Jul  8 23:04:05 CST 2022] Standalone mode.
[Fri Jul  8 23:04:05 CST 2022] Single domain='trojanjx2.tmdjx.online'
[Fri Jul  8 23:04:05 CST 2022] Getting domain auth token for each domain
[Fri Jul  8 23:04:06 CST 2022] Getting webroot for domain='trojanjx2.tmdjx.online'
[Fri Jul  8 23:04:06 CST 2022] Verifying: trojanjx2.tmdjx.online
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
[Fri Jul  8 23:04:11 CST 2022] Your cert is in: /root/.acme.sh/trojanjx2.tmdjx.online_ecc/trojanjx2.tmdjx.online.cer
[Fri Jul  8 23:04:11 CST 2022] Your cert key is in: /root/.acme.sh/trojanjx2.tmdjx.online_ecc/trojanjx2.tmdjx.online.key
[Fri Jul  8 23:04:11 CST 2022] The intermediate CA cert is in: /root/.acme.sh/trojanjx2.tmdjx.online_ecc/ca.cer
[Fri Jul  8 23:04:11 CST 2022] And the full chain certs is there: /root/.acme.sh/trojanjx2.tmdjx.online_ecc/fullchain.cer
[Fri Jul  8 23:04:12 CST 2022] Installing key to: /data/trojanjx2.tmdjx.online/privkey.key
[Fri Jul  8 23:04:12 CST 2022] Installing full chain to: /data/trojanjx2.tmdjx.online/fullchain.crt

```
.acme.sh path is /root/.acme.sh

trojanjx2.tmdjx.online is the domain name.

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
at last, reset trojan-go with /etc/trojan_mgr.sh

