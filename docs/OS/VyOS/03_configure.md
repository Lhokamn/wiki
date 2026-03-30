---
tags:
  - vyos
  
---
# Gestion du routeur

## Gestion des interfaces

### configurer une interface réseau (routeur 1, interface eth0): 

```bash
set interfaces ethernet eth<> address <address/masque>
set interfaces ethernet eth<> address <addressIPv6/masque>
set interfaces ethernet eth<> description '<description>'
commit
save
```

### Configurer une interface Vlan

```bash
set interfaces ethernet eth<> vif <num_vlan> address '<address/masque>'
set interfaces ethernet eth<> vif <num_vlan> address '<addressIPv6/masque>'
set interfaces ethernet eth<> vif <num_vlan> description '<description>'
commit
save
```

## Gestion du routage

### Routage static

```bash
set protocols static route <reseau> next-hop <address>
set protocols static route6 <reseau6> next-hop <address ipv6>
commit
save
```

### Routage dynamique (OSPF)

Gestion de la table de routage IPv4

```bash
set protocols ospf area <number> network <x.x.x.x/y> // Mettre tous les réseaux connecté directement au routeur dans la même area
set protocols ospf neighbor <x.x.x.1> // Mettre toutes les addresses voisins
commit
save
```

### Routage dynamique (OSPFv3)

Gestion de la table de routager l'IPv6

```bash
set protocols ospfv3 interface <interface> area <number>
commit
save
```

!!! note

    Si le réseau utilises de l'IPv6, il faut activer le "router-advert" pour qu'il puisse indiquer au machine client le préfixe de l'IPv6.  
    ```bash
    set service router-advert interface <interface> prefix <prefix/mask>
    ```