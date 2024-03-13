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
## OUPUT - ARP
![312143571-ee812d0a-84f9-48a1-904c-7f83944ba705](https://github.com/GOWTHAM54577/2c.ARP_RARP_PROTOCOLS/assets/144589420/6ee7e170-46a5-4f1d-b525-3abe4e5e5432)

## PROGRAM - RARP
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
## OUPUT -RARP
![312143628-790d399e-bbec-4232-be5a-cb061910e19e](https://github.com/GOWTHAM54577/2c.ARP_RARP_PROTOCOLS/assets/144589420/cf168481-a201-4b6d-a948-d9e8409098df)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
