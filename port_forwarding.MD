# clear existing rule on table nat
```
iptables -t nat -F
```

# forward traffic on port 23 to anotherip:port
```
sudo iptables -t nat -A PREROUTING -p tcp --dport 23 -j DNAT --to-destination 192.168.100.92:22
```

# forward back traffic from anotherip:port to this server
```
sudo iptables -t nat -A POSTROUTING -p tcp -d 192.168.100.92 --dport 22 -j SNAT --to-source 192.168.100.91
```

# save iptables to make it persistence
```
iptables-save
```

# check iptables rule on nat
```
iptables -t nat -nvL --line-numbers
```

# enable rule to allow port forwarding (debian)
```
1. edit => /etc/sysctl.conf
2. change value to 1 or uncomment if it was commented before => net.ipv4.ip_forward=1
3. check => sysctl -p
```
