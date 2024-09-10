# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket.

### Step 2:

Implementation using Python code.

### Step 3:

Testing the server and client.

## PROGRAM:
### Server code:
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
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
### Client code:
```
import socket

HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)

print(f"Received {data!r}")
```
## OUTPUT:
### python3 echo-server.py
![server](https://github.com/user-attachments/assets/da080cea-9436-4ac4-89b7-00e8e9faa2c5)

### python3 echo-client.py
![client](https://github.com/user-attachments/assets/50fdcfdd-2531-4e97-ae72-8f07cbea4b98)

## RESULT:
The program is executed successfully
