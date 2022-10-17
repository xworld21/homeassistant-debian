# Home Assistant debianized

Minimal Debian package to install Home Assistant core under `/var/lib/homeassistant`, plus fail2ban filters to block login attempts on the Home Assistant server.

To use, install the `homeassistant-core` package, then run
```
sudo update-homeassistant-core
sudo systemctl enable homeassistant-core
sudo systemctl start homeassistant-core
```

For fail2ban filters, install the `homeassistant-fail2ban` package and reload fail2ban.

To enable the fail2ban integration in Home Assistant, add the following line
```
/usr/bin/setfacl --modify user:homeassistant:r /var/log/fail2ban.log
```
to the postrotate script in `/etc/logrotate.d/fail2ban`.
