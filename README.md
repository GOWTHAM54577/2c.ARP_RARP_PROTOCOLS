# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
## PROGRAM - ARP
## CLIENT PROGRAM:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
## SERVER PROGRAM:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT - ARP
## CLIENT OUTPUT:
![Screenshot 2024-03-13 094355](https://github.com/NaliniG007/2c.ARP_RARP_PROTOCOLS/assets/144589420/0afa0a14-0c41-4ed5-a7b1-5f228da04772)
## SERVER OUTPUT:
![Screenshot 2024-03-13 094359](https://github.com/NaliniG007/2c.ARP_RARP_PROTOCOLS/assets/144589420/66faf327-9f75-4e50-bce0-95b33cbffd1c)
## PROGRAM - RARP
## CLIENT PROGRAM:
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
## SERVER PROGRAM:
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
    ip=input("Enter MAC Address : ")
    s.send(ip.encode())
    print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
## CLIENT OUTPUT:
![Screenshot 2024-03-13 094355](https://github.com/NaliniG007/2c.ARP_RARP_PROTOCOLS/assets/144589420/56cc1114-b2cb-4a50-9eef-6a3009d29f2b)
## SERVER OUTPUT:
![Screenshot 2024-03-13 094359](https://github.com/NaliniG007/2c.ARP_RARP_PROTOCOLS/assets/144589420/798ba77d-7734-40d6-81c2-6e86468cd637)
## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
