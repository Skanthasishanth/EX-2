# IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# EXP : 2

# DATE : 15-03-2023

# AIM :
To write a python program to perform stop and wait protocol


# ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
6. Stop the program

# CLIENT PROGRAM :
```PYTHON 3 

import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

```
# SERVER PROGRAM :
```PYTHON 3
import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())

```


# CLIENT OUTPUT :



![client](https://github.com/Skanthasishanth/EX-2/assets/118298456/8f5e1393-d7f4-4625-ba23-755e3ef76015)
# SERVER OUTPUT :
![server](https://github.com/Skanthasishanth/EX-2/assets/118298456/d610906f-8278-419a-9e8f-01e4da95ce05)

# RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.
