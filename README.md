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
client.py:
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

print("Connected to server")

while True:
    msg = input("Client > ")
    s.send(msg.encode())

    ServerMessage = s.recv(1024).decode()
    print("Server >", ServerMessage)
```
server.py:
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

print("Server waiting for connection...")

c, addr = s.accept()

print("Connected with", addr)

while True:
    ClientMessage = c.recv(1024).decode()
    print("Client >", ClientMessage)

    msg = input("Server > ")
    c.send(msg.encode()
```

## OUPUT
<img width="1597" height="935" alt="Screenshot 2026-05-20 092615" src="https://github.com/user-attachments/assets/594acb92-d250-4eb5-96dc-e12e2dee044d" />
