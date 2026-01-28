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
**server**
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
**client**

```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Ramya G 28.01.2026")
    data = s.recv(1024)


print(f"Received {data!r}")

```


## OUTPUT:

**server**
<img width="707" height="768" alt="Screenshot 2026-01-28 092228" src="https://github.com/user-attachments/assets/862f2c19-921d-422b-8479-b62f58ff1dc9" />



**client**
<img width="752" height="717" alt="Screenshot 2026-01-28 092245" src="https://github.com/user-attachments/assets/acb3fd65-16b3-49d7-8f8f-52cf726a5687" />



## RESULT:
The program is executed successfully
