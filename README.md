# EX-4  IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL (ARP)
# DATE : 30.03.2023
# AIM :
To write a python program for simulating ARP protocols using TCP
# ALGORITHM :
# CLIENT:
### STEP 1: Start the program
### STEP 2: Using socket connection is established between client and server.
### STEP 3: Get the IP address to be converted into MAC address.
### STEP 4: Send this IP address to server.
### STEP 5: Server returns the MAC address to client.
# SERVER:
```
1.Start the program.
2.Accept the socket which is created by the client.
3.Server maintains the table in which IP and corresponding MAC addresses are stored.
4.Read the IP address which is send by the client.
5.Map the IP address with its MAC address and return the MAC address to client.
```
# CLIENT PROGRAM :
## Developed : Kalpana S
## Reg no : 212222040069
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
# SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
    
# OUTPUT :
# CLIENT OUTPUT :
![ex04 client output](https://github.com/Kalpanareshma/EX-4/assets/122040453/0afd0dd9-35bd-4b75-ba63-91374d84aaf3)
# SERVER OUTPUT :
![ex04 server output](https://github.com/Kalpanareshma/EX-4/assets/122040453/6039266d-02dd-4534-b8ab-b065244ca041)

# RESULT :
Thus, the python program for simulating ARP protocols using TCP was successfully executed.


