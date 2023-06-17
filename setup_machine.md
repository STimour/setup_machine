# I. WSL

#### Le Sous-système Windows pour Linux (WSL) permet aux développeurs d’installer une distribution Linux (comme Ubuntu, OpenSUSE, Kali, Debian, Arch Linux, etc.) et d’utiliser des applications, des utilitaires et des outils en ligne de commande Bash Linux directement sur Windows, sans modification, sans devoir passer par une machine virtuelle traditionnelle ou une configuration à double démarrage.

### Installer la commande WSL 
### PowerShell ->  wsl --install
#### Cette commande active les fonctionnalités nécessaires pour exécuter WSL et installer la distribution Ubuntu de Linux. (Cette distribution par défaut peut être changée).
- il faut redemarrer la machine 
### Modifier la distribution Linux par défaut installée
#### Par défaut, la distribution Linux installée sera Ubuntu. Elle peut être modifiée à l’aide de l’indicateur -d.
- Pour changer la distribution installée, entrez : wsl --install -d <Distribution Name>. Remplacez <Distribution Name> par le nom de la distribution que vous souhaitez installer.
- Pour afficher la liste des distributions Linux disponibles en téléchargement par le biais du magasin en ligne, entrez : wsl --list --online ou wsl -l -o.
- Pour installer des distributions Linux supplémentaires après l’installation initiale, vous pouvez également utiliser la commande : wsl --install -d <Distribution Name>.

### S'on tombe sur l'erreur vertualisation:
#### il faut soit passer dans le bios ou dans la barre de recherceh(windows) on cherhcer hyper-v et on l'active - si ça ne fonctionne pas il faut aller dans le bios (https://www.bleepingcomputer.com/tutorials/how-to-enable-cpu-virtualization-in-your-computer-bios/) 
- il faut redemarrer la machine ensuite pour que ça fonctionne


# II. GIT 
 
## installation sur linux
    sudo apt install git-all (-all en option)
## installation sur mac os
### - on verifie s'il y est avec le terminal
### s'il n'y est pas - l'ordi va nous proposer l'installation sinon on peut aller sur le site git-scm.com/download/mac
## installation sur windows
### - on va sur le site et on telecharge et on installe 
--------

## Configuration  

### rensegner le nom et adresse mail
    git config --global user.name "... ..."
    
    git config --global user.email "..." (il faut mettre le même mail qui dans le github)
### pour verifier qui est l'utilisateur
    git config --global --list

#### si on tappe juste git dans le terminl ça nous sortira les commandes utilisable


------------------------

## On peut passer à l'initialisation, avec "cd" on se met dans le dossier avec un projet puis on tappe 

    git init -> initialisation d'un projet git
### maitenant on peut faire 
    git status -> ça nous permet voir le status de projet et si les fichiers sont bien suivis
### pour faire suivre les fichier par le git on fait 
    git add <nom du fichier> ou . pour ajouter tout 

-------

