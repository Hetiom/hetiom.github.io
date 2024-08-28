**informations générales:** 
- ports par défaut: 2049
- All OS

# Explication

NFS, "Network File System" permet à un système de partager des répertoires et des fichiers avec d'autres sur un réseau. Les utilisateurs et les programmes peuvent accéder aux fichiers sur des systèmes distants presque comme s'il s'agissait de fichiers locaux. Pour ce faire, il monte tout ou partie d'un système de fichiers sur un serveur. La partie du système de fichiers montée est accessible aux clients avec les privilèges attribués à chaque fichier.

**fonctionnement:** Tout d'abord, le client demandera à monter un répertoire d'un hôte distant sur un répertoire local de la même manière qu'il peut monter un périphérique physique comme un disque dur. Le service de montage agira alors pour se connecter au daemon de montage approprié via RPC. 

Le serveur vérifie si l'utilisateur a la permission de monter le répertoire demandé. Il renvoie alors un handle de fichier qui identifie de manière unique chaque fichier et répertoire présent sur le serveur.

Si quelqu'un veut accéder à un fichier, un appel RPC est placé à NFSD (le daemon NFS) sur le serveur. Cet appel prend des paramètres tels que :
- Le handle du fichier
- Le nom du fichier auquel on veut accéder
- L'ID de l'utilisateur
- L'ID du groupe de l'utilisateur
Ces paramètres servent à déterminé les droits  d'accès aux fichiers demandés ainsi que leur permitions(lire, écrire,...)

# Enumération

voir notes (**Enumération**)
- utiliser **nfs-common**

**Monter le partage NFS:**
Pour commencer, il vous faudrat un dossier vide où monter le partage NFS. Pour monter le partage NFS il vous faudrat utiliser la commande "**mount**" avec cette Syntaxe: **sudo mount -t nfs [IP]:[share] /tmp/mount/ -nolock**

**Tag**                                                 **Function**
mount                                             monte le répertoire
-t                                                    spécifie le type de périphérique à monter
IP:share                                          L'adresse ip du serveur et le nom du partage
-nolock                                          précise de ne pas utiliser le verrouillage NLM

Il peut être intéressant de chercher une clé ssh pour pouvoir se connecter en ssh par la suite.

# Exploitation

**Parcours tracé:**   
  
Etape par étape des actions que nous prenons pour nous permettre d'obtenir un shell root :  
  
- Accès NFS ->  
- Gagnez un shell à faible privilège ->  
- Upload l'exécutable Bash sur le partage NFS ->  
- Définir les autorisations SUID via NFS en raison d'un squash racine mal configuré (**chmod +s**)->  
- Connectez-vous via SSH ->  
- Exécuter l'exécutable SUID Bit Bash ->  
- normalement root acces
