# ONKYO RC-807M Remote file for LIRC

The following file should allow you to use the ONKYO RC-807M remote with LIRC.
Remote codes were recorded using the remote on the ONKYO default setting (Onkyo code 62503) and were set to fit perfectly to control the KODI mediacenter.

## Getting started with lircd on OSMC
When using OSMC you have to place the file in osmc's home-directory.

If you want to change the mapping you can do this by following this steps:

### Stop service
  `sudo killall lircd`

### List possible key names
  `sudo irrecord --list-namespace`

### Start recording
  `sudo irrecord --device=/dev/lirc0 /home/osmc/lircd.conf`

### Configure service to start up
  `sudo /usr/sbin/lircd --driver=default --device=/dev/lirc0 --uinput --output=/var/run/lirc/lircd-lirc0 --pidfile=/var/run/lirc/lircd.pid /home/osmc/lircd.conf`

### Test remote control
  `irw /var/run/lirc/lircd-lirc0`
