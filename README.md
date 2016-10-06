# ngx#genba

### (i.e. engine X hashgen BA)


kinda replica of **htpasswd** util from [apache httpd](https://httpd.apache.org/) toolset, ```ngx#genba``` inherits the basics of its prototype & offers similar
workflow to maintain the task. the thing is, ```ngx#genba``` is targeted at [nginx](https://nginx.org) w/ the goal to make web more secure & safe by providing
simple solution to obtain modern strong hashes based on actual crypto
methods for nginx [auth_basic](http://nginx.org/en/docs/http/ngx_http_auth_basic_module.html) & to get rid of obsolete insecure oldies like
crypt, sha, md5 et cetera  

#### engineXhashgenBA v0.08.1.060916.4.8



```

usage: ngx#genba ⌘ ngx#genba username ⌘ ngx#genba username password

```




```ngx#genba``` turns username & password passed by user into the hash pair for
[auth_basic_user_file](http://nginx.org/en/docs/http/ngx_http_auth_basic_module.html#auth_basic_user_file) in interactive, semi-interactive
or non-interactive way. hash pairs are secured w/ **SSHA** (salted SSH-1; [strong,
durable & trustworthy scheme](https://goo.gl/CcksEm), widely used by **openldap**
& **dovecot** on regular basics & recommended by nginx). hashes meet the guidlines
declared at [sec 5.3 rfc2307](https://goo.gl/x4ZXmy)


```

ngx#genba username password >>/etc/nginx/conf.d/vhosts/auth/.vhost14-userfile

```


username & password are accepted either via **cl args** or from **stdin**. outcome is published to startdard **stdout** stream & copypaste phase may be omitted since
the result can be easily put directly to your auth_basic_user_file w/ pipes.
passing both username & password via command line forces non-interactive mode
i.e. any output to stdout except for the hash is suppressed


```

ngx#genba stepansraka `cat /root/.webpwdplain | grep stepansraka | cut -d: -f2` 

```


if you beleive no password should never be typed at cl nowai, you still can apply workaround like shown above to obtain batch processing while your passwords will stay safe away from cl

**glory to Ukraine!**

Juliy V. Chirkov,  
[twitter.com/juliychirkov](https://twitter.com/juliychirkov)
