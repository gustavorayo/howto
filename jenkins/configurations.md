## Change teporal directory

### Motivation

Disk space low in /tmp and the master node goes offline \
<span style="color:red">Disk space is too low. Only 0.881GB left on /tmp.</span>

### Solution in CentOS
* Edit file  ```/etc/sysconfig/jenkins``` and add the follwin argument:

```bash
JENKINS_JAVA_OPTIONS="-Djava.awt.headless=true -Djava.io.tmpdir=/var/tmp"
```
* Restart jenkins \
```sudo  systemctl restart jenkins```

