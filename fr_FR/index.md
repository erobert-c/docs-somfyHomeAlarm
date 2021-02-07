---
layout: default
title: Somfy Home Alarm
lang: fr_FR
pluginId: SomfyHomeAlarm
---

# Plugin SomfyHomeAlarm

Plugin permettant de controller l'alarme Somfy Home Alarme depuis Jeedom.

# Configuration du plugin
Après le téléchargement du plugin, il vous suffit de l'activer, puis de renseigner vos identifiants Somfy Home Alarm.
![Configuration](https://erobert-c.github.io/docs-somfyHomeAlarm/images/configuration.png)

# Création des alarmes
Le plugin va automatiquement créer les alarmes associées à votre compte. Cliquez simplement sur "Scan des Alarmes" pour récupérer les alarmes et créer les commandes dans jeedom.

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
Pour le moment, le retour d'état n'est pas possible, et la solution pour avoir un retour "live" reste de passer par
IFTTT.
