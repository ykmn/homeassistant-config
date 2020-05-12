# homeassistant-config
Home Assistant Configuration, home-assistant.io
==================

Homeassistant version: 0.109.6
Using Lovelace UI

[GitHub](https://github.com/ykmn/homeassistant-config)

Hass.io plugins configuration:
==================
Mosquitto broker:
------------------
```yaml
logins: []
anonymous: false
customize:
  active: false
  folder: mosquitto
certfile: fullchain.pem
keyfile: privkey.pem
require_certificate: false
```
Then add Integration.

Terminal & SSH:
------------------
```yaml
authorized_keys:
  - >-
    ssh-rsa [***] twelve@TECH-RE10
password: ''
```

Log Viewer:
------------------
```yaml
ssl: true
certfile: fullchain.pem
keyfile: privkey.pem
```

DuckDNS:
------------------
```yaml
lets_encrypt:
  accept_terms: true
  certfile: fullchain.pem
  keyfile: privkey.pem
token: [***]
domains:
  - [***].duckdns.org
seconds: 300
```

AdGuard Home:
------------------
```yaml
ssl: true
certfile: fullchain.pem
keyfile: privkey.pem
```
Then add Integration.

File Editor:
------------------
```yaml
dirsfirst: false
enforce_basepath: true
ignore_pattern:
  - __pycache__
  - .cloud
  - .storage
  - deps
ssh_keys: []
```

NGINX Home Assistant Proxy:
------------------
```yaml
domain: [***].duckdns.org
certfile: fullchain.pem
keyfile: privkey.pem
hsts: max-age=31536000; includeSubDomains
cloudflare: false
customize:
  active: false
  default: nginx_proxy_default*.conf
  servers: nginx_proxy/*.conf
```

Hass.io Integrations:
==================
AdGuard
AirVisual
Certificate Expiry
COVID-19
HACS (use [installation manual](https://hacs.xyz/docs/installation/prerequisites))
HomeAssistant iOS
Local IP Address
Meteorologisk institutt
MQTT
Network UPS Tools
iRobot Roomba
Shopping List
Synology DSM
Transmission
UPnP
