
# 2c.SIMULATING ARP /RARP PROTOCOLS
# DATE :
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
P
## PROGRAM - ARP
```
Developed by: SREE NIVEDITAA SARAVANAN
Reg no: 212223230213
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


## OUPUT - ARP

![{3BE5B0D6-C581-41CB-9E0C-52E7163AD75C}](https://github.com/user-attachments/assets/dab2561c-66dd-4c09-ac1e-7b6355efe472)


## PROGRAM - RARP
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
 ip=input("Enter logical Address : ") 
 s.send(ip.encode()) 
 print("MAC Address",s.recv(1024).decode()) 
```
## OUPUT -RARP

![{E5E74656-07F8-4941-9896-D62AF4A55F17}](https://github.com/user-attachments/assets/a683d94c-b74b-4a7d-89a6-d482c5dfd8a8)


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
