# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
### client.py
```python
import socket

s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))

s.send("Hello server!".encode())
with open('received_file', 'wb') as f:
    while True:
        print('Receiving data...')
        data = s.recv(1024)
        if not data:
            break
        print(f"Received chunk of size {len(data)} bytes")
        f.write(data)

print('File received successfully.')

s.close()
print('Connection closed.')

```
### server.py
```python
import socket

s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))

s.send("Hello server!".encode())
with open('received_file', 'wb') as f:
    while True:
        print('Receiving data...')
        data = s.recv(1024)
        if not data:
            break
        print(f"Received chunk of size {len(data)} bytes")
        f.write(data)

print('File received successfully.')

s.close()
print('Connection closed.')

```
## OUTPUT
### clinet.py
![Screenshot 2025-05-17 113202](https://github.com/user-attachments/assets/8452e5fd-b55d-430c-8679-4a61e1bd0e54)

### server.py
![Screenshot 2025-05-17 113016](https://github.com/user-attachments/assets/54d6a8e4-c610-46a0-ab85-5098529e795b)


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
