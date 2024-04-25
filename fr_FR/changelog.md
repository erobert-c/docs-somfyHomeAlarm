# Changelog plugin SomfyHomeAlarm

## 25-04-2024
* Ajout support LinkTwo. Uniquement les fonctions du Link classiques sont implémentées
* Ajout d'une colonne avec les valeurs dans la vue des équipements
* Ajout des types génériques pour un début d'intégration avec le plugin homebridge. Intégration non testée, je ne possède pas le plugin homebridge
  * Nouvelle commande [Site][Mode]: Information donnant le dernier mode activé de l'alarme ('partial', 'armed'). Correspond au type générique `ALARM_MODE`
  * Nouvelle commande [Site][Enable]: Information donnant l'état de l'alarme. Correspond au type générique `ALARM_ENABLE_STATE`
  * La commande [Site][Armement total] a maintenant un type générique `ALARM_SET_MODE`. La commande passera la valeur de [Site][Mode] à `armed`, et activera l'alarme.
  * La commande [Site][Armement partiel] a maintenant un type générique `ALARM_SET_MODE`. La commande passera la valeur de [Site][Mode] à `partial`, et activera l'alarme.
  * La commande [Site][Désarmer] a maintenant un type générique `ALARM_RELEASED`.
  * La commande [Site][Activer] a maintenant un type générique `ALARM_ARMED`. La commande activera l'alarme dans le dernier mode où elle a été activée, se basant sur la valeur de la commande [Site][Mode].

## 28-07-2022
* Fix pour la mise à jour du statut de l'alarme en cas de déclenchement depuis Somfy

## 25-02-2022
* Ajout du display du Link Premium
* Fix du démon qui ne démarre pas si le mot de passe contient des caractères spéciaux

## 03-02-2022
* Ajout du type LinkPremium pour SomfyHomeAlarm Advanced
* Réorganisation des images pour Jeedom 4.2
* Ajout des infos de diagnostic pour les équipements

## 06-12-2021
* Retrait du package globals pour éviter problème d'installation sur debian 8
* Ajout de la dépendance sur packaging, pour pouvoir controler le numéro de version de websocket-client
* Gestion des anciennes versions de websocket-client on_close.

## 09-11-2021
* Correction du comportement si le refresh du security_level ne renvoie pas d'info. On ne change pas la valeur et on essaie à nouveau un refresh.
* Ajout d'un message dans jeedom en cas d'utilisation de commandes deprecated.
* Fix de la fonction on_close du websocket.

## 01-09-2021
**Mise à jour majeure, il faut acheter le plugin pour pouvoir faire la mise à jour**
* Ajout d'un démon pour le retour temps réel pour le niveau de sécurité et si alarme en cours
* Ajout du support de la configuration des différents périphériques (pas de retour temps réel)
  * Sirène intérieure et extérieure
  * Intellitag
  * PIR
  * Link
  * Badge
* **Ne plus utiliser la commande État**
  * L'activation de l'alarme est donnée par la commande [Site][Niveau de protection]
  * La commande [Site][Alarme] indique si une alarme est en cours
* **Ne plus utiliser les commandes Activer/Désactiver notification**
  * L'activation ou la désactivation des notifications se fait sur l'équipement [Sirène intérieure] ou [Sirène extérieure], avec les commandes [Son ON] et [Son OFF]
  * Les notifications lumineuses peuvent aussi être activées avec les commandes [Lunière ON] et [Lumière OFF]

## 07-02-2021
* Correction réactivation notification après délai (merci @Jenjen)
* Changement du comportement mode partial: le mode partial ne change plus l'état des notifications
* Ajout des commandes *Panic*, *Alarme Silencieuse* et *Stop*
  * Panic: Correspond à la commande "Déclencher la sirène" de l'application
  * Alarme Silencieuse: Correspond à la commande "Envoyer un SOS" de l'application
  * Permet d'arrêter l'alerte en cours. L'alarme retourne dans le statut où elle était avant l'alerte: elle reste
  activée si elle l'était


## 30-12-2020
* Fix des URLs pour l'activation/désactivation des notifications

## 24-11-2020
* Changement de la commande état pour 'armed', 'disarmed', 'partial' au lieu de 0 ou 1

## 22-11-2020
Version beta initiale:
* Récupération du statut de l'alarme
* Activation/désactivation en mode total/partiel
