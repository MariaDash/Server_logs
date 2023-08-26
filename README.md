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
