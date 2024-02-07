# brother-scan

This tool is alternative to the brscan-skey with automatic document feeder
support and compressed PDF output.

(This tutorial is meant for a Debian 11 (Bullseye) system)
Behavior on other versions might be different.

## Before setting up:
- Be root
```
apt-get -y upgrade; apt-get -y update;
apt-get -y screen;
```

## Install docker (if not installed already) (These commands are all copy-pastable)
```
apt-get -y upgrade; apt-get -y update;
apt-get install -y ca-certificates curl;
install -m 0755 -d /etc/apt/keyrings;
curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc;
chmod a+r /etc/apt/keyrings/docker.asc;

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null;
apt-get update;
apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin;



```

## Finally, run the instant setup script:
```sh
chmod +x start_scanner
./start_scanner
```

### Notice:
- Change the brscan version in the start_scanner file to the version available (if applicable)
- Change the IP addresses in the start_scanner file depending on your network configuration

## For issues:
- Create an issue on the repo
- contact me on telegram: @dockerchompz
