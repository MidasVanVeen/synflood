# SYN Flooder + IP spoofer

this is a tool that can perform a SYN flood attack on a target server using raw sockets and multithreading.

## What is a SYN flood attack?

A SYN flood attack is a form of denial-of-service (DoS) or distributed denial-of-service (DDoS) attack that exploits the TCP handshake process to overwhelm a server with open connections. The attacker sends massive numbers of SYN packets, which are part of the initial connection request, without responding to the corresponding acknowledgements. The server has to spend resources waiting for half-opened connections, which can consume enough resources to make the system unresponsive to legitimate traffic.

## Features

- Uses raw sockets to create and send custom TCP packets with spoofed IP addresses
- Uses multithreading to increase the speed and efficiency of the attack
- Requires root privileges and libpcap-dev library to run

## Installation

To install SYN Flooder, clone this repository and compile the source code using gcc:

```
git clone https://github.com/MidasVanVeen/synflood.git
cd synflood
gcc synflood.c -o synflood -lpthread
```

## Usage

To use this SYN flooder, run it as root and provide two arguments: the target IP address and the target port number. For example:

```
sudo ./synflood 192.168.0.1 80
```

This will launch a predefined number of threads (defined in the source code) that will each send SYN packets continuously to port 80 of 192.168.0.1 until the program receives a SIGINT signal (Ctrl+C).

## Disclaimer

This tool is for educational purposes only. Do not use it for illegal or malicious activities. I am not responsible for any consequences of using this tool.
