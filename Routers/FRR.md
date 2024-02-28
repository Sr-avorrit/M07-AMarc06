# FRR

Configuracio del router FRR

## .yml

```
frr:
   kind: linux
   image: frrouting/frr:v8.4.1
   binds:
     - frr/daemons:/etc/frr/daemons
   exec:
     - sysctl -w net.ipv4.ip_forward=1
```

## Acces al Router

```
 sudo docker exec -it {nom-docker} /bin/sh
```

Un cop estem en el router hem d'iniciar els daemons manualment

```
cd /usr/lib/frr
./watchfrr zebra eigrpd &
vtysh
```

## Canviar Nom

```
configure terminal
hostname {nom}
```

## Descripcio de una interficie

```
configure terminal
interface {nom-interficie}
description "{descripcio}"

```

## Configurar IP interficie

```
configure terminal
interface {nom-interficie}
ip address {ip}/{mask}
```

## Configuracio ruta estatica

```
configure terminal
ip route {ip-xarxa-desti}/{mask} {ip-gateway}
```

## Veure taula de enrutament

```
show ip route
```
