# Echoserver
Echo server and client using python socket
# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```
#SERVER.PY
import socket
HOST = "127.0.0.1"  
PORT = 65432 
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

#CLIENT.PY
import socket
HOST = "127.0.0.1" 
PORT = 65432  
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"V KAMALESH VIJAYAKUMAR, 212224110028 [22/04/2026]")
    data = s.recv(1024)
print(f"Received {data!r}")
```


##  Architecture Diagram

```bash
+--------------------------+
|  User's Web Browser      |
|  (Client: Chrome/Firefox)|
+-----------+--------------+
            |
            |  HTTP Request (GET /)
            v
+-----------+--------------+
|   Python Web Server      |
| (http.server + Handler)  |
| - Listens on Port 8000   |
| - Handles GET Requests   |
| - Sends HTML Response    |
+-----------+--------------+
            |
            |  HTML Response
            v
+--------------------------+
|  User Sees Rendered Page |
|  <h1>Hello Web Server</h1>|
+--------------------------+
```


## OUTPUT:
### CLIENT OUTPUT:
<img width="1278" height="720" alt="image" src="https://github.com/user-attachments/assets/9c7b499d-1127-48eb-b87c-d68f61b28a8e" />


### SERVER OUTPUT:
<img width="1123" height="756" alt="image" src="https://github.com/user-attachments/assets/a01b9739-4fda-44a8-89de-4c3664e4a9b1" />


## RESULT:
The program is executed succesfully
