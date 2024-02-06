# brother-scan

This tool is alternative to the brscan-skey with automatic document feeder
support and compressed PDF output.

## Using Docker

The easiest way to use brscand is to build a Docker image with the Dockerfile
provided here.

### Requirements

* Docker installed.
* The latest proprietary brscan4 deb from Brother
  * I had to go through their 'Downloads' page for my device (https://support.brother.com/g/b/productsearch.aspx?c=us&lang=en&content=dl)
  * The Dockerfile defaults to the deb name `brscan4-0.4.11-1.amd64.deb`

### Build image

Make sure you have downloaded the brscan4 deb file and placed it
in the top-level directory of the repository next to the Dockerfile.

Adapt `BRSCAN_DEB` if the version has changed.

```
python3 setup.py build sdist
docker build -t brscan --build-arg BRSCAN_DEB="brscan4-0.4.9-1.amd64.deb" .
```

### Configuration

Edit `brother-scan.yaml` according to your preferences.

### Run

To run brscand with the following setup:

* MFC-L2700DW scanner.
* Scanner at IP address 192.168.123.114.
* Host OS at IP address 192.168.123.101.
* Brscan version 4-0.4.11-1
* Output written to $HOME/brscan

```sh
chmod +x start_scanner
./start_scanner
```
```

## Uselinks

* https://www.mcbsys.com/blog/2014/11/register-pc-on-brother-scanner/
* https://github.com/jmesmon/brother2/blob/master/PROTO

## Tested devices
 * MFC-L2710DN
