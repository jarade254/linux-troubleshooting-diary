# Network Service Failure - 2026-02-08

## Problem
A web service was not reachable on the local Linux server:

`curl http://localhost` → `Failed to connect`

## Analysis
- Checked if the service was running: `systemctl status apache2` → inactive (dead)  
- Checked logs: `journalctl -u apache2` → found a configuration error

## Solution
1. Corrected the Apache config: `sudo nano /etc/apache2/sites-enabled/000-default.conf`  
2. Restarted the service: `sudo systemctl restart apache2`  
3. Verified service: `systemctl status apache2` and `curl http://localhost` → success

## Notes
- Always check service status and logs before assuming the cause  
- Keep backups of config files before editing

