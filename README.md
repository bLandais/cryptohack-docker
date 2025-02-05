# CryptoHack Docker Container

A Jupyter notebook environment built for attacking crypto CTF challenges, with custom theming matching [CryptoHack](https://cryptohack.org).

![screenshot](screenshot.png)

It comes with the following installed and integrated:
 - Sage 9 (based on Python3)
 - Pwntools
 - PyCryptodome
 - z3 Prover

## Installation

Clone the repository and create the image:
```
docker image build . -t cryptohack
```

Create a Docker volume:
```
docker volume create sage_data
```

Run the Cryptohack container:
```
docker run -p 8888:8888 -v sage_data:/home/sage -it cryptohack
```

Open 127.0.0.1:8888 (or exposed IP) in your browser.

## Notes

We map to 127.0.0.1 on the host rather than the default 0.0.0.0 as Jupyter token authentication was disabled for the sake of convenience.
