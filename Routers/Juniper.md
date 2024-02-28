# Juniper

Configuracio del router Juniper

**Nota:** A les interficies es diuen ge-0/0/x


## Acces al Router

**Usuari:** admin	**Contrasenya:** admin@123

```
ssh admin@{nom-docker}
```

Ara haurem d'afegir la llisencia

```
show system license installed
request system license add terminal
```

introduim la llisencia i despres presionem Enter i Ctrl+D

## Canviar Nom

```
configure
set system host-name {nom}
commit
```

## Descripcio de una interficie

```
configure
set interfaces {nom-interficie} description "{descripcio}"
commit
```

## Configurar IP interficie

```
configure
set interface {nom-interficie} unit 0 family init address {ip}/{mask}
commit
```

## Configuracio ruta estatica

```

```

## Veure taula de enrutament

```

```
