Tricky SSH for shell_command at Hass.IO
------------------
1. Before Hass.IO installation you need to prepare SSH access to the host. Assume you plan to connect to hassio.local from TARGET_MACHINE:
* run `ssh-keygen` on TARGET_MACHINE
* get `id_rsa.pub`, save it to the root of your SD card and rename it to `authorized_keys` - this is your public key. Once the device is booted, you can access your device from TARGET_MACHINE as root over SSH on port 22222 with `ssh root@hassio.local -p 22222`
2. Once you have “root@hassio:~#” prompt type: `docker exec -i -t homeassistant /bin/bash`
Now we're creating keys for reverse connection - from hassio.local to TARGET_MACHINE:
3. Run `ssh-keygen` and save keys to `/config/ssh`
4. Run `ssh-copy-id -i /config/ssh/id_rsa.pub hass@TARGET_MACHINE`
5. Create config file `/config/ssh/config`:
`ConnectTimeout 10
IdentityFile /config/ssh/id_rsa
UserKnownHostsFile /config/ssh/.known_hosts`
6. Test: `ssh -F /config/ssh/config hass@TARGET_MACHINE`

Now you need to force using /config/ssh/config file when creating SSH shell_command on Hass.IO. That's because commands in Hass.IO are igniting from OS level but HomeAssistant runs at Docker level.

**Example:**
`sleep_macbook: "ssh -F /config/ssh/config user@192.168.1.10 pmset sleepnow"`
where 192.168.1.10 is your TARGET_MACHINE
