# Nokia

Configuracio del router Nokia

**Nota:** 

## Acces al Router

**Usuari:** admin	**Contrasenya:** NokiaSrl1!

```
ssh admin@{nom-docker}
```

## Canviar Nom

```

```

## Descripcio de una interficie

```

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

## Veure taula de enrutament

```

```
