- Copiez votre dossier `wwww`dans `\vagrant` via la commande `cp -r /usr/share/nginx/www /vagrant/www`  

![](../../images/nginx_17.png)

- Faites en sorte que Nginx serve le dossier `wwww` situé sur la machine hôte et non pas sur la VM. Pour cela, deux étapes:
  - Supprimez le dossier `www` de votre VM via la commande `sudo rm -rf /usr/share/nginx/www` 
  - Créez un lien symbolique vers le dossier de la machine hôte via la commande `sudo ln -s /vagrant/www/ /usr/share/nginx/www`

- Ouvrez le fichier `index.html`, changez la propriété de couleur de page `bgcolor="white"`vers `bgcolor="red"`, puis sauvegardez le fichier.

![](../../images/nginx_18.png)

- Ouvrez votre navigateur puis
 entrez l'adresse forwardée du serveur Nginx, vous devriez obtenir une page sur fond rouge.

 ![](../../images/nginx_19.png)


- Changez maintenant le fichier `index.html` pour le mettre sur fond bleu.

![](../../images/nginx_20.png)

- Provisionnez ces changements directement sur le script shell afin que cela se fasse automatiquement:
  - Ouvrez le fichier `provision.sh`, rajoutez-y les commandes utilisées puis sauvegardez le fichier. ![](../../images/nginx_21.png)

  - Détruisez la VM après vous être délogué puis recréez la afin de valider ces changements. Lancez votre navigateur en ouvrant la page `localhost:8080`, le fond devrait être bleu à nouveau.  ![](../../images/nginx_20.png)

