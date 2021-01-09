# homeassistant-config
Home Assistant Configuration, home-assistant.io
==================

Homeassistant version: 0.84.6
Using Lovelace UI

[GitHub](https://github.com/ykmn/homeassistant-config)

Hass.io plugins configuration:
==================
Mosquitto broker:
------------------
{
  "logins": [
    {
      "username": "mqtt-user",
      "password": "mqtt-password"
    }
  ],
  "anonymous": false,
  "quiet_logs": true,
  "customize": {
    "active": false,
    "folder": "mosquitto"
  },
  "certfile": "fullchain.pem",
  "keyfile": "privkey.pem"
}

SSH server:
------------------
{
  "authorized_keys": [
    "ssh-rsa ******* twelve@TECH-RE10"
  ],
  "password": ""
}

Log Viewer:
------------------
{
  "ssl": true,
  "certfile": "fullchain.pem",
  "keyfile": "privkey.pem"
}

