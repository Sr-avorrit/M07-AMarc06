# Nokia

Configuracio del router Nokia

## .yml

```
nokia:
   kind: nokia_srlinux
   image: ghcr.io/nokia/srlinux:latest
```

## Acces al Router

**Usuari:** admin	**Contrasenya:** NokiaSrl1!

```
ssh admin@{nom-docker}
```

## Canviar Nom

```
enter candidate
system name host-name {nom}
commit now
```

## Descripcio de una interficie

```
enter candidate
set / network-instance default description "{descripcio}"
commit now
```

## Configurar IP interficie

```
enter candidate
set / interface {nom-interficie}
set / interface {nom-interficie} admin-state enable
set / interface {nom-interficie} subinterface 0 admin-state enable
set / interface {nom-interficie} subinterface 0 ipv4 admin-state enable
set / interface {nom-interficie} subinterface 0 ipv4 address {ip}/{mask}
set / network-instance default interface {nom-interficie}.0
commit now
```

## Configuracio ruta estatica

```
enter candidate
set /network-instance default next-hop-groups group {nom-grup} nexthop 1000 ip-address {ip-gateway}
set /network-instance default static-routes route {ip-xarxa-desti}/{mask} next-hop-group {nom-grup}
commit now
```

## Eliminar ruta estatica
```
enter candidate
delete /network-instance default static-routes route {ip-xarxa-desti}/{mask}
commit now
```

## Veure taula de enrutament

```
show network-instance route-table ipv4-unicast summary
```
