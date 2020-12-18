# File-Watcher-Discord
Get discord notifications of recently added to GDrive / TDrive 


**Requirements**:

- Python >= 3.7.4

**Install Ubuntu:**

- apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget libsqlite3-dev
- wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz
- tar xzf Python-3.7.4.tgz
- cd Python-3.7.4
- ./configure
- make
- make altinstall
- tar xzf file-watcher.tar.gz
- cd file-watcher
- python3.7 -m venv venv
- venv/bin/pip install -r requirements.txt

**First Start**
- copy google json file to script directory and rename it to "credentials.json"
- venv/bin/python3 main.py
- Go to urls which will be printed and make auth with google
- paste into script key which you receive from google and click enter
- Ctrl+C for exit from script
- copy "file-watcher.service" to /etc/systemd/system/
- edit "ExecStart" for format: "{FULL_PATH_TO_PYTHON_VENV}/bin/python3 -u /{FULL_PATH_TO_REMOTE_TRIGGER}/main.py"
- systemctl daemon-reload
- systemctl start file-watcher.service
