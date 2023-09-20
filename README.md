# HOMESERV
Home server with vpn

## Objectives

## How to 

### Install OMV6

Download the ISO from the official website :

https://www.openmediavault.org/download.html

Burn it on a usb stick, and install it on your machine.

Once it is done, you can log in with the username ```admin``` and password ```openmediavault```

### Install wireguard

Update your server and install wireguard :

```
sudo apt update && apt upgrade && apt install wireguard -y
```

Create a private key for the server :
```
wg genkey | sudo tee /etc/wireguard/private.key
```
Remove the users right on the keys (except root account)
```
sudo chmod go= /etc/wireguard/private.key
```
A copy of the output is also stored in the ```/etc/wireguard/private.key```

Create a public key for the server :
```
sudo cat /etc/wireguard/private.key | wg pubkey | sudo tee /etc/wireguard/public.key
```




### Sources

https://www.digitalocean.com/community/tutorials/how-to-set-up-wireguard-on-debian-11

