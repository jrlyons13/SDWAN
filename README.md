# SDWAN
Troubleshooting SDWAN routers

# Cisco Router SSH & Ping Utility

A collection of Python scripts for accessing Cisco routers via SSH, extracting interface information, and launching ping tests for monitoring.

## Overview

This toolkit contains two main components:

1. **Cisco Router SSH Script**: Connects to Cisco routers via SSH, executes commands, and saves the output with timestamps and security features
2. **Ping Launcher**: Parses router output files, extracts IP addresses from interfaces in "up" state, and launches continuous ping windows

These utilities help network administrators quickly connect to Cisco devices, retrieve status information, and monitor connectivity to critical interfaces.

## Features

### Cisco Router SSH Script

- Securely connects to Cisco routers using Paramiko SSH library
- Executes enable mode and runs common show commands
- Automatically timestamps output files for historical records
- Sanitizes passwords and sensitive information in logs
- Provides clear status reporting for troubleshooting

### Ping Launcher (Cross-Platform)

- Available for both Windows and Ubuntu Linux systems
- Extracts active interface IPs from router output
- Launches separate ping windows for interface monitoring
- Supports interactive selection of interfaces to ping
- Filters out unassigned or invalid IPs automatically

## Requirements

- Python 3.6 or higher
- Paramiko library (`pip install paramiko`)
- Access to Cisco routers with SSH enabled
- Windows 11 or Ubuntu 24.04 (depending on which ping launcher you use)

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/cisco-router-utilities.git
   cd cisco-router-utilities
   ```

2. Install required dependencies:
   ```
   pip install paramiko
   ```

3. Make scripts executable (Linux only):
   ```
   chmod +x improved_cisco_script.py
   chmod +x cisco_ping_launcher.py
   ```

## Usage

### SSH Connection Script

```python
python improved_cisco_script.py
```

You will be prompted to enter:
- Router IP address
- SSH username
- SSH password (hidden input)
- Enable password (hidden input)

The script will connect, execute commands, and save the output to a file named after the IP address with a timestamp.

### Ping Launcher (Ubuntu)

```python
python cisco_ping_launcher.py
```

Or use command-line options:
```
python cisco_ping_launcher.py -l  # Use latest output file
python cisco_ping_launcher.py -f FILENAME  # Specify file
python cisco_ping_launcher.py -a  # Process all files
```

### Ping Launcher (Windows)

```python
python cisco_ping_launcher_windows.py
```

Command-line options are the same as the Ubuntu version.

## Security Features

- Passwords are not displayed during input
- Enable passwords are sanitized in output files
- SSH session properly closed after use
- No hardcoded credentials

## Sample Workflow

1. Connect to your router using the SSH script
2. Review the output saved to the timestamped file
3. Use the ping launcher to monitor active interfaces
4. Track historical changes across multiple router checks

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgments

- Paramiko Project for the SSH library
- The Cisco networking community
