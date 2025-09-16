# SSH Locked Out Issue

**Date:** Sept 16, 2025  
**VM:** Ubuntu 22.04  

**Problem:**  
I edited `/etc/ssh/sshd_config` incorrectly (typo in `PermitRootLogin no`).  
After restarting `sshd`, I could not log in via SSH.

**Troubleshooting Steps:**  
1. Switched to VM console (VirtualBox direct access).  
2. Checked logs:  
   ```bash
   journalctl -u sshd -xe
