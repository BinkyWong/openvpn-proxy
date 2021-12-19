# Simple Docker OpenVPN Client 

# Quickstart

Add your netflix.ovpn file in the vpn folder

Start the proxy using:

```docker-compose up```

Set your browser netork proxy to you-docker-ip:8888 

e.g. if the IP of your docker instance is ```192.168.0.10```

Then the proxy address will be:

```192.168.0.10:8888```

Enjoy Netflix US :) 

# Instructions

You will need the following:

* A valid Netflix account :) 
* A valid .ovpn file that connects to a US server
* docker-compose - see https://docs.docker.com/compose/install/

There are 3 components to the docker compose file

## ovpn ##

This connects to the VPN server.

## tinyproxy-int ##

Connects to the ovpn container and provides an uplink to the tinyproxy-ext instance.

## tinyproxy-ext ##

Connects to the tinyproxy-int instance for the uplink and exposes port 8888 so that browsers can use it as a proxy server.

## Multiple Ovpn Files ##

Place all your ```.ovpn``` files in the ```vpn``` folder.

To open a specific .ovpn connection, edit the following line in the ```docker-compose.yml``` file:

```
entrypoint: "openvpn --config /srv/netflix.ovpn"
```

