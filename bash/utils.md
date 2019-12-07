# Dump traffic of all interfaces
* -n dont convert addresses to names
* -q quick output 

```sudo tcpdump -n -q```

#Filter 
* -l Make stdout line buffered
* print columns 3 and 5

```sudo tcpdump -n -l -q 2>/dev/null | awk '{print $3, $5}'```