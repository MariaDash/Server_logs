# Server_logs
### Filtering logs by name
```
fing server_logs -name  "*.log"
```
### Filtering and show logs in real time
```
tail -f app.log | grep  ERROR
```
### Filtering logs from buffer in real time and saving them in real time in the file
```
tail -f app.log | grep --line-buffered ERROR >> error_log.log
```
### While logs in real time are recording in the file you cannot see them in CLI, so you can open another CLI and type this command to see them:
```
tail -f app.log | grep error_log.log
```
## Pushing server from local machine to remote machine
1. Open folder with server in CLI
2. Push it
```
scp p_l_s.py test_33_40@23.88.52.139:/home/test_33_40/p_l_s.py
enter password
```
Where:
+ `scp` is a moving command,
+ `p_l_s.py` - name of server,
+ `test_33_40` name of remote user,
+ `23.88.52.139` IP address of remote machine,
+ `/home/test_33_40/p_l_s.py`  -end directory and name of end file on remote machine
