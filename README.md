# SetTimeAtBoot

If there is no time set at boot time of a Linux server, you should do this. Otherwise ntp cannor run of a too large gap. 


Thus create an entry at /etc/rc.local to set the local time at boot-time 


```
if test "`which wget`" != ""
then
        date --set="`wget -S http://www.google.de/ 2>&1  | grep "Date:" | sed s/Date://g`"
fi

# Maybe you should do a restart of the system time daemon afterwards

# systemctl restart ntp
# or
# systemctl restart systemd-timesyncd

```


