# Changelog plugin SomfyHomeAlarm

##07-02-2020
* Correction réactivation notification après délai (merci @Jenjen)
* Changement du comportement mode partial: le mode partial ne change plus l'état des notifications
* Ajout des commandes *Panic*, *Alarme Silencieuse* et *Stop*
  * Panic: Correspond à la commande "Déclencher la sirène" de l'application
  * Alarme Silencieuse: Correspond à la commande "Envoyer un SOS" de l'application
  * Permet d'arrêter l'alerte en cours. L'alarme retourne dans le statut où elle était avant l'alerte: elle reste
  activée si elle l'était


##30-12-2020
* Fix des URLs pour l'activation/désactivation des notifications

##24-11-2020
* Changement de la commande état pour 'armed', 'disarmed', 'partial' au lieu de 0 ou 1

##22-11-2020
Version beta initiale:
* Récupération du statut de l'alarme
* Activation/désactivation en mode total/partiel

