# FRR

Configuracio del router FRR

**Nota:** A les interficies s'els ha de sumar un numero

## Acces al Router

```
 sudo docker exec -it clab-pc1MF-ffr /bin/sh
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
