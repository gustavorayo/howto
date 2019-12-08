## Dump traffic of all interfaces
* -n dont convert addresses to names
* -q quick output 

```sudo tcpdump -n -q```

## Filter 
* -l Make stdout line buffered
* Print columns 3 and 5

```sudo tcpdump -n -l -q 2>/dev/null | awk '{print $3, $5}'```


## List port mapping

    sudo iptables -t nat -L -n -v

## List open ports
    
Option 1:

    netstat -tulpn | grep LISTEN
Option 2:

    sudo lsof -i -P -n