# Echoserver
Echo server and client using python socket
# AIM:

To develop an echo server and client using python socket

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 


## PROGRAM:
### Server:
```
import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()

    print("Server is waiting for connection...")

    conn, addr = s.accept()

    with conn:
        print(f"Connected by {addr}")

        while True:
            data = conn.recv(1024)

            if not data:
                break

            print("Received:", data.decode())

            conn.sendall(data)
```

### Client:
```
import socket

HOST = "127.0.0.1"  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Kishore M\n212224040161\n05.08.2026")
    data = s.recv(1024)

print("Received from server:\n" + data.decode('utf-8'))

```

## OUTPUT:
<img width="1908" height="1193" alt="image" src="https://github.com/user-attachments/assets/2cc24cf1-bbd3-44be-a814-82547ff461a7" />



## RESULT:
The program for echo client and echo server is executed successfully.
