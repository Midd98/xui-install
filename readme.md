# XC install
Xtream Codes 2.93 - Install

## Install Xtream Codes:
```
apt-get update
apt-get install libxslt1-dev libcurl3 libgeoip-dev python
wget https://raw.githubusercontent.com/Midd98/xui-install/master/install.py
python install.py
```

## Install Xtream UI 22F:
```
apt-get install unzip e2fsprogs python-paramiko -y && chattr -i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && rm -rf /home/xtreamcodes/iptv_xtream_codes/admin && rm -rf /home/xtreamcodes/iptv_xtream_codes/pytools && wget "https://repo.programadorx.cl/xui/22f/master.zip" -O /tmp/master.zip -o /dev/null && unzip /tmp/master.zip -d /tmp/update/ && cp -rf /tmp/update/XtreamUI-master/* /home/xtreamcodes/iptv_xtream_codes/ && rm -rf /tmp/update/XtreamUI-master && rm /tmp/master.zip && rm -rf /tmp/update && chattr +i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/ && chmod +x /home/xtreamcodes/iptv_xtream_codes/permissions.sh && /home/xtreamcodes/iptv_xtream_codes/permissions.sh && /home/xtreamcodes/iptv_xtream_codes/start_services.sh
```

## Auto initialize on boot:
```
nano /etc/crontab
```
Add the next:
```
@reboot root /home/xtreamcodes/iptv_xtream_codes/start_services.sh
```

## EPG Database Fix:
epg_data overload and tilt panel fix
```
wget "https://raw.githubusercontent.com/Midd98/xui-install/master/fix/epg.php" -O /tmp/epg.php -o /dev/null;sudo rm -rf /home/xtreamcodes/iptv_xtream_codes/crons/epg.php; sudo cp /tmp/epg.php /home/xtreamcodes/iptv_xtream_codes/crons/; sudo chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/;sudo chmod 777 /home/xtreamcodes/iptv_xtream_codes/crons/epg.php; rm /tmp/epg.php;
```

## Monitor PID Fix:
```
wget "https://raw.githubusercontent.com/Midd98/xui-install/master/fix/pid_monitor.php" -O /tmp/pid_monitor.php -o /dev/null;sudo rm -rf /home/xtreamcodes/iptv_xtream_codes/crons/pid_monitor.php; sudo cp /tmp/pid_monitor.php /home/xtreamcodes/iptv_xtream_codes/crons/; sudo chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/;sudo chmod 777 /home/xtreamcodes/iptv_xtream_codes/crons/pid_monitor.php; rm /tmp/pid_monitor.php;
```

## Servers Checker Fix:
```
wget "https://raw.githubusercontent.com/Midd98/xui-install/master/fix/servers_checker.php" -O /tmp/servers_checker.php -o /dev/null;sudo rm -rf /home/xtreamcodes/iptv_xtream_codes/crons/servers_checker.php; sudo cp /tmp/servers_checker.php /home/xtreamcodes/iptv_xtream_codes/crons/; sudo chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/;sudo chmod 777 /home/xtreamcodes/iptv_xtream_codes/crons/servers_checker.php; rm /tmp/servers_checker.php;
```

## Error installing LoadBalancer

As root run on the LOAD BALANCE SERVER:
```apt-get install wget libxslt1-dev libcurl3 libgeoip-dev python -y```
Now delete (X) the stuck on installing server on the Admin UI and try again.

## Fix 500 Errors on XC v2

As root run:
```
apt-get install e2fsprogs -y && chattr -i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb ; wget https://archive.org/download/geolite2_201910/GeoLite2.mmdb -O /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && chown xtreamcodes.xtreamcodes  /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb  && chattr +i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && clear && echo "If you see this message, 500 errors are probably fixed"
```

## Get Network Interface Name

In the server run as root: 
```route -n | awk '$1 == "0.0.0.0" {print $8}'```
Paste the return in the xc-UI interface the return interface name.
