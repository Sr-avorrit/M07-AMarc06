# Configuracio PC2

## Conectarse

Conectarse al PC 2 mitjansant la seguent comanda.

```shell
sudo docker exec -it clab-06labMN-pc2 /bin/sh
```

## Configuracio IP

En primer lloc necesitarem saver el nom de la interficie hon realitzarem la configuracio.

```shell
ip address
```

Ara recordarem el nom de la interficie a la qual volem realitzarli la configuracio.

```shell
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
22: eth0@if23: <BROADCAST,MULTICAST,UP,LOWER_UP,M-DOWN> mtu 1500 qdisc noqueue state UP
    link/ether 02:42:ac:14:14:02 brd ff:ff:ff:ff:ff:ff
    inet 172.20.20.2/24 brd 172.20.20.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 2001:172:20:20::2/64 scope global flags 02
       valid_lft forever preferred_lft forever
    inet6 fe80::42:acff:fe14:1402/64 scope link
       valid_lft forever preferred_lft forever
26: eth1@if27: <BROADCAST,MULTICAST,UP,LOWER_UP,M-DOWN> mtu 9500 qdisc noqueue state UP
    link/ether aa:c1:ab:a9:e4:8c brd ff:ff:ff:ff:ff:ff
    inet6 fe80::a8c1:abff:fea9:e48c/64 scope link
       valid_lft forever preferred_lft forever
```

Com podem veure la interficie a la que voldrem asignarli una addressa sera la **eth1**. Ara li asignarem una adressa IP.

```shell
ip address add 192.168.X+20.1/24 dev eth1
```

## Configuracio Encaminament Estatic

A continuacio volem configurar l'encaminament estatic per tal de que el nostre equip pugui conectarse amb les altres xarxes.

Per a fero executarem la comanda seguent:

```shell
ip route add 192.168.X+10.0/30 via 192.168.X+20.254
ip route add 192.168.X.0/24 via 192.168.X+20.254
```
