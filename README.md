# Run rust embdedded code on the Raspberry Pi 3B+.

I did some reasearch on the subject and tried to follow many tutorials without success. I finally found IMO the easiest way to build rust code for raspberry pi. I am sharing it here in case it helps someone else.

This tutorial was the one that helped me the most, but I wanted to do even more simplified version: https://hackernoon.com/building-a-wireless-thermostat-in-rust-for-raspberry-pi-part-2

## Prerequisites

- Raspberry Pi 3B+
- Rust installed
  - Cross installe (`cargo install cross`)
- Docker installed

Disclaimer: I used MacOS to build this. Might not work on Windows without modifications. Also this tutorial is pretty low effort so I might have missed something.

## Steps

1. Optionally install fresh OS on your pi using Raspberry Pi Imager. I used the Raspberry Pi OS Lite (32-bit) version. Remember to check the settings to enable ssh and wifi. This tutorial provides good instructions for the installation: https://www.freecodecamp.org/news/embedded-rust-programming-on-raspberry-pi-zero-w/

2. Try connecting to your pi using ssh. If you are using MacOS, you can use the following command:

```bash
ssh name@host.local
```

3. I created separate SSH key to skip password authentication. This is optional, but I recommend it. You can follow this tutorial to create a new key: https://www.raspberrypi.com/documentation/computers/remote-access.html#passwordless-ssh-access . I saved mine in the same location on my mac as the default one but with name `raspberrypi`.

4. Clone this repository to your local machine.

5. Edit the deploy script to match your settings.
   NOTE: You might also need to create folder `rust-raspberry-pi` to your pi before deployment script runs (`ssh name@host.local` and `mkdir rust-raspberry-pi`).

6. Run the deployment script. You might need to add permissions first.

```bash

chmod +x ./deploy && ./deploy

```
