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

SERVER.py

```

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recieved".encode())
```


CLIENT.py

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

## OUTPUT

SERVER.py

![image](https://github.com/user-attachments/assets/226b4209-e58f-44bd-923e-0c254d780df6)


CLIENT.py

![image](https://github.com/user-attachments/assets/714a4f16-b979-4df5-9547-21ee35f4c422)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
