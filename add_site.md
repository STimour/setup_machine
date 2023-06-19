# Configurer le host du site avec lamp

### Apache on Ubuntu 22.04 has one virtual host enabled by default that is configured to serve documents from the /var/www/html directory. While this works well for a single site, it can become unwieldy if you are hosting multiple sites. Instead of modifying /var/www/html, we’ll create a directory structure within /var/www for the your_domain site, leaving /var/www/html in place as the default directory to be served if a client request doesn’t match any other sites.
-------
     sudo mkdir /var/www/nom_domaine
## ensuite il faut donner les autorisation 
     sudo chown -R $USER:$USER /var/www/test
## Then, open a new configuration file in Apache’s sites-available directory using your preferred command-line editor. Here, we’ll use nano:
     sudo nano /etc/apache2/sites-available/your_domain.conf
### dans le fichier on met le code ci-dessous 
-------------------------------------------------------------------------
     <VirtualHost *:80>
         ServerName your_domain -> on change 
         ServerAlias www.your_domain -> on change 
         ServerAdmin webmaster@localhost -> on change 
         DocumentRoot /var/www/your_domain -> on change 
         ErrorLog ${APACHE_LOG_DIR}/error.log
         CustomLog ${APACHE_LOG_DIR}/access.log combined
     </VirtualHost>
-------------------------------------------------------------------------
## Now, use a2ensite to enable the new virtual host:
    sudo a2ensite your_domain
## To make sure your configuration file doesn’t contain syntax errors, run the following command:
    sudo apache2ctl configtest
### Finally, reload Apache so these changes take effect:
    sudo systemctl reload apache2
### Your new website is now active, but the web root /var/www/your_domain is still empty. Create an index.html file in that location to test that the virtual host works as expected:
    nano /var/www/your_domain/index.html
-------------------------------------------------------------------------
    <html>
         <title>your_domain website</title>
       <head>
       </head>
       <body>
         <h1>Hello World!</h1> 
         <p>This is the landing page of <strong>your_domain</strong>.</p>
       </body>
     </html>
-------------------------------------------------------------------------
### commande -> code . (permet ouvrir le vs dans le dossier courant)
