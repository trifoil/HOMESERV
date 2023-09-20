# HOMESERV
Home server with vpn

## Objectives

## How to 

### Install docker 
Install curl :

```
sudo apt install curl -y
```

Install docker with curl :
```
curl -sSL https://get.docker.com | bash
```
Make your user able to run without using sudo everytime (optional) :
```
sudo usermod -aG docker $(whoami)
```

## Sources
https://medium.com/@gurayy/set-up-a-wireguard-vpn-server-with-docker-in-5-minutes-4e603fe37e32
