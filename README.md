# 2a_Stop_and_Wait_Protocol

# Developed By : SANJAY M
# Register No  : 212223230187


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
# Client.py:
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

# server.py:
```
    import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
# Client :
![clien py 111](https://github.com/sanjayofficial2005/2a_Stop_and_Wait_Protocol/assets/148048602/3ae523a8-484b-46f8-aee0-4e6342857e7e)


# Server :
![server py 1111](https://github.com/sanjayofficial2005/2a_Stop_and_Wait_Protocol/assets/148048602/6809db03-b26c-494b-9147-310e0aa0c8cc)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
