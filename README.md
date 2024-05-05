## Features:

Automated Backup:
The daemon automatically copies files from the source directory to the backup directory according to the specified interval.

Configurability:
Users can configure the source directory, backup directory, and backup interval through a simple configuration file.

Signal Handling:
The daemon responds to various signals, allowing users to control its operation easily.

## Compilation:

Compile the daemon using your preferred C++ compiler:
```bash
g++ -o daemon main.cc SignalHandler.cc -lpthread -O3
```

## Configuration:

Edit the daemon.conf file to specify the source directory, backup directory, and backup interval according to your requirements.

## Service Setup:

Customize the backup_daemon.service file if necessary, ensuring the correct paths are set for the daemon executable and configuration file.

## Enable Service:

Copy the backup_daemon.service file to the appropriate systemd directory (e.g., /etc/systemd/system/) and enable the service:
```bash
sudo cp backup_daemon.service /etc/systemd/system/
sudo systemctl enable backup_daemon.service
```

## Usage:

Once the Backup Daemon is installed and configured, it will automatically start running as a background service. You can monitor its status, start, pause, or stop it using standard systemd commands:

Start Daemon:
```bash
sudo systemctl start backup_daemon.service
```
Pause Daemon:
```bash
sudo systemctl stop backup_daemon.service
```
Stop Daemon:
```bash
sudo systemctl stop backup_daemon.service
```
Check Status:
```bash
sudo systemctl status backup_daemon.service
```
