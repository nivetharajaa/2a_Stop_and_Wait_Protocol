# 2a_Stop_and_Wait_Protocol
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
### CLIENT
'''
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
'''
### SERVER
'''
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
 '''
## OUTPUT

### CLIENT

![image](https://github.com/nivetharajaa/2a_Stop_and_Wait_Protocol/assets/120543388/2f118db1-bd29-4932-b017-652c4f1f7f91)

### SERVER
![image](https://github.com/nivetharajaa/2a_Stop_and_Wait_Protocol/assets/120543388/d4d30083-9c39-4b51-829b-beb1804a305d)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
