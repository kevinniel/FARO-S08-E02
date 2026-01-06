# Configuration de PM2 pour démarrer au lancement du système (BONUS)

Configurez PM2 pour démarrer automatiquement avec le système :
`pm2 startup systemd`

Copiez-collez la commande fournie dans le terminal.

Sauvegardez la configuration :
`pm2 save`

Redémarrez le serveur pour appliquer les changements :
`sudo reboot`

Pour gérer les processus PM2 :
`pm2 stop <nom> pour arrêter un processus`
`pm2 restart <nom> pour redémarrer un processus`
