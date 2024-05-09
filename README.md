# EX NO:2a_Stop_and_Wait_Protocol
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

# client:
```python
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
   print(ack)
   continue
 else:
   c.close()
   break
```
# Server
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())

```
## OUTPUT
# Client
![Screenshot 2024-03-06 215309](https://github.com/syedmokthiyar/2a_Stop_and_Wait_Protocol/assets/118787294/5fb342e5-39ea-4234-b80c-c89441553910)

# Server
![Screenshot 2024-03-06 215255](https://github.com/syedmokthiyar/2a_Stop_and_Wait_Protocol/assets/118787294/1e0f820b-7bd5-4629-bf15-b116bce15cb7)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
