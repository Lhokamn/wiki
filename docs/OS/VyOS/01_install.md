---
tags:
  - vyos
  - installation

---

# Installation de machine

Pour configurer une machine VyOS c'est assez simple.

Il suffit de rentrer dans le terminal te de taper la commande suivante :

```sh
install image
```

Une fois toutes les questions répondus il faut la redémarrer.

# Utilisation

Pour utiliser une machine VyOS il a 2 grands concepts à comprendre, la gestion des modes, et la logique des commandes.

## Gestion des modes

Pour les modes il y en a 2 :

- Mode standard
  
Mode par défaut de la machine VyOS elle permet l'accès à toutes les commandes linux classiques
- Mode Configuration

Mode de configuration du routeur. On y rentre avec le commande clé :
```sh
configure
```

A partir de ce mode nous pouvons intéragir comme si nous étions sur un routeur physique (Cisco, Aruba, etc)

- La commande clé 
```sh
commit
```

Permet de loader en mémoire les changements qui viennent d'être fait 

- La commande clé
```sh
save
```

Permet de sauvegarder la configuration actuelle pour les prochains redémarrage

Pour tous le reste de la documentation (sauf contre indication), nous serons dans le mode configure

## Logique des commandes

Trois commandes sont primordial à connaitre :

- set : permet de changer la configuration 
- delete : permet de supprimer une ligne de configuration
- show : permet d'afficher la configuration

Par la suite, il suffit de suivre la logique de VyOS avec les différents mots clés (system, interfaces,services,...)