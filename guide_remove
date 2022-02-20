#!/bin/bash
echo 'Description="Process Remove CoinMinerPwnRig",Author="FIS.CSD",Website="https://www.fpt-is.com/security/'
echo 'Process Remove CoinMinerPwnRig Running'
# Change attribute of file, allowing read/write/delete
chattr -aui /etc/cron.d/root /etc/cron.d/apache /var/spool/cron/root /var/spool/cron/crontabs/root /etc/cron.d/root.bk /etc/cron.hourly/oanacroner1 /etc/init.d/down /root/.bash_profile /tmp/dbused /etc/cron.d/pwnrig /etc/cron.hourly/pwnrig /etc/rc.d/init.d/pwnrig /etc/cron.daily/pwnrig /etc/cron.monthly/pwnrig /etc/cron.weekly/pwnrig /etc/cron.d/nginx /etc/rc*.d/init.d/*pwnrig* /etc/rc*.d/*pwnrig* /etc/systemd/system/pwnrig* /usr/lib/systemd/system/pwnrig*
# Remove dbused from .bash_profile
cp /root/.bash_profile /root/.bash_profile.bak
sed '/dbused/d' /root/.bash_profile.bak > /root/.bash_profile
# Remove malicious files
rm -rf /tmp/bashirc /tmp/.python /tmp/.lock /bin/dbused  /root/.bash_profile.bak /etc/cron.d/root /etc/cron.d/root.bk /etc/cron.d/bashgo /etc/cron.d/apache /var/spool/cron/root /var/spool/cron/crontabs/root /etc/cron.hourly/oanacroner1 /etc/init.d/down /tmp/dbused /etc/cron.d/pwnrig /etc/cron.hourly/pwnrig /etc/rc.d/init.d/pwnrig /etc/rc*.d/init.d/*pwnrig* /etc/rc*.d/*pwnrig* /etc/cron.daily/pwnrig /etc/cron.monthly/pwnrig /etc/cron.weekly/pwnrig /etc/cron.d/nginx /dev/shm/cruner /tmp/cruner /var/tmp/cruner /home/$(whoami)/cruner /run/user/$(echo $UID)/cruner /run/user/$(echo $UID)/systemd/cruner
# Remove new malicious files
find / -name "bashgo*" -type f | xargs rm
find / -name "httpgo*" -type f | xargs rm
rm -rf /etc/rc.d /rc.local /etc/rc.local 
rm -rf /etc/ld.so.preload
if [ -f /etc/redhat-release ]; then
    cat > /etc/crontab << EOFDEFAULTCRON
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=root

# For details see man 4 crontabs

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name  command to be executed
EOFDEFAULTCRON
fi
# Kill malicious process
ps aux  |  grep -i 'bashirc'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'dbused'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'xms'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'bash -sh'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'wget'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'cruner'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'iss.sh'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'rss.sh'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'sendmail'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i '209.141.40.190'  |  awk '{print $2}' | xargs kill -9
ps aux  |  grep -i 'givemexyz'  |  awk '{print $2}' | xargs kill -9
# Stop, disable and remove malicious processes
service pwnrig* stop
service pwnrig* disable
service bashgo* stop
service bashgo* disable
service httpgo* stop
service httpgo* disable
systemctl stop pwnrig*
systemctl disable pwnrig*
systemctl stop bashgo*
systemctl disable bashgo*
systemctl stop httpgo*
systemctl disable httpgo*
rm -f /etc/systemd/system/pwnrig*
rm -f /usr/lib/systemd/system/pwnrig*
rm -f /etc/systemd/system/multi-user.target.wants/pwnrig*
rm -f /etc/systemd/system/bashgo*
rm -f /usr/lib/systemd/system/bashgo*
rm -f /etc/systemd/system/multi-user.target.wants/bashgo*
rm -f /etc/systemd/system/httpgo*
rm -f /usr/lib/systemd/system/httpgo*
rm -f /etc/systemd/system/multi-user.target.wants/httpgo*
systemctl daemon-reload
systemctl reset-failed
# Re-enable SELinux
setenforce 1
echo 'Process Remove CoinMinerPwnRig Complete'
