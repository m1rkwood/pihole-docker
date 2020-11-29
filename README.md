# Pi-hole setup

This docker will setup pihole on your server.  
To use this configuration, you will have to also run the `traefik-docker` project available [here](https://github.com/m1rkwood/traefik-docker).  
You can also combine it with [Wireguard](https://github.com/m1rkwood/wireguard).

## Folder structure

```
.env
docker-compose.yml
```

## Envionment

Duplicate the `.env.template` file and rename it to `.env`  
Fill the information:

```
TZ=
VIRTUAL_HOST=
WEBPASSWORD=
DASHBOARD_USERNAME=
DASHBOARD_PASSWORD=
```

`TZ` is your timezone, i.e. `America/Los Angeles`.  
`VIRTUAL_HOST` is the complete url (with subdomain) where the pi-hole dashboard will appear.  
`WEBPASSWORD` is the admin password for the pi-hole dashboard.  
`DASHBOARD_USERNAME` & `DASHBOARD_PASSWORD` are used to generate a htaccess to the pi-hole dashboard.  
To generate the `DASHBOARD_PASSWORD`, use following commands

```
sudo apt-get install apache2-utils
htpasswd -nb <username> <secure_password>
```

## Start the container

```
docker-compose build && docker-compose up -d
```
