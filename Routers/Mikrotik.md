# MikroTik

Configuracio del router MikroTik

**Nota:** A les interficies s'els ha de sumar un numero

## .yml

```
mikrotik:
   kind: vr-ros
   image: vrnetlab/vr-routeros:7.12.1
```

## Acces al Router

**Usuari:** admin	**Contrasenya:** admin

```
ssh admin@{nom-docker}
```

## Canviar Nom

```
system identity set name={nom}
```

## Descripcio de una interficie

```
interface ethernet set {nom-interficie} comment="{descripcio}"
```

## Configurar IP interficie

```
ip address add address={ip}/{mask} interface={nom-interficie}
```

## Configuracio ruta estatica

```
ip route add dst-address={ip-xarxa-desti}/{mask} gateway={ip-gateway}
```
## Eliminar ruta estatica
```
ip route print
ip route remove number=x
```

## Veure taula de enrutament

```
ip route print
```
