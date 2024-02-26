# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:

### server.py

```
import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024).decode()
            if not data:
                break
            conn.sendall(data.encode())
     

     
```
### client.py

```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
       s.sendall(input().encode()) 
       data = s.recv(1024).decode()
       print(f"Received {data!r}")

```

## OUTPUT:

### Server
![image](https://github.com/Pranav-AJ/Echoserver/assets/118904526/53efecf2-07f1-4433-89cb-83fc1d3ca7df)

### Client
![image](https://github.com/Pranav-AJ/Echoserver/assets/118904526/bac84f86-7486-416e-97dd-7ae70e389624)

## RESULT:
The program is executed successfully
