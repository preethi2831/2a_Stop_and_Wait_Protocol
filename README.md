NAME : Preethika N  
REG NO : 212223040130

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

CLIENT :

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

SERVER :           

import socket            
s=socket.socket()                   
s.connect(('localhost',8000))             
while True:                         
    print(s.recv(1024).decode())                           
    s.send("Acknowledgement Recived".encode())              
    
## OUTPUT   
CLIENT  : 

![Screenshot 2024-09-09 221159](https://github.com/user-attachments/assets/88035784-78ca-4501-8d3a-e68dfdc51274)

SERVER :

![Screenshot 2024-09-09 221302](https://github.com/user-attachments/assets/94dd0644-6bf1-405b-bb98-4a6b03029494)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
