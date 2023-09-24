# HOMESERV
Home server with vpn

## Objectives

Homeserver with VPN install for a small amount of users, small NAS server.

* OpenMediaVault
* Wireguard
* Home Assistant

## Install OMV6

Download the ISO from the official website :

https://www.openmediavault.org/download.html

Burn it on a usb stick (or boot it from the network), and install it on your machine.

Once it is done, you can log in with the username ```admin``` and password ```openmediavault``` :




### Install wireguard and create a key pair

Update your server and install wireguard :

```
sudo apt update && apt upgrade && apt install wireguard -y
```

Create a private key for the server :
```
wg genkey | sudo tee /etc/wireguard/private.key
```
Remove the users right on the keys (except root account) :
```
sudo chmod go= /etc/wireguard/private.key
```
A copy of the output is also stored in the ```/etc/wireguard/private.key```.

Create a public key for the server :
```
sudo cat /etc/wireguard/private.key | wg pubkey | sudo tee /etc/wireguard/public.key
```
the ```|``` (pipe) operator chains the three commands that 
* reads the private key file and outputs it to the standard output stream
* takes the output from the first command as its standard input and processes it to generate a public key
* takes the output of the public key generation command and redirects it into the file named /etc/wireguard/public.key

Copy the output where you can find it, because it is the pubkey to connect to the server.

### IPV4 and IPV6 setup



### Wireguard Server Configuration File creation


### Wireguard's Server's Configuration


### Wireguard's Server's Firewall Configuration


### Wireguard peer configuration


### Adding Peer' Pubkey to the WireGuard Server


### Wireguard Peer Connection to the Tunnel




### Sources

https://www.digitalocean.com/community/tutorials/how-to-set-up-wireguard-on-debian-11

