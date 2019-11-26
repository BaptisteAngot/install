# Installation d'un serveur Debian
- Tout d'abord installé Debian via le Microsoft Store
- Faite une mise à jours de Debian
	> sudo su
- Installer un serveur Apache
  > sudo apt-get install apache2
- Pour lancer votre serveur Apache : 
  > sudo service apache2 start
- Installer un serveur MariaDB :
  > sudo apt-get install mariadb-server
- Se connecter au serveur MariaDB:
  > sudo mysql -u root -p
 - Afin que le serveur Apache et MariaDB soit en relation :
   > sudo apt-get install php libapache2-mod-php php-mysql
- Installation de vim:
 > sudo apt-get install vim
- Installation de htop:
  > sudo apt-get install htop
- Veuillez redémarrer votre service Apache
> sudo service apache2 restart
- Installation de git: 
> sudo apt-get install git

# Installation de Composer sur Debian
- Télécharger les paquets suivants:
	>sudo apt install wget php-cli php-zip unzip
- Faites les commandes suivantes : 
	> php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
	> HASH="$(wget -q -O - https://composer.github.io/installer.sig)"
	> php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
- Si votre console marque "Installer verified", l'installation sera bien effectué, faite les commandes suivantes:
	> sudo php composer-setup.php --install-dir=/usr/local/bin –filename=composer
	
- Composer est bien installé, pour tester votre version de composer :
	> composer --version

# Changement de l'index.html
Le fichier par défaut se situe sur /var/www/html/index.html, veuillez le supprimé avec la commande et remplacé par un autre fichier tels que index.php
 > sudo rm -r /var/www/html/index.html
 >sudo  vim /var/www/html/index.php
