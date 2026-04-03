---
tags:
  - RHEL
  - Red Hat

---

# RHEL c'est quoi ?

Comme souvent, on va faire un petit moment wikipedia.

!!! inline end note
    RHEL = Red Hat Enterprise Linux. Mais comme le nom est chiant, on va rester sur RHEL ou Red Hat

RHEL est une distribution Linux crée en **1994** par [Marc Ewing](https://fr.wikipedia.org/wiki/Marc_Ewing), qui va fusionner l'année d'après avec l'entreprise AAC Corporation pour donné Red Hat Software.

On peut se poser la question de pourquoi cette distribution qui est détenue par une aussi grande entreprise est très utilisé:

!!! inline end ""
    ![](../../assets/images/rhel/logo_rhel.svg)

1. Le premier argument est que la distribution est maintenu avec les mises à jour de sécurité sur **10 ans** pour une version donnée. Ce qui en tant qu'admin système est un plaisir. On installe un système et pendant 10 ans c'est mis à jour et donc on a pas besoin de faire des réinstallation de système (et donc pété la prod)
2. Avec la licence, les entreprises ont accès à un support en cas de problème

## Les packages

Depuis les versions plus récentes de RHEL, le resolveur de paquet est ``dnf``. Sur les versions plus aniennes, on retrouveras ``yum``. Dans tous les cas, on retrouveras en dessous l'installateurs de paquets ``rpm``.


### Upgrade les packages

```bash
# dnf va automatiquement mettre à jour son cache pour les paquets
sudo dnf update -y
```

### Chercher un paquet

```bash
dnf search <package>
```

### Installer un paquet 

```bash
sudo dnf install -y <package>
```

### Désinstaller un paquet

```bash
sudo dnf remove -y <package>
```

## Est ce que Red Hat est fait pour moi ?

RHEL n'est pas pensé pour tout le monde. Il est principalement pensé pour le coté serveur que poste client. Sans compte que pour du personnel, la license obligatoire est assez cher.

!!! warning
    Cette section est vraiment importante. Ce que Red Hat nous fait payé c'est le support qui est obligatoire. Il respecte donc la licence GPLv2 du kernel linux

Vous allez me posé la question: "Mais comment on peut faire pour apprendre à utiliser RHEL si c'est cher" ?

Et vous aurez bien raison de me poser la question. La réponse se situe dans les "enfants" de RHEL [voir la section](#les-distributions-enfants).

## Désavantages de RHEL

Comme expliqué plutôt, les releases de RHEL ont 10 ans de support. et certaines releases ne supporte pas beaucoup de paquets récent car cela rendrai le noyau instable. Donc, les vieilles releases peuvent être dépassé.

J'en ai déjà pu en parler, mais le prix de la licence (plus de 300$ la licence serveur sur 10 ans), ça fait mal au portefeuille, notamment quand on est une petite entreprise qui n'a pas les fond pour le faire.

## Les distributions enfants

RHEL étant payant, il fallait être en entreprise ou être vraiment motivé pour payé pour utilisé un système dans le monde du libre. 

Mais comme le code source de RHEL se doit d'être ouvert car ils sont soumis à la GPLv2, certaines personnes se sont amusés à tout recompiler (en changeant le logo) et à proposé des versions binairement compatible. Je vais en lister quelqu'uns :

- centOS : L'historique qui avait l'idée de faire ce fork. Mais depuis 2021, centOS est passé en mode "stream" donc il n'y a plus la stabilité de RHEL
- Rocky Linux : Le nouveau clone qui est 100% binairement compatible
- Alma Linux : Le nouveau clone à 99% comptabile car il opère une gestion de compatibilité avec des plus vieux systèmes que la version actuel. Et est géré par une association
- Fedora : Pas un clone car c'est Red Hat qui est en charge de la distribution. Mais un Red Hat tournée vers le poste client (et gratuit)

!!! info
    petit apparté sur Fedora, c'est une distribution qui a engendré énormément de distribution fille. Notamment du coté du jeux vidéos. Je pense en premier à Bazzite OS qui est vraiment un OS Clé en main pour jouer.