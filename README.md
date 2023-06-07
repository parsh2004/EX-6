# EX-6 IMPLEMENTATION OF PING COMMAND
DATE :10-04-2023

# AIM :
To write the python program for simulating ping command.

# ALGORITHM :
```
1.start the program.
2.Include necessary package in java.
3.To create a process object p to implement the ping command.
4.declare one Buffered Reader stream class object.
5.Get the details of the server
6.length of the IP address.
7.time required to get the details.
8.send packets, receive packets and lost packets.
9.minimum, maximum and average times.
10.print the results.
11.Stop the program.
```
# PROGRAM :
```
Developed By: Parshwanath M
Register Number: 212221230073
```
## CLIENT :
```

import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
 ```
## SERVER :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
# OUTPUT :
## CLIENT :
![##6](https://github.com/parsh2004/EX-6/assets/95388047/946d7725-71df-4fd2-9cc9-dcf2d33e7110)

## SERVER :
![###6](https://github.com/parsh2004/EX-6/assets/95388047/e6af7c6c-f833-46f3-a40d-d4e70828f939)

# RESULT :
Thus, the python program for simulating ping command was successfully executed.
