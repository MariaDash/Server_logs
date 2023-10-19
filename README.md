# Server_logs
### Filtering logs by name
```
find server_logs -name  "*.log"
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
## 1. Pushing script (on python) from local machine to remote machine and testing server
1. Open folder with script in CLI on local machine
2. Push it with scp
```
scp p_l_s.py test_33_40@23.88.52.139:/home/test_33_40/p_l_s.py
```
Where:
+ `scp` is a secure copy command,
+ `p_l_s.py` - name of script,
+ `test_33_40` name of remote user,
+ `23.88.52.139` IP address of remote machine,
+ `/home/test_33_40/p_l_s.py`  -end directory and name of end file on remote machine we you will work with it
3. Enter password
4. Authorize into the remote server
5. In `second` terminal open your work directory with the script file
6. Run script:
```
python3 p_l_s.py
```
6. Testing script is running
7. Advanced - you can edit script to `print` some info that will show that the script is running correctly.
## 2. Pushing log file from remote machine to local machine:
Change directory to that in with you will save logs, then copy them
```
Admin@DESKTOP-V6V9F0T MINGW64 /
$scp test_33_40@23.88.52.139:/home/test_33_40/test_server/logs.log logs.log
```
## 3. We will browse the server with logs and we will nock at it with Postman
1. Creating virtual environment to run python scripts on remote machine
```
python3 -m venv venv
```
Check that venv exists by `ls -la` command on remote machine
2. From the local machine send `main.py` file:
```
scp main.py test_33_40@23.88.52.139:/home/test_33_40/test_server/main.py
```
Check that main.py exists by `ls -la` command on remote machine
3. Activate venv:
```
source venv/bin/activate
(venv)test_33_40@ubuntu
```
you will see `(venv)` in the command line.
4. Export flask
```
export   FLASK_APP=main.py
export FLASK_DEBUG=1
```
5. Run FLASK
```
flask run --host='0.0.0.0' --port='5003'
```
Server is running!!!
