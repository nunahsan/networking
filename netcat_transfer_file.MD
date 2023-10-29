# on server side (IP : 123.123.123.123)
```
cat <filename> | nc -lnvp <PORT>
```
e.g : cat abc.json | nc -lnvp 8080 

# on client side
```
nc -v <SERVER_IP> <SERVER_PORT> > <filename>
```
e.g: nc -v 123.123.123.123 8080 > abc.json
