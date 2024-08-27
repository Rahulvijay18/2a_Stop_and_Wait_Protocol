# 2a_Stop_and_Wait_Protocol
### Name:Rahul Vijay.V
### Register NO:212223040164
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Client
```
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
    else:
        c.close()
        break
```
### Server
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT
### Server
![Screenshot 2024-08-27 091914](https://github.com/user-attachments/assets/2950c2ef-580a-439e-9cc6-642733667903)
### Client
![Screenshot 2024-08-27 091925](https://github.com/user-attachments/assets/cd2d70dd-f81c-4abf-874d-7bec72942e0a)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
