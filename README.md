# rpi

Raspberry Pi applications

security_camera
---------------
* setup - create /home/pi/cam_server_settings.json. Include keys
 * CLIENT_KEY: camera server client id
 * CLIENT_SECRET: camera server client secret
 * UPLOAD_ENDPOINT_URL: camera server image upload endpoint.
* start
```
rpi/security/security_camera.py &
```
* stop
```
kill -INT $(cat /home/pi/security_camera.pid)
```
* installing security_camera as a systemd service
```
cp systemd/security_camera.service /lib/systemd/system
chmod 644 /lib/systemd/system/security_camera.service
sudo systemctl daemon-reload
sudo systemctl enable security_camera.service
```
* view logs
 * Log levels can be changed by editing security_camera.py. default is logger.setLevel(logging.INFO)
```
tail -f /var/log/syslog
```

