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