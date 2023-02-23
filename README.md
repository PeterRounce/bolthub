# Bolt Card Hub docker container

### install Docker

- [Docker engine download &
   install](https://docs.docker.com/engine/install/)
   
### pre setup
```
$ git clone https://github.com/onesandzeros-nz/bolthub.git
$ cd bolthub
$ git clone https://github.com/onesandzeros-nz/BoltCardHub.git
$ git clone https://github.com/boltcard/boltcard.git
```
- Make a .env file (copy the .env.example file and change the variable values)
- Edit `Caddyfile` to set the domain name
- Edit database details in `boltcard/sql/create__db_user.sql`
- Edit settings in `boltcard/sql/settings.sql` [Bolt card system settings](https://github.com/boltcard/boltcard/blob/main/docs/SETTINGS.md)
- Add `admin.macaroon` and `tls.cert` files in the root project directory

### service bring-up and running
```
$ sudo groupadd docker
$ sudo usermod -aG docker ${USER}
(log out & in again)
$ docker volume create caddy_data
$ docker volume create boltcard_hub_lnd
// add -d option for detached mode
$ docker compose up
```
- Go to `https://your.domain.com:8080` to access your bolt card hub gui 
