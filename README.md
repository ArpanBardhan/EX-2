# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

DATE: 13/03/23

AIM : To write a python program to perform sliding window protocol


ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program
```
PROGRAM :
```
CLIENT:
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
```
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
REG NO:
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
 ```

OUTPUT :

CLIENT OUTPUT :
![Screenshot (48)](https://github.com/ArpanBardhan/EX-2/assets/119405037/41129eb9-3323-4b33-976f-374ba3b8ef56)

SERVER OUTPUT :
![Screenshot (49)](https://github.com/ArpanBardhan/EX-2/assets/119405037/50302d3b-4253-4a52-81d9-64f6deab0bcc)



RESULT : Thus, python program to perform stop and wait protocol was successfully executed.




