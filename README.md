# 19CS406-EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## DATE : 23-03-2023

# AIM :
### To write a python program to perform sliding window protocol
# ALGORITHM :
### 1. Start the program.
### 2. Get the frame size from the user
### 3. To create the frame based on the user request.
### 4. To send frames to server from the client side.
### 5. If your frames reach the server it will send ACK signal to client otherwise it will send NACKsignal to client.
### 6. Stop the program
# CLIENT PROGRAM :
```py
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s

```
# SERVER PROGRAM :
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
REG NO:
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
# CLIENT OUTPUT :

![3c](https://github.com/ARSHADAHMEDM/EX-3/assets/128116503/93daa4ad-dcc1-4c03-8592-2d469c19cb2a)


# SERVER OUTPUT :
![3s](https://github.com/ARSHADAHMEDM/EX-3/assets/128116503/f6ba3146-d5fa-4e26-9cd9-63ff9e0de8e9)

# RESULT :
### Thus, python program to perform stop and wait protocol was successfully executed.