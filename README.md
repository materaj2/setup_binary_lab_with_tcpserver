# setup_binary_lab_with_tcpserver  
Setup binary lab with TCPServer for CTF  
1. Setup environment  
```
apt-get install ucspi-tcp
```  
2. Create shell script (test.sh)  
```
#!/bin/bash

read msg 
echo "Hello "$msg
```  
3. Create socket for receive input with tcpserver  
```
tcpserver -t 50 -RHl0 0.0.0.0 31337 ./test.sh
```  
4. Connect with netcat  
```
echo "testing" | nc localhost 31337
```  
