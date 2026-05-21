# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
```
Client.py :

import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())

Server.py :

import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Server is waiting for connection...")

c, addr = s.accept()
print("Connected to:", addr)

while True:
    msg = c.recv(1024).decode()
    print("Client >", msg)
    reply = input("Server > ")
    c.send(reply.encode())

```

## OUPUT

Client.py :

<img width="767" height="171" alt="Screenshot 2026-05-21 143603" src="https://github.com/user-attachments/assets/dc9f545d-7d46-4f61-b236-f2909c194db7" />

Server.py :

<img width="780" height="223" alt="Screenshot 2026-05-21 143555" src="https://github.com/user-attachments/assets/06c77240-3bc0-4acc-9d35-ea909524e81a" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
