---
title: Mon application ne fonctionne plus
description: "Résolution des problèmes liés au bug de base donnée corrompue."
---

**Chers utilisateurs : nous souhaitons premièrement nous excuser pour les problèmes rencontrés avant le correctif 0.9+138.
Nous rappelons que yNotes est une application en développement :  certaines fonctionnalités peuvent être encore incomplètes et des problèmes peuvent survenir, bien que nous faisons tout notre possible pour les éviter**

## Pourquoi mon application ne fonctionne plus ?
Vous aurez peut-être remarqué, si vous êtes un utilisateur plus ancien que le correctif 0.9+138 que votre application ne fonctionne plus hors ligne ou charge des éléments à l'infini.
Depuis un certain temps, nous avons remarqué que l'usage des **Notifications de nouveaux mails et de nouvelles notes** après une certaine periode d'utilisation pouvait **corrompre** la base de donnée utilisateur. C'est à dire que l'intégralité ou une partie des données hors ligne sont rendues inutilisables. C'est un problème grave qui a normalement été corrigé.

## Puis-je récupérer mes données hors ligne ?
Malheureusement, il est impossible de récupérer les **devoirs hors ligne, notes hors ligne et les éléments de l'agenda**.
Il est toutefois possible de sauver vos **devoirs épinglés et faits** ou bien simplement rester **connecté au service scolaire** mais en perdant le reste des autres données **si vous êtes un utilisateur Android**. 

### J'aimerais récupérer mes devoirs épinglés et/ou faits ou bien simplement rester connecté
* Rendez-vous, depuis l'explorateur de fichiers de votre choix, au chemin **(internal storage)/Android/data/fr.ynotes**.
* Supprimez les fichiers **offlinedata.hive** et **offlinedata.lock** ou bien l'intégralité des fichiers si récupérer le reste de vos données ne vous importe pas.
* Vous aurez dès lors supprimé les **devoirs hors ligne, notes hors ligne et les éléments de l'agenda** mais le reste des données restera disponible et vous resterez connecté.
### Je me moque de récupérer mes devoirs épinglés et/ou faits et de rester connecté
* Cette méthode est plus simple que la précédente mais **vous déconnectera** et vous empêchera de conserver la moindre donnée.
* Rendez-vous dans les Paramètres puis dans **Applications**, trouvez l'application **yNotes** puis rendez vous dans **Stockage**. Ici, cliquez sur **Effacer les données** et acceptez si on vous le demande. 
* Vous aurez alors supprimé **l'intégralité de vos données hors ligne et devrez vous reconnecter**. 