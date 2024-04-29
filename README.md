# 2a_Stop_and_Wait_Protocol
## Name : H Vishinu
## Reg No : 212223220124
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
Client 
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else :
        c.close()
        break
```
Server 
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())

```
## OUTPUT
Client :
![Screenshot 2024-04-22 144510](https://github.com/VisHinu24/2a_Stop_and_Wait_Protocol/assets/144244396/4227c1e8-4b65-4859-b5a0-42cd73645d71)

Server :
![Screenshot 2024-04-22 144518](https://github.com/VisHinu24/2a_Stop_and_Wait_Protocol/assets/144244396/0bec2334-0a9a-4789-9d2c-934bef86db1d)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
