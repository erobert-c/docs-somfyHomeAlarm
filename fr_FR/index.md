---
layout: default
title: Somfy Home Alarm
lang: fr_FR
pluginId: SomfyHomeAlarm
---

# Plugin SomfyHomeAlarm

Ce plugin permet d'intéragir avec l'alarme Somfy Home Alarme depuis Jeedom. Certaines informations sont mise à jour en temps réel par Somfy, elles seront clairement identifié dans la liste des commandes de chaque équipement.

# Configuration du plugin
> **Tip**<br>
Afin d'utiliser le plugin, vous devez le télécharger, l'installer et l'activer comme tout plugin.

Une fois ceci fait, vous arriverez sur cette page:
![Configuration](https://erobert-c.github.io/docs-somfyHomeAlarm/images/configuration.png)

Renseignez simplement vos identifiants Somfy (les mêmes que sur l'application), et sauvegarder.

Il est recommandé de lancer l'installation des dépendances même si elles apparaissent OK. Enfin, assurez vous que le démon a bien été lancé.

# Scan des alarmes
Une fois la configuration effectuée, rendez-vous sur la page du plugin (Plugins->Sécurité->Somfy Home Alarm), et lancez le "Scan des alarmes"
![Scan](https://erobert-c.github.io/docs-somfyHomeAlarm/images/scan.png)

Le plugin va automatiquement créer les équipements associées à votre compte dans Jeedom.

## Le Site
Il s'agit de l'équipement principal du plugin. Celui ci donne le niveau d'activation de l'alarme, et indique si une alarme est en cours.

### Liste des commandes
* Niveau de sécurité (*mis à jour en temps réel*): Indique le niveau actuel d'activation de l'alarme.
    * disarmed: L'alarme n'est pas activée
    * partial: Correspond au mode "Nuit" (icône du cadenas noir et blanc de l'application)
    * armed: Armement total de l'alarme
* Alarme (*mis à jour en temps réel*): Indique si une alarme est en cours
* Refresh: Permet de forcer un refresh des informations du site
* Armement total: Active la protection en mode total (Niveau de sécurité=armed)
* Armement partiel: Active la protection en mode nuit (Niveau de sécurité=partial)
* Désarmer: Désactive la protection (Niveau de sécurité=disarmed)
* Panic: Déclenche la sirène. Une notification est envoyé à tous les utilisateurs configuré sur l'application.
* Alarme silencieuse: Déclenche une alarme sans déclencher la sirène. Une notification est envoyé à tous les utilisateurs configuré sur l'application.
* Stop: Arrête l'alarme (silencieuse ou non) cours

## Le link
Permet d'avoir les informations relative au link.

### Liste des commandes
* Diagnostic ok?: Indique si il y a un problème avec le link (par exemple, s'il n'est pas connecté à internet)
* Problèmes: Liste les problèmes éventuels
* Qualité Wifi: Indique la qualité de la connexion Wifi
* Qualité LoRa: Indique la qualité de la connexion LoRa si vous bénéficiez de ce service
* Mode alimentation: Indique si le link est alimenté sur secteur (*current*) ou sur batterie (*battery*)
* État alimentation: Binaire indiquant si le link est actuellement alimenté sur secteur
* Batterie: Niveau de batterie

## Sirènes intérieure et extérieure
Cet équipement permet de configurer les paramètres de la sirène intérieure.

### Liste des commandes
* Diagnostic ok?: Indique si il y a un problème avec la sirène (par exemple en cas de batterie faible)
* Problèmes: Liste les problèmes éventuels
* Qualité RLink: indique la qualité du lien radio entre la sirène et le Link
* Batterie: Indique le niveau de batterie de la sirène
* Lumière active: Indique si la notification lumineuse est active lors des changements de niveau de sécurité
* Notification sonore active: Indique si la notification sonore est active lors des changements de niveau de sécurité
* Autoprotect actif: Indique si l'autoprotection est active. Si elle est active, l'alarme se déclenchera si la sirène est déplacée alors que l'alarme est active
* Lumière ON: Active la notifcation lumineuse en cas de changement de niveau de sécurité
* Lumière OFF: Désactive la notifcation lumineuse en cas de changement de niveau de sécurité
* Son ON: Active la notifcation sonore en cas de changement de niveau de sécurité
* Son OFF: Désactive la notifcation sonore en cas de changement de niveau de sécurité
* Autoprotect ON: Active la fonction d'autoprotection
* Autoprotect OFF: Désactive la fonction d'autoprotection
* Température (**Sirène extérieure uniquement**): Indique la température mesurée par la sirène

## Badges
Cet équipement permet de configurer les badges (KeyFob). **Aucune information n'est retournée en temps réel, vous ne pourrez pas utiliser le plugin pour gérer la présence des membres à partir des badges !** Pour gérer la présence, vous pouvez cependant vous tourner vers le plugin BLEA qui gère ces badges.

### Liste des commandes
* Diagnostic ok?: Indique si il y a un problème avec le badge (par exemple en cas de batterie faible)
* Problèmes: Liste les problèmes éventuels
* Qualité RLink: indique la qualité du lien radio entre le badge et le Link
* Batterie: Indique le niveau de batterie du badge
* Actif: Indique si le badge est actif ou non (utilisé pour la désactivation auto de l'alarme)
* Activer: Permet d'activer le badge
* Désactiver: Permet de désactiver le badge

## Intellitags
Cet équipement permet de configurer les Intellitags. **Aucune information n'est retournée en temps réel, vous ne pourrez pas utiliser le plugin pour détecter quand une porte a été ouverte !**

### List des commandes
* Diagnostic ok?: Indique si il y a un problème avec l'intellitag (par exemple en cas de batterie faible)
* Problèmes: Liste les problèmes éventuels
* Qualité RLink: indique la qualité du lien radio entre l'intellitag et le Link
* Batterie: Indique le niveau de batterie de l'intellitag
* Recalibration nécessaire: Indique si la calibration (depuis l'application) de l'intellitag est nécessaire
* Couvercle présent: Indique si le couvercle de la batterie est présent
* Niveau de sensibilité: Indique le niveau de sensibilité de détection de l'intellitag
* Type de support: Indique sur quel type de support est actuellement monté l'intellitag
* Mode nuit actif: Indique si cet intellitag est actif pour le mode nuit (partial) ou non.
* Pré alarme active: Indique si l'alarme sera déclenchée immédiatement par l'intellitag ou s'il y aura une mise en garde sonore avant
* Sensibilité: Permet de régler le niveau de sensibilité de l'intellitag
* Mode nuit ON: Active l'intellitag quand l'alarme sera en mode nuit (partial)
* Mode nuit OFF: Désactive l'intellitag quand l'alarme sera en mode nuit (partial)
* Pre alarme ON: Active la mise en garde avant la sirène quand une intrusion est détectée par l'intellitag
* Pre alarme OFF: Désactive la mise en garde avant la sirène quand une intrusion est détectée par l'intellitag. La sirène se déclenchera immédiatement.

## PIR
Cet équipement permet de configurer les PIRs (détecteurs de mouvement). **Aucune information n'est retournée en temps réel, vous ne pourrez pas utiliser le plugin pour détecter quand il y a un mouvement !**

### Liste des commandes
* Diagnostic ok?: Indique si il y a un problème avec le PIR (par exemple en cas de batterie faible)
* Problèmes: Liste les problèmes éventuels
* Qualité RLink: indique la qualité du lien radio entre le PIR et le Link
* Batterie: Indique le niveau de batterie de le PIR
* Température: Indique la température mesurée par le détecteur
* Niveau de sensibilité: Indique le niveau de sensibilité de détection du détecteur de mouvement
* Autoprotect actif: Indique si l'autoprotection est active. Si elle est active, l'alarme se déclenchera si le détecteur est déplacée alors que l'alarme est active
* Lumière active: Indique si la notification lumineuse est active lors des changements de niveau de sécurité
* Mode nuit actif: Indique si ce détecteur est actif pour le mode nuit (partial) ou non.
* Pré alarme active: Indique si l'alarme sera déclenchée immédiatement par le détecteur ou s'il y aura une mise en garde sonore avant
* Sensibilité: Permet de régler le niveau de sensibilité du détecteur
* Autoprotect ON: Active la fonction d'autoprotection
* Autoprotect OFF: Désactive la fonction d'autoprotection
* Lumière ON: Active la notifcation lumineuse en cas de changement de niveau de sécurité
* Lumière OFF: Désactive la notifcation lumineuse en cas de changement de niveau de sécurité
* Mode nuit ON: Active le détecteur quand l'alarme sera en mode nuit (partial)
* Mode nuit OFF: Désactive le détecteur quand l'alarme sera en mode nuit (partial)
* Pre alarme ON: Active la mise en garde avant la sirène quand une intrusion est détectée par le détecteur
* Pre alarme OFF: Désactive la mise en garde avant la sirène quand une intrusion est détectée par le détecteur. La sirène se déclenchera immédiatement.
