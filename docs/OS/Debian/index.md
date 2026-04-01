# Debian c'est quoi ?

Petit moment Wikipedia:

Debian est une distribution Linux créé le **16 août 1996** par [Ian Murdock](https://fr.wikipedia.org/wiki/Ian_Murdock). La distributoin est géré par l'association **Debian Project**.

Si les gens aiment autant Debian c'est pour deux grand aspect:
1. Tout ce que fait Debian est gratuit. Il n'y a pas de licence payante pour avoir le maximum que ce peu proposer la distribution (comme Ubuntu avec sa version pro)
2. Debian est d'une stabilité incroyable ce qui en fait un choix solide pour un serveur voir même un poste de travail. Cette stabilité vient que les développeurs testent longtemps une version d'un outil avant de l'intégré. Ce qui implique aussi que les paquets ne sont souvent pas les dernières versions mais sont plus simples

## Les packages

Debian utilisent son resolveur de paquet historique ``apt`` qui permet si on installe un package, d'aussi installé ces dépendances.

En dessous d'apt qui n'est qu'un résolveur on retrouve ``dpkg`` qui lui installes les packages.

En plus de cela ``apt`` s'utilise de deux façon:
- ``apt``: Pour quand il doit y avoir de l'intéractivité entre l'utilisateur et le shell
- ``apt-get``: Pour quand il ne doit pas y avoir d'intéractivité entre l'utilisateur et le shell. Utile dans des scripts Shell ou bien pour créer des images docker

### Mettre à jour le cache des paquet

```bash
sudo apt update
sudo apt-get update
```

### Upgrade les packages

```bash
sudo apt upgrade -y
sudo apt-get upgrade -y
```

### Chercher un paquet

```bash
apt search <package>
apt-get search <package>
```

### Installer un paquet 

```bash
sudo apt install -y <package>
sudo apt-get install -y <package>
```

### Désinstaller un paquet

```bash
sudo apt remove -y <package>
sudo apt-get remove -y <package>
```

## Est ce que Debian est fait pour moi ?

Debian peut être fait pour tout le monde, si vous rechercher surtout la stabilité sur votre système d'exploitation du quotidien (comme moi). 
Et si vous commencez sur Linux, vous aurez beaucoup de tuto qui vont vous dire de prendre la distribution Ubuntu qui est une base Debian. Même si je ne suis pas le plus grand de cette distribution car j'ai souvent eu des merdes. Alors que Debian 0 problèmes (a part celle de layer 8)

!!! note
    Pour ceux qui ne connaissent pas, la layer 8. C'est une expression en informatique réseau qui est sur le modèle OSI qui contient 7 couches. La layer 8 représente donc l'utilisateur qui fait une connerie (équivalent de problème interface chaise clavier)

Si vous rechercher un OS pour toujours être à la pointe des technos, dans ce que Debian n'est pas le meilleur dans ce cas. Une distribution comme Fedora ou Arch Linux sont plus adaptés. 
Aussi si votre pc n'est pas le plus puissant du monde (ou que vos parents vous demande de réparer leur pc devenu lent), Debian est parfait pour ce cas car il est très léger et tournent sur une très grande majorité de machine.


## Désavantages de Debian

Les désavantages de Debian sont souvent du justement à sa stabilité. Comme les packages ont un peu de retard et que certaines technos n'arrivent toujours pas, on peut avoir certaines performances moindres notamment en jeux vidéos qui se basent généralement sur les derniers paquets disponibles

Mais ce défaut certes principals peut être contourné en utilsant un autre système de package qui est **FlatPak**.

## Les distributions enfants

Comme tout le monde peut prendre une distribution et en créer en fork. Debian a engendré de nombreuses distributions filles comme:

!!! info inline end 
    Ceci est une liste non exhaustive de toutes les distributions que Debian a pu engendré

- Ubuntu : La plus connu
- Linux Mint : La plus tourné facilité d'utilisation de l'utilisateur en interface graphique
- Kali Linux : La plus tourné vers le hack ethique avec tous les outils préinstallé
- PopOS : Tournée jeux vidéos



Les distributions au dessus on un aspect vrai machine de travail, mais la communauté est très imaginiatives, on a donc eu:

- Hannah montana OS
- Justin Bieber OS
- UWUbuntu

!!! info
    Ces distributions ne sont **PAS** prévus pour être utilisés dans un contexte d'entreprise. Mais plus pour faire flipper un ami en boottant dessus sans installé le système !