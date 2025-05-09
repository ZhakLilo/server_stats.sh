# server_stats.sh

Quick Guide to Automate Server Monitoring. Want to keep tabs on your server's performance? Here's a simple setup using server_stat.sh, cron, and logrotate!

1. Script: `server_stat.sh` grabs CPU, memory, disk usage, and top processes. Save it in `/home/user/project/server_stat.sh`.

2. Cron: Run it every 8 hours. Add this to `crontab -e`: 
```
0 */8** * /home/user/project/server_stat.sh >> /home/ user/project/report/server_stats.log 2>&1
```
3. Log Rotation: 

Keep logs tidy with logrotate. Create `/etc/logrotate.d/server_stats`:
```
/home/user/project/report/server_stats.log{
daily 
rotate 7
compress 
copytruncate
}
```
Done! Your server stats are logged, rotated, and ready for review. Quick, efficient, and scalable!
