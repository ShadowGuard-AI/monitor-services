## monitor-services

### Project Description

Monitor-services is a cybersecurity tool that monitors critical service status, with a focus on system monitoring and alerts.

### Installation Instructions

To install monitor-services, use the following steps:

1. Ensure you have the following dependencies installed:
   - psutil
   - argparse
   - logging
2. Clone the monitor-services repository:
   ```
   git clone https://github.com/ShadowStrikeHQ/monitor-services.git
   ```
3. Run the tool from the cloned directory (the repo ships no setup.py; the tool is the single script `main.py`):
   ```
   cd monitor-services
   python main.py --services <name> [<name> ...]
   ```

### Usage Examples

To use monitor-services, run the following command:

```
python main.py --services sshd cron
```

The following options are available:

- `--services`: List of services to monitor, separated by spaces. Required; one or more service names.
- `-h`, `--help`: Show this help message and exit.

The tool checks each named service once and logs whether it is running, warning if it is not and erroring if it is not found. Service lookup uses `psutil.win_service_iter()`, so the tool runs on Windows. Note that importing main.py creates a `monitor_services.log` file in the working directory.

### Security Warnings

Monitor-services does not perform any security checks on the monitored services. It is the responsibility of the user to ensure that the monitored services are secure.

### License

Monitor-services is licensed under the GNU General Public License v3.0 to CY83R-3X71NC710N.
