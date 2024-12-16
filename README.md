# airspy_tcp
## RTL-TCP compatible, IQ server for Airspy SDRs

`airspy_tcp` is a direct port of [rtl_tcp](https://github.com/osmocom/rtl-sdr) for the [Airspy SDRs](https://airspy.com/).

As the rtl_tcp protocol is only 8 bits IQ, man will loose the major advantage of an airspy : its 12-bit DAC, but :

1. It will work with any rtl_tcp capable frontend (Well I hope, see below),
2. As it's opensource, you could compile it on any Linux (and perhaps other UNIXes) server.

Notes :
 - I tried it with gqrx and sdrangelove frontend only. Other tests are welcome.
 - The rtl_tcp frontend client must use only the two supported sampling rates for the Airspy SDR. Others sampling rates are not supported.
 - It should work with Airspy Mini too, but it has not been tested.

## Building instructions
To build on Debian-based systems, run:
```bash
sudo apt update
sudo apt install pkg-config libairspy-dev
git clone https://github.com/TLeconte/airspy_tcp
cd airspy_tcp
pkg-config --cflags libairspy
make
```
To run your server, use `./airspy_tcp` with all the necessary arguments, the same way as for `./rtl_tcp`.
