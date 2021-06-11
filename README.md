# mina-export-logs-crontab

## Ubuntu/Debian
1. SSH to server. Ensure you SSH with user that mina runs on
2. crontab -e
3. Insert line at the end of the file:  
         <0 1 * * * mina client export-logs>  
4. " 0 1 * * * " means at 01:00 AM every day
5. Save and exit


## Docker
1. SSH to server
2. If your user is not root: sudo crontab -eu root , else: crontab -e
3. Insert line at the end of the file:
         0 1 * * * docker exec -d mina mina client export-logs 
   
4. " 0 1 * * * " means at 01:00 AM every day, "docker exec" - run command in container, "-d" - detach mode, "mina" - container name (modify if container has another name), "mina client export-logs" - command to export logs
5. Save and exit
