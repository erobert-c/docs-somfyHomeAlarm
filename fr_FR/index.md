---
layout: default
title: Somfy Home Alarm
lang: fr_FR
pluginId: SomfyHomeAlarm
---

# Plugin SomfyHomeAlarm

Ce plugin permet de controller certaines fonctionnalités de l'alarme Somfy Home Alarme depuis Jeedom.

# Configuration du plugin
Après le téléchargement du plugin, il vous suffit de l'activer, puis de renseigner vos identifiants Somfy Home Alarm.
![Configuration](https://erobert-c.github.io/docs-somfyHomeAlarm/images/configuration.png)

# Création des alarmes
Une fois la configuration effectuée, rendez-vous sur la page du plugin, et lancez le "Scan des alarmes"
![Scan](https://erobert-c.github.io/docs-somfyHomeAlarm/images/scan.png)

Le plugin va automatiquement créer les alarmes associées à votre compte et créer les commandes dans jeedom.

## Commandes disponibles
- Armement total
- Armement partiel (nuit)
- Mode panic: Déclenchement de la sirène
- Alarme silencieuse: Activation de la fonction SOS de l'application
- Stop: Arrête l'alerte en cours
- Désactiver/activer notification
- Mode weekend: Désactive les notifications et passe en mode partiel
- Refresh: actualisation de l'état de l'alarme

## Retour d'état
Pour le moment, le retour d'état n'est pas possible, et la solution pour avoir un retour temps réel reste de passer par
IFTTT.
