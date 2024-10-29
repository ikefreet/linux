# linux

## ping(icmp) shell script
```
#!/bin/bash

if [ -f impossible.txt ]; then
  rm impossible.txt
fi

if [ -f possible.txt ]; then
  rm possible.txt
fi

for (( i=1; i<255; i++)); do
  ip=172.30.0.$i
  ping -c1 $ip
  if [ $? -eq 0 ]; then
    echo $ip >> impossible.txt
  else
    echo $ip >> possible.txt
  fi
done
```
