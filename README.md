# consul-utils

#/etc/init.d/consul for CentOS 6



# wget consul init.d script 

#Chkconfig command tool allows to configure services start and stop automatically in the /etc/rd.d/init.d scripts through command line
``` bash
$cd /etc/init.d/
$ wget https://raw.githubusercontent.com/sivachinnayan/consul-utils/master/consul
$chmod 755 consul
$chkconfig --add /etc/init.d/consul
$chkconfig --level 2345 consul on
```

How to start consul server
```bash
service consul start 
```
How to stop consul server
```bash
service consul stop 
```
Check consl status/logs
```bash
$service consul status
[root@localhost log]# pwd 
/var/log
[root@localhost log]# tail -10 consul.log 
    2016/08/25 17:19:46 [WARN] agent: Check 'service:webservice-bots-platform:1' is now critical
    2016/08/25 17:19:50 [DEBUG] agent: check 'service:web' script 'curl localhost >/dev/null 2>&1' output: 
    2016/08/25 17:19:50 [WARN] agent: Check 'service:web' is now critical
    2016/08/25 17:19:50 [WARN] agent: http request failed 'http://localhost:80/checkservice': Get http://localhost:80/checkservice: dial tcp [::1]:80: getsockopt: connection refused
    2016/08/25 17:19:50 [WARN] agent: http request failed 'http://localhost:80/': Get http://localhost:80/: dial tcp [::1]:80: getsockopt: connection refused
    2016/08/25 17:19:50 [WARN] agent: http request failed 'http://localhost:80/': Get http://localhost:80/: dial tcp [::1]:80: getsockopt: connection refused
    2016/08/25 17:19:51 [WARN] agent: socket connection failed 'localhost:3415': dial tcp [::1]:3415: getsockopt: connection refused
    2016/08/25 17:19:51 [WARN] agent: http request failed 'http://localhost:8080/checkservice': Get http://localhost:8080/checkservice: dial tcp [::1]:8080: getsockopt: connection refused
    2016/08/25 17:19:51 [DEBUG] agent: check 'service:webservice-bots-platform:1' script 'some_scripts.sh param1 param2' output: /bin/sh: some_scripts.sh: command not found
    2016/08/25 17:19:51 [WARN] agent: Check 'service:webservice-bots-platform:1' is now critical
[root@localhost log]# 

```






