# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# DATE: 13/03/23

# AIM : 
To write a python program to perform stop and wait protocol

# ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program
```
# PROGRAM :
# CLIENT PROGRAM:
```
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
# SERVER PROGRAM:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
 ```
# OUTPUT :
# CLIENT OUTPUT :
![OUTPUT](./Screenshot%20(95).png)

# SERVER OUTPUT :
![Screenshot (45)](https://github.com/ArpanBardhan/EX-2/assets/119405037/613a248f-1c3b-4ece-b38f-0e944e3781b3)

# RESULT : 

Thus, python program to perform stop and wait protocol was successfully executed.




