---
tags:
  - vyos
  - template

---

Pour gagner du temps, il est très utiles de créer une machine template qui pourra être cloner rapidement.

Voici les choses qui me parraissent important à mettre :

# Mettre le clavier en français

```bash
set system option keyboard-layout fr
commit
save
```

# Configuration de la première interface à 0:

```bash
sudo vi /opt/vyatta/etc/config/config.boot
```
Après il faut retirer la ligne hw-id de eth0 pour couper le lien entre l'interface et la MAC adresse. Une fois la ligne retiré. On éteind la machine et on crée une snapshot. Une fois que cette manipulation est faites **IL NE FAUT PAS REDEMARRER LA VM** sinon un nouveau lien se fera et il faudra tout recommencer. A partir de maintenant il faudra cloner les VM à partir de la template.

# Configuration d'un Hostname

Une fois que les VM sont clonées, il faudra changer leur domaine pour qu'elle soit reconnaissable sur le réseau :
```bash
set system host-name <hostname>
set system domain-name <domain> // Pas obligatoire à mettre
commit
save
```